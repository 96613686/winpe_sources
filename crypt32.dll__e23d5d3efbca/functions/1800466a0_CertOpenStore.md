# CertOpenStore

- ea: `0x1800466a0`
- end: `0x180046d1f`
- name: `CertOpenStore`
- size: `1663`
- prototype: `HCERTSTORE __stdcall(LPCSTR lpszStoreProvider, DWORD dwEncodingType, HCRYPTPROV_LEGACY hCryptProv, DWORD dwFlags, const void *pvPara)`
- caller_count: `40`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002ab4`
- `0x180016704`
- `0x180017e6c`
- `0x1800187e4`
- `0x1800189b0`
- `0x180018b10`
- `0x180018cc4`
- `0x18001bf60`
- `0x18001cf28`
- `0x18002c688`
- `0x18002db94`
- `0x180034858`
- `0x1800372ac`
- `0x1800466a0`
- `0x180046eb0`
- `0x18004778c`
- `0x1800480a8`
- `0x1800540b0`
- `0x180062198`
- `0x180068b04`
- `0x18007107c`
- `0x1800869b0`
- `0x18009def8`
- `0x1800a4110`
- `0x1800a577c`
- `0x1800a5b20`
- `0x1800ad8f0`
- `0x1800ae5e0`
- `0x1800afff0`
- `0x1800b9604`
- `0x1800cbb20`
- `0x1800e03a8`
- `0x1800e08fc`
- `0x1800e1524`
- `0x1800e15c4`
- `0x1800e6520`
- `0x1800e685c`
- `0x1800f3aac`
- `0x1800f3c54`
- `0x1800f85bc`

## callees

- `0x180012d00`
- `0x1800258c4`
- `0x180027ba8`
- `0x180027cb0`
- `0x180028d60`
- `0x180029494`
- `0x1800449d4`
- `0x1800466a0`
- `0x180046d28`
- `0x180046e10`
- `0x180047f10`
- `0x1800485c0`
- `0x1800952c4`
- `0x1800bb138`
- `0x1800bf564`
- `0x1801150d0`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046b8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046cbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046ce7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046b8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046cbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046ce7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800469ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046c5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046c92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046ca2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046cf9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800469ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046c5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046c92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046ca2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046cf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004699d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046a6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046c10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004699d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046a6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046c10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046977`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046a44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046c47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046977`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046a44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046c47`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004670a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004670a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046c2e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046c2e`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180046b1e`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180046b69`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180046be4`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180046b1e`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180046b69`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180046be4`
- `CRYPTSP!CryptReleaseContext` at `0x180046c70`
- `CRYPTSP!CryptReleaseContext` at `0x180046c70`

## pseudocode

```c
HCERTSTORE __stdcall CertOpenStore(
        LPCSTR lpszStoreProvider,
        DWORD dwEncodingType,
        HCRYPTPROV_LEGACY hCryptProv,
        DWORD dwFlags,
        const void *pvPara)
{
  LPCSTR v7; // rbx
  __int64 v8; // rdi
  _DWORD *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  _DWORD *v12; // r15
  struct _FUNC_SET *v13; // r14
  _QWORD *v14; // r13
  const char *v15; // rsi
  struct _REG_OID_FUNC_ELEMENT *v16; // rcx
  __int64 j; // rcx
  unsigned __int64 v18; // rax
  void *ProcAddress; // r14
  _DWORD *v20; // rsi
  DWORD v21; // ebx
  SIZE_T v22; // rcx
  size_t v23; // rdi
  _QWORD *v24; // rax
  struct _SHARE_STORE *v25; // rbx
  struct _CERT_DIAG_EVENT_STACK_ENTRY *v26; // rsi
  HCERTSTORE result; // rax
  __int64 v28; // rbx
  const CHAR *lpString2; // rax
  bool v30; // zf
  __int64 v31; // rbx
  __int64 v32; // rsi
  int v33; // eax
  DWORD v34; // ecx
  BOOL v35; // edi
  struct _SHARE_STORE *v36; // rax
  __int64 i; // rbx
  int v38; // eax
  DWORD v39; // ecx
  DWORD LastError; // ebx
  void *v41; // [rsp+40h] [rbp-58h] BYREF
  struct _CERT_DIAG_EVENT_STACK_ENTRY *v42; // [rsp+48h] [rbp-50h]
  int v46; // [rsp+B8h] [rbp+20h]

  v41 = 0;
  v46 = 0;
  v7 = lpszStoreProvider;
  v8 = -1;
  if ( dwFlags == 135360 && !hCryptProv )
  {
    if ( (unsigned __int64)lpszStoreProvider > 0xFFFF )
    {
      v38 = CompareStringA(0x409u, 1u, "System", -1, lpszStoreProvider, -1);
      v46 = v38 == 2;
      if ( v38 != 2 )
        goto LABEL_2;
    }
    else
    {
      if ( lpszStoreProvider != (LPCSTR)10 )
        goto LABEL_2;
      v46 = 1;
    }
    result = FindShareStore((PCNZWCH)pvPara);
    if ( result )
      return result;
  }
LABEL_2:
  v9 = LocalAlloc(0x40u, 0xC0u);
  v12 = v9;
  if ( !v9 )
  {
    SetLastError(0x8007000E);
    goto LABEL_85;
  }
  if ( !(unsigned int)Pki_InitializeCriticalSection(v9 + 6, v10, v11) )
  {
    PkiDefaultCryptFree(v12);
LABEL_85:
    if ( hCryptProv && (dwFlags & 1) == 0 )
      CryptReleaseContext(hCryptProv, 0);
    return 0;
  }
  v42 = (struct _CERT_DIAG_EVENT_STACK_ENTRY *)CertDiagOpenStoreStart(v7);
  v12[38] = 40;
  *v12 = 1;
  v12[1] = 1;
  v12[5] = 2;
  *((_QWORD *)v12 + 1) = hCryptProv;
  v12[4] = dwFlags;
  if ( (dwFlags & 4) != 0 )
    v12[26] = 1;
  if ( v7 == (LPCSTR)2 )
  {
    v20 = v12 + 44;
    v12[44] |= 4u;
    goto LABEL_22;
  }
  v13 = qword_1801582A8;
  v14 = v12 + 36;
  v15 = v7;
  if ( (unsigned __int64)v7 > 0xFFFF && *v7 == 35 )
  {
    v15 = (const char *)o_atol_0(v7 + 1);
    if ( (unsigned __int64)v15 > 0xFFFF )
    {
      v34 = -2147024809;
      goto LABEL_53;
    }
  }
  if ( !*((_DWORD *)v13 + 12) )
    LoadRegFunc((LPCSTR *)v13);
  v16 = (struct _REG_OID_FUNC_ELEMENT *)*((_QWORD *)v13 + 7);
  if ( v16 && GetRegOIDFunctionAddress(v16, 0, v15, &v41, (void **)v12 + 18) )
  {
    ProcAddress = v41;
    goto LABEL_18;
  }
  if ( (unsigned __int64)v15 > 0xFFFF )
  {
    for ( i = *((_QWORD *)v13 + 4); i; i = *(_QWORD *)(i + 8) )
    {
      if ( !*(_DWORD *)(i + 4) && CompareStringA(0x409u, 1u, v15, -1, *(PCNZCH *)(i + 16), -1) == 2 )
      {
        ProcAddress = *(void **)(i + 32);
        *v14 = i;
        v7 = lpszStoreProvider;
        goto LABEL_18;
      }
    }
  }
  else
  {
    for ( j = *((_QWORD *)v13 + 2); j; j = *(_QWORD *)(j + 8) )
    {
      if ( !*(_DWORD *)(j + 4) )
      {
        v18 = *(_QWORD *)(j + 16);
        if ( (unsigned __int64)v15 >= v18 && (unsigned __int64)v15 <= *(_QWORD *)(j + 24) )
        {
          ProcAddress = *(void **)(*(_QWORD *)(j + 40) + 8LL * (_QWORD)&v15[-v18]);
          *v14 = j;
          goto LABEL_18;
        }
      }
    }
  }
  v28 = *((_QWORD *)v13 + 8);
  if ( !v28 )
  {
LABEL_52:
    v34 = 2;
LABEL_53:
    SetLastError(v34);
    *v14 = 0;
LABEL_54:
    CertCloseStore(v12, 0);
    v12 = 0;
    v21 = dwFlags & 0x10;
    if ( (dwFlags & 0x10) == 0 )
      goto LABEL_28;
    goto LABEL_93;
  }
  while ( 1 )
  {
    if ( !v28 )
    {
      *v14 = 0;
      goto LABEL_52;
    }
    if ( !*(_DWORD *)v28 )
    {
      lpString2 = *(const CHAR **)(v28 + 16);
      if ( (unsigned __int64)v15 <= 0xFFFF )
      {
        v30 = v15 == lpString2;
        goto LABEL_36;
      }
      if ( (unsigned __int64)lpString2 > 0xFFFF )
        break;
    }
LABEL_37:
    v28 = *(_QWORD *)(v28 + 8);
  }
  v30 = CompareStringA(0x409u, 1u, v15, -1, lpString2, -1) == 2;
LABEL_36:
  if ( !v30 )
    goto LABEL_37;
  v31 = *(_QWORD *)(v28 + 24);
  EnterCriticalSection(&CriticalSection);
  ProcAddress = *(void **)(v31 + 24);
  v32 = *(_QWORD *)(v31 + 8);
  if ( ProcAddress )
  {
    AddRefDll(*(struct _DLL_ELEMENT **)(v31 + 8));
    goto LABEL_48;
  }
  LeaveCriticalSection(&CriticalSection);
  if ( !(unsigned int)LoadDll((struct _DLL_ELEMENT *)v32) )
  {
LABEL_98:
    v33 = 0;
    v32 = 0;
    ProcAddress = 0;
    goto LABEL_49;
  }
  ProcAddress = GetProcAddress(*(HMODULE *)(v32 + 24), *(LPCSTR *)(v31 + 16));
  if ( !ProcAddress )
  {
    LastError = GetLastError();
    ReleaseDll((struct _DLL_ELEMENT *)v32);
    SetLastError(LastError);
    goto LABEL_98;
  }
  EnterCriticalSection(&CriticalSection);
  *(_QWORD *)(v31 + 24) = ProcAddress;
LABEL_48:
  LeaveCriticalSection(&CriticalSection);
  v33 = 1;
LABEL_49:
  *v14 = v32;
  if ( !v33 )
    goto LABEL_52;
  v7 = lpszStoreProvider;
LABEL_18:
  if ( !((unsigned int (__fastcall *)(LPCSTR, _QWORD, HCRYPTPROV_LEGACY, _QWORD, const void *, _DWORD *, _DWORD *))ProcAddress)(
          v7,
          dwEncodingType,
          hCryptProv,
          dwFlags & 0xFFFFFFFB,
          pvPara,
          v12,
          v12 + 38) )
  {
    if ( (dwFlags & 0x1000) != 0 )
    {
      *((_QWORD *)v12 + 1) = 0;
      CertCloseStore(v12, 0);
      v12 = CertOpenStore(v7, dwEncodingType, hCryptProv, dwFlags & 0xFFFF6FFF | 0x8000, pvPara);
      v21 = dwFlags & 0x10;
      goto LABEL_28;
    }
    goto LABEL_54;
  }
  v20 = v12 + 44;
  if ( (v12[44] & 1) != 0 )
    *v12 = 2;
  if ( (dwFlags & 0x100) != 0 && *v12 == 1 )
    ArchiveManifoldCertificatesInStore((struct _CERT_STORE *)v12);
LABEL_22:
  v21 = dwFlags & 0x10;
  if ( (dwFlags & 0x10) != 0 )
  {
    if ( (*v20 & 2) != 0 )
    {
      CertCloseStore(v12, 0);
      v12 = 0;
      v39 = 0;
      goto LABEL_91;
    }
    SetLastError(0x78u);
    CertCloseStore(v12, 0);
    v12 = 0;
    v21 = dwFlags & 0x10;
LABEL_93:
    if ( GetLastError() )
      goto LABEL_28;
    v39 = -2147418113;
LABEL_91:
    SetLastError(v39);
    goto LABEL_28;
  }
  v12[5] = 3;
  if ( v46 != v21 )
  {
    if ( pvPara )
    {
      do
        ++v8;
      while ( *((_WORD *)pvPara + v8) );
    }
    else
    {
      LODWORD(v8) = 0;
    }
    v22 = (unsigned int)(2 * v8 + 2) + 32LL;
    v23 = (unsigned int)(2 * v8 + 2);
    v24 = (_QWORD *)PkiZeroAlloc(v22);
    v25 = (struct _SHARE_STORE *)v24;
    if ( v24 )
    {
      *v24 = v24 + 4;
      memcpy_0(v24 + 4, pvPara, v23);
      *((_QWORD *)v25 + 1) = v12;
      *((_QWORD *)v12 + 15) = v25;
      EnterCriticalSection(&ShareStoreCriticalSection);
      v36 = pShareStoreHead;
      if ( pShareStoreHead )
      {
        *((_QWORD *)v25 + 2) = pShareStoreHead;
        *((_QWORD *)v36 + 3) = v25;
      }
      pShareStoreHead = v25;
      LeaveCriticalSection(&ShareStoreCriticalSection);
    }
  }
  v21 = 0;
LABEL_28:
  v26 = v42;
  if ( v42 )
  {
    if ( v12 )
    {
      v35 = 1;
    }
    else
    {
      v35 = 0;
      if ( v21 )
        v35 = GetLastError() == 0;
    }
    CertDiagOpenStoreEnd(v26, v35);
  }
  return v12;
}

