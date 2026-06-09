# GetRegistryActivePath(_GPOINFO *,int,ushort * *)

- ea: `0x18002243c`
- end: `0x180022bce`
- name: `?GetRegistryActivePath@@YAHPEAU_GPOINFO@@HPEAPEAG@Z`
- size: `1938`
- prototype: `__int64 __fastcall(struct _GPOINFO *, int, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001dd14`
- `0x1800221d4`
- `0x180024d30`
- `0x180070458`
- `0x180075064`
- `0x18009dd2c`

## callees

- `0x180003770`
- `0x18000a504`
- `0x18002243c`
- `0x180022bd4`
- `0x180022c30`
- `0x1800336a0`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002257b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800226ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800226ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002270f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800227b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002280b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022869`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800228a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022a13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022bb9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002257b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800226ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800226ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002270f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800227b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002280b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022869`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800228a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022a13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022bb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800225a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800225b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800225a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800225b5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022522`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022653`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022522`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022653`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002255e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022696`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022722`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800227c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002281a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800228b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002255e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022696`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022722`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800227c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002281a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800228b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800228e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800229aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800228e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800229aa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180022776`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180022776`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022852`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022852`

## string_xrefs

- `0x180022947`: `GetCurrentActiveKey: Failed to read reg key: %s`
- `0x18002297a`: `GetCurrentActiveKey: Failed to read reg key: %s`
- `0x180022b6e`: `GetRegistryActivePath: Failed to build szKey`
- `0x180022b9e`: `GetRegistryActivePath: Failed to build szKey`
- `0x180022b1c`: `GetRegistryActivePath: Failed to get current active bit.`
- `0x180022b4c`: `GetRegistryActivePath: Failed to get current active bit.`
- `0x180022a45`: `GetRegistryActivePath: Failed to build szActivePath`
- `0x180022a6a`: `GetRegistryActivePath: Failed to build szActivePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall GetRegistryActivePath(struct _GPOINFO *a1, int a2, unsigned __int16 **a3)
{
  unsigned __int16 *v5; // rdi
  DWORD LastError; // r14d
  const wchar_t *v7; // rsi
  __int64 v8; // rdx
  const wchar_t *v9; // rax
  __int64 v10; // r9
  const wchar_t *v11; // rax
  unsigned __int64 v12; // r15
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rbx
  int v15; // eax
  unsigned __int16 v16; // si
  int v17; // eax
  DWORD v19; // r15d
  unsigned __int16 *v20; // rbx
  DWORD v21; // esi
  const wchar_t *v22; // r9
  __int64 v23; // rdx
  const wchar_t *v24; // rax
  __int64 v25; // r8
  __int64 v26; // rcx
  const wchar_t *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r13
  unsigned __int16 *v30; // r12
  int v31; // eax
  unsigned __int16 v32; // r13
  int v33; // eax
  void *v34; // rcx
  HKEY v35; // r12
  int v36; // ebx
  DWORD v37; // ecx
  HKEY hKey; // [rsp+68h] [rbp-19h] BYREF
  unsigned __int16 *v39; // [rsp+70h] [rbp-11h] BYREF
  const wchar_t *v40; // [rsp+78h] [rbp-9h]
  unsigned __int16 *v41; // [rsp+80h] [rbp-1h] BYREF
  __int64 v42[10]; // [rsp+88h] [rbp+7h] BYREF
  unsigned __int16 *cbData; // [rsp+E8h] [rbp+67h] BYREF
  int Data; // [rsp+F0h] [rbp+6Fh] BYREF
  unsigned __int16 **v45; // [rsp+F8h] [rbp+77h]
  DWORD dwDisposition; // [rsp+100h] [rbp+7Fh] BYREF

  v45 = a3;
  Data = a2;
  cbData = (unsigned __int16 *)a1;
  v5 = 0;
  v39 = 0;
  LastError = GetLastError();
  if ( !a1 || !a3 )
  {
    v37 = 87;
LABEL_115:
    SetLastError(v37);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v39);
    return 0;
  }
  v40 = L"Machine";
  v7 = L"Machine";
  if ( *((_QWORD *)a1 + 9) )
    v7 = (const wchar_t *)*((_QWORD *)a1 + 9);
  v8 = 0x7FFFFFFF;
  v9 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\DataStore";
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v8;
  }
  while ( v8 );
  v10 = (0x7FFFFFFF - v8) & -(__int64)(v8 != 0);
  if ( !v8 )
    goto LABEL_70;
  v8 = 0x7FFFFFFF;
  v11 = v7;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v8;
  }
  while ( v8 );
  if ( v8 )
  {
    v12 = v10 + ((0x7FFFFFFF - v8) & -(__int64)(v8 != 0)) + 2;
    v13 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v12);
    v14 = v13;
    if ( !v13 )
      goto LABEL_17;
    v15 = StringCchPrintfW(
            v13,
            v12,
            L"%ws\\%ws",
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\DataStore",
            v7);
    v16 = v15;
    if ( v15 >= 0 )
    {
      v5 = v14;
      v39 = v14;
      goto LABEL_21;
    }
    LocalFree(v14);
    v17 = v16;
  }
  else
  {
LABEL_70:
    v17 = v8 == 0 ? 0x57 : 0;
  }
  if ( v17 )
  {
LABEL_17:
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"GetRegistryActivePath: Failed to build szKey");
      }
      else if ( g_lpDebugMsgContextInstance )
      {
        if ( g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"GetRegistryActivePath: Failed to build szKey");
      }
    }
    SetLastError(LastError);
    return 0;
  }
LABEL_21:
  v42[0] = 0;
  v19 = GetLastError();
  v20 = 0;
  v41 = 0;
  v21 = GetLastError();
  if ( (*(_BYTE *)a1 & 1) != 0 )
  {
    v22 = L"Machine";
  }
  else
  {
    v22 = (const wchar_t *)*((_QWORD *)a1 + 9);
    v40 = v22;
    if ( !v22 )
    {
LABEL_35:
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"GetCurrentActiveKey: Failed to build szKey");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"GetCurrentActiveKey: Failed to build szKey");
        }
      }
      SetLastError(v21);
LABEL_37:
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"GetCurrentActiveBit: Failed to get xKey");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"GetCurrentActiveBit: Failed to get xKey");
        }
      }
      SetLastError(v19);
      XKey::Free((XKey *)v42);
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"GetRegistryActivePath: Failed to get current active bit.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"GetRegistryActivePath: Failed to get current active bit.");
        }
      }
      SetLastError(LastError);
      if ( v5 )
        LocalFree(v5);
      return 0;
    }
  }
  v23 = 0x7FFFFFFF;
  v24 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\DataStore";
  do
  {
    if ( !*v24 )
      break;
    ++v24;
    --v23;
  }
  while ( v23 );
  v25 = (0x7FFFFFFF - v23) & -(__int64)(v23 != 0);
  if ( !v23 )
    goto LABEL_72;
  v26 = 0x7FFFFFFF;
  v27 = v22;
  do
  {
    if ( !*v27 )
      break;
    ++v27;
    --v26;
  }
  while ( v26 );
  v28 = (0x7FFFFFFF - v26) & ((unsigned __int128)-(__int128)(unsigned __int64)v26 >> 64);
  if ( v26 )
  {
    v29 = v25 + v28;
    v30 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v25 + v28) + 4);
    if ( !v30 )
      goto LABEL_35;
    v31 = StringCchPrintfW(
            v30,
            v29 + 2,
            L"%ws\\%ws",
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\DataStore",
            v40);
    v32 = v31;
    if ( v31 >= 0 )
    {
      v20 = v30;
      v41 = v30;
      goto LABEL_44;
    }
    LocalFree(v30);
    v33 = v32;
  }
  else
  {
LABEL_72:
    v33 = 87;
  }
  if ( v33 )
    goto LABEL_35;
LABEL_44:
  hKey = 0;
  dwDisposition = 0;
  if ( RegCreateKeyExW(HKEY_LOCAL_MACHINE, v20, 0, 0, 0, 0x20019u, 0, &hKey, &dwDisposition) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"GetCurrentActiveKey: Failed to read reg key: %s", v20);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"GetCurrentActiveKey: Failed to read reg key: %s", v20);
      }
    }
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL
      && (unsigned __int64)(hKey + 0x20000000) > 6
      && hKey != HKEY_PERFORMANCE_TEXT
      && hKey != HKEY_PERFORMANCE_NLSTEXT )
    {
      RegCloseKey(hKey);
    }
    hKey = 0;
    SetLastError(v21);
    if ( v20 )
      LocalFree(v20);
    goto LABEL_37;
  }
  if ( (*(_BYTE *)cbData & 1) != 0 )
    v34 = 0;
  else
    v34 = (void *)*((_QWORD *)cbData + 1);
  if ( !(unsigned int)MakeRegKeySecure(v34, HKEY_LOCAL_MACHINE, v20, 0, 0, 0) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"GetCurrentActiveKey: Failed to secure reg key: %s", v20);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"GetCurrentActiveKey: Failed to secure reg key: %s", v20);
      }
    }
    XKey::Free((XKey *)&hKey);
    SetLastError(v21);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v41);
    goto LABEL_37;
  }
  v35 = hKey;
  hKey = 0;
  SetLastError(v21);
  if ( v20 )
    LocalFree(v20);
  Data = 0;
  LODWORD(cbData) = 4;
  dwDisposition = 0;
  if ( RegQueryValueExW(v35, L"CurrentActiveBit", 0, &dwDisposition, (LPBYTE)&Data, (LPDWORD)&cbData) )
  {
    v36 = 0;
    Data = 0;
  }
  else
  {
    v36 = Data;
  }
  SetLastError(v19);
  if ( (unsigned __int64)(v35 + 0x20000000) > 6
    && v35
    && v35 != HKEY_PERFORMANCE_TEXT
    && v35 != HKEY_PERFORMANCE_NLSTEXT
    && v35 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    RegCloseKey(v35);
  }
  cbData = 0;
  if ( !(unsigned int)BuildActivePath(v5, v36, &cbData) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"GetRegistryActivePath: Failed to build szActivePath");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"GetRegistryActivePath: Failed to build szActivePath");
      }
    }
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&cbData);
    v37 = LastError;
    goto LABEL_115;
  }
  *v45 = cbData;
  SetLastError(LastError);
  if ( v5 )
    LocalFree(v5);
  return 1;
}

```

