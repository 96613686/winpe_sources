# InternalGetUserTokenBytes(void *,char * *)

- ea: `0x1800271b8`
- end: `0x180027391`
- name: `?InternalGetUserTokenBytes@@YAXPEAXPEAPEAD@Z`
- size: `473`
- prototype: `void __fastcall(HANDLE TokenHandle, char **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180025eac`

## callees

- `0x180003426`
- `0x180004074`
- `0x18000ca5c`
- `0x18001722c`
- `0x180017430`
- `0x1800271b8`

## import_xrefs

- `msvcrt!free` at `0x180027377`
- `msvcrt!free` at `0x180027377`
- `ADVAPI32!GetTokenInformation` at `0x1800271ec`
- `ADVAPI32!GetTokenInformation` at `0x1800272c3`
- `ADVAPI32!GetTokenInformation` at `0x1800271ec`
- `ADVAPI32!GetTokenInformation` at `0x1800272c3`
- `KERNEL32!GetLastError` at `0x1800271f2`
- `KERNEL32!GetLastError` at `0x1800272d1`
- `KERNEL32!GetLastError` at `0x1800271f2`
- `KERNEL32!GetLastError` at `0x1800272d1`

## pseudocode

```c
void __fastcall InternalGetUserTokenBytes(HANDLE TokenHandle, char **a2)
{
  DWORD LastError; // eax
  unsigned int v5; // ebx
  unsigned int v6; // eax
  void *v7; // rbx
  DWORD v8; // ebx
  unsigned int v9; // eax
  DWORD v10; // [rsp+60h] [rbp+17h] BYREF
  void *v11; // [rsp+68h] [rbp+1Fh]
  _BYTE pExceptionObject[48]; // [rsp+70h] [rbp+27h] BYREF
  __int16 v13; // [rsp+C0h] [rbp+77h] BYREF
  DWORD TokenInformationLength; // [rsp+C8h] [rbp+7Fh] BYREF

  TokenInformationLength = 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError != 122 )
  {
    if ( LastError )
    {
      v13 = 200;
      v10 = LastError;
      if ( g_pMSMQErrorLoggingTrace )
      {
        v6 = mqwcslen(L"acssctrl/secdscrp");
        CMSMQTrace::MSMQTraceEvent(
          g_pMSMQErrorLoggingTrace,
          1,
          2,
          2LL * (v6 + 1),
          L"acssctrl/secdscrp",
          2,
          &v13,
          4,
          &v10,
          0,
          0);
      }
    }
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v5);
    throw (bad_win32_error *)pExceptionObject;
  }
  v7 = MmAllocate(TokenInformationLength);
  v11 = v7;
  if ( !GetTokenInformation(TokenHandle, TokenUser, v7, TokenInformationLength, &TokenInformationLength) )
  {
    v8 = GetLastError();
    if ( v8 )
    {
      v13 = 201;
      v10 = v8;
      if ( g_pMSMQErrorLoggingTrace )
      {
        v9 = mqwcslen(L"acssctrl/secdscrp");
        CMSMQTrace::MSMQTraceEvent(
          g_pMSMQErrorLoggingTrace,
          1,
          2,
          2LL * (v9 + 1),
          L"acssctrl/secdscrp",
          2,
          &v13,
          4,
          &v10,
          0,
          0);
      }
    }
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v8);
    throw (bad_win32_error *)pExceptionObject;
  }
  *a2 = (char *)v7;
  free(0);
}

```

## disassembly

