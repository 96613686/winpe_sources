# MQSec_SetPrivilegeInThread(wchar_t const *,int,int *)

- ea: `0x180029990`
- end: `0x180029b47`
- name: `?MQSec_SetPrivilegeInThread@@YAJPEB_WHPEAH@Z`
- size: `439`
- prototype: `__int64 __fastcall(const wchar_t *, int, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180004074`
- `0x1800049ac`
- `0x180017430`
- `0x180029990`
- `0x180029fb8`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x1800299cf`
- `ADVAPI32!OpenThreadToken` at `0x1800299cf`
- `ADVAPI32!OpenProcessToken` at `0x1800299fe`
- `ADVAPI32!OpenProcessToken` at `0x1800299fe`
- `KERNEL32!CloseHandle` at `0x180029a93`
- `KERNEL32!CloseHandle` at `0x180029a93`
- `KERNEL32!GetCurrentThread` at `0x1800299b8`
- `KERNEL32!GetCurrentThread` at `0x1800299b8`
- `KERNEL32!GetCurrentProcess` at `0x1800299ed`
- `KERNEL32!GetCurrentProcess` at `0x1800299ed`
- `KERNEL32!GetLastError` at `0x1800299dd`
- `KERNEL32!GetLastError` at `0x180029a24`
- `KERNEL32!GetLastError` at `0x1800299dd`
- `KERNEL32!GetLastError` at `0x180029a24`

## pseudocode

```c
__int64 __fastcall MQSec_SetPrivilegeInThread(const wchar_t *a1, int a2, int *a3)
{
  int v6; // ebx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  __int64 v9; // r9
  HANDLE CurrentProcess; // rax
  DWORD v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  int v15; // ebx
  unsigned int v16; // eax
  void *TokenHandle[5]; // [rsp+60h] [rbp-28h] BYREF
  __int16 v18; // [rsp+A0h] [rbp+18h] BYREF
  int v19; // [rsp+A8h] [rbp+20h] BYREF

  TokenHandle[0] = 0;
  v6 = a3 != 0 ? 8 : 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, v6 + 32, 1, TokenHandle) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError != 1008 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) == 0 )
        return 3222146079LL;
      v13 = 13;
      goto LABEL_10;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, v6 + 32, TokenHandle) )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) == 0 )
        return 3222146079LL;
      v11 = GetLastError();
      v12 = WPP_GLOBAL_Control;
      v13 = 12;
      v9 = v11;
