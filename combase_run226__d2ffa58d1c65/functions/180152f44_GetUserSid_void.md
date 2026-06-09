# GetUserSid(void *)

- ea: `0x180152f44`
- end: `0x180153176`
- name: `?GetUserSid@@YAPEAXPEAX@Z`
- size: `562`
- prototype: `void *__fastcall(void *hUserToken)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180165ef0`
- `0x1801dcf2c`

## callees

- `0x180087660`
- `0x18008db2c`
- `0x180152f44`
- `0x1801999b0`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1801530a3`
- `ntdll!RtlLengthSid` at `0x1801530a3`
- `ntdll!NtQueryInformationToken` at `0x180152f86`
- `ntdll!NtQueryInformationToken` at `0x18015302d`
- `ntdll!NtQueryInformationToken` at `0x180152f86`
- `ntdll!NtQueryInformationToken` at `0x18015302d`
- `ntdll!RtlCopySid` at `0x1801530d9`
- `ntdll!RtlCopySid` at `0x1801530d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180152fff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801530ba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180152fff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801530ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18015308c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801530f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18015314f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18015308c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801530f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18015314f`

## string_xrefs

- `0x180152fda`: `onecore\com\combase\catalog\services.cxx`
- `0x18015306e`: `onecore\com\combase\catalog\services.cxx`
- `0x180153137`: `onecore\com\combase\catalog\services.cxx`
- `0x180152fcb`: `GetUserSid`
- `0x18015305f`: `GetUserSid`
- `0x180153130`: `GetUserSid`

## pseudocode

```c
void *__fastcall GetUserSid(void *hUserToken)
{
  NTSTATUS InformationToken; // eax
  HRESULT v3; // edx
  PSID *v4; // rbx
  int v5; // esi
  NTSTATUS v6; // edx
  void *v8; // rax
  void *v9; // rdi
  NTSTATUS v10; // ebp
  unsigned int dwBytesRequired[4]; // [rsp+30h] [rbp-B8h] BYREF
  unsigned __int8 achBuffer[100]; // [rsp+40h] [rbp-A8h] BYREF

  dwBytesRequired[0] = 0;
  InformationToken = NtQueryInformationToken(hUserToken, TokenUser, achBuffer, 0x64u, dwBytesRequired);
  v3 = InformationToken;
  if ( InformationToken >= 0 )
  {
    v5 = 0;
    v4 = (PSID *)achBuffer;
  }
  else
  {
    if ( InformationToken != -1073741789 )
    {
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        ComTraceMessageT<long>(
          "onecore\\com\\combase\\catalog\\services.cxx",
          "GetUserSid",
          1809,
          ERRORS,
          L"%!STATUS!",
          v3);
      return 0;
    }
    v4 = (PSID *)HeapAlloc(g_hHeap, 0, dwBytesRequired[0]);
    if ( !v4 )
      return 0;
    v5 = 1;
    v6 = NtQueryInformationToken(hUserToken, TokenUser, v4, dwBytesRequired[0], dwBytesRequired);
    if ( v6 < 0 )
    {
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        ComTraceMessageT<long>(
          "onecore\\com\\combase\\catalog\\services.cxx",
          "GetUserSid",
          1842,
          ERRORS,
          L"%!STATUS!",
          v6);
LABEL_13:
      HeapFree(g_hHeap, 0, v4);
      return 0;
    }
  }
  dwBytesRequired[0] = RtlLengthSid(*v4);
  v8 = HeapAlloc(g_hHeap, 0, dwBytesRequired[0]);
  v9 = v8;
  if ( !v8 )
  {
    if ( v5 != 1 )
      return 0;
    goto LABEL_13;
  }
  v10 = RtlCopySid(dwBytesRequired[0], v8, *v4);
  if ( v5 == 1 )
    HeapFree(g_hHeap, 0, v4);
  if ( v10 < 0 )
  {
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      ComTraceMessageT<long>(
        "onecore\\com\\combase\\catalog\\services.cxx",
        "GetUserSid",
        1876,
        ERRORS,
        L"%!STATUS!",
        v10);
    HeapFree(g_hHeap, 0, v9);
    return 0;
  }
  return v9;
}

