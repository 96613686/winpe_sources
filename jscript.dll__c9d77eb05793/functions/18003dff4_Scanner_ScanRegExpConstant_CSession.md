# Scanner::ScanRegExpConstant(CSession *)

- ea: `0x18003dff4`
- end: `0x18003e1c9`
- name: `?ScanRegExpConstant@Scanner@@AEAA?AW4tokens@@PEAVCSession@@@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18003dfc0`

## callees

- `0x18001d510`
- `0x18002daa0`
- `0x18002eff4`
- `0x18003d61c`
- `0x18003dff4`
- `0x18003e1d0`
- `0x18003e200`
- `0x180052840`
- `0x1800942d0`

## import_xrefs

- `msvcrt!free` at `0x18003e0d1`
- `msvcrt!free` at `0x18003e0f3`
- `msvcrt!free` at `0x18003e0d1`
- `msvcrt!free` at `0x18003e0f3`

## pseudocode

```c
__int64 __fastcall Scanner::ScanRegExpConstant(__int64 a1)
{
  const unsigned __int16 *v1; // rdx
  int v3; // eax
  bool v4; // zf
  int v5; // edi
  unsigned __int16 *v6; // rdx
  unsigned int *v7; // rax
  unsigned int v8; // ebx
  unsigned __int16 *v10; // rax
  HashTbl *v11; // rcx
  unsigned __int64 v12; // r8
  _DWORD *v13; // rcx
  int v14; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v15; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v16; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v17; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v18[264]; // [rsp+50h] [rbp-B0h] BYREF
  void *v19; // [rsp+158h] [rbp+58h]
  int v20; // [rsp+160h] [rbp+60h]
  __int64 v21; // [rsp+164h] [rbp+64h]
  __int64 v22; // [rsp+178h] [rbp+78h]
  void *Block; // [rsp+180h] [rbp+80h]
  int v24; // [rsp+190h] [rbp+90h]
  __int64 v25; // [rsp+198h] [rbp+98h] BYREF
  __m128i si128; // [rsp+1A0h] [rbp+A0h]

  v1 = *(const unsigned __int16 **)(a1 + 40);
  v19 = 0;
  v21 = 0;
  v20 = 0;
  v25 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  Block = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v14 = 0;
  v24 = 0;
  v22 = 0;
  v3 = RegExpComp::Compile(
         (RegExpComp *)v18,
         v1,
         (const unsigned __int16 **)&v15,
         (const unsigned __int16 **)&v16,
         (unsigned __int8 **)&v17,
         &v14);
  v4 = (*(_BYTE *)(a1 + 96) & 0x10) == 0;
  v5 = v3;
  v6 = v17;
  *(_QWORD *)(a1 + 72) = v17;
  if ( v4 )
  {
    v10 = v15;
    if ( v5 < 0 )
    {
      *(_QWORD *)(a1 + 40) = v15;
      *(_QWORD *)(a1 + 32) = v10;
      Scanner::FreeTemp((Scanner *)a1);
      RegExpBase::Error(*(RegExpBase **)(a1 + 56), v5);
    }
    if ( *v15 != 47 )
    {
      *(_QWORD *)(a1 + 40) = v15;
      Scanner::Error((Scanner *)a1, 1012);
    }
    v11 = *(HashTbl **)a1;
    v12 = (unsigned __int64)v14 >> 1;
    *(_QWORD *)(a1 + 40) = v16;
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = HashTbl::PidHashNameLen(v11, v6, v12, 1);
    Scanner::FreeTemp((Scanner *)a1);
    v7 = *(unsigned int **)(a1 + 8);
    v8 = 131;
  }
  else
  {
    Scanner::FreeTemp((Scanner *)a1);
    if ( v5 >= 0 && *v15 == 47 )
    {
      *(_QWORD *)(a1 + 40) = v16;
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = 0;
      v13 = *(_DWORD **)(a1 + 8);
      v8 = 131;
      *v13 = 131;
      RegExpComp::~RegExpComp((RegExpComp *)v18);
      return v8;
    }
    *(_QWORD *)(a1 + 40) = v15;
    v7 = *(unsigned int **)(a1 + 8);
    v8 = 126;
  }
  *v7 = v8;
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  NoRelAlloc::FreeAll((NoRelAlloc *)&v25);
  if ( v19 )
    free(v19);
  return v8;
}

```

