# rc4HmacBaseInitializeOld

- ea: `0x180006fa4`
- end: `0x180007083`
- name: `rc4HmacBaseInitializeOld`
- size: `223`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, size_t Size@<rdx>, char, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180007340`
- `0x180007490`
- `0x1800074c0`

## callees

- `0x1800054be`
- `0x180006b18`
- `0x180006fa4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006fca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006fca`

## pseudocode

```c
__int64 __fastcall rc4HmacBaseInitializeOld(void *Src, size_t Size, int a3, char a4, char a5, _QWORD *a6)
{
  unsigned int v6; // ebp
  _OWORD *v9; // rax
  _OWORD *v10; // rdi
  char v12; // bl
  UCHAR *v13; // r8
  _QWORD *v14; // rax
  int v15; // [rsp+70h] [rbp+18h] BYREF

  v15 = a3;
  v6 = Size;
  v9 = LocalAlloc(0, 0x11u);
  v10 = v9;
  if ( !v9 )
    return 3221225626LL;
  v12 = a5;
  v13 = (UCHAR *)&v15;
  if ( a5 )
    v13 = (UCHAR *)"fortybits";
  md5Hmac(Src, v6, v13, a5 != 0 ? 10 : 4, (UCHAR *)((unsigned __int64)&v15 & -(__int64)(a5 != 0)), a5 != 0 ? 4 : 0, v9);
  memset_0((char *)v10 + (-(__int64)(v12 != 0) & 0xFFFFFFFFFFFFFFF5uLL) + 16, 171, v12 != 0 ? 0xB : 0);
  v14 = a6;
  *((_BYTE *)v10 + 16) = a4;
  *v14 = v10;
  return 0;
}

```

## disassembly

```asm
0x180006fa4  mov     [rsp+arg_0], rbx
0x180006fa9  mov     [rsp+arg_8], rbp
0x180006fae  mov     [rsp+arg_10], r8d
0x180006fb3  push    rsi
0x180006fb4  push    rdi
0x180006fb5  push    r14
0x180006fb7  sub     rsp, 40h
0x180006fbb  mov     ebp, edx
0x180006fbd  mov     r14, rcx
0x180006fc0  mov     edx, 11h; uBytes
0x180006fc5  xor     ecx, ecx; uFlags
0x180006fc7  mov     sil, r9b
0x180006fca  call    cs:__imp_LocalAlloc
0x180006fd0  mov     rdi, rax
0x180006fd3  test    rax, rax
0x180006fd6  jnz     short loc_180006FE2
0x180006fd8  mov     eax, 0C000009Ah
0x180006fdd  jmp     loc_180007070
0x180006fe2  mov     bl, [rsp+58h+arg_20]
0x180006fe9  lea     r8, [rsp+58h+arg_10]
0x180006fee  mov     al, bl
0x180006ff0  mov     [rsp+58h+var_28], rdi; __int64
0x180006ff5  neg     al
0x180006ff7  mov     al, bl
0x180006ff9  sbb     edx, edx
0x180006ffb  and     edx, 4
0x180006ffe  neg     al
0x180007000  mov     [rsp+58h+var_30], edx; int
0x180007004  lea     rax, [rsp+58h+arg_10]
0x180007009  mov     edx, ebp; Size
0x18000700b  sbb     rcx, rcx
0x18000700e  and     rcx, rax
0x180007011  mov     al, bl
0x180007013  neg     al
0x180007015  mov     [rsp+58h+var_38], rcx; __int64
0x18000701a  lea     rax, aFortybits; "fortybits"
0x180007021  mov     rcx, r14; Src
0x180007024  sbb     r9d, r9d
0x180007027  and     r9d, 6
0x18000702b  add     r9d, 4
0x18000702f  test    bl, bl
0x180007031  cmovnz  r8, rax
0x180007035  call    md5Hmac
0x18000703a  mov     al, bl
0x18000703c  mov     edx, 0ABh; Val
0x180007041  neg     al
0x180007043  sbb     r8, r8
0x180007046  and     r8d, 0Bh; Size
0x18000704a  neg     bl
0x18000704c  sbb     rcx, rcx
0x18000704f  and     rcx, 0FFFFFFFFFFFFFFF5h
0x180007053  add     rcx, 10h
0x180007057  add     rcx, rdi; void *
0x18000705a  call    memset_0
0x18000705f  mov     rax, [rsp+58h+arg_28]
0x180007067  mov     [rdi+10h], sil
0x18000706b  mov     [rax], rdi
0x18000706e  xor     eax, eax
0x180007070  mov     rbx, [rsp+58h+arg_0]
0x180007075  mov     rbp, [rsp+58h+arg_8]
0x18000707a  add     rsp, 40h
0x18000707e  pop     r14
0x180007080  pop     rdi
0x180007081  pop     rsi
0x180007082  retn
```
