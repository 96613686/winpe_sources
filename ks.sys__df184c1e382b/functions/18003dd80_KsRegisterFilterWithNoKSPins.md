# KsRegisterFilterWithNoKSPins

- ea: `0x18003dd80`
- end: `0x18003e099`
- name: `KsRegisterFilterWithNoKSPins`
- size: `793`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, const GUID *InterfaceClassGUID, ULONG PinCount, BOOL *PinDirection, KSPIN_MEDIUM *MediumList, GUID *CategoryList)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, registry_config`

## callers

- `0x1800716f0`

## callees

- `0x18001a000`
- `0x180034120`
- `0x18003dd80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18003dfa8`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003dfe5`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003dfa8`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003dfe5`
- `ntoskrnl!ZwClose` at `0x18003e020`
- `ntoskrnl!ZwClose` at `0x18003e020`
- `ntoskrnl!ZwSetValueKey` at `0x18003e00e`
- `ntoskrnl!ZwSetValueKey` at `0x18003e00e`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x18003dfc1`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x18003dfc1`
- `ntoskrnl!IoGetDeviceInterfaces` at `0x18003df7b`
- `ntoskrnl!IoGetDeviceInterfaces` at `0x18003df7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003e05a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003e06b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003e05a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003e06b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003ddfc`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003ddfc`

## pseudocode

```c
NTSTATUS __stdcall KsRegisterFilterWithNoKSPins(
        PDEVICE_OBJECT DeviceObject,
        const GUID *InterfaceClassGUID,
        ULONG PinCount,
        BOOL *PinDirection,
        KSPIN_MEDIUM *MediumList,
        GUID *CategoryList)
{
  __int64 v6; // rdi
  SIZE_T v9; // rsi
  _DWORD *PoolWithTag; // rax
  _DWORD *v11; // rbx
  void *Data; // r15
  int v13; // r10d
  _DWORD *v14; // rbx
  _DWORD *v15; // r8
  GUID *v16; // rsi
  unsigned int v17; // r11d
  __int64 v18; // r9
  bool v19; // cf
  __int64 v20; // rax
  __int64 v22; // r9
  __int64 v23; // rax
  GUID Set; // xmm0
  int DeviceInterfaces; // ebx
  __int64 i; // rsi
  void *DeviceInterfaceRegKey; // [rsp+30h] [rbp-30h] BYREF
  PZZWSTR SymbolicLinkList; // [rsp+38h] [rbp-28h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-20h] BYREF
  UNICODE_STRING ValueName; // [rsp+50h] [rbp-10h] BYREF

  v6 = PinCount;
  SymbolicLinkList = 0;
  if ( !PinCount || !InterfaceClassGUID || !PinDirection || !MediumList )
    return -1073741808;
  v9 = 16 * (CategoryList != 0 ? PinCount + 1 : 1) + 52 * PinCount;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, v9, 0x6466534Bu);
  v11 = PoolWithTag;
  if ( ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
      goto LABEL_8;
    return -1073741670;
  }
  if ( !PoolWithTag )
    return -1073741670;
  memset(PoolWithTag, 0, (unsigned int)v9);
