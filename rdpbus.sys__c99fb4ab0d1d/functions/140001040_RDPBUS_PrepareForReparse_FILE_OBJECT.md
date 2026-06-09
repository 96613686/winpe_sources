# RDPBUS_PrepareForReparse(_FILE_OBJECT *)

- ea: `0x140001040`
- end: `0x14000144f`
- name: `?RDPBUS_PrepareForReparse@@YAJPEAU_FILE_OBJECT@@@Z`
- size: `1039`
- prototype: `__int64 __fastcall(struct _FILE_OBJECT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callers

- `0x140001460`

## callees

- `0x140001040`
- `0x1400020b4`
- `0x1400020e4`
- `0x1400021f4`
- `0x140002640`

## import_xrefs

- `ntoskrnl!IoRegisterDeviceInterface` at `0x1400010db`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1400010db`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000113e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000113e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001180`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001180`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x14000112c`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x14000112c`
- `ntoskrnl!ExAllocatePool2` at `0x140001214`
- `ntoskrnl!ExAllocatePool2` at `0x1400013b0`
- `ntoskrnl!ExAllocatePool2` at `0x140001214`
- `ntoskrnl!ExAllocatePool2` at `0x1400013b0`
- `ntoskrnl!ExFreePool` at `0x1400012dd`
- `ntoskrnl!ExFreePool` at `0x140001429`
- `ntoskrnl!ExFreePool` at `0x1400012dd`
- `ntoskrnl!ExFreePool` at `0x140001429`
- `ntoskrnl!ZwQueryValueKey` at `0x1400011ab`
- `ntoskrnl!ZwQueryValueKey` at `0x140001321`
- `ntoskrnl!ZwQueryValueKey` at `0x1400011ab`
- `ntoskrnl!ZwQueryValueKey` at `0x140001321`
- `ntoskrnl!ZwClose` at `0x1400012c9`
- `ntoskrnl!ZwClose` at `0x1400012c9`

## pseudocode