## disassembly

```asm
0x18002243c  mov     rax, rsp
0x18002243f  mov     [rax+18h], r8
0x180022443  mov     [rax+10h], edx
0x180022446  mov     [rax+8], rcx
0x18002244a  push    rbp
0x18002244b  push    rbx
0x18002244c  push    rsi
0x18002244d  push    rdi
0x18002244e  push    r12
0x180022450  push    r13
0x180022452  push    r14
0x180022454  push    r15
0x180022456  lea     rbp, [rax-5Fh]
0x18002245a  sub     rsp, 98h
0x180022461  mov     rbx, r8
0x180022464  mov     r13, rcx
0x180022467  xor     r15d, r15d
0x18002246a  mov     edi, r15d
0x18002246d  mov     [rbp+57h+var_68], r15
0x180022471  call    cs:__imp_GetLastError
0x180022477  mov     r14d, eax
0x18002247a  mov     [rbp+57h+var_80], eax
0x18002247d  test    r13, r13
0x180022480  jz      loc_180022BB4
0x180022486  test    rbx, rbx
0x180022489  jz      loc_180022BB4
0x18002248f  lea     rax, aMachine; "Machine"
0x180022496  mov     [rbp+57h+var_60], rax
0x18002249a  mov     rsi, rax
0x18002249d  cmp     [r13+48h], r15
0x1800224a1  cmovnz  rsi, [r13+48h]
0x1800224a6  mov     r12d, 7FFFFFFFh
0x1800224ac  mov     edx, r12d
0x1800224af  lea     rax, aSoftwareMicros_11; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800224b6  cmp     [rax], r15w
0x1800224ba  jz      short loc_1800224C6
0x1800224bc  add     rax, 2
0x1800224c0  sub     rdx, 1
0x1800224c4  jnz     short loc_1800224B6
0x1800224c6  mov     rax, rdx
0x1800224c9  mov     rcx, r12
0x1800224cc  sub     rcx, rdx
0x1800224cf  neg     rax
0x1800224d2  sbb     r9, r9
0x1800224d5  and     r9, rcx
0x1800224d8  test    rdx, rdx
0x1800224db  jz      loc_180022906
0x1800224e1  mov     rdx, r12
0x1800224e4  mov     rax, rsi
0x1800224e7  cmp     [rax], r15w
0x1800224eb  jz      short loc_1800224F7
0x1800224ed  add     rax, 2
0x1800224f1  sub     rdx, 1
0x1800224f5  jnz     short loc_1800224E7
0x1800224f7  mov     rax, rdx
0x1800224fa  mov     rcx, r12
0x1800224fd  sub     rcx, rdx
0x180022500  neg     rax
0x180022503  sbb     r8, r8
0x180022506  and     r8, rcx
0x180022509  test    rdx, rdx
0x18002250c  jz      loc_180022906
0x180022512  lea     r15, [r8+2]
0x180022516  add     r15, r9
0x180022519  lea     rdx, [r15+r15]; uBytes
0x18002251d  mov     ecx, 40h ; '@'; uFlags
0x180022522  call    cs:__imp_LocalAlloc
0x180022528  mov     rbx, rax
0x18002252b  test    rax, rax
0x18002252e  jz      loc_1800228F6
0x180022534  mov     qword ptr [rsp+0D0h+dwOptions], rsi
0x180022539  lea     r9, aSoftwareMicros_11; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180022540  lea     r8, aWsWs_0; "%ws\\%ws"
0x180022547  mov     rdx, r15; unsigned __int64
0x18002254a  mov     rcx, rax; unsigned __int16 *
0x18002254d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022552  mov     esi, eax
0x180022554  xor     r15d, r15d
0x180022557  test    eax, eax
0x180022559  jns     short loc_180022598
0x18002255b  mov     rcx, rbx; hMem
0x18002255e  call    cs:__imp_LocalFree
0x180022564  movzx   eax, si
0x180022567  test    eax, eax
0x180022569  jz      short loc_18002259F
0x18002256b  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180022572  jnz     loc_180022B62
0x180022578  mov     ecx, r14d; dwErrCode
0x18002257b  call    cs:__imp_SetLastError
0x180022581  nop
0x180022582  xor     eax, eax
0x180022584  add     rsp, 98h
0x18002258b  pop     r15
0x18002258d  pop     r14
0x18002258f  pop     r13
0x180022591  pop     r12
0x180022593  pop     rdi
0x180022594  pop     rsi
0x180022595  pop     rbx
0x180022596  pop     rbp
0x180022597  retn
0x180022598  mov     rdi, rbx
0x18002259b  mov     [rbp+57h+var_68], rbx
0x18002259f  mov     [rbp+57h+var_50], r15
0x1800225a3  call    cs:__imp_GetLastError
0x1800225a9  mov     r15d, eax
0x1800225ac  mov     [rbp+57h+var_7C], eax
0x1800225af  xor     ebx, ebx
0x1800225b1  mov     [rbp+57h+var_58], rbx
0x1800225b5  call    cs:__imp_GetLastError
0x1800225bb  mov     esi, eax
0x1800225bd  mov     [rbp+57h+var_78], eax
0x1800225c0  test    byte ptr [r13+0], 1
0x1800225c5  jnz     loc_180022915
0x1800225cb  mov     r9, [r13+48h]
0x1800225cf  mov     [rbp+57h+var_60], r9
0x1800225d3  xor     r13d, r13d
0x1800225d6  test    r9, r9
0x1800225d9  jz      loc_1800226AB
0x1800225df  mov     rdx, r12
0x1800225e2  lea     rax, aSoftwareMicros_11; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800225e9  cmp     [rax], r13w
0x1800225ed  jz      short loc_1800225F9
0x1800225ef  add     rax, 2
0x1800225f3  sub     rdx, 1
0x1800225f7  jnz     short loc_1800225E9
0x1800225f9  mov     rax, rdx
0x1800225fc  mov     rcx, r12
0x1800225ff  sub     rcx, rdx
0x180022602  neg     rax
0x180022605  sbb     r8, r8
0x180022608  and     r8, rcx
0x18002260b  test    rdx, rdx
0x18002260e  jz      loc_180022924
0x180022614  mov     rcx, r12
0x180022617  mov     rax, r9
0x18002261a  cmp     [rax], r13w
0x18002261e  jz      short loc_18002262A
0x180022620  add     rax, 2
0x180022624  sub     rcx, 1
0x180022628  jnz     short loc_18002261A
0x18002262a  mov     rax, rcx
0x18002262d  sub     r12, rcx
0x180022630  neg     rax
0x180022633  sbb     rdx, rdx
0x180022636  and     rdx, r12
0x180022639  test    rcx, rcx
0x18002263c  jz      loc_180022929
0x180022642  lea     r13, [r8+rdx]
0x180022646  lea     rdx, ds:4[r13*2]; uBytes
0x18002264e  mov     ecx, 40h ; '@'; uFlags
0x180022653  call    cs:__imp_LocalAlloc
0x180022659  mov     r12, rax
0x18002265c  test    rax, rax
0x18002265f  jz      loc_1800228FE
0x180022665  mov     rax, [rbp+57h+var_60]
0x180022669  mov     qword ptr [rsp+0D0h+dwOptions], rax
0x18002266e  lea     r9, aSoftwareMicros_11; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180022675  lea     r8, aWsWs_0; "%ws\\%ws"
0x18002267c  lea     rdx, [r13+2]; unsigned __int64
0x180022680  mov     rcx, r12; unsigned __int16 *
0x180022683  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022688  mov     r13d, eax
0x18002268b  test    eax, eax
0x18002268d  jns     loc_18002272D
0x180022693  mov     rcx, r12; hMem
0x180022696  call    cs:__imp_LocalFree
0x18002269c  movzx   eax, r13w
0x1800226a0  xor     r13d, r13d
0x1800226a3  test    eax, eax
0x1800226a5  jz      loc_180022737
0x1800226ab  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800226b2  jnz     loc_180022A8E
0x1800226b8  mov     ecx, esi; dwErrCode
0x1800226ba  call    cs:__imp_SetLastError
0x1800226c0  nop
0x1800226c1  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800226c8  jz      short loc_1800226EC
0x1800226ca  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800226d1  test    rax, rax
0x1800226d4  jz      loc_180022AE0
0x1800226da  lea     rdx, aGetcurrentacti_1; "GetCurrentActiveBit: Failed to get xKey"
0x1800226e1  mov     ecx, 2
0x1800226e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226eb  nop
0x1800226ec  mov     ecx, r15d; dwErrCode
0x1800226ef  call    cs:__imp_SetLastError
0x1800226f5  nop
0x1800226f6  lea     rcx, [rbp+57h+var_50]; this
0x1800226fa  call    ?Free@XKey@@QEAAXXZ; XKey::Free(void)
0x1800226ff  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180022706  jnz     loc_180022B10
0x18002270c  mov     ecx, r14d; dwErrCode
0x18002270f  call    cs:__imp_SetLastError
0x180022715  nop
0x180022716  test    rdi, rdi
0x180022719  jz      loc_180022582
0x18002271f  mov     rcx, rdi; hMem
0x180022722  call    cs:__imp_LocalFree
0x180022728  jmp     loc_180022582
0x18002272d  mov     rbx, r12
0x180022730  mov     [rbp+57h+var_58], rbx
0x180022734  xor     r13d, r13d
0x180022737  mov     [rbp+57h+hKey], r13
0x18002273b  mov     [rbp+57h+dwDisposition], r13d
0x18002273f  lea     rax, [rbp+57h+dwDisposition]
0x180022743  mov     [rsp+40h], rax; lpdwDisposition
0x180022748  lea     rax, [rbp+57h+hKey]
0x18002274c  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180022751  mov     [rsp+0D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180022756  mov     [rsp+0D0h+samDesired], 20019h; samDesired
0x18002275e  mov     [rsp+0D0h+dwOptions], r13d; dwOptions
0x180022763  xor     r9d, r9d; lpClass
0x180022766  xor     r8d, r8d; Reserved
0x180022769  mov     rdx, rbx; lpSubKey
0x18002276c  mov     r12, 0FFFFFFFF80000002h
0x180022773  mov     rcx, r12; hKey
0x180022776  call    cs:__imp_RegCreateKeyExW
0x18002277c  test    eax, eax
0x18002277e  jz      short loc_1800227D1
0x180022780  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180022787  jnz     loc_180022938
0x18002278d  mov     rcx, [rbp+57h+hKey]; hKey
0x180022791  lea     rax, [rcx-1]
0x180022795  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180022799  ja      short loc_1800227AD
0x18002279b  mov     eax, 80000000h
0x1800227a0  add     rax, rcx
0x1800227a3  cmp     rax, 6
0x1800227a7  ja      loc_180022990
0x1800227ad  mov     [rbp+57h+hKey], r13
0x1800227b1  mov     ecx, esi; dwErrCode
0x1800227b3  call    cs:__imp_SetLastError
0x1800227b9  nop
0x1800227ba  test    rbx, rbx
0x1800227bd  jz      loc_1800226C1
0x1800227c3  mov     rcx, rbx; hMem
0x1800227c6  call    cs:__imp_LocalFree
0x1800227cc  jmp     loc_1800226C1
0x1800227d1  mov     rcx, [rbp+57h+cbData]
0x1800227d5  test    byte ptr [rcx], 1
0x1800227d8  jz      loc_1800228ED
0x1800227de  mov     rcx, r13; void *
0x1800227e1  mov     [rsp+0D0h+samDesired], r13d; int
0x1800227e6  mov     [rsp+0D0h+dwOptions], r13d; int
0x1800227eb  xor     r9d, r9d; int
0x1800227ee  mov     r8, rbx; unsigned __int16 *
0x1800227f1  mov     rdx, r12; HKEY
0x1800227f4  call    ?MakeRegKeySecure@@YAHPEAXPEAUHKEY__@@PEBGHHH@Z; MakeRegKeySecure(void *,HKEY__ *,ushort const *,int,int,int)
0x1800227f9  test    eax, eax
0x1800227fb  jz      loc_1800229B5
0x180022801  mov     r12, [rbp+57h+hKey]
0x180022805  mov     [rbp+57h+hKey], r13
0x180022809  mov     ecx, esi; dwErrCode
0x18002280b  call    cs:__imp_SetLastError
0x180022811  nop
0x180022812  test    rbx, rbx
0x180022815  jz      short loc_180022820
0x180022817  mov     rcx, rbx; hMem
0x18002281a  call    cs:__imp_LocalFree
0x180022820  mov     [rbp+57h+Data], r13d
0x180022824  mov     dword ptr [rbp+57h+cbData], 4
0x18002282b  mov     [rbp+57h+dwDisposition], r13d
0x18002282f  lea     rax, [rbp+57h+cbData]
0x180022833  mov     qword ptr [rsp+0D0h+samDesired], rax; lpcbData
0x180022838  lea     rax, [rbp+57h+Data]
0x18002283c  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x180022841  lea     r9, [rbp+57h+dwDisposition]; lpType
0x180022845  xor     r8d, r8d; lpReserved
0x180022848  lea     rdx, aCurrentactiveb; "CurrentActiveBit"
0x18002284f  mov     rcx, r12; hKey
0x180022852  call    cs:__imp_RegQueryValueExW
0x180022858  test    eax, eax
0x18002285a  jz      loc_180022A28
0x180022860  mov     ebx, r13d
0x180022863  mov     [rbp+57h+Data], ebx
0x180022866  mov     ecx, r15d; dwErrCode
0x180022869  call    cs:__imp_SetLastError
0x18002286f  nop
0x180022870  mov     eax, 80000000h
0x180022875  add     rax, r12
0x180022878  cmp     rax, 6
0x18002287c  ja      short loc_1800228C5
0x18002287e  mov     [rbp+57h+cbData], r13
0x180022882  lea     r8, [rbp+57h+cbData]; unsigned __int16 **
0x180022886  mov     edx, ebx; unsigned int
0x180022888  mov     rcx, rdi; unsigned __int16 *
0x18002288b  call    ?BuildActivePath@@YAHPEBGKPEAPEAG@Z; BuildActivePath(ushort const *,ulong,ushort * *)
0x180022890  test    eax, eax
0x180022892  jz      loc_180022A30
0x180022898  mov     rcx, [rbp+57h+cbData]
0x18002289c  mov     rdx, [rbp+57h+arg_10]
0x1800228a0  mov     [rdx], rcx
0x1800228a3  mov     ecx, r14d; dwErrCode
0x1800228a6  call    cs:__imp_SetLastError
0x1800228ac  nop
0x1800228ad  test    rdi, rdi
0x1800228b0  jz      short loc_1800228BB
0x1800228b2  mov     rcx, rdi; hMem
0x1800228b5  call    cs:__imp_LocalFree
  ... truncated ...
```
