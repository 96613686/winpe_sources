# CCertConfigPrivate::GetField(ushort * const,ushort * *)

- ea: `0x18000b300`
- end: `0x18000b7d1`
- name: `?GetField@CCertConfigPrivate@@QEAAJQEAGPEAPEAG@Z`
- size: `1233`
- prototype: `__int64 __fastcall(CCertConfigPrivate *__hidden this, PCNZWCH lpString1, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a100`
- `0x18000ab44`

## callees

- `0x180002306`
- `0x18000b300`
- `0x18000ba10`
- `0x18000c15c`
- `0x18001f260`
- `0x1800200c0`
- `0x18002067c`
- `0x180039740`

## import_xrefs

- `msvcrt!wcschr` at `0x18000b5db`
- `msvcrt!wcschr` at `0x18000b66e`
- `msvcrt!wcschr` at `0x18000b5db`
- `msvcrt!wcschr` at `0x18000b66e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b610`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b610`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b771`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b7a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b771`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b7a4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b35f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b35f`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000b34b`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000b34b`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000b383`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000b72b`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000b763`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000b796`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000b383`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000b72b`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000b763`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000b796`
- `certca!__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z` at `0x18000b703`
- `certca!__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z` at `0x18000b703`

## string_xrefs

- `0x18000b3c7`: `CommonName`
- `0x18000b515`: `Config`
- `0x18000b59e`: `Comment`

## pseudocode

