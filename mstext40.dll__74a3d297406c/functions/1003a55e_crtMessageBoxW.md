# ___crtMessageBoxW

- ea: `0x1003a55e`
- end: `0x1003a744`
- name: `___crtMessageBoxW`
- size: `486`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x10033e83`

## callees

- `0x1002b81a`
- `0x10030347`
- `0x1003a55e`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1003a5b8`
- `KERNEL32!GetLastError` at `0x1003a5b8`
- `KERNEL32!LoadLibraryExW` at `0x1003a5ac`
- `KERNEL32!LoadLibraryExW` at `0x1003a5ce`
- `KERNEL32!LoadLibraryExW` at `0x1003a5ac`
- `KERNEL32!LoadLibraryExW` at `0x1003a5ce`
- `KERNEL32!IsDebuggerPresent` at `0x1003a651`
- `KERNEL32!IsDebuggerPresent` at `0x1003a651`
- `KERNEL32!EncodePointer` at `0x1003a586`
- `KERNEL32!EncodePointer` at `0x1003a5f3`
- `KERNEL32!EncodePointer` at `0x1003a607`
- `KERNEL32!EncodePointer` at `0x1003a61b`
- `KERNEL32!EncodePointer` at `0x1003a62f`
- `KERNEL32!EncodePointer` at `0x1003a647`
- `KERNEL32!EncodePointer` at `0x1003a572`
- `KERNEL32!DecodePointer` at `0x1003a681`
- `KERNEL32!DecodePointer` at `0x1003a6a3`
- `KERNEL32!DecodePointer` at `0x1003a6ae`
- `KERNEL32!DecodePointer` at `0x1003a6f3`
- `KERNEL32!DecodePointer` at `0x1003a70b`
- `KERNEL32!DecodePointer` at `0x1003a71f`
- `KERNEL32!DecodePointer` at `0x1003a681`
- `KERNEL32!DecodePointer` at `0x1003a690`
- `KERNEL32!OutputDebugStringW` at `0x1003a663`
- `KERNEL32!OutputDebugStringW` at `0x1003a663`
- `KERNEL32!GetProcAddress` at `0x1003a5e4`
- `KERNEL32!GetProcAddress` at `0x1003a600`
- `KERNEL32!GetProcAddress` at `0x1003a614`
- `KERNEL32!GetProcAddress` at `0x1003a628`
- `KERNEL32!GetProcAddress` at `0x1003a640`
- `KERNEL32!GetProcAddress` at `0x1003a5e4`
- `KERNEL32!GetProcAddress` at `0x1003a600`
- `KERNEL32!GetProcAddress` at `0x1003a614`
- `KERNEL32!GetProcAddress` at `0x1003a628`
- `KERNEL32!GetProcAddress` at `0x1003a640`

## string_xrefs

- `0x1003a5a7`: `USER32.DLL`
- `0x1003a5c9`: `USER32.DLL`

## pseudocode

