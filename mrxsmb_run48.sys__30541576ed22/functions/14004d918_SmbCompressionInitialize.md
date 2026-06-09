# SmbCompressionInitialize

- ea: `0x14004d918`
- end: `0x14004da19`
- name: `SmbCompressionInitialize`
- size: `257`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14007fd3c`

## callees

- `0x14003b830`
- `0x14004d4b8`
- `0x14004d918`

## import_xrefs

- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14004d945`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14004d972`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14004d998`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14004d9be`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14004d945`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14004d972`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14004d998`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14004d9be`

## pseudocode

```c
__int64 SmbCompressionInitialize()
{
  NTSTATUS CompressionWorkSpaceSize; // ebx
  ULONG v1; // edi
  int v2; // edx
  int v3; // r8d
  int v4; // r9d
  int v6; // [rsp+20h] [rbp-30h]
  int v7; // [rsp+38h] [rbp-18h]
  ULONG CompressBufferWorkSpaceSize; // [rsp+60h] [rbp+10h] BYREF
  ULONG CompressFragmentWorkSpaceSize; // [rsp+68h] [rbp+18h] BYREF

  CompressBufferWorkSpaceSize = 0;
  CompressFragmentWorkSpaceSize = 0;
  CompressionWorkSpaceSize = RtlGetCompressionWorkSpaceSize(
                               2u,
                               &CompressBufferWorkSpaceSize,
                               &CompressFragmentWorkSpaceSize);
  if ( CompressionWorkSpaceSize < 0 )
    goto LABEL_15;
  v1 = 0;
  if ( CompressBufferWorkSpaceSize )
    v1 = CompressBufferWorkSpaceSize;
  CompressionWorkSpaceSize = RtlGetCompressionWorkSpaceSize(
                               3u,
                               &CompressBufferWorkSpaceSize,
                               &CompressFragmentWorkSpaceSize);
  if ( CompressionWorkSpaceSize < 0 )
    goto LABEL_15;
  if ( CompressBufferWorkSpaceSize > v1 )
    v1 = CompressBufferWorkSpaceSize;
  CompressionWorkSpaceSize = RtlGetCompressionWorkSpaceSize(
                               4u,
                               &CompressBufferWorkSpaceSize,
                               &CompressFragmentWorkSpaceSize);
  if ( CompressionWorkSpaceSize < 0 )
    goto LABEL_15;
  if ( CompressBufferWorkSpaceSize > v1 )
    v1 = CompressBufferWorkSpaceSize;
  CompressionWorkSpaceSize = RtlGetCompressionWorkSpaceSize(
                               6u,
                               &CompressBufferWorkSpaceSize,
                               &CompressFragmentWorkSpaceSize);
  if ( CompressionWorkSpaceSize < 0 )
    goto LABEL_15;
  if ( CompressBufferWorkSpaceSize > v1 )
    v1 = CompressBufferWorkSpaceSize;
  qword_140070A80 = (PVOID)PplCreateLookasideList(624055116, v2, v3, v4, v6, v1, 0x2532534Cu, v7, 0x2532534Cu);
  if ( !qword_140070A80 )
  {
    CompressionWorkSpaceSize = -1073741670;
LABEL_15:
    SmbCompressionCleanup();
  }
  return (unsigned int)CompressionWorkSpaceSize;
}

