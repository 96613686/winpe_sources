# CInpagePlugIn::StartCoFireProcess(void)

- ea: `0x18002a8fc`
- end: `0x18002abd2`
- name: `?StartCoFireProcess@CInpagePlugIn@@AEAAJXZ`
- size: `726`
- prototype: `__int64 __fastcall(CInpagePlugIn *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18002abe0`

## callees

- `0x180002890`
- `0x180003474`
- `0x180006684`
- `0x180009ed8`
- `0x18002a8fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002ab43`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002ab43`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18002a98b`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18002a98b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a995`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ab7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a995`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ab7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002aad7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002aae7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ab9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002abae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002aad7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002aae7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ab9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002abae`

## string_xrefs

- `0x18002aa1e`: `%s\system32\cofire.exe`

## pseudocode

```c
__int64 __fastcall CInpagePlugIn::StartCoFireProcess(CInpagePlugIn *this)
{
  UINT WindowsDirectoryW; // eax
  signed int v3; // eax
  signed int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  signed int LastError; // eax
  struct _PROCESS_INFORMATION hObject; // [rsp+50h] [rbp-B0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW v11; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR Buffer[264]; // [rsp+150h] [rbp+50h] BYREF
  WCHAR ApplicationName[264]; // [rsp+360h] [rbp+260h] BYREF

  memset(&hObject, 0, sizeof(hObject));
  memset_0(&v11, 0, sizeof(v11));
  StartupInfo = v11;
  WindowsDirectoryW = GetWindowsDirectoryW(Buffer, 0x104u);
  if ( WindowsDirectoryW )
  {
    if ( WindowsDirectoryW < 0x104 )
    {
      v4 = StringCchPrintfW(ApplicationName, 0x104u, L"%s\\system32\\cofire.exe", Buffer);
      if ( v4 >= 0 )
      {
        v4 = StringCchPrintfW(
               Buffer,
               0x104u,
               L"\"%s\" \"%s\" \"%s\"",
               ApplicationName,
               (char *)this + 568,
               (char *)this + 1088);
        if ( v4 >= 0 )
        {
          StartupInfo.cb = 104;
          if ( hObject.hProcess )
            CloseHandle(hObject.hProcess);
          if ( hObject.hThread )
            CloseHandle(hObject.hThread);
          memset(&hObject, 0, sizeof(hObject));
          if ( CreateProcessW(ApplicationName, Buffer, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &hObject) )
          {
            v4 = 0;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids);
            LastError = GetLastError();
            v4 = LastError;
            if ( LastError > 0 )
              v4 = (unsigned __int16)LastError | 0x80070000;
          }
        }
        else
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v6 = 19;
            goto LABEL_7;
          }
        }
      }
      else
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 18;
          goto LABEL_7;
        }
      }
    }
    else
    {
      v4 = -2147024774;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 17;
        goto LABEL_7;
      }
    }
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 16;
LABEL_7:
      WPP_SF_(v5[2], v6, &WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids);
    }
  }
  if ( hObject.hProcess )
    CloseHandle(hObject.hProcess);
  if ( hObject.hThread )
    CloseHandle(hObject.hThread);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002a8fc  push    rbp
