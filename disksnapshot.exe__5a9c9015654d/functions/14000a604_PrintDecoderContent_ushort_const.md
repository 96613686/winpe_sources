# PrintDecoderContent(ushort const *)

- ea: `0x14000a604`
- end: `0x14000a84d`
- name: `?PrintDecoderContent@@YAJPEBG@Z`
- size: `585`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140009ee0`

## callees

- `0x140001c50`
- `0x1400027d2`
- `0x140002870`
- `0x140002c84`
- `0x140002fb8`
- `0x140009d0c`
- `0x140009d24`
- `0x14000a604`
- `0x14000b7dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a734`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a734`
- `CRYPT32!CryptBinaryToStringW` at `0x14000a7ab`
- `CRYPT32!CryptBinaryToStringW` at `0x14000a7ab`
- `CRYPTSP!CryptDestroyHash` at `0x14000a7c5`
- `CRYPTSP!CryptDestroyHash` at `0x14000a7c5`
- `CRYPTSP!CryptGetHashParam` at `0x14000a77c`
- `CRYPTSP!CryptGetHashParam` at `0x14000a77c`
- `CRYPTSP!CryptHashData` at `0x14000a757`
- `CRYPTSP!CryptHashData` at `0x14000a757`
- `CRYPTSP!CryptCreateHash` at `0x14000a72a`
- `CRYPTSP!CryptCreateHash` at `0x14000a72a`

## pseudocode

