# HrULIToStr(tagPROPVARIANT *,tagPROPVARIANT const *,ushort)

- ea: `0x1800526cc`
- end: `0x180052879`
- name: `?HrULIToStr@@YAJPEAUtagPROPVARIANT@@PEBU1@G@Z`
- size: `429`
- prototype: `__int64 __fastcall(struct tagPROPVARIANT *, const struct tagPROPVARIANT *, unsigned __int16)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180051308`
- `0x1800517b4`

## callees

- `0x180042800`
- `0x180050a98`
- `0x1800526cc`
- `0x18006141c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005273a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052805`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005273a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052805`
- `OLEAUT32!__imp_SysAllocString` at `0x180052845`
- `OLEAUT32!__imp_SysAllocString` at `0x180052845`

## pseudocode

```c
__int64 __fastcall HrULIToStr(struct tagPROPVARIANT *a1, const struct tagPROPVARIANT *a2, unsigned __int16 a3)
{
  unsigned int v3; // ebx
  int v4; // eax
  unsigned __int64 QuadPart; // rcx
  unsigned __int64 v7; // r8
  SIZE_T v8; // rdi
  void *v9; // rax
  LARGE_INTEGER v10; // rsi
  char *v11; // r9
  unsigned __int64 v12; // r11
  char *v13; // r10
  char v14; // al
  char *v15; // rdx
  unsigned int v16; // r8d
  char v17; // cl
  size_t v18; // rsi
  void *v19; // rax
  LARGE_INTEGER v20; // rdi
  BSTR v21; // rax
  char v23; // [rsp+20h] [rbp-328h] BYREF
  char v24; // [rsp+21h] [rbp-327h] BYREF
  OLECHAR Src[256]; // [rsp+120h] [rbp-228h] BYREF

  v3 = 0;
  v4 = a3;
  QuadPart = a2->uhVal.QuadPart;
  if ( a2->vt == 20 )
    v7 = QuadPart >> 63;
  else
    LODWORD(v7) = 0;
  switch ( v4 )
  {
    case 8:
      DwULIToWStr(QuadPart, Src, v7);
      v21 = SysAllocString(Src);
      if ( v21 )
      {
        a1->hVal.QuadPart = (LONGLONG)v21;
        return v3;
      }
      return (unsigned int)-2147024882;
    case 30:
      if ( (_DWORD)v7 )
        v23 = 45;
      v11 = &v23;
      if ( (_DWORD)v7 )
        v11 = &v24;
      v12 = -(__int64)QuadPart;
      v13 = v11;
      if ( !(_DWORD)v7 )
        v12 = QuadPart;
      do
      {
        v14 = v12 % 0xA;
        v12 /= 0xAu;
        *v13++ = v14 + 48;
      }
      while ( v12 && (unsigned int)v13 - (unsigned int)&v23 < 0xFE );
      *v13 = 0;
      v15 = v13 - 1;
      v16 = (_DWORD)v13 - (unsigned int)&v23 + 1;
      do
      {
        v17 = *v15;
        *v15-- = *v11;
        *v11++ = v17;
      }
      while ( v11 < v15 );
      v18 = v16;
      v19 = CoTaskMemAlloc(v16);
      v20.QuadPart = (LONGLONG)v19;
      if ( v19 )
      {
        memcpy_0(v19, &v23, v18);
        a1->hVal = v20;
        return v3;
      }
      return (unsigned int)-2147024882;
    case 31:
      v8 = 2LL * DwULIToWStr(QuadPart, Src, v7);
      v9 = CoTaskMemAlloc(v8);
      v10.QuadPart = (LONGLONG)v9;
      if ( v9 )
      {
        memcpy_0(v9, Src, v8);
        a1->hVal = v10;
        return v3;
      }
      return (unsigned int)-2147024882;
  }
  return v3;
}

