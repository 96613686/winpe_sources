# HsmiDecompressBuffer

- ea: `0x14005f198`
- end: `0x14005f2ac`
- name: `HsmiDecompressBuffer`
- size: `276`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14005074c`

## callees

- `0x140003c50`
- `0x14005f198`
- `0x14005f2b4`

## import_xrefs

- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14005f242`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14005f242`
- `ntoskrnl!RtlDecompressBufferEx` at `0x14005f1ff`
- `ntoskrnl!RtlDecompressBufferEx` at `0x14005f1ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f29b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f29b`
- `ntoskrnl!ExAllocatePool2` at `0x14005f274`
- `ntoskrnl!ExAllocatePool2` at `0x14005f274`

## pseudocode

```c
__int64 __fastcall HsmiDecompressBuffer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        __int64 a7)
{
  __int64 SupportedCompressionType; // rax
  USHORT v10; // si
  void *Pool2; // rdi
  unsigned int CompressionWorkSpaceSize; // ebx
  ULONG CompressFragmentWorkSpaceSize; // [rsp+40h] [rbp-38h] BYREF
  ULONG CompressBufferWorkSpaceSize[13]; // [rsp+44h] [rbp-34h] BYREF

  CompressBufferWorkSpaceSize[0] = 0;
  CompressFragmentWorkSpaceSize = 0;
  SupportedCompressionType = HsmiFindSupportedCompressionType(a1, a2, a4);
  if ( !SupportedCompressionType )
  {
    CompressionWorkSpaceSize = -1073741217;
LABEL_7:
    HsmDbgBreakOnStatus(CompressionWorkSpaceSize);
    return CompressionWorkSpaceSize;
  }
  v10 = *(_WORD *)SupportedCompressionType;
  Pool2 = 0;
  if ( *(_BYTE *)(SupportedCompressionType + 3) )
  {
    CompressionWorkSpaceSize = RtlGetCompressionWorkSpaceSize(
                                 v10,
                                 CompressBufferWorkSpaceSize,
                                 &CompressFragmentWorkSpaceSize);
    HsmDbgBreakOnStatus(CompressionWorkSpaceSize);
    if ( (CompressionWorkSpaceSize & 0x80000000) != 0 )
      return CompressionWorkSpaceSize;
    if ( CompressFragmentWorkSpaceSize )
    {
      Pool2 = (void *)ExAllocatePool2(256, CompressFragmentWorkSpaceSize, 1917875016);
      if ( !Pool2 )
      {
        CompressionWorkSpaceSize = -1073741670;
        goto LABEL_7;
      }
    }
  }
  CompressionWorkSpaceSize = RtlDecompressBufferEx(v10, a3, a4, a5, a6, a7, Pool2);
  HsmDbgBreakOnStatus(CompressionWorkSpaceSize);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x72507348u);
  return CompressionWorkSpaceSize;
}

```

## disassembly

```asm
0x14005f198  push    rbx
0x14005f19a  push    rbp
0x14005f19b  push    rsi
0x14005f19c  push    rdi
0x14005f19d  push    r14
0x14005f19f  sub     rsp, 50h
0x14005f1a3  mov     r14, r8
0x14005f1a6  mov     [rsp+78h+CompressBufferWorkSpaceSize], 0
0x14005f1ae  mov     r8d, r9d
0x14005f1b1  mov     [rsp+78h+CompressFragmentWorkSpaceSize], 0
0x14005f1b9  mov     ebp, r9d
0x14005f1bc  call    HsmiFindSupportedCompressionType
0x14005f1c1  test    rax, rax
0x14005f1c4  jz      short loc_14005F227
0x14005f1c6  movzx   esi, word ptr [rax]
0x14005f1c9  xor     edi, edi
0x14005f1cb  cmp     [rax+3], dil
0x14005f1cf  jnz     short loc_14005F235
0x14005f1d1  mov     rax, [rsp+78h+arg_30]
0x14005f1d9  mov     r8d, ebp
0x14005f1dc  mov     r9, [rsp+78h+arg_20]
0x14005f1e4  mov     rdx, r14
0x14005f1e7  mov     [rsp+78h+var_48], rdi
0x14005f1ec  movzx   ecx, si
0x14005f1ef  mov     [rsp+78h+var_50], rax
0x14005f1f4  mov     eax, [rsp+78h+arg_28]
0x14005f1fb  mov     [rsp+78h+var_58], eax
0x14005f1ff  call    cs:__imp_RtlDecompressBufferEx
0x14005f206  nop     dword ptr [rax+rax+00h]
0x14005f20b  mov     ecx, eax
0x14005f20d  mov     ebx, eax
0x14005f20f  call    HsmDbgBreakOnStatus
0x14005f214  test    rdi, rdi
0x14005f217  jnz     short loc_14005F293
0x14005f219  mov     eax, ebx
0x14005f21b  add     rsp, 50h
0x14005f21f  pop     r14
0x14005f221  pop     rdi
0x14005f222  pop     rsi
0x14005f223  pop     rbp
0x14005f224  pop     rbx
0x14005f225  retn
0x14005f227  mov     ebx, 0C000025Fh
0x14005f22c  mov     ecx, ebx
0x14005f22e  call    HsmDbgBreakOnStatus
0x14005f233  jmp     short loc_14005F219
0x14005f235  lea     r8, [rsp+78h+CompressFragmentWorkSpaceSize]; CompressFragmentWorkSpaceSize
0x14005f23a  movzx   ecx, si; CompressionFormatAndEngine
0x14005f23d  lea     rdx, [rsp+78h+CompressBufferWorkSpaceSize]; CompressBufferWorkSpaceSize
0x14005f242  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x14005f249  nop     dword ptr [rax+rax+00h]
0x14005f24e  mov     ecx, eax
0x14005f250  mov     ebx, eax
0x14005f252  call    HsmDbgBreakOnStatus
0x14005f257  test    ebx, ebx
0x14005f259  js      short loc_14005F219
0x14005f25b  mov     eax, [rsp+78h+CompressFragmentWorkSpaceSize]
0x14005f25f  test    eax, eax
0x14005f261  jz      loc_14005F1D1
0x14005f267  mov     edx, eax
0x14005f269  mov     ecx, 100h
0x14005f26e  mov     r8d, 72507348h
0x14005f274  call    cs:__imp_ExAllocatePool2
0x14005f27b  nop     dword ptr [rax+rax+00h]
0x14005f280  mov     rdi, rax
0x14005f283  test    rax, rax
0x14005f286  jnz     loc_14005F1D1
0x14005f28c  mov     ebx, 0C000009Ah
0x14005f291  jmp     short loc_14005F22C
0x14005f293  mov     edx, 72507348h; Tag
0x14005f298  mov     rcx, rdi; P
0x14005f29b  call    cs:__imp_ExFreePoolWithTag
0x14005f2a2  nop     dword ptr [rax+rax+00h]
0x14005f2a7  jmp     loc_14005F219
```
