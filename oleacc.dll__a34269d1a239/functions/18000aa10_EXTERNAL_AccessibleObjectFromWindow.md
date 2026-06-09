# EXTERNAL_AccessibleObjectFromWindow

- ea: `0x18000aa10`
- end: `0x18000b2af`
- name: `EXTERNAL_AccessibleObjectFromWindow`
- size: `2207`
- prototype: `HRESULT __stdcall(HWND hwnd, DWORD dwId, const IID *const riid, void **ppvObject)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180007700`
- `0x1800093c0`
- `0x1800097e0`
- `0x18000aa10`
- `0x18000b2c0`
- `0x18001e4c0`
- `0x180047fec`
- `0x180047ff8`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000b16a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000b16a`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000afc2`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000b045`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000afc2`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000b045`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000afdc`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000b069`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000afdc`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000b069`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b10b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b1b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b10b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b1b3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000b1a8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000b1a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b17c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b17c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ab04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000af98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000aff5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b127`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ab04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000af98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000aff5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b127`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aa94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aa94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b100`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b100`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000b077`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000b077`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ac86`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b01a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ac86`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b01a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000b26d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000b280`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000b26d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000b280`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000b0ac`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000b0ac`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000b08c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000b08c`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x18000ab3e`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x18000ab3e`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18000af8f`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18000af8f`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x18000b0e4`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x18000b0e4`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000b0c8`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000b0c8`
- `USER32!EnumWindows` at `0x18000b23e`
- `USER32!EnumWindows` at `0x18000b23e`
- `USER32!SendMessageTimeoutW` at `0x18000aacc`
- `USER32!SendMessageTimeoutW` at `0x18000aacc`
- `USER32!GetWindowThreadProcessId` at `0x18000aa8c`
- `USER32!GetWindowThreadProcessId` at `0x18000aa8c`
- `USER32!IsWindow` at `0x18000aa78`
- `USER32!IsWindow` at `0x18000aa78`

## pseudocode

