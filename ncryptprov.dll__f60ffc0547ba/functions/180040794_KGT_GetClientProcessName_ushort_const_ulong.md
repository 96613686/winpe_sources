# KGT_GetClientProcessName(ushort const *,ulong)

- ea: `0x180040794`
- end: `0x180040950`
- name: `?KGT_GetClientProcessName@@YAPEAGPEBGK@Z`
- size: `444`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180040e24`

## callees

- `0x18000af80`
- `0x180039928`
- `0x180040794`
- `0x180040958`
- `0x180062310`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180040861`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180040861`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800407ef`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800407ef`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800408ea`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800408ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004083a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004083a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800408b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040914`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800408b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040914`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040826`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040826`

## string_xrefs

- `0x18004080e`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\telemetry-utils.cpp`
- `0x1800408fc`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\telemetry-utils.cpp`

## pseudocode

```c
unsigned __int16 *__fastcall KGT_GetClientProcessName(const unsigned __int16 *a1, unsigned int a2)
{
  __int64 v3; // rbx
  DWORD LastError; // eax
  __int64 v5; // r9
  const char *v6; // rdx
  wchar_t *v7; // rdi
  __int64 SvchostServiceName; // rax
  void *v9; // rsi
  int v10; // ebx
  unsigned int *v11; // rax
  wchar_t Filename[256]; // [rsp+50h] [rbp-418h] BYREF
  wchar_t Ext[256]; // [rsp+250h] [rbp-218h] BYREF

  v3 = 0;
  LastError = _wsplitpath_s(a1, 0, 0, 0, 0, Filename, 0x100u, Ext, 0x100u);
  if ( LastError )
  {
    v5 = 233;
    v6 = "err";
LABEL_3:
    DebugTraceError(LastError, v6, "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\telemetry-utils.cpp", v5);
    return (unsigned __int16 *)v3;
  }
  v7 = (wchar_t *)LocalAlloc(0, 0x20Au);
  if ( !v7 )
  {
    LastError = GetLastError();
    v5 = 243;
    v6 = "GetLastError()";
    goto LABEL_3;
  }
  if ( !(unsigned int)_o__wcsicmp(Filename, L"svchost") )
  {
    SvchostServiceName = KGT_GetSvchostServiceName(a2);
    v9 = (void *)SvchostServiceName;
    if ( SvchostServiceName )
    {
      v10 = swprintf_s(v7, 0x105u, L"%s%s[%s]", Filename, Ext, SvchostServiceName);
      LocalFree(v9);
      if ( v10 > 0 )
        return v7;
    }
  }
  if ( swprintf_s(v7, 0x105u, L"%s%s", Filename, Ext) > 0 )
    return v7;
  v11 = (unsigned int *)_o__errno();
  DebugTraceError(*v11, "errno", "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\telemetry-utils.cpp", 268);
  LocalFree(v7);
  return 0;
}

```

## disassembly