```c
__int64 __fastcall PrintDecoderContent(wchar_t *a1)
{
  int v1; // ebx
  unsigned __int64 v2; // rdi
  __int64 v3; // rax
  __int64 v4; // rsi
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // rax
  __int128 *p_Src; // rax
  int v8; // edi
  const BYTE *v9; // rbx
  signed int LastError; // eax
  BYTE **v11; // rdx
  DWORD pcchString; // [rsp+30h] [rbp-D0h] BYREF
  HCRYPTHASH hHash; // [rsp+38h] [rbp-C8h] BYREF
  DWORD pdwDataLen; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *pbData[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v17; // [rsp+58h] [rbp-A8h]
  __int128 Src; // [rsp+68h] [rbp-98h] BYREF
  __m128i si128; // [rsp+78h] [rbp-88h]
  BYTE pbBinary[40]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR pszString[264]; // [rsp+B0h] [rbp-50h] BYREF

  Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src) = 0;
  v1 = LoadTextFile(a1, &Src);
  if ( v1 >= 0 )
  {
    v2 = 0;
    do
    {
      v3 = std::wstring::find(&Src, (__int64)L"\n", v2);
      v4 = v3;
      if ( v3 == -1 )
        break;
      *(_OWORD *)pbData = 0;
      v17 = 0;
      if ( si128.m128i_i64[0] < v2 )
        std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
      v5 = si128.m128i_i64[0] - v2;
      v6 = v3 - v2;
      if ( si128.m128i_i64[0] - v2 >= v6 )
        v5 = v6;
      p_Src = &Src;
      if ( si128.m128i_i64[1] > 7uLL )
        p_Src = (__int128 *)Src;
      std::wstring::_Construct<1,unsigned short const *>(pbData, (char *)p_Src + 2 * v2, v5);
      memset_0(pszString, 0, 0x208u);
      v8 = v17;
      v9 = (const BYTE *)pbData;
      if ( *((_QWORD *)&v17 + 1) > 7u )
        v9 = pbData[0];
      hHash = 0;
      pdwDataLen = 32;
      if ( CryptCreateHash(hProv, 0x800Cu, 0, 0, &hHash)
        && CryptHashData(hHash, v9, 2 * v8, 0)
        && CryptGetHashParam(hHash, 2u, pbBinary, &pdwDataLen, 0)
        && (pcchString = 260, CryptBinaryToStringW(pbBinary, 0x20u, 0x40000001u, pszString, &pcchString)) )
      {
        v1 = 0;
      }
      else
      {
        LastError = GetLastError();
        v1 = LastError;
        if ( LastError > 0 )
          v1 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( hHash )
        CryptDestroyHash(hHash);
      if ( v1 < 0 )
      {
        std::wstring::~wstring((char **)pbData);
        break;
      }
      v11 = pbData;
      if ( *((_QWORD *)&v17 + 1) > 7u )
        v11 = (BYTE **)pbData[0];
      wprintf(L"%s|%s\n", v11, pszString);
      v2 = v4 + 1;
      std::wstring::~wstring((char **)pbData);
    }
    while ( v4 != -2 );
  }
  std::wstring::~wstring((char **)&Src);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14000a604  mov     [rsp-8+arg_8], rbx
0x14000a609  mov     [rsp-8+arg_10], rsi
0x14000a60e  push    rbp
0x14000a60f  push    rdi
0x14000a610  push    r15
0x14000a612  lea     rbp, [rsp-1D0h]
0x14000a61a  sub     rsp, 2D0h
0x14000a621  mov     rax, cs:__security_cookie
0x14000a628  xor     rax, rsp
0x14000a62b  mov     [rbp+1E0h+var_20], rax
0x14000a632  xorps   xmm0, xmm0
0x14000a635  movups  [rsp+2E0h+Src], xmm0
0x14000a63a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14000a642  movdqu  [rsp+2E0h+var_268], xmm1
0x14000a648  xor     eax, eax
0x14000a64a  mov     word ptr [rsp+2E0h+Src], ax
0x14000a64f  lea     rdx, [rsp+2E0h+Src]; Src
0x14000a654  call    ?LoadTextFile@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LoadTextFile(ushort const *,std::wstring &)
0x14000a659  mov     ebx, eax
0x14000a65b  test    eax, eax
0x14000a65d  js      loc_14000A808
0x14000a663  xor     edi, edi
0x14000a665  mov     r15d, 80070000h
0x14000a66b  mov     r8, rdi
0x14000a66e  lea     rdx, asc_14000EE8C; "\n"
0x14000a675  lea     rcx, [rsp+2E0h+Src]
0x14000a67a  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x14000a67f  mov     rsi, rax
0x14000a682  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000a686  jz      loc_14000A808
0x14000a68c  xorps   xmm0, xmm0
0x14000a68f  movups  xmmword ptr [rsp+2E0h+pbData], xmm0
0x14000a694  xorps   xmm1, xmm1
0x14000a697  movdqu  [rsp+2E0h+var_288], xmm1
0x14000a69d  mov     r8, qword ptr [rsp+2E0h+var_268]
0x14000a6a2  cmp     r8, rdi
0x14000a6a5  jb      loc_14000A847
0x14000a6ab  sub     r8, rdi
0x14000a6ae  sub     rax, rdi
0x14000a6b1  cmp     r8, rax
0x14000a6b4  cmovnb  r8, rax
0x14000a6b8  lea     rax, [rsp+2E0h+Src]
0x14000a6bd  cmp     qword ptr [rbp+1E0h+var_268+8], 7
0x14000a6c2  cmova   rax, qword ptr [rsp+2E0h+Src]
0x14000a6c8  lea     rdx, [rax+rdi*2]
0x14000a6cc  lea     rcx, [rsp+2E0h+pbData]
0x14000a6d1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000a6d6  xor     edx, edx; Val
0x14000a6d8  mov     r8d, 208h; Size
0x14000a6de  lea     rcx, [rbp+1E0h+pszString]; void *
0x14000a6e2  call    memset_0
0x14000a6e7  mov     rdi, qword ptr [rsp+2E0h+var_288]
0x14000a6ec  lea     rbx, [rsp+2E0h+pbData]
0x14000a6f1  cmp     qword ptr [rsp+2E0h+var_288+8], 7
0x14000a6f7  cmova   rbx, [rsp+2E0h+pbData]
0x14000a6fd  mov     [rsp+2E0h+hHash], 0
0x14000a706  mov     [rsp+2E0h+pdwDataLen], 20h ; ' '
0x14000a70e  lea     rax, [rsp+2E0h+hHash]
0x14000a713  mov     [rsp+2E0h+phHash], rax; phHash
0x14000a718  xor     r9d, r9d; dwFlags
0x14000a71b  xor     r8d, r8d; hKey
0x14000a71e  mov     edx, 800Ch; Algid
0x14000a723  mov     rcx, cs:hProv; hProv
0x14000a72a  call    cs:__imp_CryptCreateHash
0x14000a730  test    eax, eax
0x14000a732  jnz     short loc_14000A748
0x14000a734  call    cs:__imp_GetLastError
0x14000a73a  mov     ebx, eax
0x14000a73c  test    eax, eax
0x14000a73e  jle     short loc_14000A7BB
0x14000a740  movzx   ebx, ax
0x14000a743  or      ebx, r15d
0x14000a746  jmp     short loc_14000A7BB
0x14000a748  lea     r8d, [rdi+rdi]; dwDataLen
0x14000a74c  xor     r9d, r9d; dwFlags
0x14000a74f  mov     rdx, rbx; pbData
0x14000a752  mov     rcx, [rsp+2E0h+hHash]; hHash
0x14000a757  call    cs:__imp_CryptHashData
0x14000a75d  test    eax, eax
0x14000a75f  jz      short loc_14000A734
0x14000a761  mov     dword ptr [rsp+2E0h+phHash], 0; dwFlags
0x14000a769  lea     r9, [rsp+2E0h+pdwDataLen]; pdwDataLen
0x14000a76e  lea     r8, [rbp+1E0h+pbBinary]; pbData
0x14000a772  mov     edx, 2; dwParam
0x14000a777  mov     rcx, [rsp+2E0h+hHash]; hHash
0x14000a77c  call    cs:__imp_CryptGetHashParam
0x14000a782  test    eax, eax
0x14000a784  jz      short loc_14000A734
0x14000a786  mov     [rsp+2E0h+pcchString], 104h
0x14000a78e  lea     rax, [rsp+2E0h+pcchString]
0x14000a793  mov     [rsp+2E0h+phHash], rax; pcchString
0x14000a798  lea     r9, [rbp+1E0h+pszString]; pszString
0x14000a79c  mov     edx, 20h ; ' '; cbBinary
0x14000a7a1  mov     r8d, 40000001h; dwFlags
0x14000a7a7  lea     rcx, [rbp+1E0h+pbBinary]; pbBinary
0x14000a7ab  call    cs:__imp_CryptBinaryToStringW
0x14000a7b1  test    eax, eax
0x14000a7b3  jz      loc_14000A734
0x14000a7b9  xor     ebx, ebx
0x14000a7bb  mov     rcx, [rsp+2E0h+hHash]; hHash
0x14000a7c0  test    rcx, rcx
0x14000a7c3  jz      short loc_14000A7CB
0x14000a7c5  call    cs:__imp_CryptDestroyHash
0x14000a7cb  test    ebx, ebx
0x14000a7cd  js      short loc_14000A83B
0x14000a7cf  lea     rdx, [rsp+2E0h+pbData]
0x14000a7d4  cmp     qword ptr [rsp+2E0h+var_288+8], 7
0x14000a7da  cmova   rdx, [rsp+2E0h+pbData]
0x14000a7e0  lea     r8, [rbp+1E0h+pszString]
0x14000a7e4  lea     rcx, aSS_0; "%s|%s\n"
0x14000a7eb  call    wprintf
0x14000a7f0  lea     rdi, [rsi+1]
0x14000a7f4  lea     rcx, [rsp+2E0h+pbData]
0x14000a7f9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000a7fe  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14000a802  jnz     loc_14000A66B
0x14000a808  lea     rcx, [rsp+2E0h+Src]
0x14000a80d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000a812  mov     eax, ebx
0x14000a814  mov     rcx, [rbp+1E0h+var_20]
0x14000a81b  xor     rcx, rsp; StackCookie
0x14000a81e  call    __security_check_cookie
0x14000a823  lea     r11, [rsp+2E0h+var_10]
0x14000a82b  mov     rbx, [r11+28h]
0x14000a82f  mov     rsi, [r11+30h]
0x14000a833  mov     rsp, r11
0x14000a836  pop     r15
0x14000a838  pop     rdi
0x14000a839  pop     rbp
0x14000a83a  retn
0x14000a83b  lea     rcx, [rsp+2E0h+pbData]
0x14000a840  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000a845  jmp     short loc_14000A808
0x14000a847  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
