# CRemoteRingNode::RingDevice(void)

- ea: `0x1800452c0`
- end: `0x180045496`
- name: `?RingDevice@CRemoteRingNode@@AEAAJXZ`
- size: `470`
- prototype: `__int64 __fastcall(CRemoteRingNode *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800451b0`

## callees

- `0x180008de0`
- `0x180009cc4`
- `0x18000f0c8`
- `0x18001a014`
- `0x18002031c`
- `0x180023fa0`
- `0x18002d994`
- `0x1800452c0`
- `0x18004549c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800453dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800453dc`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800453cc`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800453cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800453fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004540d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800453fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004540d`
- `OLEAUT32!__imp_SysAllocString` at `0x180045366`
- `OLEAUT32!__imp_SysAllocString` at `0x180045366`
- `OLEAUT32!__imp_SysFreeString` at `0x180045437`
- `OLEAUT32!__imp_SysFreeString` at `0x180045437`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045423`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045423`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180045326`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180045326`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRemoteRingNode::RingDevice(CRemoteRingNode *this)
{
  WCHAR *v1; // rdi
  int v2; // ebx
  const OLECHAR *v3; // rax
  const WCHAR *v4; // rax
  signed int LastError; // eax
  int v6; // edx
  int v7; // r8d
  int v8; // ecx
  PWSTR ppszPath; // [rsp+50h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v13[32]; // [rsp+E0h] [rbp-20h] BYREF

  v1 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  ppszPath = 0;
  std::wstring::wstring(v13);
  v2 = SHGetKnownFolderPath(&FOLDERID_SystemProgramsRoot, 0, 0, &ppszPath);
  if ( v2 >= 0 )
  {
    std::wstring::operator=(v13, ppszPath);
    std::wstring::append(v13, L"\\EnterpriseRing\\EnterpriseRing.exe");
    v3 = (const OLECHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
    v1 = SysAllocString(v3);
    if ( v1 )
    {
      v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
      if ( !CreateProcessW(v4, v1, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      v2 = -2147024882;
    }
  }
  CloseHandle(ProcessInformation.hProcess);
  CloseHandle(ProcessInformation.hThread);
  v8 = (int)ppszPath;
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
  if ( v1 )
    SysFreeString(v1);
  if ( v2 < 0 && (Microsoft_WindowsPhone_RemoteLockRingCsps_ProviderEnableBits & 2) != 0 )
    McTemplateU0ssqd_EventWriteTransfer(v8, v6, v7, (unsigned int)"CRemoteRingNode::RingDevice", 12, v2);
  std::wstring::~wstring(v13);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800452c0  mov     [rsp-8+arg_0], rbx
0x1800452c5  mov     [rsp-8+arg_8], rdi
0x1800452ca  push    rbp
0x1800452cb  lea     rbp, [rsp-10h]
0x1800452d0  sub     rsp, 110h
0x1800452d7  mov     rax, cs:__security_cookie
0x1800452de  xor     rax, rsp
0x1800452e1  mov     [rbp+10h+var_10], rax
0x1800452e5  xor     edi, edi
0x1800452e7  xorps   xmm0, xmm0
0x1800452ea  xor     eax, eax
0x1800452ec  movups  xmmword ptr [rsp+110h+ProcessInformation.hProcess], xmm0
0x1800452f1  mov     qword ptr [rsp+110h+ProcessInformation.dwProcessId], rax
0x1800452f6  xor     edx, edx; Val
0x1800452f8  lea     r8d, [rdi+68h]; Size
0x1800452fc  lea     rcx, [rsp+110h+StartupInfo]; void *
0x180045301  call    memset_0
0x180045306  mov     [rsp+110h+ppszPath], rdi
0x18004530b  lea     rcx, [rbp+10h+var_30]
0x18004530f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180045314  nop
0x180045315  lea     r9, [rsp+110h+ppszPath]; ppszPath
0x18004531a  xor     r8d, r8d; hToken
0x18004531d  xor     edx, edx; dwFlags
0x18004531f  lea     rcx, FOLDERID_SystemProgramsRoot; rfid
0x180045326  call    cs:__imp_SHGetKnownFolderPath
0x18004532d  nop     dword ptr [rax+rax+00h]
0x180045332  mov     ebx, eax
0x180045334  test    eax, eax
0x180045336  js      loc_1800453F7
0x18004533c  mov     rdx, [rsp+110h+ppszPath]
0x180045341  lea     rcx, [rbp+10h+var_30]
0x180045345  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x18004534a  lea     rdx, aEnterprisering; "\\EnterpriseRing\\EnterpriseRing.exe"
0x180045351  lea     rcx, [rbp+10h+var_30]
0x180045355  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004535a  lea     rcx, [rbp+10h+var_30]
0x18004535e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180045363  mov     rcx, rax; psz
0x180045366  call    cs:__imp_SysAllocString
0x18004536d  nop     dword ptr [rax+rax+00h]
0x180045372  mov     rdi, rax
0x180045375  test    rax, rax
0x180045378  jnz     short loc_180045381
0x18004537a  mov     ebx, 8007000Eh
0x18004537f  jmp     short loc_1800453F7
0x180045381  lea     rcx, [rbp+10h+var_30]
0x180045385  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004538a  mov     rcx, rax; lpApplicationName
0x18004538d  lea     rax, [rsp+110h+ProcessInformation]
0x180045392  mov     [rsp+110h+lpProcessInformation], rax; lpProcessInformation
0x180045397  lea     rax, [rsp+110h+StartupInfo]
0x18004539c  mov     [rsp+110h+lpStartupInfo], rax; lpStartupInfo
0x1800453a1  mov     [rsp+110h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1800453aa  mov     [rsp+110h+lpEnvironment], 0; lpEnvironment
0x1800453b3  mov     [rsp+110h+dwCreationFlags], 0; dwCreationFlags
0x1800453bb  mov     [rsp+110h+bInheritHandles], 0; bInheritHandles
0x1800453c3  xor     r9d, r9d; lpThreadAttributes
0x1800453c6  xor     r8d, r8d; lpProcessAttributes
0x1800453c9  mov     rdx, rdi; lpCommandLine
0x1800453cc  call    cs:__imp_CreateProcessW
0x1800453d3  nop     dword ptr [rax+rax+00h]
0x1800453d8  test    eax, eax
0x1800453da  jnz     short loc_1800453F7
0x1800453dc  call    cs:__imp_GetLastError
0x1800453e3  nop     dword ptr [rax+rax+00h]
0x1800453e8  mov     ebx, eax
0x1800453ea  test    eax, eax
0x1800453ec  jle     short loc_1800453F7
0x1800453ee  movzx   ebx, ax
0x1800453f1  or      ebx, 80070000h
0x1800453f7  mov     rcx, [rsp+110h+ProcessInformation.hProcess]; hObject
0x1800453fc  call    cs:__imp_CloseHandle
0x180045403  nop     dword ptr [rax+rax+00h]
0x180045408  mov     rcx, [rsp+110h+ProcessInformation.hThread]; hObject
0x18004540d  call    cs:__imp_CloseHandle
0x180045414  nop     dword ptr [rax+rax+00h]
0x180045419  mov     rcx, [rsp+110h+ppszPath]; pv
0x18004541e  test    rcx, rcx
0x180045421  jz      short loc_18004542F
0x180045423  call    cs:__imp_CoTaskMemFree
0x18004542a  nop     dword ptr [rax+rax+00h]
0x18004542f  test    rdi, rdi
0x180045432  jz      short loc_180045443
0x180045434  mov     rcx, rdi; bstrString
0x180045437  call    cs:__imp_SysFreeString
0x18004543e  nop     dword ptr [rax+rax+00h]
0x180045443  test    ebx, ebx
0x180045445  jns     short loc_180045469
0x180045447  test    cs:Microsoft_WindowsPhone_RemoteLockRingCsps_ProviderEnableBits, 2
0x18004544e  jz      short loc_180045469
0x180045450  mov     [rsp+110h+dwCreationFlags], ebx
0x180045454  mov     [rsp+110h+bInheritHandles], 10Ch
0x18004545c  lea     r9, aCremoteringnod_2; "CRemoteRingNode::RingDevice"
0x180045463  call    McTemplateU0ssqd_EventWriteTransfer
0x180045468  nop
0x180045469  lea     rcx, [rbp+10h+var_30]
0x18004546d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180045472  mov     eax, ebx
0x180045474  mov     rcx, [rbp+10h+var_10]
0x180045478  xor     rcx, rsp; StackCookie
0x18004547b  call    __security_check_cookie
0x180045480  lea     r11, [rsp+110h+var_s0]
0x180045488  mov     rbx, [r11+10h]
0x18004548c  mov     rdi, [r11+18h]
0x180045490  mov     rsp, r11
0x180045493  pop     rbp
0x180045494  retn
```