```

## disassembly

```asm
0x180152f44  push    rbx
0x180152f46  push    rbp
0x180152f47  push    rsi
0x180152f48  push    rdi
0x180152f49  sub     rsp, 0C8h
0x180152f50  mov     rax, cs:__security_cookie
0x180152f57  xor     rax, rsp
0x180152f5a  mov     [rsp+0E8h+var_38], rax
0x180152f62  mov     r9d, 64h ; 'd'; TokenInformationLength
0x180152f68  mov     [rsp+0E8h+dwBytesRequired], 0
0x180152f70  lea     rax, [rsp+0E8h+dwBytesRequired]
0x180152f75  mov     rdi, hUserToken
0x180152f78  lea     r8, [rsp+0E8h+achBuffer]; TokenInformation
0x180152f7d  mov     [rsp+0E8h+ReturnLength], rax; ReturnLength
0x180152f82  lea     edx, [r9-63h]; TokenInformationClass
0x180152f86  call    cs:__imp_NtQueryInformationToken
0x180152f8c  mov     edx, eax
0x180152f8e  test    eax, eax
0x180152f90  jns     loc_180153099
0x180152f96  cmp     eax, 0C0000023h
0x180152f9b  jz      short loc_180152FF1
0x180152f9d  mov     ecx, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1; level
0x180152fa3  test    ecx, ecx
0x180152fa5  jnz     short loc_180152FC0
0x180152fa7  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x180152fad  jz      loc_180153092
0x180152fb3  call    IsWppLevelEnabled
0x180152fb8  test    al, al
0x180152fba  jz      loc_180153092
0x180152fc0  mov     [rsp+0E8h+var_C0], edx; <args_0>
0x180152fc4  lea     rax, aStatus; "%!STATUS!"
0x180152fcb  lea     rdx, aGetusersid; "GetUserSid"
0x180152fd2  mov     [rsp+0E8h+ReturnLength], rax; format
0x180152fd7  xor     r9d, r9d; level
0x180152fda  lea     hUserToken, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x180152fe1  mov     r8d, 711h; line
0x180152fe7  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180152fec  jmp     loc_180153092
0x180152ff1  mov     r8d, [rsp+0E8h+dwBytesRequired]; dwBytes
0x180152ff6  xor     edx, edx; dwFlags
0x180152ff8  mov     hUserToken, cs:?g_hHeap@@3QEAXEA; hHeap
0x180152fff  call    cs:__imp_HeapAlloc
0x180153005  mov     rbx, rax
0x180153008  test    rax, rax
0x18015300b  jz      loc_180153092
0x180153011  mov     r9d, [rsp+0E8h+dwBytesRequired]; TokenInformationLength
0x180153016  lea     rax, [rsp+0E8h+dwBytesRequired]
0x18015301b  mov     esi, 1
0x180153020  mov     [rsp+0E8h+ReturnLength], rax; ReturnLength
0x180153025  mov     edx, esi; TokenInformationClass
0x180153027  mov     r8, rbx; TokenInformation
0x18015302a  mov     hUserToken, rdi; TokenHandle
0x18015302d  call    cs:__imp_NtQueryInformationToken
0x180153033  mov     edx, eax
0x180153035  test    eax, eax
0x180153037  jns     short loc_1801530A0
0x180153039  mov     ecx, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1; level
0x18015303f  test    ecx, ecx
0x180153041  jnz     short loc_180153054
0x180153043  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x180153049  jz      short loc_180153080
0x18015304b  call    IsWppLevelEnabled
0x180153050  test    al, al
0x180153052  jz      short loc_180153080
0x180153054  mov     [rsp+0E8h+var_C0], edx; <args_0>
0x180153058  lea     rax, aStatus; "%!STATUS!"
0x18015305f  lea     rdx, aGetusersid; "GetUserSid"
0x180153066  mov     [rsp+0E8h+ReturnLength], rax; format
0x18015306b  xor     r9d, r9d; level
0x18015306e  lea     hUserToken, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x180153075  mov     r8d, 732h; line
0x18015307b  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180153080  mov     hUserToken, cs:?g_hHeap@@3QEAXEA; hHeap
0x180153087  mov     r8, rbx; lpMem
0x18015308a  xor     edx, edx; dwFlags
0x18015308c  call    cs:__imp_HeapFree
0x180153092  xor     eax, eax
0x180153094  jmp     loc_18015315A
0x180153099  xor     esi, esi
0x18015309b  lea     rbx, [rsp+0E8h+achBuffer]
0x1801530a0  mov     hUserToken, [rbx]; Sid
0x1801530a3  call    cs:__imp_RtlLengthSid
0x1801530a9  mov     hUserToken, cs:?g_hHeap@@3QEAXEA; hHeap
0x1801530b0  xor     edx, edx; dwFlags
0x1801530b2  mov     r8d, eax; dwBytes
0x1801530b5  mov     [rsp+0E8h+dwBytesRequired], r8d
0x1801530ba  call    cs:__imp_HeapAlloc
0x1801530c0  mov     rdi, rax
0x1801530c3  test    rax, rax
0x1801530c6  jnz     short loc_1801530CF
0x1801530c8  cmp     esi, 1
0x1801530cb  jnz     short loc_180153092
0x1801530cd  jmp     short loc_180153080
0x1801530cf  mov     r8, [rbx]; SourceSid
0x1801530d2  mov     rdx, rdi; DestinationSid
0x1801530d5  mov     ecx, [rsp+0E8h+dwBytesRequired]; DestinationSidLength
0x1801530d9  call    cs:__imp_RtlCopySid
0x1801530df  mov     ebp, eax
0x1801530e1  cmp     esi, 1
0x1801530e4  jnz     short loc_1801530F8
0x1801530e6  mov     hUserToken, cs:?g_hHeap@@3QEAXEA; hHeap
0x1801530ed  mov     r8, rbx; lpMem
0x1801530f0  xor     edx, edx; dwFlags
0x1801530f2  call    cs:__imp_HeapFree
0x1801530f8  test    ebp, ebp
0x1801530fa  jns     short loc_180153157
0x1801530fc  mov     ecx, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1; level
0x180153102  test    ecx, ecx
0x180153104  jnz     short loc_180153117
0x180153106  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x18015310c  jz      short loc_180153143
0x18015310e  call    IsWppLevelEnabled
0x180153113  test    al, al
0x180153115  jz      short loc_180153143
0x180153117  lea     rax, aStatus; "%!STATUS!"
0x18015311e  mov     [rsp+0E8h+var_C0], ebp; <args_0>
0x180153122  xor     r9d, r9d; level
0x180153125  mov     [rsp+0E8h+ReturnLength], rax; format
0x18015312a  mov     r8d, 754h; line
0x180153130  lea     rdx, aGetusersid; "GetUserSid"
0x180153137  lea     hUserToken, aOnecoreComComb_115; "onecore\\com\\combase\\catalog\\service"...
0x18015313e  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180153143  mov     hUserToken, cs:?g_hHeap@@3QEAXEA; hHeap
0x18015314a  mov     r8, rdi; lpMem
0x18015314d  xor     edx, edx; dwFlags
0x18015314f  call    cs:__imp_HeapFree
0x180153155  xor     edi, edi
0x180153157  mov     rax, rdi
0x18015315a  mov     hUserToken, [rsp+0E8h+var_38]
0x180153162  xor     hUserToken, rsp; StackCookie
0x180153165  call    __security_check_cookie
0x18015316a  add     rsp, 0C8h
0x180153171  pop     rdi
0x180153172  pop     rsi
0x180153173  pop     rbp
0x180153174  pop     rbx
0x180153175  retn
```
