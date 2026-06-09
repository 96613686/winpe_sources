# CCompRC::LoadLibrary(HINSTANCE__ * *)

- ea: `0x18003f38c`
- end: `0x18003f4d3`
- name: `?LoadLibrary@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@@Z`
- size: `327`
- prototype: `__int64 __fastcall(CCompRC *__hidden this, HINSTANCE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003eff4`

## callees

- `0x18000d614`
- `0x18002a7c8`
- `0x18002dfb4`
- `0x18003f38c`
- `0x18003f4dc`
- `0x180041ac0`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x18003f3cd`
- `KERNEL32!GetModuleFileNameW` at `0x18003f3cd`

## string_xrefs

- `0x18003f408`: `mscorrc.dll`

## pseudocode

```c
__int64 __fastcall CCompRC::LoadLibrary(CCompRC *this, HINSTANCE *a2)
{
  unsigned int v4; // r9d
  __int64 result; // rax
  unsigned int v6; // r9d
  rsize_t SizeInWords; // [rsp+30h] [rbp-D0h]
  rsize_t v8; // [rsp+48h] [rbp-B8h]
  int v9; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v10; // [rsp+64h] [rbp-9Ch] BYREF
  wchar_t v11[36]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Filename[264]; // [rsp+B0h] [rbp-50h] BYREF

  if ( !GetModuleFileNameW(g_hShimMod, Filename, 0x104u) )
    return HRESULT_FROM_GetLastError();
  result = CCompRC::LoadLibraryHelper(this, a2, Filename, v4);
  if ( (_DWORD)result == -2147024882 )
    return 2147942414LL;
  if ( (int)result < 0 && *((wchar_t **)this + 26) == L"mscorrc.dll" )
  {
    v9 = 0;
    LODWORD(v8) = 30;
    LODWORD(SizeInWords) = 260;
    result = GetRequestedRuntimeInfo(0, 193, Filename, SizeInWords, (__int64)&v10, v11, v8, (__int64)&v9);
    if ( (int)result >= 0 )
    {
      if ( v9 )
      {
        wcscat_s(Filename, 0x104u, v11);
        wcscat_s(Filename, 0x104u, L"\\");
      }
      return CCompRC::LoadLibraryHelper(this, a2, Filename, v6);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003f38c  mov     [rsp-8+arg_10], rbx
0x18003f391  push    rbp
0x18003f392  push    rsi
0x18003f393  push    rdi
0x18003f394  lea     rbp, [rsp-1D0h]
0x18003f39c  sub     rsp, 2D0h
0x18003f3a3  mov     rax, cs:__security_cookie
0x18003f3aa  xor     rax, rsp
0x18003f3ad  mov     [rbp+1E0h+var_20], rax
0x18003f3b4  mov     rdi, rdx
0x18003f3b7  mov     rbx, rcx
0x18003f3ba  mov     rcx, cs:?g_hShimMod@@3PEAUHINSTANCE__@@EA; hModule
0x18003f3c1  lea     rdx, [rbp+1E0h+Filename]; lpFilename
0x18003f3c5  mov     esi, 104h
0x18003f3ca  mov     r8d, esi; nSize
0x18003f3cd  call    cs:__imp_GetModuleFileNameW
0x18003f3d3  test    eax, eax
0x18003f3d5  jnz     short loc_18003F3E1
0x18003f3d7  call    ?HRESULT_FROM_GetLastError@@YAJXZ; HRESULT_FROM_GetLastError(void)
0x18003f3dc  jmp     loc_18003F4B1
0x18003f3e1  lea     r8, [rbp+1E0h+Filename]; Source
0x18003f3e5  mov     rdx, rdi; HINSTANCE *
0x18003f3e8  mov     rcx, rbx; this
0x18003f3eb  call    ?LoadLibraryHelper@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@PEAGK@Z; CCompRC::LoadLibraryHelper(HINSTANCE__ * *,ushort *,ulong)
0x18003f3f0  mov     ecx, 8007000Eh
0x18003f3f5  cmp     eax, ecx
0x18003f3f7  jnz     short loc_18003F400
0x18003f3f9  mov     eax, ecx
0x18003f3fb  jmp     loc_18003F4B1
0x18003f400  test    eax, eax
0x18003f402  jns     loc_18003F4B1
0x18003f408  lea     rcx, aMscorrcDll; "mscorrc.dll"
0x18003f40f  cmp     [rbx+0D0h], rcx
0x18003f416  jnz     loc_18003F4B1
0x18003f41c  lea     rax, [rsp+2E0h+var_280]
0x18003f421  mov     dword ptr [rsp+2E0h+var_280], 0
0x18003f429  mov     [rsp+2E0h+var_290], rax; __int64
0x18003f42e  lea     rdx, aV4041213; "v4.0.41213"
0x18003f435  mov     dword ptr [rsp+2E0h+var_298], 1Eh; rsize_t
0x18003f43d  lea     rax, [rsp+2E0h+var_278]
0x18003f442  mov     [rsp+2E0h+var_2A0], rax; wchar_t *
0x18003f447  xor     r9d, r9d
0x18003f44a  lea     rax, [rsp+2E0h+var_280+4]
0x18003f44f  xor     r8d, r8d
0x18003f452  mov     [rsp+2E0h+var_2A8], rax; __int64
0x18003f457  xor     ecx, ecx; unsigned __int16 *
0x18003f459  lea     rax, [rbp+1E0h+Filename]
0x18003f45d  mov     dword ptr [rsp+2E0h+SizeInWords], esi; SizeInWords
0x18003f461  mov     [rsp+2E0h+Destination], rax; Destination
0x18003f466  mov     [rsp+2E0h+var_2C0], 0C1h; int
0x18003f46e  call    GetRequestedRuntimeInfo
0x18003f473  test    eax, eax
0x18003f475  js      short loc_18003F4B1
0x18003f477  cmp     dword ptr [rsp+2E0h+var_280], 0
0x18003f47c  jbe     short loc_18003F4A2
0x18003f47e  lea     r8, [rsp+2E0h+var_278]; Source
0x18003f483  mov     rdx, rsi; SizeInWords
0x18003f486  lea     rcx, [rbp+1E0h+Filename]; Destination
0x18003f48a  call    wcscat_s
0x18003f48f  lea     r8, asc_18004C8C0; "\\"
0x18003f496  mov     rdx, rsi; SizeInWords
0x18003f499  lea     rcx, [rbp+1E0h+Filename]; Destination
0x18003f49d  call    wcscat_s
0x18003f4a2  lea     r8, [rbp+1E0h+Filename]; Source
0x18003f4a6  mov     rdx, rdi; HINSTANCE *
0x18003f4a9  mov     rcx, rbx; this
0x18003f4ac  call    ?LoadLibraryHelper@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@PEAGK@Z; CCompRC::LoadLibraryHelper(HINSTANCE__ * *,ushort *,ulong)
0x18003f4b1  mov     rcx, [rbp+1E0h+var_20]
0x18003f4b8  xor     rcx, rsp; StackCookie
0x18003f4bb  call    __security_check_cookie
0x18003f4c0  mov     rbx, [rsp+2E0h+arg_10]
0x18003f4c8  add     rsp, 2D0h
0x18003f4cf  pop     rdi
0x18003f4d0  pop     rsi
0x18003f4d1  pop     rbp
0x18003f4d2  retn
```
