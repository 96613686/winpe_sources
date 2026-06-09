# HsmiRpCompressBuffer

- ea: `0x14006a8b0`
- end: `0x14006a9dc`
- name: `HsmiRpCompressBuffer`
- size: `300`
- prototype: `void __fastcall(UCHAR *, _DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140067e24`
- `0x14006b314`

## callees

- `0x14001e300`
- `0x14006a8b0`

## import_xrefs

- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14006a8f9`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14006a8f9`
- `ntoskrnl!RtlCompressBuffer` at `0x14006a973`
- `ntoskrnl!RtlCompressBuffer` at `0x14006a973`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a990`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a990`
- `ntoskrnl!ExAllocatePool2` at `0x14006a920`
- `ntoskrnl!ExAllocatePool2` at `0x14006a920`

## pseudocode

```c
void __fastcall HsmiRpCompressBuffer(UCHAR *a1, _DWORD *a2)
{
  __int64 Pool2; // rbx
  NTSTATUS CompressionWorkSpaceSize; // esi
  ULONG v6; // esi
  size_t v7; // r8
  ULONG v8; // [rsp+78h] [rbp+10h] BYREF
  ULONG FinalCompressedSize; // [rsp+80h] [rbp+18h] BYREF
  ULONG v10; // [rsp+88h] [rbp+20h] BYREF

  v8 = 0;
  v10 = 0;
  FinalCompressedSize = 0;
  if ( *a2 >= 0x100u )
  {
    Pool2 = 0;
    CompressionWorkSpaceSize = RtlGetCompressionWorkSpaceSize(2u, &v8, &v10);
    if ( CompressionWorkSpaceSize >= 0 )
    {
      v8 += *a2;
      Pool2 = ExAllocatePool2(256, v8, 1884451656);
      if ( !Pool2 )
        CompressionWorkSpaceSize = -1073741670;
    }
    if ( CompressionWorkSpaceSize >= 0
      && RtlCompressBuffer(
           2u,
           a1 + 4,
           *a2 - 4,
           (PUCHAR)(Pool2 + 4),
           *a2 - 4,
           0x1000u,
           &FinalCompressedSize,
           (PVOID)(Pool2 + (unsigned int)*a2)) >= 0 )
    {
      v6 = FinalCompressedSize;
      v7 = FinalCompressedSize;
      if ( FinalCompressedSize < (unsigned __int64)(unsigned int)*a2 - 4 )
      {
        *(_DWORD *)a1 |= 0x8000u;
        memmove(a1 + 4, (const void *)(Pool2 + 4), v7);
        *a2 = v6 + 4;
      }
    }
    if ( Pool2 )
      ExFreePoolWithTag((PVOID)Pool2, 0x70527348u);
  }
}

```

## disassembly

```asm
0x14006a8b0  mov     rax, rsp
0x14006a8b3  mov     [rax+8], rbx
0x14006a8b7  push    rbp
0x14006a8b8  push    rsi
0x14006a8b9  push    rdi
0x14006a8ba  push    r14
0x14006a8bc  push    r15
0x14006a8be  sub     rsp, 40h
0x14006a8c2  mov     r14d, 100h
0x14006a8c8  mov     dword ptr [rax+10h], 0
0x14006a8cf  mov     rdi, rdx
0x14006a8d2  mov     rbp, rcx
0x14006a8d5  mov     dword ptr [rax+20h], 0
0x14006a8dc  mov     dword ptr [rax+18h], 0
0x14006a8e3  cmp     [rdx], r14d
0x14006a8e6  jb      loc_14006A99C
0x14006a8ec  xor     ebx, ebx
0x14006a8ee  lea     r8, [rax+20h]; CompressFragmentWorkSpaceSize
0x14006a8f2  lea     rdx, [rax+10h]; CompressBufferWorkSpaceSize
0x14006a8f6  lea     ecx, [rbx+2]; CompressionFormatAndEngine
0x14006a8f9  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x14006a900  nop     dword ptr [rax+rax+00h]
0x14006a905  mov     esi, eax
0x14006a907  test    eax, eax
0x14006a909  js      short loc_14006A93A
0x14006a90b  mov     eax, [rsp+68h+arg_8]
0x14006a90f  mov     r8d, 70527348h
0x14006a915  add     eax, [rdi]
0x14006a917  mov     ecx, r14d
0x14006a91a  mov     edx, eax
0x14006a91c  mov     [rsp+68h+arg_8], eax
0x14006a920  call    cs:__imp_ExAllocatePool2
0x14006a927  nop     dword ptr [rax+rax+00h]
0x14006a92c  mov     rbx, rax
0x14006a92f  mov     eax, 0C000009Ah
0x14006a934  test    rbx, rbx
0x14006a937  cmovz   esi, eax
0x14006a93a  test    esi, esi
0x14006a93c  js      short loc_14006A983
0x14006a93e  mov     edx, [rdi]
0x14006a940  lea     rax, [rsp+68h+arg_10]
0x14006a948  mov     ecx, 2; CompressionFormatAndEngine
0x14006a94d  lea     r9, [rbx+4]; CompressedBuffer
0x14006a951  lea     r8d, [rdx-4]; UncompressedBufferSize
0x14006a955  add     rdx, rbx
0x14006a958  mov     [rsp+68h+WorkSpace], rdx; WorkSpace
0x14006a95d  lea     rdx, [rbp+4]; UncompressedBuffer
0x14006a961  mov     [rsp+68h+FinalCompressedSize], rax; FinalCompressedSize
0x14006a966  mov     [rsp+68h+UncompressedChunkSize], 1000h; UncompressedChunkSize
0x14006a96e  mov     [rsp+68h+CompressedBufferSize], r8d; CompressedBufferSize
0x14006a973  call    cs:__imp_RtlCompressBuffer
0x14006a97a  nop     dword ptr [rax+rax+00h]
0x14006a97f  test    eax, eax
0x14006a981  jns     short loc_14006A9AE
0x14006a983  test    rbx, rbx
0x14006a986  jz      short loc_14006A99C
0x14006a988  mov     edx, 70527348h; Tag
0x14006a98d  mov     rcx, rbx; P
0x14006a990  call    cs:__imp_ExFreePoolWithTag
0x14006a997  nop     dword ptr [rax+rax+00h]
0x14006a99c  mov     rbx, [rsp+68h+arg_0]
0x14006a9a1  add     rsp, 40h
0x14006a9a5  pop     r15
0x14006a9a7  pop     r14
0x14006a9a9  pop     rdi
0x14006a9aa  pop     rsi
0x14006a9ab  pop     rbp
0x14006a9ac  retn
0x14006a9ae  mov     esi, [rsp+68h+arg_10]
0x14006a9b5  mov     eax, [rdi]
0x14006a9b7  mov     r8d, esi; Size
0x14006a9ba  sub     rax, 4
0x14006a9be  cmp     rsi, rax
0x14006a9c1  jnb     short loc_14006A983
0x14006a9c3  bts     dword ptr [rbp+0], 0Fh
0x14006a9c8  lea     rdx, [rbx+4]; Src
0x14006a9cc  lea     rcx, [rbp+4]; void *
0x14006a9d0  call    memmove
0x14006a9d5  lea     eax, [rsi+4]
0x14006a9d8  mov     [rdi], eax
0x14006a9da  jmp     short loc_14006A983
```