```asm
0x180040794  mov     [rsp+arg_10], rbx
0x180040799  mov     [rsp+arg_18], rsi
0x18004079e  push    rdi
0x18004079f  sub     rsp, 460h
0x1800407a6  mov     rax, cs:__security_cookie
0x1800407ad  xor     rax, rsp
0x1800407b0  mov     [rsp+468h+var_18], rax
0x1800407b8  mov     esi, edx
0x1800407ba  lea     rax, [rsp+468h+var_218]
0x1800407c2  mov     edx, 100h
0x1800407c7  xor     ebx, ebx
0x1800407c9  mov     [rsp+468h+ExtCount], rdx; ExtCount
0x1800407ce  xor     r9d, r9d; Dir
0x1800407d1  mov     [rsp+468h+Ext], rax; Ext
0x1800407d6  xor     r8d, r8d; DriveCount
0x1800407d9  mov     [rsp+468h+FilenameCount], rdx; FilenameCount
0x1800407de  lea     rax, [rsp+468h+var_418]
0x1800407e3  mov     [rsp+468h+Filename], rax; Filename
0x1800407e8  xor     edx, edx; Drive
0x1800407ea  mov     [rsp+468h+DirCount], rbx; DirCount
0x1800407ef  call    cs:__imp__wsplitpath_s
0x1800407f6  nop     dword ptr [rax+rax+00h]
0x1800407fb  test    eax, eax
0x1800407fd  jz      short loc_18004081F
0x1800407ff  mov     r9d, 0E9h
0x180040805  lea     rdx, aErr; "err"
0x18004080c  mov     ecx, eax
0x18004080e  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180040815  call    DebugTraceError
0x18004081a  jmp     loc_180040927
0x18004081f  mov     edx, 20Ah; uBytes
0x180040824  xor     ecx, ecx; uFlags
0x180040826  call    cs:__imp_LocalAlloc
0x18004082d  nop     dword ptr [rax+rax+00h]
0x180040832  mov     rdi, rax
0x180040835  test    rax, rax
0x180040838  jnz     short loc_180040855
0x18004083a  call    cs:__imp_GetLastError
0x180040841  nop     dword ptr [rax+rax+00h]
0x180040846  mov     r9d, 0F3h
0x18004084c  lea     rdx, aGetlasterror; "GetLastError()"
0x180040853  jmp     short loc_18004080C
0x180040855  lea     rdx, aSvchost; "svchost"
0x18004085c  lea     rcx, [rsp+468h+var_418]
0x180040861  call    cs:__imp__o__wcsicmp
0x180040868  nop     dword ptr [rax+rax+00h]
0x18004086d  test    eax, eax
0x18004086f  jnz     short loc_1800408C0
0x180040871  mov     ecx, esi
0x180040873  call    KGT_GetSvchostServiceName
0x180040878  mov     rsi, rax
0x18004087b  test    rax, rax
0x18004087e  jz      short loc_1800408C0
0x180040880  mov     [rsp+468h+Filename], rax
0x180040885  lea     r9, [rsp+468h+var_418]
0x18004088a  lea     rax, [rsp+468h+var_218]
0x180040892  mov     edx, 105h; BufferCount
0x180040897  lea     r8, aSSS; "%s%s[%s]"
0x18004089e  mov     [rsp+468h+DirCount], rax
0x1800408a3  mov     rcx, rdi; Buffer
0x1800408a6  call    swprintf_s
0x1800408ab  mov     rcx, rsi; hMem
0x1800408ae  mov     ebx, eax
0x1800408b0  call    cs:__imp_LocalFree
0x1800408b7  nop     dword ptr [rax+rax+00h]
0x1800408bc  test    ebx, ebx
0x1800408be  jg      short loc_180040924
0x1800408c0  lea     rax, [rsp+468h+var_218]
0x1800408c8  mov     edx, 105h; BufferCount
0x1800408cd  lea     r9, [rsp+468h+var_418]
0x1800408d2  mov     [rsp+468h+DirCount], rax
0x1800408d7  lea     r8, aSS_0; "%s%s"
0x1800408de  mov     rcx, rdi; Buffer
0x1800408e1  call    swprintf_s
0x1800408e6  test    eax, eax
0x1800408e8  jg      short loc_180040924
0x1800408ea  call    cs:__imp__o__errno
0x1800408f1  nop     dword ptr [rax+rax+00h]
0x1800408f6  mov     r9d, 10Ch
0x1800408fc  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180040903  lea     rdx, aErrno; "errno"
0x18004090a  mov     ecx, [rax]
0x18004090c  call    DebugTraceError
0x180040911  mov     rcx, rdi; hMem
0x180040914  call    cs:__imp_LocalFree
0x18004091b  nop     dword ptr [rax+rax+00h]
0x180040920  xor     ebx, ebx
0x180040922  jmp     short loc_180040927
0x180040924  mov     rbx, rdi
0x180040927  mov     rax, rbx
0x18004092a  mov     rcx, [rsp+468h+var_18]
0x180040932  xor     rcx, rsp; StackCookie
0x180040935  call    __security_check_cookie
0x18004093a  lea     r11, [rsp+468h+var_8]
0x180040942  mov     rbx, [r11+20h]
0x180040946  mov     rsi, [r11+28h]
0x18004094a  mov     rsp, r11
0x18004094d  pop     rdi
0x18004094e  retn
```
