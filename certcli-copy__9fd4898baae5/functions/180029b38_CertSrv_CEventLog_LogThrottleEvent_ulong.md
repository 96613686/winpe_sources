# CertSrv::CEventLog::LogThrottleEvent(ulong)

- ea: `0x180029b38`
- end: `0x180029bde`
- name: `?LogThrottleEvent@CEventLog@CertSrv@@AEAAHK@Z`
- size: `166`
- prototype: `__int64 __fastcall(CertSrv::CEventLog *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002993c`

## callees

- `0x180029b38`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180029ba3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180029ba3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180029b89`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180029b89`

## pseudocode

```c
__int64 __fastcall CertSrv::CEventLog::LogThrottleEvent(CertSrv::CEventLog *this)
{
  unsigned int v1; // esi
  __int64 v2; // rdi
  unsigned int i; // eax
  __int64 v4; // rbx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp+8h] BYREF
  FILETIME FileTime1; // [rsp+40h] [rbp+18h] BYREF

  SystemTimeAsFileTime = (struct _FILETIME)this;
  v1 = 0;
  if ( (unsigned int)dword_180069D1C < 5 )
  {
    v2 = CertEnrollHttp::g_Event;
    for ( i = 0; i < dword_180069D18; ++i )
    {
      v4 = 2LL * i;
      if ( *(_DWORD *)(CertEnrollHttp::g_Event + 16LL * i) == 10000 )
      {
        SystemTimeAsFileTime = 0;
        FileTime1 = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        FileTime1 = *(FILETIME *)(v2 + 8 * v4 + 8);
        if ( CompareFileTime(&FileTime1, &SystemTimeAsFileTime) >= 0 )
          return 1;
        else
          *(_QWORD *)(v2 + 8 * v4 + 8) = 10000000LL * *(unsigned int *)(v2 + 8 * v4 + 4)
                                       + *(_QWORD *)&SystemTimeAsFileTime;
        return v1;
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180029b38  mov     [rsp+arg_8], rbx
0x180029b3d  mov     [rsp+arg_18], rsi
0x180029b42  mov     qword ptr [rsp+SystemTimeAsFileTime.dwLowDateTime], rcx
0x180029b47  push    rdi
0x180029b48  sub     rsp, 20h
0x180029b4c  xor     esi, esi
0x180029b4e  cmp     cs:dword_180069D1C, 5
0x180029b55  jnb     short loc_180029BCC
0x180029b57  mov     rdi, cs:?g_Event@CertEnrollHttp@@3VCEventLog@CertSrv@@A; CertSrv::CEventLog CertEnrollHttp::g_Event
0x180029b5e  xor     eax, eax
0x180029b60  cmp     eax, cs:dword_180069D18
0x180029b66  jnb     short loc_180029BCC
0x180029b68  mov     ebx, eax
0x180029b6a  add     rbx, rbx
0x180029b6d  cmp     dword ptr [rdi+rbx*8], 2710h
0x180029b74  jz      short loc_180029B7A
0x180029b76  inc     eax
0x180029b78  jmp     short loc_180029B60
0x180029b7a  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180029b7f  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x180029b84  mov     qword ptr [rsp+28h+FileTime1.dwLowDateTime], rsi
0x180029b89  call    cs:__imp_GetSystemTimeAsFileTime
0x180029b8f  mov     rax, [rdi+rbx*8+8]
0x180029b94  lea     rdx, [rsp+28h+SystemTimeAsFileTime]; lpFileTime2
0x180029b99  lea     rcx, [rsp+28h+FileTime1]; lpFileTime1
0x180029b9e  mov     qword ptr [rsp+28h+FileTime1.dwLowDateTime], rax
0x180029ba3  call    cs:__imp_CompareFileTime
0x180029ba9  test    eax, eax
0x180029bab  jns     short loc_180029BC7
0x180029bad  mov     eax, [rdi+rbx*8+4]
0x180029bb1  imul    rcx, rax, 989680h
0x180029bb8  mov     rax, qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]
0x180029bbd  add     rax, rcx
0x180029bc0  mov     [rdi+rbx*8+8], rax
0x180029bc5  jmp     short loc_180029BCC
0x180029bc7  mov     esi, 1
0x180029bcc  mov     rbx, [rsp+28h+arg_8]
0x180029bd1  mov     eax, esi
0x180029bd3  mov     rsi, [rsp+28h+arg_18]
0x180029bd8  add     rsp, 20h
0x180029bdc  pop     rdi
0x180029bdd  retn
```
