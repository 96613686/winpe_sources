# ReportHangInternal

- ea: `0x18000c44c`
- end: `0x18000c8fd`
- name: `ReportHangInternal`
- size: `1201`
- prototype: ``
- caller_count: `5`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x18000ceb0`
- `0x18000cef0`
- `0x18000cf30`
- `0x18000cf60`
- `0x18000cfa0`

## callees

- `0x180002890`
- `0x180003474`
- `0x1800035f3`
- `0x1800035ff`
- `0x180003898`
- `0x180003978`
- `0x180003b38`
- `0x180003c50`
- `0x18000c44c`
- `0x18000c904`
- `0x18000ca34`
- `0x180049280`
- `0x180049304`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c8e2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c8e2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c870`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c870`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000c5d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000c5d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c8ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c8ef`
- `ntdll!PssNtFreeSnapshot` at `0x18000c779`
- `ntdll!PssNtFreeSnapshot` at `0x18000c779`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c510`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c525`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c510`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c525`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000c808`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000c808`
- `ext-ms-win-ntuser-gui-l1-3-0!ChangeWindowMessageFilterEx` at `0x18000c8b7`
- `ext-ms-win-ntuser-gui-l1-3-0!ChangeWindowMessageFilterEx` at `0x18000c8b7`
- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x18000c8a2`
- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x18000c8a2`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18000c4ef`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18000c4ef`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x18000c69b`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x18000c69b`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18000c6c5`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18000c6c5`

## string_xrefs

- `0x18000c863`: `user32.dll`
- `0x18000c75b`: `\WindowsErrorReportingServicePort`

## pseudocode

