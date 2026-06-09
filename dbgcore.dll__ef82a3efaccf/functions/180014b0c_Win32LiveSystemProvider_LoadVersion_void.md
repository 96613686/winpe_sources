# Win32LiveSystemProvider::LoadVersion(void)

- ea: `0x180014b0c`
- end: `0x180014d6f`
- name: `?LoadVersion@Win32LiveSystemProvider@@IEAAJXZ`
- size: `611`
- prototype: `__int64 __fastcall(Win32LiveSystemProvider *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180013020`
- `0x180016198`

## callees

- `0x180014b0c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014b8a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014bc1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014bf7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014c2e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014c64`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014c7b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014cc4`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014cdf`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014cfa`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014d15`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014d30`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014d4b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014b8a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014bc1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014bf7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014c2e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014c64`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014c7b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014cc4`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014cdf`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014cfa`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014d15`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014d30`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014d4b`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180014b34`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180014b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c96`

## string_xrefs

- `0x180014b2b`: `version.dll`

## pseudocode

```c
signed int __fastcall Win32LiveSystemProvider::LoadVersion(Win32LiveSystemProvider *this)
{
  signed int result; // eax
  HMODULE Library; // rax
  HMODULE v4; // rdi
  FARPROC v5; // rax
  FARPROC v6; // rax
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC ProcAddress; // rax
  HMODULE v10; // rcx
  FARPROC v11; // rax
  HMODULE v12; // rcx
  FARPROC v13; // rax
  HMODULE v14; // rcx
  FARPROC v15; // rax
  HMODULE v16; // rcx
  FARPROC v17; // rax
  HMODULE v18; // rcx

  result = *((_DWORD *)this + 132);
  if ( result == 1 )
  {
    Library = LoadLibraryExA("version.dll", 0, 0);
    *((_QWORD *)this + 25) = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "GetFileVersionInfoSizeA");
      v10 = (HMODULE)*((_QWORD *)this + 25);
      *((_QWORD *)this + 67) = ProcAddress;
      v11 = GetProcAddress(v10, "GetFileVersionInfoSizeW");
      v12 = (HMODULE)*((_QWORD *)this + 25);
      *((_QWORD *)this + 68) = v11;
      v13 = GetProcAddress(v12, "GetFileVersionInfoA");
      v14 = (HMODULE)*((_QWORD *)this + 25);
      *((_QWORD *)this + 69) = v13;
      v15 = GetProcAddress(v14, "GetFileVersionInfoW");
      v16 = (HMODULE)*((_QWORD *)this + 25);
      *((_QWORD *)this + 70) = v15;
      v17 = GetProcAddress(v16, "VerQueryValueA");
      v18 = (HMODULE)*((_QWORD *)this + 25);
      *((_QWORD *)this + 71) = v17;
      *((_QWORD *)this + 72) = GetProcAddress(v18, "VerQueryValueW");
      result = 0;
      *((_DWORD *)this + 132) = 0;
    }
    else
    {
      if ( *((_QWORD *)this + 16)
        || !*((_QWORD *)this + 26)
        || (v4 = (HMODULE)*((_QWORD *)this + 27)) == 0
        || *((_QWORD *)this + 26) )
      {
        if ( GetLastError() )
        {
          result = GetLastError();
          if ( result > 0 )
            result = (unsigned __int16)result | 0x80070000;
        }
        else
        {
          result = -2147467259;
        }
      }
      else
      {
        v5 = GetProcAddress(0, "GetFileVersionInfoSizeExA");
        _InterlockedExchange64((volatile __int64 *)&Win32LiveSystemProvider::s_GetFileVersionInfoSizeExA, (__int64)v5);
        if ( !*((_QWORD *)this + 67) && v5 )
          *((_QWORD *)this + 67) = Win32LiveSystemProvider::GetFileVersionInfoSizeAStub;
        v6 = GetProcAddress(v4, "GetFileVersionInfoSizeExW");
        _InterlockedExchange64((volatile __int64 *)&Win32LiveSystemProvider::s_GetFileVersionInfoSizeExW, (__int64)v6);
        if ( !*((_QWORD *)this + 68) && v6 )
          *((_QWORD *)this + 68) = Win32LiveSystemProvider::GetFileVersionInfoSizeWStub;
        v7 = GetProcAddress(0, "GetFileVersionInfoExA");
        _InterlockedExchange64((volatile __int64 *)&Win32LiveSystemProvider::s_GetFileVersionInfoExA, (__int64)v7);
        if ( !*((_QWORD *)this + 69) && v7 )
          *((_QWORD *)this + 69) = Win32LiveSystemProvider::GetFileVersionInfoAStub;
        v8 = GetProcAddress(v4, "GetFileVersionInfoExW");
        _InterlockedExchange64((volatile __int64 *)&Win32LiveSystemProvider::s_GetFileVersionInfoExW, (__int64)v8);
        if ( !*((_QWORD *)this + 70) )
        {
          if ( v8 )
            *((_QWORD *)this + 70) = Win32LiveSystemProvider::GetFileVersionInfoWStub;
        }
        *((_QWORD *)this + 71) = GetProcAddress(0, "VerQueryValueA");
        *((_QWORD *)this + 72) = GetProcAddress(v4, "VerQueryValueW");
        result = 0;
      }
      *((_DWORD *)this + 132) = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180014b0c  mov     [rsp+arg_0], rbx
0x180014b11  push    rdi
0x180014b12  sub     rsp, 20h
0x180014b16  mov     eax, [rcx+210h]
0x180014b1c  mov     rbx, rcx
0x180014b1f  cmp     eax, 1
0x180014b22  jnz     loc_180014D64
0x180014b28  xor     r8d, r8d; dwFlags
0x180014b2b  lea     rcx, aVersionDll_0; "version.dll"
0x180014b32  xor     edx, edx; hFile
0x180014b34  call    cs:__imp_LoadLibraryExA
0x180014b3a  mov     [rbx+0C8h], rax
0x180014b41  test    rax, rax
0x180014b44  jnz     loc_180014CBA
0x180014b4a  cmp     [rbx+80h], rax
0x180014b51  jnz     loc_180014C8C
0x180014b57  cmp     [rbx+0D0h], rax
0x180014b5e  jz      loc_180014C8C
0x180014b64  mov     rdi, [rbx+0D8h]
0x180014b6b  test    rdi, rdi
0x180014b6e  jz      loc_180014C8C
0x180014b74  cmp     [rbx+0D0h], rax
0x180014b7b  jnz     loc_180014C8C
0x180014b81  lea     rdx, aGetfileversion_3; "GetFileVersionInfoSizeExA"
0x180014b88  xor     ecx, ecx; hModule
0x180014b8a  call    cs:__imp_GetProcAddress
0x180014b90  mov     rcx, rax
0x180014b93  xchg    rcx, cs:?s_GetFileVersionInfoSizeExA@Win32LiveSystemProvider@@1P6AKKPEBDPEAK@ZEA; ulong (*Win32LiveSystemProvider::s_GetFileVersionInfoSizeExA)(ulong,char const *,ulong *)
0x180014b9a  cmp     qword ptr [rbx+218h], 0
0x180014ba2  jnz     short loc_180014BB7
0x180014ba4  test    rax, rax
0x180014ba7  jz      short loc_180014BB7
0x180014ba9  lea     rax, ?GetFileVersionInfoSizeAStub@Win32LiveSystemProvider@@KAKPEBDPEAK@Z; Win32LiveSystemProvider::GetFileVersionInfoSizeAStub(char const *,ulong *)
0x180014bb0  mov     [rbx+218h], rax
0x180014bb7  lea     rdx, aGetfileversion_2; "GetFileVersionInfoSizeExW"
0x180014bbe  mov     rcx, rdi; hModule
0x180014bc1  call    cs:__imp_GetProcAddress
0x180014bc7  mov     rcx, rax
0x180014bca  xchg    rcx, cs:?s_GetFileVersionInfoSizeExW@Win32LiveSystemProvider@@1P6AKKPEBGPEAK@ZEA; ulong (*Win32LiveSystemProvider::s_GetFileVersionInfoSizeExW)(ulong,ushort const *,ulong *)
0x180014bd1  cmp     qword ptr [rbx+220h], 0
0x180014bd9  jnz     short loc_180014BEE
0x180014bdb  test    rax, rax
0x180014bde  jz      short loc_180014BEE
0x180014be0  lea     rax, ?GetFileVersionInfoSizeWStub@Win32LiveSystemProvider@@KAKPEBGPEAK@Z; Win32LiveSystemProvider::GetFileVersionInfoSizeWStub(ushort const *,ulong *)
0x180014be7  mov     [rbx+220h], rax
0x180014bee  lea     rdx, aGetfileversion_5; "GetFileVersionInfoExA"
0x180014bf5  xor     ecx, ecx; hModule
0x180014bf7  call    cs:__imp_GetProcAddress
0x180014bfd  mov     rcx, rax
0x180014c00  xchg    rcx, cs:?s_GetFileVersionInfoExA@Win32LiveSystemProvider@@1P6AHKPEBDKKPEAX@ZEA; int (*Win32LiveSystemProvider::s_GetFileVersionInfoExA)(ulong,char const *,ulong,ulong,void *)
0x180014c07  cmp     qword ptr [rbx+228h], 0
0x180014c0f  jnz     short loc_180014C24
0x180014c11  test    rax, rax
0x180014c14  jz      short loc_180014C24
0x180014c16  lea     rax, ?GetFileVersionInfoAStub@Win32LiveSystemProvider@@KAHPEBDKKPEAX@Z; Win32LiveSystemProvider::GetFileVersionInfoAStub(char const *,ulong,ulong,void *)
0x180014c1d  mov     [rbx+228h], rax
0x180014c24  lea     rdx, aGetfileversion; "GetFileVersionInfoExW"
0x180014c2b  mov     rcx, rdi; hModule
0x180014c2e  call    cs:__imp_GetProcAddress
0x180014c34  mov     rcx, rax
0x180014c37  xchg    rcx, cs:?s_GetFileVersionInfoExW@Win32LiveSystemProvider@@1P6AHKPEBGKKPEAX@ZEA; int (*Win32LiveSystemProvider::s_GetFileVersionInfoExW)(ulong,ushort const *,ulong,ulong,void *)
0x180014c3e  cmp     qword ptr [rbx+230h], 0
0x180014c46  jnz     short loc_180014C5B
0x180014c48  test    rax, rax
0x180014c4b  jz      short loc_180014C5B
0x180014c4d  lea     rax, ?GetFileVersionInfoWStub@Win32LiveSystemProvider@@KAHPEBGKKPEAX@Z; Win32LiveSystemProvider::GetFileVersionInfoWStub(ushort const *,ulong,ulong,void *)
0x180014c54  mov     [rbx+230h], rax
0x180014c5b  lea     rdx, aVerqueryvaluea; "VerQueryValueA"
0x180014c62  xor     ecx, ecx; hModule
0x180014c64  call    cs:__imp_GetProcAddress
0x180014c6a  lea     rdx, aVerqueryvaluew; "VerQueryValueW"
0x180014c71  mov     rcx, rdi; hModule
0x180014c74  mov     [rbx+238h], rax
0x180014c7b  call    cs:__imp_GetProcAddress
0x180014c81  mov     [rbx+240h], rax
0x180014c88  xor     eax, eax
0x180014c8a  jmp     short loc_180014CAF
0x180014c8c  call    cs:__imp_GetLastError
0x180014c92  test    eax, eax
0x180014c94  jz      short loc_180014CAA
0x180014c96  call    cs:__imp_GetLastError
0x180014c9c  test    eax, eax
0x180014c9e  jle     short loc_180014CAF
0x180014ca0  movzx   eax, ax
0x180014ca3  or      eax, 80070000h
0x180014ca8  jmp     short loc_180014CAF
0x180014caa  mov     eax, 80004005h
0x180014caf  mov     [rbx+210h], eax
0x180014cb5  jmp     loc_180014D64
0x180014cba  lea     rdx, aGetfileversion_0; "GetFileVersionInfoSizeA"
0x180014cc1  mov     rcx, rax; hModule
0x180014cc4  call    cs:__imp_GetProcAddress
0x180014cca  mov     rcx, [rbx+0C8h]; hModule
0x180014cd1  lea     rdx, aGetfileversion_1; "GetFileVersionInfoSizeW"
0x180014cd8  mov     [rbx+218h], rax
0x180014cdf  call    cs:__imp_GetProcAddress
0x180014ce5  mov     rcx, [rbx+0C8h]; hModule
0x180014cec  lea     rdx, aGetfileversion_4; "GetFileVersionInfoA"
0x180014cf3  mov     [rbx+220h], rax
0x180014cfa  call    cs:__imp_GetProcAddress
0x180014d00  mov     rcx, [rbx+0C8h]; hModule
0x180014d07  lea     rdx, aGetfileversion_6; "GetFileVersionInfoW"
0x180014d0e  mov     [rbx+228h], rax
0x180014d15  call    cs:__imp_GetProcAddress
0x180014d1b  mov     rcx, [rbx+0C8h]; hModule
0x180014d22  lea     rdx, aVerqueryvaluea; "VerQueryValueA"
0x180014d29  mov     [rbx+230h], rax
0x180014d30  call    cs:__imp_GetProcAddress
0x180014d36  mov     rcx, [rbx+0C8h]; hModule
0x180014d3d  lea     rdx, aVerqueryvaluew; "VerQueryValueW"
0x180014d44  mov     [rbx+238h], rax
0x180014d4b  call    cs:__imp_GetProcAddress
0x180014d51  mov     [rbx+240h], rax
0x180014d58  xor     eax, eax
0x180014d5a  mov     dword ptr [rbx+210h], 0
0x180014d64  mov     rbx, [rsp+28h+arg_0]
0x180014d69  add     rsp, 20h
0x180014d6d  pop     rdi
0x180014d6e  retn
```
