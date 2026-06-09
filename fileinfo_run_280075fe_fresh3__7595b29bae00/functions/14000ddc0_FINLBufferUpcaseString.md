# FINLBufferUpcaseString

- ea: `0x14000ddc0`
- end: `0x14000deaa`
- name: `FINLBufferUpcaseString`
- size: `234`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140016fa0`
- `0x140017284`

## callees

- `0x140003d80`
- `0x14000dd98`
- `0x14000ddc0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000de14`
- `ntoskrnl!ExAllocatePool2` at `0x14000de14`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14000de8c`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14000de8c`

## pseudocode

```c
__int64 __fastcall FINLBufferUpcaseString(wchar_t *a1, unsigned __int16 a2, __int64 a3)
{
  wchar_t *Pool2; // rsi
  unsigned int v7; // r14d
  unsigned int v8; // ebp
  UNICODE_STRING SourceString; // [rsp+20h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF

  Pool2 = *(wchar_t **)a3;
  SourceString = 0;
  v7 = a2 + 1;
  DestinationString = 0;
  if ( !Pool2 || v7 > *(_DWORD *)(a3 + 8) )
  {
    v8 = 256;
    if ( v7 > 0x100 )
      v8 = a2 + 1;
    Pool2 = (wchar_t *)ExAllocatePool2(256, 2LL * v8, 1651853638);
    if ( !Pool2 )
      return 3221225626LL;
    FINLBufferCleanup(a3);
    *(_QWORD *)(a3 + 8) = 0;
    *(_QWORD *)a3 = Pool2;
    *(_DWORD *)(a3 + 8) = v8;
  }
  memset(Pool2, 0, 2LL * v7);
  DestinationString.Buffer = *(wchar_t **)a3;
  SourceString.Buffer = a1;
  DestinationString.Length = 0;
  SourceString.Length = 2 * a2;
  SourceString.MaximumLength = 2 * a2;
  DestinationString.MaximumLength = 2 * a2;
  RtlUpcaseUnicodeString(&DestinationString, &SourceString, 0);
  return 0;
}

```

## disassembly

```asm
0x14000ddc0  push    rbx
0x14000ddc2  push    rbp
0x14000ddc3  push    rsi
0x14000ddc4  push    rdi
0x14000ddc5  push    r12
0x14000ddc7  push    r14
0x14000ddc9  push    r15
0x14000ddcb  sub     rsp, 40h
0x14000ddcf  mov     rsi, [r8]
0x14000ddd2  xorps   xmm0, xmm0
0x14000ddd5  movzx   r15d, dx
0x14000ddd9  xorps   xmm1, xmm1
0x14000dddc  mov     rdi, r8
0x14000dddf  mov     r12, rcx
0x14000dde2  movups  xmmword ptr [rsp+78h+SourceString.Length], xmm0
0x14000dde7  lea     r14d, [r15+1]
0x14000ddeb  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm1
0x14000ddf0  test    rsi, rsi
0x14000ddf3  jz      short loc_14000DDFB
0x14000ddf5  cmp     r14d, [r8+8]
0x14000ddf9  jbe     short loc_14000DE45
0x14000ddfb  mov     ecx, 100h
0x14000de00  mov     r8d, 62754946h
0x14000de06  cmp     r14d, ecx
0x14000de09  mov     ebp, ecx
0x14000de0b  cmova   ebp, r14d
0x14000de0f  mov     edx, ebp
0x14000de11  add     rdx, rdx
0x14000de14  call    cs:__imp_ExAllocatePool2
0x14000de1b  nop     dword ptr [rax+rax+00h]
0x14000de20  mov     rsi, rax
0x14000de23  test    rax, rax
0x14000de26  jnz     short loc_14000DE2F
0x14000de28  mov     eax, 0C000009Ah
0x14000de2d  jmp     short loc_14000DE9A
0x14000de2f  mov     rcx, rdi
0x14000de32  call    FINLBufferCleanup
0x14000de37  mov     qword ptr [rdi+8], 0
0x14000de3f  mov     [rdi], rsi
0x14000de42  mov     [rdi+8], ebp
0x14000de45  mov     r8d, r14d
0x14000de48  xor     edx, edx; Val
0x14000de4a  add     r8, r8; Size
0x14000de4d  mov     rcx, rsi; void *
0x14000de50  call    memset
0x14000de55  mov     rax, [rdi]
0x14000de58  lea     rdx, [rsp+78h+SourceString]; SourceString
0x14000de5d  add     r15w, r15w
0x14000de61  mov     [rsp+78h+DestinationString.Buffer], rax
0x14000de66  xor     eax, eax
0x14000de68  mov     [rsp+78h+SourceString.Buffer], r12
0x14000de6d  xor     r8d, r8d; AllocateDestinationString
0x14000de70  mov     [rsp+78h+DestinationString.Length], ax
0x14000de75  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x14000de7a  mov     [rsp+78h+SourceString.Length], r15w
0x14000de80  mov     [rsp+78h+SourceString.MaximumLength], r15w
0x14000de86  mov     [rsp+78h+DestinationString.MaximumLength], r15w
0x14000de8c  call    cs:__imp_RtlUpcaseUnicodeString
0x14000de93  nop     dword ptr [rax+rax+00h]
0x14000de98  xor     eax, eax
0x14000de9a  add     rsp, 40h
0x14000de9e  pop     r15
0x14000dea0  pop     r14
0x14000dea2  pop     r12
0x14000dea4  pop     rdi
0x14000dea5  pop     rsi
0x14000dea6  pop     rbp
0x14000dea7  pop     rbx
0x14000dea8  retn
```
