# HidpGetPdoReenumerateSelfInterfaceEnabled

- ea: `0x180037b20`
- end: `0x180037e5a`
- name: `HidpGetPdoReenumerateSelfInterfaceEnabled`
- size: `826`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003a590`

## callees

- `0x18000ddc8`
- `0x180014e80`
- `0x180037b20`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x180037cf8`
- `ntoskrnl!ZwQueryValueKey` at `0x180037cf8`
- `ntoskrnl!ZwClose` at `0x180037e3d`
- `ntoskrnl!ZwClose` at `0x180037e3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x180037e28`
- `ntoskrnl!ExFreePoolWithTag` at `0x180037e28`
- `ntoskrnl!ExAllocatePool2` at `0x180037c31`
- `ntoskrnl!ExAllocatePool2` at `0x180037c31`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x180037b66`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x180037b66`
- `ntoskrnl!RtlInitUnicodeString` at `0x180037c0e`
- `ntoskrnl!RtlInitUnicodeString` at `0x180037c0e`

## pseudocode

```c
void __fastcall HidpGetPdoReenumerateSelfInterfaceEnabled(__int64 *a1, struct _DEVICE_OBJECT *a2)
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

  *((_BYTE *)a1 + 1978) = 0;
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
        23,
        (__int64)WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids,
        *a1,
        v17);
    }
    goto LABEL_36;
  }
  RtlInitUnicodeString(&DestinationString, L"CollectionReenumerateSelfInterfaceEnabled");
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
      *((_BYTE *)a1 + 1978) = v13;
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
      v15 = 26;
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
      v15 = 25;
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
      24,
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
0x180037b20  mov     [rsp-18h+arg_8], rbx
0x180037b25  push    rbp
0x180037b26  push    rsi
0x180037b27  push    rdi
0x180037b28  mov     rbp, rsp
0x180037b2b  sub     rsp, 70h
0x180037b2f  mov     rax, rdx
0x180037b32  mov     byte ptr [rcx+7BAh], 0
0x180037b39  mov     rsi, rcx
0x180037b3c  mov     [rbp+DeviceRegKey], 0
0x180037b44  xorps   xmm0, xmm0
0x180037b47  mov     [rbp+arg_0], 0
0x180037b4e  mov     ebx, 1
0x180037b53  lea     r9, [rbp+DeviceRegKey]; DeviceRegKey
0x180037b57  mov     edx, ebx; DevInstKeyType
0x180037b59  mov     rcx, rax; DeviceObject
0x180037b5c  mov     r8d, 1F0000h; DesiredAccess
0x180037b62  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180037b66  call    cs:__imp_IoOpenDeviceRegistryKey
0x180037b6d  nop     dword ptr [rax+rax+00h]
0x180037b72  mov     edx, eax
0x180037b74  test    eax, eax
0x180037b76  jns     loc_180037C03
0x180037b7c  mov     r10, cs:WPP_GLOBAL_Control
0x180037b83  lea     rcx, WPP_GLOBAL_Control
0x180037b8a  cmp     r10, rcx
0x180037b8d  jz      short loc_180037B9F
0x180037b8f  mov     ecx, [r10+2Ch]
0x180037b93  test    cl, 4
0x180037b96  jz      short loc_180037B9F
0x180037b98  cmp     byte ptr [r10+29h], 2
0x180037b9d  jnb     short loc_180037BA1
0x180037b9f  xor     bl, bl
0x180037ba1  lea     rax, WPP_RECORDER_INITIALIZED
0x180037ba8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180037baf  setnz   r8b
0x180037bb3  test    bl, bl
0x180037bb5  jnz     short loc_180037BC0
0x180037bb7  test    r8b, r8b
0x180037bba  jz      loc_180037E34
0x180037bc0  mov     rax, [rsi]
0x180037bc3  mov     r9, [rsi+2A0h]
0x180037bca  mov     rcx, [r10+18h]
0x180037bce  mov     dword ptr [rsp+70h+var_28], edx
0x180037bd2  mov     dl, bl
0x180037bd4  mov     [rsp+70h+var_30], rax
0x180037bd9  lea     rax, WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids
0x180037be0  mov     [rsp+70h+var_38], rax
0x180037be5  mov     [rsp+70h+var_40], 17h
0x180037bec  mov     dword ptr [rsp+70h+ResultLength], 3
0x180037bf4  mov     [rsp+70h+Length], 2
0x180037bf9  call    WPP_RECORDER_AND_TRACE_SF_qL
0x180037bfe  jmp     loc_180037E34
0x180037c03  lea     rdx, aCollectionreen; "CollectionReenumerateSelfInterfaceEnabl"...
0x180037c0a  lea     rcx, [rbp+DestinationString]; DestinationString
0x180037c0e  call    cs:__imp_RtlInitUnicodeString
0x180037c15  nop     dword ptr [rax+rax+00h]
0x180037c1a  movzx   eax, [rbp+DestinationString.MaximumLength]
0x180037c1e  mov     ecx, 100h
0x180037c23  add     eax, 1Ch
0x180037c26  mov     r8d, 43646948h
0x180037c2c  mov     edx, eax
0x180037c2e  mov     [rbp+arg_0], eax
0x180037c31  call    cs:__imp_ExAllocatePool2
0x180037c38  nop     dword ptr [rax+rax+00h]
0x180037c3d  mov     rdi, rax
0x180037c40  test    rax, rax
0x180037c43  jnz     loc_180037CDA
0x180037c49  mov     r10, cs:WPP_GLOBAL_Control
0x180037c50  lea     rcx, WPP_GLOBAL_Control
0x180037c57  cmp     r10, rcx
0x180037c5a  jz      short loc_180037C6B
0x180037c5c  mov     eax, [r10+2Ch]
0x180037c60  test    al, 4
0x180037c62  jz      short loc_180037C6B
0x180037c64  cmp     byte ptr [r10+29h], 2
0x180037c69  jnb     short loc_180037C6D
0x180037c6b  xor     bl, bl
0x180037c6d  lea     rax, WPP_RECORDER_INITIALIZED
0x180037c74  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180037c7b  setnz   r8b
0x180037c7f  test    bl, bl
0x180037c81  jnz     short loc_180037C8C
0x180037c83  test    r8b, r8b
0x180037c86  jz      loc_180037E34
0x180037c8c  mov     eax, [rbp+arg_0]
0x180037c8f  mov     dl, bl
0x180037c91  mov     r9, [rsi+2A0h]
0x180037c98  mov     rcx, [r10+18h]
0x180037c9c  mov     [rsp+70h+var_20], 0C000009Ah
0x180037ca4  mov     dword ptr [rsp+70h+var_28], eax
0x180037ca8  mov     rax, [rsi]
0x180037cab  mov     [rsp+70h+var_30], rax
0x180037cb0  lea     rax, WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids
0x180037cb7  mov     [rsp+70h+var_38], rax
0x180037cbc  mov     [rsp+70h+var_40], 18h
0x180037cc3  mov     dword ptr [rsp+70h+ResultLength], 3
0x180037ccb  mov     [rsp+70h+Length], 2
0x180037cd0  call    WPP_RECORDER_AND_TRACE_SF_qLL
0x180037cd5  jmp     loc_180037E34
0x180037cda  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x180037cde  lea     rax, [rbp+arg_0]
0x180037ce2  mov     [rsp+70h+ResultLength], rax; ResultLength
0x180037ce7  lea     rdx, [rbp+DestinationString]; ValueName
0x180037ceb  mov     eax, [rbp+arg_0]
0x180037cee  mov     r9, rdi; KeyValueInformation
0x180037cf1  mov     r8d, ebx; KeyValueInformationClass
0x180037cf4  mov     dword ptr [rsp+70h+Length], eax; Length
0x180037cf8  call    cs:__imp_ZwQueryValueKey
0x180037cff  nop     dword ptr [rax+rax+00h]
0x180037d04  mov     edx, eax
0x180037d06  test    eax, eax
0x180037d08  jns     short loc_180037D89
0x180037d0a  cmp     eax, 0C0000034h
0x180037d0f  jz      loc_180037E23
0x180037d15  mov     r10, cs:WPP_GLOBAL_Control
0x180037d1c  lea     rcx, WPP_GLOBAL_Control
0x180037d23  cmp     r10, rcx
0x180037d26  jz      short loc_180037D37
0x180037d28  mov     eax, [r10+2Ch]
0x180037d2c  test    al, 4
0x180037d2e  jz      short loc_180037D37
0x180037d30  cmp     byte ptr [r10+29h], 3
0x180037d35  jnb     short loc_180037D39
0x180037d37  xor     bl, bl
0x180037d39  lea     rax, WPP_RECORDER_INITIALIZED
0x180037d40  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180037d47  setnz   r8b
0x180037d4b  test    bl, bl
0x180037d4d  jnz     short loc_180037D58
0x180037d4f  test    r8b, r8b
0x180037d52  jz      loc_180037E23
0x180037d58  mov     rax, [rsi]
0x180037d5b  mov     dword ptr [rsp+70h+var_28], edx
0x180037d5f  mov     [rsp+70h+var_30], rax
0x180037d64  lea     rax, WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids
0x180037d6b  mov     [rsp+70h+var_38], rax
0x180037d70  mov     [rsp+70h+var_40], 19h
0x180037d77  mov     dword ptr [rsp+70h+ResultLength], 3
0x180037d7f  mov     [rsp+70h+Length], 3
0x180037d84  jmp     loc_180037E11
0x180037d89  cmp     dword ptr [rdi+0Ch], 4
0x180037d8d  jnz     loc_180037E23
0x180037d93  mov     eax, [rdi+8]
0x180037d96  cmp     dword ptr [rax+rdi], 0
0x180037d9a  setnz   dl
0x180037d9d  mov     [rsi+7BAh], dl
0x180037da3  mov     r10, cs:WPP_GLOBAL_Control
0x180037daa  lea     rcx, WPP_GLOBAL_Control
0x180037db1  cmp     r10, rcx
0x180037db4  jz      short loc_180037DC5
0x180037db6  mov     eax, [r10+2Ch]
0x180037dba  test    al, 4
0x180037dbc  jz      short loc_180037DC5
0x180037dbe  cmp     byte ptr [r10+29h], 4
0x180037dc3  jnb     short loc_180037DC7
0x180037dc5  xor     bl, bl
0x180037dc7  lea     rax, WPP_RECORDER_INITIALIZED
0x180037dce  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180037dd5  setnz   r8b
0x180037dd9  test    bl, bl
0x180037ddb  jnz     short loc_180037DE2
0x180037ddd  test    r8b, r8b
0x180037de0  jz      short loc_180037E23
0x180037de2  movzx   eax, dl
0x180037de5  mov     dword ptr [rsp+70h+var_28], eax
0x180037de9  mov     rax, [rsi]
0x180037dec  mov     [rsp+70h+var_30], rax
0x180037df1  lea     rax, WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids
0x180037df8  mov     [rsp+70h+var_38], rax
0x180037dfd  mov     [rsp+70h+var_40], 1Ah
0x180037e04  mov     dword ptr [rsp+70h+ResultLength], 3
0x180037e0c  mov     [rsp+70h+Length], 4
0x180037e11  mov     r9, [rsi+2A0h]
0x180037e18  mov     dl, bl
0x180037e1a  mov     rcx, [r10+18h]
0x180037e1e  call    WPP_RECORDER_AND_TRACE_SF_qL
0x180037e23  xor     edx, edx; Tag
0x180037e25  mov     rcx, rdi; P
0x180037e28  call    cs:__imp_ExFreePoolWithTag
0x180037e2f  nop     dword ptr [rax+rax+00h]
0x180037e34  mov     rcx, [rbp+DeviceRegKey]; Handle
0x180037e38  test    rcx, rcx
0x180037e3b  jz      short loc_180037E49
0x180037e3d  call    cs:__imp_ZwClose
0x180037e44  nop     dword ptr [rax+rax+00h]
0x180037e49  mov     rbx, [rsp+70h+arg_8]
0x180037e51  add     rsp, 70h
0x180037e55  pop     rdi
0x180037e56  pop     rsi
0x180037e57  pop     rbp
0x180037e58  retn
```