```c
int __cdecl __crtMessageBoxW(const WCHAR *a1, int a2, int a3)
{
  int v3; // esi
  PVOID v4; // edi
  HMODULE Library; // edi
  int (__stdcall *MessageBoxW)(HWND, LPCWSTR, LPCWSTR, UINT); // eax
  HWND (__stdcall *GetActiveWindow)(); // eax
  HWND (__stdcall *GetLastActivePopup)(HWND); // eax
  BOOL (__stdcall *GetUserObjectInformationW)(HANDLE, int, PVOID, DWORD, LPDWORD); // eax
  HWINSTA (__stdcall *GetProcessWindowStation)(); // eax
  PVOID v12; // eax
  int v13; // eax
  int v14; // edi
  int (*v15)(void); // eax
  int (__stdcall *v16)(int); // eax
  int (__stdcall *v17)(int, LPCWSTR, int, int); // eax
  _BYTE v19[4]; // [esp+Ch] [ebp-24h] BYREF
  int v20; // [esp+10h] [ebp-20h]
  LPCWSTR lpOutputString; // [esp+14h] [ebp-1Ch]
  int (__stdcall *v22)(_DWORD, _DWORD, _DWORD, _DWORD, _DWORD); // [esp+18h] [ebp-18h]
  int (*IsPackagedApp)(void); // [esp+1Ch] [ebp-14h]
  _BYTE v24[12]; // [esp+20h] [ebp-10h] BYREF

  lpOutputString = a1;
  v3 = 0;
  v20 = a2;
  v4 = EncodePointer(0);
  v22 = (int (__stdcall *)(_DWORD, _DWORD, _DWORD, _DWORD, _DWORD))v4;
  IsPackagedApp = (int (*)(void))__crtIsPackagedApp();
  if ( !dword_10045154 )
  {
    Library = LoadLibraryExW(L"USER32.DLL", 0, 0x800u);
    if ( !Library )
    {
      if ( GetLastError() != 87 )
        return 0;
      Library = LoadLibraryExW(L"USER32.DLL", 0, 0);
      if ( !Library )
        return 0;
    }
    MessageBoxW = (int (__stdcall *)(HWND, LPCWSTR, LPCWSTR, UINT))GetProcAddress(Library, "MessageBoxW");
    if ( !MessageBoxW )
      return 0;
    dword_10045154 = EncodePointer(MessageBoxW);
    GetActiveWindow = (HWND (__stdcall *)())GetProcAddress(Library, "GetActiveWindow");
    dword_10045158 = EncodePointer(GetActiveWindow);
    GetLastActivePopup = (HWND (__stdcall *)(HWND))GetProcAddress(Library, "GetLastActivePopup");
    dword_1004515C = EncodePointer(GetLastActivePopup);
    GetUserObjectInformationW = (BOOL (__stdcall *)(HANDLE, int, PVOID, DWORD, LPDWORD))GetProcAddress(
                                                                                          Library,
                                                                                          "GetUserObjectInformationW");
    dword_10045164 = EncodePointer(GetUserObjectInformationW);
    if ( dword_10045164 )
    {
      GetProcessWindowStation = (HWINSTA (__stdcall *)())GetProcAddress(Library, "GetProcessWindowStation");
      dword_10045160 = EncodePointer(GetProcessWindowStation);
    }
    v4 = v22;
  }
  if ( IsDebuggerPresent() )
  {
    if ( lpOutputString )
      OutputDebugStringW(lpOutputString);
    if ( IsPackagedApp )
      return 4;
  }
  else if ( IsPackagedApp )
  {
    DecodePointer(dword_10045154);
    return 3;
  }
  if ( dword_10045160 == v4
    || dword_10045164 == v4
    || (IsPackagedApp = (int (*)(void))DecodePointer(dword_10045160),
        v12 = DecodePointer(dword_10045164),
        v22 = (int (__stdcall *)(_DWORD, _DWORD, _DWORD, _DWORD, _DWORD))v12,
        !IsPackagedApp)
    || !v12
    || (v13 = IsPackagedApp()) != 0 && v22(v13, 1, v24, 12, v19) && (v24[8] & 1) != 0 )
  {
    if ( dword_10045158 != v4 )
    {
      v15 = (int (*)(void))DecodePointer(dword_10045158);
      if ( v15 )
      {
        v3 = v15();
        if ( v3 )
        {
          if ( dword_1004515C != v4 )
          {
            v16 = (int (__stdcall *)(int))DecodePointer(dword_1004515C);
            if ( v16 )
              v3 = v16(v3);
          }
        }
      }
    }
    v14 = a3;
  }
  else
  {
    v14 = a3 | 0x200000;
  }
  v17 = (int (__stdcall *)(int, LPCWSTR, int, int))DecodePointer(dword_10045154);
  if ( v17 )
    return v17(v3, lpOutputString, v20, v14);
  return 0;
}

```

## disassembly

