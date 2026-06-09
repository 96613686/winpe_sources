# ScriptNameToDSName

- ea: `0x1800fbd7c`
- end: `0x1800fc35c`
- name: `ScriptNameToDSName`
- size: `1504`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180290c64`
- `0x1803911ac`
- `0x180392648`

## callees

- `0x180006330`
- `0x1800067d0`
- `0x18001e090`
- `0x18001ea60`
- `0x180021aa3`
- `0x18002f0f4`
- `0x1800f8e24`
- `0x1800f9b18`
- `0x1800f9c9c`
- `0x1800fb0bc`
- `0x1800fbd7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800fbe9f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800fbf6d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800fc03f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800fc064`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800fbe9f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800fbf6d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800fc03f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800fc064`
- `api-ms-win-crt-private-l1-1-0!_o_iswxdigit` at `0x1800fbfe9`
- `api-ms-win-crt-private-l1-1-0!_o_iswxdigit` at `0x1800fbffb`
- `api-ms-win-crt-private-l1-1-0!_o_iswxdigit` at `0x1800fc1d0`
- `api-ms-win-crt-private-l1-1-0!_o_iswxdigit` at `0x1800fc1e2`
- `api-ms-win-crt-private-l1-1-0!_o_iswxdigit` at `0x1800fbfe9`
- `api-ms-win-crt-private-l1-1-0!_o_iswxdigit` at `0x1800fbffb`
- `api-ms-win-crt-private-l1-1-0!_o_iswxdigit` at `0x1800fc1d0`
- `api-ms-win-crt-private-l1-1-0!_o_iswxdigit` at `0x1800fc1e2`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800fbfcc`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800fbfdb`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800fc1b3`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800fc1c2`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800fbfcc`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800fbfdb`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800fc1b3`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800fc1c2`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800fc013`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800fc1fa`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800fc013`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800fc1fa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800fbdb4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800fbdb4`
- `RPCRT4!UuidFromStringW` at `0x1800fbfa6`
- `RPCRT4!UuidFromStringW` at `0x1800fbfa6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800fc0c5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800fc0c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fc0ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fc14c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fc0ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fc14c`
- `ntdll!RtlValidSid` at `0x1800fc312`
- `ntdll!RtlValidSid` at `0x1800fc312`
- `ntdll!RtlLengthSid` at `0x1800fc0d8`
- `ntdll!RtlLengthSid` at `0x1800fc300`
- `ntdll!RtlLengthSid` at `0x1800fc0d8`
- `ntdll!RtlLengthSid` at `0x1800fc300`

## string_xrefs

- `0x1800fc05d`: `sid:S-`

## pseudocode

