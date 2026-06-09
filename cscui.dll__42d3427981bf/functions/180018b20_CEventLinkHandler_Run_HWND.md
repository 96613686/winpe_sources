# CEventLinkHandler::Run(HWND__ *)

- ea: `0x180018b20`
- end: `0x180018c37`
- name: `?Run@CEventLinkHandler@@UEAAJPEAUHWND__@@@Z`
- size: `279`
- prototype: `__int64 __fastcall(CEventLinkHandler *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003c20`
- `0x180006360`
- `0x180008b40`
- `0x180018b20`
- `0x18004c612`
- `0x18004c636`
- `0x18004c670`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x180018bfb`
- `SHELL32!ShellExecuteExW` at `0x180018bfb`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180018b62`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180018b62`

## string_xrefs

- `0x180018bb1`: `%systemroot%\system32\rundll32.exe`
- `0x180018bd6`: `shell32.dll,Control_RunDLL cscui.dll,,1`

## pseudocode

```c
__int64 __fastcall CEventLinkHandler::Run(CEventLinkHandler *this, HWND a2)
{
  const OLECHAR *v2; // rcx
  HRESULT Error; // ebx
  unsigned __int16 *v5; // rdi
  void *v6; // rdx
  __int64 Buf2; // [rsp+20h] [rbp-49h] BYREF
  int v9; // [rsp+28h] [rbp-41h]
  int v10; // [rsp+2Ch] [rbp-3Dh]
  SHELLEXECUTEINFOW pExecInfo; // [rsp+30h] [rbp-39h] BYREF
  GUID pclsid; // [rsp+A0h] [rbp+37h] BYREF

  v2 = (const OLECHAR *)*((_QWORD *)this + 2);
  Error = 0;
  if ( v2 )
  {
    pclsid = 0;
    Error = CLSIDFromString(v2, &pclsid);
    if ( Error >= 0 )
    {
      Buf2 = 0x40DA9740FAC8A598LL;
      v9 = 1332529320;
      v10 = 1656534649;
      if ( !memcmp_0(&pclsid, &Buf2, 0x10u) )
      {
        Buf2 = 0;
        Error = CscUtil_ExpandEnvironmentStringsAlloc(
                  L"%systemroot%\\system32\\rundll32.exe",
                  (unsigned __int16 **)&Buf2);
        if ( Error >= 0 )
        {
          memset_0(&pExecInfo, 0, sizeof(pExecInfo));
          pExecInfo.hwnd = a2;
          v5 = (unsigned __int16 *)Buf2;
          pExecInfo.lpFile = (LPCWSTR)Buf2;
          pExecInfo.lpParameters = L"shell32.dll,Control_RunDLL cscui.dll,,1";
          pExecInfo.cbSize = 112;
          pExecInfo.nShow = 1;
          if ( !ShellExecuteExW(&pExecInfo) )
            Error = ResultFromLastError();
          CscUtil_HeapFree(v5, v6);
        }
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180018b20  mov     [rsp-8+arg_10], rbx
0x180018b25  mov     [rsp-8+arg_18], rdi
0x180018b2a  push    rbp
0x180018b2b  lea     rbp, [rsp-57h]
0x180018b30  sub     rsp, 0C0h
0x180018b37  mov     rax, cs:__security_cookie
0x180018b3e  xor     rax, rsp
0x180018b41  mov     [rbp+57h+var_10], rax
0x180018b45  mov     rcx, [rcx+10h]; lpsz
0x180018b49  xor     ebx, ebx
0x180018b4b  mov     rdi, rdx
0x180018b4e  test    rcx, rcx
0x180018b51  jz      loc_180018C14
0x180018b57  xorps   xmm0, xmm0
0x180018b5a  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180018b5e  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x180018b62  call    cs:__imp_CLSIDFromString
0x180018b68  mov     ebx, eax
0x180018b6a  test    eax, eax
0x180018b6c  js      loc_180018C14
0x180018b72  mov     r8d, 10h; Size
0x180018b78  mov     dword ptr [rbp+57h+Buf2], 0FAC8A598h
0x180018b7f  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180018b83  mov     dword ptr [rbp+57h+Buf2+4], 40DA9740h
0x180018b8a  lea     rcx, [rbp+57h+pclsid]; Buf1
0x180018b8e  mov     [rbp+57h+var_98], 4F6CC8A8h
0x180018b95  mov     [rbp+57h+var_94], 62BCB679h
0x180018b9c  call    memcmp_0
0x180018ba1  test    eax, eax
0x180018ba3  jnz     short loc_180018C14
0x180018ba5  lea     rdx, [rbp+57h+Buf2]; unsigned __int16 **
0x180018ba9  mov     [rbp+57h+Buf2], 0
0x180018bb1  lea     rcx, Src; "%systemroot%\\system32\\rundll32.exe"
0x180018bb8  call    ?CscUtil_ExpandEnvironmentStringsAlloc@@YAJPEBGPEAPEAG@Z; CscUtil_ExpandEnvironmentStringsAlloc(ushort const *,ushort * *)
0x180018bbd  mov     ebx, eax
0x180018bbf  test    eax, eax
0x180018bc1  js      short loc_180018C14
0x180018bc3  xor     edx, edx; Val
0x180018bc5  lea     rcx, [rbp+57h+pExecInfo]; void *
0x180018bc9  lea     r8d, [rdx+70h]; Size
0x180018bcd  call    memset_0
0x180018bd2  mov     [rbp+57h+pExecInfo.hwnd], rdi
0x180018bd6  lea     rax, aShell32DllCont; "shell32.dll,Control_RunDLL cscui.dll,,1"
0x180018bdd  mov     rdi, [rbp+57h+Buf2]
0x180018be1  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x180018be5  mov     [rbp+57h+pExecInfo.lpFile], rdi
0x180018be9  mov     [rbp+57h+pExecInfo.lpParameters], rax
0x180018bed  mov     [rbp+57h+pExecInfo.cbSize], 70h ; 'p'
0x180018bf4  mov     [rbp+57h+pExecInfo.nShow], 1
0x180018bfb  call    cs:__imp_ShellExecuteExW
0x180018c01  test    eax, eax
0x180018c03  jnz     short loc_180018C0C
0x180018c05  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180018c0a  mov     ebx, eax
0x180018c0c  mov     rcx, rdi; lpMem
0x180018c0f  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180018c14  mov     eax, ebx
0x180018c16  mov     rcx, [rbp+57h+var_10]
0x180018c1a  xor     rcx, rsp; StackCookie
0x180018c1d  call    __security_check_cookie
0x180018c22  lea     r11, [rsp+0C0h+var_s0]
0x180018c2a  mov     rbx, [r11+20h]
0x180018c2e  mov     rdi, [r11+28h]
0x180018c32  mov     rsp, r11
0x180018c35  pop     rbp
0x180018c36  retn
```
