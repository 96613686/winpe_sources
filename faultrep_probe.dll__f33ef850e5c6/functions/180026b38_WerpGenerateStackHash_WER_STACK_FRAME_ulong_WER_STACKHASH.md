# WerpGenerateStackHash(_WER_STACK_FRAME *,ulong,WER_STACKHASH *)

- ea: `0x180026b38`
- end: `0x180026e03`
- name: `?WerpGenerateStackHash@@YAJPEAU_WER_STACK_FRAME@@KPEAUWER_STACKHASH@@@Z`
- size: `715`
- prototype: `__int64 __fastcall(struct _WER_STACK_FRAME *, unsigned int, struct WER_STACKHASH *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180026210`

## callees

- `0x180002890`
- `0x180003474`
- `0x180006684`
- `0x180026b38`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180026c18`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180026c18`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026c98`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026c98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026dbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026dbf`
- `bcrypt!BCryptDestroyHash` at `0x180026d75`
- `bcrypt!BCryptDestroyHash` at `0x180026dfb`
- `bcrypt!BCryptDestroyHash` at `0x180026d75`
- `bcrypt!BCryptDestroyHash` at `0x180026dfb`
- `bcrypt!BCryptHashData` at `0x180026c3e`
- `bcrypt!BCryptHashData` at `0x180026d2d`
- `bcrypt!BCryptHashData` at `0x180026c3e`
- `bcrypt!BCryptHashData` at `0x180026d2d`
- `bcrypt!BCryptCreateHash` at `0x180026bcb`
- `bcrypt!BCryptCreateHash` at `0x180026bcb`
- `bcrypt!BCryptFinishHash` at `0x180026d5f`
- `bcrypt!BCryptFinishHash` at `0x180026de5`
- `bcrypt!BCryptFinishHash` at `0x180026d5f`
- `bcrypt!BCryptFinishHash` at `0x180026de5`

## pseudocode

```c
__int64 __fastcall WerpGenerateStackHash(struct _WER_STACK_FRAME *a1, unsigned int a2, struct WER_STACKHASH *a3)
{
  unsigned int v6; // esi
  unsigned int v8; // r14d
  const WCHAR *v9; // r15
  int v10; // r8d
  __int64 v11; // rbx
  const WCHAR *v12; // r8
  __int64 v13; // rax
  unsigned int v14; // ebx
  __int64 v15; // rdx
  WCHAR *v16; // rax
  __int16 v17; // cx
  __int64 v18; // rax
  signed int LastError; // eax
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h]
  WCHAR DestStr[264]; // [rsp+60h] [rbp-A0h] BYREF

  v21 = 0;
  *(_OWORD *)phHash = 0;
  memset_0(DestStr, 0, 0x208u);
  v6 = 0;
  if ( !a2 )
    return 0;
  if ( *(_DWORD *)a3 > 1u )
    return 2147942487LL;
  if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, phHash, 0, 0, 0, 0, 0) < 0 )
    __fastfail(7u);
  v8 = 0;
  while ( 1 )
  {
    v9 = (const WCHAR *)((char *)a1 + 1048 * v8);
    v10 = LCMapStringW(0x7Fu, 0x100u, v9, -1, DestStr, 260);
    if ( !v10 )
      break;
    if ( BCryptHashData(phHash[0], (PUCHAR)DestStr, 2 * v10 - 2, 0) < 0 )
      __fastfail(7u);
    if ( *(_DWORD *)a3 == 1 )
    {
      v11 = -1;
      do
        ++v11;
      while ( v9[v11] );
      do
      {
        v12 = `_werDetail::IsInExcludeList'::`2'::ExcludeModList[v6];
        v13 = -1;
        do
          ++v13;
        while ( v12[v13] );
        if ( v11 == v13 && CompareStringOrdinal(v9, v11, v12, v11, 1) == 2 )
        {
          v6 = 0;
          goto LABEL_27;
        }
        ++v6;
      }
      while ( v6 < 0xA );
      v6 = 0;
      v14 = StringCchPrintfW(DestStr, 0x104u, L"%0I64x", *((_QWORD *)v9 + 130));
      if ( (v14 & 0x80000000) != 0 )
        goto LABEL_34;
      v15 = 260;
      v16 = DestStr;
      do
      {
        if ( !*v16 )
          break;
        ++v16;
        --v15;
      }
      while ( v15 );
      v14 = v15 == 0 ? 0x80070057 : 0;
      if ( !v15 )
        goto LABEL_34;
      if ( BCryptHashData(phHash[0], (PUCHAR)DestStr, 2 * (v15 != 0 ? 260 - v15 : 0), 0) < 0 )
        __fastfail(7u);
    }