```c
__int64 __fastcall ScriptNameToDSName(const wchar_t *a1, unsigned int a2, _QWORD *a3)
{
  int v6; // eax
  int v7; // r15d
  int v8; // r13d
  int v9; // r8d
  __int64 v10; // rdx
  int v11; // ecx
  unsigned int v12; // edi
  void *v13; // rax
  int v14; // r13d
  int v15; // r13d
  const wchar_t *v16; // r8
  wchar_t *v17; // rax
  unsigned int k; // edx
  wchar_t v19; // cx
  __int64 j; // rbx
  wchar_t v21; // ax
  __int64 v22; // rcx
  bool v23; // cf
  void *v24; // rbx
  int v25; // r8d
  int v26; // r9d
  ULONG v27; // eax
  int v28; // r8d
  int v29; // r9d
  __int64 result; // rax
  unsigned int v31; // eax
  __int64 i; // rbx
  wchar_t v33; // ax
  __int64 v34; // rcx
  void *v35; // rcx
  LPVOID v36; // rdi
  unsigned int v37; // ebx
  int v38; // r8d
  int v39; // r9d
  unsigned int v40; // ebx
  STRSAFE_LPWSTR *v41; // [rsp+20h] [rbp-B9h]
  size_t *v42; // [rsp+28h] [rbp-B1h]
  DWORD v43; // [rsp+30h] [rbp-A9h]
  PSID Sid; // [rsp+40h] [rbp-99h] BYREF
  size_t Size; // [rsp+48h] [rbp-91h]
  LPVOID Value; // [rsp+50h] [rbp-89h]
  wchar_t String; // [rsp+60h] [rbp-79h] BYREF
  unsigned __int16 v48; // [rsp+62h] [rbp-77h]
  UUID Uuid; // [rsp+68h] [rbp-71h] BYREF
  _BYTE Src[40]; // [rsp+78h] [rbp-61h] BYREF
  wchar_t pszDest[40]; // [rsp+A0h] [rbp-39h] BYREF

  Value = TlsGetValue(dwTSindex);
  v6 = 0;
  memset(Src, 0, 28);
  Uuid = 0;
  v7 = 1;
  if ( !a3 || !a1 )
    return 1;
  LODWORD(Size) = 0;
  v8 = 3;
  while ( a2 && !v6 )
  {
    if ( *a1 == 10 || *a1 == 13 || *a1 == 32 )
    {
      ++a1;
      --a2;
    }
    else
    {
      v6 = 1;
    }
  }
  v9 = 0;
  while ( a2 && !v9 )
  {
    v10 = a2 - 1;
    if ( a1[v10] == 10 || a1[v10] == 13 || a1[v10] == 32 )
    {
      if ( a2 > 1 && a1[a2 - 2] == 92 )
      {
        v11 = 1;
        if ( a2 > 2 )
        {
          do
          {
            if ( a1[a2 - v11 - 2] != 92 )
              break;
            ++v11;
          }
          while ( a2 > v11 + 1 );
        }
        v9 = 1;
        if ( (v11 & 1) != 0 )
          LODWORD(v10) = a2;
      }
      a2 = v10;
    }
    else
    {
      v9 = 1;
    }
  }
  if ( a2 > 3 && !(unsigned int)_o__wcsnicmp(a1, L"dn:", 3) )
  {
    a2 -= 3;
    a1 += 3;
    goto LABEL_29;
  }
  if ( a2 <= 5 )
  {
    if ( a2 <= 4 )
    {
      if ( a2 <= 2 )
        goto LABEL_29;
      goto LABEL_73;
    }
LABEL_50:
    if ( !(unsigned int)_o__wcsnicmp(a1, L"sid:", 4) )
    {
      v23 = a2 < 6;
      if ( a2 > 6 )
      {
        if ( (unsigned int)_o__wcsnicmp(a1, L"sid:S-", 6) )
        {
LABEL_64:
          if ( (a2 & 1) != 0 )
            return 1;
          v31 = (a2 - 4) >> 1;
          LODWORD(Size) = v31;
          if ( v31 > 0x1C )
            return 1;
          a1 += 4;
          for ( i = 0; (unsigned int)i < v31; i = (unsigned int)(i + 1) )
          {
            v33 = _o_towlower(*a1);
            v34 = a1[1];
            String = v33;
            v48 = _o_towlower(v34);
            if ( !(unsigned int)_o_iswxdigit(String) || !(unsigned int)_o_iswxdigit(v48) )
              return 1;
            Src[i] = wcstol(&String, 0, 16);
            a1 += 2;
            v31 = Size;
          }
          a2 = 0;
          v8 = 2;
          goto LABEL_29;
        }
        Sid = 0;
        v24 = (void *)THAlloc_((_DWORD)Value, 1, 2 * (a2 - 3), 1, 0, 51383435);
        memcpy_0(v24, a1 + 4, 2LL * (a2 - 3));
        *((_WORD *)v24 + a2 - 4) = 0;
        if ( ConvertStringSidToSidW((LPCWSTR)v24, &Sid) )
        {
          v27 = RtlLengthSid(Sid);
          LODWORD(Size) = v27;
          if ( v27 > 0x1C )
          {
            LocalFree(Sid);
            if ( v24 )
              THFreeAux((_DWORD)Value, (_DWORD)v24, v28, v29, 51383445);
            return 1;
          }
          memcpy_0(Src, Sid, v27);
          LocalFree(Sid);
          a2 = 0;
          Sid = 0;
          v8 = 2;
        }
        if ( v24 )
          THFreeAux((_DWORD)Value, (_DWORD)v24, v25, v26, 51383461);
        if ( v8 == 2 )
          goto LABEL_29;
        v23 = a2 < 6;
      }
      if ( v23 )
        return 1;
      goto LABEL_64;
    }
LABEL_73:
    if ( *a1 == 36 )
    {
      result = DSNameExpandMacro(Value, a1, a2, a3);
      if ( !(_DWORD)result )
        return result;
    }
    goto LABEL_29;
  }
  if ( (unsigned int)_o__wcsnicmp(a1, L"guid:", 5) )
    goto LABEL_50;
  if ( a2 == 37 )
  {
    a1 += 5;
    for ( j = 0; (unsigned int)j < 0x10; j = (unsigned int)(j + 1) )
    {
      v21 = _o_towlower(*a1);
      v22 = a1[1];
      String = v21;
      v48 = _o_towlower(v22);
      if ( !(unsigned int)_o_iswxdigit(String) || !(unsigned int)_o_iswxdigit(v48) )
        return 1;
      a1 += 2;
      *((_BYTE *)&Uuid.Data1 + j) = wcstol(&String, 0, 16);
    }
  }
  else
  {
    if ( a2 != 41 )
      return 1;
    a1 += 5;
    StringCchCopyNExW(pszDest, 0x25u, a1, 0x24u, v41, v42, v43);
    if ( UuidFromStringW(pszDest, &Uuid) )
      return 1;
  }
  v8 = 1;
  a2 = 0;
LABEL_29:
  v12 = 2 * a2 + 58;
  v13 = (void *)THAlloc_((_DWORD)Value, 1, v12, 1, 0, 51383509);
  *a3 = v13;
  memset_0(v13, 0, v12);
  *(_DWORD *)*a3 = v12;
  v14 = v8 - 1;
  if ( !v14 )
  {
    *(UUID *)(*a3 + 8LL) = Uuid;
    goto LABEL_88;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    v40 = Size;
    if ( !(_DWORD)Size )
    {
LABEL_88:
      result = 0;
      *(_WORD *)(*a3 + 2LL * a2 + 56) = 0;
      return result;
    }
    if ( RtlLengthSid(Src) == v40 && RtlValidSid(Src) )
    {
      memcpy_0((void *)(*a3 + 24LL), Src, v40);
      *(_DWORD *)(*a3 + 4LL) = v40;
      goto LABEL_88;
    }
    return 1;
  }
  if ( v15 != 1 || !a2 )
    goto LABEL_88;
  v16 = a1;
  v17 = (wchar_t *)(*a3 + 56LL);
  for ( k = a2; k; --k )
  {
    v19 = *v16;
    if ( *v16 == 34 || v19 == 92 )
    {
      v7 = 0;
      break;
    }
    *v17 = v19;
    ++v16;
    ++v17;
  }
  *(_DWORD *)(*a3 + 52LL) = a2;
  if ( v7 )
    goto LABEL_88;
  v35 = (void *)(*a3 + 56LL);
  Sid = 0;
  memcpy_0(v35, a1, 2LL * a2);
  v36 = Value;
  *(_WORD *)(*a3 + 2LL * a2 + 56) = 0;
  v37 = DSNameToBlockName(v36, *a3, &Sid, 0);
  if ( *a3 )
    THFreeAux((_DWORD)v36, *a3, v38, v39, 51383554);
  *a3 = 0;
  if ( !v37 )
  {
    v37 = BlockNameToDSName(v36, Sid, a3);
    FreeBlockName(Sid);
  }
  return v37;
}

```

