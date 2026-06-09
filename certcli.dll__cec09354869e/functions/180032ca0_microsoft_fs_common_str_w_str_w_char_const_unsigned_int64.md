# microsoft::fs::common::str_w::str_w(char const *,unsigned __int64)

- ea: `0x180032ca0`
- end: `0x180032e6d`
- name: `??0str_w@common@fs@microsoft@@QEAA@PEBD_K@Z`
- size: `461`
- prototype: `microsoft::fs::common::str_w *__fastcall(microsoft::fs::common::str_w *this, const char *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180033160`
- `0x180035d40`

## callees

- `0x180001798`
- `0x1800022ec`
- `0x180019448`
- `0x18002b7d0`
- `0x18002e5e4`
- `0x180032ca0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180032de0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180032de0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032e0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032e0d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180032d38`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180032e03`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180032d38`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180032e03`

## string_xrefs

- `0x180032cf6`: `onecore\ds\security\services\ca\fs\common\str_t.h`
- `0x180032d61`: `onecore\ds\security\services\ca\fs\common\str_t.h`
- `0x180032e2b`: `onecore\ds\security\services\ca\fs\common\str_t.h`
- `0x180032db3`: `onecore\ds\security\services\ca\fs\common\auto_array.h`

## pseudocode

```c
microsoft::fs::common::str_w *__fastcall microsoft::fs::common::str_w::str_w(
        microsoft::fs::common::str_w *this,
        const char *a2,
        unsigned __int64 *a3)
{
  int v5; // eax
  int cchWideChar; // ebp
  DWORD LastError; // eax
  int v8; // eax
  WCHAR *v9; // rax
  WCHAR *lpWideCharStr; // rdi
  DWORD v11; // eax
  int v12; // eax
  _BYTE pExceptionObject[48]; // [rsp+30h] [rbp-48h] BYREF

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  if ( a2 )
  {
    if ( (int)StringCchLengthA(a2, (unsigned __int64)a2, a3) < 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\common\\str_t.h",
        121,
        L"0 == psz || SUCCEEDED(StringCchLengthA(psz, cchMaxLength, 0))",
        -2147024809);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    v5 = MultiByteToWideChar(0, 0, a2, -1, 0, 0);
    cchWideChar = v5;
    if ( !v5 )
    {
      LastError = GetLastError();
      v8 = HR_FROM_WIN32(LastError);
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\common\\str_t.h",
        126,
        L"0 != cch",
        v8);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    v9 = (WCHAR *)operator new[](saturated_mul(v5, 2u));
    lpWideCharStr = v9;
    if ( !v9 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\common\\auto_array.h",
        80,
        L"p",
        -2147024809);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    if ( v9 == *((WCHAR **)this + 1) )
    {
      lpWideCharStr = (WCHAR *)*((_QWORD *)this + 1);
    }
    else
    {
      operator delete[](*((void **)this + 1));
      *((_QWORD *)this + 1) = lpWideCharStr;
    }
    if ( !MultiByteToWideChar(0, 0, a2, -1, lpWideCharStr, cchWideChar) )
    {
      v11 = GetLastError();
      v12 = HR_FROM_WIN32(v11);
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\common\\str_t.h",
        128,
        L"0 != MultiByteToWideChar(CP_ACP, 0, psz, -1, m_wsz, cch)",
        v12);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    *(_QWORD *)this = *((_QWORD *)this + 1);
  }
  return this;
}

