# SystemNaturalLanguageGet

- ea: `0x180033da8`
- end: `0x180033e69`
- name: `SystemNaturalLanguageGet`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800339f0`

## callees

- `0x180001710`
- `0x180033da8`
- `0x180036010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180033e4a`
- `KERNEL32!FreeLibrary` at `0x180033e4a`
- `KERNEL32!GetLastError` at `0x180033deb`
- `KERNEL32!GetLastError` at `0x180033e0d`
- `KERNEL32!GetLastError` at `0x180033deb`
- `KERNEL32!GetLastError` at `0x180033e0d`
- `KERNEL32!GetProcAddress` at `0x180033dff`
- `KERNEL32!GetProcAddress` at `0x180033dff`
- `KERNEL32!LoadLibraryW` at `0x180033ddd`
- `KERNEL32!LoadLibraryW` at `0x180033ddd`
- `KERNEL32!GetSystemDefaultLCID` at `0x180033e17`
- `KERNEL32!GetSystemDefaultLCID` at `0x180033e17`

## string_xrefs

- `0x180033dcb`: `mlang.dll`

## pseudocode

```c
__int64 __fastcall SystemNaturalLanguageGet(_WORD *a1)
{
  DWORD LastError; // ebx
  HMODULE LibraryW; // rax
  HMODULE v4; // rdi
  FARPROC ProcAddress; // rsi
  LCID SystemDefaultLCID; // eax
  char v8; // [rsp+20h] [rbp-48h] BYREF
  __int64 v9; // [rsp+21h] [rbp-47h]

  *a1 = 25966;
  LastError = 0;
  v9 = 0;
  v8 = 0;
  LibraryW = LoadLibraryW(L"mlang.dll");
  v4 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "LcidToRfc1766A");
    if ( ProcAddress )
    {
      SystemDefaultLCID = GetSystemDefaultLCID();
      ((void (__fastcall *)(_QWORD, char *, __int64))ProcAddress)(SystemDefaultLCID, &v8, 9);
      *a1 = (char)v9 | (unsigned __int16)(v8 << 8);
    }
    else
    {
      LastError = GetLastError();
    }
    FreeLibrary(v4);
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x180033da8  push    rbx
0x180033daa  push    rsi
0x180033dab  push    rdi
0x180033dac  push    r14
0x180033dae  sub     rsp, 48h
0x180033db2  mov     rax, cs:__security_cookie
0x180033db9  xor     rax, rsp
0x180033dbc  mov     [rsp+68h+var_38], rax
0x180033dc1  mov     r14, rcx
0x180033dc4  mov     word ptr [rcx], 656Eh
0x180033dc9  xor     eax, eax
0x180033dcb  lea     rcx, aMlangDll; "mlang.dll"
0x180033dd2  xor     ebx, ebx
0x180033dd4  mov     [rsp+68h+var_47], rax
0x180033dd9  mov     [rsp+68h+var_48], bl
0x180033ddd  call    cs:__imp_LoadLibraryW
0x180033de3  mov     rdi, rax
0x180033de6  test    rax, rax
0x180033de9  jnz     short loc_180033DF5
0x180033deb  call    cs:__imp_GetLastError
0x180033df1  mov     ebx, eax
0x180033df3  jmp     short loc_180033E50
0x180033df5  lea     rdx, aLcidtorfc1766a; "LcidToRfc1766A"
0x180033dfc  mov     rcx, rdi; hModule
0x180033dff  call    cs:__imp_GetProcAddress
0x180033e05  mov     rsi, rax
0x180033e08  test    rax, rax
0x180033e0b  jnz     short loc_180033E17
0x180033e0d  call    cs:__imp_GetLastError
0x180033e13  mov     ebx, eax
0x180033e15  jmp     short loc_180033E47
0x180033e17  call    cs:__imp_GetSystemDefaultLCID
0x180033e1d  mov     r8d, 9
0x180033e23  lea     rdx, [rsp+68h+var_48]
0x180033e28  mov     ecx, eax
0x180033e2a  mov     rax, rsi
0x180033e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e32  movsx   ecx, [rsp+68h+var_48]
0x180033e37  movsx   eax, byte ptr [rsp+68h+var_47]
0x180033e3c  shl     cx, 8
0x180033e40  or      cx, ax
0x180033e43  mov     [r14], cx
0x180033e47  mov     rcx, rdi; hLibModule
0x180033e4a  call    cs:__imp_FreeLibrary
0x180033e50  mov     eax, ebx
0x180033e52  mov     rcx, [rsp+68h+var_38]
0x180033e57  xor     rcx, rsp; StackCookie
0x180033e5a  call    __security_check_cookie
0x180033e5f  add     rsp, 48h
0x180033e63  pop     r14
0x180033e65  pop     rdi
0x180033e66  pop     rsi
0x180033e67  pop     rbx
0x180033e68  retn
```