```c
__int64 __fastcall ReportHangInternal(
        HWND a1,
        DWORD *a2,
        unsigned int a3,
        DWORD WindowThreadProcessId,
        int a5,
        __int16 *a6)
{
  __int64 v6; // rbx
  int v10; // ebx
  __int16 *v12; // rcx
  __int64 v13; // rdx
  __int16 *v14; // rax
  __int64 v15; // r8
  __int16 *v16; // rcx
  int v17; // r9d
  DWORD CurrentThreadId_0; // eax
  HDESK ThreadDesktop; // rax
  unsigned int v20; // ecx
  __int64 i; // rsi
  int v22; // r8d
  __int64 v23; // rcx
  __int64 v24; // rax
  HWND v25; // rbx
  DWORD v26; // esi
  HMODULE Library; // rdi
  DWORD v28; // ecx
  UINT v29; // eax
  FARPROC RegisterErrorReportingDialog; // rax
  DWORD dwProcessId; // [rsp+30h] [rbp-D0h] BYREF
  DWORD nLengthNeeded; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE Handles[3]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE Src[1408]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v35; // [rsp+5D0h] [rbp+4D0h] BYREF
  _BYTE v36[38]; // [rsp+5D2h] [rbp+4D2h] BYREF
  int v37; // [rsp+5F8h] [rbp+4F8h]
  int v38; // [rsp+5FCh] [rbp+4FCh]
  HWND hwnd; // [rsp+600h] [rbp+500h]
  HANDLE hObject; // [rsp+B38h] [rbp+A38h]
  HANDLE v41; // [rsp+B40h] [rbp+A40h]
  _DWORD v42[12]; // [rsp+B50h] [rbp+A50h] BYREF
  _DWORD v43[18]; // [rsp+B80h] [rbp+A80h] BYREF
  _QWORD v44[16]; // [rsp+BC8h] [rbp+AC8h] BYREF
  char v45; // [rsp+C48h] [rbp+B48h] BYREF
  _DWORD v46[16]; // [rsp+C58h] [rbp+B58h] BYREF
  HWND v47; // [rsp+C98h] [rbp+B98h]
  _WORD pvInfo[260]; // [rsp+CA0h] [rbp+BA0h] BYREF
  __int16 v49; // [rsp+EA8h] [rbp+DA8h] BYREF
  int v50; // [rsp+10B0h] [rbp+FB0h]
  DWORD TickCount; // [rsp+10B4h] [rbp+FB4h]

  v6 = a3;
  dwProcessId = 0;
  LOWORD(v42[0]) = 0;
  memset_0((char *)v42 + 2, 0, 0x576u);
  v35 = 0;
  memset_0(v36, 0, 0x576u);
  *(_OWORD *)Handles = 0;
  if ( a1 )
  {
    if ( !(unsigned __int8)IsGetShellWindowPresent() )
    {
      v10 = -1073741637;
      goto LABEL_6;
    }
    WindowThreadProcessId = GetWindowThreadProcessId(a1, &dwProcessId);
    if ( !WindowThreadProcessId )
      goto LABEL_5;
  }
  else
  {
    if ( !a2 || !(_DWORD)v6 )
      goto LABEL_5;
    dwProcessId = *a2;
  }
  if ( (a5 & 0xFFE00000) != 0 || !a1 && (!a2 || !(_DWORD)v6) )
  {
LABEL_5:
    v10 = -1073741811;
    goto LABEL_6;
  }
  if ( (unsigned int)v6 > 0x10 )
  {
    v10 = -1073740757;
    goto LABEL_6;
  }
  memset_0(Src, 0, 0x578u);
  memcpy_0(v42, Src, 0x578u);
  v42[0] = 91751760;
  v42[10] = 0x10000000;
  v43[16] = WindowThreadProcessId;
  v47 = a1;
  TickCount = GetTickCount();
  if ( a2 && (_DWORD)v6 )
  {
    memcpy_0(v43, a2, 4 * v6);
  }
  else
  {
    LODWORD(v6) = 1;
    v43[0] = dwProcessId;
  }
  if ( (a5 & 2) != 0 )
  {
    v12 = a6;
    if ( a6 )
    {
      v13 = 260;
      v14 = &v49;
      v15 = 2147483646;
      do
      {
        if ( !v15 )
          break;
        if ( !*v12 )
          break;
        *v14++ = *v12++;
        --v15;
        --v13;
      }
      while ( v13 );
      v16 = v14 - 1;
      if ( v13 )
        v16 = v14;
      *v16 = 0;
    }
    else
    {
      v49 = 0;
    }
  }
  nLengthNeeded = 0;
  pvInfo[0] = 0;
  if ( !(unsigned __int8)IsGetThreadDesktopPresent()
    || !(unsigned __int8)IsGetThreadDesktopPresent()
    || (CurrentThreadId_0 = GetCurrentThreadId_0(), (ThreadDesktop = GetThreadDesktop(CurrentThreadId_0)) == 0)
    || !GetUserObjectInformationW(ThreadDesktop, 2, pvInfo, 0x208u, &nLengthNeeded) )
  {
    pvInfo[0] = 0;
  }
  v50 = a5;
  if ( (a5 & 0x84000) != 0 )
  {
    v20 = 0;
    do
    {
      if ( (a5 & 0x80000) != 0 )
      {
        v46[v20] = -1073741248;
      }
      else if ( !v20 || (a5 & 0x100000) != 0 )
      {
        v46[v20] = -1073741822;
      }
      ++v20;
    }
    while ( v20 < (unsigned int)v6 );
  }
  else
  {
    RhpCaptureSnapshots((unsigned int)v44, (unsigned int)&v45, (unsigned int)v46, v17, (__int64)v43);
  }
  v10 = WersvcSendMessage(L"\\WindowsErrorReportingServicePort", (struct _WERSVC_MSG *)v42, (struct _WERSVC_MSG *)&v35);
  for ( i = 0; i != 16; ++i )
  {
    if ( v44[i] )
      PssNtFreeSnapshot();
  }
  if ( v10 >= 0 )
  {
    if ( v10 == 258 )
    {
      v10 = -1073741248;
      goto LABEL_6;
    }
    v22 = v37;
    if ( v37 != 268435457 )
    {
      if ( v37 == 268435458 )
      {
        v10 = v38;
        if ( v38 < 0 )
          goto LABEL_6;
      }
      else if ( v37 == 268435461 )
      {
        goto LABEL_58;
      }
      v10 = -1073741823;
      goto LABEL_6;
    }
LABEL_58:
    v23 = 0;
    if ( hObject )
    {
      Handles[0] = hObject;
      v23 = 1;
    }
    if ( v41 )
    {
      v24 = (unsigned int)v23;
      v23 = (unsigned int)(v23 + 1);
      Handles[v24] = v41;
    }
    if ( (a5 & 0x20) != 0 && (_DWORD)v23 )
    {
      WaitForMultipleObjects(v23, Handles, 0, 0xFFFFFFFF);
      v22 = v37;
    }
    v25 = hwnd;
    if ( !hwnd )
      goto LABEL_81;
    if ( v22 != 268435461 )
      goto LABEL_81;
    v26 = dwProcessId;
    if ( !dwProcessId )
      goto LABEL_81;
    if ( (unsigned __int8)IsRegisterWindowMessageWPresent(v23)
      && (unsigned __int8)IsChangeWindowMessageFilterExPresent() )
    {
      Library = LoadLibraryExW(L"user32.dll", 0, 0x800u);
      if ( Library )
      {
        v29 = RegisterWindowMessageW(L"WerHangRepMessage");
        if ( v29 )
        {
          if ( ChangeWindowMessageFilterEx(v25, v29, 1u, 0) )
          {
            RegisterErrorReportingDialog = GetProcAddress_0(Library, "RegisterErrorReportingDialog");
            if ( RegisterErrorReportingDialog )
              ((void (__fastcall *)(HWND, _QWORD))RegisterErrorReportingDialog)(v25, v26);
          }
        }
        FreeLibrary(Library);
        goto LABEL_81;
      }
      v28 = 126;
    }
    else
    {
      v28 = 127;
    }
    SetLastError(v28);
LABEL_81:
    v10 = 0;
  }
LABEL_6:
  if ( hObject )
    CloseHandle(hObject);
  if ( v41 )
    CloseHandle(v41);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000c44c  push    rbp
0x18000c44e  push    rbx
0x18000c44f  push    rsi
0x18000c450  push    rdi
0x18000c451  push    r12
0x18000c453  push    r13
0x18000c455  push    r14
0x18000c457  push    r15
0x18000c459  lea     rbp, [rsp-0FE8h]
0x18000c461  mov     eax, 10E8h
0x18000c466  call    _alloca_probe
0x18000c46b  sub     rsp, rax
0x18000c46e  mov     rax, cs:__security_cookie
0x18000c475  xor     rax, rsp
0x18000c478  mov     [rbp+1020h+var_50], rax
0x18000c47f  mov     ebx, r8d
0x18000c482  mov     rsi, rdx
0x18000c485  mov     r14, rcx
0x18000c488  xor     r13d, r13d
0x18000c48b  mov     edi, 576h
0x18000c490  mov     [rsp+1120h+dwProcessId], r13d
0x18000c495  mov     r8d, edi; Size
0x18000c498  mov     word ptr [rbp+1020h+var_5D0], r13w
0x18000c4a0  xor     edx, edx; Val
0x18000c4a2  lea     rcx, [rbp+1020h+var_5D0+2]; void *
0x18000c4a9  mov     r15d, r9d
0x18000c4ac  call    memset_0
0x18000c4b1  mov     r8d, edi; Size
0x18000c4b4  mov     [rbp+1020h+var_B50], r13w
0x18000c4bc  xor     edx, edx; Val
0x18000c4be  lea     rcx, [rbp+1020h+var_B4E]; void *
0x18000c4c5  call    memset_0
0x18000c4ca  xorps   xmm0, xmm0
0x18000c4cd  movups  xmmword ptr [rsp+1120h+Handles], xmm0
0x18000c4d2  test    r14, r14
0x18000c4d5  jz      short loc_18000C550
0x18000c4d7  call    IsGetShellWindowPresent
0x18000c4dc  test    al, al
0x18000c4de  jnz     short loc_18000C4E7
0x18000c4e0  mov     ebx, 0C00000BBh
0x18000c4e5  jmp     short loc_18000C501
0x18000c4e7  lea     rdx, [rsp+1120h+dwProcessId]; lpdwProcessId
0x18000c4ec  mov     rcx, r14; hWnd
0x18000c4ef  call    cs:__imp_GetWindowThreadProcessId
0x18000c4f5  mov     r15d, eax
0x18000c4f8  test    eax, eax
0x18000c4fa  jnz     short loc_18000C55F
0x18000c4fc  mov     ebx, 0C000000Dh
0x18000c501  mov     rax, [rbp+1020h+hObject]
0x18000c508  test    rax, rax
0x18000c50b  jz      short loc_18000C516
0x18000c50d  mov     rcx, rax; hObject
0x18000c510  call    cs:__imp_CloseHandle
0x18000c516  mov     rdx, [rbp+1020h+var_5E0]
0x18000c51d  test    rdx, rdx
0x18000c520  jz      short loc_18000C52B
0x18000c522  mov     rcx, rdx; hObject
0x18000c525  call    cs:__imp_CloseHandle
0x18000c52b  mov     eax, ebx
0x18000c52d  mov     rcx, [rbp+1020h+var_50]
0x18000c534  xor     rcx, rsp; StackCookie
0x18000c537  call    __security_check_cookie
0x18000c53c  add     rsp, 10E8h
0x18000c543  pop     r15
0x18000c545  pop     r14
0x18000c547  pop     r13
0x18000c549  pop     r12
0x18000c54b  pop     rdi
0x18000c54c  pop     rsi
0x18000c54d  pop     rbx
0x18000c54e  pop     rbp
0x18000c54f  retn
0x18000c550  test    rsi, rsi
0x18000c553  jz      short loc_18000C4FC
0x18000c555  test    ebx, ebx
0x18000c557  jz      short loc_18000C4FC
0x18000c559  mov     eax, [rsi]
0x18000c55b  mov     [rsp+1120h+dwProcessId], eax
0x18000c55f  mov     edi, [rbp+1020h+arg_20]
0x18000c565  test    edi, 0FFE00000h
0x18000c56b  jnz     short loc_18000C4FC
0x18000c56d  test    r14, r14
0x18000c570  jnz     short loc_18000C57B
0x18000c572  test    rsi, rsi
0x18000c575  jz      short loc_18000C4FC
0x18000c577  test    ebx, ebx
0x18000c579  jz      short loc_18000C4FC
0x18000c57b  cmp     ebx, 10h
0x18000c57e  jbe     short loc_18000C58A
0x18000c580  mov     ebx, 0C000042Bh
0x18000c585  jmp     loc_18000C501
0x18000c58a  mov     r12d, 578h
0x18000c590  lea     rcx, [rsp+1120h+Src]; void *
0x18000c595  mov     r8d, r12d; Size
0x18000c598  xor     edx, edx; Val
0x18000c59a  call    memset_0
0x18000c59f  lea     rcx, [rbp+1020h+var_5D0]; void *
0x18000c5a6  mov     r8d, r12d; Size
0x18000c5a9  lea     rdx, [rsp+1120h+Src]; Src
0x18000c5ae  call    memcpy_0
0x18000c5b3  mov     [rbp+1020h+var_5D0], 5780550h
0x18000c5bd  mov     [rbp+1020h+var_5A8], 10000000h
0x18000c5c7  mov     [rbp+1020h+var_560], r15d
0x18000c5ce  mov     [rbp+1020h+var_488], r14
0x18000c5d5  call    cs:__imp_GetTickCount
0x18000c5db  mov     [rbp+1020h+var_6C], eax
0x18000c5e1  mov     r14d, 1
0x18000c5e7  test    rsi, rsi
0x18000c5ea  jz      short loc_18000C608
0x18000c5ec  test    ebx, ebx
0x18000c5ee  jz      short loc_18000C608
0x18000c5f0  mov     r8, rbx
0x18000c5f3  lea     rcx, [rbp+1020h+var_5A0]; void *
0x18000c5fa  shl     r8, 2; Size
0x18000c5fe  mov     rdx, rsi; Src
0x18000c601  call    memcpy_0
0x18000c606  jmp     short loc_18000C615
0x18000c608  mov     eax, [rsp+1120h+dwProcessId]
0x18000c60c  mov     ebx, r14d
0x18000c60f  mov     [rbp+1020h+var_5A0], eax
0x18000c615  test    dil, 2
0x18000c619  jz      short loc_18000C675
0x18000c61b  mov     rcx, [rbp+1020h+arg_28]
0x18000c622  test    rcx, rcx
0x18000c625  jz      short loc_18000C66D
0x18000c627  mov     edx, 104h
0x18000c62c  lea     rax, [rbp+1020h+var_278]
0x18000c633  mov     r8d, 7FFFFFFEh
0x18000c639  test    r8, r8
0x18000c63c  jz      short loc_18000C65C
0x18000c63e  movzx   r9d, word ptr [rcx]
0x18000c642  test    r9w, r9w
0x18000c646  jz      short loc_18000C65C
0x18000c648  mov     [rax], r9w
0x18000c64c  add     rcx, 2
0x18000c650  add     rax, 2
0x18000c654  sub     r8, r14
0x18000c657  sub     rdx, r14
0x18000c65a  jnz     short loc_18000C639
0x18000c65c  test    rdx, rdx
0x18000c65f  lea     rcx, [rax-2]
0x18000c663  cmovnz  rcx, rax
0x18000c667  mov     [rcx], r13w
0x18000c66b  jmp     short loc_18000C675
0x18000c66d  mov     [rbp+1020h+var_278], r13w
0x18000c675  mov     [rsp+1120h+nLengthNeeded], r13d
0x18000c67a  mov     [rbp+1020h+pvInfo], r13w
0x18000c682  call    IsGetThreadDesktopPresent
0x18000c687  test    al, al
0x18000c689  jz      short loc_18000C6CF
0x18000c68b  call    IsGetThreadDesktopPresent
0x18000c690  test    al, al
0x18000c692  jz      short loc_18000C6CF
0x18000c694  call    GetCurrentThreadId_0
0x18000c699  mov     ecx, eax; dwThreadId
0x18000c69b  call    cs:__imp_GetThreadDesktop
0x18000c6a1  test    rax, rax
0x18000c6a4  jz      short loc_18000C6CF
0x18000c6a6  lea     rcx, [rsp+1120h+nLengthNeeded]
0x18000c6ab  mov     r9d, 208h; nLength
0x18000c6b1  mov     [rsp+1120h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x18000c6b6  lea     r8, [rbp+1020h+pvInfo]; pvInfo
0x18000c6bd  mov     rcx, rax; hObj
0x18000c6c0  mov     edx, 2; nIndex
0x18000c6c5  call    cs:__imp_GetUserObjectInformationW
0x18000c6cb  test    eax, eax
0x18000c6cd  jnz     short loc_18000C6D7
0x18000c6cf  mov     [rbp+1020h+pvInfo], r13w
0x18000c6d7  mov     [rbp+1020h+var_70], edi
0x18000c6dd  test    edi, 84000h
0x18000c6e3  jnz     short loc_18000C70D
0x18000c6e5  lea     rax, [rbp+1020h+var_5A0]
0x18000c6ec  lea     r8, [rbp+1020h+var_4C8]
0x18000c6f3  mov     [rsp+1120h+lpnLengthNeeded], rax
0x18000c6f8  lea     rdx, [rbp+1020h+var_4D8]
0x18000c6ff  lea     rcx, [rbp+1020h+var_558]
0x18000c706  call    RhpCaptureSnapshots
0x18000c70b  jmp     short loc_18000C74D
0x18000c70d  mov     ecx, r13d
0x18000c710  test    ebx, ebx
0x18000c712  jz      short loc_18000C74D
0x18000c714  mov     edx, edi
0x18000c716  and     edx, 80000h
0x18000c71c  test    edx, edx
0x18000c71e  jz      short loc_18000C72F
0x18000c720  mov     eax, ecx
0x18000c722  mov     [rbp+rax*4+1020h+var_4C8], 0C0000240h
0x18000c72d  jmp     short loc_18000C746
0x18000c72f  test    ecx, ecx
0x18000c731  jz      short loc_18000C739
0x18000c733  bt      edi, 14h
0x18000c737  jnb     short loc_18000C746
0x18000c739  mov     eax, ecx
0x18000c73b  mov     [rbp+rax*4+1020h+var_4C8], 0C0000002h
0x18000c746  add     ecx, r14d
0x18000c749  cmp     ecx, ebx
0x18000c74b  jb      short loc_18000C71C
0x18000c74d  lea     r8, [rbp+1020h+var_B50]; struct _WERSVC_MSG *
0x18000c754  lea     rdx, [rbp+1020h+var_5D0]; struct _WERSVC_MSG *
0x18000c75b  lea     rcx, aWindowserrorre; "\\WindowsErrorReportingServicePort"
0x18000c762  call    ?WersvcSendMessage@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z; WersvcSendMessage(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)
0x18000c767  mov     ebx, eax
0x18000c769  mov     rsi, r13
0x18000c76c  mov     rcx, [rbp+rsi*8+1020h+var_558]
0x18000c774  test    rcx, rcx
0x18000c777  jz      short loc_18000C77F
0x18000c779  call    cs:__imp_PssNtFreeSnapshot
0x18000c77f  add     rsi, r14
0x18000c782  cmp     rsi, 10h
0x18000c786  jnz     short loc_18000C76C
0x18000c788  test    ebx, ebx
0x18000c78a  js      loc_18000C501
0x18000c790  cmp     ebx, 102h
0x18000c796  jnz     short loc_18000C7A2
0x18000c798  mov     ebx, 0C0000240h
0x18000c79d  jmp     loc_18000C501
0x18000c7a2  mov     r8d, [rbp+1020h+var_B28]
0x18000c7a9  mov     eax, r8d
0x18000c7ac  sub     eax, 10000001h
0x18000c7b1  jz      short loc_18000C7C5
0x18000c7b3  sub     eax, r14d
0x18000c7b6  jz      loc_18000C883
0x18000c7bc  cmp     eax, 3
0x18000c7bf  jnz     loc_18000C891
0x18000c7c5  mov     rax, [rbp+1020h+hObject]
0x18000c7cc  mov     ecx, r13d
0x18000c7cf  test    rax, rax
0x18000c7d2  jz      short loc_18000C7DC
0x18000c7d4  mov     [rsp+1120h+Handles], rax
0x18000c7d9  mov     ecx, r14d
0x18000c7dc  mov     rdx, [rbp+1020h+var_5E0]
0x18000c7e3  test    rdx, rdx
0x18000c7e6  jz      short loc_18000C7F2
0x18000c7e8  mov     eax, ecx
0x18000c7ea  add     ecx, r14d; nCount
0x18000c7ed  mov     [rsp+rax*8+1120h+Handles], rdx
0x18000c7f2  test    dil, 20h
0x18000c7f6  jz      short loc_18000C815
0x18000c7f8  test    ecx, ecx
0x18000c7fa  jz      short loc_18000C815
0x18000c7fc  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000c800  lea     rdx, [rsp+1120h+Handles]; lpHandles
0x18000c805  xor     r8d, r8d; bWaitAll
0x18000c808  call    cs:__imp_WaitForMultipleObjects
0x18000c80e  mov     r8d, [rbp+1020h+var_B28]
0x18000c815  mov     rbx, [rbp+1020h+hwnd]
0x18000c81c  test    rbx, rbx
0x18000c81f  jz      loc_18000C8F5
0x18000c825  cmp     r8d, 10000005h
0x18000c82c  jnz     loc_18000C8F5
0x18000c832  test    rbx, rbx
0x18000c835  jz      loc_18000C8F5
0x18000c83b  mov     esi, [rsp+1120h+dwProcessId]
0x18000c83f  test    esi, esi
0x18000c841  jz      loc_18000C8F5
0x18000c847  call    IsRegisterWindowMessageWPresent
0x18000c84c  test    al, al
0x18000c84e  jz      loc_18000C8EA
0x18000c854  call    IsChangeWindowMessageFilterExPresent
0x18000c859  test    al, al
0x18000c85b  jz      loc_18000C8EA
0x18000c861  xor     edx, edx; hFile
0x18000c863  lea     rcx, LibFileName; "user32.dll"
0x18000c86a  mov     r8d, 800h; dwFlags
0x18000c870  call    cs:__imp_LoadLibraryExW
0x18000c876  mov     rdi, rax
0x18000c879  test    rax, rax
0x18000c87c  jnz     short loc_18000C89B
0x18000c87e  lea     ecx, [rax+7Eh]
0x18000c881  jmp     short loc_18000C8EF
0x18000c883  mov     ebx, [rbp+1020h+var_B24]
0x18000c889  test    ebx, ebx
0x18000c88b  js      loc_18000C501
0x18000c891  mov     ebx, 0C0000001h
0x18000c896  jmp     loc_18000C501
0x18000c89b  lea     rcx, String; "WerHangRepMessage"
0x18000c8a2  call    cs:__imp_RegisterWindowMessageW
0x18000c8a8  test    eax, eax
0x18000c8aa  jz      short loc_18000C8DF
0x18000c8ac  xor     r9d, r9d; pChangeFilterStruct
0x18000c8af  mov     r8d, r14d; action
0x18000c8b2  mov     edx, eax; message
0x18000c8b4  mov     rcx, rbx; hwnd
0x18000c8b7  call    cs:__imp_ChangeWindowMessageFilterEx
0x18000c8bd  test    eax, eax
0x18000c8bf  jz      short loc_18000C8DF
0x18000c8c1  lea     rdx, aRegistererrorr; "RegisterErrorReportingDialog"
0x18000c8c8  mov     rcx, rdi; hModule
0x18000c8cb  call    GetProcAddress_0
0x18000c8d0  test    rax, rax
0x18000c8d3  jz      short loc_18000C8DF
0x18000c8d5  mov     edx, esi
0x18000c8d7  mov     rcx, rbx
0x18000c8da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8df  mov     rcx, rdi; hLibModule
0x18000c8e2  call    cs:__imp_FreeLibrary
0x18000c8e8  jmp     short loc_18000C8F5
0x18000c8ea  mov     ecx, 7Fh; dwErrCode
0x18000c8ef  call    cs:__imp_SetLastError
0x18000c8f5  mov     ebx, r13d
  ... truncated ...
```
