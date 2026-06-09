# CCMLuaUtil::SetCustomAuthData(ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x1800039c0`
- end: `0x180003aa1`
- name: `?SetCustomAuthData@CCMLuaUtil@@UEAAJPEBG00K@Z`
- size: `225`
- prototype: `__int64 __fastcall(CCMLuaUtil *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800039c0`
- `0x18000440c`
- `0x180004e1c`
- `0x180006010`

## import_xrefs

- `cmutil!CmFree` at `0x180003a71`
- `cmutil!CmFree` at `0x180003a71`
- `KERNEL32!FreeLibrary` at `0x180003a81`
- `KERNEL32!FreeLibrary` at `0x180003a81`
- `KERNEL32!LoadLibraryExW` at `0x1800039e0`
- `KERNEL32!LoadLibraryExW` at `0x1800039e0`
- `KERNEL32!GetProcAddress` at `0x180003a14`
- `KERNEL32!GetProcAddress` at `0x180003a14`
- `KERNEL32!GetLastError` at `0x1800039ee`
- `KERNEL32!GetLastError` at `0x180003a22`
- `KERNEL32!GetLastError` at `0x1800039ee`
- `KERNEL32!GetLastError` at `0x180003a22`

## string_xrefs

- `0x1800039ce`: `RASAPI32.DLL`
- `0x1800039f4`: `LoadLibrary failed in SetCustomAuthData. GLE = %#x`

## pseudocode

```c
__int64 __fastcall CCMLuaUtil::SetCustomAuthData(
        CCMLuaUtil *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5)
{
  HMODULE Library; // rax
  HMODULE v9; // rdi
  DWORD LastError; // ebx
  __int64 v11; // r9
  FARPROC ProcAddress; // rbx
  __int64 v13; // r9
  __int64 v14; // rax
  void *v15; // rsi
  _BYTE v17[56]; // [rsp+30h] [rbp-38h] BYREF

  Library = LoadLibraryExW(L"RASAPI32.DLL", 0, 0);
  v9 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RasSetCustomAuthDataW");
    if ( ProcAddress )
    {
      v14 = ConvertStringToBinary(a4, v17);
      v15 = (void *)v14;
      if ( v14 )
      {
        LastError = ((__int64 (__fastcall *)(const unsigned __int16 *, const unsigned __int16 *, __int64, _QWORD))ProcAddress)(
                      a2,
                      a3,
                      v14,
                      a5);
        CmFree(v15);
      }
      else
      {
        LastError = 8;
      }
    }
    else
    {
      LastError = GetLastError();
      MyDbgPrintfW(0xFFFFFFFFLL, L"GetProcAddress failed in SetCustomAuthData. GLE = %#x", LastError, v13);
    }
    FreeLibrary(v9);
  }
  else
  {
    LastError = GetLastError();
    MyDbgPrintfW(0xFFFFFFFFLL, L"LoadLibrary failed in SetCustomAuthData. GLE = %#x", LastError, v11);
  }
  if ( (int)LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x1800039c0  push    rbx
0x1800039c2  push    rbp
0x1800039c3  push    rsi
0x1800039c4  push    rdi
0x1800039c5  push    r14
0x1800039c7  sub     rsp, 40h
0x1800039cb  mov     rbp, r8
0x1800039ce  lea     rcx, LibFileName; "RASAPI32.DLL"
0x1800039d5  mov     r14, rdx
0x1800039d8  xor     r8d, r8d; dwFlags
0x1800039db  xor     edx, edx; hFile
0x1800039dd  mov     rsi, r9
0x1800039e0  call    cs:__imp_LoadLibraryExW
0x1800039e6  mov     rdi, rax
0x1800039e9  test    rax, rax
0x1800039ec  jnz     short loc_180003A0A
0x1800039ee  call    cs:__imp_GetLastError
0x1800039f4  lea     rdx, aLoadlibraryFai_0; "LoadLibrary failed in SetCustomAuthData"...
0x1800039fb  or      ecx, 0FFFFFFFFh
0x1800039fe  mov     r8d, eax
0x180003a01  mov     ebx, eax
0x180003a03  call    MyDbgPrintfW
0x180003a08  jmp     short loc_180003A87
0x180003a0a  lea     rdx, aRassetcustomau; "RasSetCustomAuthDataW"
0x180003a11  mov     rcx, rdi; hModule
0x180003a14  call    cs:__imp_GetProcAddress
0x180003a1a  mov     rbx, rax
0x180003a1d  test    rax, rax
0x180003a20  jnz     short loc_180003A3E
0x180003a22  call    cs:__imp_GetLastError
0x180003a28  lea     rdx, aGetprocaddress_0; "GetProcAddress failed in SetCustomAuthD"...
0x180003a2f  or      ecx, 0FFFFFFFFh
0x180003a32  mov     r8d, eax
0x180003a35  mov     ebx, eax
0x180003a37  call    MyDbgPrintfW
0x180003a3c  jmp     short loc_180003A7E
0x180003a3e  lea     rdx, [rsp+68h+var_38]
0x180003a43  mov     rcx, rsi
0x180003a46  call    ConvertStringToBinary
0x180003a4b  mov     rsi, rax
0x180003a4e  test    rax, rax
0x180003a51  jz      short loc_180003A79
0x180003a53  mov     r9d, [rsp+68h+arg_20]
0x180003a5b  mov     r8, rax
0x180003a5e  mov     rax, rbx
0x180003a61  mov     rdx, rbp
0x180003a64  mov     rcx, r14
0x180003a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a6c  mov     rcx, rsi
0x180003a6f  mov     ebx, eax
0x180003a71  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x180003a77  jmp     short loc_180003A7E
0x180003a79  mov     ebx, 8
0x180003a7e  mov     rcx, rdi; hLibModule
0x180003a81  call    cs:__imp_FreeLibrary
0x180003a87  test    ebx, ebx
0x180003a89  jle     short loc_180003A94
0x180003a8b  movzx   ebx, bx
0x180003a8e  or      ebx, 80070000h
0x180003a94  mov     eax, ebx
0x180003a96  add     rsp, 40h
0x180003a9a  pop     r14
0x180003a9c  pop     rdi
0x180003a9d  pop     rsi
0x180003a9e  pop     rbp
0x180003a9f  pop     rbx
0x180003aa0  retn
```