```c
__int64 __fastcall RDPBUS_PrepareForReparse(struct _FILE_OBJECT *a1)
{
  _WORD *Pool2; // r14
  UNICODE_STRING FileName; // xmm0
  unsigned __int16 v4; // cx
  __int64 v5; // rdx
  unsigned int v6; // ebx
  __int64 v7; // r8
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  __int64 v11; // rax
  __int16 v13; // cx
  __int64 v14; // rdx
  __int64 v15; // r13
  __int64 v16; // rax
  __int64 v17; // rax
  wchar_t *v18; // rbx
  unsigned __int16 v19; // [rsp+30h] [rbp-19h]
  struct _UNICODE_STRING ReferenceString; // [rsp+38h] [rbp-11h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+48h] [rbp-1h] BYREF
  __int16 v22; // [rsp+B0h] [rbp+67h]
  ULONG ResultLength; // [rsp+B8h] [rbp+6Fh] BYREF
  void *DeviceInterfaceRegKey; // [rsp+C0h] [rbp+77h] BYREF
  __int64 v25; // [rsp+C8h] [rbp+7Fh]

  Pool2 = 0;
  a1->FsContext = 0;
  SymbolicLinkName = 0;
  a1->FsContext2 = 0;
  FileName = a1->FileName;
  DeviceInterfaceRegKey = 0;
  v4 = _mm_cvtsi128_si32((__m128i)FileName);
  ResultLength = 0;
  ReferenceString = FileName;
  if ( v4 >= 2u && ReferenceString.MaximumLength >= 2u && *ReferenceString.Buffer == 92 )
  {
    ++ReferenceString.Buffer;
    ReferenceString.MaximumLength -= 2;
    ReferenceString.Length = v4 - 2;
  }
  v6 = IoRegisterDeviceInterface(RDPDYN_PDO, &InterfaceClassGuid, &ReferenceString, &SymbolicLinkName);
  if ( v6 )
    goto LABEL_15;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids);
  v6 = IoOpenDeviceInterfaceRegistryKey(&SymbolicLinkName, 0xF003Fu, &DeviceInterfaceRegKey);
  RtlFreeUnicodeString(&SymbolicLinkName);
  if ( v6 )
  {
LABEL_15:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids, v6);
    DeviceInterfaceRegKey = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids);
    RtlInitUnicodeString(&ReferenceString, L"Client Device Name");
    v6 = ZwQueryValueKey(DeviceInterfaceRegKey, &ReferenceString, KeyValuePartialInformation, 0, 0, &ResultLength);
  }
  if ( v6 != -1073741789 )
  {
    if ( v6 )
      goto LABEL_25;
    goto LABEL_37;
  }
  Pool2 = (_WORD *)ExAllocatePool2(64, ResultLength, 1114662002);
  if ( Pool2 )
  {
LABEL_37:
    v6 = ZwQueryValueKey(
           DeviceInterfaceRegKey,
           &ReferenceString,
           KeyValuePartialInformation,
           Pool2,
           ResultLength,
           &ResultLength);
    if ( v6 )
      goto LABEL_25;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids);
    v11 = -1;
    while ( Pool2[v11++ + 7] != 0 )
      ;
    v13 = Pool2[6];
    v14 = 2 * v11;
    v25 = 2 * v11;
    v22 = v13;
    v15 = 26;
    v16 = 26;
    if ( v13 != 92 )
      v16 = 28;
    v19 = v14 + v16;
    v17 = ExAllocatePool2(64, v14 + v16 + 2, 1114662002);
    v18 = (wchar_t *)v17;
    if ( v17 )
    {
      *(_OWORD *)v17 = *(_OWORD *)L"\\Device\\RdpDr";
      *(_OWORD *)(v17 + 10) = *(_OWORD *)L"ce\\RdpDr";
      if ( v22 != 92 )
      {
        *(_WORD *)(v17 + 26) = 92;
        v15 = 28;
      }
      memmove((void *)(v17 + v15), Pool2 + 6, v25 + 2);
      ExFreePool(a1->FileName.Buffer);
      a1->FileName.Buffer = v18;
      v6 = 260;
      a1->FileName.Length = v19;
      a1->FileName.MaximumLength = v19;
      goto LABEL_28;
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      goto LABEL_24;
    v9 = 17;
    goto LABEL_23;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    goto LABEL_24;
  v9 = 15;
LABEL_23:
  WPP_SF_(v8->AttachedDevice, v9, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids);
LABEL_24:
  v6 = -1073741670;
LABEL_25:
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_31;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids, v6);
LABEL_28:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, v5, v7, &a1->FileName);
LABEL_31:
  if ( DeviceInterfaceRegKey )
    ZwClose(DeviceInterfaceRegKey);
  if ( Pool2 )
    ExFreePool(Pool2);
  return v6;
}

```

## disassembly

