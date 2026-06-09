# IkeOptionalDHThrottleEnd

- ea: `0x1800b767c`
- end: `0x1800b77e9`
- name: `IkeOptionalDHThrottleEnd`
- size: `365`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1800b62fc`
- `0x1800b6d4c`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800061ec`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x18005bc40`
- `0x1800b767c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b7786`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b7786`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800b7791`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800b7791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b779b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b779b`

## string_xrefs

- `0x1800b77a7`: `SetThreadPriority`
- `0x1800b7743`: `Restoring to original thread priority for DH DOS Throttle`

## pseudocode

```c
__int64 __fastcall IkeOptionalDHThrottleEnd(_DWORD *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v5; // rcx
  int TlsMmLuid; // eax
  __int64 v7; // rcx
  const WCHAR *v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // ebx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  __int64 v14; // rcx
  __int64 v16; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v17[32]; // [rsp+40h] [rbp-68h] BYREF
  __int64 *v18; // [rsp+60h] [rbp-48h]
  __int64 v19; // [rsp+68h] [rbp-40h]
  _BYTE v20[16]; // [rsp+70h] [rbp-38h] BYREF
  const char *v21; // [rsp+80h] [rbp-28h]
  __int64 v22; // [rsp+88h] [rbp-20h]

  TraceLogHelper("IkeOptionalDHThrottleEnd", 1);
  if ( *a1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v3 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      TlsPeerAddr = IkeGetTlsPeerAddr(v2);
      TlsMmLuid = IkeGetTlsMmLuid(v5);
      WPP_SF_iS(v3, 13, (unsigned int)WPP_2442be43de8f375c35c8813a9973035c_Traceguids, TlsMmLuid, TlsPeerAddr);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v16 = IkeGetTlsMmLuid(v2);
      v18 = &v16;
      v19 = 8;
      v8 = (const WCHAR *)IkeGetTlsPeerAddr(v7);
      tlgCreate1Sz_wchar_t((__int64)v20, v8);
      v22 = 58;
      v21 = "Restoring to original thread priority for DH DOS Throttle";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)&dword_1801599BC,
        v9,
        v10,
        5,
        (__int64)v17);
    }
    v11 = a1[1];
    CurrentThread = GetCurrentThread();
    if ( !SetThreadPriority(CurrentThread, v11) )
    {
      LastError = GetLastError();
      WfpReportSysErrorAsWinError(v14, "SetThreadPriority", LastError, 1);
    }
  }
  return TraceLogHelper("IkeOptionalDHThrottleEnd", 0);
}

```

## disassembly

```asm
0x1800b767c  mov     [rsp+arg_8], rbx
0x1800b7681  mov     [rsp+arg_10], rsi
0x1800b7686  push    rdi
0x1800b7687  sub     rsp, 0A0h
0x1800b768e  mov     rax, cs:__security_cookie
0x1800b7695  xor     rax, rsp
0x1800b7698  mov     [rsp+0A8h+var_18], rax
0x1800b76a0  mov     rsi, rcx
0x1800b76a3  mov     edx, 1
0x1800b76a8  lea     rcx, aIkeoptionaldht; "IkeOptionalDHThrottleEnd"
0x1800b76af  call    TraceLogHelper
0x1800b76b4  cmp     dword ptr [rsi], 0
0x1800b76b7  jz      loc_1800B77B6
0x1800b76bd  mov     rdi, cs:WPP_GLOBAL_Control
0x1800b76c4  lea     rax, WPP_GLOBAL_Control
0x1800b76cb  cmp     rdi, rax
0x1800b76ce  jz      short loc_1800B7709
0x1800b76d0  cmp     byte ptr [rdi+19h], 4
0x1800b76d4  jb      short loc_1800B7709
0x1800b76d6  test    byte ptr [rdi+1Ch], 10h
0x1800b76da  jz      short loc_1800B7709
0x1800b76dc  mov     rdi, [rdi+10h]
0x1800b76e0  call    IkeGetTlsPeerAddr
0x1800b76e5  mov     rbx, rax
0x1800b76e8  call    IkeGetTlsMmLuid
0x1800b76ed  mov     r9, rax
0x1800b76f0  mov     [rsp+0A8h+var_88], rbx
0x1800b76f5  mov     edx, 0Dh
0x1800b76fa  lea     r8, WPP_2442be43de8f375c35c8813a9973035c_Traceguids
0x1800b7701  mov     rcx, rdi
0x1800b7704  call    WPP_SF_iS
0x1800b7709  mov     eax, cs:dword_180173278
0x1800b770f  cmp     eax, 4
0x1800b7712  jbe     short loc_1800B7783
0x1800b7714  call    IkeGetTlsMmLuid
0x1800b7719  mov     [rsp+0A8h+var_78], rax
0x1800b771e  lea     rax, [rsp+0A8h+var_78]
0x1800b7723  mov     [rsp+0A8h+var_48], rax
0x1800b7728  mov     [rsp+0A8h+var_40], 8
0x1800b7731  call    IkeGetTlsPeerAddr
0x1800b7736  mov     rdx, rax
0x1800b7739  lea     rcx, [rsp+0A8h+var_38]
0x1800b773e  call    _tlgCreate1Sz_wchar_t
0x1800b7743  lea     rcx, aRestoringToOri; "Restoring to original thread priority f"...
0x1800b774a  mov     [rsp+0A8h+var_20], 3Ah ; ':'
0x1800b7756  lea     rax, [rsp+0A8h+var_68]
0x1800b775b  mov     [rsp+0A8h+var_28], rcx
0x1800b7763  mov     [rsp+0A8h+var_80], rax
0x1800b7768  lea     rcx, dword_180173278
0x1800b776f  lea     rdx, dword_1801599BC
0x1800b7776  mov     dword ptr [rsp+0A8h+var_88], 5
0x1800b777e  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800b7783  mov     ebx, [rsi+4]
0x1800b7786  call    cs:__imp_GetCurrentThread
0x1800b778c  mov     rcx, rax; hThread
0x1800b778f  mov     edx, ebx; nPriority
0x1800b7791  call    cs:__imp_SetThreadPriority
0x1800b7797  test    eax, eax
0x1800b7799  jnz     short loc_1800B77B6
0x1800b779b  call    cs:__imp_GetLastError
0x1800b77a1  mov     r9d, 1
0x1800b77a7  lea     rdx, aSetthreadprior; "SetThreadPriority"
0x1800b77ae  mov     r8d, eax
0x1800b77b1  call    WfpReportSysErrorAsWinError
0x1800b77b6  xor     edx, edx
0x1800b77b8  lea     rcx, aIkeoptionaldht; "IkeOptionalDHThrottleEnd"
0x1800b77bf  call    TraceLogHelper
0x1800b77c4  mov     rcx, [rsp+0A8h+var_18]
0x1800b77cc  xor     rcx, rsp; StackCookie
0x1800b77cf  call    __security_check_cookie
0x1800b77d4  lea     r11, [rsp+0A8h+var_8]
0x1800b77dc  mov     rbx, [r11+18h]
0x1800b77e0  mov     rsi, [r11+20h]
0x1800b77e4  mov     rsp, r11
0x1800b77e7  pop     rdi
0x1800b77e8  retn
```