LABEL_8:
  Data = v11;
  *v11 = 2;
  v13 = (int)v11;
  v11[1] = 0x200000;
  v11[2] = v6;
  v11[3] = 0;
  v14 = v11 + 4;
  v15 = &v14[7 * v6];
  v16 = (GUID *)&v15[6 * v6];
  if ( (_DWORD)v6 )
  {
    v17 = 0;
    if ( CategoryList )
    {
      v18 = 0;
      do
      {
        *v14 = 862548016;
        *(_BYTE *)v14 = v17 + 48;
        v14 += 7;
        v19 = PinDirection[v18];
        *(_QWORD *)(v14 - 5) = 1;
        *(v14 - 3) = 1;
        *(v14 - 1) = (_DWORD)v15 - v13;
        *(v14 - 6) = v19 ? 8 : 0;
        ++v17;
        *(KSPIN_MEDIUM *)v15 = MediumList[v18];
        *(v14 - 2) = (_DWORD)v16 - v13;
        v15 += 6;
        v20 = v18++;
        *v16++ = CategoryList[v20];
      }
      while ( v17 < (unsigned int)v6 );
    }
    else
    {
      v22 = 0;
      do
      {
        *v14 = 862548016;
        *(_BYTE *)v14 = v22 + 48;
        v14 += 7;
        v19 = PinDirection[v22];
        *(_QWORD *)(v14 - 5) = 1;
        *(v14 - 3) = 1;
        *(v14 - 1) = (_DWORD)v15 - v13;
        *(v14 - 6) = v19 ? 8 : 0;
        v23 = v22;
        Set = MediumList[v22].Set;
        v22 = (unsigned int)(v22 + 1);
        *(GUID *)v15 = Set;
        *((_QWORD *)v15 + 2) = *(&MediumList[v23].Alignment + 2);
        v15 += 6;
        *(v14 - 2) = 0;
      }
      while ( (unsigned int)v22 < (unsigned int)v6 );
    }
  }
  DeviceInterfaces = IoGetDeviceInterfaces(InterfaceClassGUID, DeviceObject, 1u, &SymbolicLinkList);
  if ( DeviceInterfaces >= 0 )
  {
    DeviceInterfaceRegKey = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, SymbolicLinkList);
    DeviceInterfaces = IoOpenDeviceInterfaceRegistryKey(&DestinationString, 0x1F0000u, &DeviceInterfaceRegKey);
    if ( DeviceInterfaces >= 0 )
    {
      ValueName = 0;
      RtlInitUnicodeString(&ValueName, L"FilterData");
      DeviceInterfaces = ZwSetValueKey(
                           DeviceInterfaceRegKey,
                           &ValueName,
                           0,
                           3u,
                           Data,
                           16 * (CategoryList != 0 ? v6 + 1 : 1) + 52 * v6);
      ZwClose(DeviceInterfaceRegKey);
    }
    for ( i = 0; (unsigned int)i < (unsigned int)v6; i = (unsigned int)(i + 1) )
      KsCacheMedium(&DestinationString, &MediumList[i], PinDirection[i]);
    ExFreePoolWithTag(SymbolicLinkList, 0);
  }
  ExFreePoolWithTag(Data, 0);
  return DeviceInterfaces;
}

