# Win32LiveSystemProvider::LoadVersion(void)

- ea: `0x180400dd4`
- end: `0x180401092`
- name: `?LoadVersion@Win32LiveSystemProvider@@IEAAJXZ`
- size: `702`
- prototype: `__int64 __fastcall(Win32LiveSystemProvider *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1803ff300`
- `0x180402690`

## callees

- `0x180400dd4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400e58`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400e95`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400ed1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400f0e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400f4a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400f67`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400fc2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400fe3`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180401004`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180401025`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180401046`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180401067`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400e58`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400e95`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400ed1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400f0e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400f4a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400f67`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400fc2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400fe3`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180401004`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180401025`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180401046`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180401067`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180400dfc`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180400dfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180400f7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180400f8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180400f7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180400f8e`

## string_xrefs

- `0x180400df3`: `version.dll`

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
0x180400dd4  mov     [rsp+arg_0], rbx
0x180400dd9  push    rdi
0x180400dda  sub     rsp, 20h
0x180400dde  mov     eax, [rcx+210h]
0x180400de4  mov     rbx, rcx
0x180400de7  cmp     eax, 1
0x180400dea  jnz     loc_180401086
0x180400df0  xor     r8d, r8d; dwFlags
0x180400df3  lea     rcx, aVersionDll_0; "version.dll"
0x180400dfa  xor     edx, edx; hFile
0x180400dfc  call    cs:__imp_LoadLibraryExA
0x180400e03  nop     dword ptr [rax+rax+00h]
0x180400e08  mov     [rbx+0C8h], rax
0x180400e0f  test    rax, rax
0x180400e12  jnz     loc_180400FB8
0x180400e18  cmp     [rbx+80h], rax
0x180400e1f  jnz     loc_180400F7E
0x180400e25  cmp     [rbx+0D0h], rax
0x180400e2c  jz      loc_180400F7E
0x180400e32  mov     rdi, [rbx+0D8h]
0x180400e39  test    rdi, rdi
0x180400e3c  jz      loc_180400F7E
0x180400e42  cmp     [rbx+0D0h], rax
0x180400e49  jnz     loc_180400F7E
0x180400e4f  lea     rdx, aGetfileversion_3; "GetFileVersionInfoSizeExA"
0x180400e56  xor     ecx, ecx; hModule
0x180400e58  call    cs:__imp_GetProcAddress
0x180400e5f  nop     dword ptr [rax+rax+00h]
0x180400e64  mov     rcx, rax
0x180400e67  xchg    rcx, cs:?s_GetFileVersionInfoSizeExA@Win32LiveSystemProvider@@1P6AKKPEBDPEAK@ZEA; ulong (*Win32LiveSystemProvider::s_GetFileVersionInfoSizeExA)(ulong,char const *,ulong *)
0x180400e6e  cmp     qword ptr [rbx+218h], 0
0x180400e76  jnz     short loc_180400E8B
0x180400e78  test    rax, rax
0x180400e7b  jz      short loc_180400E8B
0x180400e7d  lea     rax, ?GetFileVersionInfoSizeAStub@Win32LiveSystemProvider@@KAKPEBDPEAK@Z; Win32LiveSystemProvider::GetFileVersionInfoSizeAStub(char const *,ulong *)
0x180400e84  mov     [rbx+218h], rax
0x180400e8b  lea     rdx, aGetfileversion_2; "GetFileVersionInfoSizeExW"
0x180400e92  mov     rcx, rdi; hModule
0x180400e95  call    cs:__imp_GetProcAddress
0x180400e9c  nop     dword ptr [rax+rax+00h]
0x180400ea1  mov     rcx, rax
0x180400ea4  xchg    rcx, cs:?s_GetFileVersionInfoSizeExW@Win32LiveSystemProvider@@1P6AKKPEBGPEAK@ZEA; ulong (*Win32LiveSystemProvider::s_GetFileVersionInfoSizeExW)(ulong,ushort const *,ulong *)
0x180400eab  cmp     qword ptr [rbx+220h], 0
0x180400eb3  jnz     short loc_180400EC8
0x180400eb5  test    rax, rax
0x180400eb8  jz      short loc_180400EC8
0x180400eba  lea     rax, ?GetFileVersionInfoSizeWStub@Win32LiveSystemProvider@@KAKPEBGPEAK@Z; Win32LiveSystemProvider::GetFileVersionInfoSizeWStub(ushort const *,ulong *)
0x180400ec1  mov     [rbx+220h], rax
0x180400ec8  lea     rdx, aGetfileversion_5; "GetFileVersionInfoExA"
0x180400ecf  xor     ecx, ecx; hModule
0x180400ed1  call    cs:__imp_GetProcAddress
0x180400ed8  nop     dword ptr [rax+rax+00h]
0x180400edd  mov     rcx, rax
0x180400ee0  xchg    rcx, cs:?s_GetFileVersionInfoExA@Win32LiveSystemProvider@@1P6AHKPEBDKKPEAX@ZEA; int (*Win32LiveSystemProvider::s_GetFileVersionInfoExA)(ulong,char const *,ulong,ulong,void *)
0x180400ee7  cmp     qword ptr [rbx+228h], 0
0x180400eef  jnz     short loc_180400F04
0x180400ef1  test    rax, rax
0x180400ef4  jz      short loc_180400F04
0x180400ef6  lea     rax, ?GetFileVersionInfoAStub@Win32LiveSystemProvider@@KAHPEBDKKPEAX@Z; Win32LiveSystemProvider::GetFileVersionInfoAStub(char const *,ulong,ulong,void *)
0x180400efd  mov     [rbx+228h], rax
0x180400f04  lea     rdx, aGetfileversion; "GetFileVersionInfoExW"
0x180400f0b  mov     rcx, rdi; hModule
0x180400f0e  call    cs:__imp_GetProcAddress
0x180400f15  nop     dword ptr [rax+rax+00h]
0x180400f1a  mov     rcx, rax
0x180400f1d  xchg    rcx, cs:?s_GetFileVersionInfoExW@Win32LiveSystemProvider@@1P6AHKPEBGKKPEAX@ZEA; int (*Win32LiveSystemProvider::s_GetFileVersionInfoExW)(ulong,ushort const *,ulong,ulong,void *)
0x180400f24  cmp     qword ptr [rbx+230h], 0
0x180400f2c  jnz     short loc_180400F41
0x180400f2e  test    rax, rax
0x180400f31  jz      short loc_180400F41
0x180400f33  lea     rax, ?GetFileVersionInfoWStub@Win32LiveSystemProvider@@KAHPEBGKKPEAX@Z; Win32LiveSystemProvider::GetFileVersionInfoWStub(ushort const *,ulong,ulong,void *)
0x180400f3a  mov     [rbx+230h], rax
0x180400f41  lea     rdx, aVerqueryvaluea; "VerQueryValueA"
0x180400f48  xor     ecx, ecx; hModule
0x180400f4a  call    cs:__imp_GetProcAddress
0x180400f51  nop     dword ptr [rax+rax+00h]
0x180400f56  lea     rdx, aVerqueryvaluew; "VerQueryValueW"
0x180400f5d  mov     rcx, rdi; hModule
0x180400f60  mov     [rbx+238h], rax
0x180400f67  call    cs:__imp_GetProcAddress
0x180400f6e  nop     dword ptr [rax+rax+00h]
0x180400f73  mov     [rbx+240h], rax
0x180400f7a  xor     eax, eax
0x180400f7c  jmp     short loc_180400FAD
0x180400f7e  call    cs:__imp_GetLastError
0x180400f85  nop     dword ptr [rax+rax+00h]
0x180400f8a  test    eax, eax
0x180400f8c  jz      short loc_180400FA8
0x180400f8e  call    cs:__imp_GetLastError
0x180400f95  nop     dword ptr [rax+rax+00h]
0x180400f9a  test    eax, eax
0x180400f9c  jle     short loc_180400FAD
0x180400f9e  movzx   eax, ax
0x180400fa1  or      eax, 80070000h
0x180400fa6  jmp     short loc_180400FAD
0x180400fa8  mov     eax, 80004005h
0x180400fad  mov     [rbx+210h], eax
0x180400fb3  jmp     loc_180401086
0x180400fb8  lea     rdx, aGetfileversion_0; "GetFileVersionInfoSizeA"
0x180400fbf  mov     rcx, rax; hModule
0x180400fc2  call    cs:__imp_GetProcAddress
0x180400fc9  nop     dword ptr [rax+rax+00h]
0x180400fce  mov     rcx, [rbx+0C8h]; hModule
0x180400fd5  lea     rdx, aGetfileversion_1; "GetFileVersionInfoSizeW"
0x180400fdc  mov     [rbx+218h], rax
0x180400fe3  call    cs:__imp_GetProcAddress
0x180400fea  nop     dword ptr [rax+rax+00h]
0x180400fef  mov     rcx, [rbx+0C8h]; hModule
0x180400ff6  lea     rdx, aGetfileversion_4; "GetFileVersionInfoA"
0x180400ffd  mov     [rbx+220h], rax
0x180401004  call    cs:__imp_GetProcAddress
0x18040100b  nop     dword ptr [rax+rax+00h]
0x180401010  mov     rcx, [rbx+0C8h]; hModule
0x180401017  lea     rdx, aGetfileversion_6; "GetFileVersionInfoW"
0x18040101e  mov     [rbx+228h], rax
0x180401025  call    cs:__imp_GetProcAddress
0x18040102c  nop     dword ptr [rax+rax+00h]
0x180401031  mov     rcx, [rbx+0C8h]; hModule
0x180401038  lea     rdx, aVerqueryvaluea; "VerQueryValueA"
0x18040103f  mov     [rbx+230h], rax
0x180401046  call    cs:__imp_GetProcAddress
0x18040104d  nop     dword ptr [rax+rax+00h]
0x180401052  mov     rcx, [rbx+0C8h]; hModule
0x180401059  lea     rdx, aVerqueryvaluew; "VerQueryValueW"
0x180401060  mov     [rbx+238h], rax
0x180401067  call    cs:__imp_GetProcAddress
0x18040106e  nop     dword ptr [rax+rax+00h]
0x180401073  mov     [rbx+240h], rax
0x18040107a  xor     eax, eax
0x18040107c  mov     dword ptr [rbx+210h], 0
0x180401086  mov     rbx, [rsp+28h+arg_0]
0x18040108b  add     rsp, 20h
0x18040108f  pop     rdi
0x180401090  retn
```
