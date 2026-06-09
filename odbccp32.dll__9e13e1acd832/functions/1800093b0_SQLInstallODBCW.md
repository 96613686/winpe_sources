# SQLInstallODBCW

- ea: `0x1800093b0`
- end: `0x18000945d`
- name: `SQLInstallODBCW`
- size: `173`
- prototype: `BOOL __stdcall(HWND, LPCWSTR, LPCWSTR, LPCWSTR)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000f5e0`

## callees

- `0x1800093b0`
- `0x180014ae0`

## import_xrefs

- `USER32!MessageBoxW` at `0x180009430`
- `USER32!MessageBoxW` at `0x180009430`
- `USER32!LoadStringW` at `0x1800093f0`
- `USER32!LoadStringW` at `0x180009411`
- `USER32!LoadStringW` at `0x1800093f0`
- `USER32!LoadStringW` at `0x180009411`
- `KERNEL32!LeaveCriticalSection` at `0x18000943d`
- `KERNEL32!LeaveCriticalSection` at `0x18000943d`
- `KERNEL32!EnterCriticalSection` at `0x1800093d0`
- `KERNEL32!EnterCriticalSection` at `0x1800093d0`

## pseudocode

```c
BOOL __stdcall SQLInstallODBCW(HWND a1, LPCWSTR a2, LPCWSTR a3, LPCWSTR a4)
{
  WCHAR Caption[128]; // [rsp+20h] [rbp-378h] BYREF
  WCHAR Buffer[304]; // [rsp+120h] [rbp-278h] BYREF

  EnterCriticalSection(&g_csInstaller);
  if ( LoadStringW(g_hResDLL, 0x531u, Buffer, 301) && LoadStringW(g_hResDLL, 0x522u, Caption, 128) )
    MessageBoxW(0, Buffer, Caption, 0x10u);
  LeaveCriticalSection(&g_csInstaller);
  return 0;
}

```

## disassembly

```asm
0x1800093b0  sub     rsp, 398h
0x1800093b7  mov     rax, cs:__security_cookie
0x1800093be  xor     rax, rsp
0x1800093c1  mov     [rsp+398h+var_18], rax
0x1800093c9  lea     rcx, g_csInstaller; lpCriticalSection
0x1800093d0  call    cs:__imp_EnterCriticalSection
0x1800093d6  mov     rcx, cs:g_hResDLL; hInstance
0x1800093dd  lea     r8, [rsp+398h+Buffer]; lpBuffer
0x1800093e5  mov     r9d, 12Dh; cchBufferMax
0x1800093eb  mov     edx, 531h; uID
0x1800093f0  call    cs:__imp_LoadStringW
0x1800093f6  test    eax, eax
0x1800093f8  jz      short loc_180009436
0x1800093fa  mov     rcx, cs:g_hResDLL; hInstance
0x180009401  lea     r8, [rsp+398h+Caption]; lpBuffer
0x180009406  mov     r9d, 80h; cchBufferMax
0x18000940c  mov     edx, 522h; uID
0x180009411  call    cs:__imp_LoadStringW
0x180009417  test    eax, eax
0x180009419  jz      short loc_180009436
0x18000941b  mov     r9d, 10h; uType
0x180009421  lea     r8, [rsp+398h+Caption]; lpCaption
0x180009426  lea     rdx, [rsp+398h+Buffer]; lpText
0x18000942e  xor     ecx, ecx; hWnd
0x180009430  call    cs:__imp_MessageBoxW
0x180009436  lea     rcx, g_csInstaller; lpCriticalSection
0x18000943d  call    cs:__imp_LeaveCriticalSection
0x180009443  xor     eax, eax
0x180009445  mov     rcx, [rsp+398h+var_18]
0x18000944d  xor     rcx, rsp; StackCookie
0x180009450  call    __security_check_cookie
0x180009455  add     rsp, 398h
0x18000945c  retn
```
