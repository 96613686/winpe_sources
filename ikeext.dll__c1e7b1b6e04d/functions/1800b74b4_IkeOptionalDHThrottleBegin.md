# IkeOptionalDHThrottleBegin

- ea: `0x1800b74b4`
- end: `0x1800b7674`
- name: `IkeOptionalDHThrottleBegin`
- size: `448`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800b62fc`
- `0x1800b6d4c`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800061ec`
- `0x180008388`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x18005bc40`
- `0x1800b74b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800b75db`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800b75db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b75d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b760a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b75d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b760a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800b7616`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800b7616`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b75ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7620`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b75ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7620`

## string_xrefs

- `0x1800b75f0`: `GetThreadPriority`
- `0x1800b7592`: `Lowering priority of thread due to DH DOS Throttle`
- `0x1800b7626`: `SetThreadPriority`

## pseudocode

```c
__int64 __fastcall IkeOptionalDHThrottleBegin(__int64 a1, _DWORD *a2)
{
  __int64 v4; // rsi
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v8; // rcx
  int TlsMmLuid; // eax
  __int64 v10; // rcx
  const WCHAR *v11; // rax
  __int64 v12; // r8
  __int64 v13; // r9
  HANDLE CurrentThread; // rax
  int ThreadPriority; // ebx
  DWORD LastError; // eax
  __int64 v17; // rcx
  const char *v18; // rdx
  HANDLE v19; // rax
  __int64 v21; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v22[32]; // [rsp+40h] [rbp-88h] BYREF
  __int64 *v23; // [rsp+60h] [rbp-68h]
  __int64 v24; // [rsp+68h] [rbp-60h]
  _BYTE v25[16]; // [rsp+70h] [rbp-58h] BYREF
  const char *v26; // [rsp+80h] [rbp-48h]
  __int64 v27; // [rsp+88h] [rbp-40h]

  v4 = 0;
  TraceLogHelper("IkeOptionalDHThrottleBegin", 1);
  *a2 = 0;
  if ( (gIkeExtGlobals[50].SpinCount & 0x100000000LL) != 0 && (*(_DWORD *)(a1 + 8) & 0x1000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      TlsPeerAddr = IkeGetTlsPeerAddr(v5);
      TlsMmLuid = IkeGetTlsMmLuid(v8);
      WPP_SF_iS(v6, 12, (unsigned int)WPP_2442be43de8f375c35c8813a9973035c_Traceguids, TlsMmLuid, TlsPeerAddr);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v21 = IkeGetTlsMmLuid(v5);
      v23 = &v21;
      v24 = 8;
      v11 = (const WCHAR *)IkeGetTlsPeerAddr(v10);
      tlgCreate1Sz_wchar_t((__int64)v25, v11);
      v27 = 51;
      v26 = "Lowering priority of thread due to DH DOS Throttle";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)word_1801599FA,
        v12,
        v13,
        5,
        (__int64)v22);
    }
    CurrentThread = GetCurrentThread();
    ThreadPriority = GetThreadPriority(CurrentThread);
    if ( ThreadPriority == 0x7FFFFFFF )
    {
      LastError = GetLastError();
      v18 = "GetThreadPriority";
    }
    else
    {
      v19 = GetCurrentThread();
      if ( SetThreadPriority(v19, -1) )
      {
        *a2 = 1;
        a2[1] = ThreadPriority;
        goto LABEL_15;
      }
      LastError = GetLastError();
      v18 = "SetThreadPriority";
    }
    v4 = WfpReportSysErrorAsWinError(v17, v18, LastError, 1);
  }
LABEL_15:
  TraceLogHelper("IkeOptionalDHThrottleBegin", 0);
  return IkeReturnError(v4, "IkeOptionalDHThrottleBegin");
}

