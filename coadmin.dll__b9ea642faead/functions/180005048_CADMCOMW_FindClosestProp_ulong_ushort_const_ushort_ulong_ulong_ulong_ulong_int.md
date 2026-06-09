# CADMCOMW::FindClosestProp(ulong,ushort const *,ushort * *,ulong,ulong,ulong,ulong,int)

- ea: `0x180005048`
- end: `0x180005288`
- name: `?FindClosestProp@CADMCOMW@@QEAAJKPEBGPEAPEAGKKKKH@Z`
- size: `576`
- prototype: `__int64 __usercall@<rax>(CADMCOMW *__hidden this@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, unsigned __int16 **@<r9>, unsigned int, unsigned int, unsigned int, unsigned int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006e44`

## callees

- `0x180005048`
- `0x180007068`
- `0x18000be20`
- `0x18000fb06`
- `0x180010010`

## import_xrefs

- `msvcrt!wcschr` at `0x1800051a2`
- `msvcrt!wcschr` at `0x1800051bd`
- `msvcrt!wcschr` at `0x1800051a2`
- `msvcrt!wcschr` at `0x1800051bd`
- `KERNEL32!LocalAlloc` at `0x180005139`
- `KERNEL32!LocalAlloc` at `0x180005139`
- `KERNEL32!LocalFree` at `0x180005217`
- `KERNEL32!LocalFree` at `0x180005217`

## pseudocode