```

## disassembly

```asm
0x1800466a0  mov     [rsp+hCryptProv], r8
0x1800466a5  mov     [rsp+dwEncodingType], edx
0x1800466a9  mov     [rsp+arg_0], rcx
0x1800466ae  push    rbx
0x1800466af  push    rbp
0x1800466b0  push    rsi
0x1800466b1  push    rdi
0x1800466b2  push    r12
0x1800466b4  push    r13
0x1800466b6  push    r14
0x1800466b8  sub     rsp, 60h
0x1800466bc  mov     rbp, [rsp+98h+pvPara]
0x1800466c4  mov     r12d, r9d
0x1800466c7  mov     [rsp+98h+var_58], 0
0x1800466d0  mov     rsi, r8
0x1800466d3  mov     [rsp+98h+arg_18], 0
0x1800466de  mov     rbx, rcx
0x1800466e1  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800466e8  mov     r13d, 1
0x1800466ee  cmp     r9d, 210C0h
0x1800466f5  jz      loc_18004691F
0x1800466fb  mov     edx, 0C0h; uBytes
0x180046700  mov     [rsp+98h+var_40], r15
0x180046705  mov     ecx, 40h ; '@'; uFlags
0x18004670a  call    cs:__imp_LocalAlloc
0x180046710  mov     r15, rax
0x180046713  test    rax, rax
0x180046716  jz      loc_180046C56
0x18004671c  lea     rcx, [rax+18h]
0x180046720  call    Pki_InitializeCriticalSection
0x180046725  test    eax, eax
0x180046727  jz      loc_180046D0B
0x18004672d  mov     rcx, rbx; lpString1
0x180046730  call    CertDiagOpenStoreStart
0x180046735  mov     [rsp+98h+var_50], rax
0x18004673a  mov     dword ptr [r15+98h], 28h ; '('
0x180046745  mov     [r15], r13d
0x180046748  mov     [r15+4], r13d
0x18004674c  mov     dword ptr [r15+14h], 2
0x180046754  mov     [r15+8], rsi
0x180046758  mov     [r15+10h], r12d
0x18004675c  test    r12b, 4
0x180046760  jz      short loc_180046766
0x180046762  mov     [r15+68h], r13d
0x180046766  cmp     rbx, 2
0x18004676a  jz      loc_18004695D
0x180046770  mov     r14, cs:qword_1801582A8
0x180046777  lea     r13, [r15+90h]
0x18004677e  mov     rsi, rbx
0x180046781  cmp     rbx, 0FFFFh
0x180046788  ja      loc_180046AC2
0x18004678e  cmp     dword ptr [r14+30h], 0
0x180046793  jz      loc_180046B77
0x180046799  mov     rcx, [r14+38h]; struct _REG_OID_FUNC_ELEMENT *
0x18004679d  test    rcx, rcx
0x1800467a0  jnz     loc_180046BA3
0x1800467a6  cmp     rsi, 0FFFFh
0x1800467ad  ja      loc_180046AEE
0x1800467b3  mov     rcx, [r14+10h]
0x1800467b7  test    rcx, rcx
0x1800467ba  jz      loc_1800468D0
0x1800467c0  cmp     dword ptr [rcx+4], 0
0x1800467c4  jnz     loc_18004690A
0x1800467ca  mov     rax, [rcx+10h]
0x1800467ce  cmp     rsi, rax
0x1800467d1  jb      loc_18004690A
0x1800467d7  cmp     rsi, [rcx+18h]
0x1800467db  ja      loc_18004690A
0x1800467e1  sub     rsi, rax
0x1800467e4  mov     rax, [rcx+28h]
0x1800467e8  mov     r14, [rax+rsi*8]
0x1800467ec  mov     [r13+0], rcx
0x1800467f0  mov     rsi, [rsp+98h+hCryptProv]
0x1800467f8  lea     rax, [r15+98h]
0x1800467ff  mov     r13d, [rsp+98h+dwEncodingType]
0x180046807  mov     r9d, r12d
0x18004680a  mov     [rsp+98h+var_68], rax
0x18004680f  and     r9d, 0FFFFFFFBh
0x180046813  mov     qword ptr [rsp+98h+cchCount2], r15
0x180046818  mov     rax, r14
0x18004681b  mov     r8, rsi
0x18004681e  mov     [rsp+98h+lpString2], rbp
0x180046823  mov     edx, r13d
0x180046826  mov     rcx, rbx
0x180046829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004682e  test    eax, eax
0x180046830  jz      loc_180046A77
0x180046836  lea     rsi, [r15+0B0h]
0x18004683d  test    byte ptr [rsi], 1
0x180046840  jnz     loc_180046913
0x180046846  bt      r12d, 8
0x18004684b  jb      loc_180046CD0
0x180046851  mov     ebx, r12d
0x180046854  and     ebx, 10h
0x180046857  jnz     loc_180046C7D
0x18004685d  mov     dword ptr [r15+14h], 3
0x180046865  cmp     [rsp+98h+arg_18], ebx
0x18004686c  jz      short loc_1800468A9
0x18004686e  test    rbp, rbp
0x180046871  jz      loc_180046D18
0x180046877  nop     word ptr [rax+rax+00000000h]
0x180046880  inc     rdi
0x180046883  cmp     word ptr [rbp+rdi*2+0], 0
0x180046889  jnz     short loc_180046880
0x18004688b  lea     eax, ds:2[rdi*2]
0x180046892  lea     rcx, [rax+20h]; uBytes
0x180046896  mov     edi, eax
0x180046898  call    PkiZeroAlloc
0x18004689d  mov     rbx, rax
0x1800468a0  test    rax, rax
0x1800468a3  jnz     loc_180046A23
0x1800468a9  xor     ebx, ebx
0x1800468ab  mov     rsi, [rsp+98h+var_50]
0x1800468b0  test    rsi, rsi
0x1800468b3  jnz     loc_1800469F6
0x1800468b9  mov     rax, r15
0x1800468bc  mov     r15, [rsp+98h+var_40]
0x1800468c1  add     rsp, 60h
0x1800468c5  pop     r14
0x1800468c7  pop     r13
0x1800468c9  pop     r12
0x1800468cb  pop     rdi
0x1800468cc  pop     rsi
0x1800468cd  pop     rbp
0x1800468ce  pop     rbx
0x1800468cf  retn
0x1800468d0  mov     rbx, [r14+40h]
0x1800468d4  test    rbx, rbx
0x1800468d7  jz      loc_1800469C5
0x1800468dd  nop     dword ptr [rax]
0x1800468e0  test    rbx, rbx
0x1800468e3  jz      loc_1800469BD
0x1800468e9  cmp     dword ptr [rbx], 0
0x1800468ec  jnz     short loc_180046904
0x1800468ee  mov     rax, [rbx+10h]
0x1800468f2  cmp     rsi, 0FFFFh
0x1800468f9  ja      loc_180046B44
0x1800468ff  cmp     rsi, rax
0x180046902  jz      short loc_18004696C
0x180046904  mov     rbx, [rbx+8]
0x180046908  jmp     short loc_1800468E0
0x18004690a  mov     rcx, [rcx+8]
0x18004690e  jmp     loc_1800467B7
0x180046913  mov     dword ptr [r15], 2
0x18004691a  jmp     loc_180046846
0x18004691f  test    rsi, rsi
0x180046922  jnz     loc_1800466FB
0x180046928  cmp     rbx, 0FFFFh
0x18004692f  ja      loc_180046BC9
0x180046935  cmp     rbx, 0Ah
0x180046939  jnz     loc_1800466FB
0x18004693f  mov     [rsp+98h+arg_18], r13d
0x180046947  mov     rcx, rbp; lpString2
0x18004694a  call    ?FindShareStore@@YAPEAU_CERT_STORE@@PEBG@Z; FindShareStore(ushort const *)
0x18004694f  test    rax, rax
0x180046952  jnz     loc_1800468C1
0x180046958  jmp     loc_1800466FB
0x18004695d  lea     rsi, [r15+0B0h]
0x180046964  or      dword ptr [rsi], 4
0x180046967  jmp     loc_180046851
0x18004696c  mov     rbx, [rbx+18h]
0x180046970  lea     rcx, CriticalSection; lpCriticalSection
0x180046977  call    cs:__imp_EnterCriticalSection
0x18004697d  mov     r14, [rbx+18h]
0x180046981  mov     rsi, [rbx+8]
0x180046985  test    r14, r14
0x180046988  jz      loc_180046C09
0x18004698e  mov     rcx, rsi; struct _DLL_ELEMENT *
0x180046991  call    ?AddRefDll@@YAXPEAU_DLL_ELEMENT@@@Z; AddRefDll(_DLL_ELEMENT *)
0x180046996  lea     rcx, CriticalSection; lpCriticalSection
0x18004699d  call    cs:__imp_LeaveCriticalSection
0x1800469a3  mov     eax, 1
0x1800469a8  mov     [r13+0], rsi
0x1800469ac  test    eax, eax
0x1800469ae  jz      short loc_1800469C5
0x1800469b0  mov     rbx, [rsp+98h+arg_0]
0x1800469b8  jmp     loc_1800467F0
0x1800469bd  mov     qword ptr [r13+0], 0
0x1800469c5  mov     ecx, 2; dwErrCode
0x1800469ca  call    cs:__imp_SetLastError
0x1800469d0  mov     qword ptr [r13+0], 0
0x1800469d8  xor     edx, edx; dwFlags
0x1800469da  mov     rcx, r15; hCertStore
0x1800469dd  call    CertCloseStore
0x1800469e2  xor     r15d, r15d
0x1800469e5  mov     ebx, r12d
0x1800469e8  and     ebx, 10h
0x1800469eb  jz      loc_1800468AB
0x1800469f1  jmp     loc_180046CBB
0x1800469f6  test    r15, r15
0x1800469f9  jz      loc_180046B84
0x1800469ff  mov     edi, 1
0x180046a04  mov     r8, [rsp+98h+arg_0]
0x180046a0c  mov     r9d, r12d
0x180046a0f  mov     edx, edi; __int64
0x180046a11  mov     [rsp+98h+lpString2], rbp
0x180046a16  mov     rcx, rsi; struct _CERT_DIAG_EVENT_STACK_ENTRY *
0x180046a19  call    CertDiagOpenStoreEnd
0x180046a1e  jmp     loc_1800468B9
0x180046a23  lea     rcx, [rax+20h]; void *
0x180046a27  mov     r8, rdi; Size
0x180046a2a  mov     rdx, rbp; Src
0x180046a2d  mov     [rax], rcx
0x180046a30  call    memcpy_0
0x180046a35  mov     [rbx+8], r15
0x180046a39  lea     rcx, ?ShareStoreCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180046a40  mov     [r15+78h], rbx
0x180046a44  call    cs:__imp_EnterCriticalSection
0x180046a4a  mov     rax, cs:?pShareStoreHead@@3PEAU_SHARE_STORE@@EA; _SHARE_STORE * pShareStoreHead
0x180046a51  test    rax, rax
0x180046a54  jz      short loc_180046A5E
0x180046a56  mov     [rbx+10h], rax
0x180046a5a  mov     [rax+18h], rbx
0x180046a5e  lea     rcx, ?ShareStoreCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180046a65  mov     cs:?pShareStoreHead@@3PEAU_SHARE_STORE@@EA, rbx; _SHARE_STORE * pShareStoreHead
0x180046a6c  call    cs:__imp_LeaveCriticalSection
0x180046a72  jmp     loc_1800468A9
0x180046a77  bt      r12d, 0Ch
0x180046a7c  jnb     loc_1800469D8
0x180046a82  xor     edx, edx; dwFlags
0x180046a84  mov     qword ptr [r15+8], 0
0x180046a8c  mov     rcx, r15; hCertStore
0x180046a8f  call    CertCloseStore
0x180046a94  mov     r9d, r12d
0x180046a97  mov     [rsp+98h+lpString2], rbp; pvPara
0x180046a9c  btr     r9d, 0Ch
0x180046aa1  mov     r8, rsi; hCryptProv
0x180046aa4  bts     r9d, 0Fh; dwFlags
0x180046aa9  mov     edx, r13d; dwEncodingType
0x180046aac  mov     rcx, rbx; lpszStoreProvider
0x180046aaf  call    CertOpenStore
0x180046ab4  mov     ebx, r12d
0x180046ab7  mov     r15, rax
0x180046aba  and     ebx, 10h
0x180046abd  jmp     loc_1800468AB
0x180046ac2  cmp     byte ptr [rbx], 23h ; '#'
0x180046ac5  jnz     loc_18004678E
0x180046acb  lea     rcx, [rbx+1]; String
0x180046acf  call    _o_atol_0
0x180046ad4  movsxd  rsi, eax
0x180046ad7  cmp     rsi, 0FFFFh
0x180046ade  jbe     loc_18004678E
0x180046ae4  mov     ecx, 80070057h
0x180046ae9  jmp     loc_1800469CA
0x180046aee  mov     rbx, [r14+20h]
0x180046af2  test    rbx, rbx
0x180046af5  jz      loc_1800468D0
0x180046afb  cmp     dword ptr [rbx+4], 0
0x180046aff  jnz     short loc_180046B29
0x180046b01  mov     rax, [rbx+10h]
0x180046b05  mov     r9d, edi; cchCount1
0x180046b08  mov     [rsp+98h+cchCount2], edi; cchCount2
0x180046b0c  mov     r8, rsi; lpString1
0x180046b0f  mov     edx, 1; dwCmpFlags
0x180046b14  mov     [rsp+98h+lpString2], rax; lpString2
0x180046b19  mov     ecx, 409h; Locale
0x180046b1e  call    cs:__imp_CompareStringA
0x180046b24  cmp     eax, 2
0x180046b27  jz      short loc_180046B2F
0x180046b29  mov     rbx, [rbx+8]
0x180046b2d  jmp     short loc_180046AF2
0x180046b2f  mov     r14, [rbx+20h]
0x180046b33  mov     [r13+0], rbx
0x180046b37  mov     rbx, [rsp+98h+arg_0]
0x180046b3f  jmp     loc_1800467F0
0x180046b44  cmp     rax, 0FFFFh
0x180046b4a  jbe     loc_180046904
0x180046b50  mov     [rsp+98h+cchCount2], edi; cchCount2
0x180046b54  mov     r9d, edi; cchCount1
0x180046b57  mov     r8, rsi; lpString1
0x180046b5a  mov     [rsp+98h+lpString2], rax; lpString2
0x180046b5f  mov     edx, 1; dwCmpFlags
0x180046b64  mov     ecx, 409h; Locale
0x180046b69  call    cs:__imp_CompareStringA
0x180046b6f  cmp     eax, 2
0x180046b72  jmp     loc_180046902
0x180046b77  mov     rcx, r14; pvArg
0x180046b7a  call    ?LoadRegFunc@@YAXPEAU_FUNC_SET@@@Z; LoadRegFunc(_FUNC_SET *)
0x180046b7f  jmp     loc_180046799
0x180046b84  xor     edi, edi
0x180046b86  test    ebx, ebx
0x180046b88  jz      loc_180046A04
0x180046b8e  call    cs:__imp_GetLastError
0x180046b94  test    eax, eax
0x180046b96  mov     eax, 1
0x180046b9b  cmovz   edi, eax
0x180046b9e  jmp     loc_180046A04
0x180046ba3  lea     r9, [rsp+98h+var_58]; void **
0x180046ba8  mov     [rsp+98h+lpString2], r13; void **
0x180046bad  mov     r8, rsi; char *
0x180046bb0  xor     edx, edx; unsigned int
0x180046bb2  call    ?GetRegOIDFunctionAddress@@YAHPEAU_REG_OID_FUNC_ELEMENT@@KPEBDPEAPEAX2@Z; GetRegOIDFunctionAddress(_REG_OID_FUNC_ELEMENT *,ulong,char const *,void * *,void * *)
0x180046bb7  test    eax, eax
0x180046bb9  jz      loc_1800467A6
0x180046bbf  mov     r14, [rsp+98h+var_58]
0x180046bc4  jmp     loc_1800467F0
0x180046bc9  mov     [rsp+98h+cchCount2], edi; cchCount2
0x180046bcd  lea     r8, aSystem; "System"
0x180046bd4  mov     r9d, edi; cchCount1
0x180046bd7  mov     [rsp+98h+lpString2], rbx; lpString2
  ... truncated ...
```