```asm
0x1800271b8  mov     [rsp-8+arg_0], rbx
0x1800271bd  push    rbp
0x1800271be  push    rsi
0x1800271bf  push    rdi
0x1800271c0  lea     rbp, [rsp-47h]
0x1800271c5  sub     rsp, 90h
0x1800271cc  mov     rdi, rdx
0x1800271cf  mov     rsi, rcx
0x1800271d2  mov     [rbp+57h+TokenInformationLength], 0
0x1800271d9  lea     rax, [rbp+57h+TokenInformationLength]
0x1800271dd  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x1800271e2  xor     r9d, r9d; TokenInformationLength
0x1800271e5  xor     r8d, r8d; TokenInformation
0x1800271e8  lea     edx, [r9+1]; TokenInformationClass
0x1800271ec  call    cs:__imp_GetTokenInformation
0x1800271f2  call    cs:__imp_GetLastError
0x1800271f8  mov     ebx, eax
0x1800271fa  cmp     eax, 7Ah ; 'z'
0x1800271fd  jz      loc_18002729C
0x180027203  test    eax, eax
0x180027205  jz      short loc_180027280
0x180027207  mov     eax, 0C8h
0x18002720c  mov     [rbp+57h+arg_10], ax
0x180027210  mov     [rbp+57h+var_40], ebx
0x180027213  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18002721b  jz      short loc_180027280
0x18002721d  lea     rdi, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x180027224  mov     rcx, rdi; wchar_t *
0x180027227  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18002722c  lea     r9d, [rax+1]
0x180027230  add     r9, r9
0x180027233  mov     [rsp+0A0h+var_50], 0
0x18002723c  mov     [rsp+0A0h+var_58], 0
0x180027245  lea     rax, [rbp+57h+var_40]
0x180027249  mov     [rsp+0A0h+var_60], rax
0x18002724e  mov     [rsp+0A0h+var_68], 4
0x180027257  lea     rax, [rbp+57h+arg_10]
0x18002725b  mov     [rsp+0A0h+var_70], rax
0x180027260  mov     r8d, 2
0x180027266  mov     [rsp+0A0h+var_78], r8
0x18002726b  mov     [rsp+0A0h+ReturnLength], rdi
0x180027270  lea     edx, [r8-1]
0x180027274  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18002727b  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180027280  mov     edx, ebx; unsigned int
0x180027282  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180027286  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18002728b  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x180027292  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180027296  call    _CxxThrowException_0
0x18002729c  mov     ecx, [rbp+57h+TokenInformationLength]; unsigned __int64
0x18002729f  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800272a4  mov     rbx, rax
0x1800272a7  mov     [rbp+57h+var_38], rax
0x1800272ab  lea     rax, [rbp+57h+TokenInformationLength]
0x1800272af  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x1800272b4  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x1800272b8  mov     r8, rbx; TokenInformation
0x1800272bb  mov     edx, 1; TokenInformationClass
0x1800272c0  mov     rcx, rsi; TokenHandle
0x1800272c3  call    cs:__imp_GetTokenInformation
0x1800272c9  test    eax, eax
0x1800272cb  jnz     loc_180027372
0x1800272d1  call    cs:__imp_GetLastError
0x1800272d7  mov     ebx, eax
0x1800272d9  test    eax, eax
0x1800272db  jz      short loc_180027356
0x1800272dd  mov     eax, 0C9h
0x1800272e2  mov     [rbp+57h+arg_10], ax
0x1800272e6  mov     [rbp+57h+var_40], ebx
0x1800272e9  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800272f1  jz      short loc_180027356
0x1800272f3  lea     rdi, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x1800272fa  mov     rcx, rdi; wchar_t *
0x1800272fd  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180027302  lea     r9d, [rax+1]
0x180027306  add     r9, r9
0x180027309  mov     [rsp+0A0h+var_50], 0
0x180027312  mov     [rsp+0A0h+var_58], 0
0x18002731b  lea     rax, [rbp+57h+var_40]
0x18002731f  mov     [rsp+0A0h+var_60], rax
0x180027324  mov     [rsp+0A0h+var_68], 4
0x18002732d  lea     rax, [rbp+57h+arg_10]
0x180027331  mov     [rsp+0A0h+var_70], rax
0x180027336  mov     r8d, 2
0x18002733c  mov     [rsp+0A0h+var_78], r8
0x180027341  mov     [rsp+0A0h+ReturnLength], rdi
0x180027346  lea     edx, [r8-1]
0x18002734a  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180027351  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180027356  mov     edx, ebx; unsigned int
0x180027358  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002735c  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180027361  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x180027368  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002736c  call    _CxxThrowException_0
0x180027372  mov     [rdi], rbx
0x180027375  xor     ecx, ecx; Block
0x180027377  call    cs:__imp_free
0x18002737d  nop
0x18002737e  mov     rbx, [rsp+0A0h+arg_0]
0x180027386  add     rsp, 90h
0x18002738d  pop     rdi
0x18002738e  pop     rsi
0x18002738f  pop     rbp
0x180027390  retn
```
