# WerpGenerateStackHash(_WER_STACK_FRAME *,ulong,WER_STACKHASH *)

- ea: `0x1800546d8`
- end: `0x180054930`
- name: `?WerpGenerateStackHash@@YAJPEAU_WER_STACK_FRAME@@KPEAUWER_STACKHASH@@@Z`
- size: `600`
- prototype: `__int64 __fastcall(struct _WER_STACK_FRAME *, unsigned int, struct WER_STACKHASH *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004edcc`

## callees

- `0x180021d38`
- `0x18003fb80`
- `0x1800546d8`
- `0x180054938`
- `0x180083bc2`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800548c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800548c4`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800547b8`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800547b8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180054842`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180054842`
- `bcrypt!BCryptHashData` at `0x1800547e1`
- `bcrypt!BCryptHashData` at `0x1800548a9`
- `bcrypt!BCryptHashData` at `0x1800547e1`
- `bcrypt!BCryptHashData` at `0x1800548a9`
- `bcrypt!BCryptCreateHash` at `0x18005476b`
- `bcrypt!BCryptCreateHash` at `0x18005476b`

## pseudocode

```c
__int64 __fastcall WerpGenerateStackHash(struct _WER_STACK_FRAME *a1, unsigned int a2, struct WER_STACKHASH *a3)
{
  unsigned int i; // r14d
  const WCHAR *v8; // r15
  int v9; // eax
  __int64 v10; // rdi
  unsigned int j; // ebx
  const WCHAR *v12; // r8
  __int64 v13; // rax
  signed int v14; // ebx
  signed int LastError; // eax
  __int128 v16; // xmm0
  unsigned __int64 v17; // [rsp+40h] [rbp-C0h] BYREF
  BCRYPT_HASH_HANDLE phHash[3]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR DestStr[264]; // [rsp+60h] [rbp-A0h] BYREF

  memset(phHash, 0, sizeof(phHash));
  memset_0(DestStr, 0, 0x208u);
  if ( !a2 )
    return 0;
  if ( *(_DWORD *)a3 > 1u )
    return 2147942487LL;
  if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, phHash, 0, 0, 0, 0, 0) < 0 )
    __fastfail(7u);
  for ( i = 0; i < a2; ++i )
  {
    v8 = (const WCHAR *)((char *)a1 + 1048 * i);
    v9 = LCMapStringW(0x7Fu, 0x100u, v8, -1, DestStr, 260);
    if ( !v9 )
    {
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
LABEL_29:
      CngRsa32Compat_MD5Final(phHash);
      return (unsigned int)v14;
    }
    v17 = v9 - 1LL;
    if ( BCryptHashData(phHash[0], (PUCHAR)DestStr, 2 * (v9 - 1), 0) < 0 )
      __fastfail(7u);
    if ( *(_DWORD *)a3 == 1 )
    {
      v10 = -1;
      do
        ++v10;
      while ( v8[v10] );
      for ( j = 0; j < 0xA; ++j )
      {
        v12 = `_werDetail::IsInExcludeList'::`2'::ExcludeModList[j];
        v13 = -1;
        do
          ++v13;
        while ( v12[v13] );
        if ( v10 == v13 && CompareStringOrdinal(v8, v10, v12, v10, 1) == 2 )
          goto LABEL_26;
      }
      v14 = StringCchPrintfW(DestStr, 0x104u, L"%0I64x", *((_QWORD *)v8 + 130));
      if ( v14 < 0 )
        goto LABEL_29;
      v14 = StringCchLengthW(DestStr, 0x104u, &v17);
      if ( v14 < 0 )
        goto LABEL_29;
      if ( BCryptHashData(phHash[0], (PUCHAR)DestStr, 2 * v17, 0) < 0 )
        __fastfail(7u);
    }
