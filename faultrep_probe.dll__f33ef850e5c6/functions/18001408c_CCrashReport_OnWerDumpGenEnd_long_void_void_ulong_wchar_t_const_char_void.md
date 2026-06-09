# CCrashReport::OnWerDumpGenEnd(long,void (*)(void *,ulong,wchar_t const *,char *),void *)

- ea: `0x18001408c`
- end: `0x180014163`
- name: `?OnWerDumpGenEnd@CCrashReport@@AEAAHJP6AXPEAXKPEB_WPEAD@Z0@Z`
- size: `215`
- prototype: `int(CCrashReport *__hidden this, int, void (*)(void *, unsigned int, const wchar_t *, char *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001611c`

## callees

- `0x18000f700`
- `0x18001408c`
- `0x18003e5a8`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800140ed`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800140ed`
- `wer!WerpResetTransientImageCacheStatistics` at `0x180014148`
- `wer!WerpResetTransientImageCacheStatistics` at `0x180014148`
- `wer!WerpTraceImageCacheStatistics` at `0x180014118`
- `wer!WerpTraceImageCacheStatistics` at `0x180014118`

## string_xrefs

- `0x1800140c2`: `VM read statistics:\n- Pre-read calls : %9u\n- Post-read calls: %9u\n\n`

## pseudocode

```c
__int64 __fastcall CCrashReport::OnWerDumpGenEnd(
        CCrashReport *this,
        __int64 a2,
        void (*a3)(void *, unsigned int, const wchar_t *, char *),
        void *a4)
{
  bool v4; // zf
  __int64 v8; // rcx
  LARGE_INTEGER Frequency; // [rsp+40h] [rbp+8h] BYREF

  v4 = *((_QWORD *)this + 617) == 0;
  Frequency.QuadPart = 0;
  if ( !v4 && a3 )
  {
    CCrashReport::CallWerpLogger(
      a3,
      a4,
      0xC0000002,
      L"VM read statistics:\r\n- Pre-read calls : %9u\r\n- Post-read calls: %9u\r\n\r\n",
      *((_DWORD *)this + 1276),
      *((_DWORD *)this + 1277));
    QueryPerformanceFrequency(&Frequency);
    if ( !Frequency.QuadPart )
      MicrosoftTelemetryAssertTriggeredNoArgs(v8);
    WerpTraceImageCacheStatistics(a3, a4, (char *)this + 9336, &Frequency);
    CCrashReport::CallWerpLogger(a3, a4, 0xC0000002, L"\r\n\r\n");
  }
  *((_QWORD *)this + 638) = 0;
  WerpResetTransientImageCacheStatistics((CCrashReport *)((char *)this + 9336));
  return 1;
}

```

## disassembly

```asm
0x18001408c  mov     [rsp+arg_8], rbx
0x180014091  mov     [rsp+arg_10], rsi
0x180014096  push    rdi
0x180014097  sub     rsp, 30h
0x18001409b  cmp     qword ptr [rcx+1348h], 0
0x1800140a3  mov     rsi, r9
0x1800140a6  mov     rdi, r8
0x1800140a9  mov     qword ptr [rsp+38h+Frequency], 0
0x1800140b2  mov     rbx, rcx
0x1800140b5  jz      short loc_180014136
0x1800140b7  test    r8, r8
0x1800140ba  jz      short loc_180014136
0x1800140bc  mov     eax, [rcx+13F4h]
0x1800140c2  lea     r9, aVmReadStatisti; "VM read statistics:\r\n- Pre-read calls"...
0x1800140c9  mov     [rsp+38h+var_10], eax
0x1800140cd  mov     r8d, 0C0000002h; unsigned int
0x1800140d3  mov     eax, [rcx+13F0h]
0x1800140d9  mov     rdx, rsi; void *
0x1800140dc  mov     rcx, rdi; void (*)(void *, unsigned int, const wchar_t *, char *)
0x1800140df  mov     [rsp+38h+var_18], eax
0x1800140e3  call    ?CallWerpLogger@CCrashReport@@CAXP6AXPEAXKPEB_WPEAD@Z0K1ZZ; CCrashReport::CallWerpLogger(void (*)(void *,ulong,wchar_t const *,char *),void *,ulong,wchar_t const *,...)
0x1800140e8  lea     rcx, [rsp+38h+Frequency]; lpFrequency
0x1800140ed  call    cs:__imp_QueryPerformanceFrequency
0x1800140f3  cmp     dword ptr [rsp+38h+Frequency], 0
0x1800140f8  jnz     short loc_180014106
0x1800140fa  cmp     dword ptr [rsp+38h+Frequency+4], 0
0x1800140ff  jnz     short loc_180014106
0x180014101  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180014106  lea     r8, [rbx+2478h]
0x18001410d  mov     rdx, rsi
0x180014110  lea     r9, [rsp+38h+Frequency]
0x180014115  mov     rcx, rdi
0x180014118  call    cs:__imp_WerpTraceImageCacheStatistics
0x18001411e  lea     r9, asc_180051790; "\r\n\r\n"
0x180014125  mov     r8d, 0C0000002h; unsigned int
0x18001412b  mov     rdx, rsi; void *
0x18001412e  mov     rcx, rdi; void (*)(void *, unsigned int, const wchar_t *, char *)
0x180014131  call    ?CallWerpLogger@CCrashReport@@CAXP6AXPEAXKPEB_WPEAD@Z0K1ZZ; CCrashReport::CallWerpLogger(void (*)(void *,ulong,wchar_t const *,char *),void *,ulong,wchar_t const *,...)
0x180014136  lea     rcx, [rbx+2478h]
0x18001413d  mov     qword ptr [rbx+13F0h], 0
0x180014148  call    cs:__imp_?WerpResetTransientImageCacheStatistics@@YAXPEAUWERP_IMAGE_CACHE@@@Z; WerpResetTransientImageCacheStatistics(WERP_IMAGE_CACHE *)
0x18001414e  mov     rbx, [rsp+38h+arg_8]
0x180014153  mov     eax, 1
0x180014158  mov     rsi, [rsp+38h+arg_10]
0x18001415d  add     rsp, 30h
0x180014161  pop     rdi
0x180014162  retn
```