```c
__int64 __fastcall CADMCOMW::FindClosestProp(
        CADMCOMW *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int a9)
{
  CADMCOMW *v10; // rdi
  int v11; // r15d
  const unsigned __int16 *v12; // rsi
  _WORD *v13; // rax
  __int64 v14; // r14
  __int64 v15; // rdi
  __int64 v16; // r12
  __int64 v17; // rcx
  SIZE_T v18; // r13
  unsigned __int16 *v19; // rbx
  size_t v20; // r12
  wchar_t *i; // rax
  unsigned __int16 *v22; // rdi
  int v24; // [rsp+30h] [rbp-40h] BYREF
  struct COpenHandle *v25; // [rsp+38h] [rbp-38h] BYREF
  void *Src; // [rsp+40h] [rbp-30h]
  __int128 v27; // [rsp+48h] [rbp-28h] BYREF
  __int128 v28; // [rsp+58h] [rbp-18h]
  __int64 v29; // [rsp+68h] [rbp-8h]

  a9 = 0;
  v29 = 0;
  a8 = 0;
  v25 = 0;
  v10 = this;
  v24 = 0;
  v27 = 0;
  v28 = 0;
  v11 = CADMCOMW::Lookup(this, a2, &a9, &a8, &v25);
  if ( v11 >= 0 )
  {
    v12 = &byte_1800127D8;
    if ( a3 )
      v12 = a3;
    v13 = *(_WORD **)v25;
    Src = *(void **)v25;
    if ( *v12 == 47 || *v12 == 92 )
      ++v12;
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( v12[v15] );
    v16 = -1;
    do
      ++v16;
    while ( v13[v16] );
    if ( (_DWORD)v15 )
    {
      v17 = (unsigned int)(v15 - 1);
      if ( v12[v17] == 47 || v12[v17] == 92 )
        LODWORD(v15) = v15 - 1;
    }
    v18 = 2 * ((unsigned int)v15 + (_DWORD)v16 + ((_DWORD)v15 != 0)) + 2;
    v19 = (unsigned __int16 *)LocalAlloc(0, v18);
    *a4 = v19;
    if ( v19 )
    {
      v20 = (unsigned int)v16;
      memcpy_0(v19, Src, v20 * 2);
      if ( (_DWORD)v15 )
      {
        v19[v20] = 47;
        memcpy_0(&v19[v20 + 1], v12, 2LL * (unsigned int)v15);
      }
      v19[(v18 >> 1) - 1] = 0;
      for ( i = wcschr(v19, 0x5Cu); i; i = wcschr(i, 0x5Cu) )
        *i = 47;
      do
        ++v14;
      while ( v19[v14] );
      v22 = &v19[v14];
      *(_QWORD *)&v27 = a5 | 0x400000000LL;
      *((_QWORD *)&v27 + 1) = __PAIR64__(a6, a7);
      LODWORD(v28) = 0;
      *((_QWORD *)&v28 + 1) = 0;
      LODWORD(v29) = 0;
      while ( 1 )
      {
        if ( v22 <= v19 )
        {
          *a4 = 0;
          LocalFree(v19);
          goto LABEL_27;
        }
        if ( *--v22 == 47 )
        {
          *v22 = 0;
          v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, __int128 *, int *))(**((_QWORD **)this + 4)
                                                                                                 + 168LL))(
                  *((_QWORD *)this + 4),
                  0,
                  v19,
                  &v27,
                  &v24);
          if ( v11 == -2147024774 )
            break;
        }
      }
      v11 = 0;
    }
    else
    {
      v11 = -2147024882;
    }
LABEL_27:
    v10 = this;
  }
  if ( v25 )
    COpenHandle::Release(v25, v10);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180005048  mov     [rsp-38h+arg_8], rbx
0x18000504d  mov     [rsp-38h+arg_18], r9
0x180005052  mov     [rsp-38h+arg_0], rcx
0x180005057  push    rbp
0x180005058  push    rsi
0x180005059  push    rdi
0x18000505a  push    r12
0x18000505c  push    r13
0x18000505e  push    r14
0x180005060  push    r15
0x180005062  mov     rbp, rsp
0x180005065  sub     rsp, 70h
0x180005069  xor     r13d, r13d
0x18000506c  lea     r9, [rbp+arg_38]; unsigned int *
0x180005070  xor     eax, eax
0x180005072  mov     [rbp+arg_40], r13d
0x180005079  xorps   xmm0, xmm0
0x18000507c  mov     [rbp+var_8], rax
0x180005080  lea     rax, [rbp+var_38]
0x180005084  mov     [rbp+arg_38], r13d
0x180005088  mov     rbx, r8
0x18000508b  mov     [rsp+70h+var_50], rax; struct COpenHandle **
0x180005090  lea     r8, [rbp+arg_40]; unsigned int *
0x180005097  mov     [rbp+var_38], r13
0x18000509b  mov     rdi, rcx
0x18000509e  mov     [rbp+var_40], r13d
0x1800050a2  movups  [rbp+var_28], xmm0
0x1800050a6  movups  [rbp+var_18], xmm0
0x1800050aa  call    ?Lookup@CADMCOMW@@QEAAJKPEAK0PEAPEAVCOpenHandle@@@Z; CADMCOMW::Lookup(ulong,ulong *,ulong *,COpenHandle * *)
0x1800050af  mov     r15d, eax
0x1800050b2  test    eax, eax
0x1800050b4  js      loc_180005221
0x1800050ba  mov     rax, [rbp+var_38]
0x1800050be  lea     rsi, byte_1800127D8
0x1800050c5  test    rbx, rbx
0x1800050c8  lea     r8d, [r13+2Fh]
0x1800050cc  lea     edx, [r13+5Ch]
0x1800050d0  cmovnz  rsi, rbx
0x1800050d4  mov     rax, [rax]
0x1800050d7  mov     [rbp+Src], rax
0x1800050db  cmp     [rsi], r8w
0x1800050df  jz      short loc_1800050E6
0x1800050e1  cmp     [rsi], dx
0x1800050e4  jnz     short loc_1800050EA
0x1800050e6  add     rsi, 2
0x1800050ea  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800050ee  mov     rdi, r14
0x1800050f1  inc     rdi
0x1800050f4  cmp     [rsi+rdi*2], r13w
0x1800050f9  jnz     short loc_1800050F1
0x1800050fb  mov     r12, r14
0x1800050fe  inc     r12
0x180005101  cmp     [rax+r12*2], r13w
0x180005106  jnz     short loc_1800050FE
0x180005108  test    edi, edi
0x18000510a  jz      short loc_18000511E
0x18000510c  lea     ecx, [rdi-1]
0x18000510f  cmp     [rsi+rcx*2], r8w
0x180005114  jz      short loc_18000511C
0x180005116  cmp     [rsi+rcx*2], dx
0x18000511a  jnz     short loc_18000511E
0x18000511c  mov     edi, ecx
0x18000511e  mov     eax, r13d
0x180005121  test    edi, edi
0x180005123  setnz   al
0x180005126  xor     ecx, ecx; uFlags
0x180005128  add     eax, r12d
0x18000512b  add     eax, edi
0x18000512d  lea     eax, ds:2[rax*2]
0x180005134  mov     edx, eax; uBytes
0x180005136  mov     r13d, eax
0x180005139  call    cs:__imp_LocalAlloc
0x18000513f  mov     rbx, rax
0x180005142  mov     rax, [rbp+arg_18]
0x180005146  mov     [rax], rbx
0x180005149  test    rbx, rbx
0x18000514c  jnz     short loc_180005159
0x18000514e  mov     r15d, 8007000Eh
0x180005154  jmp     loc_18000521D
0x180005159  mov     rdx, [rbp+Src]; Src
0x18000515d  mov     rcx, rbx; void *
0x180005160  mov     eax, r12d
0x180005163  lea     r12, [rax+rax]
0x180005167  mov     r8, r12; Size
0x18000516a  call    memcpy_0
0x18000516f  test    edi, edi
0x180005171  jz      short loc_18000518F
0x180005173  mov     r8d, edi
0x180005176  lea     rcx, [rbx+2]
0x18000517a  add     r8, r8; Size
0x18000517d  mov     word ptr [r12+rbx], 2Fh ; '/'
0x180005184  add     rcx, r12; void *
0x180005187  mov     rdx, rsi; Src
0x18000518a  call    memcpy_0
0x18000518f  xor     eax, eax
0x180005191  shr     r13, 1
0x180005194  mov     rcx, rbx; Str
0x180005197  lea     edi, [rax+5Ch]
0x18000519a  mov     [rbx+r13*2-2], ax
0x1800051a0  mov     edx, edi; Ch
0x1800051a2  call    cs:__imp_wcschr
0x1800051a8  xor     r13d, r13d
0x1800051ab  lea     r12d, [rdi-2Dh]
0x1800051af  test    rax, rax
0x1800051b2  jz      short loc_1800051C5
0x1800051b4  mov     edx, edi; Ch
0x1800051b6  mov     [rax], r12w
0x1800051ba  mov     rcx, rax; Str
0x1800051bd  call    cs:__imp_wcschr
0x1800051c3  jmp     short loc_1800051AF
0x1800051c5  inc     r14
0x1800051c8  cmp     [rbx+r14*2], r13w
0x1800051cd  jnz     short loc_1800051C5
0x1800051cf  mov     eax, [rbp+arg_20]
0x1800051d2  lea     rdi, [rbx+r14*2]
0x1800051d6  mov     rsi, [rbp+arg_0]
0x1800051da  mov     dword ptr [rbp+var_28], eax
0x1800051dd  mov     eax, [rbp+arg_30]
0x1800051e0  mov     dword ptr [rbp+var_28+8], eax
0x1800051e3  mov     eax, [rbp+arg_28]
0x1800051e6  mov     dword ptr [rbp+var_28+0Ch], eax
0x1800051e9  mov     dword ptr [rbp+var_28+4], 4
0x1800051f0  mov     dword ptr [rbp+var_18], r13d
0x1800051f4  mov     qword ptr [rbp+var_18+8], r13
0x1800051f8  mov     dword ptr [rbp+var_8], r13d
0x1800051fc  jmp     short loc_180005208
0x1800051fe  sub     rdi, 2
0x180005202  cmp     [rdi], r12w
0x180005206  jz      short loc_180005250
0x180005208  cmp     rdi, rbx
0x18000520b  ja      short loc_1800051FE
0x18000520d  mov     rax, [rbp+arg_18]
0x180005211  mov     rcx, rbx; hMem
0x180005214  mov     [rax], r13
0x180005217  call    cs:__imp_LocalFree
0x18000521d  mov     rdi, [rbp+arg_0]
0x180005221  mov     rax, [rbp+var_38]
0x180005225  test    rax, rax
0x180005228  jz      short loc_180005235
0x18000522a  mov     rdx, rdi; void *
0x18000522d  mov     rcx, rax; this
0x180005230  call    ?Release@COpenHandle@@QEAAXPEAX@Z; COpenHandle::Release(void *)
0x180005235  mov     rbx, [rsp+70h+arg_8]
0x18000523d  mov     eax, r15d
0x180005240  add     rsp, 70h
0x180005244  pop     r15
0x180005246  pop     r14
0x180005248  pop     r13
0x18000524a  pop     r12
0x18000524c  pop     rdi
0x18000524d  pop     rsi
0x18000524e  pop     rbp
0x18000524f  retn
0x180005250  mov     [rdi], r13w
0x180005254  lea     rdx, [rbp+var_40]
0x180005258  mov     rcx, [rsi+20h]
0x18000525c  lea     r9, [rbp+var_28]
0x180005260  mov     [rsp+70h+var_50], rdx
0x180005265  mov     r8, rbx
0x180005268  xor     edx, edx
0x18000526a  mov     rax, [rcx]
0x18000526d  mov     rax, [rax+0A8h]
0x180005274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005279  mov     r15d, eax
0x18000527c  cmp     eax, 8007007Ah
0x180005281  jnz     short loc_180005208
0x180005283  mov     r15d, r13d
0x180005286  jmp     short loc_18000521D
```
