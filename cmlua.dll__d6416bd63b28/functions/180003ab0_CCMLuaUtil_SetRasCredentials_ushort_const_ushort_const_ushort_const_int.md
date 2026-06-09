# CCMLuaUtil::SetRasCredentials(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180003ab0`
- end: `0x180003b91`
- name: `?SetRasCredentials@CCMLuaUtil@@UEAAJPEBG00H@Z`
- size: `225`
- prototype: `__int64 __fastcall(CCMLuaUtil *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003ab0`
- `0x18000440c`
- `0x180004e1c`
- `0x180006010`

## import_xrefs

- `cmutil!CmFree` at `0x180003b61`
- `cmutil!CmFree` at `0x180003b61`
- `KERNEL32!FreeLibrary` at `0x180003b71`
- `KERNEL32!FreeLibrary` at `0x180003b71`
- `KERNEL32!LoadLibraryExW` at `0x180003ad0`
- `KERNEL32!LoadLibraryExW` at `0x180003ad0`
- `KERNEL32!GetProcAddress` at `0x180003b04`
- `KERNEL32!GetProcAddress` at `0x180003b04`
- `KERNEL32!GetLastError` at `0x180003ade`
- `KERNEL32!GetLastError` at `0x180003b12`
- `KERNEL32!GetLastError` at `0x180003ade`
- `KERNEL32!GetLastError` at `0x180003b12`

## string_xrefs

- `0x180003abe`: `RASAPI32.DLL`
- `0x180003ae4`: `LoadLibrary failed in SetRasCredentials. GLE = %#x`

## pseudocode

```c
__int64 __fastcall CCMLuaUtil::SetRasCredentials(
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
  _BYTE *v14; // rax
  void *v15; // rsi
  _DWORD v17[14]; // [rsp+30h] [rbp-38h] BYREF

  Library = LoadLibraryExW(L"RASAPI32.DLL", 0, 0);
  v9 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RasSetCredentialsW");
    if ( ProcAddress )
    {
      v14 = ConvertStringToBinary((__int64)a4, v17);
      v15 = v14;
      if ( v14 )
      {
        LastError = ((__int64 (__fastcall *)(const unsigned __int16 *, const unsigned __int16 *, _BYTE *, _QWORD))ProcAddress)(
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
      MyDbgPrintfW(0xFFFFFFFFLL, L"GetProcAddress failed in SetRasCredentials. GLE = %#x", LastError, v13);
    }
    FreeLibrary(v9);
  }
  else
  {
    LastError = GetLastError();
    MyDbgPrintfW(0xFFFFFFFFLL, L"LoadLibrary failed in SetRasCredentials. GLE = %#x", LastError, v11);
  }
  if ( (int)LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x180003ab0  push    rbx
0x180003ab2  push    rbp
0x180003ab3  push    rsi
0x180003ab4  push    rdi
0x180003ab5  push    r14
0x180003ab7  sub     rsp, 40h
0x180003abb  mov     rbp, r8
0x180003abe  lea     rcx, LibFileName; "RASAPI32.DLL"
0x180003ac5  mov     r14, rdx
0x180003ac8  xor     r8d, r8d; dwFlags
0x180003acb  xor     edx, edx; hFile
0x180003acd  mov     rsi, r9
0x180003ad0  call    cs:__imp_LoadLibraryExW
0x180003ad6  mov     rdi, rax
0x180003ad9  test    rax, rax
0x180003adc  jnz     short loc_180003AFA
0x180003ade  call    cs:__imp_GetLastError
0x180003ae4  lea     rdx, aLoadlibraryFai; "LoadLibrary failed in SetRasCredentials"...
0x180003aeb  or      ecx, 0FFFFFFFFh
0x180003aee  mov     r8d, eax
0x180003af1  mov     ebx, eax
0x180003af3  call    MyDbgPrintfW
0x180003af8  jmp     short loc_180003B77
0x180003afa  lea     rdx, aRassetcredenti; "RasSetCredentialsW"
0x180003b01  mov     rcx, rdi; hModule
0x180003b04  call    cs:__imp_GetProcAddress
0x180003b0a  mov     rbx, rax
0x180003b0d  test    rax, rax
0x180003b10  jnz     short loc_180003B2E
0x180003b12  call    cs:__imp_GetLastError
0x180003b18  lea     rdx, aGetprocaddress_3; "GetProcAddress failed in SetRasCredenti"...
0x180003b1f  or      ecx, 0FFFFFFFFh
0x180003b22  mov     r8d, eax
0x180003b25  mov     ebx, eax
0x180003b27  call    MyDbgPrintfW
0x180003b2c  jmp     short loc_180003B6E
0x180003b2e  lea     rdx, [rsp+68h+var_38]
0x180003b33  mov     rcx, rsi
0x180003b36  call    ConvertStringToBinary
0x180003b3b  mov     rsi, rax
0x180003b3e  test    rax, rax
0x180003b41  jz      short loc_180003B69
0x180003b43  mov     r9d, [rsp+68h+arg_20]
0x180003b4b  mov     r8, rax
0x180003b4e  mov     rax, rbx
0x180003b51  mov     rdx, rbp
0x180003b54  mov     rcx, r14
0x180003b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b5c  mov     rcx, rsi
0x180003b5f  mov     ebx, eax
0x180003b61  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x180003b67  jmp     short loc_180003B6E
0x180003b69  mov     ebx, 8
0x180003b6e  mov     rcx, rdi; hLibModule
0x180003b71  call    cs:__imp_FreeLibrary
0x180003b77  test    ebx, ebx
0x180003b79  jle     short loc_180003B84
0x180003b7b  movzx   ebx, bx
0x180003b7e  or      ebx, 80070000h
0x180003b84  mov     eax, ebx
0x180003b86  add     rsp, 40h
0x180003b8a  pop     r14
0x180003b8c  pop     rdi
0x180003b8d  pop     rsi
0x180003b8e  pop     rbp
0x180003b8f  pop     rbx
0x180003b90  retn
```