```

## disassembly

```asm
0x14004d918  mov     [rsp-8+arg_10], rbx
0x14004d91d  mov     [rsp-8+arg_18], rdi
0x14004d922  push    rbp
0x14004d923  mov     rbp, rsp
0x14004d926  sub     rsp, 50h
0x14004d92a  mov     ecx, 2; CompressionFormatAndEngine
0x14004d92f  mov     [rbp+CompressBufferWorkSpaceSize], 0
0x14004d936  lea     r8, [rbp+CompressFragmentWorkSpaceSize]; CompressFragmentWorkSpaceSize
0x14004d93a  mov     [rbp+CompressFragmentWorkSpaceSize], 0
0x14004d941  lea     rdx, [rbp+CompressBufferWorkSpaceSize]; CompressBufferWorkSpaceSize
0x14004d945  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x14004d94c  nop     dword ptr [rax+rax+00h]
0x14004d951  mov     ebx, eax
0x14004d953  test    eax, eax
0x14004d955  js      loc_14004DA01
0x14004d95b  mov     eax, [rbp+CompressBufferWorkSpaceSize]
0x14004d95e  lea     r8, [rbp+CompressFragmentWorkSpaceSize]; CompressFragmentWorkSpaceSize
0x14004d962  xor     edi, edi
0x14004d964  lea     rdx, [rbp+CompressBufferWorkSpaceSize]; CompressBufferWorkSpaceSize
0x14004d968  test    eax, eax
0x14004d96a  mov     ecx, 3; CompressionFormatAndEngine
0x14004d96f  cmovnz  edi, eax
0x14004d972  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x14004d979  nop     dword ptr [rax+rax+00h]
0x14004d97e  mov     ebx, eax
0x14004d980  test    eax, eax
0x14004d982  js      short loc_14004DA01
0x14004d984  cmp     [rbp+CompressBufferWorkSpaceSize], edi
0x14004d987  lea     r8, [rbp+CompressFragmentWorkSpaceSize]; CompressFragmentWorkSpaceSize
0x14004d98b  mov     ecx, 4; CompressionFormatAndEngine
0x14004d990  lea     rdx, [rbp+CompressBufferWorkSpaceSize]; CompressBufferWorkSpaceSize
0x14004d994  cmova   edi, [rbp+CompressBufferWorkSpaceSize]
0x14004d998  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x14004d99f  nop     dword ptr [rax+rax+00h]
0x14004d9a4  mov     ebx, eax
0x14004d9a6  test    eax, eax
0x14004d9a8  js      short loc_14004DA01
0x14004d9aa  cmp     [rbp+CompressBufferWorkSpaceSize], edi
0x14004d9ad  lea     r8, [rbp+CompressFragmentWorkSpaceSize]; CompressFragmentWorkSpaceSize
0x14004d9b1  mov     ecx, 6; CompressionFormatAndEngine
0x14004d9b6  lea     rdx, [rbp+CompressBufferWorkSpaceSize]; CompressBufferWorkSpaceSize
0x14004d9ba  cmova   edi, [rbp+CompressBufferWorkSpaceSize]
0x14004d9be  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x14004d9c5  nop     dword ptr [rax+rax+00h]
0x14004d9ca  mov     ebx, eax
0x14004d9cc  test    eax, eax
0x14004d9ce  js      short loc_14004DA01
0x14004d9d0  cmp     [rbp+CompressBufferWorkSpaceSize], edi
0x14004d9d3  mov     ecx, 2532534Ch; int
0x14004d9d8  mov     [rsp+50h+var_10], ecx; ULONG
0x14004d9dc  cmova   edi, [rbp+CompressBufferWorkSpaceSize]
0x14004d9e0  mov     eax, edi
0x14004d9e2  mov     [rsp+50h+var_20], ecx; ULONG
0x14004d9e6  mov     [rsp+50h+var_28], rax; SIZE_T
0x14004d9eb  call    PplCreateLookasideList
0x14004d9f0  mov     cs:qword_140070A80, rax
0x14004d9f7  test    rax, rax
0x14004d9fa  jnz     short loc_14004DA06
0x14004d9fc  mov     ebx, 0C000009Ah
0x14004da01  call    SmbCompressionCleanup
0x14004da06  mov     rdi, [rsp+50h+arg_18]
0x14004da0b  mov     eax, ebx
0x14004da0d  mov     rbx, [rsp+50h+arg_10]
0x14004da12  add     rsp, 50h
0x14004da16  pop     rbp
0x14004da17  retn
```