```asm
0x140001040  push    rbp
0x140001042  push    rbx
0x140001043  push    r14
0x140001045  lea     rbp, [rsp-47h]
0x14000104a  sub     rsp, 90h
0x140001051  xor     r14d, r14d
0x140001054  mov     [rsp+0A0h+var_18], rsi
0x14000105c  xorps   xmm0, xmm0
0x14000105f  mov     [rcx+18h], r14
0x140001063  movups  xmmword ptr [rbp+57h+SymbolicLinkName.Length], xmm0
0x140001067  mov     rsi, rcx
0x14000106a  mov     [rcx+20h], r14
0x14000106e  movups  xmm0, xmmword ptr [rcx+58h]
0x140001072  mov     [rsp+0A0h+var_38], r15
0x140001077  mov     [rbp+57h+DeviceInterfaceRegKey], r14
0x14000107b  movd    ecx, xmm0
0x14000107f  mov     [rbp+57h+arg_8], r14d
0x140001083  movups  xmmword ptr [rbp+57h+ReferenceString.Length], xmm0
0x140001087  cmp     cx, 2
0x14000108b  jb      short loc_1400010BD
0x14000108d  mov     rax, qword ptr [rbp+57h+ReferenceString.Length]
0x140001091  shr     rax, 10h
0x140001095  cmp     ax, 2
0x140001099  jb      short loc_1400010BD
0x14000109b  mov     rax, [rbp+57h+ReferenceString.Buffer]
0x14000109f  cmp     word ptr [rax], 5Ch ; '\'
0x1400010a3  jnz     short loc_1400010BD
0x1400010a5  add     rax, 2
0x1400010a9  mov     [rbp+57h+ReferenceString.Buffer], rax
0x1400010ad  mov     eax, 0FFFEh
0x1400010b2  add     cx, ax
0x1400010b5  add     [rbp+57h+ReferenceString.MaximumLength], ax
0x1400010b9  mov     [rbp+57h+ReferenceString.Length], cx
0x1400010bd  mov     rcx, cs:?RDPDYN_PDO@@3PEAU_DEVICE_OBJECT@@EA; PhysicalDeviceObject
0x1400010c4  lea     r9, [rbp+57h+SymbolicLinkName]; SymbolicLinkName
0x1400010c8  lea     r8, [rbp+57h+ReferenceString]; ReferenceString
0x1400010cc  mov     [rsp+0A0h+var_20], rdi
0x1400010d4  lea     rdx, InterfaceClassGuid; InterfaceClassGuid
0x1400010db  call    cs:__imp_IoRegisterDeviceInterface
0x1400010e2  nop     dword ptr [rax+rax+00h]
0x1400010e7  mov     ebx, eax
0x1400010e9  test    eax, eax
0x1400010eb  jnz     loc_1400011BB
0x1400010f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400010f8  lea     rdi, WPP_GLOBAL_Control
0x1400010ff  cmp     rcx, rdi
0x140001102  jz      short loc_14000111F
0x140001104  cmp     byte ptr [rcx+29h], 2
0x140001108  jb      short loc_14000111F
0x14000110a  mov     rcx, [rcx+18h]
0x14000110e  lea     r8, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids
0x140001115  mov     edx, 0Ch
0x14000111a  call    WPP_SF_
0x14000111f  lea     r8, [rbp+57h+DeviceInterfaceRegKey]; DeviceInterfaceRegKey
0x140001123  mov     edx, 0F003Fh; DesiredAccess
0x140001128  lea     rcx, [rbp+57h+SymbolicLinkName]; SymbolicLinkName
0x14000112c  call    cs:__imp_IoOpenDeviceInterfaceRegistryKey
0x140001133  nop     dword ptr [rax+rax+00h]
0x140001138  lea     rcx, [rbp+57h+SymbolicLinkName]; UnicodeString
0x14000113c  mov     ebx, eax
0x14000113e  call    cs:__imp_RtlFreeUnicodeString
0x140001145  nop     dword ptr [rax+rax+00h]
0x14000114a  test    ebx, ebx
0x14000114c  jnz     short loc_1400011C2
0x14000114e  mov     rcx, cs:WPP_GLOBAL_Control
0x140001155  cmp     rcx, rdi
0x140001158  jz      short loc_140001175
0x14000115a  cmp     byte ptr [rcx+29h], 4
0x14000115e  jb      short loc_140001175
0x140001160  mov     rcx, [rcx+18h]
0x140001164  lea     r8, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids
0x14000116b  mov     edx, 0Dh
0x140001170  call    WPP_SF_
0x140001175  lea     rdx, SourceString; "Client Device Name"
0x14000117c  lea     rcx, [rbp+57h+ReferenceString]; DestinationString
0x140001180  call    cs:__imp_RtlInitUnicodeString
0x140001187  nop     dword ptr [rax+rax+00h]
0x14000118c  mov     rcx, [rbp+57h+DeviceInterfaceRegKey]; KeyHandle
0x140001190  lea     rax, [rbp+57h+arg_8]
0x140001194  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x140001199  lea     rdx, [rbp+57h+ReferenceString]; ValueName
0x14000119d  xor     r9d, r9d; KeyValueInformation
0x1400011a0  mov     [rsp+0A0h+Length], r14d; Length
0x1400011a5  mov     r8d, 2; KeyValueInformationClass
0x1400011ab  call    cs:__imp_ZwQueryValueKey
0x1400011b2  nop     dword ptr [rax+rax+00h]
0x1400011b7  mov     ebx, eax
0x1400011b9  jmp     short loc_1400011F0
0x1400011bb  lea     rdi, WPP_GLOBAL_Control
0x1400011c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400011c9  cmp     rcx, rdi
0x1400011cc  jz      short loc_1400011EC
0x1400011ce  cmp     byte ptr [rcx+29h], 4
0x1400011d2  jb      short loc_1400011EC
0x1400011d4  mov     rcx, [rcx+18h]
0x1400011d8  lea     r8, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids
0x1400011df  mov     edx, 0Eh
0x1400011e4  mov     r9d, ebx
0x1400011e7  call    WPP_SF_D
0x1400011ec  mov     [rbp+57h+DeviceInterfaceRegKey], r14
0x1400011f0  mov     [rsp+0A0h+var_28], r12
0x1400011f5  mov     [rsp+0A0h+var_30], r13
0x1400011fa  cmp     ebx, 0C0000023h
0x140001200  jnz     loc_1400012F8
0x140001206  mov     edx, [rbp+57h+arg_8]
0x140001209  mov     ecx, 40h ; '@'
0x14000120e  mov     r8d, 42706472h
0x140001214  call    cs:__imp_ExAllocatePool2
0x14000121b  nop     dword ptr [rax+rax+00h]
0x140001220  mov     r14, rax
0x140001223  test    rax, rax
0x140001226  jnz     loc_140001300
0x14000122c  mov     rcx, cs:WPP_GLOBAL_Control
0x140001233  cmp     rcx, rdi
0x140001236  jz      short loc_140001253
0x140001238  cmp     byte ptr [rcx+29h], 4
0x14000123c  jb      short loc_140001253
0x14000123e  mov     edx, 0Fh
0x140001243  mov     rcx, [rcx+18h]
0x140001247  lea     r8, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids
0x14000124e  call    WPP_SF_
0x140001253  mov     ebx, 0C000009Ah
0x140001258  mov     rcx, cs:WPP_GLOBAL_Control
0x14000125f  cmp     rcx, rdi
0x140001262  jz      short loc_1400012A1
0x140001264  cmp     byte ptr [rcx+29h], 2
0x140001268  jb      short loc_140001282
0x14000126a  mov     rcx, [rcx+18h]
0x14000126e  lea     r8, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids
0x140001275  mov     edx, 12h
0x14000127a  mov     r9d, ebx
0x14000127d  call    WPP_SF_D
0x140001282  mov     rcx, cs:WPP_GLOBAL_Control
0x140001289  cmp     rcx, rdi
0x14000128c  jz      short loc_1400012A1
0x14000128e  cmp     byte ptr [rcx+29h], 4
0x140001292  jb      short loc_1400012A1
0x140001294  mov     rcx, [rcx+18h]
0x140001298  lea     r9, [rsi+58h]
0x14000129c  call    WPP_SF_Z
0x1400012a1  mov     rcx, [rbp+57h+DeviceInterfaceRegKey]; Handle
0x1400012a5  mov     r15, [rsp+0A0h+var_38]
0x1400012aa  mov     r13, [rsp+0A0h+var_30]
0x1400012af  mov     r12, [rsp+0A0h+var_28]
0x1400012b4  mov     rdi, [rsp+0A0h+var_20]
0x1400012bc  mov     rsi, [rsp+0A0h+var_18]
0x1400012c4  test    rcx, rcx
0x1400012c7  jz      short loc_1400012D5
0x1400012c9  call    cs:__imp_ZwClose
0x1400012d0  nop     dword ptr [rax+rax+00h]
0x1400012d5  test    r14, r14
0x1400012d8  jz      short loc_1400012E9
0x1400012da  mov     rcx, r14; P
0x1400012dd  call    cs:__imp_ExFreePool
0x1400012e4  nop     dword ptr [rax+rax+00h]
0x1400012e9  mov     eax, ebx
0x1400012eb  add     rsp, 90h
0x1400012f2  pop     r14
0x1400012f4  pop     rbx
0x1400012f5  pop     rbp
0x1400012f6  retn
0x1400012f8  test    ebx, ebx
0x1400012fa  jnz     loc_140001258
0x140001300  mov     rcx, [rbp+57h+DeviceInterfaceRegKey]; KeyHandle
0x140001304  lea     rax, [rbp+57h+arg_8]
0x140001308  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x14000130d  lea     rdx, [rbp+57h+ReferenceString]; ValueName
0x140001311  mov     eax, [rbp+57h+arg_8]
0x140001314  mov     r9, r14; KeyValueInformation
0x140001317  mov     r8d, 2; KeyValueInformationClass
0x14000131d  mov     [rsp+0A0h+Length], eax; Length
0x140001321  call    cs:__imp_ZwQueryValueKey
0x140001328  nop     dword ptr [rax+rax+00h]
0x14000132d  mov     ebx, eax
0x14000132f  test    eax, eax
0x140001331  jnz     loc_140001258
0x140001337  mov     rcx, cs:WPP_GLOBAL_Control
0x14000133e  cmp     rcx, rdi
0x140001341  jz      short loc_14000135E
0x140001343  cmp     byte ptr [rcx+29h], 4
0x140001347  jb      short loc_14000135E
0x140001349  mov     rcx, [rcx+18h]
0x14000134d  lea     r8, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids
0x140001354  mov     edx, 10h
0x140001359  call    WPP_SF_
0x14000135e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140001365  cmp     word ptr [r14+rax*2+0Eh], 0
0x14000136c  lea     rax, [rax+1]
0x140001370  jnz     short loc_140001365
0x140001372  movzx   ecx, word ptr [r14+0Ch]
0x140001377  lea     rdx, [rax+rax]
0x14000137b  cmp     cx, 5Ch ; '\'
0x14000137f  mov     [rbp+57h+arg_18], rdx
0x140001383  mov     r8d, 1Ch
0x140001389  mov     [rbp+57h+arg_0], cx
0x14000138d  mov     r13d, 1Ah
0x140001393  mov     ecx, 40h ; '@'
0x140001398  mov     eax, r13d
0x14000139b  cmovnz  eax, r8d
0x14000139f  mov     r8d, 42706472h
0x1400013a5  add     rax, rdx
0x1400013a8  mov     [rbp+57h+var_70], rax
0x1400013ac  lea     rdx, [rax+2]
0x1400013b0  call    cs:__imp_ExAllocatePool2
0x1400013b7  nop     dword ptr [rax+rax+00h]
0x1400013bc  mov     rbx, rax
0x1400013bf  test    rax, rax
0x1400013c2  jnz     short loc_1400013E8
0x1400013c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400013cb  cmp     rcx, rdi
0x1400013ce  jz      loc_140001253
0x1400013d4  cmp     byte ptr [rcx+29h], 4
0x1400013d8  jb      loc_140001253
0x1400013de  mov     edx, 11h
0x1400013e3  jmp     loc_140001243
0x1400013e8  cmp     [rbp+57h+arg_0], 5Ch ; '\'
0x1400013ed  movups  xmm0, xmmword ptr cs:aDeviceRdpdr; "\\Device\\RdpDr"
0x1400013f4  movups  xmm1, xmmword ptr cs:aDeviceRdpdr+0Ah; "ce\\RdpDr"
0x1400013fb  movups  xmmword ptr [rax], xmm0
0x1400013fe  movups  xmmword ptr [rax+0Ah], xmm1
0x140001402  jz      short loc_140001410
0x140001404  mov     word ptr [rax+1Ah], 5Ch ; '\'
0x14000140a  mov     r13d, 1Ch
0x140001410  mov     r8, [rbp+57h+arg_18]
0x140001414  lea     rcx, [rax+r13]; void *
0x140001418  add     r8, 2; Size
0x14000141c  lea     rdx, [r14+0Ch]; Src
0x140001420  call    memmove
0x140001425  mov     rcx, [rsi+60h]; P
0x140001429  call    cs:__imp_ExFreePool
0x140001430  nop     dword ptr [rax+rax+00h]
0x140001435  mov     rax, [rbp+57h+var_70]
0x140001439  mov     [rsi+60h], rbx
0x14000143d  mov     ebx, 104h
0x140001442  mov     [rsi+58h], ax
0x140001446  mov     [rsi+5Ah], ax
0x14000144a  jmp     loc_140001282
```
