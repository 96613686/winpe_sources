# NfsUpCallpPasswdGroupWatchEtcDir

- ea: `0x140011e80`
- end: `0x140011fc1`
- name: `NfsUpCallpPasswdGroupWatchEtcDir`
- size: `321`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140011614`
- `0x140011968`
- `0x140011e80`
- `0x140018350`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x140011ef5`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140011ef5`
- `KERNEL32!FindFirstChangeNotificationW` at `0x140011f16`
- `KERNEL32!FindFirstChangeNotificationW` at `0x140011f16`
- `KERNEL32!FindCloseChangeNotification` at `0x140011f91`
- `KERNEL32!FindCloseChangeNotification` at `0x140011f91`
- `KERNEL32!FindNextChangeNotification` at `0x140011f67`
- `KERNEL32!FindNextChangeNotification` at `0x140011f67`
- `KERNEL32!GetLastError` at `0x140011ec6`
- `KERNEL32!GetLastError` at `0x140011eff`
- `KERNEL32!GetLastError` at `0x140011f29`
- `KERNEL32!GetLastError` at `0x140011f71`
- `KERNEL32!GetLastError` at `0x140011ec6`
- `KERNEL32!GetLastError` at `0x140011eff`
- `KERNEL32!GetLastError` at `0x140011f29`
- `KERNEL32!GetLastError` at `0x140011f71`
- `KERNEL32!CreateEventW` at `0x140011eb6`
- `KERNEL32!CreateEventW` at `0x140011eb6`
- `KERNEL32!WaitForMultipleObjects` at `0x140011f48`
- `KERNEL32!WaitForMultipleObjects` at `0x140011f48`
- `KERNEL32!CloseHandle` at `0x140011f82`
- `KERNEL32!CloseHandle` at `0x140011f82`

## string_xrefs

- `0x140011eeb`: `%SystemRoot%\System32\drivers\etc`

## pseudocode

```c
__int64 __fastcall NfsUpCallpPasswdGroupWatchEtcDir(__int64 Parameter)
{
  HANDLE EventW; // rax
  char v3; // si
  DWORD LastError; // ebx
  char v5; // bp
  HANDLE v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rcx
  WCHAR Dst[264]; // [rsp+20h] [rbp-238h] BYREF

  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)(Parameter + 64) = EventW;
  if ( EventW == (HANDLE)-1LL )
  {
    v3 = 0;
    LastError = GetLastError();
    if ( LastError )
      return LastError;
  }
  else
  {
    LastError = 0;
    v3 = 1;
  }
  v5 = 0;
  if ( ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\drivers\\etc", Dst, 0x105u)
    || (LastError = GetLastError()) == 0 )
  {
    v6 = FindFirstChangeNotificationW(Dst, 0, 0x1Du);
    *(_QWORD *)(Parameter + 56) = v6;
    if ( v6 == (HANDLE)-1LL )
      LastError = GetLastError();
    else
      v5 = 1;
    if ( !LastError )
    {
      while ( 1 )
      {
        LastError = WaitForMultipleObjects(2u, (const HANDLE *)(Parameter + 56), 0, 0xFFFFFFFF);
        if ( LastError )
          break;
        NfsUpCallpPasswdGroupRefreshPasswdIfNeeded(v7, Parameter);
        NfsUpCallpPasswdGroupRefreshGroupIfNeeded(v8, Parameter);
        if ( !FindNextChangeNotification(*(HANDLE *)(Parameter + 56)) )
        {
          LastError = GetLastError();
          break;
        }
      }
    }
  }
  if ( v3 )
    CloseHandle(*(HANDLE *)(Parameter + 64));
  if ( v5 )
    FindCloseChangeNotification(*(HANDLE *)(Parameter + 56));
  return LastError;
}

