# CPreferredKeys::CPreferredKey::ReadFromLsaSecret(void)

- ea: `0x180032cb4`
- end: `0x180032e7e`
- name: `?ReadFromLsaSecret@CPreferredKey@CPreferredKeys@@AEAAJXZ`
- size: `458`
- prototype: `__int64 __fastcall(CPreferredKeys::CPreferredKey *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180035320`

## callees

- `0x180007f10`
- `0x18001d810`
- `0x180030414`
- `0x18003281c`
- `0x180032a9c`
- `0x180032cb4`
- `0x180032e84`
- `0x180035da4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032e24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032e24`

## string_xrefs

- `0x180032d0d`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180032db8`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180032e3b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall CPreferredKeys::CPreferredKey::ReadFromLsaSecret(CPreferredKeys::CPreferredKey *this)
{
  unsigned int v2; // ecx
  int v3; // eax
  wil::filetime *v4; // rcx
  unsigned int v5; // esi
  struct _FILETIME system_time; // rax
  union _LARGE_INTEGER v8; // rbx
  struct _FILETIME v9; // r15
  unsigned int LastError; // ebx
  HLOCAL v11; // r14
  DWORD LowPart; // r12d
  struct _GUID v13; // xmm0
  union _LARGE_INTEGER v14; // [rsp+20h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-28h] BYREF
  struct _GUID v16; // [rsp+30h] [rbp-20h] BYREF

  v14.QuadPart = 0;
  v2 = *(_DWORD *)this;
  v16 = GUID_NULL;
  v3 = CPreferredKeys::CPreferredKey::ReadGuidAndTimeFromLsaSecret(v2, &v16, &v14);
  v5 = v3;
  if ( v3 < 0 )
  {
    DebugTraceError((unsigned int)v3, "status", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 3634);
    return v5;
  }
  system_time = wil::filetime::get_system_time(v4);
  v8 = v14;
  if ( v14.QuadPart <= 0 || (v9 = system_time, v14.QuadPart > *(_QWORD *)&system_time) )
  {
    DebugTraceError(1901, "ERROR_INVALID_TIME", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 3644);
    return 3221225485LL;
  }
  else
  {
    hMem = 0;
    v14.LowPart = 0;
    if ( (unsigned int)ReadBackupKeyFromLsaSecret(&v16, (unsigned __int8 **)&hMem, (unsigned int *)&v14) )
    {
      v11 = hMem;
      LowPart = v14.LowPart;
      if ( CPreferredKeys::IsValidKeyBuffer(*(_DWORD *)this, (unsigned __int8 *const)hMem, v14.LowPart) )
      {
        CPreferredKeys::CPreferredKey::Clean(this);
        v13 = v16;
        *((_DWORD *)this + 8) = LowPart;
        *((_QWORD *)this + 3) = v11;
        *(struct _GUID *)((char *)this + 4) = v13;
        *((union _LARGE_INTEGER *)this + 5) = v8;
        *((struct _FILETIME *)this + 6) = v9;
      }
      else
      {
        v5 = -1073283059;
        if ( v11 )
          LocalFree(v11);
      }
      return v5;
    }
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0xC0070000;
    else
      LastError = GetLastError();
    DebugTraceError(LastError, "status", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 3655);
    return LastError;
  }
}

```

## disassembly

