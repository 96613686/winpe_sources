# HidpGetComboHardwareIdV2Enabled

- ea: `0x1800377e0`
- end: `0x180037b1a`
- name: `HidpGetComboHardwareIdV2Enabled`
- size: `826`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a590`

## callees

- `0x18000ddc8`
- `0x180014e80`
- `0x1800377e0`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x1800379b8`
- `ntoskrnl!ZwQueryValueKey` at `0x1800379b8`
- `ntoskrnl!ZwClose` at `0x180037afd`
- `ntoskrnl!ZwClose` at `0x180037afd`
- `ntoskrnl!ExFreePoolWithTag` at `0x180037ae8`
- `ntoskrnl!ExFreePoolWithTag` at `0x180037ae8`
- `ntoskrnl!ExAllocatePool2` at `0x1800378f1`
- `ntoskrnl!ExAllocatePool2` at `0x1800378f1`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x180037826`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x180037826`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800378ce`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800378ce`

## string_xrefs

- `0x1800378c3`: `ComboHardwareIdV2Enabled`

## pseudocode

```c
void __fastcall HidpGetComboHardwareIdV2Enabled(__int64 *a1, struct _DEVICE_OBJECT *a2)
{
  char v3; // bl
  NTSTATUS v4; // edx
  int v5; // r8d
  int v6; // edx
  unsigned int *Pool2; // rdi
  int v8; // r8d
  NTSTATUS v9; // eax
  int v10; // r8d
  NTSTATUS v11; // edx
  PDEVICE_OBJECT v12; // r10
  bool v13; // dl
  char Length; // [rsp+20h] [rbp-50h]
  __int16 v15; // [rsp+30h] [rbp-40h]
  __int64 v16; // [rsp+40h] [rbp-30h]
  char v17; // [rsp+48h] [rbp-28h]
  char v18; // [rsp+48h] [rbp-28h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-10h] BYREF
  ULONG ResultLength; // [rsp+90h] [rbp+20h] BYREF
  void *DeviceRegKey; // [rsp+A0h] [rbp+30h] BYREF

  *((_BYTE *)a1 + 1977) = 0;
  DeviceRegKey = 0;
  ResultLength = 0;
  v3 = 1;
  DestinationString = 0;
  v4 = IoOpenDeviceRegistryKey(a2, 1u, 0x1F0000u, &DeviceRegKey);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v3 = 0;
    }
    if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v17 = v4;
      LOBYTE(v4) = v3;
      LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v4,
        v5,
        a1[84],
        2,
        3,
        19,
        (__int64)WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids,
        *a1,
        v17);
    }
    goto LABEL_36;
  }
  RtlInitUnicodeString(&DestinationString, L"ComboHardwareIdV2Enabled");
  ResultLength = DestinationString.MaximumLength + 28;
  Pool2 = (unsigned int *)ExAllocatePool2(256, ResultLength, 1130654024);
  if ( Pool2 )
  {
    v9 = ZwQueryValueKey(DeviceRegKey, &DestinationString, KeyValueFullInformation, Pool2, ResultLength, &ResultLength);
    v11 = v9;
    if ( v9 >= 0 )
    {
      if ( Pool2[3] != 4 )
        goto LABEL_35;
      v13 = *(unsigned int *)((char *)Pool2 + Pool2[2]) != 0;
      *((_BYTE *)a1 + 1977) = v13;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v3 = 0;
      }
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v3 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_35;
      v18 = v13;
      v16 = *a1;
      v15 = 22;
      Length = 4;
    }
    else
    {
      if ( v9 == -1073741772 )
        goto LABEL_35;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        v3 = 0;
      }
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v3 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_35;
      v18 = v9;
      v16 = *a1;
      v15 = 21;
      Length = 3;
    }
    LOBYTE(v11) = v3;
    WPP_RECORDER_AND_TRACE_SF_qL(
      v12->AttachedDevice,
      v11,
      v10,
      a1[84],
      Length,
      3,
      v15,
      (__int64)WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids,
      v16,
      v18);
LABEL_35:
    ExFreePoolWithTag(Pool2, 0);
    goto LABEL_36;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
  {
    v3 = 0;
  }
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = v3;
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_qLL(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      v8,
      a1[84],
      2,
      3,
      20,
      (__int64)WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids,
      *a1,
      ResultLength,
      154);
  }
LABEL_36:
  if ( DeviceRegKey )
    ZwClose(DeviceRegKey);
}

```

## disassembly

