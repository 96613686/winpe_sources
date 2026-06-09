# CCMLuaUtil::SetRasSubEntryProperties(ushort const *,ushort const *,ulong,ushort * *,ulong)

- ea: `0x180003cd0`
- end: `0x180003dfd`
- name: `?SetRasSubEntryProperties@CCMLuaUtil@@UEAAJPEBG0KPEAPEAGK@Z`
- size: `301`
- prototype: `__int64 __fastcall(CCMLuaUtil *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 **, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180003cd0`
- `0x180004368`
- `0x18000440c`
- `0x180004e1c`
- `0x180006010`

## import_xrefs

- `cmutil!CmFree` at `0x180003db6`
- `cmutil!CmFree` at `0x180003dce`
- `cmutil!CmFree` at `0x180003db6`
- `cmutil!CmFree` at `0x180003dce`
- `KERNEL32!FreeLibrary` at `0x180003dd7`
- `KERNEL32!FreeLibrary` at `0x180003dd7`
- `KERNEL32!LoadLibraryExW` at `0x180003cf6`
- `KERNEL32!LoadLibraryExW` at `0x180003cf6`
- `KERNEL32!GetProcAddress` at `0x180003d2d`
- `KERNEL32!GetProcAddress` at `0x180003d2d`
- `KERNEL32!GetLastError` at `0x180003d04`
- `KERNEL32!GetLastError` at `0x180003d3b`
- `KERNEL32!GetLastError` at `0x180003d04`
- `KERNEL32!GetLastError` at `0x180003d3b`

## string_xrefs

- `0x180003ce4`: `RASAPI32.DLL`
- `0x180003d0a`: `LoadLibrary failed in SetRasSubEntryProperties. GLE = %#x`

## pseudocode

