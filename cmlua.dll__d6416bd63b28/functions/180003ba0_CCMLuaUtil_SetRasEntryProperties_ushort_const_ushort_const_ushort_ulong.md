# CCMLuaUtil::SetRasEntryProperties(ushort const *,ushort const *,ushort * *,ulong)

- ea: `0x180003ba0`
- end: `0x180003cbb`
- name: `?SetRasEntryProperties@CCMLuaUtil@@UEAAJPEBG0PEAPEAGK@Z`
- size: `283`
- prototype: `__int64 __fastcall(CCMLuaUtil *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180003ba0`
- `0x180004368`
- `0x18000440c`
- `0x180004e1c`
- `0x180006010`

## import_xrefs

- `cmutil!CmFree` at `0x180003c76`
- `cmutil!CmFree` at `0x180003c8e`
- `cmutil!CmFree` at `0x180003c76`
- `cmutil!CmFree` at `0x180003c8e`
- `KERNEL32!FreeLibrary` at `0x180003c97`
- `KERNEL32!FreeLibrary` at `0x180003c97`
- `KERNEL32!LoadLibraryExW` at `0x180003bc4`
- `KERNEL32!LoadLibraryExW` at `0x180003bc4`
- `KERNEL32!GetProcAddress` at `0x180003bfb`
- `KERNEL32!GetProcAddress` at `0x180003bfb`
- `KERNEL32!GetLastError` at `0x180003bd2`
- `KERNEL32!GetLastError` at `0x180003c09`
- `KERNEL32!GetLastError` at `0x180003bd2`
- `KERNEL32!GetLastError` at `0x180003c09`

## string_xrefs

- `0x180003bb2`: `RASAPI32.DLL`
- `0x180003bd8`: `LoadLibrary failed in SetRasEntryProperties. GLE = %#x`

## pseudocode

```c
__int64 __fastcall CCMLuaUtil::SetRasEntryProperties(
        CCMLuaUtil *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned int a5)
{
  HMODULE Library; // rax
  HMODULE v9; // rdi
  DWORD LastError; // ebx
  __int64 v11; // r9
  FARPROC ProcAddress; // rbp
  __int64 v13; // r9
  void *v14; // rcx
  __int64 v15; // rax
  void *v16; // rsi
  _DWORD v18[18]; // [rsp+40h] [rbp-48h] BYREF

  Library = LoadLibraryExW(L"RASAPI32.DLL", 0, 0);
  v9 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RasSetEntryPropertiesW");
    if ( ProcAddress )
    {
      v14 = *a4;
      LastError = 87;
      v18[0] = 0;
      v15 = ConvertStringToBinary(v14, v18);
      v16 = (void *)v15;
      if ( v15 )
      {
        LastError = ((__int64 (__fastcall *)(const unsigned __int16 *, const unsigned __int16 *, __int64, _QWORD, _QWORD, _DWORD))ProcAddress)(
                      a2,
                      a3,
                      v15,
                      a5,
                      0,
                      0);
        CmFree(*a4);
        *a4 = (unsigned __int16 *)ConvertBinaryToString(v16, v18[0]);
        CmFree(v16);
      }
    }
    else
    {
      LastError = GetLastError();
      MyDbgPrintfW(0xFFFFFFFFLL, L"GetProcAddress failed in SetRasEntryProperties. GLE = %#x", LastError, v13);
    }
    FreeLibrary(v9);
  }
  else
  {
    LastError = GetLastError();
    MyDbgPrintfW(0xFFFFFFFFLL, L"LoadLibrary failed in SetRasEntryProperties. GLE = %#x", LastError, v11);
  }
  if ( (int)LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x180003ba0  push    rbx
0x180003ba2  push    rbp
0x180003ba3  push    rsi
0x180003ba4  push    rdi
0x180003ba5  push    r12
0x180003ba7  push    r14
0x180003ba9  push    r15
0x180003bab  sub     rsp, 50h
0x180003baf  mov     r15, r8
0x180003bb2  lea     rcx, LibFileName; "RASAPI32.DLL"
0x180003bb9  mov     r12, rdx
0x180003bbc  xor     r8d, r8d; dwFlags
0x180003bbf  xor     edx, edx; hFile
0x180003bc1  mov     r14, r9
0x180003bc4  call    cs:__imp_LoadLibraryExW
0x180003bca  mov     rdi, rax
0x180003bcd  test    rax, rax
0x180003bd0  jnz     short loc_180003BF1
0x180003bd2  call    cs:__imp_GetLastError
0x180003bd8  lea     rdx, aLoadlibraryFai_2; "LoadLibrary failed in SetRasEntryProper"...
0x180003bdf  or      ecx, 0FFFFFFFFh
0x180003be2  mov     r8d, eax
0x180003be5  mov     ebx, eax
0x180003be7  call    MyDbgPrintfW
0x180003bec  jmp     loc_180003C9D
0x180003bf1  lea     rdx, aRassetentrypro; "RasSetEntryPropertiesW"
0x180003bf8  mov     rcx, rdi; hModule
0x180003bfb  call    cs:__imp_GetProcAddress
0x180003c01  mov     rbp, rax
0x180003c04  test    rax, rax
0x180003c07  jnz     short loc_180003C25
0x180003c09  call    cs:__imp_GetLastError
0x180003c0f  lea     rdx, aGetprocaddress_2; "GetProcAddress failed in SetRasEntryPro"...
0x180003c16  or      ecx, 0FFFFFFFFh
0x180003c19  mov     r8d, eax
0x180003c1c  mov     ebx, eax
0x180003c1e  call    MyDbgPrintfW
0x180003c23  jmp     short loc_180003C94
0x180003c25  mov     rcx, [r14]
0x180003c28  lea     rdx, [rsp+88h+var_48]
0x180003c2d  mov     ebx, 57h ; 'W'
0x180003c32  mov     [rsp+88h+var_48], 0
0x180003c3a  call    ConvertStringToBinary
0x180003c3f  mov     rsi, rax
0x180003c42  test    rax, rax
0x180003c45  jz      short loc_180003C94
0x180003c47  mov     r9d, [rsp+88h+arg_20]
0x180003c4f  mov     r8, rax
0x180003c52  mov     rax, rbp
0x180003c55  mov     [rsp+88h+var_60], 0
0x180003c5d  mov     rdx, r15
0x180003c60  mov     [rsp+88h+var_68], 0
0x180003c69  mov     rcx, r12
0x180003c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c71  mov     rcx, [r14]
0x180003c74  mov     ebx, eax
0x180003c76  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x180003c7c  mov     edx, [rsp+88h+var_48]
0x180003c80  mov     rcx, rsi
0x180003c83  call    ConvertBinaryToString
0x180003c88  mov     rcx, rsi
0x180003c8b  mov     [r14], rax
0x180003c8e  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x180003c94  mov     rcx, rdi; hLibModule
0x180003c97  call    cs:__imp_FreeLibrary
0x180003c9d  test    ebx, ebx
0x180003c9f  jle     short loc_180003CAA
0x180003ca1  movzx   ebx, bx
0x180003ca4  or      ebx, 80070000h
0x180003caa  mov     eax, ebx
0x180003cac  add     rsp, 50h
0x180003cb0  pop     r15
0x180003cb2  pop     r14
0x180003cb4  pop     r12
0x180003cb6  pop     rdi
0x180003cb7  pop     rsi
0x180003cb8  pop     rbp
0x180003cb9  pop     rbx
0x180003cba  retn
```
