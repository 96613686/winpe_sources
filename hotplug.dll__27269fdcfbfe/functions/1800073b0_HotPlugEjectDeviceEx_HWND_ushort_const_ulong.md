# HotPlugEjectDeviceEx(HWND__ *,ushort const *,ulong)

- ea: `0x1800073b0`
- end: `0x180007515`
- name: `?HotPlugEjectDeviceEx@@YAKPEAUHWND__@@PEBGK@Z`
- size: `357`
- prototype: `unsigned int __fastcall(HWND hWnd, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800025e0`

## callees

- `0x180003048`
- `0x18000701c`
- `0x18000712c`
- `0x1800073b0`
- `0x180008440`
- `0x18000873a`
- `0x180008760`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800074d0`
- `KERNEL32!CloseHandle` at `0x1800074d0`
- `KERNEL32!WaitForSingleObject` at `0x1800074c6`
- `KERNEL32!WaitForSingleObject` at `0x1800074c6`
- `USER32!GetSystemMetrics` at `0x180007406`
- `USER32!GetSystemMetrics` at `0x180007406`
- `SHELL32!ShellExecuteExW` at `0x1800074b1`
- `SHELL32!ShellExecuteExW` at `0x1800074b1`

## string_xrefs

- `0x18000749c`: `%windir%\System32\DeviceEject.exe`

## pseudocode

```c
unsigned int __fastcall HotPlugEjectDeviceEx(HWND hWnd, const unsigned __int16 *a2, unsigned int a3)
{
  unsigned int v4; // edi
  int v6; // ebx
  __int64 v7; // rcx
  ULONG v8; // eax
  _DWORD v10[4]; // [rsp+30h] [rbp-D0h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v12[464]; // [rsp+B0h] [rbp-50h] BYREF

  v4 = a3 & 0xFFFFFFF9;
  if ( (a3 & 0xFFFFFFF8) != 0 )
  {
    __debugbreak();
    return 19;
  }
  v6 = a3 & 2;
  if ( (a3 & 4) != 0 )
  {
    if ( GetSystemMetrics(4096) )
    {
      v10[0] = 0;
      if ( !(unsigned int)LUAGetUserType(v7, v10) )
      {
        if ( v10[0] )
        {
          if ( (int)StringCchPrintfW(v12, 0x1CCu, L"%x \"%s\" %x", 0, a2, v4) >= 0 )
          {
            memset_0(&pExecInfo, 0, sizeof(pExecInfo));
            v8 = 1536;
            pExecInfo.cbSize = 112;
            pExecInfo.hwnd = 0;
            pExecInfo.nShow = 1;
            if ( !v6 )
              v8 = 1600;
            pExecInfo.fMask = v8;
            pExecInfo.lpFile = L"%windir%\\System32\\DeviceEject.exe";
            pExecInfo.lpParameters = v12;
            if ( ShellExecuteExW(&pExecInfo) )
            {
              if ( !v6 )
              {
                WaitForSingleObject(&pExecInfo.hProcess, 0xFFFFFFFF);
                CloseHandle(pExecInfo.hProcess);
              }
            }
          }
          return 19;
        }
      }
    }
  }
  if ( v6 )
    return HotPlugEjectDeviceAsync(a2, v4);
  else
    return HotPlugEjectDeviceBase(hWnd, a2, a3);
}

