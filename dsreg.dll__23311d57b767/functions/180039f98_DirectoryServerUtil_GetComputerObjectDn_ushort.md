# DirectoryServerUtil::GetComputerObjectDn(ushort * *)

- ea: `0x180039f98`
- end: `0x18003a12f`
- name: `?GetComputerObjectDn@DirectoryServerUtil@@CAJPEAPEAG@Z`
- size: `407`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18004b240`
- `0x18004b468`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x1800307c4`
- `0x18003334c`
- `0x180039f98`
- `0x18003a138`
- `0x180043ef8`
- `0x18004654c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a00b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a01f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a0b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a0c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a00b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a01f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a0b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a0c6`
- `ext-ms-win-secur32-translatename-l1-1-0!GetComputerObjectNameW` at `0x18003a001`
- `ext-ms-win-secur32-translatename-l1-1-0!GetComputerObjectNameW` at `0x18003a0a8`
- `ext-ms-win-secur32-translatename-l1-1-0!GetComputerObjectNameW` at `0x18003a001`
- `ext-ms-win-secur32-translatename-l1-1-0!GetComputerObjectNameW` at `0x18003a0a8`

## string_xrefs

- `0x18003a037`: `GetComputerObjectNameW`
- `0x18003a0de`: `GetComputerObjectNameW`
- `0x180039fc3`: `DirectoryServerUtil::GetComputerObjectDn`
- `0x180039fdd`: `DirectoryServerUtil::GetComputerObjectDn`
- `0x18003a03e`: `DirectoryServerUtil::GetComputerObjectDn`
- `0x18003a084`: `DirectoryServerUtil::GetComputerObjectDn`
- `0x18003a0e5`: `DirectoryServerUtil::GetComputerObjectDn`
- `0x18003a104`: `DirectoryServerUtil::GetComputerObjectDn`
- `0x180039fb7`: `ppszComputerDn`
- `0x180039fd6`: `ppszComputerDn`
- `0x18003a10e`: `%s: DN of the computer object is %s`

## pseudocode

```c
__int64 __fastcall DirectoryServerUtil::GetComputerObjectDn(unsigned __int16 **a1)
{
  unsigned int v2; // ebx
  DWORD v3; // eax
  signed int v4; // eax
  unsigned __int64 v5; // rax
  WCHAR *v6; // rax
  unsigned __int16 *v7; // rsi
  DWORD LastError; // eax
  signed int v9; // eax
  ULONG nSize; // [rsp+30h] [rbp+8h] BYREF

  nSize = 0;
  if ( a1 )
  {
    *a1 = 0;
    if ( GetComputerObjectNameW(NameFullyQualifiedDN, 0, &nSize) )
    {
      v5 = 2LL * nSize;
      if ( !is_mul_ok(nSize, 2u) )
        v5 = -1;
      v6 = (WCHAR *)operator new[](v5, (const struct std::nothrow_t *)&std::nothrow);
      v7 = v6;
      if ( v6 )
      {
        if ( GetComputerObjectNameW(NameFullyQualifiedDN, v6, &nSize) )
        {
          v2 = 0;
          Logger::TraceVerbose(
            (wchar_t *)L"%s: DN of the computer object is %s",
            L"DirectoryServerUtil::GetComputerObjectDn",
            v7);
          *a1 = v7;
        }
        else
        {
          LastError = GetLastError();
          Logger::WriteGetComputerNameFailureEvent(L"NameFullyQualifiedDN", LastError);
          v9 = GetLastError();
          v2 = v9;
          if ( v9 > 0 )
            v2 = (unsigned __int16)v9 | 0x80070000;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x",
            L"DirectoryServerUtil::GetComputerObjectDn",
            L"GetComputerObjectNameW",
            v2);
          operator delete(v7);
        }
      }
      else
      {
        v2 = -2147024882;
        Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"DirectoryServerUtil::GetComputerObjectDn");
      }
    }
    else
    {
      v3 = GetLastError();
      Logger::WriteGetComputerNameFailureEvent(L"NameFullyQualifiedDN", v3);
      v4 = GetLastError();
      v2 = v4;
      if ( v4 > 0 )
        v2 = (unsigned __int16)v4 | 0x80070000;
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x",
        L"DirectoryServerUtil::GetComputerObjectDn",
        L"GetComputerObjectNameW",
        v2);
    }
  }
  else
  {
    v2 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DirectoryServerUtil::GetComputerObjectDn",
      L"ppszComputerDn");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"DirectoryServerUtil::GetComputerObjectDn", L"ppszComputerDn");
  }
  return v2;
}

```

## disassembly

