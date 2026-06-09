# CFileNameParts::CFileNameParts(ushort const *)

- ea: `0x180001ec0`
- end: `0x1800020e3`
- name: `??0CFileNameParts@@QEAA@PEBG@Z`
- size: `547`
- prototype: `CFileNameParts *__fastcall(CFileNameParts *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800047e0`

## callees

- `0x180001ec0`
- `0x180003f78`
- `0x180004d54`
- `0x180004ffc`
- `0x180005486`

## import_xrefs

- `USER32!CharNextW` at `0x18000200d`
- `USER32!CharNextW` at `0x18000201e`
- `USER32!CharNextW` at `0x18000202a`
- `USER32!CharNextW` at `0x18000206e`
- `USER32!CharNextW` at `0x18000200d`
- `USER32!CharNextW` at `0x18000201e`
- `USER32!CharNextW` at `0x18000202a`
- `USER32!CharNextW` at `0x18000206e`
- `USER32!CharPrevW` at `0x180001fd1`
- `USER32!CharPrevW` at `0x180001fd1`

## string_xrefs

- `0x180001f54`: `StringCchCopyEx failed with error: 0x%x\n`

## pseudocode

```c
CFileNameParts *__fastcall CFileNameParts::CFileNameParts(CFileNameParts *this, const size_t *a2)
{
  unsigned __int16 **v4; // r9
  int v5; // eax
  const WCHAR *v6; // r14
  CFileNameParts *v7; // r13
  const size_t *v8; // rbp
  const size_t *v9; // rbx
  LPWSTR v10; // r12
  CFileNameParts *v11; // rsi
  unsigned __int64 *v13; // [rsp+20h] [rbp-68h]

  if ( !a2 )
    return this;
  memset_0(this, 0, 0x20Au);
  *(_QWORD *)((char *)this + 522) = 0;
  *((_WORD *)this + 265) = 0;
  memset_0((char *)this + 532, 0, 0x202u);
  memset_0((char *)this + 1046, 0, 0x202u);
  memset_0((char *)this + 1560, 0, 0x202u);
  v5 = StringCchCopyExW((STRSAFE_LPWSTR)this, 0x105u, a2, v4, v13, 0x900u);
  if ( v5 < 0 )
  {
    MyDbgPrintfA(0xFFFFFFFFLL, "StringCchCopyEx failed with error: 0x%x\n", v5);
    return this;
  }
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = (const size_t *)this;
  v10 = (LPWSTR)a2;
  v11 = this;
  if ( !*(_WORD *)a2 )
    goto LABEL_25;
  while ( (__int64)(((char *)v10 - (char *)a2) & 0xFFFFFFFFFFFFFFFEuLL) <= 520 )
  {
    switch ( *v10 )
    {
      case '.':
        v8 = (const size_t *)v11;
        break;
      case '/':
        goto LABEL_10;
      case ':':
        if ( v7
          || v11 == this
          || this != (CFileNameParts *)CharPrevW((LPCWSTR)this, (LPCWSTR)v11)
          || (int)CmStringCchCopyNExW((unsigned __int16 *)this + 261, 5u, v9, ((v11 - (CFileNameParts *)v9) >> 1) + 1) < 0 )
        {
          return this;
        }
        v7 = v11;
        v9 = (const size_t *)CharNextW((LPCWSTR)v11);
        break;
      case '\\':
LABEL_10:
        v6 = (const WCHAR *)v11;
        break;
    }
    v10 = CharNextW(v10);
    v11 = (CFileNameParts *)CharNextW((LPCWSTR)v11);
    if ( !*v10 )
      break;
  }
  if ( !v6 )
  {
LABEL_21:
    if ( v8 && v8 > (const size_t *)v6 )
    {
      if ( (int)CmStringCchCopyNExW((unsigned __int16 *)this + 523, 0x101u, v9, ((char *)v8 - (char *)v9) >> 1) >= 0 )
        CmStringCchCopyNExW((unsigned __int16 *)this + 780, 0x101u, v8, 0x101u);
      return this;
    }
LABEL_25:
    CmStringCchCopyNExW((unsigned __int16 *)this + 523, 0x101u, v9, 0x101u);
    return this;
  }
  if ( (int)CmStringCchCopyNExW((unsigned __int16 *)this + 266, 0x101u, v9, (((char *)v6 - (char *)v9) >> 1) + 1) >= 0 )
  {
    v9 = (const size_t *)CharNextW(v6);
    goto LABEL_21;
  }
  return this;
}

```