```

## disassembly

```asm
0x1800526cc  mov     [rsp+arg_10], rbx
0x1800526d1  push    rbp
0x1800526d2  push    rsi
0x1800526d3  push    rdi
0x1800526d4  sub     rsp, 330h
0x1800526db  mov     rax, cs:__security_cookie
0x1800526e2  xor     rax, rsp
0x1800526e5  mov     [rsp+348h+var_28], rax
0x1800526ed  xor     ebx, ebx
0x1800526ef  movzx   eax, r8w
0x1800526f3  cmp     word ptr [rdx], 14h
0x1800526f7  mov     rbp, rcx
0x1800526fa  mov     rcx, [rdx+8]; unsigned __int64
0x1800526fe  jnz     short loc_180052709
0x180052700  mov     r8, rcx
0x180052703  shr     r8, 3Fh
0x180052707  jmp     short loc_18005270C
0x180052709  xor     r8d, r8d; int
0x18005270c  mov     edx, eax
0x18005270e  sub     edx, 8
0x180052711  jz      loc_180052830
0x180052717  sub     edx, 16h
0x18005271a  jz      short loc_180052768
0x18005271c  cmp     edx, 1
0x18005271f  jnz     loc_180052854
0x180052725  lea     rdx, [rsp+348h+Src]; unsigned __int16 *
0x18005272d  call    ?DwULIToWStr@@YAK_KPEAGH@Z; DwULIToWStr(unsigned __int64,ushort *,int)
0x180052732  mov     edi, eax
0x180052734  add     rdi, rdi
0x180052737  mov     rcx, rdi; cb
0x18005273a  call    cs:__imp_CoTaskMemAlloc
0x180052740  mov     rsi, rax
0x180052743  test    rax, rax
0x180052746  jz      loc_180052813
0x18005274c  mov     r8, rdi; Size
0x18005274f  lea     rdx, [rsp+348h+Src]; Src
0x180052757  mov     rcx, rax; void *
0x18005275a  call    memcpy_0
0x18005275f  mov     [rbp+8], rsi
0x180052763  jmp     loc_180052854
0x180052768  test    r8d, r8d
0x18005276b  jz      short loc_180052772
0x18005276d  mov     [rsp+348h+var_328], 2Dh ; '-'
0x180052772  test    r8d, r8d
0x180052775  lea     r9, [rsp+348h+var_328]
0x18005277a  lea     rax, [rsp+348h+var_327]
0x18005277f  mov     r11, rcx
0x180052782  cmovnz  r9, rax
0x180052786  neg     r11
0x180052789  test    r8d, r8d
0x18005278c  mov     r10, r9
0x18005278f  cmovz   r11, rcx
0x180052793  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18005279d  mul     r11
0x1800527a0  shr     rdx, 3
0x1800527a4  mov     al, dl
0x1800527a6  shl     al, 2
0x1800527a9  lea     ecx, [rax+rdx]
0x1800527ac  add     cl, cl
0x1800527ae  sub     r11b, cl
0x1800527b1  mov     al, r11b
0x1800527b4  mov     r11, rdx
0x1800527b7  add     al, 30h ; '0'
0x1800527b9  mov     [r10], al
0x1800527bc  inc     r10
0x1800527bf  test    rdx, rdx
0x1800527c2  jz      short loc_1800527D5
0x1800527c4  lea     rcx, [rsp+348h+var_328]
0x1800527c9  mov     eax, r10d
0x1800527cc  sub     eax, ecx
0x1800527ce  cmp     eax, 0FEh
0x1800527d3  jb      short loc_180052793
0x1800527d5  lea     rax, [rsp+348h+var_328]
0x1800527da  mov     [r10], bl
0x1800527dd  mov     r8d, r10d
0x1800527e0  lea     rdx, [r10-1]
0x1800527e4  sub     r8d, eax
0x1800527e7  inc     r8d
0x1800527ea  mov     al, [r9]
0x1800527ed  mov     cl, [rdx]
0x1800527ef  mov     [rdx], al
0x1800527f1  dec     rdx
0x1800527f4  mov     [r9], cl
0x1800527f7  inc     r9
0x1800527fa  cmp     r9, rdx
0x1800527fd  jb      short loc_1800527EA
0x1800527ff  mov     ecx, r8d; cb
0x180052802  mov     esi, r8d
0x180052805  call    cs:__imp_CoTaskMemAlloc
0x18005280b  mov     rdi, rax
0x18005280e  test    rax, rax
0x180052811  jnz     short loc_18005281A
0x180052813  mov     ebx, 8007000Eh
0x180052818  jmp     short loc_180052854
0x18005281a  mov     r8, rsi; Size
0x18005281d  lea     rdx, [rsp+348h+var_328]; Src
0x180052822  mov     rcx, rdi; void *
0x180052825  call    memcpy_0
0x18005282a  mov     [rbp+8], rdi
0x18005282e  jmp     short loc_180052854
0x180052830  lea     rdx, [rsp+348h+Src]; unsigned __int16 *
0x180052838  call    ?DwULIToWStr@@YAK_KPEAGH@Z; DwULIToWStr(unsigned __int64,ushort *,int)
0x18005283d  lea     rcx, [rsp+348h+Src]; psz
0x180052845  call    cs:__imp_SysAllocString
0x18005284b  test    rax, rax
0x18005284e  jz      short loc_180052813
0x180052850  mov     [rbp+8], rax
0x180052854  mov     eax, ebx
0x180052856  mov     rcx, [rsp+348h+var_28]
0x18005285e  xor     rcx, rsp; StackCookie
0x180052861  call    __security_check_cookie
0x180052866  mov     rbx, [rsp+348h+arg_10]
0x18005286e  add     rsp, 330h
0x180052875  pop     rdi
0x180052876  pop     rsi
0x180052877  pop     rbp
0x180052878  retn
```
