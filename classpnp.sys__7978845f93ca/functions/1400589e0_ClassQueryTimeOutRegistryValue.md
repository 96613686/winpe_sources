# ClassQueryTimeOutRegistryValue

- ea: `0x1400589e0`
- end: `0x140058b90`
- name: `ClassQueryTimeOutRegistryValue`
- size: `432`
- prototype: `ULONG __stdcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x14001fbf4`
- `0x14003e470`
- `0x14003e640`
- `0x1400589e0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140058ad9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140058ad9`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140058b0d`
- `ntoskrnl!ExAllocatePool2` at `0x140058a2b`
- `ntoskrnl!ExAllocatePool2` at `0x140058a4f`
- `ntoskrnl!ExAllocatePool2` at `0x140058a2b`
- `ntoskrnl!ExAllocatePool2` at `0x140058a4f`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140058aea`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140058aea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058a68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058b2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058b3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058a68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058b2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058b3f`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x1400589f7`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x1400589f7`

## string_xrefs

- `0x140058aa5`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
ULONG __stdcall ClassQueryTimeOutRegistryValue(PDEVICE_OBJECT DeviceObject)
{
  const void **DriverObjectExtension; // rax
  const void **v2; // rdi
  __int64 Pool2; // rbx
  size_t v4; // rbp
  void *v5; // rax
  void *v6; // rsi
  PVOID SystemRoutineAddress; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-28h] BYREF
  ULONG v10; // [rsp+60h] [rbp+8h] BYREF
  int v11; // [rsp+68h] [rbp+10h] BYREF

  DriverObjectExtension = (const void **)IoGetDriverObjectExtension(DeviceObject->DriverObject, ClassInitialize);
  v10 = 0;
  v2 = DriverObjectExtension;
  v11 = 0;
  if ( !DriverObjectExtension )
    return 0;
  Pool2 = ExAllocatePool2(64, 112, 826434387);
  if ( !Pool2 )
    return 0;
  v4 = *((unsigned __int16 *)v2 + 1);
  v5 = (void *)ExAllocatePool2(64, v4 + 2, 843211603);
  v6 = v5;
  if ( !v5 )
  {
    ExFreePoolWithTag((PVOID)Pool2, 0);
    return 0;
  }
  memmove(v5, v2[1], v4);
  *(_DWORD *)(Pool2 + 8) = 288;
  *(_QWORD *)(Pool2 + 16) = L"TimeOutValue";
  *(_DWORD *)(Pool2 + 32) = 67108868;
  *(_QWORD *)(Pool2 + 24) = &v10;
  *(_DWORD *)(Pool2 + 48) = 4;
  *(_QWORD *)(Pool2 + 40) = &v11;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  if ( ((int (__fastcall *)(__int64, void *, __int64, _QWORD, _QWORD))SystemRoutineAddress)(
         0x80000000LL,
         v6,
         Pool2,
         0,
         0) < 0 )
    v10 = 0;
  ExFreePoolWithTag((PVOID)Pool2, 0);
  ExFreePoolWithTag(v6, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 171, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x1400589e0  mov     [rsp+arg_10], rbx
0x1400589e5  push    rbp
0x1400589e6  push    rsi
0x1400589e7  push    rdi
0x1400589e8  sub     rsp, 40h
0x1400589ec  mov     rcx, [rcx+8]; DriverObject
0x1400589f0  lea     rdx, ClassInitialize; ClientIdentificationAddress
0x1400589f7  call    cs:__imp_IoGetDriverObjectExtension
0x1400589fe  nop     dword ptr [rax+rax+00h]
0x140058a03  mov     [rsp+58h+arg_0], 0
0x140058a0b  mov     rdi, rax
0x140058a0e  mov     [rsp+58h+arg_8], 0
0x140058a16  test    rax, rax
0x140058a19  jz      short loc_140058A74
0x140058a1b  mov     edx, 70h ; 'p'
0x140058a20  mov     r8d, 31426353h
0x140058a26  lea     esi, [rdx-30h]
0x140058a29  mov     ecx, esi
0x140058a2b  call    cs:__imp_ExAllocatePool2
0x140058a32  nop     dword ptr [rax+rax+00h]
0x140058a37  mov     rbx, rax
0x140058a3a  test    rax, rax
0x140058a3d  jz      short loc_140058A74
0x140058a3f  movzx   ebp, word ptr [rdi+2]
0x140058a43  mov     r8d, 32426353h
0x140058a49  mov     ecx, esi
0x140058a4b  lea     rdx, [rbp+2]
0x140058a4f  call    cs:__imp_ExAllocatePool2
0x140058a56  nop     dword ptr [rax+rax+00h]
0x140058a5b  mov     rsi, rax
0x140058a5e  test    rax, rax
0x140058a61  jnz     short loc_140058A84
0x140058a63  xor     edx, edx; Tag
0x140058a65  mov     rcx, rbx; P
0x140058a68  call    cs:__imp_ExFreePoolWithTag
0x140058a6f  nop     dword ptr [rax+rax+00h]
0x140058a74  xor     eax, eax
0x140058a76  mov     rbx, [rsp+58h+arg_10]
0x140058a7b  add     rsp, 40h
0x140058a7f  pop     rdi
0x140058a80  pop     rsi
0x140058a81  pop     rbp
0x140058a82  retn
0x140058a84  mov     rdx, [rdi+8]; Src
0x140058a88  mov     r8, rbp; Size
0x140058a8b  mov     rcx, rsi; void *
0x140058a8e  call    memmove
0x140058a93  lea     rax, aTimeoutvalue; "TimeOutValue"
0x140058a9a  mov     dword ptr [rbx+8], 120h
0x140058aa1  mov     [rbx+10h], rax
0x140058aa5  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x140058aac  lea     rax, [rsp+58h+arg_0]
0x140058ab1  mov     dword ptr [rbx+20h], 4000004h
0x140058ab8  mov     [rbx+18h], rax
0x140058abc  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x140058ac1  lea     rax, [rsp+58h+arg_8]
0x140058ac6  mov     dword ptr [rbx+30h], 4
0x140058acd  xorps   xmm0, xmm0
0x140058ad0  mov     [rbx+28h], rax
0x140058ad4  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x140058ad9  call    cs:__imp_RtlInitUnicodeString
0x140058ae0  nop     dword ptr [rax+rax+00h]
0x140058ae5  lea     rcx, [rsp+58h+DestinationString]; SystemRoutineName
0x140058aea  call    cs:__imp_MmGetSystemRoutineAddress
0x140058af1  nop     dword ptr [rax+rax+00h]
0x140058af6  mov     r8, rbx
0x140058af9  mov     [rsp+58h+var_38], 0
0x140058b02  test    rax, rax
0x140058b05  mov     rdx, rsi
0x140058b08  mov     ecx, 80000000h
0x140058b0d  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140058b15  xor     r9d, r9d
0x140058b18  call    _guard_dispatch_icall
0x140058b1d  test    eax, eax
0x140058b1f  jns     short loc_140058B29
0x140058b21  mov     [rsp+58h+arg_0], 0
0x140058b29  xor     edx, edx; Tag
0x140058b2b  mov     rcx, rbx; P
0x140058b2e  call    cs:__imp_ExFreePoolWithTag
0x140058b35  nop     dword ptr [rax+rax+00h]
0x140058b3a  xor     edx, edx; Tag
0x140058b3c  mov     rcx, rsi; P
0x140058b3f  call    cs:__imp_ExFreePoolWithTag
0x140058b46  nop     dword ptr [rax+rax+00h]
0x140058b4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140058b52  lea     rax, WPP_GLOBAL_Control
0x140058b59  cmp     rcx, rax
0x140058b5c  jz      short loc_140058B87
0x140058b5e  test    dword ptr [rcx+2Ch], 100h
0x140058b65  jz      short loc_140058B87
0x140058b67  cmp     byte ptr [rcx+29h], 4
0x140058b6b  jb      short loc_140058B87
0x140058b6d  mov     r9d, [rsp+58h+arg_0]
0x140058b72  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140058b79  mov     rcx, [rcx+18h]
0x140058b7d  mov     edx, 0ABh
0x140058b82  call    WPP_SF_d
0x140058b87  mov     eax, [rsp+58h+arg_0]
0x140058b8b  jmp     loc_140058A76
```
