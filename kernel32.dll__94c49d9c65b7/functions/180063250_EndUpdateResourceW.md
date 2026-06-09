# EndUpdateResourceW

- ea: `0x180063250`
- end: `0x1800634d8`
- name: `EndUpdateResourceW`
- size: `648`
- prototype: `BOOL __stdcall(HANDLE hUpdate, BOOL fDiscard)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180063240`

## callees

- `0x18002db60`
- `0x1800629c4`
- `0x180063034`
- `0x180063250`
- `0x18007a840`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18006328d`
- `ntdll!RtlSetLastWin32Error` at `0x18006329c`
- `ntdll!RtlSetLastWin32Error` at `0x1800634a8`
- `ntdll!RtlSetLastWin32Error` at `0x18006328d`
- `ntdll!RtlSetLastWin32Error` at `0x18006329c`
- `ntdll!RtlSetLastWin32Error` at `0x1800634a8`
- `KERNELBASE!GlobalFree` at `0x1800632d1`
- `KERNELBASE!GlobalFree` at `0x180063486`
- `KERNELBASE!GlobalFree` at `0x1800634a0`
- `KERNELBASE!GlobalFree` at `0x1800632d1`
- `KERNELBASE!GlobalFree` at `0x180063486`
- `KERNELBASE!GlobalFree` at `0x1800634a0`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180063379`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180063412`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180063379`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180063412`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180063466`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180063472`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180063466`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180063472`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1800633d3`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1800633d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800633ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800633ae`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800633e4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800633e4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180063396`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180063396`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180063445`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180063445`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800632ac`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800632c2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800632fb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800632ac`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800632c2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800632fb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006347c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180063497`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006347c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180063497`

## string_xrefs

- `0x1800633a4`: `GetTempPath2W`
- `0x180063389`: `kernelbase.dll`

## pseudocode

```c
BOOL __stdcall EndUpdateResourceW(HANDLE hUpdate, BOOL fDiscard)
{
  ULONG v4; // ecx
  HGLOBAL *v6; // rax
  HGLOBAL *v7; // rsi
  ULONG LastErrorValue; // ebx
  ULONG v9; // edi
  const wchar_t *v10; // rax
  const WCHAR *v11; // r15
  HRESULT v12; // eax
  STRSAFE_LPWSTR v13; // rcx
  HMODULE Library; // rax
  HMODULE v15; // rbx
  FARPROC ProcAddress; // rax
  DWORD TempPathW; // r12d
  ULONG v18; // eax
  DWORD v19; // [rsp+28h] [rbp-D8h]
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF

  ppszDestEnd = 0;
  RtlSetLastWin32Error(0);
  if ( !hUpdate )
  {
    v4 = 87;
LABEL_3:
    RtlSetLastWin32Error(v4);
    return 0;
  }
  v6 = (HGLOBAL *)GlobalLock(hUpdate);
  v7 = v6;
  if ( !fDiscard )
  {
    if ( !v6 )
      return 0;
    v10 = (const wchar_t *)GlobalLock(v6[6]);
    v11 = v10;
    if ( !v10 )
    {
      v4 = 1359;
      goto LABEL_3;
    }
    v12 = StringCchCopyExW(pszDest, 0x104u, v10, &ppszDestEnd, 0, v19);
    if ( v12 < 0 )
    {
      LastErrorValue = (unsigned __int16)v12;
LABEL_34:
      v9 = LastErrorValue;
      goto LABEL_36;
    }
    v13 = ppszDestEnd;
    v9 = 0;
    do
      --v13;
    while ( *v13 != 92 && v13 >= pszDest );
    v13[1] = 0;
    if ( GetTempFileNameW(pszDest, L"RCX", 0, pszDest) )
      goto LABEL_29;
    Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
    v15 = Library;
    if ( Library && (ProcAddress = GetProcAddress(Library, "GetTempPath2W")) != 0 )
    {
      TempPathW = ((__int64 (__fastcall *)(__int64, wchar_t *))ProcAddress)(260, pszDest);
    }
    else
    {
      TempPathW = GetTempPathW(0x104u, pszDest);
      if ( !v15 )
        goto LABEL_25;
    }
    FreeLibrary(v15);
LABEL_25:
    if ( !TempPathW )
      wcscpy(pszDest, L".\\");
    if ( !GetTempFileNameW(pszDest, L"RCX", 0, pszDest) )
    {
      LastErrorValue = NtCurrentTeb()->LastErrorValue;
      goto LABEL_36;
    }
LABEL_29:
    v18 = WriteResFile(hUpdate, pszDest);
    LastErrorValue = v18;
    if ( v18 )
    {
      v9 = v18;
      DeleteFileW(pszDest);
      goto LABEL_36;
    }
    if ( !MoveFileExW(pszDest, v11, 3u) )
    {
      LastErrorValue = NtCurrentTeb()->LastErrorValue;
      if ( !LastErrorValue )
        LastErrorValue = 1359;
      DeleteFileW(pszDest);
      goto LABEL_34;
    }
LABEL_36:
    GlobalUnlock(v7[6]);
    GlobalFree(v7[6]);
    goto LABEL_37;
  }
  if ( v6 )
  {
    if ( !GlobalLock(v6[6]) )
    {
      LastErrorValue = 0;
      v9 = 0;
LABEL_38:
      GlobalUnlock(hUpdate);
      goto LABEL_39;
    }
    GlobalFree(v7[6]);
    LastErrorValue = 0;
    v9 = 0;
LABEL_37:
    FreeData((struct _UPDATEDATA *)v7);
    goto LABEL_38;
  }
  LastErrorValue = 0;
  v9 = 0;
LABEL_39:
  GlobalFree(hUpdate);
  RtlSetLastWin32Error(v9);
  return LastErrorValue == 0;
}