```c
__int64 __fastcall CCertConfigPrivate::GetField(CCertConfigPrivate *this, WCHAR *lpString1, unsigned __int16 **a3)
{
  unsigned __int16 *v6; // r12
  unsigned int v7; // edi
  unsigned int Table; // eax
  int v9; // edx
  unsigned int v10; // ecx
  __int64 v11; // rax
  __int64 v12; // rbx
  unsigned __int16 *v13; // r15
  int v14; // ebp
  __int64 v15; // rsi
  unsigned __int16 *v16; // rax
  wchar_t *v17; // rax
  __int64 v18; // rax
  size_t v19; // rdi
  unsigned __int16 *v20; // rax
  wchar_t *v21; // rax
  unsigned int v22; // eax
  unsigned __int16 *v24; // [rsp+20h] [rbp-68h] BYREF
  unsigned __int16 v25[12]; // [rsp+28h] [rbp-60h] BYREF

  v24 = 0;
  v6 = 0;
  if ( a3 && lpString1 && SysStringByteLen(lpString1) )
  {
    v7 = 0;
    SysFreeString(*a3);
    *a3 = 0;
    if ( !*(_QWORD *)this )
    {
      Table = CCertConfigPrivate::_LoadTable(this);
      v7 = Table;
      if ( Table )
      {
        v9 = Table;
        v10 = 96010945;
LABEL_7:
        CSPrintErrorLineFile(v10, v9);
        return v7;
      }
    }
    v11 = *((unsigned int *)this + 2);
    if ( (_DWORD)v11 == -1 )
    {
      *((_DWORD *)this + 2) = 0;
      v11 = 0;
    }
    else if ( (int)v11 < 0 )
    {
      goto LABEL_69;
    }
    if ( (int)v11 < *((_DWORD *)this + 3) )
    {
      v12 = *(_QWORD *)this;
      if ( !v12 )
      {
        v7 = -2147418113;
        v10 = 96993985;
        v9 = -2147418113;
        goto LABEL_7;
      }
      v13 = 0;
      v14 = 1;
      v15 = 104 * v11;
      if ( !(unsigned int)mylstrcmpNLSub(lpString1, L"CommonName", -1, 1u) )
      {
        v16 = *(unsigned __int16 **)(v15 + v12);
        goto LABEL_59;
      }
      if ( (unsigned int)mylstrcmpNLSub(lpString1, L"SanitizedName", -1, 1u) )
      {
        if ( !(unsigned int)mylstrcmpNLSub(lpString1, L"ShortName", -1, 1u) )
        {
          v16 = *(unsigned __int16 **)(v15 + v12 + 8);
          goto LABEL_59;
        }
        if ( (unsigned int)mylstrcmpNLSub(lpString1, L"SanitizedShortName", -1, 1u) )
        {
          if ( !(unsigned int)mylstrcmpNLSub(lpString1, L"OrgUnit", -1, 1u) )
          {
            v16 = *(unsigned __int16 **)(v15 + v12 + 16);
            goto LABEL_59;
          }
          if ( !(unsigned int)mylstrcmpNLSub(lpString1, L"Organization", -1, 1u) )
          {
            v16 = *(unsigned __int16 **)(v15 + v12 + 24);
            goto LABEL_59;
          }
          if ( !(unsigned int)mylstrcmpNLSub(lpString1, L"Locality", -1, 1u) )
          {
            v16 = *(unsigned __int16 **)(v15 + v12 + 32);
            goto LABEL_59;
          }
          if ( !(unsigned int)mylstrcmpNLSub(lpString1, L"State", -1, 1u) )
          {
            v16 = *(unsigned __int16 **)(v15 + v12 + 40);
            goto LABEL_59;
          }
          if ( !(unsigned int)mylstrcmpNLSub(lpString1, L"Country", -1, 1u) )
          {
            v16 = *(unsigned __int16 **)(v15 + v12 + 48);
            goto LABEL_59;
          }
          if ( !(unsigned int)mylstrcmpNLSub(lpString1, L"Config", -1, 1u) )
          {
            v16 = *(unsigned __int16 **)(v15 + v12 + 56);
            goto LABEL_59;
          }
          if ( (unsigned int)mylstrcmpNLSub(lpString1, L"ExchangeCertificate", -1, 1u) )
          {
            if ( (unsigned int)mylstrcmpNLSub(lpString1, L"SignatureCertificate", -1, 1u) )
            {
              if ( (unsigned int)mylstrcmpNLSub(lpString1, L"Description", -1, 1u)
                && (unsigned int)mylstrcmpNLSub(lpString1, L"Comment", -1, 1u) )
              {
                if ( !(unsigned int)mylstrcmpNLSub(lpString1, L"Server", -1, 1u) )
                {
                  v17 = wcschr(*(const wchar_t **)(v15 + v12 + 56), 0x5Cu);
                  if ( v17 )
                  {
                    v18 = (unsigned int)(((unsigned __int64)v17 - *(_QWORD *)(v15 + v12 + 56)) >> 1);
                  }
                  else
                  {
                    v18 = -1;
                    do
                      ++v18;
                    while ( *(_WORD *)(*(_QWORD *)(v15 + v12 + 56) + 2 * v18) );
                  }
                  v19 = v18;
                  v20 = (unsigned __int16 *)LocalAlloc(0, 2 * v18 + 2);
                  v13 = v20;
                  if ( !v20 )
                  {
                    v9 = -2147024882;
                    v10 = 102892225;
                    v7 = -2147024882;
                    goto LABEL_7;
                  }
                  memcpy_0(v20, *(const void **)(v15 + v12 + 56), v19 * 2);
                  v16 = v13;
                  v13[v19] = 0;
                  goto LABEL_62;
                }
                if ( (unsigned int)mylstrcmpNLSub(lpString1, L"Authority", -1, 1u) )
                {
                  if ( !(unsigned int)mylstrcmpNLSub(lpString1, L"Flags", -1, 1u) )
                  {
                    StringCchPrintfW(v25, 0xCu, L"%u", *(unsigned int *)(v15 + v12 + 88));
                    v16 = v25;
                    goto LABEL_62;
                  }
                  v14 = 0;
                  if ( (unsigned int)mylstrcmpNLSub(lpString1, L"WebEnrollmentServers", -1, 1u) )
                  {
LABEL_60:
                    v7 = -2146877436;
                    CSPrintErrorLineFile2(0x64602C1u, -2146877436, -2146877436);
                    goto LABEL_67;
                  }
                  v16 = *(unsigned __int16 **)(v15 + v12 + 96);
                }
                else
                {
                  v21 = wcschr(*(const wchar_t **)(v15 + v12 + 56), 0x5Cu);
                  if ( !v21 )
                  {
                    v16 = (unsigned __int16 *)&psz;
                    goto LABEL_62;
                  }
                  v16 = v21 + 1;
                }
              }
              else
              {
                v16 = *(unsigned __int16 **)(v15 + v12 + 80);
              }
LABEL_59:
              if ( !v16 )
                goto LABEL_60;
              if ( !v14 )
              {
LABEL_65:
                if ( !myConvertWszToBstr(a3, v16, -1) )
                {
                  v7 = -2147024882;
                  CSPrintErrorLineFile(0x65402C1u, -2147024882);
                }
                goto LABEL_67;
              }
LABEL_62:
              v22 = myRevertSanitizeName(v16, &v24);
              v7 = v22;
              if ( v22 )
              {
                CSPrintErrorLineFile(0x64C02C1u, v22);
                v6 = v24;
LABEL_67:
                if ( v13 )
                  LocalFree(v13);
                goto LABEL_71;
              }
              v6 = v24;
              v16 = v24;
              goto LABEL_65;
            }
            v16 = *(unsigned __int16 **)(v15 + v12 + 72);
          }
          else
          {
            v16 = *(unsigned __int16 **)(v15 + v12 + 64);
          }
        }
        else
        {
          v16 = *(unsigned __int16 **)(v15 + v12 + 8);
        }
      }
      else
      {
        v16 = *(unsigned __int16 **)(v15 + v12);
      }
      v14 = 0;
      goto LABEL_59;
    }
LABEL_69:
    v7 = -2147024809;
    v10 = 96666305;
    v9 = -2147024809;
    goto LABEL_7;
  }
  v7 = -2147467261;
  CSPrintErrorLineFile(0x5B102C1u, -2147467261);
LABEL_71:
  if ( v6 )
    LocalFree(v6);
  return v7;
}

```

