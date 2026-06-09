# ReportHangInternal

- ea: `0x18000a9c4`
- end: `0x18000ad1e`
- name: `ReportHangInternal`
- size: `858`
- prototype: `__int64 __fastcall(HWND)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180008dfc`

## callees

- `0x180001190`
- `0x18000194a`
- `0x180001962`
- `0x1800019d0`
- `0x1800019dc`
- `0x1800019e8`
- `0x1800019f4`
- `0x180002840`
- `0x180002894`
- `0x1800028e8`
- `0x18000293c`
- `0x18000a9c4`
- `0x18000ad24`
- `0x18000ae54`
- `0x18000b390`
- `0x18000c010`

## import_xrefs

- `ntdll!PssNtFreeSnapshot` at `0x18000ab89`
- `ntdll!PssNtFreeSnapshot` at `0x18000ab89`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000acc4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000acc4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000ac58`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000ac58`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000aab8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000aab8`
- `ext-ms-win-ntuser-gui-l1-3-0!ChangeWindowMessageFilterEx` at `0x18000ac99`
- `ext-ms-win-ntuser-gui-l1-3-0!ChangeWindowMessageFilterEx` at `0x18000ac99`
- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x18000ac83`
- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x18000ac83`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18000aa5f`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18000aa5f`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18000ab22`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18000ab22`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x18000aaf8`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x18000aaf8`

## string_xrefs

- `0x18000ac4b`: `user32.dll`

## pseudocode

```c
__int64 __fastcall ReportHangInternal(HWND a1)
{
  int v2; // ebx
  DWORD WindowThreadProcessId; // ebx
  int v4; // r9d
  DWORD CurrentThreadId_0; // eax
  HDESK ThreadDesktop; // rax
  const wchar_t *v7; // rcx
  unsigned int v8; // r9d
  __int64 i; // rdi
  __int64 v10; // rax
  HWND v11; // rbx
  DWORD v12; // esi
  HMODULE Library; // rdi
  DWORD v14; // ecx
  UINT v15; // eax
  FARPROC RegisterErrorReportingDialog; // rax
  DWORD dwProcessId; // [rsp+30h] [rbp-D0h] BYREF
  DWORD nLengthNeeded; // [rsp+34h] [rbp-CCh] BYREF
  __int128 v20; // [rsp+38h] [rbp-C8h]
  _BYTE Src[1408]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v22; // [rsp+5D0h] [rbp+4D0h] BYREF
  _BYTE v23[38]; // [rsp+5D2h] [rbp+4D2h] BYREF
  int v24; // [rsp+5F8h] [rbp+4F8h]
  int v25; // [rsp+5FCh] [rbp+4FCh]
  HWND hwnd; // [rsp+600h] [rbp+500h]
  HANDLE hObject; // [rsp+B38h] [rbp+A38h]
  HANDLE v28; // [rsp+B40h] [rbp+A40h]
  _DWORD v29[12]; // [rsp+B50h] [rbp+A50h] BYREF
  _DWORD v30[18]; // [rsp+B80h] [rbp+A80h] BYREF
  _QWORD v31[16]; // [rsp+BC8h] [rbp+AC8h] BYREF
  char v32; // [rsp+C48h] [rbp+B48h] BYREF
  char v33; // [rsp+C58h] [rbp+B58h] BYREF
  HWND v34; // [rsp+C98h] [rbp+B98h]
  _WORD pvInfo[520]; // [rsp+CA0h] [rbp+BA0h] BYREF
  int v36; // [rsp+10B0h] [rbp+FB0h]
  DWORD TickCount; // [rsp+10B4h] [rbp+FB4h]

  dwProcessId = 0;
  LOWORD(v29[0]) = 0;
  memset_0((char *)v29 + 2, 0, 0x576u);
  v22 = 0;
  memset_0(v23, 0, 0x576u);
  v20 = 0;
  if ( !a1 )
    goto LABEL_41;
  if ( !(unsigned __int8)IsGetWindowThreadProcessIdPresent() )
  {
    v2 = -1073741637;
    goto LABEL_42;
  }
  WindowThreadProcessId = GetWindowThreadProcessId(a1, &dwProcessId);
  if ( WindowThreadProcessId )
  {
    memset_0(Src, 0, 0x578u);
    memcpy_0(v29, Src, 0x578u);
    v29[0] = 91751760;
    v29[10] = 0x10000000;
    v30[16] = WindowThreadProcessId;
    v34 = a1;
    TickCount = GetTickCount();
    v30[0] = dwProcessId;
    pvInfo[0] = 0;
    nLengthNeeded = 0;
    if ( !(unsigned __int8)IsGetThreadDesktopPresent()
      || !(unsigned __int8)IsGetThreadDesktopPresent()
      || (CurrentThreadId_0 = GetCurrentThreadId_0(), (ThreadDesktop = GetThreadDesktop(CurrentThreadId_0)) == 0)
      || !GetUserObjectInformationW(ThreadDesktop, 2, pvInfo, 0x208u, &nLengthNeeded) )
    {
      pvInfo[0] = 0;
    }
    v36 = 4096;
    RhpCaptureSnapshots((unsigned int)v31, (unsigned int)&v32, (unsigned int)&v33, v4, (__int64)v30);
    v2 = WersvcSendMessage(v7, (struct _WERSVC_MSG *)v29, (struct _WERSVC_MSG *)&v22, v8);
    for ( i = 0; i != 16; ++i )
    {
      if ( v31[i] )
        PssNtFreeSnapshot();
    }
    if ( v2 >= 0 )
    {
      if ( v2 == 258 )
      {
        v2 = -1073741248;
        goto LABEL_42;
      }
      if ( v24 != 268435457 )
      {
        if ( v24 == 268435458 )
        {
          v2 = v25;
          if ( v25 < 0 )
            goto LABEL_42;
        }
        else if ( v24 == 268435461 )
        {
          goto LABEL_20;
        }
        v2 = -1073741823;
        goto LABEL_42;
      }
LABEL_20:
      v10 = 0;
      if ( hObject )
      {
        *(_QWORD *)&v20 = hObject;
        v10 = 1;
      }
      if ( v28 )
        *(_QWORD *)&Src[8 * v10 - 8] = v28;
      v11 = hwnd;
      if ( !hwnd )
        goto LABEL_40;
      if ( v24 != 268435461 )
        goto LABEL_40;
      v12 = dwProcessId;
      if ( !dwProcessId )
        goto LABEL_40;
      if ( (unsigned __int8)IsRegisterWindowMessageWPresent() && (unsigned __int8)IsChangeWindowMessageFilterExPresent() )
      {
        Library = LoadLibraryExW(L"user32.dll", 0, 0x800u);
        if ( Library )
        {
          v15 = RegisterWindowMessageW(L"WerHangRepMessage");
          if ( v15 )
          {
            if ( ChangeWindowMessageFilterEx(v11, v15, 1u, 0) )
            {
              RegisterErrorReportingDialog = GetProcAddress_0(Library, "RegisterErrorReportingDialog");
              if ( RegisterErrorReportingDialog )
                ((void (__fastcall *)(HWND, _QWORD))RegisterErrorReportingDialog)(v11, v12);
            }
          }
          FreeLibrary(Library);
          goto LABEL_40;
        }
        v14 = 126;
      }
      else
      {
        v14 = 127;
      }
      SetLastError_0(v14);
LABEL_40:
      v2 = 0;
    }
  }
  else
  {
LABEL_41:
    v2 = -1073741811;
  }
LABEL_42:
  if ( hObject )
    CloseHandle_0(hObject);
  if ( v28 )
    CloseHandle_0(v28);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000a9c4  push    rbp
0x18000a9c6  push    rbx
0x18000a9c7  push    rsi
0x18000a9c8  push    rdi
0x18000a9c9  lea     rbp, [rsp-0FE8h]
0x18000a9d1  mov     eax, 10E8h
0x18000a9d6  call    _alloca_probe
0x18000a9db  sub     rsp, rax
0x18000a9de  mov     rax, cs:__security_cookie
0x18000a9e5  xor     rax, rsp
0x18000a9e8  mov     [rbp+1000h+var_30], rax
0x18000a9ef  mov     rdi, rcx
0x18000a9f2  mov     [rsp+1100h+dwProcessId], 0
0x18000a9fa  xor     eax, eax
0x18000a9fc  lea     rcx, [rbp+1000h+var_5B0+2]; void *
0x18000aa03  mov     ebx, 576h
0x18000aa08  mov     word ptr [rbp+1000h+var_5B0], ax
0x18000aa0f  mov     r8d, ebx; Size
0x18000aa12  xor     edx, edx; Val
0x18000aa14  call    memset_0
0x18000aa19  xor     eax, eax
0x18000aa1b  lea     rcx, [rbp+1000h+var_B2E]; void *
0x18000aa22  mov     r8d, ebx; Size
0x18000aa25  mov     [rbp+1000h+var_B30], ax
0x18000aa2c  xor     edx, edx; Val
0x18000aa2e  call    memset_0
0x18000aa33  xorps   xmm0, xmm0
0x18000aa36  movups  [rsp+1100h+var_10C8], xmm0
0x18000aa3b  test    rdi, rdi
0x18000aa3e  jz      loc_18000ACDA
0x18000aa44  call    IsGetWindowThreadProcessIdPresent
0x18000aa49  test    al, al
0x18000aa4b  jnz     short loc_18000AA57
0x18000aa4d  mov     ebx, 0C00000BBh
0x18000aa52  jmp     loc_18000ACDF
0x18000aa57  lea     rdx, [rsp+1100h+dwProcessId]; lpdwProcessId
0x18000aa5c  mov     rcx, rdi; hWnd
0x18000aa5f  call    cs:__imp_GetWindowThreadProcessId
0x18000aa65  mov     ebx, eax
0x18000aa67  test    eax, eax
0x18000aa69  jz      loc_18000ACDA
0x18000aa6f  mov     esi, 578h
0x18000aa74  lea     rcx, [rsp+1100h+Src]; void *
0x18000aa79  mov     r8d, esi; Size
0x18000aa7c  xor     edx, edx; Val
0x18000aa7e  call    memset_0
0x18000aa83  lea     rcx, [rbp+1000h+var_5B0]; void *
0x18000aa8a  mov     r8d, esi; Size
0x18000aa8d  lea     rdx, [rsp+1100h+Src]; Src
0x18000aa92  call    memcpy_0
0x18000aa97  mov     [rbp+1000h+var_5B0], 5780550h
0x18000aaa1  mov     [rbp+1000h+var_588], 10000000h
0x18000aaab  mov     [rbp+1000h+var_540], ebx
0x18000aab1  mov     [rbp+1000h+var_468], rdi
0x18000aab8  call    cs:__imp_GetTickCount
0x18000aabe  mov     [rbp+1000h+var_4C], eax
0x18000aac4  mov     eax, [rsp+1100h+dwProcessId]
0x18000aac8  mov     [rbp+1000h+var_580], eax
0x18000aace  xor     eax, eax
0x18000aad0  mov     [rbp+1000h+pvInfo], ax
0x18000aad7  mov     [rsp+1100h+nLengthNeeded], 0
0x18000aadf  call    IsGetThreadDesktopPresent
0x18000aae4  test    al, al
0x18000aae6  jz      short loc_18000AB2C
0x18000aae8  call    IsGetThreadDesktopPresent
0x18000aaed  test    al, al
0x18000aaef  jz      short loc_18000AB2C
0x18000aaf1  call    GetCurrentThreadId_0
0x18000aaf6  mov     ecx, eax; dwThreadId
0x18000aaf8  call    cs:__imp_GetThreadDesktop
0x18000aafe  test    rax, rax
0x18000ab01  jz      short loc_18000AB2C
0x18000ab03  lea     rcx, [rsp+1100h+nLengthNeeded]
0x18000ab08  mov     r9d, 208h; nLength
0x18000ab0e  mov     [rsp+1100h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x18000ab13  lea     r8, [rbp+1000h+pvInfo]; pvInfo
0x18000ab1a  mov     rcx, rax; hObj
0x18000ab1d  mov     edx, 2; nIndex
0x18000ab22  call    cs:__imp_GetUserObjectInformationW
0x18000ab28  test    eax, eax
0x18000ab2a  jnz     short loc_18000AB35
0x18000ab2c  xor     eax, eax
0x18000ab2e  mov     [rbp+1000h+pvInfo], ax
0x18000ab35  lea     rax, [rbp+1000h+var_580]
0x18000ab3c  mov     [rbp+1000h+var_50], 1000h
0x18000ab46  lea     r8, [rbp+1000h+var_4A8]
0x18000ab4d  mov     [rsp+1100h+lpnLengthNeeded], rax
0x18000ab52  lea     rdx, [rbp+1000h+var_4B8]
0x18000ab59  lea     rcx, [rbp+1000h+var_538]
0x18000ab60  call    RhpCaptureSnapshots
0x18000ab65  lea     r8, [rbp+1000h+var_B30]; struct _WERSVC_MSG *
0x18000ab6c  lea     rdx, [rbp+1000h+var_5B0]; struct _WERSVC_MSG *
0x18000ab73  call    ?WersvcSendMessage@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z; WersvcSendMessage(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)
0x18000ab78  mov     ebx, eax
0x18000ab7a  xor     edi, edi
0x18000ab7c  mov     rcx, [rbp+rdi*8+1000h+var_538]
0x18000ab84  test    rcx, rcx
0x18000ab87  jz      short loc_18000AB8F
0x18000ab89  call    cs:__imp_PssNtFreeSnapshot
0x18000ab8f  inc     rdi
0x18000ab92  cmp     rdi, 10h
0x18000ab96  jnz     short loc_18000AB7C
0x18000ab98  test    ebx, ebx
0x18000ab9a  js      loc_18000ACDF
0x18000aba0  cmp     ebx, 102h
0x18000aba6  jnz     short loc_18000ABB2
0x18000aba8  mov     ebx, 0C0000240h
0x18000abad  jmp     loc_18000ACDF
0x18000abb2  mov     eax, [rbp+1000h+var_B08]
0x18000abb8  sub     eax, 10000001h
0x18000abbd  jz      short loc_18000ABD1
0x18000abbf  sub     eax, 1
0x18000abc2  jz      loc_18000AC6B
0x18000abc8  cmp     eax, 3
0x18000abcb  jnz     loc_18000AC75
0x18000abd1  mov     rcx, [rbp+1000h+hObject]
0x18000abd8  xor     eax, eax
0x18000abda  test    rcx, rcx
0x18000abdd  jz      short loc_18000ABE9
0x18000abdf  mov     qword ptr [rsp+1100h+var_10C8], rcx
0x18000abe4  mov     eax, 1
0x18000abe9  mov     rcx, [rbp+1000h+var_5C0]
0x18000abf0  test    rcx, rcx
0x18000abf3  jz      short loc_18000ABFA
0x18000abf5  mov     qword ptr [rsp+rax*8+1100h+var_10C8], rcx
0x18000abfa  mov     rbx, [rbp+1000h+hwnd]
0x18000ac01  test    rbx, rbx
0x18000ac04  jz      loc_18000ACD6
0x18000ac0a  cmp     [rbp+1000h+var_B08], 10000005h
0x18000ac14  jnz     loc_18000ACD6
0x18000ac1a  test    rbx, rbx
0x18000ac1d  jz      loc_18000ACD6
0x18000ac23  mov     esi, [rsp+1100h+dwProcessId]
0x18000ac27  test    esi, esi
0x18000ac29  jz      loc_18000ACD6
0x18000ac2f  call    IsRegisterWindowMessageWPresent
0x18000ac34  test    al, al
0x18000ac36  jz      loc_18000ACCC
0x18000ac3c  call    IsChangeWindowMessageFilterExPresent
0x18000ac41  test    al, al
0x18000ac43  jz      loc_18000ACCC
0x18000ac49  xor     edx, edx; hFile
0x18000ac4b  lea     rcx, LibFileName; "user32.dll"
0x18000ac52  mov     r8d, 800h; dwFlags
0x18000ac58  call    cs:__imp_LoadLibraryExW
0x18000ac5e  mov     rdi, rax
0x18000ac61  test    rax, rax
0x18000ac64  jnz     short loc_18000AC7C
0x18000ac66  lea     ecx, [rax+7Eh]
0x18000ac69  jmp     short loc_18000ACD1
0x18000ac6b  mov     ebx, [rbp+1000h+var_B04]
0x18000ac71  test    ebx, ebx
0x18000ac73  js      short loc_18000ACDF
0x18000ac75  mov     ebx, 0C0000001h
0x18000ac7a  jmp     short loc_18000ACDF
0x18000ac7c  lea     rcx, String; "WerHangRepMessage"
0x18000ac83  call    cs:__imp_RegisterWindowMessageW
0x18000ac89  test    eax, eax
0x18000ac8b  jz      short loc_18000ACC1
0x18000ac8d  xor     r9d, r9d; pChangeFilterStruct
0x18000ac90  mov     edx, eax; message
0x18000ac92  mov     rcx, rbx; hwnd
0x18000ac95  lea     r8d, [r9+1]; action
0x18000ac99  call    cs:__imp_ChangeWindowMessageFilterEx
0x18000ac9f  test    eax, eax
0x18000aca1  jz      short loc_18000ACC1
0x18000aca3  lea     rdx, aRegistererrorr; "RegisterErrorReportingDialog"
0x18000acaa  mov     rcx, rdi; hModule
0x18000acad  call    GetProcAddress_0
0x18000acb2  test    rax, rax
0x18000acb5  jz      short loc_18000ACC1
0x18000acb7  mov     edx, esi
0x18000acb9  mov     rcx, rbx
0x18000acbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acc1  mov     rcx, rdi; hLibModule
0x18000acc4  call    cs:__imp_FreeLibrary
0x18000acca  jmp     short loc_18000ACD6
0x18000accc  mov     ecx, 7Fh; dwErrCode
0x18000acd1  call    SetLastError_0
0x18000acd6  xor     ebx, ebx
0x18000acd8  jmp     short loc_18000ACDF
0x18000acda  mov     ebx, 0C000000Dh
0x18000acdf  mov     rcx, [rbp+1000h+hObject]; hObject
0x18000ace6  test    rcx, rcx
0x18000ace9  jz      short loc_18000ACF0
0x18000aceb  call    CloseHandle_0
0x18000acf0  mov     rcx, [rbp+1000h+var_5C0]; hObject
0x18000acf7  test    rcx, rcx
0x18000acfa  jz      short loc_18000AD01
0x18000acfc  call    CloseHandle_0
0x18000ad01  mov     eax, ebx
0x18000ad03  mov     rcx, [rbp+1000h+var_30]
0x18000ad0a  xor     rcx, rsp; StackCookie
0x18000ad0d  call    __security_check_cookie
0x18000ad12  add     rsp, 10E8h
0x18000ad19  pop     rdi
0x18000ad1a  pop     rsi
0x18000ad1b  pop     rbx
0x18000ad1c  pop     rbp
0x18000ad1d  retn
```
