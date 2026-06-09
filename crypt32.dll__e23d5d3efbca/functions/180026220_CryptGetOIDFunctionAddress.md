# CryptGetOIDFunctionAddress

- ea: `0x180026220`
- end: `0x180026715`
- name: `CryptGetOIDFunctionAddress`
- size: `1269`
- prototype: `BOOL __stdcall(HCRYPTOIDFUNCSET hFuncSet, DWORD dwEncodingType, LPCSTR pszOID, DWORD dwFlags, void **ppvFuncAddr, HCRYPTOIDFUNCADDR *phFuncAddr)`
- caller_count: `46`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800240d0`
- `0x1800252d0`
- `0x1800253b0`
- `0x180025488`
- `0x180025540`
- `0x1800257d0`
- `0x180025ac0`
- `0x180025cf0`
- `0x18005acf0`
- `0x18005be80`
- `0x18006d370`
- `0x1800701b0`
- `0x180070274`
- `0x180070c18`
- `0x180083584`
- `0x180083768`
- `0x180085660`
- `0x180085800`
- `0x180085de0`
- `0x180089024`
- `0x1800890f4`
- `0x180089450`
- `0x18008d010`
- `0x1800a2c60`
- `0x1800a2ff0`
- `0x1800a33e8`
- `0x1800a9f44`
- `0x1800af618`
- `0x1800b0dfc`
- `0x1800bb2c0`
- `0x1800bc1f8`
- `0x1800c99b0`
- `0x1800cb304`
- `0x1800e241c`
- `0x1800f69a0`
- `0x1801004b0`
- `0x1801005b0`
- `0x1801006a0`
- `0x1801026c0`
- `0x180102910`
- `0x1801029b4`
- `0x180102b4c`
- `0x1801047f0`
- `0x180109f7c`
- `0x18010a1f4`
- `0x180112f44`

## callees

- `0x1800258c4`
- `0x180026220`
- `0x180026720`
- `0x180027ba8`
- `0x180027cb0`
- `0x1800bf564`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800266ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800266f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800266ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800266f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002631f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026425`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800266dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026702`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002631f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026425`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800266dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026702`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800263d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026540`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800265af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026643`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002668c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800263d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026540`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800265af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026643`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002668c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002635a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026501`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026589`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026676`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800266bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002635a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026501`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026589`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026676`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800266bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026661`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800266a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026661`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800266a6`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180026492`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800264ec`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18002662e`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180026492`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800264ec`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18002662e`

## pseudocode