```asm
0x1800377e0  mov     [rsp-18h+arg_8], rbx
0x1800377e5  push    rbp
0x1800377e6  push    rsi
0x1800377e7  push    rdi
0x1800377e8  mov     rbp, rsp
0x1800377eb  sub     rsp, 70h
0x1800377ef  mov     rax, rdx
0x1800377f2  mov     byte ptr [rcx+7B9h], 0
0x1800377f9  mov     rsi, rcx
0x1800377fc  mov     [rbp+DeviceRegKey], 0
0x180037804  xorps   xmm0, xmm0
0x180037807  mov     [rbp+arg_0], 0
0x18003780e  mov     ebx, 1
0x180037813  lea     r9, [rbp+DeviceRegKey]; DeviceRegKey
0x180037817  mov     edx, ebx; DevInstKeyType
0x180037819  mov     rcx, rax; DeviceObject
0x18003781c  mov     r8d, 1F0000h; DesiredAccess
0x180037822  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180037826  call    cs:__imp_IoOpenDeviceRegistryKey
0x18003782d  nop     dword ptr [rax+rax+00h]
0x180037832  mov     edx, eax
0x180037834  test    eax, eax
0x180037836  jns     loc_1800378C3
0x18003783c  mov     r10, cs:WPP_GLOBAL_Control
0x180037843  lea     rcx, WPP_GLOBAL_Control
0x18003784a  cmp     r10, rcx
0x18003784d  jz      short loc_18003785F
0x18003784f  mov     ecx, [r10+2Ch]
0x180037853  test    cl, 4
0x180037856  jz      short loc_18003785F
0x180037858  cmp     byte ptr [r10+29h], 2
0x18003785d  jnb     short loc_180037861
0x18003785f  xor     bl, bl
0x180037861  lea     rax, WPP_RECORDER_INITIALIZED
0x180037868  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003786f  setnz   r8b
0x180037873  test    bl, bl
0x180037875  jnz     short loc_180037880
0x180037877  test    r8b, r8b
0x18003787a  jz      loc_180037AF4
0x180037880  mov     rax, [rsi]
0x180037883  mov     r9, [rsi+2A0h]
0x18003788a  mov     rcx, [r10+18h]
0x18003788e  mov     dword ptr [rsp+70h+var_28], edx
0x180037892  mov     dl, bl
0x180037894  mov     [rsp+70h+var_30], rax
0x180037899  lea     rax, WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids
0x1800378a0  mov     [rsp+70h+var_38], rax
0x1800378a5  mov     [rsp+70h+var_40], 13h
0x1800378ac  mov     dword ptr [rsp+70h+ResultLength], 3
0x1800378b4  mov     [rsp+70h+Length], 2
0x1800378b9  call    WPP_RECORDER_AND_TRACE_SF_qL
0x1800378be  jmp     loc_180037AF4
0x1800378c3  lea     rdx, aCombohardwarei; "ComboHardwareIdV2Enabled"
0x1800378ca  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800378ce  call    cs:__imp_RtlInitUnicodeString
0x1800378d5  nop     dword ptr [rax+rax+00h]
0x1800378da  movzx   eax, [rbp+DestinationString.MaximumLength]
0x1800378de  mov     ecx, 100h
0x1800378e3  add     eax, 1Ch
0x1800378e6  mov     r8d, 43646948h
0x1800378ec  mov     edx, eax
0x1800378ee  mov     [rbp+arg_0], eax
0x1800378f1  call    cs:__imp_ExAllocatePool2
0x1800378f8  nop     dword ptr [rax+rax+00h]
0x1800378fd  mov     rdi, rax
0x180037900  test    rax, rax
0x180037903  jnz     loc_18003799A
0x180037909  mov     r10, cs:WPP_GLOBAL_Control
0x180037910  lea     rcx, WPP_GLOBAL_Control
0x180037917  cmp     r10, rcx
0x18003791a  jz      short loc_18003792B
0x18003791c  mov     eax, [r10+2Ch]
0x180037920  test    al, 4
0x180037922  jz      short loc_18003792B
0x180037924  cmp     byte ptr [r10+29h], 2
0x180037929  jnb     short loc_18003792D
0x18003792b  xor     bl, bl
0x18003792d  lea     rax, WPP_RECORDER_INITIALIZED
0x180037934  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003793b  setnz   r8b
0x18003793f  test    bl, bl
0x180037941  jnz     short loc_18003794C
0x180037943  test    r8b, r8b
0x180037946  jz      loc_180037AF4
0x18003794c  mov     eax, [rbp+arg_0]
0x18003794f  mov     dl, bl
0x180037951  mov     r9, [rsi+2A0h]
0x180037958  mov     rcx, [r10+18h]
0x18003795c  mov     [rsp+70h+var_20], 0C000009Ah
0x180037964  mov     dword ptr [rsp+70h+var_28], eax
0x180037968  mov     rax, [rsi]
0x18003796b  mov     [rsp+70h+var_30], rax
0x180037970  lea     rax, WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids
0x180037977  mov     [rsp+70h+var_38], rax
0x18003797c  mov     [rsp+70h+var_40], 14h
0x180037983  mov     dword ptr [rsp+70h+ResultLength], 3
0x18003798b  mov     [rsp+70h+Length], 2
0x180037990  call    WPP_RECORDER_AND_TRACE_SF_qLL
0x180037995  jmp     loc_180037AF4
0x18003799a  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x18003799e  lea     rax, [rbp+arg_0]
0x1800379a2  mov     [rsp+70h+ResultLength], rax; ResultLength
0x1800379a7  lea     rdx, [rbp+DestinationString]; ValueName
0x1800379ab  mov     eax, [rbp+arg_0]
0x1800379ae  mov     r9, rdi; KeyValueInformation
0x1800379b1  mov     r8d, ebx; KeyValueInformationClass
0x1800379b4  mov     dword ptr [rsp+70h+Length], eax; Length
0x1800379b8  call    cs:__imp_ZwQueryValueKey
0x1800379bf  nop     dword ptr [rax+rax+00h]
0x1800379c4  mov     edx, eax
0x1800379c6  test    eax, eax
0x1800379c8  jns     short loc_180037A49
0x1800379ca  cmp     eax, 0C0000034h
0x1800379cf  jz      loc_180037AE3
0x1800379d5  mov     r10, cs:WPP_GLOBAL_Control
0x1800379dc  lea     rcx, WPP_GLOBAL_Control
0x1800379e3  cmp     r10, rcx
0x1800379e6  jz      short loc_1800379F7
0x1800379e8  mov     eax, [r10+2Ch]
0x1800379ec  test    al, 4
0x1800379ee  jz      short loc_1800379F7
0x1800379f0  cmp     byte ptr [r10+29h], 3
0x1800379f5  jnb     short loc_1800379F9
0x1800379f7  xor     bl, bl
0x1800379f9  lea     rax, WPP_RECORDER_INITIALIZED
0x180037a00  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180037a07  setnz   r8b
0x180037a0b  test    bl, bl
0x180037a0d  jnz     short loc_180037A18
0x180037a0f  test    r8b, r8b
0x180037a12  jz      loc_180037AE3
0x180037a18  mov     rax, [rsi]
0x180037a1b  mov     dword ptr [rsp+70h+var_28], edx
0x180037a1f  mov     [rsp+70h+var_30], rax
0x180037a24  lea     rax, WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids
0x180037a2b  mov     [rsp+70h+var_38], rax
0x180037a30  mov     [rsp+70h+var_40], 15h
0x180037a37  mov     dword ptr [rsp+70h+ResultLength], 3
0x180037a3f  mov     [rsp+70h+Length], 3
0x180037a44  jmp     loc_180037AD1
0x180037a49  cmp     dword ptr [rdi+0Ch], 4
0x180037a4d  jnz     loc_180037AE3
0x180037a53  mov     eax, [rdi+8]
0x180037a56  cmp     dword ptr [rax+rdi], 0
0x180037a5a  setnz   dl
0x180037a5d  mov     [rsi+7B9h], dl
0x180037a63  mov     r10, cs:WPP_GLOBAL_Control
0x180037a6a  lea     rcx, WPP_GLOBAL_Control
0x180037a71  cmp     r10, rcx
0x180037a74  jz      short loc_180037A85
0x180037a76  mov     eax, [r10+2Ch]
0x180037a7a  test    al, 4
0x180037a7c  jz      short loc_180037A85
0x180037a7e  cmp     byte ptr [r10+29h], 4
0x180037a83  jnb     short loc_180037A87
0x180037a85  xor     bl, bl
0x180037a87  lea     rax, WPP_RECORDER_INITIALIZED
0x180037a8e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180037a95  setnz   r8b
0x180037a99  test    bl, bl
0x180037a9b  jnz     short loc_180037AA2
0x180037a9d  test    r8b, r8b
0x180037aa0  jz      short loc_180037AE3
0x180037aa2  movzx   eax, dl
0x180037aa5  mov     dword ptr [rsp+70h+var_28], eax
0x180037aa9  mov     rax, [rsi]
0x180037aac  mov     [rsp+70h+var_30], rax
0x180037ab1  lea     rax, WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids
0x180037ab8  mov     [rsp+70h+var_38], rax
0x180037abd  mov     [rsp+70h+var_40], 16h
0x180037ac4  mov     dword ptr [rsp+70h+ResultLength], 3
0x180037acc  mov     [rsp+70h+Length], 4
0x180037ad1  mov     r9, [rsi+2A0h]
0x180037ad8  mov     dl, bl
0x180037ada  mov     rcx, [r10+18h]
0x180037ade  call    WPP_RECORDER_AND_TRACE_SF_qL
0x180037ae3  xor     edx, edx; Tag
0x180037ae5  mov     rcx, rdi; P
0x180037ae8  call    cs:__imp_ExFreePoolWithTag
0x180037aef  nop     dword ptr [rax+rax+00h]
0x180037af4  mov     rcx, [rbp+DeviceRegKey]; Handle
0x180037af8  test    rcx, rcx
0x180037afb  jz      short loc_180037B09
0x180037afd  call    cs:__imp_ZwClose
0x180037b04  nop     dword ptr [rax+rax+00h]
0x180037b09  mov     rbx, [rsp+70h+arg_8]
0x180037b11  add     rsp, 70h
0x180037b15  pop     rdi
0x180037b16  pop     rsi
0x180037b17  pop     rbp
0x180037b18  retn
```