0x18002a8fe  push    rbx
0x18002a8ff  push    rdi
0x18002a900  push    r14
0x18002a902  lea     rbp, [rsp-488h]
0x18002a90a  sub     rsp, 588h
0x18002a911  mov     rax, cs:__security_cookie
0x18002a918  xor     rax, rsp
0x18002a91b  mov     [rbp+4A0h+var_30], rax
0x18002a922  xor     eax, eax
0x18002a924  mov     rdi, rcx
0x18002a927  xorps   xmm0, xmm0
0x18002a92a  mov     [rsp+5A0h+var_540], rax
0x18002a92f  xor     edx, edx; Val
0x18002a931  lea     rcx, [rbp+4A0h+var_4C0]; void *
0x18002a935  movups  xmmword ptr [rsp+5A0h+hObject], xmm0
0x18002a93a  lea     r8d, [rax+68h]; Size
0x18002a93e  call    memset_0
0x18002a943  movups  xmm0, [rbp+4A0h+var_4C0]
0x18002a947  mov     r14d, 104h
0x18002a94d  lea     rcx, [rbp+4A0h+Buffer]; lpBuffer
0x18002a951  movups  xmm1, [rbp+4A0h+var_4B0]
0x18002a955  mov     edx, r14d; uSize
0x18002a958  movaps  xmmword ptr [rsp+5A0h+StartupInfo.cb], xmm0
0x18002a95d  movups  xmm0, [rbp+4A0h+var_4A0]
0x18002a961  movaps  xmmword ptr [rbp+4A0h+StartupInfo.lpDesktop], xmm1
0x18002a965  movups  xmm1, [rbp+4A0h+var_490]
0x18002a969  movaps  xmmword ptr [rbp+4A0h+StartupInfo.dwX], xmm0
0x18002a96d  movups  xmm0, [rbp+4A0h+var_480]
0x18002a971  movaps  xmmword ptr [rbp+4A0h+StartupInfo.dwXCountChars], xmm1
0x18002a975  movups  xmm1, [rbp+4A0h+var_470]
0x18002a979  movaps  xmmword ptr [rbp+4A0h+StartupInfo.wShowWindow], xmm0
0x18002a97d  movsd   xmm0, [rbp+4A0h+var_460]
0x18002a982  movsd   [rbp+4A0h+StartupInfo.hStdError], xmm0
0x18002a987  movaps  xmmword ptr [rbp+4A0h+StartupInfo.hStdInput], xmm1
0x18002a98b  call    cs:__imp_GetWindowsDirectoryW
0x18002a991  test    eax, eax
0x18002a993  jnz     short loc_18002A9E5
0x18002a995  call    cs:__imp_GetLastError
0x18002a99b  mov     ebx, eax
0x18002a99d  test    eax, eax
0x18002a99f  jle     short loc_18002A9AA
0x18002a9a1  movzx   ebx, ax
0x18002a9a4  or      ebx, 80070000h
0x18002a9aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a9b1  lea     rax, WPP_GLOBAL_Control
0x18002a9b8  cmp     rcx, rax
0x18002a9bb  jz      loc_18002AB94
0x18002a9c1  test    byte ptr [rcx+1Ch], 1
0x18002a9c5  jz      loc_18002AB94
0x18002a9cb  mov     edx, 10h
0x18002a9d0  mov     rcx, [rcx+10h]
0x18002a9d4  lea     r8, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids
0x18002a9db  call    WPP_SF_
0x18002a9e0  jmp     loc_18002AB94
0x18002a9e5  cmp     eax, r14d
0x18002a9e8  jb      short loc_18002AA17
0x18002a9ea  mov     ebx, 8007007Ah
0x18002a9ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a9f6  lea     rax, WPP_GLOBAL_Control
0x18002a9fd  cmp     rcx, rax
0x18002aa00  jz      loc_18002AB94
0x18002aa06  test    byte ptr [rcx+1Ch], 1
0x18002aa0a  jz      loc_18002AB94
0x18002aa10  mov     edx, 11h
0x18002aa15  jmp     short loc_18002A9D0
0x18002aa17  lea     r9, [rbp+4A0h+Buffer]
0x18002aa1b  mov     rdx, r14; unsigned __int64
0x18002aa1e  lea     r8, aSSystem32Cofir; "%s\\system32\\cofire.exe"
0x18002aa25  lea     rcx, [rbp+4A0h+ApplicationName]; wchar_t *
0x18002aa2c  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18002aa31  mov     ebx, eax
0x18002aa33  test    eax, eax
0x18002aa35  jns     short loc_18002AA62
0x18002aa37  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aa3e  lea     rax, WPP_GLOBAL_Control
0x18002aa45  cmp     rcx, rax
0x18002aa48  jz      loc_18002AB94
0x18002aa4e  test    byte ptr [rcx+1Ch], 1
0x18002aa52  jz      loc_18002AB94
0x18002aa58  mov     edx, 12h
0x18002aa5d  jmp     loc_18002A9D0
0x18002aa62  lea     rax, [rdi+440h]
0x18002aa69  mov     rdx, r14; unsigned __int64
0x18002aa6c  lea     rcx, [rdi+238h]
0x18002aa73  mov     qword ptr [rsp+5A0h+dwCreationFlags], rax
0x18002aa78  mov     qword ptr [rsp+5A0h+bInheritHandles], rcx
0x18002aa7d  lea     r9, [rbp+4A0h+ApplicationName]
0x18002aa84  lea     rcx, [rbp+4A0h+Buffer]; wchar_t *
0x18002aa88  lea     r8, aSSS_0; "\"%s\" \"%s\" \"%s\""
0x18002aa8f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18002aa94  mov     ebx, eax
0x18002aa96  test    eax, eax
0x18002aa98  jns     short loc_18002AAC5
0x18002aa9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aaa1  lea     rax, WPP_GLOBAL_Control
0x18002aaa8  cmp     rcx, rax
0x18002aaab  jz      loc_18002AB94
0x18002aab1  test    byte ptr [rcx+1Ch], 1
0x18002aab5  jz      loc_18002AB94
0x18002aabb  mov     edx, 13h
0x18002aac0  jmp     loc_18002A9D0
0x18002aac5  mov     rcx, [rsp+5A0h+hObject]; hObject
0x18002aaca  mov     [rsp+5A0h+StartupInfo.cb], 68h ; 'h'
0x18002aad2  test    rcx, rcx
0x18002aad5  jz      short loc_18002AADD
0x18002aad7  call    cs:__imp_CloseHandle
0x18002aadd  mov     rcx, [rsp+5A0h+hObject+8]; hObject
0x18002aae2  test    rcx, rcx
0x18002aae5  jz      short loc_18002AAED
0x18002aae7  call    cs:__imp_CloseHandle
0x18002aaed  xor     eax, eax
0x18002aaef  lea     rdx, [rbp+4A0h+Buffer]; lpCommandLine
0x18002aaf3  mov     [rsp+5A0h+var_540], rax
0x18002aaf8  lea     rcx, [rbp+4A0h+ApplicationName]; lpApplicationName
0x18002aaff  lea     rax, [rsp+5A0h+hObject]
0x18002ab04  xorps   xmm0, xmm0
0x18002ab07  mov     [rsp+5A0h+lpProcessInformation], rax; lpProcessInformation
0x18002ab0c  xor     r9d, r9d; lpThreadAttributes
0x18002ab0f  lea     rax, [rsp+5A0h+StartupInfo]
0x18002ab14  xor     r8d, r8d; lpProcessAttributes
0x18002ab17  mov     [rsp+5A0h+lpStartupInfo], rax; lpStartupInfo
0x18002ab1c  mov     [rsp+5A0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18002ab25  mov     [rsp+5A0h+lpEnvironment], 0; lpEnvironment
0x18002ab2e  mov     [rsp+5A0h+dwCreationFlags], 8000000h; dwCreationFlags
0x18002ab36  mov     [rsp+5A0h+bInheritHandles], 0; bInheritHandles
0x18002ab3e  movups  xmmword ptr [rsp+5A0h+hObject], xmm0
0x18002ab43  call    cs:__imp_CreateProcessW
0x18002ab49  test    eax, eax
0x18002ab4b  jnz     short loc_18002AB92
0x18002ab4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab54  lea     rax, WPP_GLOBAL_Control
0x18002ab5b  cmp     rcx, rax
0x18002ab5e  jz      short loc_18002AB7B
0x18002ab60  test    byte ptr [rcx+1Ch], 1
0x18002ab64  jz      short loc_18002AB7B
0x18002ab66  mov     rcx, [rcx+10h]
0x18002ab6a  lea     r8, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids
0x18002ab71  mov     edx, 14h
0x18002ab76  call    WPP_SF_
0x18002ab7b  call    cs:__imp_GetLastError
0x18002ab81  mov     ebx, eax
0x18002ab83  test    eax, eax
0x18002ab85  jle     short loc_18002AB94
0x18002ab87  movzx   ebx, ax
0x18002ab8a  or      ebx, 80070000h
0x18002ab90  jmp     short loc_18002AB94
0x18002ab92  xor     ebx, ebx
0x18002ab94  mov     rcx, [rsp+5A0h+hObject]; hObject
0x18002ab99  test    rcx, rcx
0x18002ab9c  jz      short loc_18002ABA4
0x18002ab9e  call    cs:__imp_CloseHandle
0x18002aba4  mov     rcx, [rsp+5A0h+hObject+8]; hObject
0x18002aba9  test    rcx, rcx
0x18002abac  jz      short loc_18002ABB4
0x18002abae  call    cs:__imp_CloseHandle
0x18002abb4  mov     eax, ebx
0x18002abb6  mov     rcx, [rbp+4A0h+var_30]
0x18002abbd  xor     rcx, rsp; StackCookie
0x18002abc0  call    __security_check_cookie
0x18002abc5  add     rsp, 588h
0x18002abcc  pop     r14
0x18002abce  pop     rdi
0x18002abcf  pop     rbx
0x18002abd0  pop     rbp
0x18002abd1  retn
```