## disassembly

```asm
0x18000b300  mov     [rsp+arg_18], rbx
0x18000b305  push    rbp
0x18000b306  push    rsi
0x18000b307  push    rdi
0x18000b308  push    r12
0x18000b30a  push    r13
0x18000b30c  push    r14
0x18000b30e  push    r15
0x18000b310  sub     rsp, 50h
0x18000b314  mov     rax, cs:__security_cookie
0x18000b31b  xor     rax, rsp
0x18000b31e  mov     [rsp+88h+var_48], rax
0x18000b323  xor     ebp, ebp
0x18000b325  mov     r13, r8
0x18000b328  mov     [rsp+88h+var_68], rbp
0x18000b32d  mov     r14, rdx
0x18000b330  mov     rbx, rcx
0x18000b333  mov     r12d, ebp
0x18000b336  test    r8, r8
0x18000b339  jz      loc_18000B78A
0x18000b33f  test    rdx, rdx
0x18000b342  jz      loc_18000B78A
0x18000b348  mov     rcx, rdx; bstr
0x18000b34b  call    cs:__imp_SysStringByteLen
0x18000b351  test    eax, eax
0x18000b353  jz      loc_18000B78A
0x18000b359  mov     rcx, [r13+0]; bstrString
0x18000b35d  mov     edi, ebp
0x18000b35f  call    cs:__imp_SysFreeString
0x18000b365  mov     [r13+0], rbp
0x18000b369  cmp     [rbx], rbp
0x18000b36c  jnz     short loc_18000B38E
0x18000b36e  mov     rcx, rbx; this
0x18000b371  call    ?_LoadTable@CCertConfigPrivate@@AEAAJXZ; CCertConfigPrivate::_LoadTable(void)
0x18000b376  mov     edi, eax
0x18000b378  test    eax, eax
0x18000b37a  jz      short loc_18000B38E
0x18000b37c  mov     edx, eax
0x18000b37e  mov     ecx, 5B902C1h
0x18000b383  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000b389  jmp     loc_18000B7AA
0x18000b38e  mov     eax, [rbx+8]
0x18000b391  cmp     eax, 0FFFFFFFFh
0x18000b394  jnz     short loc_18000B39D
0x18000b396  mov     [rbx+8], ebp
0x18000b399  mov     eax, ebp
0x18000b39b  jmp     short loc_18000B3A5
0x18000b39d  test    eax, eax
0x18000b39f  js      loc_18000B779
0x18000b3a5  cmp     eax, [rbx+0Ch]
0x18000b3a8  jge     loc_18000B779
0x18000b3ae  mov     rbx, [rbx]
0x18000b3b1  test    rbx, rbx
0x18000b3b4  jnz     short loc_18000B3C4
0x18000b3b6  mov     edi, 8000FFFFh
0x18000b3bb  mov     ecx, 5C802C1h
0x18000b3c0  mov     edx, edi
0x18000b3c2  jmp     short loc_18000B383
0x18000b3c4  mov     r15, rbp
0x18000b3c7  lea     rdx, aCommonname; "CommonName"
0x18000b3ce  mov     ebp, 1
0x18000b3d3  or      r8d, 0FFFFFFFFh; int
0x18000b3d7  mov     r9b, bpl; bool
0x18000b3da  mov     rcx, r14; lpString1
0x18000b3dd  imul    rsi, rax, 68h ; 'h'
0x18000b3e1  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18000b3e6  test    eax, eax
0x18000b3e8  jnz     short loc_18000B3F3
0x18000b3ea  mov     rax, [rsi+rbx]
0x18000b3ee  jmp     loc_18000B6ED
0x18000b3f3  mov     r9b, bpl; bool
0x18000b3f6  lea     rdx, aSanitizedname; "SanitizedName"
0x18000b3fd  or      r8d, 0FFFFFFFFh; int
0x18000b401  mov     rcx, r14; lpString1
0x18000b404  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18000b409  test    eax, eax
0x18000b40b  jnz     short loc_18000B416
0x18000b40d  mov     rax, [rsi+rbx]
0x18000b411  jmp     loc_18000B576
0x18000b416  mov     r9b, bpl; bool
0x18000b419  lea     rdx, aShortname; "ShortName"
0x18000b420  or      r8d, 0FFFFFFFFh; int
0x18000b424  mov     rcx, r14; lpString1
0x18000b427  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18000b42c  test    eax, eax
0x18000b42e  jnz     short loc_18000B43A
0x18000b430  mov     rax, [rsi+rbx+8]
0x18000b435  jmp     loc_18000B6ED
0x18000b43a  mov     r9b, bpl; bool
0x18000b43d  lea     rdx, aSanitizedshort; "SanitizedShortName"
0x18000b444  or      r8d, 0FFFFFFFFh; int
0x18000b448  mov     rcx, r14; lpString1
0x18000b44b  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18000b450  test    eax, eax
0x18000b452  jnz     short loc_18000B45E
0x18000b454  mov     rax, [rsi+rbx+8]
0x18000b459  jmp     loc_18000B576
0x18000b45e  mov     r9b, bpl; bool
0x18000b461  lea     rdx, aOrgunit; "OrgUnit"
0x18000b468  or      r8d, 0FFFFFFFFh; int
0x18000b46c  mov     rcx, r14; lpString1
0x18000b46f  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18000b474  test    eax, eax
0x18000b476  jnz     short loc_18000B482
0x18000b478  mov     rax, [rsi+rbx+10h]
0x18000b47d  jmp     loc_18000B6ED
0x18000b482  mov     r9b, bpl; bool
0x18000b485  lea     rdx, aOrganization; "Organization"
0x18000b48c  or      r8d, 0FFFFFFFFh; int
0x18000b490  mov     rcx, r14; lpString1
0x18000b493  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18000b498  test    eax, eax
0x18000b49a  jnz     short loc_18000B4A6
0x18000b49c  mov     rax, [rsi+rbx+18h]
0x18000b4a1  jmp     loc_18000B6ED
0x18000b4a6  mov     r9b, bpl; bool
0x18000b4a9  lea     rdx, aLocality; "Locality"
0x18000b4b0  or      r8d, 0FFFFFFFFh; int
0x18000b4b4  mov     rcx, r14; lpString1
0x18000b4b7  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18000b4bc  test    eax, eax
0x18000b4be  jnz     short loc_18000B4CA
0x18000b4c0  mov     rax, [rsi+rbx+20h]
0x18000b4c5  jmp     loc_18000B6ED
0x18000b4ca  mov     r9b, bpl; bool
0x18000b4cd  lea     rdx, aState; "State"
0x18000b4d4  or      r8d, 0FFFFFFFFh; int
0x18000b4d8  mov     rcx, r14; lpString1
0x18000b4db  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18000b4e0  test    eax, eax
0x18000b4e2  jnz     short loc_18000B4EE
0x18000b4e4  mov     rax, [rsi+rbx+28h]
0x18000b4e9  jmp     loc_18000B6ED
0x18000b4ee  mov     r9b, bpl; bool
0x18000b4f1  lea     rdx, aCountry; "Country"
0x18000b4f8  or      r8d, 0FFFFFFFFh; int
0x18000b4fc  mov     rcx, r14; lpString1
0x18000b4ff  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18000b504  test    eax, eax
0x18000b506  jnz     short loc_18000B512
0x18000b508  mov     rax, [rsi+rbx+30h]
0x18000b50d  jmp     loc_18000B6ED
0x18000b512  mov     r9b, bpl; bool
0x18000b515  lea     rdx, aConfig; "Config"
0x18000b51c  or      r8d, 0FFFFFFFFh; int
0x18000b520  mov     rcx, r14; lpString1
0x18000b523  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18000b528  test    eax, eax
0x18000b52a  jnz     short loc_18000B536
0x18000b52c  mov     rax, [rsi+rbx+38h]
0x18000b531  jmp     loc_18000B6ED
0x18000b536  mov     r9b, bpl; bool
0x18000b539  lea     rdx, aExchangecertif; "ExchangeCertificate"
0x18000b540  or      r8d, 0FFFFFFFFh; int
0x18000b544  mov     rcx, r14; lpString1
0x18000b547  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18000b54c  test    eax, eax
0x18000b54e  jnz     short loc_18000B557
0x18000b550  mov     rax, [rsi+rbx+40h]
0x18000b555  jmp     short loc_18000B576
0x18000b557  mov     r9b, bpl; bool
0x18000b55a  lea     rdx, aSignaturecerti; "SignatureCertificate"
0x18000b561  or      r8d, 0FFFFFFFFh; int
0x18000b565  mov     rcx, r14; lpString1
0x18000b568  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18000b56d  test    eax, eax
0x18000b56f  jnz     short loc_18000B57D
0x18000b571  mov     rax, [rsi+rbx+48h]
0x18000b576  xor     ebp, ebp
0x18000b578  jmp     loc_18000B6ED
0x18000b57d  mov     r9b, bpl; bool
0x18000b580  lea     rdx, aDescription; "Description"
0x18000b587  or      r8d, 0FFFFFFFFh; int
0x18000b58b  mov     rcx, r14; lpString1
0x18000b58e  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18000b593  test    eax, eax
0x18000b595  jz      loc_18000B6E8
0x18000b59b  mov     r9b, bpl; bool
0x18000b59e  lea     rdx, aComment; "Comment"
0x18000b5a5  or      r8d, 0FFFFFFFFh; int
0x18000b5a9  mov     rcx, r14; lpString1
0x18000b5ac  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18000b5b1  test    eax, eax
0x18000b5b3  jz      loc_18000B6E8
0x18000b5b9  mov     r9b, bpl; bool
0x18000b5bc  lea     rdx, aServer; "Server"
0x18000b5c3  or      r8d, 0FFFFFFFFh; int
0x18000b5c7  mov     rcx, r14; lpString1
0x18000b5ca  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18000b5cf  test    eax, eax
0x18000b5d1  jnz     short loc_18000B64C
0x18000b5d3  mov     rcx, [rsi+rbx+38h]; Str
0x18000b5d8  lea     edx, [rax+5Ch]; Ch
0x18000b5db  call    cs:__imp_wcschr
0x18000b5e1  xor     ebp, ebp
0x18000b5e3  test    rax, rax
0x18000b5e6  jnz     short loc_18000B5FC
0x18000b5e8  mov     rcx, [rsi+rbx+38h]
0x18000b5ed  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b5f1  inc     rax
0x18000b5f4  cmp     [rcx+rax*2], bp
0x18000b5f8  jnz     short loc_18000B5F1
0x18000b5fa  jmp     short loc_18000B606
0x18000b5fc  sub     rax, [rsi+rbx+38h]
0x18000b601  shr     rax, 1
0x18000b604  mov     eax, eax
0x18000b606  lea     rdi, [rax+rax]
0x18000b60a  xor     ecx, ecx; uFlags
0x18000b60c  lea     rdx, [rdi+2]; uBytes
0x18000b610  call    cs:__imp_LocalAlloc
0x18000b616  mov     r15, rax
0x18000b619  test    rax, rax
0x18000b61c  jnz     short loc_18000B62F
0x18000b61e  mov     edx, 8007000Eh
0x18000b623  mov     ecx, 62202C1h
0x18000b628  mov     edi, edx
0x18000b62a  jmp     loc_18000B383
0x18000b62f  mov     rdx, [rsi+rbx+38h]; Src
0x18000b634  mov     r8, rdi; Size
0x18000b637  mov     rcx, r15; void *
0x18000b63a  call    memcpy_0
0x18000b63f  mov     rax, r15
0x18000b642  mov     [rdi+r15], bp
0x18000b647  jmp     loc_18000B711
0x18000b64c  mov     r9b, bpl; bool
0x18000b64f  lea     rdx, aAuthority; "Authority"
0x18000b656  or      r8d, 0FFFFFFFFh; int
0x18000b65a  mov     rcx, r14; lpString1
0x18000b65d  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18000b662  test    eax, eax
0x18000b664  jnz     short loc_18000B68B
0x18000b666  mov     rcx, [rsi+rbx+38h]; Str
0x18000b66b  lea     edx, [rax+5Ch]; Ch
0x18000b66e  call    cs:__imp_wcschr
0x18000b674  test    rax, rax
0x18000b677  jnz     short loc_18000B685
0x18000b679  lea     rax, psz
0x18000b680  jmp     loc_18000B70F
0x18000b685  add     rax, 2
0x18000b689  jmp     short loc_18000B6ED
0x18000b68b  mov     r9b, bpl; bool
0x18000b68e  lea     rdx, aFlags; "Flags"
0x18000b695  or      r8d, 0FFFFFFFFh; int
0x18000b699  mov     rcx, r14; lpString1
0x18000b69c  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18000b6a1  test    eax, eax
0x18000b6a3  jnz     short loc_18000B6C5
0x18000b6a5  mov     r9d, [rsi+rbx+58h]
0x18000b6aa  lea     r8, aU; "%u"
0x18000b6b1  lea     edx, [rax+0Ch]; unsigned __int64
0x18000b6b4  lea     rcx, [rsp+88h+var_60]; unsigned __int16 *
0x18000b6b9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b6be  lea     rax, [rsp+88h+var_60]
0x18000b6c3  jmp     short loc_18000B70F
0x18000b6c5  mov     r9b, bpl; bool
0x18000b6c8  lea     rdx, aWebenrollments; "WebEnrollmentServers"
0x18000b6cf  or      r8d, 0FFFFFFFFh; int
0x18000b6d3  mov     rcx, r14; lpString1
0x18000b6d6  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18000b6db  xor     ebp, ebp
0x18000b6dd  test    eax, eax
0x18000b6df  jnz     short loc_18000B6F4
0x18000b6e1  mov     rax, [rsi+rbx+60h]
0x18000b6e6  jmp     short loc_18000B6ED
0x18000b6e8  mov     rax, [rsi+rbx+50h]
0x18000b6ed  test    rax, rax
0x18000b6f0  jnz     short loc_18000B70B
0x18000b6f2  xor     ebp, ebp
0x18000b6f4  mov     edi, 80094004h
0x18000b6f9  mov     ecx, 64602C1h
0x18000b6fe  mov     r8d, edi
0x18000b701  mov     edx, edi
0x18000b703  call    cs:__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z; CSPrintErrorLineFile2(ulong,long,long)
0x18000b709  jmp     short loc_18000B769
0x18000b70b  test    ebp, ebp
0x18000b70d  jz      short loc_18000B742
0x18000b70f  xor     ebp, ebp
0x18000b711  lea     rdx, [rsp+88h+var_68]; unsigned __int16 **
0x18000b716  mov     rcx, rax; unsigned __int16 *
0x18000b719  call    ?myRevertSanitizeName@@YAJPEBGPEAPEAG@Z; myRevertSanitizeName(ushort const *,ushort * *)
0x18000b71e  mov     edi, eax
0x18000b720  test    eax, eax
0x18000b722  jz      short loc_18000B738
0x18000b724  mov     edx, eax
0x18000b726  mov     ecx, 64C02C1h
0x18000b72b  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000b731  mov     r12, [rsp+88h+var_68]
0x18000b736  jmp     short loc_18000B769
0x18000b738  mov     r12, [rsp+88h+var_68]
0x18000b73d  mov     rax, r12
0x18000b740  jmp     short loc_18000B744
0x18000b742  xor     ebp, ebp
0x18000b744  or      r8d, 0FFFFFFFFh; int
0x18000b748  mov     rdx, rax; unsigned __int16 *
0x18000b74b  mov     rcx, r13; unsigned __int16 **
0x18000b74e  call    ?myConvertWszToBstr@@YAHPEAPEAGPEBGJ@Z; myConvertWszToBstr(ushort * *,ushort const *,long)
0x18000b753  test    eax, eax
0x18000b755  jnz     short loc_18000B769
0x18000b757  mov     edx, 8007000Eh
0x18000b75c  mov     ecx, 65402C1h
  ... truncated ...
```
