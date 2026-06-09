# EnumWindowsProc(HWND__ *,long)

- ea: `0x1001ec10`
- end: `0x1001ec8b`
- name: `?EnumWindowsProc@@YGHPAUHWND__@@J@Z`
- size: `123`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1001ec10`
- `0x10035510`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1001ec55`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1001ec55`
- `USER32!GetClassNameW` at `0x1001ec36`
- `USER32!GetClassNameW` at `0x1001ec36`
- `USER32!SendMessageW` at `0x1001ec6f`
- `USER32!SendMessageW` at `0x1001ec6f`
- `mswstr10!__imp__DBCompareStringW@24` at `0x1001ec5c`
- `mswstr10!__imp__DBCompareStringW@24` at `0x1001ec5c`

## pseudocode

```c
BOOL __stdcall EnumWindowsProc(HWND hWnd, LPARAM a2)
{
  LCID UserDefaultLCID; // eax
  WCHAR ClassName[512]; // [esp+4h] [ebp-404h] BYREF

  if ( GetClassNameW(hWnd, ClassName, 512) )
  {
    UserDefaultLCID = GetUserDefaultLCID();
    if ( DBCompareStringW(UserDefaultLCID, 196609, ClassName, -1, L"XLMAIN", -1) == 2 )
      SendMessageW(hWnd, 0x412u, 0, 0);
  }
  return 1;
}

```

## disassembly

```asm
0x1001ec10  mov     edi, edi
0x1001ec12  push    ebp
0x1001ec13  mov     ebp, esp
0x1001ec15  sub     esp, 404h
0x1001ec1b  mov     eax, ___security_cookie
0x1001ec20  xor     eax, ebp
0x1001ec22  mov     [ebp+var_4], eax
0x1001ec25  push    esi
0x1001ec26  mov     esi, [ebp+hWnd]
0x1001ec29  lea     eax, [ebp+ClassName]
0x1001ec2f  push    200h; nMaxCount
0x1001ec34  push    eax; lpClassName
0x1001ec35  push    esi; hWnd
0x1001ec36  call    ds:__imp__GetClassNameW@12; GetClassNameW(x,x,x)
0x1001ec3c  test    eax, eax
0x1001ec3e  jz      short loc_1001EC75
0x1001ec40  push    0FFFFFFFFh
0x1001ec42  push    offset aXlmain; "XLMAIN"
0x1001ec47  push    0FFFFFFFFh
0x1001ec49  lea     eax, [ebp+ClassName]
0x1001ec4f  push    eax
0x1001ec50  push    30001h
0x1001ec55  call    ds:__imp__GetUserDefaultLCID@0; GetUserDefaultLCID()
0x1001ec5b  push    eax
0x1001ec5c  call    ds:__imp__DBCompareStringW@24; DBCompareStringW(x,x,x,x,x,x)
0x1001ec62  sub     eax, 2
0x1001ec65  jnz     short loc_1001EC75
0x1001ec67  push    eax; lParam
0x1001ec68  push    eax; wParam
0x1001ec69  push    412h; Msg
0x1001ec6e  push    esi; hWnd
0x1001ec6f  call    ds:__imp__SendMessageW@16; SendMessageW(x,x,x,x)
0x1001ec75  mov     ecx, [ebp+var_4]
0x1001ec78  mov     eax, 1
0x1001ec7d  xor     ecx, ebp; StackCookie
0x1001ec7f  pop     esi
0x1001ec80  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001ec85  mov     esp, ebp
0x1001ec87  pop     ebp
0x1001ec88  retn    8
```