LABEL_27:
    if ( ++v8 >= a2 )
    {
      if ( BCryptFinishHash(phHash[0], (PUCHAR)&phHash[1], 0x10u, 0) < 0 )
        __fastfail(7u);
      BCryptDestroyHash(phHash[0]);
      v17 = (__int16)phHash[1];
      v14 = 0;
      v18 = v21;
      *(BCRYPT_HASH_HANDLE *)((char *)a3 + 4) = phHash[1];
      *(_QWORD *)((char *)a3 + 12) = v18;
      *((_WORD *)a3 + 10) = v17;
      return v14;
    }
  }
  LastError = GetLastError();
  v14 = LastError;
  if ( LastError > 0 )
    v14 = (unsigned __int16)LastError | 0x80070000;
LABEL_34:
  if ( BCryptFinishHash(phHash[0], (PUCHAR)&phHash[1], 0x10u, 0) < 0 )
    __fastfail(7u);
  BCryptDestroyHash(phHash[0]);
  return v14;
}

```

## disassembly

```asm
0x180026b38  mov     [rsp-8+arg_8], rbx
0x180026b3d  push    rbp
0x180026b3e  push    rsi
0x180026b3f  push    rdi
0x180026b40  push    r12
0x180026b42  push    r13
0x180026b44  push    r14
0x180026b46  push    r15
0x180026b48  lea     rbp, [rsp-180h]
0x180026b50  sub     rsp, 280h
0x180026b57  mov     rax, cs:__security_cookie
0x180026b5e  xor     rax, rsp
0x180026b61  mov     [rbp+1B0h+var_40], rax
0x180026b68  mov     rdi, r8
0x180026b6b  mov     r12d, edx
0x180026b6e  mov     r13, rcx
0x180026b71  xorps   xmm0, xmm0
0x180026b74  xor     eax, eax
0x180026b76  lea     rcx, [rsp+2B0h+DestStr]; void *
0x180026b7b  xor     edx, edx; Val
0x180026b7d  mov     [rsp+2B0h+var_260], rax
0x180026b82  mov     r8d, 208h; Size
0x180026b88  movups  xmmword ptr [rsp+2B0h+phHash], xmm0
0x180026b8d  call    memset_0
0x180026b92  xor     esi, esi
0x180026b94  test    r12d, r12d
0x180026b97  jnz     short loc_180026BA0
0x180026b99  xor     eax, eax
0x180026b9b  jmp     loc_180026D95
0x180026ba0  cmp     dword ptr [rdi], 1
0x180026ba3  jbe     short loc_180026BAF
0x180026ba5  mov     eax, 80070057h
0x180026baa  jmp     loc_180026D95
0x180026baf  xor     r9d, r9d; cbHashObject
0x180026bb2  mov     [rsp+2B0h+dwFlags], esi; dwFlags
0x180026bb6  mov     [rsp+2B0h+cbSecret], esi; cbSecret
0x180026bba  lea     rdx, [rsp+2B0h+phHash]; phHash
0x180026bbf  xor     r8d, r8d; pbHashObject
0x180026bc2  mov     [rsp+2B0h+pbSecret], rsi; pbSecret
0x180026bc7  lea     ecx, [r9+21h]; hAlgorithm
0x180026bcb  call    cs:__imp_BCryptCreateHash
0x180026bd1  test    eax, eax
0x180026bd3  jns     short loc_180026BDC
0x180026bd5  mov     ecx, 7
0x180026bda  int     29h; Win8: RtlFailFast(ecx)
0x180026bdc  mov     r14d, esi
0x180026bdf  test    r12d, r12d
0x180026be2  jz      loc_180026D4E
0x180026be8  mov     eax, r14d
0x180026beb  or      r9d, 0FFFFFFFFh; cchSrc
0x180026bef  imul    r15, rax, 418h
0x180026bf6  lea     rax, [rsp+2B0h+DestStr]
0x180026bfb  mov     [rsp+2B0h+cbSecret], 104h; cchDest
0x180026c03  add     r15, r13
0x180026c06  mov     [rsp+2B0h+pbSecret], rax; lpDestStr
0x180026c0b  mov     r8, r15; lpSrcStr
0x180026c0e  mov     edx, 100h; dwMapFlags
0x180026c13  mov     ecx, 7Fh; Locale
0x180026c18  call    cs:__imp_LCMapStringW
0x180026c1e  movsxd  r8, eax
0x180026c21  test    eax, eax
0x180026c23  jz      loc_180026DBF
0x180026c29  mov     rcx, [rsp+2B0h+phHash]; hHash
0x180026c2e  lea     r8d, ds:0FFFFFFFFFFFFFFFEh[r8*2]; cbInput
0x180026c36  xor     r9d, r9d; dwFlags
0x180026c39  lea     rdx, [rsp+2B0h+DestStr]; pbInput
0x180026c3e  call    cs:__imp_BCryptHashData
0x180026c44  test    eax, eax
0x180026c46  jns     short loc_180026C4F
0x180026c48  mov     ecx, 7
0x180026c4d  int     29h; Win8: RtlFailFast(ecx)
0x180026c4f  cmp     dword ptr [rdi], 1
0x180026c52  jnz     loc_180026D42
0x180026c58  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180026c5c  inc     rbx
0x180026c5f  cmp     [r15+rbx*2], si
0x180026c64  jnz     short loc_180026C5C
0x180026c66  mov     eax, esi
0x180026c68  lea     r8, ?ExcludeModList@?1??IsInExcludeList@_werDetail@@YAHPEB_W@Z@4QBQEB_WB; wchar_t const * const near * const `_werDetail::IsInExcludeList(wchar_t const *)'::`2'::ExcludeModList
0x180026c6f  mov     r8, [r8+rax*8]; lpString2
0x180026c73  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026c77  xor     ecx, ecx
0x180026c79  inc     rax
0x180026c7c  cmp     [r8+rax*2], cx
0x180026c81  jnz     short loc_180026C79
0x180026c83  cmp     rbx, rax
0x180026c86  jnz     short loc_180026CA7
0x180026c88  mov     r9d, ebx; cchCount2
0x180026c8b  mov     dword ptr [rsp+2B0h+pbSecret], 1; bIgnoreCase
0x180026c93  mov     edx, ebx; cchCount1
0x180026c95  mov     rcx, r15; lpString1
0x180026c98  call    cs:__imp_CompareStringOrdinal
0x180026c9e  cmp     eax, 2
0x180026ca1  jz      loc_180026D40
0x180026ca7  inc     esi
0x180026ca9  cmp     esi, 0Ah
0x180026cac  jb      short loc_180026C66
0x180026cae  mov     r9, [r15+410h]
0x180026cb5  lea     r8, a0i64x; "%0I64x"
0x180026cbc  mov     r15d, 104h
0x180026cc2  lea     rcx, [rsp+2B0h+DestStr]; wchar_t *
0x180026cc7  mov     edx, r15d; unsigned __int64
0x180026cca  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180026ccf  xor     esi, esi
0x180026cd1  mov     ebx, eax
0x180026cd3  test    eax, eax
0x180026cd5  js      loc_180026DD4
0x180026cdb  mov     edx, r15d
0x180026cde  lea     rax, [rsp+2B0h+DestStr]
0x180026ce3  cmp     [rax], si
0x180026ce6  jz      short loc_180026CF2
0x180026ce8  add     rax, 2
0x180026cec  sub     rdx, 1
0x180026cf0  jnz     short loc_180026CE3
0x180026cf2  mov     rax, rdx
0x180026cf5  mov     rcx, r15
0x180026cf8  neg     rax
0x180026cfb  mov     rax, rdx
0x180026cfe  sbb     ebx, ebx
0x180026d00  sub     rcx, rdx
0x180026d03  not     ebx
0x180026d05  and     ebx, 80070057h
0x180026d0b  neg     rax
0x180026d0e  sbb     r8, r8
0x180026d11  and     r8, rcx
0x180026d14  test    rdx, rdx
0x180026d17  jz      loc_180026DD4
0x180026d1d  mov     rcx, [rsp+2B0h+phHash]; hHash
0x180026d22  lea     rdx, [rsp+2B0h+DestStr]; pbInput
0x180026d27  add     r8d, r8d; cbInput
0x180026d2a  xor     r9d, r9d; dwFlags
0x180026d2d  call    cs:__imp_BCryptHashData
0x180026d33  test    eax, eax
0x180026d35  jns     short loc_180026D42
0x180026d37  mov     ecx, 7
0x180026d3c  int     29h; Win8: RtlFailFast(ecx)
0x180026d3e  jmp     short loc_180026D42
0x180026d40  xor     esi, esi
0x180026d42  inc     r14d
0x180026d45  cmp     r14d, r12d
0x180026d48  jb      loc_180026BE8
0x180026d4e  mov     rcx, [rsp+2B0h+phHash]; hHash
0x180026d53  lea     rdx, [rsp+2B0h+phHash+8]; pbOutput
0x180026d58  xor     r9d, r9d; dwFlags
0x180026d5b  lea     r8d, [r9+10h]; cbOutput
0x180026d5f  call    cs:__imp_BCryptFinishHash
0x180026d65  test    eax, eax
0x180026d67  jns     short loc_180026D70
0x180026d69  mov     ecx, 7
0x180026d6e  int     29h; Win8: RtlFailFast(ecx)
0x180026d70  mov     rcx, [rsp+2B0h+phHash]; hHash
0x180026d75  call    cs:__imp_BCryptDestroyHash
0x180026d7b  mov     rcx, [rsp+2B0h+phHash+8]
0x180026d80  mov     ebx, esi
0x180026d82  mov     rax, [rsp+2B0h+var_260]
0x180026d87  mov     [rdi+4], rcx
0x180026d8b  mov     [rdi+0Ch], rax
0x180026d8f  mov     [rdi+14h], cx
0x180026d93  mov     eax, ebx
0x180026d95  mov     rcx, [rbp+1B0h+var_40]
0x180026d9c  xor     rcx, rsp; StackCookie
0x180026d9f  call    __security_check_cookie
0x180026da4  mov     rbx, [rsp+2B0h+arg_8]
0x180026dac  add     rsp, 280h
0x180026db3  pop     r15
0x180026db5  pop     r14
0x180026db7  pop     r13
0x180026db9  pop     r12
0x180026dbb  pop     rdi
0x180026dbc  pop     rsi
0x180026dbd  pop     rbp
0x180026dbe  retn
0x180026dbf  call    cs:__imp_GetLastError
0x180026dc5  mov     ebx, eax
0x180026dc7  test    eax, eax
0x180026dc9  jle     short loc_180026DD4
0x180026dcb  movzx   ebx, ax
0x180026dce  or      ebx, 80070000h
0x180026dd4  mov     rcx, [rsp+2B0h+phHash]; hHash
0x180026dd9  lea     rdx, [rsp+2B0h+phHash+8]; pbOutput
0x180026dde  xor     r9d, r9d; dwFlags
0x180026de1  lea     r8d, [r9+10h]; cbOutput
0x180026de5  call    cs:__imp_BCryptFinishHash
0x180026deb  test    eax, eax
0x180026ded  jns     short loc_180026DF6
0x180026def  mov     ecx, 7
0x180026df4  int     29h; Win8: RtlFailFast(ecx)
0x180026df6  mov     rcx, [rsp+2B0h+phHash]; hHash
0x180026dfb  call    cs:__imp_BCryptDestroyHash
0x180026e01  jmp     short loc_180026D93
```
