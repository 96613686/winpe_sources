# EfspCreateStreamTransitionMetadata

- ea: `0x1400558c4`
- end: `0x1400559e7`
- name: `EfspCreateStreamTransitionMetadata`
- size: `291`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140050780`
- `0x140050cf0`
- `0x140053800`

## callees

- `0x14000c380`
- `0x1400558c4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400558fa`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400558fa`
- `ntoskrnl!ExAllocatePool2` at `0x14005593e`
- `ntoskrnl!ExAllocatePool2` at `0x14005593e`

## pseudocode

```c
__int64 __fastcall EfspCreateStreamTransitionMetadata(
        struct _UNICODE_STRING *a1,
        int a2,
        __int64 *a3,
        __int64 *a4,
        unsigned int *a5)
{
  unsigned __int16 v5; // di
  struct _UNICODE_STRING *p_DestinationString; // rbx
  int v10; // esi
  unsigned int v11; // ebp
  __int64 Pool2; // rax
  __int64 v13; // rdi
  __int64 v15; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-48h] BYREF

  v5 = 0;
  p_DestinationString = a1;
  DestinationString = 0;
  if ( !a1 )
  {
    RtlInitUnicodeString(&DestinationString, &word_14000FEA0);
    p_DestinationString = &DestinationString;
  }
  if ( p_DestinationString->Length > 8u )
  {
    if ( (((unsigned __int16)(p_DestinationString->Length - 8) + 7) & 0xFFFFFFF8) > 0xFFFF )
      return 3221225621LL;
    v5 = (p_DestinationString->Length - 8 + 7) & 0xFFF8;
  }
  v10 = v5;
  v11 = v5 + 72;
  Pool2 = ExAllocatePool2(256, v11, 1836279365);
  v13 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  *(_OWORD *)Pool2 = 0;
  *(_OWORD *)(Pool2 + 16) = 0;
  *(_OWORD *)(Pool2 + 32) = 0;
  *(_DWORD *)(Pool2 + 8) = 1;
  *(_QWORD *)Pool2 = 0x4E41525453534645LL;
  *(_WORD *)(Pool2 + 28) = p_DestinationString->Length;
  memmove((void *)(Pool2 + 40), p_DestinationString->Buffer, p_DestinationString->Length);
  *(_DWORD *)(v13 + 24) = v10 + 48;
  v15 = v13 + (unsigned int)(v10 + 48);
  *(_QWORD *)(v15 + 16) = 0;
  *(_QWORD *)v15 = 0x5446525453534645LL;
  *(_DWORD *)(v15 + 12) = a2;
  *(_DWORD *)(v15 + 8) = 1;
  *a3 = v13;
  *a5 = v11;
  *a4 = v15;
  return 0;
}

```

## disassembly

```asm
0x1400558c4  push    rbx
0x1400558c6  push    rbp
0x1400558c7  push    rsi
0x1400558c8  push    rdi
0x1400558c9  push    r12
0x1400558cb  push    r14
0x1400558cd  push    r15
0x1400558cf  sub     rsp, 30h
0x1400558d3  xor     edi, edi
0x1400558d5  xorps   xmm0, xmm0
0x1400558d8  mov     r14, r9
0x1400558db  mov     r15, r8
0x1400558de  mov     r12d, edx
0x1400558e1  mov     rbx, rcx
0x1400558e4  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1400558e9  test    rcx, rcx
0x1400558ec  jnz     short loc_14005590B
0x1400558ee  lea     rdx, word_14000FEA0; SourceString
0x1400558f5  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1400558fa  call    cs:__imp_RtlInitUnicodeString
0x140055901  nop     dword ptr [rax+rax+00h]
0x140055906  lea     rbx, [rsp+68h+DestinationString]
0x14005590b  movzx   eax, word ptr [rbx]
0x14005590e  cmp     ax, 8
0x140055912  jbe     short loc_14005592B
0x140055914  sub     ax, 8
0x140055918  movzx   eax, ax
0x14005591b  add     eax, 7
0x14005591e  and     eax, 0FFFFFFF8h
0x140055921  cmp     eax, 0FFFFh
0x140055926  ja      short loc_140055959
0x140055928  movzx   edi, ax
0x14005592b  movzx   esi, di
0x14005592e  mov     ecx, 100h
0x140055933  mov     r8d, 6D736645h
0x140055939  lea     ebp, [rsi+48h]
0x14005593c  mov     edx, ebp
0x14005593e  call    cs:__imp_ExAllocatePool2
0x140055945  nop     dword ptr [rax+rax+00h]
0x14005594a  mov     rdi, rax
0x14005594d  test    rax, rax
0x140055950  jnz     short loc_140055960
0x140055952  mov     eax, 0C000009Ah
0x140055957  jmp     short loc_1400559D7
0x140055959  mov     eax, 0C0000095h
0x14005595e  jmp     short loc_1400559D7
0x140055960  xorps   xmm0, xmm0
0x140055963  lea     rcx, [rdi+28h]; void *
0x140055967  movups  xmmword ptr [rax], xmm0
0x14005596a  movups  xmmword ptr [rax+10h], xmm0
0x14005596e  movups  xmmword ptr [rax+20h], xmm0
0x140055972  mov     dword ptr [rdi+8], 1
0x140055979  mov     rax, 4E41525453534645h
0x140055983  mov     [rdi], rax
0x140055986  movzx   eax, word ptr [rbx]
0x140055989  mov     [rdi+1Ch], ax
0x14005598d  movzx   r8d, word ptr [rbx]; Size
0x140055991  mov     rdx, [rbx+8]; Src
0x140055995  call    memmove
0x14005599a  lea     eax, [rsi+30h]
0x14005599d  mov     [rdi+18h], eax
0x1400559a0  mov     ecx, eax
0x1400559a2  mov     rax, 5446525453534645h
0x1400559ac  add     rcx, rdi
0x1400559af  mov     qword ptr [rcx+10h], 0
0x1400559b7  mov     [rcx], rax
0x1400559ba  mov     rax, [rsp+68h+arg_20]
0x1400559c2  mov     [rcx+0Ch], r12d
0x1400559c6  mov     dword ptr [rcx+8], 1
0x1400559cd  mov     [r15], rdi
0x1400559d0  mov     [rax], ebp
0x1400559d2  mov     [r14], rcx
0x1400559d5  xor     eax, eax
0x1400559d7  add     rsp, 30h
0x1400559db  pop     r15
0x1400559dd  pop     r14
0x1400559df  pop     r12
0x1400559e1  pop     rdi
0x1400559e2  pop     rsi
0x1400559e3  pop     rbp
0x1400559e4  pop     rbx
0x1400559e5  retn
```
