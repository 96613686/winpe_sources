# HsmiRpCompressBuffer

- ea: `0x14006a790`
- end: `0x14006a8bc`
- name: `HsmiRpCompressBuffer`
- size: `300`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140067d04`
- `0x14006b1f4`

## callees

- `0x14001e280`
- `0x14006a790`

## import_xrefs

- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14006a7d9`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14006a7d9`
- `ntoskrnl!RtlCompressBuffer` at `0x14006a853`
- `ntoskrnl!RtlCompressBuffer` at `0x14006a853`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a870`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a870`
- `ntoskrnl!ExAllocatePool2` at `0x14006a800`
- `ntoskrnl!ExAllocatePool2` at `0x14006a800`

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
0x14006a790  mov     rax, rsp
0x14006a793  mov     [rax+8], rbx
0x14006a797  push    rbp
0x14006a798  push    rsi
0x14006a799  push    rdi
0x14006a79a  push    r14
0x14006a79c  push    r15
0x14006a79e  sub     rsp, 40h
0x14006a7a2  mov     r14d, 100h
0x14006a7a8  mov     dword ptr [rax+10h], 0
0x14006a7af  mov     rdi, rdx
0x14006a7b2  mov     rbp, rcx
0x14006a7b5  mov     dword ptr [rax+20h], 0
0x14006a7bc  mov     dword ptr [rax+18h], 0
0x14006a7c3  cmp     [rdx], r14d
0x14006a7c6  jb      loc_14006A87C
0x14006a7cc  xor     ebx, ebx
0x14006a7ce  lea     r8, [rax+20h]; CompressFragmentWorkSpaceSize
0x14006a7d2  lea     rdx, [rax+10h]; CompressBufferWorkSpaceSize
0x14006a7d6  lea     ecx, [rbx+2]; CompressionFormatAndEngine
0x14006a7d9  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x14006a7e0  nop     dword ptr [rax+rax+00h]
0x14006a7e5  mov     esi, eax
0x14006a7e7  test    eax, eax
0x14006a7e9  js      short loc_14006A81A
0x14006a7eb  mov     eax, [rsp+68h+arg_8]
0x14006a7ef  mov     r8d, 70527348h
0x14006a7f5  add     eax, [rdi]
0x14006a7f7  mov     ecx, r14d
0x14006a7fa  mov     edx, eax
0x14006a7fc  mov     [rsp+68h+arg_8], eax
0x14006a800  call    cs:__imp_ExAllocatePool2
0x14006a807  nop     dword ptr [rax+rax+00h]
0x14006a80c  mov     rbx, rax
0x14006a80f  mov     eax, 0C000009Ah
0x14006a814  test    rbx, rbx
0x14006a817  cmovz   esi, eax
0x14006a81a  test    esi, esi
0x14006a81c  js      short loc_14006A863
0x14006a81e  mov     edx, [rdi]
0x14006a820  lea     rax, [rsp+68h+arg_10]
0x14006a828  mov     ecx, 2; CompressionFormatAndEngine
0x14006a82d  lea     r9, [rbx+4]; CompressedBuffer
0x14006a831  lea     r8d, [rdx-4]; UncompressedBufferSize
0x14006a835  add     rdx, rbx
0x14006a838  mov     [rsp+68h+WorkSpace], rdx; WorkSpace
0x14006a83d  lea     rdx, [rbp+4]; UncompressedBuffer
0x14006a841  mov     [rsp+68h+FinalCompressedSize], rax; FinalCompressedSize
0x14006a846  mov     [rsp+68h+UncompressedChunkSize], 1000h; UncompressedChunkSize
0x14006a84e  mov     [rsp+68h+CompressedBufferSize], r8d; CompressedBufferSize
0x14006a853  call    cs:__imp_RtlCompressBuffer
0x14006a85a  nop     dword ptr [rax+rax+00h]
0x14006a85f  test    eax, eax
0x14006a861  jns     short loc_14006A88E
0x14006a863  test    rbx, rbx
0x14006a866  jz      short loc_14006A87C
0x14006a868  mov     edx, 70527348h; Tag
0x14006a86d  mov     rcx, rbx; P
0x14006a870  call    cs:__imp_ExFreePoolWithTag
0x14006a877  nop     dword ptr [rax+rax+00h]
0x14006a87c  mov     rbx, [rsp+68h+arg_0]
0x14006a881  add     rsp, 40h
0x14006a885  pop     r15
0x14006a887  pop     r14
0x14006a889  pop     rdi
0x14006a88a  pop     rsi
0x14006a88b  pop     rbp
0x14006a88c  retn
0x14006a88e  mov     esi, [rsp+68h+arg_10]
0x14006a895  mov     eax, [rdi]
0x14006a897  mov     r8d, esi; Size
0x14006a89a  sub     rax, 4
0x14006a89e  cmp     rsi, rax
0x14006a8a1  jnb     short loc_14006A863
0x14006a8a3  bts     dword ptr [rbp+0], 0Fh
0x14006a8a8  lea     rdx, [rbx+4]; Src
0x14006a8ac  lea     rcx, [rbp+4]; void *
0x14006a8b0  call    memmove
0x14006a8b5  lea     eax, [rsi+4]
0x14006a8b8  mov     [rdi], eax
0x14006a8ba  jmp     short loc_14006A863
```
