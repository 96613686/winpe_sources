# RefsEtwPostWriteEvent

- ea: `0x1c009d714`
- end: `0x1c009d89b`
- name: `RefsEtwPostWriteEvent`
- size: `391`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1c009a1f0`
- `0x1c009aee0`
- `0x1c009b0f0`
- `0x1c009d5c4`

## callees

- `0x1c003f35c`
- `0x1c006acc0`
- `0x1c009d714`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c009d743`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c009d7bc`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c009d743`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c009d7bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009d842`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009d853`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009d842`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c009d853`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c009d87f`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c009d87f`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1c009d829`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1c009d829`
- `ntoskrnl!ObfReferenceObject` at `0x1c009d78f`
- `ntoskrnl!ObfReferenceObject` at `0x1c009d78f`

## pseudocode

```c
__int64 __fastcall RefsEtwPostWriteEvent(__int64 a1)
{
  _OWORD *PoolWithTag; // rdi
  void *v3; // rcx
  unsigned int v4; // eax
  PVOID v5; // rax
  char v7; // [rsp+28h] [rbp-20h]
  char v8; // [rsp+30h] [rbp-18h]

  v8 = 0;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)528, 0x48u, 0x4E466552u);
  *PoolWithTag = *(_OWORD *)a1;
  PoolWithTag[1] = *(_OWORD *)(a1 + 16);
  PoolWithTag[2] = *(_OWORD *)(a1 + 32);
  PoolWithTag[3] = *(_OWORD *)(a1 + 48);
  *((_QWORD *)PoolWithTag + 8) = *(_QWORD *)(a1 + 64);
  if ( *(_WORD *)(a1 + 48) == 1 )
  {
    v3 = *(void **)(a1 + 56);
    if ( v3 )
      ObfReferenceObject(v3);
  }
  else
  {
    v4 = *(unsigned __int16 *)(a1 + 56);
    if ( (_WORD)v4 )
    {
      *(_OWORD *)((char *)PoolWithTag + 56) = *(_OWORD *)(a1 + 56);
      v5 = ExAllocatePoolWithTag((POOL_TYPE)528, v4, 0x4E466552u);
      *((_QWORD *)PoolWithTag + 8) = v5;
      memmove(v5, *(const void **)(a1 + 64), *(unsigned __int16 *)(a1 + 56));
    }
  }
  v7 = 0;
  return RefsPostSpecial(
           0,
           *((_QWORD *)PoolWithTag + 1),
           (unsigned int)&RefsEtwPostWriteEventWorker,
           (_DWORD)PoolWithTag,
           1,
           v7,
           v8,
           PoolWithTag);
}

```

## disassembly

