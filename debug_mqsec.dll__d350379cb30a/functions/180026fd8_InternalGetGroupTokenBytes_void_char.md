# InternalGetGroupTokenBytes(void *,char * *)

- ea: `0x180026fd8`
- end: `0x1800271b1`
- name: `?InternalGetGroupTokenBytes@@YAXPEAXPEAPEAD@Z`
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
- `0x180026fd8`

## import_xrefs

- `msvcrt!free` at `0x180027197`
- `msvcrt!free` at `0x180027197`
- `ADVAPI32!GetTokenInformation` at `0x18002700c`
- `ADVAPI32!GetTokenInformation` at `0x1800270e3`
- `ADVAPI32!GetTokenInformation` at `0x18002700c`
- `ADVAPI32!GetTokenInformation` at `0x1800270e3`
- `KERNEL32!GetLastError` at `0x180027012`
- `KERNEL32!GetLastError` at `0x1800270f1`
- `KERNEL32!GetLastError` at `0x180027012`
- `KERNEL32!GetLastError` at `0x1800270f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall InternalGetGroupTokenBytes(HANDLE TokenHandle, char **a2)
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
  GetTokenInformation(TokenHandle, TokenPrimaryGroup, 0, 0, &TokenInformationLength);
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError != 122 )
  {
    if ( LastError )
    {
      v13 = 300;
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
  if ( !GetTokenInformation(TokenHandle, TokenPrimaryGroup, v7, TokenInformationLength, &TokenInformationLength) )
  {
    v8 = GetLastError();
    if ( v8 )
    {
      v13 = 301;
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
0x180026fd8  mov     [rsp-8+arg_0], rbx
0x180026fdd  push    rbp
0x180026fde  push    rsi
0x180026fdf  push    rdi
0x180026fe0  lea     rbp, [rsp-47h]
0x180026fe5  sub     rsp, 90h
0x180026fec  mov     rdi, rdx
0x180026fef  mov     rsi, rcx
0x180026ff2  mov     [rbp+57h+TokenInformationLength], 0
0x180026ff9  lea     rax, [rbp+57h+TokenInformationLength]
0x180026ffd  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x180027002  xor     r9d, r9d; TokenInformationLength
0x180027005  xor     r8d, r8d; TokenInformation
0x180027008  lea     edx, [r9+5]; TokenInformationClass
0x18002700c  call    cs:__imp_GetTokenInformation
0x180027012  call    cs:__imp_GetLastError
0x180027018  mov     ebx, eax
0x18002701a  cmp     eax, 7Ah ; 'z'
0x18002701d  jz      loc_1800270BC
0x180027023  test    eax, eax
0x180027025  jz      short loc_1800270A0
0x180027027  mov     eax, 12Ch
0x18002702c  mov     [rbp+57h+arg_10], ax
0x180027030  mov     [rbp+57h+var_40], ebx
0x180027033  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18002703b  jz      short loc_1800270A0
0x18002703d  lea     rdi, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x180027044  mov     rcx, rdi; wchar_t *
0x180027047  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18002704c  lea     r9d, [rax+1]
0x180027050  add     r9, r9
0x180027053  mov     [rsp+0A0h+var_50], 0
0x18002705c  mov     [rsp+0A0h+var_58], 0
0x180027065  lea     rax, [rbp+57h+var_40]
0x180027069  mov     [rsp+0A0h+var_60], rax
0x18002706e  mov     [rsp+0A0h+var_68], 4
0x180027077  lea     rax, [rbp+57h+arg_10]
0x18002707b  mov     [rsp+0A0h+var_70], rax
0x180027080  mov     r8d, 2
0x180027086  mov     [rsp+0A0h+var_78], r8
0x18002708b  mov     [rsp+0A0h+ReturnLength], rdi
0x180027090  lea     edx, [r8-1]
0x180027094  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18002709b  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x1800270a0  mov     edx, ebx; unsigned int
0x1800270a2  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800270a6  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x1800270ab  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x1800270b2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800270b6  call    _CxxThrowException_0
0x1800270bc  mov     ecx, [rbp+57h+TokenInformationLength]; unsigned __int64
0x1800270bf  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800270c4  mov     rbx, rax
0x1800270c7  mov     [rbp+57h+var_38], rax
0x1800270cb  lea     rax, [rbp+57h+TokenInformationLength]
0x1800270cf  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x1800270d4  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x1800270d8  mov     r8, rbx; TokenInformation
0x1800270db  mov     edx, 5; TokenInformationClass
0x1800270e0  mov     rcx, rsi; TokenHandle
0x1800270e3  call    cs:__imp_GetTokenInformation
0x1800270e9  test    eax, eax
0x1800270eb  jnz     loc_180027192
0x1800270f1  call    cs:__imp_GetLastError
0x1800270f7  mov     ebx, eax
0x1800270f9  test    eax, eax
0x1800270fb  jz      short loc_180027176
0x1800270fd  mov     eax, 12Dh
0x180027102  mov     [rbp+57h+arg_10], ax
0x180027106  mov     [rbp+57h+var_40], ebx
0x180027109  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180027111  jz      short loc_180027176
0x180027113  lea     rdi, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x18002711a  mov     rcx, rdi; wchar_t *
0x18002711d  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180027122  lea     r9d, [rax+1]
0x180027126  add     r9, r9
0x180027129  mov     [rsp+0A0h+var_50], 0
0x180027132  mov     [rsp+0A0h+var_58], 0
0x18002713b  lea     rax, [rbp+57h+var_40]
0x18002713f  mov     [rsp+0A0h+var_60], rax
0x180027144  mov     [rsp+0A0h+var_68], 4
0x18002714d  lea     rax, [rbp+57h+arg_10]
0x180027151  mov     [rsp+0A0h+var_70], rax
0x180027156  mov     r8d, 2
0x18002715c  mov     [rsp+0A0h+var_78], r8
0x180027161  mov     [rsp+0A0h+ReturnLength], rdi
0x180027166  lea     edx, [r8-1]
0x18002716a  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180027171  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180027176  mov     edx, ebx; unsigned int
0x180027178  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002717c  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180027181  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x180027188  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002718c  call    _CxxThrowException_0
0x180027192  mov     [rdi], rbx
0x180027195  xor     ecx, ecx; Block
0x180027197  call    cs:__imp_free
0x18002719d  nop
0x18002719e  mov     rbx, [rsp+0A0h+arg_0]
0x1800271a6  add     rsp, 90h
0x1800271ad  pop     rdi
0x1800271ae  pop     rsi
0x1800271af  pop     rbp
0x1800271b0  retn
```