```

## disassembly

```asm
0x180063250  push    rbp
0x180063252  push    rbx
0x180063253  push    rsi
0x180063254  push    rdi
0x180063255  push    r12
0x180063257  push    r13
0x180063259  push    r14
0x18006325b  push    r15
0x18006325d  lea     rbp, [rsp-168h]
0x180063265  sub     rsp, 268h
0x18006326c  mov     rax, cs:__security_cookie
0x180063273  xor     rax, rsp
0x180063276  mov     [rbp+1A0h+var_50], rax
0x18006327d  mov     r14, rcx
0x180063280  mov     [rsp+2A0h+ppszDestEnd], 0
0x180063289  xor     ecx, ecx; LastError
0x18006328b  mov     ebx, edx
0x18006328d  call    cs:__imp_RtlSetLastWin32Error
0x180063293  test    r14, r14
0x180063296  jnz     short loc_1800632A9
0x180063298  lea     ecx, [r14+57h]; LastError
0x18006329c  call    cs:__imp_RtlSetLastWin32Error
0x1800632a2  xor     eax, eax
0x1800632a4  jmp     loc_1800634B5
0x1800632a9  mov     rcx, r14; hMem
0x1800632ac  call    cs:__imp_GlobalLock
0x1800632b2  mov     rsi, rax
0x1800632b5  test    ebx, ebx
0x1800632b7  jz      short loc_1800632F2
0x1800632b9  test    rax, rax
0x1800632bc  jz      short loc_1800632E9
0x1800632be  mov     rcx, [rax+30h]; hMem
0x1800632c2  call    cs:__imp_GlobalLock
0x1800632c8  test    rax, rax
0x1800632cb  jz      short loc_1800632E0
0x1800632cd  mov     rcx, [rsi+30h]; hMem
0x1800632d1  call    cs:__imp_GlobalFree
0x1800632d7  xor     ebx, ebx
0x1800632d9  xor     edi, edi
0x1800632db  jmp     loc_18006348C
0x1800632e0  xor     ebx, ebx
0x1800632e2  xor     edi, edi
0x1800632e4  jmp     loc_180063494
0x1800632e9  xor     ebx, ebx
0x1800632eb  xor     edi, edi
0x1800632ed  jmp     loc_18006349D
0x1800632f2  test    rsi, rsi
0x1800632f5  jz      short loc_1800632A2
0x1800632f7  mov     rcx, [rax+30h]; hMem
0x1800632fb  call    cs:__imp_GlobalLock
0x180063301  mov     r15, rax
0x180063304  test    rax, rax
0x180063307  jnz     short loc_180063310
0x180063309  mov     ecx, 54Fh
0x18006330e  jmp     short loc_18006329C
0x180063310  mov     r12d, 104h
0x180063316  mov     [rsp+2A0h+pcchRemaining], 0; pcchRemaining
0x18006331f  mov     edx, r12d; cchDest
0x180063322  lea     r9, [rsp+2A0h+ppszDestEnd]; ppszDestEnd
0x180063327  mov     r8, r15; pszSrc
0x18006332a  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x18006332f  call    StringCchCopyExW
0x180063334  test    eax, eax
0x180063336  jns     short loc_180063340
0x180063338  movzx   ebx, ax
0x18006333b  jmp     loc_18006346C
0x180063340  mov     rcx, [rsp+2A0h+ppszDestEnd]
0x180063345  xor     edi, edi
0x180063347  lea     r13d, [rdi+5Ch]
0x18006334b  sub     rcx, 2
0x18006334f  cmp     [rcx], r13w
0x180063353  jz      short loc_18006335F
0x180063355  lea     rax, [rsp+2A0h+pszDest]
0x18006335a  cmp     rcx, rax
0x18006335d  jnb     short loc_18006334B
0x18006335f  xor     eax, eax
0x180063361  lea     r9, [rsp+2A0h+pszDest]; lpTempFileName
0x180063366  mov     [rcx+2], ax
0x18006336a  lea     rdx, PrefixString; "RCX"
0x180063371  lea     rcx, [rsp+2A0h+pszDest]; lpPathName
0x180063376  xor     r8d, r8d; uUnique
0x180063379  call    cs:__imp_GetTempFileNameW
0x18006337f  test    eax, eax
0x180063381  jnz     loc_180063426
0x180063387  xor     edx, edx; hFile
0x180063389  lea     rcx, aKernelbaseDll_0; "kernelbase.dll"
0x180063390  mov     r8d, 800h; dwFlags
0x180063396  call    cs:__imp_LoadLibraryExW
0x18006339c  mov     rbx, rax
0x18006339f  test    rax, rax
0x1800633a2  jz      short loc_1800633CB
0x1800633a4  lea     rdx, aGettemppath2w_0; "GetTempPath2W"
0x1800633ab  mov     rcx, rax; hModule
0x1800633ae  call    cs:__imp_GetProcAddress
0x1800633b4  test    rax, rax
0x1800633b7  jz      short loc_1800633CB
0x1800633b9  lea     rdx, [rsp+2A0h+pszDest]
0x1800633be  mov     ecx, r12d
0x1800633c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800633c6  mov     r12d, eax
0x1800633c9  jmp     short loc_1800633E1
0x1800633cb  lea     rdx, [rsp+2A0h+pszDest]; lpBuffer
0x1800633d0  mov     ecx, r12d; nBufferLength
0x1800633d3  call    cs:__imp_GetTempPathW
0x1800633d9  mov     r12d, eax
0x1800633dc  test    rbx, rbx
0x1800633df  jz      short loc_1800633EA
0x1800633e1  mov     rcx, rbx; hLibModule
0x1800633e4  call    cs:__imp_FreeLibrary
0x1800633ea  test    r12d, r12d
0x1800633ed  jnz     short loc_1800633FE
0x1800633ef  xor     eax, eax
0x1800633f1  mov     dword ptr [rsp+2A0h+pszDest], 5C002Eh
0x1800633f9  mov     [rsp+2A0h+var_25C], ax
0x1800633fe  lea     r9, [rsp+2A0h+pszDest]; lpTempFileName
0x180063403  xor     r8d, r8d; uUnique
0x180063406  lea     rdx, PrefixString; "RCX"
0x18006340d  lea     rcx, [rsp+2A0h+pszDest]; lpPathName
0x180063412  call    cs:__imp_GetTempFileNameW
0x180063418  test    eax, eax
0x18006341a  jnz     short loc_180063426
0x18006341c  mov     ebx, gs:68h
0x180063424  jmp     short loc_180063478
0x180063426  lea     rdx, [rsp+2A0h+pszDest]; lpFileName
0x18006342b  mov     rcx, r14; hMem
0x18006342e  call    ?WriteResFile@@YAJPEAXPEAG@Z; WriteResFile(void *,ushort *)
0x180063433  lea     rcx, [rsp+2A0h+pszDest]; lpFileName
0x180063438  mov     ebx, eax
0x18006343a  test    eax, eax
0x18006343c  jnz     short loc_180063470
0x18006343e  lea     r8d, [rax+3]; dwFlags
0x180063442  mov     rdx, r15; lpNewFileName
0x180063445  call    cs:__imp_MoveFileExW
0x18006344b  test    eax, eax
0x18006344d  jnz     short loc_180063478
0x18006344f  mov     ebx, gs:68h
0x180063457  lea     rcx, [rsp+2A0h+pszDest]; lpFileName
0x18006345c  test    ebx, ebx
0x18006345e  mov     eax, 54Fh
0x180063463  cmovz   ebx, eax
0x180063466  call    cs:__imp_DeleteFileW
0x18006346c  mov     edi, ebx
0x18006346e  jmp     short loc_180063478
0x180063470  mov     edi, eax
0x180063472  call    cs:__imp_DeleteFileW
0x180063478  mov     rcx, [rsi+30h]; hMem
0x18006347c  call    cs:__imp_GlobalUnlock
0x180063482  mov     rcx, [rsi+30h]; hMem
0x180063486  call    cs:__imp_GlobalFree
0x18006348c  mov     rcx, rsi; struct _UPDATEDATA *
0x18006348f  call    ?FreeData@@YAXPEAU_UPDATEDATA@@@Z; FreeData(_UPDATEDATA *)
0x180063494  mov     rcx, r14; hMem
0x180063497  call    cs:__imp_GlobalUnlock
0x18006349d  mov     rcx, r14; hMem
0x1800634a0  call    cs:__imp_GlobalFree
0x1800634a6  mov     ecx, edi; LastError
0x1800634a8  call    cs:__imp_RtlSetLastWin32Error
0x1800634ae  xor     eax, eax
0x1800634b0  test    ebx, ebx
0x1800634b2  setz    al
0x1800634b5  mov     rcx, [rbp+1A0h+var_50]
0x1800634bc  xor     rcx, rsp; StackCookie
0x1800634bf  call    __security_check_cookie
0x1800634c4  add     rsp, 268h
0x1800634cb  pop     r15
0x1800634cd  pop     r14
0x1800634cf  pop     r13
0x1800634d1  pop     r12
0x1800634d3  pop     rdi
0x1800634d4  pop     rsi
0x1800634d5  pop     rbx
0x1800634d6  pop     rbp
0x1800634d7  retn
```