```c
BOOL __stdcall CryptGetOIDFunctionAddress(
        HCRYPTOIDFUNCSET hFuncSet,
        DWORD dwEncodingType,
        LPCSTR pszOID,
        DWORD dwFlags,
        void **ppvFuncAddr,
        HCRYPTOIDFUNCADDR *phFuncAddr)
{
  DWORD v6; // esi
  char v7; // r14
  DWORD v8; // edx
  const CHAR *v9; // rdi
  int v11; // r14d
  __int64 v12; // rbx
  void **v13; // r8
  __int64 i; // rax
  unsigned __int64 v15; // rcx
  BOOL result; // eax
  __int64 v17; // rbx
  const CHAR *lpString2; // rax
  bool v19; // zf
  __int64 v20; // rsi
  FARPROC v21; // rbx
  __int64 v22; // rdi
  __int64 v23; // rcx
  __int64 v24; // rcx
  int v25; // eax
  int v26; // eax
  __int64 j; // rbx
  const CHAR *v28; // rax
  bool v29; // zf
  __int64 v30; // rbx
  FARPROC ProcAddress; // r12
  __int64 v32; // r15
  int v33; // eax
  DWORD v34; // ebx
  DWORD LastError; // ebx

  v6 = (unsigned __int16)dwEncodingType;
  v7 = dwFlags;
  v8 = HIWORD(dwEncodingType);
  v9 = pszOID;
  if ( !v6 )
    v6 = v8;
  if ( (unsigned __int64)pszOID > 0xFFFF && *pszOID == 35 )
  {
    v9 = (const CHAR *)o_atol_0(pszOID + 1);
    if ( (unsigned __int64)v9 > 0xFFFF )
    {
      SetLastError(0x80070057);
      *ppvFuncAddr = 0;
      *phFuncAddr = 0;
      return 0;
    }
  }
  if ( !*((_DWORD *)hFuncSet + 12) )
  {
    EnterCriticalSection(&CriticalSection);
    if ( !*((_DWORD *)hFuncSet + 12) )
    {
      CryptEnumOIDFunction(0xFFFFFFFF, *((LPCSTR *)hFuncSet + 1), 0, 0, hFuncSet, EnumRegFuncCallback);
      *((_DWORD *)hFuncSet + 12) = 1;
    }
    LeaveCriticalSection(&CriticalSection);
  }
  v11 = v7 & 1;
  if ( v11 || (v12 = *((_QWORD *)hFuncSet + 7)) == 0 )
  {
    v13 = ppvFuncAddr;
    goto LABEL_8;
  }
  while ( 1 )
  {
    if ( !v12 )
    {
      v13 = ppvFuncAddr;
      *ppvFuncAddr = 0;
      *phFuncAddr = 0;
      goto LABEL_8;
    }
    if ( v6 == *(_DWORD *)v12 )
    {
      v28 = *(const CHAR **)(v12 + 16);
      if ( (unsigned __int64)v9 <= 0xFFFF )
      {
        v29 = v9 == v28;
        goto LABEL_56;
      }
      if ( (unsigned __int64)v28 > 0xFFFF )
        break;
    }
LABEL_57:
    v12 = *(_QWORD *)(v12 + 8);
  }
  v29 = CompareStringA(0x409u, 1u, v9, -1, v28, -1) == 2;
LABEL_56:
  if ( !v29 )
    goto LABEL_57;
  v30 = *(_QWORD *)(v12 + 24);
  EnterCriticalSection(&CriticalSection);
  ProcAddress = *(FARPROC *)(v30 + 24);
  v32 = *(_QWORD *)(v30 + 8);
  if ( ProcAddress )
  {
    AddRefDll(*(struct _DLL_ELEMENT **)(v30 + 8));
    goto LABEL_60;
  }
  LeaveCriticalSection(&CriticalSection);
  if ( !(unsigned int)LoadDll((struct _DLL_ELEMENT *)v32) )
  {
LABEL_76:
    v33 = 0;
    v32 = 0;
    ProcAddress = 0;
    goto LABEL_61;
  }
  ProcAddress = GetProcAddress(*(HMODULE *)(v32 + 24), *(LPCSTR *)(v30 + 16));
  if ( !ProcAddress )
  {
    LastError = GetLastError();
    ReleaseDll((struct _DLL_ELEMENT *)v32);
    SetLastError(LastError);
    goto LABEL_76;
  }
  EnterCriticalSection(&CriticalSection);
  *(_QWORD *)(v30 + 24) = ProcAddress;
LABEL_60:
  LeaveCriticalSection(&CriticalSection);
  v33 = 1;
LABEL_61:
  v13 = ppvFuncAddr;
  *ppvFuncAddr = ProcAddress;
  *phFuncAddr = (HCRYPTOIDFUNCADDR)v32;
  if ( v33 )
    return 1;
LABEL_8:
  if ( (unsigned __int64)v9 <= 0xFFFF )
  {
    for ( i = *((_QWORD *)hFuncSet + 2); i; i = *(_QWORD *)(i + 8) )
    {
      if ( v6 == *(_DWORD *)(i + 4) )
      {
        v15 = *(_QWORD *)(i + 16);
        if ( (unsigned __int64)v9 >= v15 && (unsigned __int64)v9 <= *(_QWORD *)(i + 24) )
        {
          *v13 = *(void **)(*(_QWORD *)(i + 40) + 8LL * (_QWORD)&v9[-v15]);
          *phFuncAddr = (HCRYPTOIDFUNCADDR)i;
          return 1;
        }
      }
    }
LABEL_15:
    if ( v11 )
      goto LABEL_25;
    v17 = *((_QWORD *)hFuncSet + 8);
    if ( !v17 )
      goto LABEL_25;
    while ( 2 )
    {
      if ( !v17 )
      {
        *ppvFuncAddr = 0;
        *phFuncAddr = 0;
        goto LABEL_25;
      }
      if ( v6 == *(_DWORD *)v17 )
      {
        lpString2 = *(const CHAR **)(v17 + 16);
        if ( (unsigned __int64)v9 > 0xFFFF )
        {
          if ( (unsigned __int64)lpString2 > 0xFFFF )
          {
            v19 = CompareStringA(0x409u, 1u, v9, -1, lpString2, -1) == 2;
            goto LABEL_21;
          }
        }
        else
        {
          v19 = v9 == lpString2;
LABEL_21:
          if ( v19 )
          {
            v20 = *(_QWORD *)(v17 + 24);
            EnterCriticalSection(&CriticalSection);
            v21 = *(FARPROC *)(v20 + 24);
            v22 = *(_QWORD *)(v20 + 8);
            if ( v21 )
            {
              ++*(_DWORD *)(v22 + 32);
              if ( *(_DWORD *)(v22 + 56) )
              {
                v23 = *(_QWORD *)(v22 + 64);
                *(_DWORD *)(v22 + 56) = 0;
                if ( v23 )
                  *(_QWORD *)(v23 + 72) = *(_QWORD *)(v22 + 72);
                v24 = *(_QWORD *)(v22 + 72);
                if ( v24 )
                {
                  *(_QWORD *)(v24 + 64) = *(_QWORD *)(v22 + 64);
                }
                else if ( (struct _DLL_ELEMENT *)v22 == qword_1801583A0 )
                {
                  qword_1801583A0 = *(struct _DLL_ELEMENT **)(v22 + 64);
                }
                v25 = dword_1801583A8;
                *(_QWORD *)(v22 + 64) = 0;
                *(_QWORD *)(v22 + 72) = 0;
                if ( v25 )
                  dword_1801583A8 = v25 - 1;
              }
LABEL_35:
              LeaveCriticalSection(&CriticalSection);
              v26 = 1;
            }
            else
            {
              LeaveCriticalSection(&CriticalSection);
              if ( (unsigned int)LoadDll((struct _DLL_ELEMENT *)v22) )
              {
                v21 = GetProcAddress(*(HMODULE *)(v22 + 24), *(LPCSTR *)(v20 + 16));
                if ( v21 )
                {
                  EnterCriticalSection(&CriticalSection);
                  *(_QWORD *)(v20 + 24) = v21;
                  goto LABEL_35;
                }
                v34 = GetLastError();
                ReleaseDll((struct _DLL_ELEMENT *)v22);
                SetLastError(v34);
              }
              v26 = 0;
              v22 = 0;
              v21 = 0;
            }
            *ppvFuncAddr = v21;
            *phFuncAddr = (HCRYPTOIDFUNCADDR)v22;
            if ( v26 )
              return 1;
LABEL_25:
            SetLastError(2u);
            *ppvFuncAddr = 0;
            result = 0;
            *phFuncAddr = 0;
            return result;
          }
        }
      }
      v17 = *(_QWORD *)(v17 + 8);
      continue;
    }
  }
  for ( j = *((_QWORD *)hFuncSet + 4); ; j = *(_QWORD *)(j + 8) )
  {
    if ( !j )
      goto LABEL_15;
    if ( v6 == *(_DWORD *)(j + 4) && CompareStringA(0x409u, 1u, v9, -1, *(PCNZCH *)(j + 16), -1) == 2 )
      break;
  }
  *ppvFuncAddr = *(void **)(j + 32);
  result = 1;
  *phFuncAddr = (HCRYPTOIDFUNCADDR)j;
  return result;
}

```

