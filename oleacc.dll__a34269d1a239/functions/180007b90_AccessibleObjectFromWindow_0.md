# AccessibleObjectFromWindow_0

- ea: `0x180007b90`
- end: `0x180008472`
- name: `AccessibleObjectFromWindow_0`
- size: `2274`
- prototype: `HRESULT __stdcall(HWND hwnd, DWORD dwId, const IID *const riid, void **ppvObject)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800079d0`
- `0x180045fe8`

## callees

- `0x180007700`
- `0x180007b90`
- `0x1800097e0`
- `0x18001e4c0`
- `0x180047fec`
- `0x180047ff8`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008352`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008352`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180008172`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800081f5`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180008172`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800081f5`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000818c`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180008219`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000818c`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180008219`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000839b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000839b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180008390`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180008390`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008364`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008364`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007c66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008148`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800081a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800082d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007c66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008148`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800081a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800082d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007bf6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007bf6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800082b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800082b0`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180008227`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180008227`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007e41`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800081ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007e41`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800081ca`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000844b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000845e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000844b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000845e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000825c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000825c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000823c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000823c`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x180007ca0`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x180007ca0`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18000813f`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18000813f`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x180008294`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x180008294`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180008278`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180008278`
- `USER32!EnumWindows` at `0x18000841c`
- `USER32!EnumWindows` at `0x18000841c`
- `USER32!SendMessageTimeoutW` at `0x180007c2e`
- `USER32!SendMessageTimeoutW` at `0x180007c2e`
- `USER32!GetWindowThreadProcessId` at `0x180007bee`
- `USER32!GetWindowThreadProcessId` at `0x180007bee`
- `USER32!IsWindow` at `0x180007bda`
- `USER32!IsWindow` at `0x180007bda`

## pseudocode

```c
HRESULT __stdcall AccessibleObjectFromWindow_0(HWND hwnd, DWORD dwId, const IID *const riid, void **ppvObject)
{
  LPARAM v5; // r13
  const IID *v6; // r15
  WPARAM CurrentProcessId; // r15
  DWORD WindowThreadProcessId; // ebx
  int StdAccessibleObject_0; // esi
  bool v11; // zf
  int v12; // eax
  char *v13; // rdx
  DWORD v14; // edi
  int v15; // r8d
  int v16; // edi
  int v17; // edi
  HANDLE ProcessHandleFromHwnd; // rsi
  unsigned int (__fastcall ***v19)(void *, GUID *, LPSTREAM *); // rdi
  unsigned int (__fastcall **v20)(void *, GUID *, LPSTREAM *); // rax
  int v21; // ebx
  _DWORD *v22; // rax
  _DWORD *v23; // rbx
  int v24; // r15d
  HANDLE v26; // rbx
  char *v27; // rdx
  int v28; // ecx
  int v29; // r8d
  int v30; // ebx
  int v31; // ebx
  __int16 *v32; // rdx
  int i; // ecx
  __int16 v34; // r8
  __int16 *v35; // r8
  int j; // ecx
  __int16 v37; // dx
  int (__fastcall ***v38)(void *, GUID *, HANDLE *); // rdi
  int v39; // ebx
  int (__fastcall **v40)(void *, GUID *, HANDLE *); // rax
  int *v41; // rax
  int v42; // ebx
  int v43; // esi
  SIZE_T v44; // rdi
  size_t v45; // rbx
  HLOCAL v46; // rdi
  char *v47; // rax
  const void *v48; // rsi
  HGLOBAL v49; // rax
  void *v50; // rsi
  void *v51; // rax
  HRESULT v52; // ebx
  HANDLE CurrentProcess; // rax
  BOOL v54; // ebx
  LPSTREAM ppstm; // [rsp+40h] [rbp-89h] BYREF
  HANDLE hFileMappingObject; // [rsp+48h] [rbp-81h] BYREF
  IID *riida; // [rsp+50h] [rbp-79h] BYREF
  ULONG_PTR dwResult; // [rsp+58h] [rbp-71h] BYREF
  LPARAM lParam; // [rsp+60h] [rbp-69h] BYREF
  __int64 v60; // [rsp+68h] [rbp-61h]
  WCHAR Buffer[5]; // [rsp+70h] [rbp-59h] BYREF
  char v62; // [rsp+7Ah] [rbp-4Fh] BYREF
  __int16 v63; // [rsp+8Ah] [rbp-3Fh]
  char v64; // [rsp+8Ch] [rbp-3Dh] BYREF
  __int16 v65; // [rsp+9Ch] [rbp-2Dh]
  char v66; // [rsp+9Eh] [rbp-2Bh] BYREF
  __int16 v67; // [rsp+AEh] [rbp-1Bh]
  char v68; // [rsp+B0h] [rbp-19h] BYREF
  __int16 v69; // [rsp+C0h] [rbp-9h]
  __int16 v70; // [rsp+C2h] [rbp-7h]

  riida = (IID *)riid;
  v5 = dwId;
  v6 = riid;
  if ( !ppvObject )
  {
    StdAccessibleObject_0 = -2147024809;
    goto LABEL_33;
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
    SendMessageTimeoutW(hwnd, 0x3Du, CurrentProcessId, v5, 2u, 0x2710u, &dwResult);
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
      goto LABEL_29;
    }
    if ( CurrentProcessId == 0xFFFFFFFF )
      ppstm = (LPSTREAM)GetCurrentProcessId();
    else
      ppstm = (LPSTREAM)CurrentProcessId;
    hFileMappingObject = 0;
    if ( HIWORD(StdAccessibleObject_0) )
      goto LABEL_28;
    if ( !(_WORD)StdAccessibleObject_0 )
      goto LABEL_28;
    if ( GlobalGetAtomNameW(StdAccessibleObject_0, Buffer, 42) != 41 )
      goto LABEL_28;
    v12 = memcmp_0(Buffer, L"MSAA:", 0xAu);
    if ( v12 || v63 != 58 || v65 != 58 || v67 != 58 || v69 != 58 || v70 )
      goto LABEL_28;
    v13 = &v62;
    v14 = 0;
    while ( v12 < 8 )
    {
      v15 = *(unsigned __int16 *)v13;
      v16 = 16 * v14;
      if ( (unsigned __int16)(v15 - 48) <= 9u )
      {
        v17 = v16 - 48;
        goto LABEL_24;
      }
      if ( (unsigned __int16)(v15 - 65) > 5u )
      {
        if ( (unsigned __int16)(v15 - 97) > 5u )
          goto LABEL_28;
        v17 = v16 - 87;
LABEL_24:
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
    LODWORD(v26) = 0;
    v27 = &v64;
    v28 = 0;
    while ( 1 )
    {
      if ( v28 >= 8 )
      {
        v32 = (__int16 *)&v66;
        for ( i = 0; i < 8; ++i )
        {
          v34 = *v32;
          if ( (unsigned __int16)(*v32 - 48) > 9u
            && (unsigned __int16)(v34 - 65) > 5u
            && (unsigned __int16)(v34 - 97) > 5u )
          {
            goto LABEL_28;
          }
          ++v32;
        }
        v35 = (__int16 *)&v68;
        for ( j = 0; j < 8; ++j )
        {
          v37 = *v35;
          if ( (unsigned __int16)(*v35 - 48) > 9u
            && (unsigned __int16)(v37 - 65) > 5u
            && (unsigned __int16)(v37 - 97) > 5u )
          {
            goto LABEL_28;
          }
          ++v35;
        }
        GlobalDeleteAtom(StdAccessibleObject_0);
        v26 = (HANDLE)(int)v26;
        if ( v14 == GetCurrentProcessId() )
        {
          hFileMappingObject = (HANDLE)(int)v26;
          goto LABEL_77;
        }
        ProcessHandleFromHwnd = OpenProcess(0x40u, 0, v14);
        if ( !ProcessHandleFromHwnd )
        {
          lParam = v14;
          v60 = 0;
          EnumWindows(FindWindowFromProcessEnumWindowsProc, (LPARAM)&lParam);
          if ( !v60 )
            goto LABEL_28;
          ProcessHandleFromHwnd = (HANDLE)GetProcessHandleFromHwnd(v60);
          if ( !ProcessHandleFromHwnd )
            goto LABEL_28;
        }
        CurrentProcess = GetCurrentProcess();
        v54 = DuplicateHandle(ProcessHandleFromHwnd, (HANDLE)(int)v26, CurrentProcess, &hFileMappingObject, 0, 0, 3u);
        CloseHandle(ProcessHandleFromHwnd);
        if ( !v54 || (v26 = hFileMappingObject) == 0 )
        {
LABEL_28:
          StdAccessibleObject_0 = -2147467259;
          goto LABEL_29;
        }
LABEL_77:
        v41 = (int *)MapViewOfFile(v26, 0xF001Fu, 0, 0, 0x10u);
        if ( !v41 )
          goto LABEL_28;
        v42 = *v41;
        v43 = v41[2];
        v44 = (unsigned int)v41[3];
        UnmapViewOfFile(v41);
        if ( v42 != -1440944115 || (_DWORD)ppstm && v43 != GetCurrentProcessId() )
          goto LABEL_28;
        if ( (unsigned int)v44 > 0x100000 )
        {
          v52 = -2147467259;
        }
        else
        {
          v45 = v44;
          v46 = LocalAlloc(0x40u, v44);
          if ( v46 )
          {
            v47 = (char *)MapViewOfFile(hFileMappingObject, 0xF001Fu, 0, 0, v45 + 16);
            v48 = v47;
            if ( v47 )
            {
              memcpy_0(v46, v47 + 16, v45);
              UnmapViewOfFile(v48);
              v49 = GlobalAlloc(2u, v45);
              v50 = v49;
              if ( v49 )
              {
                v51 = GlobalLock(v49);
                if ( v51 )
                {
                  memcpy_0(v51, v46, v45);
                  GlobalUnlock(v50);
                  ppstm = 0;
                  v52 = CreateStreamOnHGlobal(v50, 1, &ppstm);
                  if ( v52 < 0 )
                  {
                    GlobalFree(v50);
                  }
                  else
                  {
                    v52 = CoUnmarshalInterface(ppstm, riida, ppvObject);
                    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
                  }
                }
                else
                {
                  GlobalFree(v50);
                  v52 = -2147467259;
                }
              }
              else
              {
                v52 = -2147024882;
              }
            }
            else
            {
              v52 = -2147467259;
            }
            LocalFree(v46);
          }
          else
          {
            v52 = -2147024882;
          }
        }
        CloseHandle(hFileMappingObject);
        StdAccessibleObject_0 = v52;
        if ( v52 >= 0 )
        {
LABEL_30:
          v11 = StdAccessibleObject_0 == 0;
          goto LABEL_31;
        }
LABEL_29:
        if ( CurrentProcessId == 0xFFFFFFFF )
          goto LABEL_30;
LABEL_91:
        StdAccessibleObject_0 = 0;
LABEL_32:
        v6 = riida;
        if ( !*ppvObject )
        {
          StdAccessibleObject_0 = CreateStdAccessibleObject_0(hwnd, v5, riida, ppvObject);
          if ( StdAccessibleObject_0 >= 0 )
          {
            v38 = (int (__fastcall ***)(void *, GUID *, HANDLE *))*ppvObject;
            ppstm = 0;
            if ( (**v38)(v38, &GUID_55f9c234_79cd_4699_89e7_5518fd88bcde, (HANDLE *)&ppstm) >= 0 )
            {
              v39 = (*(__int64 (__fastcall **)(LPSTREAM, __int64))(*(_QWORD *)ppstm + 32LL))(ppstm, 458752);
              (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
              if ( v39 >= 0 )
              {
                v40 = *v38;
                hFileMappingObject = 0;
                if ( (*v40)(v38, &GUID_f660d979_a938_423f_b5b9_12e4028c50b0, &hFileMappingObject) >= 0 )
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
        goto LABEL_33;
      }
      v29 = *(unsigned __int16 *)v27;
      v30 = 16 * (_DWORD)v26;
      if ( (unsigned __int16)(v29 - 48) <= 9u )
        break;
      if ( (unsigned __int16)(v29 - 65) > 5u )
      {
        if ( (unsigned __int16)(v29 - 97) > 5u )
          goto LABEL_28;
        v31 = v30 - 87;
LABEL_51:
        LODWORD(v26) = v29 + v31;
        ++v28;
        v27 += 2;
      }
      else
      {
        ++v28;
        LODWORD(v26) = v29 + v30 - 55;
        v27 += 2;
      }
    }
    v31 = v30 - 48;
    goto LABEL_51;
  }
LABEL_31:
  if ( v11 )
    goto LABEL_32;
  v6 = riida;
LABEL_33:
  if ( StdAccessibleObject_0 )
    return StdAccessibleObject_0;
  if ( !ppvObject )
    return StdAccessibleObject_0;
  v19 = (unsigned int (__fastcall ***)(void *, GUID *, LPSTREAM *))*ppvObject;
  if ( !*ppvObject )
    return StdAccessibleObject_0;
  dwResult = 0;
  if ( !(**v19)(v19, &IID_IAccessible, (LPSTREAM *)&dwResult) && dwResult )
  {
    (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)dwResult + 16LL))(dwResult);
    v20 = *v19;
    ppstm = 0;
    if ( (*v20)(v19, &IID_IServiceProvider, &ppstm)
      || !ppstm
      || (riida = 0,
          v21 = (*(__int64 (__fastcall **)(LPSTREAM, GUID *, GUID *, IID **))(*(_QWORD *)ppstm + 24LL))(
                  ppstm,
                  &IIS_AccWrapBase_GetIUnknown,
                  &IID_IUnknown,
                  &riida),
          (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm),
          v21)
      || !riida )
    {
      v22 = LocalAlloc(0x40u, 0xA8u);
      v23 = v22;
      if ( !v22 )
      {
        StdAccessibleObject_0 = -2147024882;
        goto LABEL_106;
      }
      v22[10] = 1;
      *(_QWORD *)v22 = &AccWrap_Base::`vftable'{for `IAccessible'};
      *((_QWORD *)v22 + 6) = v19;
      *((_QWORD *)v22 + 1) = &AccWrap_Base::`vftable'{for `IOleWindow'};
      *((_QWORD *)v22 + 2) = &AccWrap_Base::`vftable'{for `IEnumVARIANT'};
      *((_QWORD *)v22 + 3) = &AccWrap_Base::`vftable'{for `IAccIdentity'};
      *((_QWORD *)v22 + 4) = &AccWrap_Base::`vftable'{for `IServiceProvider'};
      *((_QWORD *)v22 + 8) = 0;
      *((_QWORD *)v22 + 9) = 0;
      *((_QWORD *)v22 + 10) = 0;
      *((_QWORD *)v22 + 11) = 0;
      *((_QWORD *)v22 + 12) = 0;
      v22[26] = 0;
      *((_QWORD *)v22 + 14) = 0;
      *((_QWORD *)v22 + 7) = *v19;
      ((void (__fastcall *)(unsigned int (__fastcall ***)(void *, GUID *, LPSTREAM *)))(*v19)[1])(v19);
      *((_QWORD *)v23 + 15) = 0;
      *(_QWORD *)v23 = &AccWrap_LocationEtcFix::`vftable'{for `IAccessible'};
      v23[32] = 0;
      *((_QWORD *)v23 + 1) = &AccWrap_LocationEtcFix::`vftable'{for `IOleWindow'};
      v23[34] = 0;
      *((_QWORD *)v23 + 2) = &AccWrap_LocationEtcFix::`vftable'{for `IEnumVARIANT'};
      *((_QWORD *)v23 + 18) = 0;
      *((_QWORD *)v23 + 3) = &AccWrap_LocationEtcFix::`vftable'{for `IAccIdentity'};
      *((_QWORD *)v23 + 4) = &AccWrap_LocationEtcFix::`vftable'{for `IServiceProvider'};
      *((_QWORD *)v23 + 19) = 0;
      *((_QWORD *)v23 + 20) = hwnd;
      v24 = ((__int64 (__fastcall *)(_DWORD *, const IID *, void **))AccWrap_LocationEtcFix::`vftable'{for `IAccessible'})(
              v23,
              v6,
              ppvObject);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v23 + 16LL))(v23);
    }
    else
    {
      (*(void (__fastcall **)(IID *))(*(_QWORD *)&riida->Data1 + 16LL))(riida);
      v24 = (**v19)(v19, (GUID *)v6, (LPSTREAM *)ppvObject);
    }
    StdAccessibleObject_0 = v24;
    if ( v24 >= 0 )
    {
LABEL_44:
      ((void (__fastcall *)(unsigned int (__fastcall ***)(void *, GUID *, LPSTREAM *)))(*v19)[2])(v19);
      return StdAccessibleObject_0;
    }
LABEL_106:
    *ppvObject = 0;
    goto LABEL_44;
  }
  return 0;
}

```

## disassembly

```asm
0x180007b90  push    rbp
0x180007b92  push    rbx
0x180007b93  push    rsi
0x180007b94  push    rdi
0x180007b95  push    r12
0x180007b97  push    r13
0x180007b99  push    r14
0x180007b9b  push    r15
0x180007b9d  lea     rbp, [rsp-1Fh]
0x180007ba2  sub     rsp, 0E8h
0x180007ba9  mov     rax, cs:__security_cookie
0x180007bb0  xor     rax, rsp
0x180007bb3  mov     [rbp+57h+var_50], rax
0x180007bb7  mov     [rbp+57h+riid], r8
0x180007bbb  mov     r14, r9
0x180007bbe  mov     r13d, edx
0x180007bc1  mov     r15, r8
0x180007bc4  mov     r12, rcx
0x180007bc7  test    r9, r9
0x180007bca  jz      loc_1800083C9
0x180007bd0  xor     r15d, r15d
0x180007bd3  mov     [r9], r15
0x180007bd6  mov     [rbp+57h+dwResult], r15
0x180007bda  call    cs:__imp_IsWindow
0x180007be0  mov     esi, 0FFFFFFFFh
0x180007be5  test    eax, eax
0x180007be7  jz      short loc_180007C34
0x180007be9  xor     edx, edx; lpdwProcessId
0x180007beb  mov     rcx, r12; hWnd
0x180007bee  call    cs:__imp_GetWindowThreadProcessId
0x180007bf4  mov     ebx, eax
0x180007bf6  call    cs:__imp_GetCurrentThreadId
0x180007bfc  cmp     ebx, eax
0x180007bfe  jnz     loc_1800082D7
0x180007c04  mov     r15d, esi
0x180007c07  lea     rax, [rbp+57h+dwResult]
0x180007c0b  mov     r9, r13; lParam
0x180007c0e  mov     [rsp+120h+lpdwResult], rax; lpdwResult
0x180007c13  mov     r8, r15; wParam
0x180007c16  mov     [rsp+120h+uTimeout], 2710h; uTimeout
0x180007c1e  mov     edx, 3Dh ; '='; Msg
0x180007c23  mov     rcx, r12; hWnd
0x180007c26  mov     [rsp+120h+fuFlags], 2; fuFlags
0x180007c2e  call    cs:__imp_SendMessageTimeoutW
0x180007c34  mov     rsi, [rbp+57h+dwResult]
0x180007c38  test    esi, esi
0x180007c3a  js      loc_180007D5B
0x180007c40  test    rsi, rsi
0x180007c43  jz      loc_1800082D0
0x180007c49  mov     qword ptr [r14], 0
0x180007c50  test    esi, esi
0x180007c52  js      loc_1800082FF
0x180007c58  mov     eax, 0FFFFFFFFh
0x180007c5d  cmp     r15, rax
0x180007c60  jnz     loc_1800082EE
0x180007c66  call    cs:__imp_GetCurrentProcessId
0x180007c6c  mov     ecx, eax
0x180007c6e  mov     [rsp+120h+ppstm], rcx
0x180007c73  mov     eax, esi
0x180007c75  mov     [rsp+120h+hFileMappingObject], 0
0x180007c7e  shr     eax, 10h
0x180007c81  test    ax, ax
0x180007c84  jnz     loc_180007D46
0x180007c8a  test    si, si
0x180007c8d  jz      loc_180007D46
0x180007c93  mov     r8d, 2Ah ; '*'; nSize
0x180007c99  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x180007c9d  movzx   ecx, si; nAtom
0x180007ca0  call    cs:__imp_GlobalGetAtomNameW
0x180007ca6  cmp     eax, 29h ; ')'
0x180007ca9  jnz     loc_180007D46
0x180007caf  mov     r8d, 0Ah; Size
0x180007cb5  lea     rdx, aMsaa_0; "MSAA:"
0x180007cbc  lea     rcx, [rbp+57h+Buffer]; Buf1
0x180007cc0  call    memcmp_0
0x180007cc5  test    eax, eax
0x180007cc7  jnz     short loc_180007D46
0x180007cc9  cmp     [rbp+57h+var_96], 3Ah ; ':'
0x180007cce  jnz     short loc_180007D46
0x180007cd0  cmp     [rbp+57h+var_84], 3Ah ; ':'
0x180007cd5  jnz     short loc_180007D46
0x180007cd7  cmp     [rbp+57h+var_72], 3Ah ; ':'
0x180007cdc  jnz     short loc_180007D46
0x180007cde  cmp     [rbp+57h+var_60], 3Ah ; ':'
0x180007ce3  jnz     short loc_180007D46
0x180007ce5  cmp     [rbp+57h+var_5E], ax
0x180007ce9  jnz     short loc_180007D46
0x180007ceb  lea     rdx, [rbp+57h+var_A6]
0x180007cef  xor     edi, edi
0x180007cf1  cmp     eax, 8
0x180007cf4  jge     loc_180007F8B
0x180007cfa  movzx   r8d, word ptr [rdx]
0x180007cfe  shl     edi, 4
0x180007d01  lea     ecx, [r8-30h]
0x180007d05  cmp     cx, 9
0x180007d09  ja      short loc_180007D19
0x180007d0b  add     edi, 0FFFFFFD0h
0x180007d0e  add     edi, r8d
0x180007d11  inc     eax
0x180007d13  add     rdx, 2
0x180007d17  jmp     short loc_180007CF1
0x180007d19  lea     ecx, [r8-41h]
0x180007d1d  cmp     cx, 5
0x180007d21  ja      loc_1800083D3
0x180007d27  add     edi, 0FFFFFFC9h
0x180007d2a  inc     eax
0x180007d2c  add     edi, r8d
0x180007d2f  add     rdx, 2
0x180007d33  jmp     short loc_180007CF1
0x180007d35  call    GetProcessHandleFromHwnd
0x180007d3a  mov     rsi, rax
0x180007d3d  test    rax, rax
0x180007d40  jnz     loc_180008364
0x180007d46  mov     esi, 80004005h
0x180007d4b  mov     eax, 0FFFFFFFFh
0x180007d50  cmp     r15, rax
0x180007d53  jnz     loc_1800082D0
0x180007d59  test    esi, esi
0x180007d5b  jnz     loc_180008469
0x180007d61  cmp     qword ptr [r14], 0
0x180007d65  mov     r15, [rbp+57h+riid]
0x180007d69  jz      loc_180008057
0x180007d6f  test    esi, esi
0x180007d71  jnz     loc_180007F65
0x180007d77  test    r14, r14
0x180007d7a  jz      loc_180007F65
0x180007d80  mov     rdi, [r14]
0x180007d83  test    rdi, rdi
0x180007d86  jz      loc_180007F65
0x180007d8c  xor     r13d, r13d
0x180007d8f  lea     r8, [rbp+57h+dwResult]
0x180007d93  mov     [rbp+57h+dwResult], r13
0x180007d97  lea     rdx, IID_IAccessible
0x180007d9e  mov     rax, [rdi]
0x180007da1  mov     rcx, rdi
0x180007da4  mov     rax, [rax]
0x180007da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dac  test    eax, eax
0x180007dae  jnz     loc_180007F87
0x180007db4  mov     rcx, [rbp+57h+dwResult]
0x180007db8  test    rcx, rcx
0x180007dbb  jz      loc_180007F87
0x180007dc1  mov     rax, [rcx]
0x180007dc4  mov     rax, [rax+10h]
0x180007dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dcd  mov     rax, [rdi]
0x180007dd0  lea     r8, [rsp+120h+ppstm]
0x180007dd5  lea     rdx, IID_IServiceProvider
0x180007ddc  mov     [rsp+120h+ppstm], r13
0x180007de1  mov     rcx, rdi
0x180007de4  mov     rax, [rax]
0x180007de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dec  test    eax, eax
0x180007dee  jnz     short loc_180007E37
0x180007df0  mov     rcx, [rsp+120h+ppstm]
0x180007df5  test    rcx, rcx
0x180007df8  jz      short loc_180007E37
0x180007dfa  mov     [rbp+57h+riid], r13
0x180007dfe  lea     r9, [rbp+57h+riid]
0x180007e02  mov     rax, [rcx]
0x180007e05  lea     r8, IID_IUnknown
0x180007e0c  lea     rdx, ?IIS_AccWrapBase_GetIUnknown@@3U_GUID@@A; _GUID IIS_AccWrapBase_GetIUnknown
0x180007e13  mov     rax, [rax+18h]
0x180007e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e1c  mov     rcx, [rsp+120h+ppstm]
0x180007e21  mov     ebx, eax
0x180007e23  mov     rdx, [rcx]
0x180007e26  mov     rax, [rdx+10h]
0x180007e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e2f  test    ebx, ebx
0x180007e31  jz      loc_180008309
0x180007e37  mov     edx, 0A8h; uBytes
0x180007e3c  mov     ecx, 40h ; '@'; uFlags
0x180007e41  call    cs:__imp_LocalAlloc
0x180007e47  mov     rbx, rax
0x180007e4a  test    rax, rax
0x180007e4d  jz      loc_1800083BC
0x180007e53  mov     dword ptr [rbx+28h], 1
0x180007e5a  lea     rax, ??_7AccWrap_Base@@6BIAccessible@@@; const AccWrap_Base::`vftable'{for `IAccessible'}
0x180007e61  mov     [rbx], rax
0x180007e64  mov     rcx, rdi
0x180007e67  mov     [rbx+30h], rdi
0x180007e6b  lea     rax, ??_7AccWrap_Base@@6BIOleWindow@@@; const AccWrap_Base::`vftable'{for `IOleWindow'}
0x180007e72  mov     [rbx+8], rax
0x180007e76  lea     rax, ??_7AccWrap_Base@@6BIEnumVARIANT@@@; const AccWrap_Base::`vftable'{for `IEnumVARIANT'}
0x180007e7d  mov     [rbx+10h], rax
0x180007e81  lea     rax, ??_7AccWrap_Base@@6BIAccIdentity@@@; const AccWrap_Base::`vftable'{for `IAccIdentity'}
0x180007e88  mov     [rbx+18h], rax
0x180007e8c  lea     rax, ??_7AccWrap_Base@@6BIServiceProvider@@@; const AccWrap_Base::`vftable'{for `IServiceProvider'}
0x180007e93  mov     [rbx+20h], rax
0x180007e97  mov     [rbx+40h], r13
0x180007e9b  mov     [rbx+48h], r13
0x180007e9f  mov     [rbx+50h], r13
0x180007ea3  mov     [rbx+58h], r13
0x180007ea7  mov     [rbx+60h], r13
0x180007eab  mov     [rbx+68h], r13d
0x180007eaf  mov     [rbx+70h], r13
0x180007eb3  mov     rax, [rdi]
0x180007eb6  mov     [rbx+38h], rax
0x180007eba  mov     rax, [rdi]
0x180007ebd  mov     rax, [rax+8]
0x180007ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ec6  lea     rax, ??_7AccWrap_LocationEtcFix@@6BIAccessible@@@; const AccWrap_LocationEtcFix::`vftable'{for `IAccessible'}
0x180007ecd  mov     [rbx+78h], r13
0x180007ed1  mov     [rbx], rax
0x180007ed4  mov     r8, r14
0x180007ed7  lea     rax, ??_7AccWrap_LocationEtcFix@@6BIOleWindow@@@; const AccWrap_LocationEtcFix::`vftable'{for `IOleWindow'}
0x180007ede  mov     [rbx+80h], r13d
0x180007ee5  mov     [rbx+8], rax
0x180007ee9  mov     rdx, r15
0x180007eec  lea     rax, ??_7AccWrap_LocationEtcFix@@6BIEnumVARIANT@@@; const AccWrap_LocationEtcFix::`vftable'{for `IEnumVARIANT'}
0x180007ef3  mov     [rbx+88h], r13d
0x180007efa  mov     [rbx+10h], rax
0x180007efe  mov     rcx, rbx
0x180007f01  lea     rax, ??_7AccWrap_LocationEtcFix@@6BIAccIdentity@@@; const AccWrap_LocationEtcFix::`vftable'{for `IAccIdentity'}
0x180007f08  mov     [rbx+90h], r13
0x180007f0f  mov     [rbx+18h], rax
0x180007f13  lea     rax, ??_7AccWrap_LocationEtcFix@@6BIServiceProvider@@@; const AccWrap_LocationEtcFix::`vftable'{for `IServiceProvider'}
0x180007f1a  mov     [rbx+20h], rax
0x180007f1e  mov     [rbx+98h], r13
0x180007f25  mov     [rbx+0A0h], r12
0x180007f2c  mov     rax, cs:??_7AccWrap_LocationEtcFix@@6BIAccessible@@@; const AccWrap_LocationEtcFix::`vftable'{for `IAccessible'}
0x180007f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f38  mov     r15d, eax
0x180007f3b  mov     rcx, rbx
0x180007f3e  mov     rax, [rbx]
0x180007f41  mov     rax, [rax+10h]
0x180007f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f4a  mov     esi, r15d
0x180007f4d  test    r15d, r15d
0x180007f50  js      loc_1800083C1
0x180007f56  mov     rax, [rdi]
0x180007f59  mov     rcx, rdi
0x180007f5c  mov     rax, [rax+10h]
0x180007f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f65  mov     eax, esi
0x180007f67  mov     rcx, [rbp+57h+var_50]
0x180007f6b  xor     rcx, rsp; StackCookie
0x180007f6e  call    __security_check_cookie
0x180007f73  add     rsp, 0E8h
0x180007f7a  pop     r15
0x180007f7c  pop     r14
0x180007f7e  pop     r13
0x180007f80  pop     r12
0x180007f82  pop     rdi
0x180007f83  pop     rsi
0x180007f84  pop     rbx
0x180007f85  pop     rbp
0x180007f86  retn
0x180007f87  xor     eax, eax
0x180007f89  jmp     short loc_180007F67
0x180007f8b  xor     ebx, ebx
0x180007f8d  lea     rdx, [rbp+57h+var_94]
0x180007f91  xor     ecx, ecx
0x180007f93  cmp     ecx, 8
0x180007f96  jge     short loc_180007FD3
0x180007f98  movzx   r8d, word ptr [rdx]
0x180007f9c  shl     ebx, 4
0x180007f9f  lea     eax, [r8-30h]
0x180007fa3  cmp     ax, 9
0x180007fa7  ja      short loc_180007FB7
0x180007fa9  add     ebx, 0FFFFFFD0h
0x180007fac  add     ebx, r8d
0x180007faf  inc     ecx
0x180007fb1  add     rdx, 2
0x180007fb5  jmp     short loc_180007F93
0x180007fb7  lea     eax, [r8-41h]
0x180007fbb  cmp     ax, 5
0x180007fbf  ja      loc_1800083E9
0x180007fc5  add     ebx, 0FFFFFFC9h
0x180007fc8  inc     ecx
0x180007fca  add     ebx, r8d
0x180007fcd  add     rdx, 2
0x180007fd1  jmp     short loc_180007F93
0x180007fd3  lea     rdx, [rbp+57h+var_82]
0x180007fd7  xor     ecx, ecx
0x180007fd9  nop     dword ptr [rax+00000000h]
0x180007fe0  cmp     ecx, 8
0x180007fe3  jge     short loc_180008017
0x180007fe5  movzx   r8d, word ptr [rdx]
0x180007fe9  lea     eax, [r8-30h]
0x180007fed  cmp     ax, 9
0x180007ff1  ja      short loc_180007FFB
0x180007ff3  inc     ecx
0x180007ff5  add     rdx, 2
0x180007ff9  jmp     short loc_180007FE0
0x180007ffb  lea     eax, [r8-41h]
0x180007fff  cmp     ax, 5
0x180008003  jbe     short loc_180007FF3
0x180008005  sub     r8w, 61h ; 'a'
0x18000800a  cmp     r8w, 5
0x18000800f  ja      loc_180007D46
0x180008015  jmp     short loc_180007FF3
0x180008017  lea     r8, [rbp+57h+var_70]
0x18000801b  xor     ecx, ecx
0x18000801d  nop     dword ptr [rax]
0x180008020  cmp     ecx, 8
0x180008023  jge     loc_18000813C
0x180008029  movzx   edx, word ptr [r8]
0x18000802d  lea     eax, [rdx-30h]
  ... truncated ...
```