```

## disassembly

```asm
0x180032ca0  mov     [rsp+arg_8], rbx
0x180032ca5  mov     [rsp+arg_10], rbp
0x180032caa  mov     [rsp+arg_0], rcx
0x180032caf  push    rsi
0x180032cb0  push    rdi
0x180032cb1  push    r15
0x180032cb3  sub     rsp, 60h
0x180032cb7  mov     rsi, rdx
0x180032cba  mov     rbx, rcx
0x180032cbd  mov     qword ptr [rcx], 0
0x180032cc4  mov     qword ptr [rcx+8], 0
0x180032ccc  test    rdx, rdx
0x180032ccf  jz      loc_180032E55
0x180032cd5  mov     rcx, rdx; char *
0x180032cd8  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x180032cdd  test    eax, eax
0x180032cdf  jns     short loc_180032D19
0x180032ce1  mov     dword ptr [rsp+78h+lpWideCharStr], 80070057h; int
0x180032ce9  lea     r9, a0PszSucceededS; "0 == psz || SUCCEEDED(StringCchLengthA("...
0x180032cf0  mov     r8d, 79h ; 'y'; unsigned int
0x180032cf6  lea     rdx, aOnecoreDsSecur_6; "onecore\\ds\\security\\services\\ca\\fs"...
0x180032cfd  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180032d02  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180032d07  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180032d0e  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180032d13  call    _CxxThrowException_0
0x180032d19  mov     [rsp+78h+cchWideChar], 0; cchWideChar
0x180032d21  mov     [rsp+78h+lpWideCharStr], 0; lpWideCharStr
0x180032d2a  or      r15, 0FFFFFFFFFFFFFFFFh
0x180032d2e  mov     r9d, r15d; cbMultiByte
0x180032d31  mov     r8, rsi; lpMultiByteStr
0x180032d34  xor     edx, edx; dwFlags
0x180032d36  xor     ecx, ecx; CodePage
0x180032d38  call    cs:__imp_MultiByteToWideChar
0x180032d3e  movsxd  rbp, eax
0x180032d41  test    eax, eax
0x180032d43  jnz     short loc_180032D84
0x180032d45  call    cs:__imp_GetLastError
0x180032d4b  mov     ecx, eax; unsigned int
0x180032d4d  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x180032d52  mov     dword ptr [rsp+78h+lpWideCharStr], eax; int
0x180032d56  lea     r9, a0Cch; "0 != cch"
0x180032d5d  lea     r8d, [r15+7Fh]; unsigned int
0x180032d61  lea     rdx, aOnecoreDsSecur_6; "onecore\\ds\\security\\services\\ca\\fs"...
0x180032d68  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180032d6d  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180032d72  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180032d79  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180032d7e  call    _CxxThrowException_0
0x180032d84  mov     eax, 2
0x180032d89  mul     rbp
0x180032d8c  cmovb   rax, r15
0x180032d90  mov     rcx, rax; unsigned __int64
0x180032d93  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180032d98  mov     rdi, rax
0x180032d9b  test    rax, rax
0x180032d9e  jnz     short loc_180032DD6
0x180032da0  mov     dword ptr [rsp+78h+lpWideCharStr], 80070057h; int
0x180032da8  lea     r9, aP; "p"
0x180032daf  lea     r8d, [rax+50h]; unsigned int
0x180032db3  lea     rdx, aOnecoreDsSecur_2; "onecore\\ds\\security\\services\\ca\\fs"...
0x180032dba  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180032dbf  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180032dc4  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180032dcb  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180032dd0  call    _CxxThrowException_0
0x180032dd6  cmp     rdi, [rbx+8]
0x180032dda  jz      short loc_180032DEC
0x180032ddc  mov     rcx, [rbx+8]
0x180032de0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180032de6  mov     [rbx+8], rdi
0x180032dea  jmp     short loc_180032DF0
0x180032dec  mov     rdi, [rbx+8]
0x180032df0  mov     [rsp+78h+cchWideChar], ebp; cchWideChar
0x180032df4  mov     [rsp+78h+lpWideCharStr], rdi; lpWideCharStr
0x180032df9  mov     r9d, r15d; cbMultiByte
0x180032dfc  mov     r8, rsi; lpMultiByteStr
0x180032dff  xor     edx, edx; dwFlags
0x180032e01  xor     ecx, ecx; CodePage
0x180032e03  call    cs:__imp_MultiByteToWideChar
0x180032e09  test    eax, eax
0x180032e0b  jnz     short loc_180032E4E
0x180032e0d  call    cs:__imp_GetLastError
0x180032e13  mov     ecx, eax; unsigned int
0x180032e15  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x180032e1a  mov     dword ptr [rsp+78h+lpWideCharStr], eax; int
0x180032e1e  lea     r9, a0Multibytetowi; "0 != MultiByteToWideChar(CP_ACP, 0, psz"...
0x180032e25  mov     r8d, 80h; unsigned int
0x180032e2b  lea     rdx, aOnecoreDsSecur_6; "onecore\\ds\\security\\services\\ca\\fs"...
0x180032e32  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180032e37  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180032e3c  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180032e43  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180032e48  call    _CxxThrowException_0
0x180032e4e  mov     rax, [rbx+8]
0x180032e52  mov     [rbx], rax
0x180032e55  mov     rax, rbx
0x180032e58  lea     r11, [rsp+78h+var_18]
0x180032e5d  mov     rbx, [r11+28h]
0x180032e61  mov     rbp, [r11+30h]
0x180032e65  mov     rsp, r11
0x180032e68  pop     r15
0x180032e6a  pop     rdi
0x180032e6b  pop     rsi
0x180032e6c  retn
```