## disassembly

```asm
0x18003dff4  push    rbp
0x18003dff6  push    rbx
0x18003dff7  push    rsi
0x18003dff8  push    rdi
0x18003dff9  lea     rbp, [rsp-0C8h]
0x18003e001  sub     rsp, 1C8h
0x18003e008  mov     rax, cs:__security_cookie
0x18003e00f  xor     rax, rsp
0x18003e012  mov     [rbp+0E0h+var_30], rax
0x18003e019  movdqa  xmm0, cs:__xmm@00004000000001000000000000000000
0x18003e021  lea     rax, [rsp+1E0h+var_1B0]
0x18003e026  mov     rdx, [rcx+28h]; unsigned __int16 *
0x18003e02a  lea     r9, [rsp+1E0h+var_1A0]; unsigned __int16 **
0x18003e02f  xor     esi, esi
0x18003e031  mov     [rsp+1E0h+var_1B8], rax; int *
0x18003e036  lea     rax, [rsp+1E0h+var_198]
0x18003e03b  mov     [rbp+0E0h+var_88], rsi
0x18003e03f  mov     rbx, rcx
0x18003e042  mov     [rsp+1E0h+var_1C0], rax; unsigned __int8 **
0x18003e047  lea     r8, [rsp+1E0h+var_1A8]; unsigned __int16 **
0x18003e04c  mov     [rbp+0E0h+var_7C], rsi
0x18003e050  lea     rcx, [rsp+1E0h+var_190]; this
0x18003e055  mov     [rbp+0E0h+var_80], esi
0x18003e058  mov     [rbp+0E0h+var_48], rsi
0x18003e05f  movdqa  [rbp+0E0h+var_40], xmm0
0x18003e067  mov     [rbp+0E0h+Block], rsi
0x18003e06e  mov     [rsp+1E0h+var_1A8], rsi
0x18003e073  mov     [rsp+1E0h+var_1A0], rsi
0x18003e078  mov     [rsp+1E0h+var_198], rsi
0x18003e07d  mov     [rsp+1E0h+var_1B0], esi
0x18003e081  mov     [rbp+0E0h+var_50], esi
0x18003e087  mov     [rbp+0E0h+var_68], rsi
0x18003e08b  call    ?Compile@RegExpComp@@IEAAJPEBGPEAPEBG1PEAPEAEPEAJ@Z; RegExpComp::Compile(ushort const *,ushort const * *,ushort const * *,uchar * *,long *)
0x18003e090  test    byte ptr [rbx+60h], 10h
0x18003e094  mov     edi, eax
0x18003e096  mov     rdx, [rsp+1E0h+var_198]; unsigned __int16 *
0x18003e09b  mov     [rbx+48h], rdx
0x18003e09f  jz      short loc_18003E116
0x18003e0a1  mov     rcx, rbx; this
0x18003e0a4  call    ?FreeTemp@Scanner@@AEAAXXZ; Scanner::FreeTemp(void)
0x18003e0a9  mov     rax, [rsp+1E0h+var_1A8]
0x18003e0ae  test    edi, edi
0x18003e0b0  jns     loc_18003E166
0x18003e0b6  mov     [rbx+28h], rax
0x18003e0ba  mov     rax, [rbx+8]
0x18003e0be  mov     ebx, 7Eh ; '~'
0x18003e0c3  mov     [rax], ebx
0x18003e0c5  mov     rcx, [rbp+0E0h+Block]; Block
0x18003e0cc  test    rcx, rcx
0x18003e0cf  jz      short loc_18003E0DE
0x18003e0d1  call    cs:__imp_free
0x18003e0d7  mov     [rbp+0E0h+Block], rsi
0x18003e0de  lea     rcx, [rbp+0E0h+var_48]; this
0x18003e0e5  call    ?FreeAll@NoRelAlloc@@QEAAXXZ; NoRelAlloc::FreeAll(void)
0x18003e0ea  mov     rcx, [rbp+0E0h+var_88]; Block
0x18003e0ee  test    rcx, rcx
0x18003e0f1  jz      short loc_18003E0F9
0x18003e0f3  call    cs:__imp_free
0x18003e0f9  mov     eax, ebx
0x18003e0fb  mov     rcx, [rbp+0E0h+var_30]
0x18003e102  xor     rcx, rsp; StackCookie
0x18003e105  call    __security_check_cookie
0x18003e10a  add     rsp, 1C8h
0x18003e111  pop     rdi
0x18003e112  pop     rsi
0x18003e113  pop     rbx
0x18003e114  pop     rbp
0x18003e115  retn
0x18003e116  mov     rax, [rsp+1E0h+var_1A8]
0x18003e11b  test    edi, edi
0x18003e11d  js      short loc_18003E19B
0x18003e11f  cmp     word ptr [rax], 2Fh ; '/'
0x18003e123  jnz     loc_18003E1B7
0x18003e129  movsxd  r8, [rsp+1E0h+var_1B0]
0x18003e12e  mov     r9d, 1; int
0x18003e134  mov     rax, [rsp+1E0h+var_1A0]
0x18003e139  mov     rcx, [rbx]; this
0x18003e13c  shr     r8, 1; int
0x18003e13f  mov     [rbx+28h], rax
0x18003e143  call    ?PidHashNameLen@HashTbl@@QEAAPEAUIdent@@PEBGJH@Z; HashTbl::PidHashNameLen(ushort const *,long,int)
0x18003e148  mov     rcx, [rbx+8]
0x18003e14c  mov     [rcx+8], rax
0x18003e150  mov     rcx, rbx; this
0x18003e153  call    ?FreeTemp@Scanner@@AEAAXXZ; Scanner::FreeTemp(void)
0x18003e158  mov     rax, [rbx+8]
0x18003e15c  mov     ebx, 83h
0x18003e161  jmp     loc_18003E0C3
0x18003e166  cmp     word ptr [rax], 2Fh ; '/'
0x18003e16a  jnz     loc_18003E0B6
0x18003e170  mov     rax, [rsp+1E0h+var_1A0]
0x18003e175  mov     [rbx+28h], rax
0x18003e179  mov     rax, [rbx+8]
0x18003e17d  mov     [rax+8], rsi
0x18003e181  mov     rcx, [rbx+8]
0x18003e185  mov     ebx, 83h
0x18003e18a  mov     [rcx], ebx
0x18003e18c  lea     rcx, [rsp+1E0h+var_190]; this
0x18003e191  call    ??1RegExpComp@@QEAA@XZ; RegExpComp::~RegExpComp(void)
0x18003e196  jmp     loc_18003E0F9
0x18003e19b  mov     rcx, rbx; this
0x18003e19e  mov     [rbx+28h], rax
0x18003e1a2  mov     [rbx+20h], rax
0x18003e1a6  call    ?FreeTemp@Scanner@@AEAAXXZ; Scanner::FreeTemp(void)
0x18003e1ab  mov     rcx, [rbx+38h]; this
0x18003e1af  mov     edx, edi; int
0x18003e1b1  call    ?Error@RegExpBase@@IEAAXJ@Z; RegExpBase::Error(long)
0x18003e1b7  mov     edx, 3F4h; int
0x18003e1bc  mov     [rbx+28h], rax
0x18003e1c0  mov     rcx, rbx; this
0x18003e1c3  call    ?Error@Scanner@@AEAAXH@Z; Scanner::Error(int)
```
