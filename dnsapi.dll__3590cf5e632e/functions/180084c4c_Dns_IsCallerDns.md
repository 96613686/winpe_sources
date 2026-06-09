# Dns_IsCallerDns

- ea: `0x180084c4c`
- end: `0x180084d98`
- name: `Dns_IsCallerDns`
- size: `332`
- prototype: `__int64 __fastcall(LPCSTR lpModuleName)`
- caller_count: `74`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002ec0`
- `0x1800034f0`
- `0x180006c30`
- `0x180006d40`
- `0x1800072a0`
- `0x1800079a0`
- `0x180011e3c`
- `0x180023d70`
- `0x180025fc0`
- `0x180028890`
- `0x180028f20`
- `0x18002a0e0`
- `0x18002cf9c`
- `0x18002d30c`
- `0x180030aec`
- `0x1800317e0`
- `0x180031e0c`
- `0x1800327bc`
- `0x180033414`
- `0x180035d40`
- `0x18003a430`
- `0x18003a900`
- `0x18003cb90`
- `0x18003da6c`
- `0x180047b80`
- `0x1800493e0`
- `0x18004a020`
- `0x18004a0b0`
- `0x18004d8f0`
- `0x180055ea0`
- `0x180058230`
- `0x180059170`
- `0x180059f9c`
- `0x18005b530`
- `0x18005bbf0`
- `0x180062450`
- `0x1800633e0`
- `0x18006d150`
- `0x18006fc70`
- `0x18006fdd0`
- `0x180074b80`
- `0x180074bd0`
- `0x180074f90`
- `0x180078200`
- `0x18007b280`
- `0x180087d30`
- `0x1800883a0`
- `0x1800934b0`
- `0x180093e90`
- `0x180099560`

## callees

- `0x180084c4c`
- `0x18008b5f0`
- `0x18008bf98`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180084d29`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180084d44`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180084d5f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180084d29`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180084d44`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180084d5f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180084d03`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180084d03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180084ca7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180084ca7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180084ccd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180084ccd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180084ceb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180084ceb`

## string_xrefs

- `0x180084d39`: `dnsapi.dll`
- `0x180084d54`: `dnsrslvr.dll`

## pseudocode

```c
__int64 __fastcall Dns_IsCallerDns(LPCSTR lpModuleName)
{
  unsigned int v2; // edi
  wchar_t *v3; // rax
  wchar_t *v4; // rbx
  HMODULE phModule; // [rsp+20h] [rbp-448h] BYREF
  WCHAR Filename[264]; // [rsp+30h] [rbp-438h] BYREF
  WCHAR Buffer[264]; // [rsp+240h] [rbp-228h] BYREF

  v2 = 0;
  phModule = 0;
  memset_0(Buffer, 0, 0x208u);
  memset_0(Filename, 0, 0x208u);
  if ( GetModuleHandleExA(6u, lpModuleName, &phModule) )
  {
    if ( GetModuleFileNameW(phModule, Filename, 0x104u) )
    {
      if ( GetSystemDirectoryW(Buffer, 0x104u) )
      {
        v3 = wcsrchr(Filename, 0x5Cu);
        v4 = v3;
        if ( v3 )
        {
          *v3 = 0;
          if ( !(unsigned int)_o__wcsicmp(Buffer, Filename)
            && (!(unsigned int)_o__wcsicmp(v4 + 1, L"dnsapi.dll") || !(unsigned int)_o__wcsicmp(v4 + 1, L"dnsrslvr.dll")) )
          {
            return 1;
          }
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180084c4c  mov     [rsp+arg_8], rbx
0x180084c51  push    rdi
0x180084c52  sub     rsp, 460h
0x180084c59  mov     rax, cs:__security_cookie
0x180084c60  xor     rax, rsp
0x180084c63  mov     [rsp+468h+var_18], rax
0x180084c6b  mov     rbx, rcx
0x180084c6e  xor     edi, edi
0x180084c70  lea     rcx, [rsp+468h+Buffer]; void *
0x180084c78  mov     [rsp+468h+phModule], rdi
0x180084c7d  xor     edx, edx; Val
0x180084c7f  mov     r8d, 208h; Size
0x180084c85  call    memset_0
0x180084c8a  xor     edx, edx; Val
0x180084c8c  lea     rcx, [rsp+468h+Filename]; void *
0x180084c91  mov     r8d, 208h; Size
0x180084c97  call    memset_0
0x180084c9c  lea     r8, [rsp+468h+phModule]; phModule
0x180084ca1  mov     rdx, rbx; lpModuleName
0x180084ca4  lea     ecx, [rdi+6]; dwFlags
0x180084ca7  call    cs:__imp_GetModuleHandleExA
0x180084cae  nop     dword ptr [rax+rax+00h]
0x180084cb3  test    eax, eax
0x180084cb5  jz      loc_180084D74
0x180084cbb  mov     rcx, [rsp+468h+phModule]; hModule
0x180084cc0  lea     rdx, [rsp+468h+Filename]; lpFilename
0x180084cc5  mov     ebx, 104h
0x180084cca  mov     r8d, ebx; nSize
0x180084ccd  call    cs:__imp_GetModuleFileNameW
0x180084cd4  nop     dword ptr [rax+rax+00h]
0x180084cd9  test    eax, eax
0x180084cdb  jz      loc_180084D74
0x180084ce1  mov     edx, ebx; uSize
0x180084ce3  lea     rcx, [rsp+468h+Buffer]; lpBuffer
0x180084ceb  call    cs:__imp_GetSystemDirectoryW
0x180084cf2  nop     dword ptr [rax+rax+00h]
0x180084cf7  test    eax, eax
0x180084cf9  jz      short loc_180084D74
0x180084cfb  lea     edx, [rdi+5Ch]; Ch
0x180084cfe  lea     rcx, [rsp+468h+Filename]; Str
0x180084d03  call    cs:__imp_wcsrchr
0x180084d0a  nop     dword ptr [rax+rax+00h]
0x180084d0f  mov     rbx, rax
0x180084d12  test    rax, rax
0x180084d15  jz      short loc_180084D74
0x180084d17  xor     ecx, ecx
0x180084d19  lea     rdx, [rsp+468h+Filename]
0x180084d1e  mov     [rax], cx
0x180084d21  lea     rcx, [rsp+468h+Buffer]
0x180084d29  call    cs:__imp__o__wcsicmp
0x180084d30  nop     dword ptr [rax+rax+00h]
0x180084d35  test    eax, eax
0x180084d37  jnz     short loc_180084D74
0x180084d39  lea     rdx, LibFileName; "dnsapi.dll"
0x180084d40  lea     rcx, [rbx+2]
0x180084d44  call    cs:__imp__o__wcsicmp
0x180084d4b  nop     dword ptr [rax+rax+00h]
0x180084d50  test    eax, eax
0x180084d52  jz      short loc_180084D6F
0x180084d54  lea     rdx, aDnsrslvrDll; "dnsrslvr.dll"
0x180084d5b  lea     rcx, [rbx+2]
0x180084d5f  call    cs:__imp__o__wcsicmp
0x180084d66  nop     dword ptr [rax+rax+00h]
0x180084d6b  test    eax, eax
0x180084d6d  jnz     short loc_180084D74
0x180084d6f  mov     edi, 1
0x180084d74  mov     eax, edi
0x180084d76  mov     rcx, [rsp+468h+var_18]
0x180084d7e  xor     rcx, rsp; StackCookie
0x180084d81  call    __security_check_cookie
0x180084d86  mov     rbx, [rsp+468h+arg_8]
0x180084d8e  add     rsp, 460h
0x180084d95  pop     rdi
0x180084d96  retn
```