```c
HRESULT __stdcall EXTERNAL_AccessibleObjectFromWindow(HWND hwnd, DWORD dwId, const IID *const riid, void **ppvObject)
{
  const IID *v5; // r15
  LPARAM v6; // r13
  WPARAM CurrentProcessId; // r15
  DWORD WindowThreadProcessId; // ebx
  int StdAccessibleObject_0; // edi
  bool v11; // zf
  int v12; // eax
  char *v13; // rdx
  DWORD v14; // esi
  int v15; // r8d
  int v16; // esi
  int v17; // esi
  HANDLE ProcessHandleFromHwnd; // rdi
  struct IUnknown *v19; // rbx
  _DWORD *v20; // rax
  _DWORD *v21; // rdi
  int v22; // esi
  HANDLE v24; // rbx
  char *v25; // rdx
  int v26; // ecx
  int v27; // r8d
  int v28; // ebx
  int v29; // ebx
  __int16 *v30; // rdx
  int i; // ecx
  __int16 v32; // r8
  __int16 *v33; // r8
  int j; // ecx
  __int16 v35; // dx
  int (__fastcall ***v36)(void *, GUID *, HANDLE *); // rsi
  int v37; // ebx
  int (__fastcall **v38)(void *, GUID *, HANDLE *); // rax
  int *v39; // rax
  int v40; // ebx
  int v41; // esi
  SIZE_T v42; // rdi
  size_t v43; // rbx
  HLOCAL v44; // rdi
  char *v45; // rax
  const void *v46; // rsi
  HGLOBAL v47; // rax
  void *v48; // rsi
  void *v49; // rax
  HRESULT v50; // ebx
  HANDLE CurrentProcess; // rax
  BOOL v52; // ebx
  HANDLE hFileMappingObject; // [rsp+40h] [rbp-89h] BYREF
  LPSTREAM ppstm; // [rsp+48h] [rbp-81h] BYREF
  ULONG_PTR dwResult; // [rsp+50h] [rbp-79h] BYREF
  IID *riida; // [rsp+58h] [rbp-71h]
  LPARAM lParam; // [rsp+60h] [rbp-69h] BYREF
  __int64 v58; // [rsp+68h] [rbp-61h]
  WCHAR Buffer[5]; // [rsp+70h] [rbp-59h] BYREF
  char v60; // [rsp+7Ah] [rbp-4Fh] BYREF
  __int16 v61; // [rsp+8Ah] [rbp-3Fh]
  char v62; // [rsp+8Ch] [rbp-3Dh] BYREF
  __int16 v63; // [rsp+9Ch] [rbp-2Dh]
  char v64; // [rsp+9Eh] [rbp-2Bh] BYREF
  __int16 v65; // [rsp+AEh] [rbp-1Bh]
  char v66; // [rsp+B0h] [rbp-19h] BYREF
  __int16 v67; // [rsp+C0h] [rbp-9h]
  __int16 v68; // [rsp+C2h] [rbp-7h]

  v5 = riid;
  riida = (IID *)riid;
  v6 = dwId;
  if ( !g_fInitedOleacc )
    InitOleacc();
  if ( !ppvObject )
  {
    StdAccessibleObject_0 = -2147024809;
    goto LABEL_35;
  }
  CurrentProcessId = 0;
  *ppvObject = 0;
  dwResult = 0;
  if ( IsWindow(hwnd) )
  {
    WindowThreadProcessId = GetWindowThreadProcessId(hwnd, 0);
    if ( WindowThreadProcessId == GetCurrentThreadId() )
    {
      CurrentProcessId = 0xFFFFFFFFLL;
    }
    else
    {
      CurrentProcessId = GetCurrentProcessId();
      if ( CurrentProcessId == 0xFFFFFFFF )
        CurrentProcessId = 0;
    }
    SendMessageTimeoutW(hwnd, 0x3Du, CurrentProcessId, v6, 2u, 0x2710u, &dwResult);
  }
  StdAccessibleObject_0 = dwResult;
  v11 = (_DWORD)dwResult == 0;
  if ( (dwResult & 0x80000000) == 0LL )
  {
    if ( !dwResult )
      goto LABEL_91;
    *ppvObject = 0;
    if ( StdAccessibleObject_0 < 0 )
    {
      StdAccessibleObject_0 = -2147024809;
      goto LABEL_31;
    }
    if ( CurrentProcessId == 0xFFFFFFFF )
      ppstm = (LPSTREAM)GetCurrentProcessId();
    else
      ppstm = (LPSTREAM)CurrentProcessId;
    hFileMappingObject = 0;
    if ( HIWORD(StdAccessibleObject_0) )
      goto LABEL_30;
    if ( !(_WORD)StdAccessibleObject_0 )
      goto LABEL_30;
    if ( GlobalGetAtomNameW(StdAccessibleObject_0, Buffer, 42) != 41 )
      goto LABEL_30;
    v12 = memcmp_0(Buffer, L"MSAA:", 0xAu);
    if ( v12 || v61 != 58 || v63 != 58 || v65 != 58 || v67 != 58 || v68 )
      goto LABEL_30;
    v13 = &v60;
    v14 = 0;
    while ( v12 < 8 )
    {
      v15 = *(unsigned __int16 *)v13;
      v16 = 16 * v14;
      if ( (unsigned __int16)(v15 - 48) <= 9u )
      {
        v17 = v16 - 48;
        goto LABEL_26;
      }
      if ( (unsigned __int16)(v15 - 65) > 5u )
      {
        if ( (unsigned __int16)(v15 - 97) > 5u )
          goto LABEL_30;
        v17 = v16 - 87;
LABEL_26:
        v14 = v15 + v17;
        ++v12;
        v13 += 2;
      }
      else
      {
        ++v12;
        v14 = v15 + v16 - 55;
        v13 += 2;
      }
    }
    LODWORD(v24) = 0;
    v25 = &v62;
    v26 = 0;
    while ( 1 )
    {
      if ( v26 >= 8 )
      {
        v30 = (__int16 *)&v64;
        for ( i = 0; i < 8; ++i )
        {
          v32 = *v30;
          if ( (unsigned __int16)(*v30 - 48) > 9u
            && (unsigned __int16)(v32 - 65) > 5u
            && (unsigned __int16)(v32 - 97) > 5u )
          {
            goto LABEL_30;
          }
          ++v30;
        }
        v33 = (__int16 *)&v66;
        for ( j = 0; j < 8; ++j )
        {
          v35 = *v33;
          if ( (unsigned __int16)(*v33 - 48) > 9u
            && (unsigned __int16)(v35 - 65) > 5u
            && (unsigned __int16)(v35 - 97) > 5u )
          {
            goto LABEL_30;
          }
          ++v33;
        }
        GlobalDeleteAtom(StdAccessibleObject_0);
        v24 = (HANDLE)(int)v24;
        if ( v14 == GetCurrentProcessId() )
        {
          hFileMappingObject = (HANDLE)(int)v24;
          goto LABEL_77;
        }
        ProcessHandleFromHwnd = OpenProcess(0x40u, 0, v14);
        if ( !ProcessHandleFromHwnd )
        {
          lParam = v14;
          v58 = 0;
          EnumWindows(FindWindowFromProcessEnumWindowsProc, (LPARAM)&lParam);
          if ( !v58 )
            goto LABEL_30;
          ProcessHandleFromHwnd = (HANDLE)GetProcessHandleFromHwnd(v58);
          if ( !ProcessHandleFromHwnd )
            goto LABEL_30;
        }
        CurrentProcess = GetCurrentProcess();
        v52 = DuplicateHandle(ProcessHandleFromHwnd, (HANDLE)(int)v24, CurrentProcess, &hFileMappingObject, 0, 0, 3u);
        CloseHandle(ProcessHandleFromHwnd);
        if ( !v52 || (v24 = hFileMappingObject) == 0 )
        {
LABEL_30:
          StdAccessibleObject_0 = -2147467259;
          goto LABEL_31;
        }
LABEL_77:
        v39 = (int *)MapViewOfFile(v24, 0xF001Fu, 0, 0, 0x10u);
        if ( !v39 )
          goto LABEL_30;
        v40 = *v39;
        v41 = v39[2];
        v42 = (unsigned int)v39[3];
        UnmapViewOfFile(v39);
        if ( v40 != -1440944115 || (_DWORD)ppstm && v41 != GetCurrentProcessId() )
          goto LABEL_30;
        if ( (unsigned int)v42 > 0x100000 )
        {
          v50 = -2147467259;
        }
        else
        {
          v43 = v42;
          v44 = LocalAlloc(0x40u, v42);
          if ( v44 )
          {
            v45 = (char *)MapViewOfFile(hFileMappingObject, 0xF001Fu, 0, 0, v43 + 16);
            v46 = v45;
            if ( v45 )
            {
              memcpy_0(v44, v45 + 16, v43);
              UnmapViewOfFile(v46);
              v47 = GlobalAlloc(2u, v43);
              v48 = v47;
              if ( v47 )
              {
                v49 = GlobalLock(v47);
                if ( v49 )
                {
                  memcpy_0(v49, v44, v43);
                  GlobalUnlock(v48);
                  ppstm = 0;
                  v50 = CreateStreamOnHGlobal(v48, 1, &ppstm);
                  if ( v50 < 0 )
                  {
                    GlobalFree(v48);
                  }
                  else
                  {
                    v50 = CoUnmarshalInterface(ppstm, riida, ppvObject);
                    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
                  }
                }
                else
                {
                  GlobalFree(v48);
                  v50 = -2147467259;
                }
              }
              else
              {
                v50 = -2147024882;
              }
            }
            else
            {
              v50 = -2147467259;
            }
            LocalFree(v44);
          }
          else
          {
            v50 = -2147024882;
          }
        }
        CloseHandle(hFileMappingObject);
        StdAccessibleObject_0 = v50;
        if ( v50 >= 0 )
        {
LABEL_32:
          v11 = StdAccessibleObject_0 == 0;
          goto LABEL_33;
        }
LABEL_31:
        if ( CurrentProcessId == 0xFFFFFFFF )
          goto LABEL_32;
LABEL_91:
        StdAccessibleObject_0 = 0;
LABEL_34:
        v5 = riida;
        if ( !*ppvObject )
        {
          StdAccessibleObject_0 = CreateStdAccessibleObject_0(hwnd, v6, riida, ppvObject);
          if ( StdAccessibleObject_0 >= 0 )
          {
            v36 = (int (__fastcall ***)(void *, GUID *, HANDLE *))*ppvObject;
            ppstm = 0;
            if ( (**v36)(v36, &GUID_55f9c234_79cd_4699_89e7_5518fd88bcde, (HANDLE *)&ppstm) >= 0 )
            {
              v37 = (*(__int64 (__fastcall **)(LPSTREAM, __int64))(*(_QWORD *)ppstm + 32LL))(ppstm, 458752);
              (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
              if ( v37 >= 0 )
              {
                v38 = *v36;
                hFileMappingObject = 0;
                if ( (*v38)(v36, &GUID_f660d979_a938_423f_b5b9_12e4028c50b0, &hFileMappingObject) >= 0 )
                {
                  if ( (*(int (__fastcall **)(HANDLE, _QWORD))(*(_QWORD *)hFileMappingObject + 32LL))(
                         hFileMappingObject,
                         0) >= 0 )
                    (*(void (__fastcall **)(HANDLE, _QWORD))(*(_QWORD *)hFileMappingObject + 48LL))(
                      hFileMappingObject,
                      0);
                  (*(void (__fastcall **)(HANDLE))(*(_QWORD *)hFileMappingObject + 16LL))(hFileMappingObject);
                }
              }
            }
          }
        }
        goto LABEL_35;
      }
      v27 = *(unsigned __int16 *)v25;
      v28 = 16 * (_DWORD)v24;
      if ( (unsigned __int16)(v27 - 48) <= 9u )
        break;
      if ( (unsigned __int16)(v27 - 65) > 5u )
      {
        if ( (unsigned __int16)(v27 - 97) > 5u )
          goto LABEL_30;
        v29 = v28 - 87;
LABEL_51:
        LODWORD(v24) = v27 + v29;
        ++v26;
        v25 += 2;
      }
      else
      {
        ++v26;
        LODWORD(v24) = v27 + v28 - 55;
        v25 += 2;
      }
    }
    v29 = v28 - 48;
    goto LABEL_51;
  }
LABEL_33:
  if ( v11 )
    goto LABEL_34;
  v5 = riida;
LABEL_35:
  if ( StdAccessibleObject_0 )
    return StdAccessibleObject_0;
  if ( !ppvObject )
    return StdAccessibleObject_0;
  v19 = (struct IUnknown *)*ppvObject;
  if ( !*ppvObject )
    return StdAccessibleObject_0;
  dwResult = 0;
  if ( !((unsigned __int64 (__fastcall *)(struct IUnknown *, GUID *, ULONG_PTR *))v19->lpVtbl->QueryInterface)(
          v19,
          &IID_IAccessible,
          &dwResult)
    && dwResult )
  {
    (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)dwResult + 16LL))(dwResult);
    if ( (unsigned int)AccWrap_Base::AlreadyWrapped(v19) )
    {
      v22 = ((__int64 (__fastcall *)(struct IUnknown *, const IID *, void **))v19->lpVtbl->QueryInterface)(
              v19,
              v5,
              ppvObject);
    }
    else
    {
      v20 = LocalAlloc(0x40u, 0xA8u);
      v21 = v20;
      if ( !v20 )
      {
        StdAccessibleObject_0 = -2147024882;
        goto LABEL_104;
      }
      v20[10] = 1;
      *(_QWORD *)v20 = &AccWrap_Base::`vftable'{for `IAccessible'};
      *((_QWORD *)v20 + 6) = v19;
      *((_QWORD *)v20 + 1) = &AccWrap_Base::`vftable'{for `IOleWindow'};
      *((_QWORD *)v20 + 2) = &AccWrap_Base::`vftable'{for `IEnumVARIANT'};
      *((_QWORD *)v20 + 3) = &AccWrap_Base::`vftable'{for `IAccIdentity'};
      *((_QWORD *)v20 + 4) = &AccWrap_Base::`vftable'{for `IServiceProvider'};
      *((_QWORD *)v20 + 8) = 0;
      *((_QWORD *)v20 + 9) = 0;
      *((_QWORD *)v20 + 10) = 0;
      *((_QWORD *)v20 + 11) = 0;
      *((_QWORD *)v20 + 12) = 0;
      v20[26] = 0;
      *((_QWORD *)v20 + 14) = 0;
      *((struct IUnknown *)v20 + 7) = (struct IUnknown)v19->lpVtbl;
      ((void (__fastcall *)(struct IUnknown *))v19->lpVtbl->AddRef)(v19);
      *((_QWORD *)v21 + 15) = 0;
      *(_QWORD *)v21 = &AccWrap_LocationEtcFix::`vftable'{for `IAccessible'};
      v21[32] = 0;
      *((_QWORD *)v21 + 1) = &AccWrap_LocationEtcFix::`vftable'{for `IOleWindow'};
      v21[34] = 0;
      *((_QWORD *)v21 + 2) = &AccWrap_LocationEtcFix::`vftable'{for `IEnumVARIANT'};
      *((_QWORD *)v21 + 18) = 0;
      *((_QWORD *)v21 + 3) = &AccWrap_LocationEtcFix::`vftable'{for `IAccIdentity'};
      *((_QWORD *)v21 + 4) = &AccWrap_LocationEtcFix::`vftable'{for `IServiceProvider'};
      *((_QWORD *)v21 + 19) = 0;
      *((_QWORD *)v21 + 20) = hwnd;
      v22 = ((__int64 (__fastcall *)(_DWORD *, const IID *, void **))AccWrap_LocationEtcFix::`vftable'{for `IAccessible'})(
              v21,
              v5,
              ppvObject);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v21 + 16LL))(v21);
    }
    StdAccessibleObject_0 = v22;
    if ( v22 >= 0 )
    {
LABEL_44:
      ((void (__fastcall *)(struct IUnknown *))v19->lpVtbl->Release)(v19);
      return StdAccessibleObject_0;
    }