```asm
0x1003a55e  push    ebp
0x1003a55f  mov     ebp, esp
0x1003a561  sub     esp, 24h
0x1003a564  mov     eax, ___security_cookie
0x1003a569  xor     eax, ebp
0x1003a56b  mov     [ebp+var_4], eax
0x1003a56e  mov     eax, [ebp+arg_0]
0x1003a571  push    ebx
0x1003a572  mov     ebx, ds:__imp__EncodePointer@4; EncodePointer(x)
0x1003a578  push    esi
0x1003a579  push    edi
0x1003a57a  mov     [ebp+lpOutputString], eax
0x1003a57d  xor     esi, esi
0x1003a57f  mov     eax, [ebp+arg_4]
0x1003a582  push    esi; Ptr
0x1003a583  mov     [ebp+var_20], eax
0x1003a586  call    ebx ; EncodePointer(x); EncodePointer(x)
0x1003a588  mov     edi, eax
0x1003a58a  mov     [ebp+var_18], edi
0x1003a58d  call    ___crtIsPackagedApp
0x1003a592  mov     [ebp+var_14], eax
0x1003a595  cmp     dword_10045154, esi
0x1003a59b  jnz     loc_1003A651
0x1003a5a1  push    800h; dwFlags
0x1003a5a6  push    esi; hFile
0x1003a5a7  push    offset aUser32Dll_0; "USER32.DLL"
0x1003a5ac  call    ds:__imp__LoadLibraryExW@12; LoadLibraryExW(x,x,x)
0x1003a5b2  mov     edi, eax
0x1003a5b4  test    edi, edi
0x1003a5b6  jnz     short loc_1003A5DE
0x1003a5b8  call    ds:__imp__GetLastError@0; GetLastError()
0x1003a5be  cmp     eax, 57h ; 'W'
0x1003a5c1  jnz     loc_1003A731
0x1003a5c7  push    esi; dwFlags
0x1003a5c8  push    esi; hFile
0x1003a5c9  push    offset aUser32Dll_0; "USER32.DLL"
0x1003a5ce  call    ds:__imp__LoadLibraryExW@12; LoadLibraryExW(x,x,x)
0x1003a5d4  mov     edi, eax
0x1003a5d6  test    edi, edi
0x1003a5d8  jz      loc_1003A731
0x1003a5de  push    offset aMessageboxw; "MessageBoxW"
0x1003a5e3  push    edi; hModule
0x1003a5e4  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1003a5ea  test    eax, eax
0x1003a5ec  jz      loc_1003A731
0x1003a5f2  push    eax; Ptr
0x1003a5f3  call    ebx ; EncodePointer(x); EncodePointer(x)
0x1003a5f5  push    offset aGetactivewindo; "GetActiveWindow"
0x1003a5fa  push    edi; hModule
0x1003a5fb  mov     dword_10045154, eax
0x1003a600  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1003a606  push    eax; Ptr
0x1003a607  call    ebx ; EncodePointer(x); EncodePointer(x)
0x1003a609  push    offset aGetlastactivep; "GetLastActivePopup"
0x1003a60e  push    edi; hModule
0x1003a60f  mov     dword_10045158, eax
0x1003a614  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1003a61a  push    eax; Ptr
0x1003a61b  call    ebx ; EncodePointer(x); EncodePointer(x)
0x1003a61d  push    offset aGetuserobjecti; "GetUserObjectInformationW"
0x1003a622  push    edi; hModule
0x1003a623  mov     dword_1004515C, eax
0x1003a628  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1003a62e  push    eax; Ptr
0x1003a62f  call    ebx ; EncodePointer(x); EncodePointer(x)
0x1003a631  mov     dword_10045164, eax
0x1003a636  test    eax, eax
0x1003a638  jz      short loc_1003A64E
0x1003a63a  push    offset aGetprocesswind; "GetProcessWindowStation"
0x1003a63f  push    edi; hModule
0x1003a640  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1003a646  push    eax; Ptr
0x1003a647  call    ebx ; EncodePointer(x); EncodePointer(x)
0x1003a649  mov     dword_10045160, eax
0x1003a64e  mov     edi, [ebp+var_18]
0x1003a651  call    ds:__imp__IsDebuggerPresent@0; IsDebuggerPresent()
0x1003a657  test    eax, eax
0x1003a659  jz      short loc_1003A676
0x1003a65b  mov     eax, [ebp+lpOutputString]
0x1003a65e  test    eax, eax
0x1003a660  jz      short loc_1003A669
0x1003a662  push    eax; lpOutputString
0x1003a663  call    ds:__imp__OutputDebugStringW@4; OutputDebugStringW(x)
0x1003a669  cmp     [ebp+var_14], esi
0x1003a66c  jz      short loc_1003A68B
0x1003a66e  push    4
0x1003a670  pop     eax
0x1003a671  jmp     loc_1003A733
0x1003a676  cmp     [ebp+var_14], esi
0x1003a679  jz      short loc_1003A68B
0x1003a67b  push    dword_10045154; Ptr
0x1003a681  call    ds:__imp__DecodePointer@4; DecodePointer(x)
0x1003a687  push    3
0x1003a689  jmp     short loc_1003A670
0x1003a68b  mov     eax, dword_10045160
0x1003a690  mov     ebx, ds:__imp__DecodePointer@4; DecodePointer(x)
0x1003a696  cmp     eax, edi
0x1003a698  jz      short loc_1003A6E9
0x1003a69a  cmp     dword_10045164, edi
0x1003a6a0  jz      short loc_1003A6E9
0x1003a6a2  push    eax; Ptr
0x1003a6a3  call    ebx ; DecodePointer(x); DecodePointer(x)
0x1003a6a5  push    dword_10045164; Ptr
0x1003a6ab  mov     [ebp+var_14], eax
0x1003a6ae  call    ebx ; DecodePointer(x); DecodePointer(x)
0x1003a6b0  mov     ecx, [ebp+var_14]
0x1003a6b3  mov     [ebp+var_18], eax
0x1003a6b6  test    ecx, ecx
0x1003a6b8  jz      short loc_1003A6E9
0x1003a6ba  test    eax, eax
0x1003a6bc  jz      short loc_1003A6E9
0x1003a6be  call    ecx
0x1003a6c0  test    eax, eax
0x1003a6c2  jz      short loc_1003A6DE
0x1003a6c4  lea     ecx, [ebp+var_24]
0x1003a6c7  push    ecx
0x1003a6c8  push    0Ch
0x1003a6ca  lea     ecx, [ebp+var_10]
0x1003a6cd  push    ecx
0x1003a6ce  push    1
0x1003a6d0  push    eax
0x1003a6d1  call    [ebp+var_18]
0x1003a6d4  test    eax, eax
0x1003a6d6  jz      short loc_1003A6DE
0x1003a6d8  test    [ebp+var_8], 1
0x1003a6dc  jnz     short loc_1003A6E9
0x1003a6de  mov     edi, [ebp+arg_8]
0x1003a6e1  or      edi, 200000h
0x1003a6e7  jmp     short loc_1003A719
0x1003a6e9  mov     eax, dword_10045158
0x1003a6ee  cmp     eax, edi
0x1003a6f0  jz      short loc_1003A716
0x1003a6f2  push    eax; Ptr
0x1003a6f3  call    ebx ; DecodePointer(x); DecodePointer(x)
0x1003a6f5  test    eax, eax
0x1003a6f7  jz      short loc_1003A716
0x1003a6f9  call    eax
0x1003a6fb  mov     esi, eax
0x1003a6fd  test    esi, esi
0x1003a6ff  jz      short loc_1003A716
0x1003a701  mov     eax, dword_1004515C
0x1003a706  cmp     eax, edi
0x1003a708  jz      short loc_1003A716
0x1003a70a  push    eax; Ptr
0x1003a70b  call    ebx ; DecodePointer(x); DecodePointer(x)
0x1003a70d  test    eax, eax
0x1003a70f  jz      short loc_1003A716
0x1003a711  push    esi
0x1003a712  call    eax
0x1003a714  mov     esi, eax
0x1003a716  mov     edi, [ebp+arg_8]
0x1003a719  push    dword_10045154; Ptr
0x1003a71f  call    ebx ; DecodePointer(x); DecodePointer(x)
0x1003a721  test    eax, eax
0x1003a723  jz      short loc_1003A731
0x1003a725  push    edi
0x1003a726  push    [ebp+var_20]
0x1003a729  push    [ebp+lpOutputString]
0x1003a72c  push    esi
0x1003a72d  call    eax
0x1003a72f  jmp     short loc_1003A733
0x1003a731  xor     eax, eax
0x1003a733  mov     ecx, [ebp+var_4]
0x1003a736  pop     edi
0x1003a737  pop     esi
0x1003a738  xor     ecx, ebp; StackCookie
0x1003a73a  pop     ebx
0x1003a73b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1003a740  mov     esp, ebp
0x1003a742  pop     ebp
0x1003a743  retn
```