```

## disassembly

```asm
0x18003dd80  mov     [rsp-38h+arg_8], rbx
0x18003dd85  mov     [rsp-38h+PhysicalDeviceObject], rcx
0x18003dd8a  push    rbp
0x18003dd8b  push    rsi
0x18003dd8c  push    rdi
0x18003dd8d  push    r12
0x18003dd8f  push    r13
0x18003dd91  push    r14
0x18003dd93  push    r15
0x18003dd95  mov     rbp, rsp
0x18003dd98  sub     rsp, 60h
0x18003dd9c  mov     edi, r8d
0x18003dd9f  mov     r12, r9
0x18003dda2  mov     [rbp+SymbolicLinkList], 0
0x18003ddaa  mov     r13, rdx
0x18003ddad  test    r8d, r8d
0x18003ddb0  jz      loc_18003E07B
0x18003ddb6  test    rdx, rdx
0x18003ddb9  jz      loc_18003E07B
0x18003ddbf  test    r9, r9
0x18003ddc2  jz      loc_18003E07B
0x18003ddc8  mov     r14, [rbp+MediumList]
0x18003ddcc  test    r14, r14
0x18003ddcf  jz      loc_18003E07B
0x18003ddd5  mov     rax, [rbp+CategoryList]
0x18003ddd9  mov     r8d, 6466534Bh; Tag
0x18003dddf  neg     rax
0x18003dde2  sbb     ecx, ecx
0x18003dde4  imul    eax, edi, 34h ; '4'
0x18003dde7  and     ecx, edi
0x18003dde9  inc     ecx
0x18003ddeb  shl     ecx, 4
0x18003ddee  add     eax, ecx
0x18003ddf0  mov     ecx, 401h; PoolType
0x18003ddf5  mov     edx, eax; NumberOfBytes
0x18003ddf7  mov     [rbp+arg_10], eax
0x18003ddfa  mov     esi, eax
0x18003ddfc  call    cs:__imp_ExAllocatePoolWithTag
0x18003de03  nop     dword ptr [rax+rax+00h]
0x18003de08  cmp     cs:ExPoolZeroingNativelySupported, 0
0x18003de0f  mov     rbx, rax
0x18003de12  jnz     loc_18003DEF4
0x18003de18  test    rax, rax
0x18003de1b  jz      loc_18003DEFD
0x18003de21  mov     r8d, esi; Size
0x18003de24  xor     edx, edx; Val
0x18003de26  mov     rcx, rax; void *
0x18003de29  call    memset
0x18003de2e  imul    r8, rdi, 1Ch
0x18003de32  mov     r15, rbx
0x18003de35  mov     dword ptr [rbx], 2
0x18003de3b  mov     r10, rbx
0x18003de3e  mov     dword ptr [rbx+4], 200000h
0x18003de45  mov     [rbx+8], edi
0x18003de48  lea     rax, [rdi+rdi*2]
0x18003de4c  mov     dword ptr [rbx+0Ch], 0
0x18003de53  add     rbx, 10h
0x18003de57  add     r8, rbx
0x18003de5a  lea     rsi, [r8+rax*8]
0x18003de5e  test    edi, edi
0x18003de60  jz      loc_18003DF6A
0x18003de66  mov     rdx, [rbp+CategoryList]
0x18003de6a  xor     r11d, r11d
0x18003de6d  test    rdx, rdx
0x18003de70  jz      loc_18003DF07
0x18003de76  xor     r9d, r9d
0x18003de79  mov     dword ptr [rbx], 33697030h
0x18003de7f  lea     eax, [r11+30h]
0x18003de83  mov     [rbx], al
0x18003de85  lea     rbx, [rbx+1Ch]
0x18003de89  mov     eax, [r12+r9*4]
0x18003de8d  neg     eax
0x18003de8f  mov     qword ptr [rbx-14h], 1
0x18003de97  mov     dword ptr [rbx-0Ch], 1
0x18003de9e  mov     eax, r8d
0x18003dea1  sbb     ecx, ecx
0x18003dea3  sub     eax, r10d
0x18003dea6  mov     [rbx-4], eax
0x18003dea9  and     ecx, 8
0x18003deac  mov     [rbx-18h], ecx
0x18003deaf  lea     rax, [r9+r9*2]
0x18003deb3  movups  xmm0, xmmword ptr [r14+rax*8]
0x18003deb8  inc     r11d
0x18003debb  movups  xmmword ptr [r8], xmm0
0x18003debf  movsd   xmm1, qword ptr [r14+rax*8+10h]
0x18003dec6  mov     eax, esi
0x18003dec8  sub     eax, r10d
0x18003decb  movsd   qword ptr [r8+10h], xmm1
0x18003ded1  mov     [rbx-8], eax
0x18003ded4  add     r8, 18h
0x18003ded8  mov     rax, r9
0x18003dedb  inc     r9
0x18003dede  add     rax, rax
0x18003dee1  movups  xmm0, xmmword ptr [rdx+rax*8]
0x18003dee5  movdqu  xmmword ptr [rsi], xmm0
0x18003dee9  add     rsi, 10h
0x18003deed  cmp     r11d, edi
0x18003def0  jb      short loc_18003DE79
0x18003def2  jmp     short loc_18003DF6A
0x18003def4  test    rbx, rbx
0x18003def7  jnz     loc_18003DE2E
0x18003defd  mov     eax, 0C000009Ah
0x18003df02  jmp     loc_18003E080
0x18003df07  xor     r9d, r9d
0x18003df0a  mov     dword ptr [rbx], 33697030h
0x18003df10  lea     eax, [r9+30h]
0x18003df14  mov     [rbx], al
0x18003df16  lea     rbx, [rbx+1Ch]
0x18003df1a  mov     eax, [r12+r9*4]
0x18003df1e  neg     eax
0x18003df20  mov     qword ptr [rbx-14h], 1
0x18003df28  mov     dword ptr [rbx-0Ch], 1
0x18003df2f  mov     eax, r8d
0x18003df32  sbb     ecx, ecx
0x18003df34  sub     eax, r10d
0x18003df37  mov     [rbx-4], eax
0x18003df3a  and     ecx, 8
0x18003df3d  mov     [rbx-18h], ecx
0x18003df40  lea     rax, [r9+r9*2]
0x18003df44  movups  xmm0, xmmword ptr [r14+rax*8]
0x18003df49  inc     r9d
0x18003df4c  movups  xmmword ptr [r8], xmm0
0x18003df50  movsd   xmm1, qword ptr [r14+rax*8+10h]
0x18003df57  movsd   qword ptr [r8+10h], xmm1
0x18003df5d  add     r8, 18h
0x18003df61  mov     [rbx-8], r11d
0x18003df65  cmp     r9d, edi
0x18003df68  jb      short loc_18003DF0A
0x18003df6a  mov     rdx, [rbp+PhysicalDeviceObject]; PhysicalDeviceObject
0x18003df6e  lea     r9, [rbp+SymbolicLinkList]; SymbolicLinkList
0x18003df72  mov     r8d, 1; Flags
0x18003df78  mov     rcx, r13; InterfaceClassGuid
0x18003df7b  call    cs:__imp_IoGetDeviceInterfaces
0x18003df82  nop     dword ptr [rax+rax+00h]
0x18003df87  mov     ebx, eax
0x18003df89  test    eax, eax
0x18003df8b  js      loc_18003E066
0x18003df91  mov     rdx, [rbp+SymbolicLinkList]; SourceString
0x18003df95  lea     rcx, [rbp+DestinationString]; DestinationString
0x18003df99  xorps   xmm0, xmm0
0x18003df9c  mov     [rbp+DeviceInterfaceRegKey], 0
0x18003dfa4  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18003dfa8  call    cs:__imp_RtlInitUnicodeString
0x18003dfaf  nop     dword ptr [rax+rax+00h]
0x18003dfb4  lea     r8, [rbp+DeviceInterfaceRegKey]; DeviceInterfaceRegKey
0x18003dfb8  mov     edx, 1F0000h; DesiredAccess
0x18003dfbd  lea     rcx, [rbp+DestinationString]; SymbolicLinkName
0x18003dfc1  call    cs:__imp_IoOpenDeviceInterfaceRegistryKey
0x18003dfc8  nop     dword ptr [rax+rax+00h]
0x18003dfcd  mov     ebx, eax
0x18003dfcf  test    eax, eax
0x18003dfd1  js      short loc_18003E02C
0x18003dfd3  xorps   xmm0, xmm0
0x18003dfd6  lea     rdx, aFilterdata; "FilterData"
0x18003dfdd  lea     rcx, [rbp+ValueName]; DestinationString
0x18003dfe1  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x18003dfe5  call    cs:__imp_RtlInitUnicodeString
0x18003dfec  nop     dword ptr [rax+rax+00h]
0x18003dff1  mov     eax, [rbp+arg_10]
0x18003dff4  lea     rdx, [rbp+ValueName]; ValueName
0x18003dff8  mov     rcx, [rbp+DeviceInterfaceRegKey]; KeyHandle
0x18003dffc  mov     r9d, 3; Type
0x18003e002  mov     [rsp+60h+DataSize], eax; DataSize
0x18003e006  xor     r8d, r8d; TitleIndex
0x18003e009  mov     [rsp+60h+Data], r15; Data
0x18003e00e  call    cs:__imp_ZwSetValueKey
0x18003e015  nop     dword ptr [rax+rax+00h]
0x18003e01a  mov     rcx, [rbp+DeviceInterfaceRegKey]; Handle
0x18003e01e  mov     ebx, eax
0x18003e020  call    cs:__imp_ZwClose
0x18003e027  nop     dword ptr [rax+rax+00h]
0x18003e02c  xor     esi, esi
0x18003e02e  test    edi, edi
0x18003e030  jz      short loc_18003E054
0x18003e032  xor     r8d, r8d
0x18003e035  lea     rax, [rsi+rsi*2]
0x18003e039  cmp     [r12+rsi*4], r8d
0x18003e03d  lea     rdx, [r14+rax*8]; Medium
0x18003e041  lea     rcx, [rbp+DestinationString]; SymbolicLink
0x18003e045  setnz   r8b; PinDirection
0x18003e049  call    KsCacheMedium
0x18003e04e  inc     esi
0x18003e050  cmp     esi, edi
0x18003e052  jb      short loc_18003E032
0x18003e054  mov     rcx, [rbp+SymbolicLinkList]; P
0x18003e058  xor     edx, edx; Tag
0x18003e05a  call    cs:__imp_ExFreePoolWithTag
0x18003e061  nop     dword ptr [rax+rax+00h]
0x18003e066  xor     edx, edx; Tag
0x18003e068  mov     rcx, r15; P
0x18003e06b  call    cs:__imp_ExFreePoolWithTag
0x18003e072  nop     dword ptr [rax+rax+00h]
0x18003e077  mov     eax, ebx
0x18003e079  jmp     short loc_18003E080
0x18003e07b  mov     eax, 0C0000010h
0x18003e080  mov     rbx, [rsp+60h+arg_8]
0x18003e088  add     rsp, 60h
0x18003e08c  pop     r15
0x18003e08e  pop     r14
0x18003e090  pop     r13
0x18003e092  pop     r12
0x18003e094  pop     rdi
0x18003e095  pop     rsi
0x18003e096  pop     rbp
0x18003e097  retn
```
