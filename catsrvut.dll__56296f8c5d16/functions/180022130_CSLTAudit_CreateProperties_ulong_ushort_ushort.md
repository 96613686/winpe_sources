# CSLTAudit::CreateProperties(ulong,ushort * *,ushort * *)

- ea: `0x180022130`
- end: `0x1800222bd`
- name: `?CreateProperties@CSLTAudit@@EEAAJKPEAPEAG0@Z`
- size: `397`
- prototype: `__int64 __fastcall(CSLTAudit *__hidden this, unsigned int, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180014f58`
- `0x180022130`
- `0x18005583a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800222a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800222a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022192`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022192`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSLTAudit::CreateProperties(
        CSLTAudit *this,
        unsigned int a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  __int64 v7; // rdx
  unsigned int v8; // ecx
  __int64 v9; // rax
  unsigned __int64 v10; // rbx
  wchar_t *v11; // rax
  STRSAFE_LPWSTR v12; // rdi
  int v13; // ebx
  unsigned int v14; // edi
  STRSAFE_LPWSTR pszDest; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int64 v17; // [rsp+38h] [rbp-8h] BYREF

  v7 = 0;
  if ( a2 )
  {
    v8 = 0;
    do
    {
      v9 = -1;
      do
        ++v9;
      while ( a3[v8][v9] );
      v7 += v9 + 5;
      ++v8;
    }
    while ( v8 < a2 );
  }
  v10 = v7 + 3;
  v17 = v7 + 3;
  v11 = (wchar_t *)CoTaskMemAlloc(saturated_mul(v7 + 3, 2u));
  v12 = v11;
  pszDest = v11;
  if ( !v11 )
  {
    v13 = -2147024882;
LABEL_17:
    CoTaskMemFree(v12);
    *a4 = 0;
    return (unsigned int)v13;
  }
  memset_0(v11, 0, 2 * v10);
  *a4 = v12;
  v13 = StringCchCopyExW(v12, v10, L"\r\n", &pszDest, &v17, 0x400u);
  if ( v13 < 0 )
  {
LABEL_16:
    v12 = pszDest;
    goto LABEL_17;
  }
  v14 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      v13 = StringCchCopyExW(pszDest, v17, L"\t\t", &pszDest, &v17, 0x400u);
      if ( v13 < 0 )
        break;
      v13 = StringCchCopyExW(pszDest, v17, a3[v14], &pszDest, &v17, 0x400u);
      if ( v13 < 0 )
        break;
      if ( v14 < a2 - 1 )
      {
        v13 = StringCchCopyExW(pszDest, v17, L"\r\n", &pszDest, &v17, 0x400u);
        if ( v13 < 0 )
          break;
      }
      if ( ++v14 >= a2 )
        return (unsigned int)v13;
    }
    goto LABEL_16;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180022130  push    rbp
0x180022132  push    rbx
0x180022133  push    rsi
0x180022134  push    rdi
0x180022135  push    r12
0x180022137  push    r14
0x180022139  push    r15
0x18002213b  mov     rbp, rsp
0x18002213e  sub     rsp, 40h
0x180022142  mov     r15, r9
0x180022145  mov     r14, r8
0x180022148  mov     esi, edx
0x18002214a  xor     r12d, r12d
0x18002214d  mov     edx, r12d
0x180022150  or      r9, 0FFFFFFFFFFFFFFFFh
0x180022154  test    esi, esi
0x180022156  jz      short loc_18002217B
0x180022158  mov     ecx, r12d
0x18002215b  mov     eax, ecx
0x18002215d  mov     r8, [r14+rax*8]
0x180022161  mov     rax, r9
0x180022164  inc     rax
0x180022167  cmp     [r8+rax*2], r12w
0x18002216c  jnz     short loc_180022164
0x18002216e  add     rdx, 5
0x180022172  add     rdx, rax
0x180022175  inc     ecx
0x180022177  cmp     ecx, esi
0x180022179  jb      short loc_18002215B
0x18002217b  lea     rbx, [rdx+3]
0x18002217f  mov     [rbp+var_8], rbx
0x180022183  mov     eax, 2
0x180022188  mul     rbx
0x18002218b  cmovb   rax, r9
0x18002218f  mov     rcx, rax; cb
0x180022192  call    cs:__imp_CoTaskMemAlloc
0x180022198  mov     rdi, rax
0x18002219b  mov     [rbp+pszDest], rax
0x18002219f  test    rax, rax
0x1800221a2  jnz     short loc_1800221AE
0x1800221a4  mov     ebx, 8007000Eh
0x1800221a9  jmp     loc_18002229F
0x1800221ae  lea     r8, [rbx+rbx]; Size
0x1800221b2  xor     edx, edx; Val
0x1800221b4  mov     rcx, rdi; void *
0x1800221b7  call    memset_0
0x1800221bc  mov     [r15], rdi
0x1800221bf  mov     [rsp+40h+var_18], 400h; unsigned int
0x1800221c7  lea     rax, [rbp+var_8]
0x1800221cb  mov     [rsp+40h+var_20], rax; unsigned __int64 *
0x1800221d0  lea     r9, [rbp+pszDest]; unsigned __int16 **
0x1800221d4  lea     r8, asc_180062E00; "\r\n"
0x1800221db  mov     rdx, rbx; unsigned __int64
0x1800221de  mov     rcx, rdi; pszDest
0x1800221e1  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800221e6  mov     ebx, eax
0x1800221e8  test    eax, eax
0x1800221ea  js      loc_18002229B
0x1800221f0  mov     edi, r12d
0x1800221f3  test    esi, esi
0x1800221f5  jz      loc_1800222AC
0x1800221fb  mov     [rsp+40h+var_18], 400h; unsigned int
0x180022203  lea     rax, [rbp+var_8]
0x180022207  mov     [rsp+40h+var_20], rax; unsigned __int64 *
0x18002220c  lea     r9, [rbp+pszDest]; unsigned __int16 **
0x180022210  lea     r8, asc_180062E08; "\t\t"
0x180022217  mov     rdx, [rbp+var_8]; unsigned __int64
0x18002221b  mov     rcx, [rbp+pszDest]; pszDest
0x18002221f  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180022224  mov     ebx, eax
0x180022226  test    eax, eax
0x180022228  js      short loc_18002229B
0x18002222a  mov     r8d, edi
0x18002222d  mov     [rsp+40h+var_18], 400h; unsigned int
0x180022235  lea     rax, [rbp+var_8]
0x180022239  mov     [rsp+40h+var_20], rax; unsigned __int64 *
0x18002223e  lea     r9, [rbp+pszDest]; unsigned __int16 **
0x180022242  mov     r8, [r14+r8*8]; unsigned __int16 *
0x180022246  mov     rdx, [rbp+var_8]; unsigned __int64
0x18002224a  mov     rcx, [rbp+pszDest]; pszDest
0x18002224e  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180022253  mov     ebx, eax
0x180022255  test    eax, eax
0x180022257  js      short loc_18002229B
0x180022259  lea     eax, [rsi-1]
0x18002225c  cmp     edi, eax
0x18002225e  jnb     short loc_18002228F
0x180022260  mov     [rsp+40h+var_18], 400h; unsigned int
0x180022268  lea     rax, [rbp+var_8]
0x18002226c  mov     [rsp+40h+var_20], rax; unsigned __int64 *
0x180022271  lea     r9, [rbp+pszDest]; unsigned __int16 **
0x180022275  lea     r8, asc_180062E00; "\r\n"
0x18002227c  mov     rdx, [rbp+var_8]; unsigned __int64
0x180022280  mov     rcx, [rbp+pszDest]; pszDest
0x180022284  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180022289  mov     ebx, eax
0x18002228b  test    eax, eax
0x18002228d  js      short loc_18002229B
0x18002228f  inc     edi
0x180022291  cmp     edi, esi
0x180022293  jb      loc_1800221FB
0x180022299  jmp     short loc_1800222AC
0x18002229b  mov     rdi, [rbp+pszDest]
0x18002229f  mov     rcx, rdi; pv
0x1800222a2  call    cs:__imp_CoTaskMemFree
0x1800222a8  nop
0x1800222a9  mov     [r15], r12
0x1800222ac  mov     eax, ebx
0x1800222ae  add     rsp, 40h
0x1800222b2  pop     r15
0x1800222b4  pop     r14
0x1800222b6  pop     r12
0x1800222b8  pop     rdi
0x1800222b9  pop     rsi
0x1800222ba  pop     rbx
0x1800222bb  pop     rbp
0x1800222bc  retn
```