LABEL_10:
      WPP_SF_d(v12[32], v13, &WPP_6595c8b0bcaf330ab6208b6e35db9f13_Traceguids, v9);
      return 3222146079LL;
    }
  }
  v15 = SetSpecificPrivilegeInAccessToken(TokenHandle[0], a1, a2, a3);
  CloseHandle(TokenHandle[0]);
  TokenHandle[0] = 0;
  if ( v15 < 0 )
  {
    v18 = 40;
    v19 = v15;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v16 = mqwcslen(L"acssctrl/privilge");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v16 + 1),
        L"acssctrl/privilge",
        2,
        &v18,
        4,
        &v19,
        0,
        0);
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180029990  mov     [rsp+arg_0], rbx
0x180029995  push    rbp
0x180029996  push    rsi
0x180029997  push    rdi
0x180029998  sub     rsp, 70h
0x18002999c  mov     rax, r8
0x18002999f  mov     [rsp+88h+TokenHandle], 0
0x1800299a8  neg     rax
0x1800299ab  mov     rdi, r8
0x1800299ae  mov     esi, edx
0x1800299b0  mov     rbp, rcx
0x1800299b3  sbb     ebx, ebx
0x1800299b5  and     ebx, 8
0x1800299b8  call    cs:__imp_GetCurrentThread
0x1800299be  lea     r9, [rsp+88h+TokenHandle]; TokenHandle
0x1800299c3  mov     r8d, 1; OpenAsSelf
0x1800299c9  mov     rcx, rax; ThreadHandle
0x1800299cc  lea     edx, [rbx+20h]; DesiredAccess
0x1800299cf  call    cs:__imp_OpenThreadToken
0x1800299d5  test    eax, eax
0x1800299d7  jnz     loc_180029A79
0x1800299dd  call    cs:__imp_GetLastError
0x1800299e3  mov     r9d, eax
0x1800299e6  cmp     eax, 3F0h
0x1800299eb  jnz     short loc_180029A3B
0x1800299ed  call    cs:__imp_GetCurrentProcess
0x1800299f3  mov     rcx, rax; ProcessHandle
0x1800299f6  lea     r8, [rsp+88h+TokenHandle]; TokenHandle
0x1800299fb  lea     edx, [rbx+20h]; DesiredAccess
0x1800299fe  call    cs:__imp_OpenProcessToken
0x180029a04  test    eax, eax
0x180029a06  jnz     short loc_180029A79
0x180029a08  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a0f  lea     rax, WPP_GLOBAL_Control
0x180029a16  cmp     rcx, rax
0x180029a19  jz      short loc_180029A6F
0x180029a1b  test    byte ptr [rcx+10Ch], 1
0x180029a22  jz      short loc_180029A6F
0x180029a24  call    cs:__imp_GetLastError
0x180029a2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a31  mov     edx, 0Ch
0x180029a36  mov     r9d, eax
0x180029a39  jmp     short loc_180029A5C
0x180029a3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a42  lea     rax, WPP_GLOBAL_Control
0x180029a49  cmp     rcx, rax
0x180029a4c  jz      short loc_180029A6F
0x180029a4e  test    byte ptr [rcx+10Ch], 1
0x180029a55  jz      short loc_180029A6F
0x180029a57  mov     edx, 0Dh
0x180029a5c  mov     rcx, [rcx+100h]
0x180029a63  lea     r8, WPP_6595c8b0bcaf330ab6208b6e35db9f13_Traceguids
0x180029a6a  call    WPP_SF_d
0x180029a6f  mov     eax, 0C00E0C1Fh
0x180029a74  jmp     loc_180029B37
0x180029a79  mov     rcx, [rsp+88h+TokenHandle]; TokenHandle
0x180029a7e  mov     r9, rdi; int *
0x180029a81  mov     r8d, esi; int
0x180029a84  mov     rdx, rbp; wchar_t *
0x180029a87  call    ?SetSpecificPrivilegeInAccessToken@@YAJPEAXPEB_WHPEAH@Z; SetSpecificPrivilegeInAccessToken(void *,wchar_t const *,int,int *)
0x180029a8c  mov     rcx, [rsp+88h+TokenHandle]; hObject
0x180029a91  mov     ebx, eax
0x180029a93  call    cs:__imp_CloseHandle
0x180029a99  mov     [rsp+88h+TokenHandle], 0
0x180029aa2  test    ebx, ebx
0x180029aa4  jns     loc_180029B35
0x180029aaa  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180029ab2  mov     eax, 28h ; '('
0x180029ab7  mov     [rsp+88h+arg_10], ax
0x180029abf  mov     [rsp+88h+arg_18], ebx
0x180029ac6  jz      short loc_180029B35
0x180029ac8  lea     rdi, aAcssctrlPrivil; "acssctrl/privilge"
0x180029acf  mov     rcx, rdi; wchar_t *
0x180029ad2  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180029ad7  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180029ade  mov     edx, 1
0x180029ae3  mov     [rsp+88h+var_38], 0
0x180029aec  mov     r8d, edx
0x180029aef  mov     [rsp+88h+var_40], 0
0x180029af8  lea     r9d, [rax+1]
0x180029afc  lea     rax, [rsp+88h+arg_18]
0x180029b04  add     r9, r9
0x180029b07  mov     [rsp+88h+var_48], rax
0x180029b0c  lea     rax, [rsp+88h+arg_10]
0x180029b14  mov     [rsp+88h+var_50], 4
0x180029b1d  mov     [rsp+88h+var_58], rax
0x180029b22  mov     [rsp+88h+var_60], 2
0x180029b2b  mov     [rsp+88h+var_68], rdi
0x180029b30  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180029b35  mov     eax, ebx
0x180029b37  mov     rbx, [rsp+88h+arg_0]
0x180029b3f  add     rsp, 70h
0x180029b43  pop     rdi
0x180029b44  pop     rsi
0x180029b45  pop     rbp
0x180029b46  retn
```