```

## disassembly

```asm
0x140011e80  mov     [rsp+arg_8], rbx
0x140011e85  mov     [rsp+arg_10], rbp
0x140011e8a  push    rsi
0x140011e8b  push    rdi
0x140011e8c  push    r14
0x140011e8e  sub     rsp, 240h
0x140011e95  mov     rax, cs:__security_cookie
0x140011e9c  xor     rax, rsp
0x140011e9f  mov     [rsp+258h+var_28], rax
0x140011ea7  xor     r9d, r9d; lpName
0x140011eaa  mov     rdi, rcx
0x140011ead  xor     r8d, r8d; bInitialState
0x140011eb0  xor     ecx, ecx; lpEventAttributes
0x140011eb2  lea     edx, [r9+1]; bManualReset
0x140011eb6  call    cs:__imp_CreateEventW
0x140011ebc  mov     [rdi+40h], rax
0x140011ec0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140011ec4  jnz     short loc_140011EDB
0x140011ec6  call    cs:__imp_GetLastError
0x140011ecc  xor     sil, sil
0x140011ecf  mov     ebx, eax
0x140011ed1  test    eax, eax
0x140011ed3  jnz     loc_140011F97
0x140011ed9  jmp     short loc_140011EE0
0x140011edb  xor     ebx, ebx
0x140011edd  mov     sil, 1
0x140011ee0  mov     r8d, 105h; nSize
0x140011ee6  lea     rdx, [rsp+258h+Dst]; lpDst
0x140011eeb  lea     rcx, aSystemrootSyst_1; "%SystemRoot%\\System32\\drivers\\etc"
0x140011ef2  xor     bpl, bpl
0x140011ef5  call    cs:__imp_ExpandEnvironmentStringsW
0x140011efb  test    eax, eax
0x140011efd  jnz     short loc_140011F0B
0x140011eff  call    cs:__imp_GetLastError
0x140011f05  mov     ebx, eax
0x140011f07  test    eax, eax
0x140011f09  jnz     short loc_140011F79
0x140011f0b  xor     edx, edx; bWatchSubtree
0x140011f0d  lea     rcx, [rsp+258h+Dst]; lpPathName
0x140011f12  lea     r8d, [rdx+1Dh]; dwNotifyFilter
0x140011f16  call    cs:__imp_FindFirstChangeNotificationW
0x140011f1c  lea     r14, [rdi+38h]
0x140011f20  mov     [r14], rax
0x140011f23  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140011f27  jnz     short loc_140011F33
0x140011f29  call    cs:__imp_GetLastError
0x140011f2f  mov     ebx, eax
0x140011f31  jmp     short loc_140011F36
0x140011f33  mov     bpl, 1
0x140011f36  test    ebx, ebx
0x140011f38  jnz     short loc_140011F79
0x140011f3a  xor     r8d, r8d; bWaitAll
0x140011f3d  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x140011f41  mov     rdx, r14; lpHandles
0x140011f44  lea     ecx, [r8+2]; nCount
0x140011f48  call    cs:__imp_WaitForMultipleObjects
0x140011f4e  mov     ebx, eax
0x140011f50  test    eax, eax
0x140011f52  jnz     short loc_140011F79
0x140011f54  mov     rdx, rdi
0x140011f57  call    NfsUpCallpPasswdGroupRefreshPasswdIfNeeded
0x140011f5c  mov     rdx, rdi
0x140011f5f  call    NfsUpCallpPasswdGroupRefreshGroupIfNeeded
0x140011f64  mov     rcx, [r14]; hChangeHandle
0x140011f67  call    cs:__imp_FindNextChangeNotification
0x140011f6d  test    eax, eax
0x140011f6f  jnz     short loc_140011F3A
0x140011f71  call    cs:__imp_GetLastError
0x140011f77  mov     ebx, eax
0x140011f79  test    sil, sil
0x140011f7c  jz      short loc_140011F88
0x140011f7e  mov     rcx, [rdi+40h]; hObject
0x140011f82  call    cs:__imp_CloseHandle
0x140011f88  test    bpl, bpl
0x140011f8b  jz      short loc_140011F97
0x140011f8d  mov     rcx, [rdi+38h]; hChangeHandle
0x140011f91  call    cs:__imp_FindCloseChangeNotification
0x140011f97  mov     eax, ebx
0x140011f99  mov     rcx, [rsp+258h+var_28]
0x140011fa1  xor     rcx, rsp; StackCookie
0x140011fa4  call    __security_check_cookie
0x140011fa9  lea     r11, [rsp+258h+var_18]
0x140011fb1  mov     rbx, [r11+28h]
0x140011fb5  mov     rbp, [r11+30h]
0x140011fb9  mov     rsp, r11
0x140011fbc  pop     r14
0x140011fbe  pop     rdi
0x140011fbf  pop     rsi
0x140011fc0  retn
```
