# HidpGetRemoteWakeEnableState

- ea: `0x180041b44`
- end: `0x180041cea`
- name: `HidpGetRemoteWakeEnableState`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180042f24`

## callees

- `0x180013860`
- `0x180041b44`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x180041bfc`
- `ntoskrnl!ZwQueryValueKey` at `0x180041bfc`
- `ntoskrnl!ZwClose` at `0x180041c34`
- `ntoskrnl!ZwClose` at `0x180041c34`
- `ntoskrnl!ExFreePoolWithTag` at `0x180041c24`
- `ntoskrnl!ExFreePoolWithTag` at `0x180041c24`
- `ntoskrnl!ExAllocatePool2` at `0x180041bca`
- `ntoskrnl!ExAllocatePool2` at `0x180041bca`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x180041b77`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x180041b77`
- `ntoskrnl!RtlInitUnicodeString` at `0x180041ba7`
- `ntoskrnl!RtlInitUnicodeString` at `0x180041ba7`

## pseudocode

```c
int __fastcall HidpGetRemoteWakeEnableState(__int64 a1)
{
  __int64 v1; // rbx
  char v3; // di
  NTSTATUS v4; // eax
  int v5; // r8d
  char v6; // r9
  unsigned int *Pool2; // rbx
  _UNKNOWN **v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-10h] BYREF
  ULONG Length; // [rsp+90h] [rbp+20h] BYREF
  void *DeviceRegKey; // [rsp+98h] [rbp+28h] BYREF

  v1 = *(_QWORD *)(a1 + 64);
  DeviceRegKey = 0;
  v3 = 1;
  v4 = IoOpenDeviceRegistryKey(*(PDEVICE_OBJECT *)(a1 + 48), 1u, 0x1F0000u, &DeviceRegKey);
  v6 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v3 = 0;
    }
    v8 = &WPP_RECORDER_INITIALIZED;
    if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = *(_QWORD *)(a1 + 64);
      v10 = *(_QWORD *)(v9 + 32);
      LOBYTE(v9) = v3;
      LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LODWORD(v8) = WPP_RECORDER_AND_TRACE_SF_qdqL(
                      WPP_GLOBAL_Control->AttachedDevice,
                      v9,
                      v5,
                      *(_QWORD *)(v1 + 704),
                      2,
                      3,
                      11,
                      (__int64)WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids,
                      v10,
                      *(_DWORD *)(a1 + 8),
                      *(_QWORD *)(a1 + 48),
                      v6);
    }
  }
  else
  {
    Length = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"RemoteWakeEnabled");
    Length = DestinationString.MaximumLength + 28;
    Pool2 = (unsigned int *)ExAllocatePool2(256, Length, 1130654024);
    if ( Pool2 )
    {
      if ( ZwQueryValueKey(DeviceRegKey, &DestinationString, KeyValueFullInformation, Pool2, Length, &Length) >= 0
        && Pool2[3] == 4 )
      {
        *(_BYTE *)(a1 + 84) = *(unsigned int *)((char *)Pool2 + Pool2[2]) != 0;
      }
      ExFreePoolWithTag(Pool2, 0);
    }
    LODWORD(v8) = ZwClose(DeviceRegKey);
  }
  return (int)v8;
}

```

## disassembly