```

## disassembly

```asm
0x1800b74b4  push    rbx
0x1800b74b6  push    rsi
0x1800b74b7  push    rdi
0x1800b74b8  push    r14
0x1800b74ba  sub     rsp, 0A8h
0x1800b74c1  mov     rax, cs:__security_cookie
0x1800b74c8  xor     rax, rsp
0x1800b74cb  mov     [rsp+0C8h+var_38], rax
0x1800b74d3  mov     r14, rdx
0x1800b74d6  mov     rbx, rcx
0x1800b74d9  xor     esi, esi
0x1800b74db  lea     rcx, aIkeoptionaldht_0; "IkeOptionalDHThrottleBegin"
0x1800b74e2  lea     edx, [rsi+1]
0x1800b74e5  call    TraceLogHelper
0x1800b74ea  mov     [r14], esi
0x1800b74ed  mov     rax, cs:gIkeExtGlobals
0x1800b74f4  test    byte ptr [rax+7F4h], 1
0x1800b74fb  jz      loc_1800B763A
0x1800b7501  test    dword ptr [rbx+8], 1000000h
0x1800b7508  jz      loc_1800B763A
0x1800b750e  mov     rdi, cs:WPP_GLOBAL_Control
0x1800b7515  lea     rax, WPP_GLOBAL_Control
0x1800b751c  cmp     rdi, rax
0x1800b751f  jz      short loc_1800B7558
0x1800b7521  cmp     byte ptr [rdi+19h], 4
0x1800b7525  jb      short loc_1800B7558
0x1800b7527  test    byte ptr [rdi+1Ch], 10h
0x1800b752b  jz      short loc_1800B7558
0x1800b752d  mov     rdi, [rdi+10h]
0x1800b7531  call    IkeGetTlsPeerAddr
0x1800b7536  mov     rbx, rax
0x1800b7539  call    IkeGetTlsMmLuid
0x1800b753e  mov     r9, rax
0x1800b7541  mov     [rsp+0C8h+var_A8], rbx
0x1800b7546  lea     edx, [rsi+0Ch]
0x1800b7549  mov     rcx, rdi
0x1800b754c  lea     r8, WPP_2442be43de8f375c35c8813a9973035c_Traceguids
0x1800b7553  call    WPP_SF_iS
0x1800b7558  mov     eax, cs:dword_180173278
0x1800b755e  cmp     eax, 4
0x1800b7561  jbe     short loc_1800B75D2
0x1800b7563  call    IkeGetTlsMmLuid
0x1800b7568  mov     [rsp+0C8h+var_98], rax
0x1800b756d  lea     rax, [rsp+0C8h+var_98]
0x1800b7572  mov     [rsp+0C8h+var_68], rax
0x1800b7577  mov     [rsp+0C8h+var_60], 8
0x1800b7580  call    IkeGetTlsPeerAddr
0x1800b7585  mov     rdx, rax
0x1800b7588  lea     rcx, [rsp+0C8h+var_58]
0x1800b758d  call    _tlgCreate1Sz_wchar_t
0x1800b7592  lea     rcx, aLoweringPriori; "Lowering priority of thread due to DH D"...
0x1800b7599  mov     [rsp+0C8h+var_40], 33h ; '3'
0x1800b75a5  lea     rax, [rsp+0C8h+var_88]
0x1800b75aa  mov     [rsp+0C8h+var_48], rcx
0x1800b75b2  mov     [rsp+0C8h+var_A0], rax
0x1800b75b7  lea     rcx, dword_180173278
0x1800b75be  lea     rdx, word_1801599FA
0x1800b75c5  mov     dword ptr [rsp+0C8h+var_A8], 5
0x1800b75cd  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800b75d2  call    cs:__imp_GetCurrentThread
0x1800b75d8  mov     rcx, rax; hThread
0x1800b75db  call    cs:__imp_GetThreadPriority
0x1800b75e1  mov     ebx, eax
0x1800b75e3  cmp     eax, 7FFFFFFFh
0x1800b75e8  jnz     short loc_1800B760A
0x1800b75ea  call    cs:__imp_GetLastError
0x1800b75f0  lea     rdx, aGetthreadprior; "GetThreadPriority"
0x1800b75f7  mov     r9d, 1
0x1800b75fd  mov     r8d, eax
0x1800b7600  call    WfpReportSysErrorAsWinError
0x1800b7605  mov     rsi, rax
0x1800b7608  jmp     short loc_1800B763A
0x1800b760a  call    cs:__imp_GetCurrentThread
0x1800b7610  mov     rcx, rax; hThread
0x1800b7613  or      edx, 0FFFFFFFFh; nPriority
0x1800b7616  call    cs:__imp_SetThreadPriority
0x1800b761c  test    eax, eax
0x1800b761e  jnz     short loc_1800B762F
0x1800b7620  call    cs:__imp_GetLastError
0x1800b7626  lea     rdx, aSetthreadprior; "SetThreadPriority"
0x1800b762d  jmp     short loc_1800B75F7
0x1800b762f  mov     dword ptr [r14], 1
0x1800b7636  mov     [r14+4], ebx
0x1800b763a  xor     edx, edx
0x1800b763c  lea     rcx, aIkeoptionaldht_0; "IkeOptionalDHThrottleBegin"
0x1800b7643  call    TraceLogHelper
0x1800b7648  lea     rdx, aIkeoptionaldht_0; "IkeOptionalDHThrottleBegin"
0x1800b764f  mov     rcx, rsi
0x1800b7652  call    IkeReturnError
0x1800b7657  mov     rcx, [rsp+0C8h+var_38]
0x1800b765f  xor     rcx, rsp; StackCookie
0x1800b7662  call    __security_check_cookie
0x1800b7667  add     rsp, 0A8h
0x1800b766e  pop     r14
0x1800b7670  pop     rdi
0x1800b7671  pop     rsi
0x1800b7672  pop     rbx
0x1800b7673  retn
```