```asm
0x180039f98  mov     [rsp+arg_8], rbx
0x180039f9d  mov     [rsp+arg_10], rsi
0x180039fa2  push    rdi
0x180039fa3  sub     rsp, 20h
0x180039fa7  mov     [rsp+28h+nSize], 0
0x180039faf  mov     rdi, rcx
0x180039fb2  test    rcx, rcx
0x180039fb5  jnz     short loc_180039FEE
0x180039fb7  lea     r8, aPpszcomputerdn; "ppszComputerDn"
0x180039fbe  mov     ebx, 80070057h
0x180039fc3  lea     rdx, aDirectoryserve_3; "DirectoryServerUtil::GetComputerObjectD"...
0x180039fca  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180039fd1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180039fd6  lea     rdx, aPpszcomputerdn; "ppszComputerDn"
0x180039fdd  lea     rcx, aDirectoryserve_3; "DirectoryServerUtil::GetComputerObjectD"...
0x180039fe4  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180039fe9  jmp     loc_18003A11D
0x180039fee  xor     edx, edx; lpNameBuffer
0x180039ff0  mov     qword ptr [rcx], 0
0x180039ff7  lea     r8, [rsp+28h+nSize]; nSize
0x180039ffc  lea     ebx, [rdx+1]
0x180039fff  mov     ecx, ebx; NameFormat
0x18003a001  call    cs:__imp_GetComputerObjectNameW
0x18003a007  test    al, al
0x18003a009  jnz     short loc_18003A056
0x18003a00b  call    cs:__imp_GetLastError
0x18003a011  mov     edx, eax; unsigned int
0x18003a013  lea     rcx, aNamefullyquali; "NameFullyQualifiedDN"
0x18003a01a  call    ?WriteGetComputerNameFailureEvent@Logger@@SAJPEBGK@Z; Logger::WriteGetComputerNameFailureEvent(ushort const *,ulong)
0x18003a01f  call    cs:__imp_GetLastError
0x18003a025  mov     ebx, eax
0x18003a027  test    eax, eax
0x18003a029  jle     short loc_18003A034
0x18003a02b  movzx   ebx, ax
0x18003a02e  or      ebx, 80070000h
0x18003a034  mov     r9d, ebx
0x18003a037  lea     r8, aGetcomputerobj_1; "GetComputerObjectNameW"
0x18003a03e  lea     rdx, aDirectoryserve_3; "DirectoryServerUtil::GetComputerObjectD"...
0x18003a045  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x"
0x18003a04c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003a051  jmp     loc_18003A11D
0x18003a056  mov     ecx, [rsp+28h+nSize]
0x18003a05a  mov     eax, 2
0x18003a05f  mul     rcx
0x18003a062  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003a069  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003a070  cmovb   rax, rcx
0x18003a074  mov     rcx, rax; unsigned __int64
0x18003a077  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003a07c  mov     rsi, rax
0x18003a07f  test    rax, rax
0x18003a082  jnz     short loc_18003A09E
0x18003a084  lea     rdx, aDirectoryserve_3; "DirectoryServerUtil::GetComputerObjectD"...
0x18003a08b  mov     ebx, 8007000Eh
0x18003a090  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x18003a097  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18003a09c  jmp     short loc_18003A11D
0x18003a09e  lea     r8, [rsp+28h+nSize]; nSize
0x18003a0a3  mov     rdx, rsi; lpNameBuffer
0x18003a0a6  mov     ecx, ebx; NameFormat
0x18003a0a8  call    cs:__imp_GetComputerObjectNameW
0x18003a0ae  test    al, al
0x18003a0b0  jnz     short loc_18003A102
0x18003a0b2  call    cs:__imp_GetLastError
0x18003a0b8  mov     edx, eax; unsigned int
0x18003a0ba  lea     rcx, aNamefullyquali; "NameFullyQualifiedDN"
0x18003a0c1  call    ?WriteGetComputerNameFailureEvent@Logger@@SAJPEBGK@Z; Logger::WriteGetComputerNameFailureEvent(ushort const *,ulong)
0x18003a0c6  call    cs:__imp_GetLastError
0x18003a0cc  mov     ebx, eax
0x18003a0ce  test    eax, eax
0x18003a0d0  jle     short loc_18003A0DB
0x18003a0d2  movzx   ebx, ax
0x18003a0d5  or      ebx, 80070000h
0x18003a0db  mov     r9d, ebx
0x18003a0de  lea     r8, aGetcomputerobj_1; "GetComputerObjectNameW"
0x18003a0e5  lea     rdx, aDirectoryserve_3; "DirectoryServerUtil::GetComputerObjectD"...
0x18003a0ec  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x"
0x18003a0f3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003a0f8  mov     rcx, rsi; Block
0x18003a0fb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003a100  jmp     short loc_18003A11D
0x18003a102  xor     ebx, ebx
0x18003a104  lea     rdx, aDirectoryserve_3; "DirectoryServerUtil::GetComputerObjectD"...
0x18003a10b  mov     r8, rsi
0x18003a10e  lea     rcx, aSDnOfTheComput; "%s: DN of the computer object is %s"
0x18003a115  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18003a11a  mov     [rdi], rsi
0x18003a11d  mov     rsi, [rsp+28h+arg_10]
0x18003a122  mov     eax, ebx
0x18003a124  mov     rbx, [rsp+28h+arg_8]
0x18003a129  add     rsp, 20h
0x18003a12d  pop     rdi
0x18003a12e  retn
```