```asm
0x180041b44  mov     [rsp-18h+arg_10], rbx
0x180041b49  push    rbp
0x180041b4a  push    rsi
0x180041b4b  push    rdi
0x180041b4c  mov     rbp, rsp
0x180041b4f  sub     rsp, 70h
0x180041b53  mov     rbx, [rcx+40h]
0x180041b57  lea     r9, [rbp+DeviceRegKey]; DeviceRegKey
0x180041b5b  mov     rsi, rcx
0x180041b5e  mov     [rbp+DeviceRegKey], 0
0x180041b66  mov     rcx, [rcx+30h]; DeviceObject
0x180041b6a  mov     edi, 1
0x180041b6f  mov     edx, edi; DevInstKeyType
0x180041b71  mov     r8d, 1F0000h; DesiredAccess
0x180041b77  call    cs:__imp_IoOpenDeviceRegistryKey
0x180041b7e  nop     dword ptr [rax+rax+00h]
0x180041b83  mov     r9d, eax
0x180041b86  test    eax, eax
0x180041b88  js      loc_180041C45
0x180041b8e  xorps   xmm0, xmm0
0x180041b91  mov     [rbp+arg_0], 0
0x180041b98  lea     rdx, aRemotewakeenab; "RemoteWakeEnabled"
0x180041b9f  lea     rcx, [rbp+DestinationString]; DestinationString
0x180041ba3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180041ba7  call    cs:__imp_RtlInitUnicodeString
0x180041bae  nop     dword ptr [rax+rax+00h]
0x180041bb3  movzx   eax, [rbp+DestinationString.MaximumLength]
0x180041bb7  mov     ecx, 100h
0x180041bbc  add     eax, 1Ch
0x180041bbf  mov     r8d, 43646948h
0x180041bc5  mov     edx, eax
0x180041bc7  mov     [rbp+arg_0], eax
0x180041bca  call    cs:__imp_ExAllocatePool2
0x180041bd1  nop     dword ptr [rax+rax+00h]
0x180041bd6  mov     rbx, rax
0x180041bd9  test    rax, rax
0x180041bdc  jz      short loc_180041C30
0x180041bde  mov     ecx, [rbp+arg_0]
0x180041be1  lea     rax, [rbp+arg_0]
0x180041be5  mov     [rsp+70h+ResultLength], rax; ResultLength
0x180041bea  lea     rdx, [rbp+DestinationString]; ValueName
0x180041bee  mov     [rsp+70h+Length], ecx; Length
0x180041bf2  mov     r9, rbx; KeyValueInformation
0x180041bf5  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x180041bf9  mov     r8d, edi; KeyValueInformationClass
0x180041bfc  call    cs:__imp_ZwQueryValueKey
0x180041c03  nop     dword ptr [rax+rax+00h]
0x180041c08  test    eax, eax
0x180041c0a  js      short loc_180041C1F
0x180041c0c  cmp     dword ptr [rbx+0Ch], 4
0x180041c10  jnz     short loc_180041C1F
0x180041c12  mov     eax, [rbx+8]
0x180041c15  cmp     dword ptr [rax+rbx], 0
0x180041c19  setnz   al
0x180041c1c  mov     [rsi+54h], al
0x180041c1f  xor     edx, edx; Tag
0x180041c21  mov     rcx, rbx; P
0x180041c24  call    cs:__imp_ExFreePoolWithTag
0x180041c2b  nop     dword ptr [rax+rax+00h]
0x180041c30  mov     rcx, [rbp+DeviceRegKey]; Handle
0x180041c34  call    cs:__imp_ZwClose
0x180041c3b  nop     dword ptr [rax+rax+00h]
0x180041c40  jmp     loc_180041CD9
0x180041c45  mov     rcx, cs:WPP_GLOBAL_Control
0x180041c4c  lea     rax, WPP_GLOBAL_Control
0x180041c53  cmp     rcx, rax
0x180041c56  jz      short loc_180041C65
0x180041c58  mov     eax, [rcx+2Ch]
0x180041c5b  test    al, 4
0x180041c5d  jz      short loc_180041C65
0x180041c5f  cmp     byte ptr [rcx+29h], 2
0x180041c63  jnb     short loc_180041C68
0x180041c65  xor     dil, dil
0x180041c68  lea     rax, WPP_RECORDER_INITIALIZED
0x180041c6f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180041c76  setnz   r8b
0x180041c7a  test    dil, dil
0x180041c7d  jnz     short loc_180041C84
0x180041c7f  test    r8b, r8b
0x180041c82  jz      short loc_180041CD9
0x180041c84  mov     rax, [rsi+30h]
0x180041c88  mov     rdx, [rsi+40h]
0x180041c8c  mov     rcx, [rcx+18h]
0x180041c90  mov     [rsp+70h+var_18], r9d
0x180041c95  mov     r9, [rbx+2C0h]
0x180041c9c  mov     [rsp+70h+var_20], rax
0x180041ca1  mov     eax, [rsi+8]
0x180041ca4  mov     [rsp+70h+var_28], eax
0x180041ca8  mov     rax, [rdx+20h]
0x180041cac  mov     dl, dil
0x180041caf  mov     [rsp+70h+var_30], rax
0x180041cb4  lea     rax, WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids
0x180041cbb  mov     [rsp+70h+var_38], rax
0x180041cc0  mov     [rsp+70h+var_40], 0Bh
0x180041cc7  mov     dword ptr [rsp+70h+ResultLength], 3
0x180041ccf  mov     byte ptr [rsp+70h+Length], 2
0x180041cd4  call    WPP_RECORDER_AND_TRACE_SF_qdqL
0x180041cd9  mov     rbx, [rsp+70h+arg_10]
0x180041ce1  add     rsp, 70h
0x180041ce5  pop     rdi
0x180041ce6  pop     rsi
0x180041ce7  pop     rbp
0x180041ce8  retn
```