## disassembly

```asm
0x1800fbd7c  mov     [rsp-8+arg_18], rbx
0x1800fbd81  push    rbp
0x1800fbd82  push    rsi
0x1800fbd83  push    rdi
0x1800fbd84  push    r12
0x1800fbd86  push    r13
0x1800fbd88  push    r14
0x1800fbd8a  push    r15
0x1800fbd8c  lea     rbp, [rsp-27h]
0x1800fbd91  sub     rsp, 100h
0x1800fbd98  mov     rax, cs:__security_cookie
0x1800fbd9f  xor     rax, rsp
0x1800fbda2  mov     [rbp+57h+var_40], rax
0x1800fbda6  mov     r14, rcx
0x1800fbda9  mov     r12, r8
0x1800fbdac  mov     ecx, cs:dwTSindex; dwTlsIndex
0x1800fbdb2  mov     esi, edx
0x1800fbdb4  call    cs:__imp_TlsGetValue
0x1800fbdba  xorps   xmm1, xmm1
0x1800fbdbd  mov     [rsp+130h+var_E0], rax
0x1800fbdc2  mov     rbx, rax
0x1800fbdc5  xorps   xmm0, xmm0
0x1800fbdc8  xor     eax, eax
0x1800fbdca  movups  xmmword ptr [rbp+57h+Src], xmm1
0x1800fbdce  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x1800fbdd2  lea     r15d, [rax+1]
0x1800fbdd6  movups  xmmword ptr [rbp+57h+Src+0Ch], xmm1
0x1800fbdda  test    r12, r12
0x1800fbddd  jz      loc_1800FC10C
0x1800fbde3  test    r14, r14
0x1800fbde6  jz      loc_1800FC10C
0x1800fbdec  mov     dword ptr [rsp+130h+Size], eax
0x1800fbdf0  lea     edi, [rax+0Ah]
0x1800fbdf3  lea     r13d, [rax+3]
0x1800fbdf7  jmp     short loc_1800FBE1C
0x1800fbdf9  test    eax, eax
0x1800fbdfb  jnz     short loc_1800FBE20
0x1800fbdfd  cmp     [r14], di
0x1800fbe01  jz      short loc_1800FBE16
0x1800fbe03  cmp     word ptr [r14], 0Dh
0x1800fbe08  jz      short loc_1800FBE16
0x1800fbe0a  cmp     word ptr [r14], 20h ; ' '
0x1800fbe0f  jz      short loc_1800FBE16
0x1800fbe11  mov     eax, r15d
0x1800fbe14  jmp     short loc_1800FBE1C
0x1800fbe16  add     r14, 2
0x1800fbe1a  dec     esi
0x1800fbe1c  test    esi, esi
0x1800fbe1e  jnz     short loc_1800FBDF9
0x1800fbe20  xor     r8d, r8d
0x1800fbe23  jmp     short loc_1800FBE85
0x1800fbe25  test    r8d, r8d
0x1800fbe28  jnz     short loc_1800FBE89
0x1800fbe2a  lea     edx, [rsi-1]
0x1800fbe2d  cmp     [r14+rdx*2], di
0x1800fbe32  jz      short loc_1800FBE49
0x1800fbe34  cmp     word ptr [r14+rdx*2], 0Dh
0x1800fbe3a  jz      short loc_1800FBE49
0x1800fbe3c  cmp     word ptr [r14+rdx*2], 20h ; ' '
0x1800fbe42  jz      short loc_1800FBE49
0x1800fbe44  mov     r8d, r15d
0x1800fbe47  jmp     short loc_1800FBE85
0x1800fbe49  cmp     esi, r15d
0x1800fbe4c  jbe     short loc_1800FBE83
0x1800fbe4e  lea     eax, [rsi-2]
0x1800fbe51  cmp     word ptr [r14+rax*2], 5Ch ; '\'
0x1800fbe57  jnz     short loc_1800FBE83
0x1800fbe59  mov     ecx, r15d
0x1800fbe5c  cmp     esi, 2
0x1800fbe5f  jbe     short loc_1800FBE7A
0x1800fbe61  mov     eax, esi
0x1800fbe63  sub     eax, ecx
0x1800fbe65  sub     eax, 2
0x1800fbe68  cmp     word ptr [r14+rax*2], 5Ch ; '\'
0x1800fbe6e  jnz     short loc_1800FBE7A
0x1800fbe70  add     ecx, r15d
0x1800fbe73  lea     eax, [rcx+1]
0x1800fbe76  cmp     esi, eax
0x1800fbe78  ja      short loc_1800FBE61
0x1800fbe7a  test    r15b, cl
0x1800fbe7d  mov     r8d, r15d
0x1800fbe80  cmovnz  edx, esi
0x1800fbe83  mov     esi, edx
0x1800fbe85  test    esi, esi
0x1800fbe87  jnz     short loc_1800FBE25
0x1800fbe89  cmp     esi, r13d
0x1800fbe8c  jbe     loc_1800FBF54
0x1800fbe92  mov     r8, r13
0x1800fbe95  lea     rdx, aDn_0; "dn:"
0x1800fbe9c  mov     rcx, r14
0x1800fbe9f  call    cs:__imp__o__wcsnicmp
0x1800fbea5  test    eax, eax
0x1800fbea7  jnz     loc_1800FBF54
0x1800fbead  add     esi, 0FFFFFFFDh
0x1800fbeb0  add     r14, 6
0x1800fbeb4  mov     rcx, [rsp+130h+var_E0]
0x1800fbeb9  lea     edi, ds:3Ah[rsi*2]
0x1800fbec0  mov     r8d, edi
0x1800fbec3  mov     r9d, r15d
0x1800fbec6  mov     dword ptr [rsp+130h+var_108], 3100CD5h
0x1800fbece  mov     rdx, r15
0x1800fbed1  mov     dword ptr [rsp+130h+var_110], 0
0x1800fbed9  call    THAlloc_
0x1800fbede  mov     r8d, edi; Size
0x1800fbee1  xor     edx, edx; Val
0x1800fbee3  mov     rcx, rax; void *
0x1800fbee6  mov     [r12], rax
0x1800fbeea  call    memset_0
0x1800fbeef  mov     rax, [r12]
0x1800fbef3  mov     [rax], edi
0x1800fbef5  sub     r13d, r15d
0x1800fbef8  jz      loc_1800FC33D
0x1800fbefe  sub     r13d, r15d
0x1800fbf01  jz      loc_1800FC2F4
0x1800fbf07  cmp     r13d, r15d
0x1800fbf0a  jnz     loc_1800FC34A
0x1800fbf10  test    esi, esi
0x1800fbf12  jz      loc_1800FC34A
0x1800fbf18  mov     rax, [r12]
0x1800fbf1c  mov     r8, r14
0x1800fbf1f  add     rax, 38h ; '8'
0x1800fbf23  mov     edx, esi
0x1800fbf25  test    edx, edx
0x1800fbf27  jz      loc_1800FC255
0x1800fbf2d  movzx   ecx, word ptr [r8]
0x1800fbf31  cmp     cx, 22h ; '"'
0x1800fbf35  jz      loc_1800FC252
0x1800fbf3b  cmp     cx, 5Ch ; '\'
0x1800fbf3f  jz      loc_1800FC252
0x1800fbf45  mov     [rax], cx
0x1800fbf48  add     r8, 2
0x1800fbf4c  add     rax, 2
0x1800fbf50  dec     edx
0x1800fbf52  jmp     short loc_1800FBF25
0x1800fbf54  mov     r8d, 5
0x1800fbf5a  cmp     esi, r8d
0x1800fbf5d  jbe     loc_1800FC026
0x1800fbf63  lea     rdx, aGuid_7; "guid:"
0x1800fbf6a  mov     rcx, r14
0x1800fbf6d  call    cs:__imp__o__wcsnicmp
0x1800fbf73  test    eax, eax
0x1800fbf75  jnz     loc_1800FC02F
0x1800fbf7b  lea     edx, [rax+25h]; cchDest
0x1800fbf7e  cmp     esi, edx
0x1800fbf80  jz      short loc_1800FBFBE
0x1800fbf82  cmp     esi, 29h ; ')'
0x1800fbf85  jnz     loc_1800FC10C
0x1800fbf8b  add     r14, rdi
0x1800fbf8e  lea     r9d, [rax+24h]; cchToCopy
0x1800fbf92  mov     r8, r14; pszSrc
0x1800fbf95  lea     rcx, [rbp+57h+pszDest]; pszDest
0x1800fbf99  call    StringCchCopyNExW
0x1800fbf9e  lea     rdx, [rbp+57h+Uuid]; Uuid
0x1800fbfa2  lea     rcx, [rbp+57h+pszDest]; StringUuid
0x1800fbfa6  call    cs:__imp_UuidFromStringW
0x1800fbfac  test    eax, eax
0x1800fbfae  jnz     loc_1800FC10C
0x1800fbfb4  mov     r13d, r15d
0x1800fbfb7  xor     esi, esi
0x1800fbfb9  jmp     loc_1800FBEB4
0x1800fbfbe  add     r14, rdi
0x1800fbfc1  xor     ebx, ebx
0x1800fbfc3  cmp     ebx, 10h
0x1800fbfc6  jnb     short loc_1800FBFB4
0x1800fbfc8  movzx   ecx, word ptr [r14]
0x1800fbfcc  call    cs:__imp__o_towlower
0x1800fbfd2  movzx   ecx, word ptr [r14+2]
0x1800fbfd7  mov     [rbp+57h+String], ax
0x1800fbfdb  call    cs:__imp__o_towlower
0x1800fbfe1  movzx   ecx, [rbp+57h+String]
0x1800fbfe5  mov     [rbp+57h+var_CE], ax
0x1800fbfe9  call    cs:__imp__o_iswxdigit
0x1800fbfef  test    eax, eax
0x1800fbff1  jz      loc_1800FC10C
0x1800fbff7  movzx   ecx, [rbp+57h+var_CE]
0x1800fbffb  call    cs:__imp__o_iswxdigit
0x1800fc001  test    eax, eax
0x1800fc003  jz      loc_1800FC10C
0x1800fc009  xor     edx, edx; EndPtr
0x1800fc00b  lea     rcx, [rbp+57h+String]; String
0x1800fc00f  lea     r8d, [rdx+10h]; Radix
0x1800fc013  call    cs:__imp_wcstol
0x1800fc019  add     r14, 4
0x1800fc01d  mov     byte ptr [rbp+rbx+57h+Uuid.Data1], al
0x1800fc021  add     ebx, r15d
0x1800fc024  jmp     short loc_1800FBFC3
0x1800fc026  cmp     esi, 4
0x1800fc029  jbe     loc_1800FC21C
0x1800fc02f  mov     r8d, 4
0x1800fc035  lea     rdx, aSid; "sid:"
0x1800fc03c  mov     rcx, r14
0x1800fc03f  call    cs:__imp__o__wcsnicmp
0x1800fc045  test    eax, eax
0x1800fc047  jnz     loc_1800FC225
0x1800fc04d  cmp     esi, 6
0x1800fc050  jbe     loc_1800FC188
0x1800fc056  lea     r8d, [rax+6]
0x1800fc05a  mov     rcx, r14
0x1800fc05d  lea     rdx, aSidS; "sid:S-"
0x1800fc064  call    cs:__imp__o__wcsnicmp
0x1800fc06a  test    eax, eax
0x1800fc06c  jnz     loc_1800FC18A
0x1800fc072  mov     rcx, [rsp+130h+var_E0]
0x1800fc077  lea     edi, [rsi-3]
0x1800fc07a  mov     ebx, edi
0x1800fc07c  mov     r9d, r15d
0x1800fc07f  add     rbx, rbx
0x1800fc082  mov     dword ptr [rsp+130h+var_108], 3100C8Bh
0x1800fc08a  mov     r8, rbx
0x1800fc08d  mov     [rsp+130h+Sid], 0
0x1800fc096  mov     rdx, r15
0x1800fc099  mov     dword ptr [rsp+130h+var_110], eax
0x1800fc09d  call    THAlloc_
0x1800fc0a2  mov     r8, rbx; Size
0x1800fc0a5  lea     rdx, [r14+8]; Src
0x1800fc0a9  mov     rcx, rax; void *
0x1800fc0ac  mov     rbx, rax
0x1800fc0af  call    memcpy_0
0x1800fc0b4  lea     ecx, [rdi-1]
0x1800fc0b7  xor     eax, eax
0x1800fc0b9  lea     rdx, [rsp+130h+Sid]; Sid
0x1800fc0be  mov     [rbx+rcx*2], ax
0x1800fc0c2  mov     rcx, rbx; StringSid
0x1800fc0c5  call    cs:__imp_ConvertStringSidToSidW
0x1800fc0cb  test    eax, eax
0x1800fc0cd  jz      loc_1800FC161
0x1800fc0d3  mov     rcx, [rsp+130h+Sid]; Sid
0x1800fc0d8  call    cs:__imp_RtlLengthSid
0x1800fc0de  mov     dword ptr [rsp+130h+Size], eax
0x1800fc0e2  cmp     eax, 1Ch
0x1800fc0e5  jbe     short loc_1800FC136
0x1800fc0e7  mov     rcx, [rsp+130h+Sid]; hMem
0x1800fc0ec  call    cs:__imp_LocalFree
0x1800fc0f2  test    rbx, rbx
0x1800fc0f5  jz      short loc_1800FC10C
0x1800fc0f7  mov     rcx, [rsp+130h+var_E0]
0x1800fc0fc  mov     rdx, rbx
0x1800fc0ff  mov     dword ptr [rsp+130h+var_110], 3100C95h
0x1800fc107  call    THFreeAux
0x1800fc10c  mov     eax, r15d
0x1800fc10f  mov     rcx, [rbp+57h+var_40]
0x1800fc113  xor     rcx, rsp; StackCookie
0x1800fc116  call    __security_check_cookie
0x1800fc11b  mov     rbx, [rsp+130h+arg_18]
0x1800fc123  add     rsp, 100h
0x1800fc12a  pop     r15
0x1800fc12c  pop     r14
0x1800fc12e  pop     r13
0x1800fc130  pop     r12
0x1800fc132  pop     rdi
0x1800fc133  pop     rsi
0x1800fc134  pop     rbp
0x1800fc135  retn
0x1800fc136  mov     rdx, [rsp+130h+Sid]; Src
0x1800fc13b  lea     rcx, [rbp+57h+Src]; void *
0x1800fc13f  mov     r8d, eax; Size
0x1800fc142  call    memcpy_0
0x1800fc147  mov     rcx, [rsp+130h+Sid]; hMem
0x1800fc14c  call    cs:__imp_LocalFree
0x1800fc152  xor     esi, esi
0x1800fc154  mov     [rsp+130h+Sid], 0
0x1800fc15d  lea     r13d, [rsi+2]
0x1800fc161  test    rbx, rbx
0x1800fc164  jz      short loc_1800FC17B
0x1800fc166  mov     rcx, [rsp+130h+var_E0]
0x1800fc16b  mov     rdx, rbx
0x1800fc16e  mov     dword ptr [rsp+130h+var_110], 3100CA5h
0x1800fc176  call    THFreeAux
0x1800fc17b  cmp     r13d, 2
0x1800fc17f  jz      loc_1800FBEB4
0x1800fc185  cmp     esi, 6
0x1800fc188  jb      short loc_1800FC10C
0x1800fc18a  test    r15b, sil
0x1800fc18d  jnz     loc_1800FC10C
0x1800fc193  lea     eax, [rsi-4]
0x1800fc196  shr     eax, 1
0x1800fc198  mov     dword ptr [rsp+130h+Size], eax
0x1800fc19c  cmp     eax, 1Ch
0x1800fc19f  ja      loc_1800FC10C
0x1800fc1a5  add     r14, 8
0x1800fc1a9  xor     ebx, ebx
0x1800fc1ab  cmp     ebx, eax
0x1800fc1ad  jnb     short loc_1800FC211
0x1800fc1af  movzx   ecx, word ptr [r14]
0x1800fc1b3  call    cs:__imp__o_towlower
0x1800fc1b9  movzx   ecx, word ptr [r14+2]
0x1800fc1be  mov     [rbp+57h+String], ax
0x1800fc1c2  call    cs:__imp__o_towlower
0x1800fc1c8  movzx   ecx, [rbp+57h+String]
0x1800fc1cc  mov     [rbp+57h+var_CE], ax
0x1800fc1d0  call    cs:__imp__o_iswxdigit
0x1800fc1d6  test    eax, eax
0x1800fc1d8  jz      loc_1800FC10C
0x1800fc1de  movzx   ecx, [rbp+57h+var_CE]
0x1800fc1e2  call    cs:__imp__o_iswxdigit
0x1800fc1e8  test    eax, eax
0x1800fc1ea  jz      loc_1800FC10C
0x1800fc1f0  xor     edx, edx; EndPtr
0x1800fc1f2  lea     rcx, [rbp+57h+String]; String
0x1800fc1f6  lea     r8d, [rdx+10h]; Radix
  ... truncated ...
```
