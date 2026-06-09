# rc4HmacBaseInitializeOld

- ea: `0x14000f150`
- end: `0x14000f23d`
- name: `rc4HmacBaseInitializeOld`
- size: `237`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, size_t Size@<rdx>, char, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14002e8a0`
- `0x14002e960`
- `0x14002e990`

## callees

- `0x14000eef8`
- `0x14000f150`
- `0x1400105c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000f17d`
- `ntoskrnl!ExAllocatePool2` at `0x14000f17d`

## pseudocode

```c
__int64 __fastcall rc4HmacBaseInitializeOld(void *Src, size_t Size, int a3, char a4, char a5, _QWORD *a6)
{
  unsigned int v6; // ebp
  _OWORD *Pool2; // rax
  _OWORD *v10; // rdi
  char v12; // bl
  UCHAR *v13; // r8
  _QWORD *v14; // rax
  int v15; // [rsp+70h] [rbp+18h] BYREF

  v15 = a3;
  v6 = Size;
  Pool2 = (_OWORD *)ExAllocatePool2(64, 17, 1887007299);
  v10 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  v12 = a5;
  v13 = (UCHAR *)&v15;
  if ( a5 )
    v13 = (UCHAR *)"fortybits";
  md5Hmac(
    Src,
    v6,
    v13,
    a5 != 0 ? 10 : 4,
    (UCHAR *)((unsigned __int64)&v15 & -(__int64)(a5 != 0)),
    a5 != 0 ? 4 : 0,
    Pool2);
  memset((char *)v10 + (-(__int64)(v12 != 0) & 0xFFFFFFFFFFFFFFF5uLL) + 16, 171, v12 != 0 ? 0xB : 0);
  v14 = a6;
  *((_BYTE *)v10 + 16) = a4;
  *v14 = v10;
  return 0;
}

```

## disassembly

```asm
0x14000f150  mov     [rsp+arg_0], rbx
0x14000f155  mov     [rsp+arg_8], rbp
0x14000f15a  mov     [rsp+arg_10], r8d
0x14000f15f  push    rsi
0x14000f160  push    rdi
0x14000f161  push    r14
0x14000f163  sub     rsp, 40h
0x14000f167  mov     ebp, edx
0x14000f169  mov     r14, rcx
0x14000f16c  mov     edx, 11h
0x14000f171  mov     r8d, 70797243h
0x14000f177  mov     sil, r9b
0x14000f17a  lea     ecx, [rdx+2Fh]
0x14000f17d  call    cs:__imp_ExAllocatePool2
0x14000f184  nop     dword ptr [rax+rax+00h]
0x14000f189  mov     rdi, rax
0x14000f18c  test    rax, rax
0x14000f18f  jnz     short loc_14000F19B
0x14000f191  mov     eax, 0C000009Ah
0x14000f196  jmp     loc_14000F229
0x14000f19b  mov     bl, [rsp+58h+arg_20]
0x14000f1a2  lea     r8, [rsp+58h+arg_10]
0x14000f1a7  mov     al, bl
0x14000f1a9  mov     [rsp+58h+var_28], rdi; __int64
0x14000f1ae  neg     al
0x14000f1b0  mov     al, bl
0x14000f1b2  sbb     edx, edx
0x14000f1b4  and     edx, 4
0x14000f1b7  neg     al
0x14000f1b9  mov     [rsp+58h+var_30], edx; int
0x14000f1bd  lea     rax, [rsp+58h+arg_10]
0x14000f1c2  mov     edx, ebp; Size
0x14000f1c4  sbb     rcx, rcx
0x14000f1c7  and     rcx, rax
0x14000f1ca  mov     al, bl
0x14000f1cc  neg     al
0x14000f1ce  mov     [rsp+58h+var_38], rcx; __int64
0x14000f1d3  lea     rax, aFortybits; "fortybits"
0x14000f1da  mov     rcx, r14; Src
0x14000f1dd  sbb     r9d, r9d
0x14000f1e0  and     r9d, 6
0x14000f1e4  add     r9d, 4
0x14000f1e8  test    bl, bl
0x14000f1ea  cmovnz  r8, rax
0x14000f1ee  call    md5Hmac
0x14000f1f3  mov     al, bl
0x14000f1f5  mov     edx, 0ABh; Val
0x14000f1fa  neg     al
0x14000f1fc  sbb     r8, r8
0x14000f1ff  and     r8d, 0Bh; Size
0x14000f203  neg     bl
0x14000f205  sbb     rcx, rcx
0x14000f208  and     rcx, 0FFFFFFFFFFFFFFF5h
0x14000f20c  add     rcx, 10h
0x14000f210  add     rcx, rdi; void *
0x14000f213  call    memset
0x14000f218  mov     rax, [rsp+58h+arg_28]
0x14000f220  mov     [rdi+10h], sil
0x14000f224  mov     [rax], rdi
0x14000f227  xor     eax, eax
0x14000f229  mov     rbx, [rsp+58h+arg_0]
0x14000f22e  mov     rbp, [rsp+58h+arg_8]
0x14000f233  add     rsp, 40h
0x14000f237  pop     r14
0x14000f239  pop     rdi
0x14000f23a  pop     rsi
0x14000f23b  retn
```