## disassembly

```asm
0x180001ec0  push    rbx
0x180001ec2  push    rbp
0x180001ec3  push    rsi
0x180001ec4  push    rdi
0x180001ec5  push    r12
0x180001ec7  push    r13
0x180001ec9  push    r14
0x180001ecb  push    r15
0x180001ecd  sub     rsp, 48h
0x180001ed1  mov     r15, rdx
0x180001ed4  mov     rdi, rcx
0x180001ed7  test    rdx, rdx
0x180001eda  jz      loc_1800020CF
0x180001ee0  xor     edx, edx; Val
0x180001ee2  mov     r8d, 20Ah; Size
0x180001ee8  call    memset_0
0x180001eed  xor     ecx, ecx
0x180001eef  lea     rax, [rdi+20Ah]
0x180001ef6  mov     [rax], rcx
0x180001ef9  mov     ebx, 202h
0x180001efe  mov     [rax+8], cx
0x180001f02  mov     r8d, ebx; Size
0x180001f05  lea     rcx, [rdi+214h]; void *
0x180001f0c  xor     edx, edx; Val
0x180001f0e  call    memset_0
0x180001f13  lea     rcx, [rdi+416h]; void *
0x180001f1a  mov     r8d, ebx; Size
0x180001f1d  xor     edx, edx; Val
0x180001f1f  call    memset_0
0x180001f24  lea     rcx, [rdi+618h]; void *
0x180001f2b  mov     r8d, ebx; Size
0x180001f2e  xor     edx, edx; Val
0x180001f30  call    memset_0
0x180001f35  mov     r8, r15; unsigned __int16 *
0x180001f38  mov     dword ptr [rsp+88h+var_60], 900h; unsigned __int64 *
0x180001f40  mov     edx, 105h; unsigned __int64
0x180001f45  mov     rcx, rdi; pszDest
0x180001f48  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180001f4d  test    eax, eax
0x180001f4f  jns     short loc_180001F68
0x180001f51  mov     r8d, eax
0x180001f54  lea     rdx, aStringcchcopye; "StringCchCopyEx failed with error: 0x%x"...
0x180001f5b  or      ecx, 0FFFFFFFFh
0x180001f5e  call    MyDbgPrintfA
0x180001f63  jmp     loc_1800020CF
0x180001f68  xor     r14d, r14d
0x180001f6b  xor     r13d, r13d
0x180001f6e  xor     ebp, ebp
0x180001f70  xor     eax, eax
0x180001f72  mov     rbx, rdi
0x180001f75  mov     r12, r15
0x180001f78  mov     rsi, rdi
0x180001f7b  cmp     ax, [r15]
0x180001f7f  jz      loc_1800020B7
0x180001f85  mov     rax, r12
0x180001f88  sub     rax, r15
0x180001f8b  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001f8f  cmp     rax, 208h
0x180001f95  jg      loc_180002040
0x180001f9b  movzx   ecx, word ptr [r12]
0x180001fa0  sub     ecx, 2Eh ; '.'
0x180001fa3  jz      short loc_180002018
0x180001fa5  sub     ecx, 1
0x180001fa8  jz      short loc_180001FB4
0x180001faa  sub     ecx, 0Bh
0x180001fad  jz      short loc_180001FB9
0x180001faf  cmp     ecx, 22h ; '"'
0x180001fb2  jnz     short loc_18000201B
0x180001fb4  mov     r14, rsi
0x180001fb7  jmp     short loc_18000201B
0x180001fb9  test    r13, r13
0x180001fbc  jnz     loc_1800020CF
0x180001fc2  cmp     rsi, rdi
0x180001fc5  jz      loc_1800020CF
0x180001fcb  mov     rdx, rsi; lpszCurrent
0x180001fce  mov     rcx, rdi; lpszStart
0x180001fd1  call    cs:__imp_CharPrevW
0x180001fd7  cmp     rdi, rax
0x180001fda  jnz     loc_1800020CF
0x180001fe0  mov     r9, rsi
0x180001fe3  lea     edx, [r13+5]; unsigned __int64
0x180001fe7  sub     r9, rbx
0x180001fea  lea     rcx, [rdi+20Ah]; unsigned __int16 *
0x180001ff1  sar     r9, 1
0x180001ff4  mov     r8, rbx; unsigned __int16 *
0x180001ff7  inc     r9; unsigned __int64
0x180001ffa  call    ?CmStringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; CmStringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180001fff  test    eax, eax
0x180002001  js      loc_1800020CF
0x180002007  mov     rcx, rsi; lpsz
0x18000200a  mov     r13, rsi
0x18000200d  call    cs:__imp_CharNextW
0x180002013  mov     rbx, rax
0x180002016  jmp     short loc_18000201B
0x180002018  mov     rbp, rsi
0x18000201b  mov     rcx, r12; lpsz
0x18000201e  call    cs:__imp_CharNextW
0x180002024  mov     rcx, rsi; lpsz
0x180002027  mov     r12, rax
0x18000202a  call    cs:__imp_CharNextW
0x180002030  mov     rsi, rax
0x180002033  xor     eax, eax
0x180002035  cmp     ax, [r12]
0x18000203a  jnz     loc_180001F85
0x180002040  mov     esi, 101h
0x180002045  test    r14, r14
0x180002048  jz      short loc_180002077
0x18000204a  mov     r9, r14
0x18000204d  lea     rcx, [rdi+214h]; unsigned __int16 *
0x180002054  sub     r9, rbx
0x180002057  mov     r8, rbx; unsigned __int16 *
0x18000205a  sar     r9, 1
0x18000205d  mov     edx, esi; unsigned __int64
0x18000205f  inc     r9; unsigned __int64
0x180002062  call    ?CmStringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; CmStringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180002067  test    eax, eax
0x180002069  js      short loc_1800020CF
0x18000206b  mov     rcx, r14; lpsz
0x18000206e  call    cs:__imp_CharNextW
0x180002074  mov     rbx, rax
0x180002077  test    rbp, rbp
0x18000207a  jz      short loc_1800020B7
0x18000207c  cmp     rbp, r14
0x18000207f  jbe     short loc_1800020B7
0x180002081  mov     r9, rbp
0x180002084  lea     rcx, [rdi+416h]; unsigned __int16 *
0x18000208b  sub     r9, rbx
0x18000208e  mov     r8, rbx; unsigned __int16 *
0x180002091  sar     r9, 1; unsigned __int64
0x180002094  mov     rdx, rsi; unsigned __int64
0x180002097  call    ?CmStringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; CmStringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18000209c  test    eax, eax
0x18000209e  js      short loc_1800020CF
0x1800020a0  mov     r9, rsi; unsigned __int64
0x1800020a3  lea     rcx, [rdi+618h]; unsigned __int16 *
0x1800020aa  mov     r8, rbp; unsigned __int16 *
0x1800020ad  mov     rdx, rsi; unsigned __int64
0x1800020b0  call    ?CmStringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; CmStringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1800020b5  jmp     short loc_1800020CF
0x1800020b7  mov     r9d, 101h; unsigned __int64
0x1800020bd  lea     rcx, [rdi+416h]; unsigned __int16 *
0x1800020c4  mov     edx, r9d; unsigned __int64
0x1800020c7  mov     r8, rbx; unsigned __int16 *
0x1800020ca  call    ?CmStringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; CmStringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1800020cf  mov     rax, rdi
0x1800020d2  add     rsp, 48h
0x1800020d6  pop     r15
0x1800020d8  pop     r14
0x1800020da  pop     r13
0x1800020dc  pop     r12
0x1800020de  pop     rdi
0x1800020df  pop     rsi
0x1800020e0  pop     rbp
0x1800020e1  pop     rbx
0x1800020e2  retn
```