```asm
0x1c009d714  mov     rax, rsp
0x1c009d717  mov     [rax+10h], rbx
0x1c009d71b  mov     [rax+18h], rsi
0x1c009d71f  mov     [rax+8], rcx
0x1c009d723  push    rdi
0x1c009d724  sub     rsp, 40h
0x1c009d728  mov     rbx, rcx
0x1c009d72b  xor     esi, esi
0x1c009d72d  mov     [rax-10h], rsi
0x1c009d731  mov     [rax-18h], sil
0x1c009d735  lea     edx, [rsi+48h]; NumberOfBytes
0x1c009d738  mov     ecx, 210h; PoolType
0x1c009d73d  mov     r8d, 4E466552h; Tag
0x1c009d743  call    cs:__imp_ExAllocatePoolWithTag
0x1c009d74a  nop     dword ptr [rax+rax+00h]
0x1c009d74f  mov     rdi, rax
0x1c009d752  mov     [rsp+48h+P], rax
0x1c009d757  movaps  xmm0, xmmword ptr [rbx]
0x1c009d75a  movups  xmmword ptr [rax], xmm0
0x1c009d75d  movaps  xmm1, xmmword ptr [rbx+10h]
0x1c009d761  movups  xmmword ptr [rax+10h], xmm1
0x1c009d765  movaps  xmm0, xmmword ptr [rbx+20h]
0x1c009d769  movups  xmmword ptr [rax+20h], xmm0
0x1c009d76d  movaps  xmm1, xmmword ptr [rbx+30h]
0x1c009d771  movups  xmmword ptr [rax+30h], xmm1
0x1c009d775  movsd   xmm0, qword ptr [rbx+40h]
0x1c009d77a  movsd   qword ptr [rax+40h], xmm0
0x1c009d77f  cmp     word ptr [rbx+30h], 1
0x1c009d784  jnz     short loc_1C009D79D
0x1c009d786  mov     rcx, [rbx+38h]; Object
0x1c009d78a  test    rcx, rcx
0x1c009d78d  jz      short loc_1C009D7DD
0x1c009d78f  call    cs:__imp_ObfReferenceObject
0x1c009d796  nop     dword ptr [rax+rax+00h]
0x1c009d79b  jmp     short loc_1C009D7DD
0x1c009d79d  movzx   eax, word ptr [rbx+38h]
0x1c009d7a1  test    ax, ax
0x1c009d7a4  jz      short loc_1C009D7DD
0x1c009d7a6  movups  xmm0, xmmword ptr [rbx+38h]
0x1c009d7aa  movdqu  xmmword ptr [rdi+38h], xmm0
0x1c009d7af  mov     edx, eax; NumberOfBytes
0x1c009d7b1  mov     ecx, 210h; PoolType
0x1c009d7b6  mov     r8d, 4E466552h; Tag
0x1c009d7bc  call    cs:__imp_ExAllocatePoolWithTag
0x1c009d7c3  nop     dword ptr [rax+rax+00h]
0x1c009d7c8  mov     [rdi+40h], rax
0x1c009d7cc  movzx   r8d, word ptr [rbx+38h]; Size
0x1c009d7d1  mov     rdx, [rbx+40h]; Src
0x1c009d7d5  mov     rcx, rax; void *
0x1c009d7d8  call    memmove
0x1c009d7dd  mov     [rsp+48h+var_20], sil
0x1c009d7e2  mov     [rsp+48h+var_28], 1
0x1c009d7e7  mov     r9, rdi
0x1c009d7ea  lea     r8, RefsEtwPostWriteEventWorker
0x1c009d7f1  mov     rdx, [rdi+8]
0x1c009d7f5  xor     ecx, ecx
0x1c009d7f7  call    RefsPostSpecial
0x1c009d7fc  mov     [rsp+48h+var_18], 1
0x1c009d801  jmp     short loc_1C009D860
0x1c009d803  cmp     [rsp+48h+var_18], 0
0x1c009d808  jnz     short loc_1C009D860
0x1c009d80a  mov     rbx, [rsp+48h+P]
0x1c009d80f  test    rbx, rbx
0x1c009d812  jz      short loc_1C009D860
0x1c009d814  mov     rax, [rsp+48h+arg_0]
0x1c009d819  cmp     word ptr [rax+30h], 1
0x1c009d81e  jnz     short loc_1C009D837
0x1c009d820  mov     rcx, [rbx+38h]; Object
0x1c009d824  test    rcx, rcx
0x1c009d827  jz      short loc_1C009D84E
0x1c009d829  call    cs:__imp_ObDereferenceObjectDeferDelete
0x1c009d830  nop     dword ptr [rax+rax+00h]
0x1c009d835  jmp     short loc_1C009D84E
0x1c009d837  mov     rcx, [rbx+40h]; P
0x1c009d83b  test    rcx, rcx
0x1c009d83e  jz      short loc_1C009D84E
0x1c009d840  xor     edx, edx; Tag
0x1c009d842  call    cs:__imp_ExFreePoolWithTag
0x1c009d849  nop     dword ptr [rax+rax+00h]
0x1c009d84e  xor     edx, edx; Tag
0x1c009d850  mov     rcx, rbx; P
0x1c009d853  call    cs:__imp_ExFreePoolWithTag
0x1c009d85a  nop     dword ptr [rax+rax+00h]
0x1c009d85f  nop
0x1c009d860  mov     rbx, [rsp+48h+arg_8]
0x1c009d865  mov     rsi, [rsp+48h+arg_10]
0x1c009d86a  add     rsp, 40h
0x1c009d86e  pop     rdi
0x1c009d86f  retn
0x1c009d871  push    rbp
0x1c009d873  sub     rsp, 30h
0x1c009d877  mov     rbp, rdx
0x1c009d87a  mov     rax, [rcx]
0x1c009d87d  mov     ecx, [rax]; Exception
0x1c009d87f  call    cs:__imp_FsRtlIsNtstatusExpected
0x1c009d886  nop     dword ptr [rax+rax+00h]
0x1c009d88b  xor     ecx, ecx
0x1c009d88d  test    al, al
0x1c009d88f  setnz   cl
0x1c009d892  mov     eax, ecx
0x1c009d894  add     rsp, 30h
0x1c009d898  pop     rbp
0x1c009d899  retn
```