## disassembly

```asm
0x180026220  push    rbp
0x180026222  push    rsi
0x180026223  push    rdi
0x180026224  push    r14
0x180026226  sub     rsp, 38h
0x18002622a  movzx   esi, dx
0x18002622d  mov     r14d, r9d
0x180026230  shr     edx, 10h
0x180026233  mov     rdi, r8
0x180026236  test    esi, esi
0x180026238  mov     rbp, rcx
0x18002623b  cmovz   esi, edx
0x18002623e  cmp     r8, 0FFFFh
0x180026245  ja      loc_1800263FD
0x18002624b  cmp     dword ptr [rbp+30h], 0
0x18002624f  mov     [rsp+58h+arg_10], r13
0x180026254  mov     r13, [rsp+58h+phFuncAddr]
0x18002625c  mov     [rsp+58h+var_28], r15
0x180026261  jz      loc_1800264FA
0x180026267  xor     r15d, r15d
0x18002626a  mov     [rsp+58h+arg_0], rbx
0x18002626f  and     r14d, 1
0x180026273  jnz     short loc_180026282
0x180026275  mov     rbx, [rbp+38h]
0x180026279  test    rbx, rbx
0x18002627c  jnz     loc_180026550
0x180026282  mov     r8, [rsp+58h+ppvFuncAddr]
0x18002628a  cmp     rdi, 0FFFFh
0x180026291  ja      loc_180026455
0x180026297  mov     rax, [rbp+10h]
0x18002629b  test    rax, rax
0x18002629e  jz      short loc_1800262CD
0x1800262a0  cmp     esi, [rax+4]
0x1800262a3  jnz     short loc_180026305
0x1800262a5  mov     rcx, [rax+10h]
0x1800262a9  cmp     rdi, rcx
0x1800262ac  jb      short loc_180026305
0x1800262ae  cmp     rdi, [rax+18h]
0x1800262b2  ja      short loc_180026305
0x1800262b4  sub     rdi, rcx
0x1800262b7  mov     rcx, [rax+28h]
0x1800262bb  mov     rdx, [rcx+rdi*8]
0x1800262bf  mov     [r8], rdx
0x1800262c2  mov     [r13+0], rax
0x1800262c6  mov     eax, 1
0x1800262cb  jmp     short loc_180026336
0x1800262cd  test    r14d, r14d
0x1800262d0  jnz     short loc_18002631A
0x1800262d2  mov     rbx, [rbp+40h]
0x1800262d6  test    rbx, rbx
0x1800262d9  jz      short loc_18002631A
0x1800262db  nop     dword ptr [rax+rax+00h]
0x1800262e0  test    rbx, rbx
0x1800262e3  jz      short loc_18002630B
0x1800262e5  cmp     esi, [rbx]
0x1800262e7  jnz     short loc_1800262FF
0x1800262e9  mov     rax, [rbx+10h]
0x1800262ed  cmp     rdi, 0FFFFh
0x1800262f4  ja      loc_1800264C0
0x1800262fa  cmp     rdi, rax
0x1800262fd  jz      short loc_18002634F
0x1800262ff  mov     rbx, [rbx+8]
0x180026303  jmp     short loc_1800262E0
0x180026305  mov     rax, [rax+8]
0x180026309  jmp     short loc_18002629B
0x18002630b  mov     rax, [rsp+58h+ppvFuncAddr]
0x180026313  mov     [rax], r15
0x180026316  mov     [r13+0], r15
0x18002631a  mov     ecx, 2; dwErrCode
0x18002631f  call    cs:__imp_SetLastError
0x180026325  mov     rax, [rsp+58h+ppvFuncAddr]
0x18002632d  mov     [rax], r15
0x180026330  xor     eax, eax
0x180026332  mov     [r13+0], r15
0x180026336  mov     rbx, [rsp+58h+arg_0]
0x18002633b  mov     r13, [rsp+58h+arg_10]
0x180026340  mov     r15, [rsp+58h+var_28]
0x180026345  add     rsp, 38h
0x180026349  pop     r14
0x18002634b  pop     rdi
0x18002634c  pop     rsi
0x18002634d  pop     rbp
0x18002634e  retn
0x18002634f  mov     rsi, [rbx+18h]
0x180026353  lea     rcx, CriticalSection; lpCriticalSection
0x18002635a  call    cs:__imp_EnterCriticalSection
0x180026360  mov     rbx, [rsi+18h]
0x180026364  mov     rdi, [rsi+8]
0x180026368  test    rbx, rbx
0x18002636b  jz      loc_18002663C
0x180026371  inc     dword ptr [rdi+20h]
0x180026374  cmp     dword ptr [rdi+38h], 0
0x180026378  jz      short loc_1800263CA
0x18002637a  mov     rcx, [rdi+40h]
0x18002637e  mov     [rdi+38h], r15d
0x180026382  test    rcx, rcx
0x180026385  jz      short loc_18002638F
0x180026387  mov     rax, [rdi+48h]
0x18002638b  mov     [rcx+48h], rax
0x18002638f  mov     rcx, [rdi+48h]
0x180026393  test    rcx, rcx
0x180026396  jnz     loc_1800265F5
0x18002639c  cmp     rdi, cs:qword_1801583A0
0x1800263a3  jnz     short loc_1800263B0
0x1800263a5  mov     rax, [rdi+40h]
0x1800263a9  mov     cs:qword_1801583A0, rax
0x1800263b0  mov     eax, cs:dword_1801583A8
0x1800263b6  mov     [rdi+40h], r15
0x1800263ba  mov     [rdi+48h], r15
0x1800263be  test    eax, eax
0x1800263c0  jz      short loc_1800263CA
0x1800263c2  dec     eax
0x1800263c4  mov     cs:dword_1801583A8, eax
0x1800263ca  lea     rcx, CriticalSection; lpCriticalSection
0x1800263d1  call    cs:__imp_LeaveCriticalSection
0x1800263d7  mov     eax, 1
0x1800263dc  mov     rcx, [rsp+58h+ppvFuncAddr]
0x1800263e4  mov     [rcx], rbx
0x1800263e7  mov     [r13+0], rdi
0x1800263eb  test    eax, eax
0x1800263ed  jz      loc_18002631A
0x1800263f3  mov     eax, 1
0x1800263f8  jmp     loc_180026336
0x1800263fd  cmp     byte ptr [r8], 23h ; '#'
0x180026401  jnz     loc_18002624B
0x180026407  lea     rcx, [r8+1]; String
0x18002640b  call    _o_atol_0
0x180026410  movsxd  rdi, eax
0x180026413  cmp     rdi, 0FFFFh
0x18002641a  jbe     loc_18002624B
0x180026420  mov     ecx, 80070057h; dwErrCode
0x180026425  call    cs:__imp_SetLastError
0x18002642b  mov     rax, [rsp+58h+ppvFuncAddr]
0x180026433  mov     qword ptr [rax], 0
0x18002643a  mov     rax, [rsp+58h+phFuncAddr]
0x180026442  mov     qword ptr [rax], 0
0x180026449  xor     eax, eax
0x18002644b  add     rsp, 38h
0x18002644f  pop     r14
0x180026451  pop     rdi
0x180026452  pop     rsi
0x180026453  pop     rbp
0x180026454  retn
0x180026455  mov     rbx, [rbp+20h]
0x180026459  nop     dword ptr [rax+00000000h]
0x180026460  test    rbx, rbx
0x180026463  jz      loc_1800262CD
0x180026469  cmp     esi, [rbx+4]
0x18002646c  jnz     short loc_18002649D
0x18002646e  mov     rax, [rbx+10h]
0x180026472  mov     r9d, 0FFFFFFFFh; cchCount1
0x180026478  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180026480  mov     r8, rdi; lpString1
0x180026483  mov     edx, 1; dwCmpFlags
0x180026488  mov     [rsp+58h+lpString2], rax; lpString2
0x18002648d  mov     ecx, 409h; Locale
0x180026492  call    cs:__imp_CompareStringA
0x180026498  cmp     eax, 2
0x18002649b  jz      short loc_1800264A3
0x18002649d  mov     rbx, [rbx+8]
0x1800264a1  jmp     short loc_180026460
0x1800264a3  mov     rax, [rbx+20h]
0x1800264a7  mov     rcx, [rsp+58h+ppvFuncAddr]
0x1800264af  mov     [rcx], rax
0x1800264b2  mov     eax, 1
0x1800264b7  mov     [r13+0], rbx
0x1800264bb  jmp     loc_180026336
0x1800264c0  cmp     rax, 0FFFFh
0x1800264c6  jbe     loc_1800262FF
0x1800264cc  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800264d4  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800264da  mov     r8, rdi; lpString1
0x1800264dd  mov     [rsp+58h+lpString2], rax; lpString2
0x1800264e2  mov     edx, 1; dwCmpFlags
0x1800264e7  mov     ecx, 409h; Locale
0x1800264ec  call    cs:__imp_CompareStringA
0x1800264f2  cmp     eax, 2
0x1800264f5  jmp     loc_1800262FD
0x1800264fa  lea     rcx, CriticalSection; lpCriticalSection
0x180026501  call    cs:__imp_EnterCriticalSection
0x180026507  cmp     dword ptr [rbp+30h], 0
0x18002650b  jnz     short loc_180026539
0x18002650d  mov     rdx, [rbp+8]; pszFuncName
0x180026511  lea     rax, ?EnumRegFuncCallback@@YAHKPEBD0KQEBKQEBQEBGQEBQEBE1PEAX@Z; EnumRegFuncCallback(ulong,char const *,char const *,ulong,ulong const * const,ushort const * const * const,uchar const * const * const,ulong const * const,void *)
0x180026518  mov     qword ptr [rsp+58h+cchCount2], rax; pfnEnumOIDFunc
0x18002651d  xor     r9d, r9d; dwFlags
0x180026520  xor     r8d, r8d; pszOID
0x180026523  mov     [rsp+58h+lpString2], rbp; pvArg
0x180026528  mov     ecx, 0FFFFFFFFh; dwEncodingType
0x18002652d  call    CryptEnumOIDFunction
0x180026532  mov     dword ptr [rbp+30h], 1
0x180026539  lea     rcx, CriticalSection; lpCriticalSection
0x180026540  call    cs:__imp_LeaveCriticalSection
0x180026546  jmp     loc_180026267
0x180026550  test    rbx, rbx
0x180026553  jz      loc_1800265DE
0x180026559  cmp     esi, [rbx]
0x18002655b  jnz     short loc_180026573
0x18002655d  mov     rax, [rbx+10h]
0x180026561  cmp     rdi, 0FFFFh
0x180026568  ja      loc_180026602
0x18002656e  cmp     rdi, rax
0x180026571  jz      short loc_180026579
0x180026573  mov     rbx, [rbx+8]
0x180026577  jmp     short loc_180026550
0x180026579  mov     rbx, [rbx+18h]
0x18002657d  lea     rcx, CriticalSection; lpCriticalSection
0x180026584  mov     [rsp+58h+arg_8], r12
0x180026589  call    cs:__imp_EnterCriticalSection
0x18002658f  mov     r12, [rbx+18h]
0x180026593  mov     r15, [rbx+8]
0x180026597  test    r12, r12
0x18002659a  jz      loc_180026685
0x1800265a0  mov     rcx, r15; struct _DLL_ELEMENT *
0x1800265a3  call    ?AddRefDll@@YAXPEAU_DLL_ELEMENT@@@Z; AddRefDll(_DLL_ELEMENT *)
0x1800265a8  lea     rcx, CriticalSection; lpCriticalSection
0x1800265af  call    cs:__imp_LeaveCriticalSection
0x1800265b5  mov     eax, 1
0x1800265ba  mov     r8, [rsp+58h+ppvFuncAddr]
0x1800265c2  mov     [r8], r12
0x1800265c5  mov     [r13+0], r15
0x1800265c9  mov     r12, [rsp+58h+arg_8]
0x1800265ce  test    eax, eax
0x1800265d0  jnz     loc_1800263F3
0x1800265d6  xor     r15d, r15d
0x1800265d9  jmp     loc_18002628A
0x1800265de  mov     rax, [rsp+58h+ppvFuncAddr]
0x1800265e6  mov     r8, rax
0x1800265e9  mov     [rax], r15
0x1800265ec  mov     [r13+0], r15
0x1800265f0  jmp     loc_18002628A
0x1800265f5  mov     rax, [rdi+40h]
0x1800265f9  mov     [rcx+40h], rax
0x1800265fd  jmp     loc_1800263B0
0x180026602  cmp     rax, 0FFFFh
0x180026608  jbe     loc_180026573
0x18002660e  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180026616  mov     r9d, 0FFFFFFFFh; cchCount1
0x18002661c  mov     r8, rdi; lpString1
0x18002661f  mov     [rsp+58h+lpString2], rax; lpString2
0x180026624  mov     edx, 1; dwCmpFlags
0x180026629  mov     ecx, 409h; Locale
0x18002662e  call    cs:__imp_CompareStringA
0x180026634  cmp     eax, 2
0x180026637  jmp     loc_180026571
0x18002663c  lea     rcx, CriticalSection; lpCriticalSection
0x180026643  call    cs:__imp_LeaveCriticalSection
0x180026649  mov     rcx, rdi; struct _DLL_ELEMENT *
0x18002664c  call    ?LoadDll@@YAHPEAU_DLL_ELEMENT@@@Z; LoadDll(_DLL_ELEMENT *)
0x180026651  test    eax, eax
0x180026653  jz      loc_1800266E2
0x180026659  mov     rdx, [rsi+10h]; lpProcName
0x18002665d  mov     rcx, [rdi+18h]; hModule
0x180026661  call    cs:__imp_GetProcAddress
0x180026667  mov     rbx, rax
0x18002666a  test    rax, rax
0x18002666d  jz      short loc_1800266CA
0x18002666f  lea     rcx, CriticalSection; lpCriticalSection
0x180026676  call    cs:__imp_EnterCriticalSection
0x18002667c  mov     [rsi+18h], rbx
0x180026680  jmp     loc_1800263CA
0x180026685  lea     rcx, CriticalSection; lpCriticalSection
0x18002668c  call    cs:__imp_LeaveCriticalSection
0x180026692  mov     rcx, r15; struct _DLL_ELEMENT *
0x180026695  call    ?LoadDll@@YAHPEAU_DLL_ELEMENT@@@Z; LoadDll(_DLL_ELEMENT *)
0x18002669a  test    eax, eax
0x18002669c  jz      short loc_180026708
0x18002669e  mov     rdx, [rbx+10h]; lpProcName
0x1800266a2  mov     rcx, [r15+18h]; hModule
0x1800266a6  call    cs:__imp_GetProcAddress
0x1800266ac  mov     r12, rax
0x1800266af  test    rax, rax
0x1800266b2  jz      short loc_1800266F0
0x1800266b4  lea     rcx, CriticalSection; lpCriticalSection
0x1800266bb  call    cs:__imp_EnterCriticalSection
0x1800266c1  mov     [rbx+18h], r12
0x1800266c5  jmp     loc_1800265A8
0x1800266ca  call    cs:__imp_GetLastError
0x1800266d0  mov     rcx, rdi; struct _DLL_ELEMENT *
0x1800266d3  mov     ebx, eax
0x1800266d5  call    ?ReleaseDll@@YAXPEAU_DLL_ELEMENT@@@Z; ReleaseDll(_DLL_ELEMENT *)
0x1800266da  mov     ecx, ebx; dwErrCode
0x1800266dc  call    cs:__imp_SetLastError
0x1800266e2  mov     eax, r15d
0x1800266e5  mov     rdi, r15
0x1800266e8  mov     rbx, r15
0x1800266eb  jmp     loc_1800263DC
0x1800266f0  call    cs:__imp_GetLastError
0x1800266f6  mov     rcx, r15; struct _DLL_ELEMENT *
0x1800266f9  mov     ebx, eax
0x1800266fb  call    ?ReleaseDll@@YAXPEAU_DLL_ELEMENT@@@Z; ReleaseDll(_DLL_ELEMENT *)
0x180026700  mov     ecx, ebx; dwErrCode
0x180026702  call    cs:__imp_SetLastError
0x180026708  xor     eax, eax
0x18002670a  xor     r15d, r15d
0x18002670d  xor     r12d, r12d
0x180026710  jmp     loc_1800265BA
```