```c
__int64 __fastcall CCMLuaUtil::SetRasSubEntryProperties(
        CCMLuaUtil *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 **a5,
        unsigned int a6)
{
  HMODULE Library; // rax
  HMODULE v10; // rdi
  DWORD LastError; // ebx
  __int64 v12; // r9
  FARPROC ProcAddress; // rbp
  __int64 v14; // r9
  __int64 v15; // rax
  void *v16; // rsi
  _DWORD v18[22]; // [rsp+40h] [rbp-58h] BYREF

  Library = LoadLibraryExW(L"RASAPI32.DLL", 0, 0);
  v10 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RasSetSubEntryPropertiesW");
    if ( ProcAddress )
    {
      LastError = 87;
      v18[0] = 0;
      v15 = ConvertStringToBinary(*a5, v18);
      v16 = (void *)v15;
      if ( v15 )
      {
        LastError = ((__int64 (__fastcall *)(const unsigned __int16 *, const unsigned __int16 *, _QWORD, __int64, unsigned int, _QWORD, _DWORD))ProcAddress)(
                      a2,
                      a3,
                      a4,
                      v15,
                      a6,
                      0,
                      0);
        CmFree(*a5);
        *a5 = (unsigned __int16 *)ConvertBinaryToString(v16, v18[0]);
        CmFree(v16);
      }
    }
    else
    {
      LastError = GetLastError();
      MyDbgPrintfW(0xFFFFFFFFLL, L"GetProcAddress failed in SetRasSubEntryProperties. GLE = %#x", LastError, v14);
    }
    FreeLibrary(v10);
  }
  else
  {
    LastError = GetLastError();
    MyDbgPrintfW(0xFFFFFFFFLL, L"LoadLibrary failed in SetRasSubEntryProperties. GLE = %#x", LastError, v12);
  }
  if ( (int)LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x180003cd0  push    rbx
0x180003cd2  push    rbp
0x180003cd3  push    rsi
0x180003cd4  push    rdi
0x180003cd5  push    r12
0x180003cd7  push    r13
0x180003cd9  push    r14
0x180003cdb  push    r15
0x180003cdd  sub     rsp, 58h
0x180003ce1  mov     r12, r8
0x180003ce4  lea     rcx, LibFileName; "RASAPI32.DLL"
0x180003ceb  mov     r13, rdx
0x180003cee  xor     r8d, r8d; dwFlags
0x180003cf1  xor     edx, edx; hFile
0x180003cf3  mov     r15d, r9d
0x180003cf6  call    cs:__imp_LoadLibraryExW
0x180003cfc  mov     rdi, rax
0x180003cff  test    rax, rax
0x180003d02  jnz     short loc_180003D23
0x180003d04  call    cs:__imp_GetLastError
0x180003d0a  lea     rdx, aLoadlibraryFai_1; "LoadLibrary failed in SetRasSubEntryPro"...
0x180003d11  or      ecx, 0FFFFFFFFh
0x180003d14  mov     r8d, eax
0x180003d17  mov     ebx, eax
0x180003d19  call    MyDbgPrintfW
0x180003d1e  jmp     loc_180003DDD
0x180003d23  lea     rdx, aRassetsubentry; "RasSetSubEntryPropertiesW"
0x180003d2a  mov     rcx, rdi; hModule
0x180003d2d  call    cs:__imp_GetProcAddress
0x180003d33  mov     rbp, rax
0x180003d36  test    rax, rax
0x180003d39  jnz     short loc_180003D57
0x180003d3b  call    cs:__imp_GetLastError
0x180003d41  lea     rdx, aGetprocaddress_5; "GetProcAddress failed in SetRasSubEntry"...
0x180003d48  or      ecx, 0FFFFFFFFh
0x180003d4b  mov     r8d, eax
0x180003d4e  mov     ebx, eax
0x180003d50  call    MyDbgPrintfW
0x180003d55  jmp     short loc_180003DD4
0x180003d57  mov     r14, [rsp+98h+arg_20]
0x180003d5f  lea     rdx, [rsp+98h+var_58]
0x180003d64  mov     ebx, 57h ; 'W'
0x180003d69  mov     [rsp+98h+var_58], 0
0x180003d71  mov     rcx, [r14]
0x180003d74  call    ConvertStringToBinary
0x180003d79  mov     rsi, rax
0x180003d7c  test    rax, rax
0x180003d7f  jz      short loc_180003DD4
0x180003d81  mov     ecx, [rsp+98h+arg_28]
0x180003d88  mov     r9, rax
0x180003d8b  mov     [rsp+98h+var_68], 0
0x180003d93  mov     r8d, r15d
0x180003d96  mov     [rsp+98h+var_70], 0
0x180003d9f  mov     rdx, r12
0x180003da2  mov     [rsp+98h+var_78], ecx
0x180003da6  mov     rax, rbp
0x180003da9  mov     rcx, r13
0x180003dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003db1  mov     rcx, [r14]
0x180003db4  mov     ebx, eax
0x180003db6  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x180003dbc  mov     edx, [rsp+98h+var_58]
0x180003dc0  mov     rcx, rsi
0x180003dc3  call    ConvertBinaryToString
0x180003dc8  mov     rcx, rsi
0x180003dcb  mov     [r14], rax
0x180003dce  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x180003dd4  mov     rcx, rdi; hLibModule
0x180003dd7  call    cs:__imp_FreeLibrary
0x180003ddd  test    ebx, ebx
0x180003ddf  jle     short loc_180003DEA
0x180003de1  movzx   ebx, bx
0x180003de4  or      ebx, 80070000h
0x180003dea  mov     eax, ebx
0x180003dec  add     rsp, 58h
0x180003df0  pop     r15
0x180003df2  pop     r14
0x180003df4  pop     r13
0x180003df6  pop     r12
0x180003df8  pop     rdi
0x180003df9  pop     rsi
0x180003dfa  pop     rbp
0x180003dfb  pop     rbx
0x180003dfc  retn
```