LABEL_104:
    *ppvObject = 0;
    goto LABEL_44;
  }
  return 0;
}

```

## disassembly

```asm
0x18000aa10  push    rbp
0x18000aa12  push    rdi
0x18000aa13  push    r12
0x18000aa15  push    r13
0x18000aa17  push    r14
0x18000aa19  push    r15
0x18000aa1b  lea     rbp, [rsp-2Fh]
0x18000aa20  sub     rsp, 0F8h
0x18000aa27  mov     rax, cs:__security_cookie
0x18000aa2e  xor     rax, rsp
0x18000aa31  mov     [rbp+57h+var_50], rax
0x18000aa35  cmp     cs:?g_fInitedOleacc@@3HA, 0; int g_fInitedOleacc
0x18000aa3c  mov     r14, r9
0x18000aa3f  mov     r15, r8
0x18000aa42  mov     [rbp+57h+riid], r8
0x18000aa46  mov     r13d, edx
0x18000aa49  mov     r12, rcx
0x18000aa4c  jz      loc_18000B1E1
0x18000aa52  mov     [rsp+120h+var_30], rbx
0x18000aa5a  mov     [rsp+120h+var_38], rsi
0x18000aa62  test    r14, r14
0x18000aa65  jz      loc_18000B1EB
0x18000aa6b  xor     r15d, r15d
0x18000aa6e  mov     rcx, r12; hWnd
0x18000aa71  mov     [r14], r15
0x18000aa74  mov     [rbp+57h+dwResult], r15
0x18000aa78  call    cs:__imp_IsWindow
0x18000aa7e  mov     edi, 0FFFFFFFFh
0x18000aa83  test    eax, eax
0x18000aa85  jz      short loc_18000AAD2
0x18000aa87  xor     edx, edx; lpdwProcessId
0x18000aa89  mov     rcx, r12; hWnd
0x18000aa8c  call    cs:__imp_GetWindowThreadProcessId
0x18000aa92  mov     ebx, eax
0x18000aa94  call    cs:__imp_GetCurrentThreadId
0x18000aa9a  cmp     ebx, eax
0x18000aa9c  jnz     loc_18000B127
0x18000aaa2  mov     r15d, edi
0x18000aaa5  lea     rax, [rbp+57h+dwResult]
0x18000aaa9  mov     r9, r13; lParam
0x18000aaac  mov     [rsp+120h+lpdwResult], rax; lpdwResult
0x18000aab1  mov     r8, r15; wParam
0x18000aab4  mov     [rsp+120h+uTimeout], 2710h; uTimeout
0x18000aabc  mov     edx, 3Dh ; '='; Msg
0x18000aac1  mov     rcx, r12; hWnd
0x18000aac4  mov     [rsp+120h+fuFlags], 2; fuFlags
0x18000aacc  call    cs:__imp_SendMessageTimeoutW
0x18000aad2  mov     rdi, [rbp+57h+dwResult]
0x18000aad6  test    edi, edi
0x18000aad8  js      loc_18000ABFA
0x18000aade  test    rdi, rdi
0x18000aae1  jz      loc_18000B120
0x18000aae7  mov     qword ptr [r14], 0
0x18000aaee  test    edi, edi
0x18000aaf0  js      loc_18000B14F
0x18000aaf6  mov     eax, 0FFFFFFFFh
0x18000aafb  cmp     r15, rax
0x18000aafe  jnz     loc_18000B13E
0x18000ab04  call    cs:__imp_GetCurrentProcessId
0x18000ab0a  mov     ecx, eax
0x18000ab0c  mov     [rsp+120h+ppstm], rcx
0x18000ab11  mov     eax, edi
0x18000ab13  mov     [rsp+120h+hFileMappingObject], 0
0x18000ab1c  shr     eax, 10h
0x18000ab1f  test    ax, ax
0x18000ab22  jnz     loc_18000ABE5
0x18000ab28  test    di, di
0x18000ab2b  jz      loc_18000ABE5
0x18000ab31  mov     r8d, 2Ah ; '*'; nSize
0x18000ab37  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x18000ab3b  movzx   ecx, di; nAtom
0x18000ab3e  call    cs:__imp_GlobalGetAtomNameW
0x18000ab44  cmp     eax, 29h ; ')'
0x18000ab47  jnz     loc_18000ABE5
0x18000ab4d  mov     r8d, 0Ah; Size
0x18000ab53  lea     rdx, aMsaa_0; "MSAA:"
0x18000ab5a  lea     rcx, [rbp+57h+Buffer]; Buf1
0x18000ab5e  call    memcmp_0
0x18000ab63  test    eax, eax
0x18000ab65  jnz     short loc_18000ABE5
0x18000ab67  cmp     [rbp+57h+var_96], 3Ah ; ':'
0x18000ab6c  jnz     short loc_18000ABE5
0x18000ab6e  cmp     [rbp+57h+var_84], 3Ah ; ':'
0x18000ab73  jnz     short loc_18000ABE5
0x18000ab75  cmp     [rbp+57h+var_72], 3Ah ; ':'
0x18000ab7a  jnz     short loc_18000ABE5
0x18000ab7c  cmp     [rbp+57h+var_60], 3Ah ; ':'
0x18000ab81  jnz     short loc_18000ABE5
0x18000ab83  cmp     [rbp+57h+var_5E], ax
0x18000ab87  jnz     short loc_18000ABE5
0x18000ab89  lea     rdx, [rbp+57h+var_A6]
0x18000ab8d  xor     esi, esi
0x18000ab8f  nop
0x18000ab90  cmp     eax, 8
0x18000ab93  jge     loc_18000ADDC
0x18000ab99  movzx   r8d, word ptr [rdx]
0x18000ab9d  shl     esi, 4
0x18000aba0  lea     ecx, [r8-30h]
0x18000aba4  cmp     cx, 9
0x18000aba8  ja      short loc_18000ABB8
0x18000abaa  add     esi, 0FFFFFFD0h
0x18000abad  add     esi, r8d
0x18000abb0  inc     eax
0x18000abb2  add     rdx, 2
0x18000abb6  jmp     short loc_18000AB90
0x18000abb8  lea     ecx, [r8-41h]
0x18000abbc  cmp     cx, 5
0x18000abc0  ja      loc_18000B1F5
0x18000abc6  add     esi, 0FFFFFFC9h
0x18000abc9  inc     eax
0x18000abcb  add     esi, r8d
0x18000abce  add     rdx, 2
0x18000abd2  jmp     short loc_18000AB90
0x18000abd4  call    GetProcessHandleFromHwnd
0x18000abd9  mov     rdi, rax
0x18000abdc  test    rax, rax
0x18000abdf  jnz     loc_18000B17C
0x18000abe5  mov     edi, 80004005h
0x18000abea  mov     eax, 0FFFFFFFFh
0x18000abef  cmp     r15, rax
0x18000abf2  jnz     loc_18000B120
0x18000abf8  test    edi, edi
0x18000abfa  jnz     loc_18000B28B
0x18000ac00  cmp     qword ptr [r14], 0
0x18000ac04  mov     r15, [rbp+57h+riid]
0x18000ac08  jz      loc_18000AEA7
0x18000ac0e  test    edi, edi
0x18000ac10  jnz     loc_18000ADA7
0x18000ac16  test    r14, r14
0x18000ac19  jz      loc_18000ADA7
0x18000ac1f  mov     rbx, [r14]
0x18000ac22  test    rbx, rbx
0x18000ac25  jz      loc_18000ADA7
0x18000ac2b  xor     r13d, r13d
0x18000ac2e  lea     r8, [rbp+57h+dwResult]
0x18000ac32  mov     [rbp+57h+dwResult], r13
0x18000ac36  lea     rdx, IID_IAccessible
0x18000ac3d  mov     rax, [rbx]
0x18000ac40  mov     rcx, rbx
0x18000ac43  mov     rax, [rax]
0x18000ac46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac4b  test    eax, eax
0x18000ac4d  jnz     loc_18000ADD7
0x18000ac53  mov     rcx, [rbp+57h+dwResult]
0x18000ac57  test    rcx, rcx
0x18000ac5a  jz      loc_18000ADD7
0x18000ac60  mov     rax, [rcx]
0x18000ac63  mov     rax, [rax+10h]
0x18000ac67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac6c  mov     rcx, rbx; struct IUnknown *
0x18000ac6f  call    ?AlreadyWrapped@AccWrap_Base@@SAHPEAUIUnknown@@@Z; AccWrap_Base::AlreadyWrapped(IUnknown *)
0x18000ac74  test    eax, eax
0x18000ac76  jnz     loc_18000B294
0x18000ac7c  mov     edx, 0A8h; uBytes
0x18000ac81  mov     ecx, 40h ; '@'; uFlags
0x18000ac86  call    cs:__imp_LocalAlloc
0x18000ac8c  mov     rdi, rax
0x18000ac8f  test    rax, rax
0x18000ac92  jz      loc_18000B1D4
0x18000ac98  mov     dword ptr [rdi+28h], 1
0x18000ac9f  lea     rax, ??_7AccWrap_Base@@6BIAccessible@@@; const AccWrap_Base::`vftable'{for `IAccessible'}
0x18000aca6  mov     [rdi], rax
0x18000aca9  mov     rcx, rbx
0x18000acac  mov     [rdi+30h], rbx
0x18000acb0  lea     rax, ??_7AccWrap_Base@@6BIOleWindow@@@; const AccWrap_Base::`vftable'{for `IOleWindow'}
0x18000acb7  mov     [rdi+8], rax
0x18000acbb  lea     rax, ??_7AccWrap_Base@@6BIEnumVARIANT@@@; const AccWrap_Base::`vftable'{for `IEnumVARIANT'}
0x18000acc2  mov     [rdi+10h], rax
0x18000acc6  lea     rax, ??_7AccWrap_Base@@6BIAccIdentity@@@; const AccWrap_Base::`vftable'{for `IAccIdentity'}
0x18000accd  mov     [rdi+18h], rax
0x18000acd1  lea     rax, ??_7AccWrap_Base@@6BIServiceProvider@@@; const AccWrap_Base::`vftable'{for `IServiceProvider'}
0x18000acd8  mov     [rdi+20h], rax
0x18000acdc  mov     [rdi+40h], r13
0x18000ace0  mov     [rdi+48h], r13
0x18000ace4  mov     [rdi+50h], r13
0x18000ace8  mov     [rdi+58h], r13
0x18000acec  mov     [rdi+60h], r13
0x18000acf0  mov     [rdi+68h], r13d
0x18000acf4  mov     [rdi+70h], r13
0x18000acf8  mov     rax, [rbx]
0x18000acfb  mov     [rdi+38h], rax
0x18000acff  mov     rax, [rbx]
0x18000ad02  mov     rax, [rax+8]
0x18000ad06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad0b  lea     rax, ??_7AccWrap_LocationEtcFix@@6BIAccessible@@@; const AccWrap_LocationEtcFix::`vftable'{for `IAccessible'}
0x18000ad12  mov     [rdi+78h], r13
0x18000ad16  mov     [rdi], rax
0x18000ad19  mov     r8, r14
0x18000ad1c  lea     rax, ??_7AccWrap_LocationEtcFix@@6BIOleWindow@@@; const AccWrap_LocationEtcFix::`vftable'{for `IOleWindow'}
0x18000ad23  mov     [rdi+80h], r13d
0x18000ad2a  mov     [rdi+8], rax
0x18000ad2e  mov     rdx, r15
0x18000ad31  lea     rax, ??_7AccWrap_LocationEtcFix@@6BIEnumVARIANT@@@; const AccWrap_LocationEtcFix::`vftable'{for `IEnumVARIANT'}
0x18000ad38  mov     [rdi+88h], r13d
0x18000ad3f  mov     [rdi+10h], rax
0x18000ad43  mov     rcx, rdi
0x18000ad46  lea     rax, ??_7AccWrap_LocationEtcFix@@6BIAccIdentity@@@; const AccWrap_LocationEtcFix::`vftable'{for `IAccIdentity'}
0x18000ad4d  mov     [rdi+90h], r13
0x18000ad54  mov     [rdi+18h], rax
0x18000ad58  lea     rax, ??_7AccWrap_LocationEtcFix@@6BIServiceProvider@@@; const AccWrap_LocationEtcFix::`vftable'{for `IServiceProvider'}
0x18000ad5f  mov     [rdi+20h], rax
0x18000ad63  mov     [rdi+98h], r13
0x18000ad6a  mov     [rdi+0A0h], r12
0x18000ad71  mov     rax, cs:??_7AccWrap_LocationEtcFix@@6BIAccessible@@@; const AccWrap_LocationEtcFix::`vftable'{for `IAccessible'}
0x18000ad78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad7d  mov     esi, eax
0x18000ad7f  mov     rcx, rdi
0x18000ad82  mov     rax, [rdi]
0x18000ad85  mov     rax, [rax+10h]
0x18000ad89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad8e  mov     edi, esi
0x18000ad90  test    esi, esi
0x18000ad92  js      loc_18000B1D9
0x18000ad98  mov     rax, [rbx]
0x18000ad9b  mov     rcx, rbx
0x18000ad9e  mov     rax, [rax+10h]
0x18000ada2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ada7  mov     eax, edi
0x18000ada9  mov     rsi, [rsp+120h+var_38]
0x18000adb1  mov     rbx, [rsp+120h+var_30]
0x18000adb9  mov     rcx, [rbp+57h+var_50]
0x18000adbd  xor     rcx, rsp; StackCookie
0x18000adc0  call    __security_check_cookie
0x18000adc5  add     rsp, 0F8h
0x18000adcc  pop     r15
0x18000adce  pop     r14
0x18000add0  pop     r13
0x18000add2  pop     r12
0x18000add4  pop     rdi
0x18000add5  pop     rbp
0x18000add6  retn
0x18000add7  mov     eax, r13d
0x18000adda  jmp     short loc_18000ADA9
0x18000addc  xor     ebx, ebx
0x18000adde  lea     rdx, [rbp+57h+var_94]
0x18000ade2  xor     ecx, ecx
0x18000ade4  cmp     ecx, 8
0x18000ade7  jge     short loc_18000AE24
0x18000ade9  movzx   r8d, word ptr [rdx]
0x18000aded  shl     ebx, 4
0x18000adf0  lea     eax, [r8-30h]
0x18000adf4  cmp     ax, 9
0x18000adf8  ja      short loc_18000AE08
0x18000adfa  add     ebx, 0FFFFFFD0h
0x18000adfd  add     ebx, r8d
0x18000ae00  inc     ecx
0x18000ae02  add     rdx, 2
0x18000ae06  jmp     short loc_18000ADE4
0x18000ae08  lea     eax, [r8-41h]
0x18000ae0c  cmp     ax, 5
0x18000ae10  ja      loc_18000B20B
0x18000ae16  add     ebx, 0FFFFFFC9h
0x18000ae19  inc     ecx
0x18000ae1b  add     ebx, r8d
0x18000ae1e  add     rdx, 2
0x18000ae22  jmp     short loc_18000ADE4
0x18000ae24  lea     rdx, [rbp+57h+var_82]
0x18000ae28  xor     ecx, ecx
0x18000ae2a  nop     word ptr [rax+rax+00h]
0x18000ae30  cmp     ecx, 8
0x18000ae33  jge     short loc_18000AE67
0x18000ae35  movzx   r8d, word ptr [rdx]
0x18000ae39  lea     eax, [r8-30h]
0x18000ae3d  cmp     ax, 9
0x18000ae41  ja      short loc_18000AE4B
0x18000ae43  inc     ecx
0x18000ae45  add     rdx, 2
0x18000ae49  jmp     short loc_18000AE30
0x18000ae4b  lea     eax, [r8-41h]
0x18000ae4f  cmp     ax, 5
0x18000ae53  jbe     short loc_18000AE43
0x18000ae55  sub     r8w, 61h ; 'a'
0x18000ae5a  cmp     r8w, 5
0x18000ae5f  ja      loc_18000ABE5
0x18000ae65  jmp     short loc_18000AE43
0x18000ae67  lea     r8, [rbp+57h+var_70]
0x18000ae6b  xor     ecx, ecx
0x18000ae6d  nop     dword ptr [rax]
0x18000ae70  cmp     ecx, 8
0x18000ae73  jge     loc_18000AF8C
0x18000ae79  movzx   edx, word ptr [r8]
0x18000ae7d  lea     eax, [rdx-30h]
0x18000ae80  cmp     ax, 9
0x18000ae84  ja      short loc_18000AE8E
0x18000ae86  inc     ecx
0x18000ae88  add     r8, 2
0x18000ae8c  jmp     short loc_18000AE70
0x18000ae8e  lea     eax, [rdx-41h]
0x18000ae91  cmp     ax, 5
0x18000ae95  jbe     short loc_18000AE86
0x18000ae97  sub     dx, 61h ; 'a'
0x18000ae9b  cmp     dx, 5
0x18000ae9f  ja      loc_18000ABE5
0x18000aea5  jmp     short loc_18000AE86
0x18000aea7  mov     r9, r14; ppvObject
0x18000aeaa  mov     r8, r15; riid
0x18000aead  mov     edx, r13d; idObject
0x18000aeb0  mov     rcx, r12; hwnd
0x18000aeb3  call    CreateStdAccessibleObject_0
0x18000aeb8  mov     edi, eax
  ... truncated ...
```