LABEL_26:
    ;
  }
  CngRsa32Compat_MD5Final(phHash);
  v16 = *(_OWORD *)&phHash[1];
  v14 = 0;
  *((_WORD *)a3 + 10) = phHash[1];
  *(_OWORD *)((char *)a3 + 4) = v16;
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800546d8  mov     [rsp-8+arg_8], rbx
0x1800546dd  push    rbp
0x1800546de  push    rsi
0x1800546df  push    rdi
0x1800546e0  push    r12
0x1800546e2  push    r13
0x1800546e4  push    r14
0x1800546e6  push    r15
0x1800546e8  lea     rbp, [rsp-180h]
0x1800546f0  sub     rsp, 280h
0x1800546f7  mov     rax, cs:__security_cookie
0x1800546fe  xor     rax, rsp
0x180054701  mov     [rbp+1B0h+var_40], rax
0x180054708  mov     rsi, r8
0x18005470b  mov     r12d, edx
0x18005470e  mov     r13, rcx
0x180054711  xorps   xmm0, xmm0
0x180054714  xor     eax, eax
0x180054716  lea     rcx, [rsp+2B0h+DestStr]; void *
0x18005471b  xor     edx, edx; Val
0x18005471d  mov     [rsp+2B0h+var_258], rax
0x180054722  mov     r8d, 208h; Size
0x180054728  movups  xmmword ptr [rsp+2B0h+phHash], xmm0
0x18005472d  call    memset_0
0x180054732  xor     edi, edi
0x180054734  test    r12d, r12d
0x180054737  jnz     short loc_180054740
0x180054739  xor     eax, eax
0x18005473b  jmp     loc_180054906
0x180054740  cmp     dword ptr [rsi], 1
0x180054743  jbe     short loc_18005474F
0x180054745  mov     eax, 80070057h
0x18005474a  jmp     loc_180054906
0x18005474f  xor     r9d, r9d; cbHashObject
0x180054752  mov     [rsp+2B0h+dwFlags], edi; dwFlags
0x180054756  mov     [rsp+2B0h+cbSecret], edi; cbSecret
0x18005475a  lea     rdx, [rsp+2B0h+phHash]; phHash
0x18005475f  xor     r8d, r8d; pbHashObject
0x180054762  mov     [rsp+2B0h+pbSecret], rdi; pbSecret
0x180054767  lea     ecx, [r9+21h]; hAlgorithm
0x18005476b  call    cs:__imp_BCryptCreateHash
0x180054771  test    eax, eax
0x180054773  jns     short loc_18005477C
0x180054775  mov     ecx, 7
0x18005477a  int     29h; Win8: RtlFailFast(ecx)
0x18005477c  mov     r14d, edi
0x18005477f  cmp     r14d, r12d
0x180054782  jnb     loc_1800548E5
0x180054788  mov     eax, r14d
0x18005478b  or      r9d, 0FFFFFFFFh; cchSrc
0x18005478f  imul    r15, rax, 418h
0x180054796  lea     rax, [rsp+2B0h+DestStr]
0x18005479b  mov     [rsp+2B0h+cbSecret], 104h; cchDest
0x1800547a3  add     r15, r13
0x1800547a6  mov     [rsp+2B0h+pbSecret], rax; lpDestStr
0x1800547ab  mov     r8, r15; lpSrcStr
0x1800547ae  mov     edx, 100h; dwMapFlags
0x1800547b3  mov     ecx, 7Fh; Locale
0x1800547b8  call    cs:__imp_LCMapStringW
0x1800547be  movsxd  r8, eax
0x1800547c1  test    eax, eax
0x1800547c3  jz      loc_1800548C4
0x1800547c9  mov     rcx, [rsp+2B0h+phHash]; hHash
0x1800547ce  lea     rdx, [rsp+2B0h+DestStr]; pbInput
0x1800547d3  dec     r8
0x1800547d6  xor     r9d, r9d; dwFlags
0x1800547d9  mov     [rsp+2B0h+var_270], r8
0x1800547de  add     r8d, r8d; cbInput
0x1800547e1  call    cs:__imp_BCryptHashData
0x1800547e7  test    eax, eax
0x1800547e9  jns     short loc_1800547F2
0x1800547eb  mov     ecx, 7
0x1800547f0  int     29h; Win8: RtlFailFast(ecx)
0x1800547f2  cmp     dword ptr [rsi], 1
0x1800547f5  jnz     loc_1800548BC
0x1800547fb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800547ff  xor     ecx, ecx
0x180054801  inc     rdi
0x180054804  cmp     [r15+rdi*2], cx
0x180054809  jnz     short loc_180054801
0x18005480b  mov     ebx, ecx
0x18005480d  cmp     ebx, 0Ah
0x180054810  jnb     short loc_180054853
0x180054812  mov     eax, ebx
0x180054814  lea     r8, ?ExcludeModList@?1??IsInExcludeList@_werDetail@@YAHPEBG@Z@4QBQEBGB; ushort const * const near * const `_werDetail::IsInExcludeList(ushort const *)'::`2'::ExcludeModList
0x18005481b  mov     r8, [r8+rax*8]; lpString2
0x18005481f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180054823  inc     rax
0x180054826  cmp     [r8+rax*2], cx
0x18005482b  jnz     short loc_180054823
0x18005482d  cmp     rdi, rax
0x180054830  jnz     short loc_18005484F
0x180054832  mov     r9d, edi; cchCount2
0x180054835  mov     dword ptr [rsp+2B0h+pbSecret], 1; bIgnoreCase
0x18005483d  mov     edx, edi; cchCount1
0x18005483f  mov     rcx, r15; lpString1
0x180054842  call    cs:__imp_CompareStringOrdinal
0x180054848  cmp     eax, 2
0x18005484b  jz      short loc_1800548BA
0x18005484d  xor     ecx, ecx
0x18005484f  inc     ebx
0x180054851  jmp     short loc_18005480D
0x180054853  mov     r9, [r15+410h]
0x18005485a  lea     r8, a0i64x; "%0I64x"
0x180054861  mov     r15d, 104h
0x180054867  lea     rcx, [rsp+2B0h+DestStr]; unsigned __int16 *
0x18005486c  mov     edx, r15d; unsigned __int64
0x18005486f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180054874  xor     edi, edi
0x180054876  mov     ebx, eax
0x180054878  test    eax, eax
0x18005487a  js      short loc_1800548D9
0x18005487c  lea     r8, [rsp+2B0h+var_270]; unsigned __int64 *
0x180054881  mov     edx, r15d; unsigned __int64
0x180054884  lea     rcx, [rsp+2B0h+DestStr]; unsigned __int16 *
0x180054889  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18005488e  mov     ebx, eax
0x180054890  test    eax, eax
0x180054892  js      short loc_1800548D9
0x180054894  mov     r8d, dword ptr [rsp+2B0h+var_270]
0x180054899  lea     rdx, [rsp+2B0h+DestStr]; pbInput
0x18005489e  mov     rcx, [rsp+2B0h+phHash]; hHash
0x1800548a3  add     r8d, r8d; cbInput
0x1800548a6  xor     r9d, r9d; dwFlags
0x1800548a9  call    cs:__imp_BCryptHashData
0x1800548af  test    eax, eax
0x1800548b1  jns     short loc_1800548BC
0x1800548b3  lea     ecx, [rdi+7]
0x1800548b6  int     29h; Win8: RtlFailFast(ecx)
0x1800548b8  jmp     short loc_1800548BC
0x1800548ba  xor     edi, edi
0x1800548bc  inc     r14d
0x1800548bf  jmp     loc_18005477F
0x1800548c4  call    cs:__imp_GetLastError
0x1800548ca  mov     ebx, eax
0x1800548cc  test    eax, eax
0x1800548ce  jle     short loc_1800548D9
0x1800548d0  movzx   ebx, ax
0x1800548d3  or      ebx, 80070000h
0x1800548d9  lea     rcx, [rsp+2B0h+phHash]
0x1800548de  call    CngRsa32Compat_MD5Final
0x1800548e3  jmp     short loc_180054904
0x1800548e5  lea     rcx, [rsp+2B0h+phHash]
0x1800548ea  call    CngRsa32Compat_MD5Final
0x1800548ef  movups  xmm0, xmmword ptr [rsp+2B0h+phHash+8]
0x1800548f4  movzx   eax, word ptr [rsp+2B0h+phHash+8]
0x1800548f9  mov     ebx, edi
0x1800548fb  mov     [rsi+14h], ax
0x1800548ff  movdqu  xmmword ptr [rsi+4], xmm0
0x180054904  mov     eax, ebx
0x180054906  mov     rcx, [rbp+1B0h+var_40]
0x18005490d  xor     rcx, rsp; StackCookie
0x180054910  call    __security_check_cookie
0x180054915  mov     rbx, [rsp+2B0h+arg_8]
0x18005491d  add     rsp, 280h
0x180054924  pop     r15
0x180054926  pop     r14
0x180054928  pop     r13
0x18005492a  pop     r12
0x18005492c  pop     rdi
0x18005492d  pop     rsi
0x18005492e  pop     rbp
0x18005492f  retn
```