```

## disassembly

```asm
0x1800073b0  push    rbp
0x1800073b2  push    rbx
0x1800073b3  push    rsi
0x1800073b4  push    rdi
0x1800073b5  push    r14
0x1800073b7  lea     rbp, [rsp-360h]
0x1800073bf  sub     rsp, 460h
0x1800073c6  mov     rax, cs:__security_cookie
0x1800073cd  xor     rax, rsp
0x1800073d0  mov     [rbp+380h+var_30], rax
0x1800073d7  mov     edi, r8d
0x1800073da  mov     rsi, rdx
0x1800073dd  and     edi, 0FFFFFFF9h
0x1800073e0  mov     r14, rcx
0x1800073e3  test    edi, 0FFFFFFF8h
0x1800073e9  jz      short loc_1800073F1
0x1800073eb  int     3; Trap to Debugger
0x1800073ec  jmp     loc_1800074D6
0x1800073f1  mov     ebx, r8d
0x1800073f4  and     ebx, 2
0x1800073f7  test    r8b, 4
0x1800073fb  jz      loc_1800074DD
0x180007401  mov     ecx, 1000h; nIndex
0x180007406  call    cs:__imp_GetSystemMetrics
0x18000740c  test    eax, eax
0x18000740e  jz      loc_1800074DD
0x180007414  lea     rdx, [rsp+480h+var_450]
0x180007419  mov     [rsp+480h+var_450], 0
0x180007421  call    LUAGetUserType
0x180007426  test    eax, eax
0x180007428  jnz     loc_1800074DD
0x18000742e  cmp     [rsp+480h+var_450], eax
0x180007432  jz      loc_1800074DD
0x180007438  mov     [rsp+480h+var_458], edi
0x18000743c  lea     r8, aXSX; "%x \"%s\" %x"
0x180007443  xor     r9d, r9d
0x180007446  mov     [rsp+480h+var_460], rsi
0x18000744b  mov     edx, 1CCh; unsigned __int64
0x180007450  lea     rcx, [rbp+380h+var_3D0]; unsigned __int16 *
0x180007454  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007459  test    eax, eax
0x18000745b  js      short loc_1800074D6
0x18000745d  mov     edi, 70h ; 'p'
0x180007462  lea     rcx, [rsp+480h+pExecInfo]; void *
0x180007467  mov     r8d, edi; Size
0x18000746a  xor     edx, edx; Val
0x18000746c  call    memset_0
0x180007471  mov     eax, 600h
0x180007476  mov     [rsp+480h+pExecInfo.cbSize], edi
0x18000747a  test    ebx, ebx
0x18000747c  mov     [rsp+480h+pExecInfo.hwnd], 0
0x180007485  mov     [rsp+480h+pExecInfo.nShow], 1
0x18000748d  lea     ecx, [rax+40h]
0x180007490  cmovz   eax, ecx
0x180007493  lea     rcx, [rsp+480h+pExecInfo]; pExecInfo
0x180007498  mov     [rsp+480h+pExecInfo.fMask], eax
0x18000749c  lea     rax, aWindirSystem32; "%windir%\\System32\\DeviceEject.exe"
0x1800074a3  mov     [rsp+480h+pExecInfo.lpFile], rax
0x1800074a8  lea     rax, [rbp+380h+var_3D0]
0x1800074ac  mov     [rsp+480h+pExecInfo.lpParameters], rax
0x1800074b1  call    cs:__imp_ShellExecuteExW
0x1800074b7  test    eax, eax
0x1800074b9  jz      short loc_1800074D6
0x1800074bb  test    ebx, ebx
0x1800074bd  jnz     short loc_1800074D6
0x1800074bf  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800074c2  lea     rcx, [rbp+380h+pExecInfo.hProcess]; hHandle
0x1800074c6  call    cs:__imp_WaitForSingleObject
0x1800074cc  mov     rcx, [rbp+380h+pExecInfo.hProcess]; hObject
0x1800074d0  call    cs:__imp_CloseHandle
0x1800074d6  mov     eax, 13h
0x1800074db  jmp     short loc_1800074F8
0x1800074dd  test    ebx, ebx
0x1800074df  jz      short loc_1800074ED
0x1800074e1  mov     edx, edi; unsigned int
0x1800074e3  mov     rcx, rsi; unsigned __int16 *
0x1800074e6  call    ?HotPlugEjectDeviceAsync@@YAKPEBGK@Z; HotPlugEjectDeviceAsync(ushort const *,ulong)
0x1800074eb  jmp     short loc_1800074F8
0x1800074ed  mov     rdx, rsi; unsigned __int16 *
0x1800074f0  mov     rcx, r14; hWnd
0x1800074f3  call    ?HotPlugEjectDeviceBase@@YAKPEAUHWND__@@PEBGK@Z; HotPlugEjectDeviceBase(HWND__ *,ushort const *,ulong)
0x1800074f8  mov     rcx, [rbp+380h+var_30]
0x1800074ff  xor     rcx, rsp; StackCookie
0x180007502  call    __security_check_cookie
0x180007507  add     rsp, 460h
0x18000750e  pop     r14
0x180007510  pop     rdi
0x180007511  pop     rsi
0x180007512  pop     rbx
0x180007513  pop     rbp
0x180007514  retn
```