```asm
0x180032cb4  mov     [rsp-28h+arg_8], rbx
0x180032cb9  mov     [rsp-28h+arg_10], rsi
0x180032cbe  push    rbp
0x180032cbf  push    rdi
0x180032cc0  push    r12
0x180032cc2  push    r14
0x180032cc4  push    r15
0x180032cc6  mov     rbp, rsp
0x180032cc9  sub     rsp, 50h
0x180032ccd  mov     rax, cs:__security_cookie
0x180032cd4  xor     rax, rsp
0x180032cd7  mov     [rbp+var_10], rax
0x180032cdb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180032ce2  mov     rdi, rcx
0x180032ce5  mov     qword ptr [rbp+var_30], 0
0x180032ced  mov     ecx, [rcx]; unsigned int
0x180032cef  lea     r8, [rbp+var_30]; union _LARGE_INTEGER *
0x180032cf3  lea     rdx, [rbp+var_20]; struct _GUID *
0x180032cf7  movdqu  xmmword ptr [rbp+var_20.Data1], xmm0
0x180032cfc  call    ?ReadGuidAndTimeFromLsaSecret@CPreferredKey@CPreferredKeys@@SAJKPEAU_GUID@@PEAT_LARGE_INTEGER@@@Z; CPreferredKeys::CPreferredKey::ReadGuidAndTimeFromLsaSecret(ulong,_GUID *,_LARGE_INTEGER *)
0x180032d01  mov     esi, eax
0x180032d03  test    eax, eax
0x180032d05  jns     short loc_180032D29
0x180032d07  mov     r9d, 0E32h
0x180032d0d  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180032d14  lea     rdx, aStatus_0; "status"
0x180032d1b  mov     ecx, eax
0x180032d1d  call    DebugTraceError
0x180032d22  mov     eax, esi
0x180032d24  jmp     loc_180032E58
0x180032d29  call    ?get_system_time@filetime@wil@@YA?AU_FILETIME@@XZ; wil::filetime::get_system_time(void)
0x180032d2e  mov     rbx, qword ptr [rbp+var_30]
0x180032d32  test    rbx, rbx
0x180032d35  jle     loc_180032E35
0x180032d3b  mov     rcx, 0FFFFFFFF00000000h
0x180032d45  mov     r15, rax
0x180032d48  and     r15, rcx
0x180032d4b  mov     ecx, eax
0x180032d4d  add     r15, rcx
0x180032d50  cmp     rbx, r15
0x180032d53  jg      loc_180032E35
0x180032d59  lea     r8, [rbp+var_30]; unsigned int *
0x180032d5d  mov     [rbp+hMem], 0
0x180032d65  lea     rdx, [rbp+hMem]; unsigned __int8 **
0x180032d69  mov     dword ptr [rbp+var_30], 0
0x180032d70  lea     rcx, [rbp+var_20]; struct _GUID *
0x180032d74  call    ?ReadBackupKeyFromLsaSecret@@YAHPEBU_GUID@@PEAPEAEPEAK@Z; ReadBackupKeyFromLsaSecret(_GUID const *,uchar * *,ulong *)
0x180032d79  test    eax, eax
0x180032d7b  jnz     short loc_180032DD4
0x180032d7d  call    cs:__imp_GetLastError
0x180032d84  nop     dword ptr [rax+rax+00h]
0x180032d89  test    eax, eax
0x180032d8b  jg      short loc_180032D9D
0x180032d8d  call    cs:__imp_GetLastError
0x180032d94  nop     dword ptr [rax+rax+00h]
0x180032d99  mov     ebx, eax
0x180032d9b  jmp     short loc_180032DB2
0x180032d9d  call    cs:__imp_GetLastError
0x180032da4  nop     dword ptr [rax+rax+00h]
0x180032da9  movzx   ebx, ax
0x180032dac  or      ebx, 0C0070000h
0x180032db2  mov     r9d, 0E47h
0x180032db8  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180032dbf  lea     rdx, aStatus_0; "status"
0x180032dc6  mov     ecx, ebx
0x180032dc8  call    DebugTraceError
0x180032dcd  mov     eax, ebx
0x180032dcf  jmp     loc_180032E58
0x180032dd4  mov     r14, [rbp+hMem]
0x180032dd8  mov     r12d, dword ptr [rbp+var_30]
0x180032ddc  mov     rdx, r14; unsigned __int8 *
0x180032ddf  mov     ecx, [rdi]; unsigned int
0x180032de1  mov     r8d, r12d; unsigned int
0x180032de4  call    ?IsValidKeyBuffer@CPreferredKeys@@SA_NKQEAEK@Z; CPreferredKeys::IsValidKeyBuffer(ulong,uchar * const,ulong)
0x180032de9  test    al, al
0x180032deb  jz      short loc_180032E13
0x180032ded  mov     rcx, rdi; this
0x180032df0  call    ?Clean@CPreferredKey@CPreferredKeys@@AEAAXXZ; CPreferredKeys::CPreferredKey::Clean(void)
0x180032df5  movups  xmm0, xmmword ptr [rbp+var_20.Data1]
0x180032df9  mov     [rdi+20h], r12d
0x180032dfd  mov     [rdi+18h], r14
0x180032e01  movdqu  xmmword ptr [rdi+4], xmm0
0x180032e06  mov     [rdi+28h], rbx
0x180032e0a  mov     [rdi+30h], r15
0x180032e0e  jmp     loc_180032D22
0x180032e13  mov     esi, 0C007000Dh
0x180032e18  test    r14, r14
0x180032e1b  jz      loc_180032D22
0x180032e21  mov     rcx, r14; hMem
0x180032e24  call    cs:__imp_LocalFree
0x180032e2b  nop     dword ptr [rax+rax+00h]
0x180032e30  jmp     loc_180032D22
0x180032e35  mov     r9d, 0E3Ch
0x180032e3b  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180032e42  lea     rdx, aErrorInvalidTi; "ERROR_INVALID_TIME"
0x180032e49  mov     ecx, 76Dh
0x180032e4e  call    DebugTraceError
0x180032e53  mov     eax, 0C000000Dh
0x180032e58  mov     rcx, [rbp+var_10]
0x180032e5c  xor     rcx, rsp; StackCookie
0x180032e5f  call    __security_check_cookie
0x180032e64  lea     r11, [rsp+50h+var_s0]
0x180032e69  mov     rbx, [r11+38h]
0x180032e6d  mov     rsi, [r11+40h]
0x180032e71  mov     rsp, r11
0x180032e74  pop     r15
0x180032e76  pop     r14
0x180032e78  pop     r12
0x180032e7a  pop     rdi
0x180032e7b  pop     rbp
0x180032e7c  retn
```
