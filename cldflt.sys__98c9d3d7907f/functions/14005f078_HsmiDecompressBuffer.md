# HsmiDecompressBuffer

- ea: `0x14005f078`
- end: `0x14005f18c`
- name: `HsmiDecompressBuffer`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14005062c`

## callees

- `0x140003c50`
- `0x14005f078`
- `0x14005f194`

## import_xrefs

- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14005f122`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14005f122`
- `ntoskrnl!RtlDecompressBufferEx` at `0x14005f0df`
- `ntoskrnl!RtlDecompressBufferEx` at `0x14005f0df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f17b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f17b`
- `ntoskrnl!ExAllocatePool2` at `0x14005f154`
- `ntoskrnl!ExAllocatePool2` at `0x14005f154`

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
  __int64 CompressionWorkSpaceSize; // rbx
  ULONG CompressFragmentWorkSpaceSize; // [rsp+40h] [rbp-38h] BYREF
  ULONG CompressBufferWorkSpaceSize[13]; // [rsp+44h] [rbp-34h] BYREF

  CompressBufferWorkSpaceSize[0] = 0;
  CompressFragmentWorkSpaceSize = 0;
  SupportedCompressionType = HsmiFindSupportedCompressionType(a1, a2, a4);
  if ( !SupportedCompressionType )
  {
    LODWORD(CompressionWorkSpaceSize) = -1073741217;
LABEL_7:
    HsmDbgBreakOnStatus((unsigned int)CompressionWorkSpaceSize);
    return (unsigned int)CompressionWorkSpaceSize;
  }
  v10 = *(_WORD *)SupportedCompressionType;
  Pool2 = 0;
  if ( *(_BYTE *)(SupportedCompressionType + 3) )
  {
    CompressionWorkSpaceSize = (unsigned int)RtlGetCompressionWorkSpaceSize(
                                               v10,
                                               CompressBufferWorkSpaceSize,
                                               &CompressFragmentWorkSpaceSize);
    HsmDbgBreakOnStatus(CompressionWorkSpaceSize);
    if ( (int)CompressionWorkSpaceSize < 0 )
      return (unsigned int)CompressionWorkSpaceSize;
    if ( CompressFragmentWorkSpaceSize )
    {
      Pool2 = (void *)ExAllocatePool2(256, CompressFragmentWorkSpaceSize, 1917875016);
      if ( !Pool2 )
      {
        LODWORD(CompressionWorkSpaceSize) = -1073741670;
        goto LABEL_7;
      }
    }
  }
  LODWORD(CompressionWorkSpaceSize) = RtlDecompressBufferEx(v10, a3, a4, a5, a6, a7, Pool2);
  HsmDbgBreakOnStatus((unsigned int)CompressionWorkSpaceSize);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x72507348u);
  return (unsigned int)CompressionWorkSpaceSize;
}

```

## disassembly

```asm
0x14005f078  push    rbx
0x14005f07a  push    rbp
0x14005f07b  push    rsi
0x14005f07c  push    rdi
0x14005f07d  push    r14
0x14005f07f  sub     rsp, 50h
0x14005f083  mov     r14, r8
0x14005f086  mov     [rsp+78h+CompressBufferWorkSpaceSize], 0
0x14005f08e  mov     r8d, r9d
0x14005f091  mov     [rsp+78h+CompressFragmentWorkSpaceSize], 0
0x14005f099  mov     ebp, r9d
0x14005f09c  call    HsmiFindSupportedCompressionType
0x14005f0a1  test    rax, rax
0x14005f0a4  jz      short loc_14005F107
0x14005f0a6  movzx   esi, word ptr [rax]
0x14005f0a9  xor     edi, edi
0x14005f0ab  cmp     [rax+3], dil
0x14005f0af  jnz     short loc_14005F115
0x14005f0b1  mov     rax, [rsp+78h+arg_30]
0x14005f0b9  mov     r8d, ebp
0x14005f0bc  mov     r9, [rsp+78h+arg_20]
0x14005f0c4  mov     rdx, r14
0x14005f0c7  mov     [rsp+78h+var_48], rdi
0x14005f0cc  movzx   ecx, si
0x14005f0cf  mov     [rsp+78h+var_50], rax
0x14005f0d4  mov     eax, [rsp+78h+arg_28]
0x14005f0db  mov     [rsp+78h+var_58], eax
0x14005f0df  call    cs:__imp_RtlDecompressBufferEx
0x14005f0e6  nop     dword ptr [rax+rax+00h]
0x14005f0eb  mov     ecx, eax
0x14005f0ed  mov     ebx, eax
0x14005f0ef  call    HsmDbgBreakOnStatus
0x14005f0f4  test    rdi, rdi
0x14005f0f7  jnz     short loc_14005F173
0x14005f0f9  mov     eax, ebx
0x14005f0fb  add     rsp, 50h
0x14005f0ff  pop     r14
0x14005f101  pop     rdi
0x14005f102  pop     rsi
0x14005f103  pop     rbp
0x14005f104  pop     rbx
0x14005f105  retn
0x14005f107  mov     ebx, 0C000025Fh
0x14005f10c  mov     ecx, ebx
0x14005f10e  call    HsmDbgBreakOnStatus
0x14005f113  jmp     short loc_14005F0F9
0x14005f115  lea     r8, [rsp+78h+CompressFragmentWorkSpaceSize]; CompressFragmentWorkSpaceSize
0x14005f11a  movzx   ecx, si; CompressionFormatAndEngine
0x14005f11d  lea     rdx, [rsp+78h+CompressBufferWorkSpaceSize]; CompressBufferWorkSpaceSize
0x14005f122  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x14005f129  nop     dword ptr [rax+rax+00h]
0x14005f12e  mov     ecx, eax
0x14005f130  mov     ebx, eax
0x14005f132  call    HsmDbgBreakOnStatus
0x14005f137  test    ebx, ebx
0x14005f139  js      short loc_14005F0F9
0x14005f13b  mov     eax, [rsp+78h+CompressFragmentWorkSpaceSize]
0x14005f13f  test    eax, eax
0x14005f141  jz      loc_14005F0B1
0x14005f147  mov     edx, eax
0x14005f149  mov     ecx, 100h
0x14005f14e  mov     r8d, 72507348h
0x14005f154  call    cs:__imp_ExAllocatePool2
0x14005f15b  nop     dword ptr [rax+rax+00h]
0x14005f160  mov     rdi, rax
0x14005f163  test    rax, rax
0x14005f166  jnz     loc_14005F0B1
0x14005f16c  mov     ebx, 0C000009Ah
0x14005f171  jmp     short loc_14005F10C
0x14005f173  mov     edx, 72507348h; Tag
0x14005f178  mov     rcx, rdi; P
0x14005f17b  call    cs:__imp_ExFreePoolWithTag
0x14005f182  nop     dword ptr [rax+rax+00h]
0x14005f187  jmp     loc_14005F0F9
```
