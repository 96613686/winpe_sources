# Microsoft::HostGuardian::Client::Utilities::GetDurationStatus(_FILETIME)

- ea: `0x180014ed8`
- end: `0x180014f89`
- name: `?GetDurationStatus@Utilities@Client@HostGuardian@Microsoft@@YA?AW4DurationStatus@1234@U_FILETIME@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(FILETIME)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d4d8`
- `0x18000f548`
- `0x180014e74`

## callees

- `0x180001770`
- `0x180014ed8`
- `0x180014f90`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180014f0a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180014f0a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180014f45`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180014f62`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180014f45`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180014f62`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180014f18`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180014f18`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::Utilities::GetDurationStatus(FILETIME a1)
{
  void *v1; // rdx
  unsigned int v2; // r8d
  const char *v3; // r9
  struct _FILETIME FileTime; // [rsp+20h] [rbp-30h] BYREF
  FILETIME FileTime2; // [rsp+28h] [rbp-28h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  FileTime2 = a1;
  FileTime = 0;
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    *(_QWORD *)&FileTime += 36000000000LL;
    if ( CompareFileTime(&FileTime, &FileTime2) >= 0 )
    {
      *(_QWORD *)&FileTime -= 36000000000LL;
      return (unsigned int)(CompareFileTime(&FileTime, &FileTime2) >= 0) + 2;
    }
    else
    {
      return 1;
    }
  }
  else
  {
    wil::details::in1diag3::Log_GetLastError(retaddr, v1, v2, v3);
    return 0;
  }
}

```

## disassembly

```asm
0x180014ed8  mov     [rsp-8+arg_8], rbx
0x180014edd  push    rbp
0x180014ede  mov     rbp, rsp
0x180014ee1  sub     rsp, 50h
0x180014ee5  mov     rax, cs:__security_cookie
0x180014eec  xor     rax, rsp
0x180014eef  mov     [rbp+var_10], rax
0x180014ef3  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rcx
0x180014ef7  xorps   xmm0, xmm0
0x180014efa  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180014efe  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x180014f06  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180014f0a  call    cs:__imp_GetSystemTime
0x180014f10  lea     rdx, [rbp+FileTime]; lpFileTime
0x180014f14  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180014f18  call    cs:__imp_SystemTimeToFileTime
0x180014f1e  test    eax, eax
0x180014f20  jnz     short loc_180014F2F
0x180014f22  mov     rcx, [rbp+8]; this
0x180014f26  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180014f2b  xor     eax, eax
0x180014f2d  jmp     short loc_180014F72
0x180014f2f  mov     rbx, 861C46800h
0x180014f39  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x180014f3d  add     qword ptr [rbp+FileTime.dwLowDateTime], rbx
0x180014f41  lea     rcx, [rbp+FileTime]; lpFileTime1
0x180014f45  call    cs:__imp_CompareFileTime
0x180014f4b  test    eax, eax
0x180014f4d  jns     short loc_180014F56
0x180014f4f  mov     eax, 1
0x180014f54  jmp     short loc_180014F72
0x180014f56  sub     qword ptr [rbp+FileTime.dwLowDateTime], rbx
0x180014f5a  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x180014f5e  lea     rcx, [rbp+FileTime]; lpFileTime1
0x180014f62  call    cs:__imp_CompareFileTime
0x180014f68  xor     ecx, ecx
0x180014f6a  test    eax, eax
0x180014f6c  setns   cl
0x180014f6f  lea     eax, [rcx+2]
0x180014f72  mov     rcx, [rbp+var_10]
0x180014f76  xor     rcx, rsp; StackCookie
0x180014f79  call    __security_check_cookie
0x180014f7e  mov     rbx, [rsp+50h+arg_8]
0x180014f83  add     rsp, 50h
0x180014f87  pop     rbp
0x180014f88  retn
```
