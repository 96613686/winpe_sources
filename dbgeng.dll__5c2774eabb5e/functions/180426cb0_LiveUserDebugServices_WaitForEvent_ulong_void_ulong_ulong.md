# LiveUserDebugServices::WaitForEvent(ulong,void *,ulong,ulong *)

- ea: `0x180426cb0`
- end: `0x180426f37`
- name: `?WaitForEvent@LiveUserDebugServices@@UEAAJKPEAXKPEAK@Z`
- size: `647`
- prototype: `__int64 __usercall@<rax>(LiveUserDebugServices *__hidden this@<rcx>, unsigned int@<edx>, struct _DEBUG_EVENT *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, service_task`

## callees

- `0x1800b3a4c`
- `0x1800b3b44`
- `0x1800de208`
- `0x1800de418`
- `0x1800f0f40`
- `0x180419e2c`
- `0x180426cb0`
- `0x18042d6c4`
- `0x1804da4c0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180426d47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180426d5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180426d79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180426d47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180426d5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180426d79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180426d1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180426d1e`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180426ef8`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180426ef8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180426e8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180426e8d`

## pseudocode

```c
__int64 __fastcall LiveUserDebugServices::WaitForEvent(
        LiveUserDebugServices *this,
        unsigned int a2,
        struct _DEBUG_EVENT *a3,
        unsigned int a4,
        unsigned int *a5)
{
  unsigned int v9; // ebx
  char v10; // bp
  int v11; // ebx
  signed int LastError; // eax
  bool v13; // zf
  DWORD dwProcessId; // ebx
  __int64 i; // rdx
  _BYTE v16[24]; // [rsp+38h] [rbp-110h] BYREF

  if ( a4 < 0xB0 )
    return 2147942487LL;
  if ( a5 )
    *a5 = 176;
  v9 = -2147467263;
  v10 = 1;
  while ( !*((_QWORD *)this + 48) )
  {
    v11 = *((_DWORD *)this + 99);
    if ( !v11 || GetCurrentThreadId() == v11 )
    {
      if ( (unsigned int)DbgWaitForDebugEvent(a3, a2) )
      {
        v9 = 0;
        break;
      }
      if ( GetLastError() == 121 )
      {
        v9 = 1;
      }
      else
      {
        if ( GetLastError() )
        {
          LastError = GetLastError();
          v9 = LastError;
          if ( LastError > 0 )
            v9 = (unsigned __int16)LastError | 0x80070000;
          break;
        }
        v9 = -2147467259;
      }
    }
    else
    {
      v9 = -805306070;
    }
LABEL_19:
    if ( !LiveUserDebugServices::TryAttachToNextPendingPlmBackgroundTask(this) )
      return v9;
  }
  if ( v9 )
    goto LABEL_19;
  v13 = *((_DWORD *)this + 90) == 0;
  *((_DWORD *)this + 91) = a3->dwProcessId;
  *((_DWORD *)this + 92) = a3->dwThreadId;
  if ( !v13 && (a3->dwDebugEventCode == 3 || a3->dwDebugEventCode == 6) )
  {
    CloseHandle(a3->u.CreateThread.hThread);
    a3->u.CreateThread.hThread = 0;
  }
  if ( a3->dwDebugEventCode == 3 )
  {
    dwProcessId = a3->dwProcessId;
    Debugger::Utils::SmartEnterCS::SmartEnterCS(
      (Debugger::Utils::SmartEnterCS *)v16,
      (struct _RTL_CRITICAL_SECTION *const)(*((_QWORD *)this + 53) + 8LL),
      0);
    for ( i = *((_QWORD *)this + 62); i; i = *(_QWORD *)(i + 32) )
    {
      if ( dwProcessId == *(_DWORD *)(i + 24) )
      {
        DbsSingleList<LiveUserDebugServices::PlmProcessItem,32>::DeleteNode();
        goto LABEL_32;
      }
    }
    v10 = 0;
LABEL_32:
    Debugger::Utils::SmartEnterCS::~SmartEnterCS((Debugger::Utils::SmartEnterCS *)v16);
    if ( v10 )
      ResumeThread(a3->u.Exception.ExceptionRecord.ExceptionAddress);
  }
  else if ( a3->dwDebugEventCode == 5 )
  {
    LiveUserDebugServices::RemoveProcessFromAllPlmLists(this, a3->dwProcessId);
  }
  return 0;
}

```

## disassembly

```asm
0x180426cb0  push    rbx
0x180426cb2  push    rbp
0x180426cb3  push    rsi
0x180426cb4  push    rdi
0x180426cb5  push    r14
0x180426cb7  sub     rsp, 120h
0x180426cbe  mov     rax, cs:__security_cookie
0x180426cc5  xor     rax, rsp
0x180426cc8  mov     [rsp+148h+var_38], rax
0x180426cd0  mov     rax, [rsp+148h+arg_20]
0x180426cd8  mov     rsi, rcx
0x180426cdb  mov     ecx, 0B0h
0x180426ce0  mov     r14d, edx
0x180426ce3  mov     rdi, r8
0x180426ce6  cmp     r9d, ecx
0x180426ce9  jnb     short loc_180426CF5
0x180426ceb  mov     eax, 80070057h
0x180426cf0  jmp     loc_180426F18
0x180426cf5  test    rax, rax
0x180426cf8  jz      short loc_180426CFC
0x180426cfa  mov     [rax], ecx
0x180426cfc  mov     ebx, 80004001h
0x180426d01  mov     ebp, 1
0x180426d06  cmp     qword ptr [rsi+180h], 0
0x180426d0e  jnz     loc_180426DA4
0x180426d14  mov     ebx, [rsi+18Ch]
0x180426d1a  test    ebx, ebx
0x180426d1c  jz      short loc_180426D38
0x180426d1e  call    cs:__imp_GetCurrentThreadId
0x180426d25  nop     dword ptr [rax+rax+00h]
0x180426d2a  cmp     eax, ebx
0x180426d2c  jz      short loc_180426D38
0x180426d2e  mov     ebx, 0D000012Ah
0x180426d33  jmp     loc_180426E4D
0x180426d38  mov     edx, r14d; unsigned int
0x180426d3b  mov     rcx, rdi; struct _DEBUG_EVENT *
0x180426d3e  call    ?DbgWaitForDebugEvent@@YAHPEAU_DEBUG_EVENT@@K@Z; DbgWaitForDebugEvent(_DEBUG_EVENT *,ulong)
0x180426d43  test    eax, eax
0x180426d45  jnz     short loc_180426D9D
0x180426d47  call    cs:__imp_GetLastError
0x180426d4e  nop     dword ptr [rax+rax+00h]
0x180426d53  cmp     eax, 79h ; 'y'
0x180426d56  jnz     short loc_180426D5F
0x180426d58  mov     ebx, ebp
0x180426d5a  jmp     loc_180426E4D
0x180426d5f  call    cs:__imp_GetLastError
0x180426d66  nop     dword ptr [rax+rax+00h]
0x180426d6b  test    eax, eax
0x180426d6d  jnz     short loc_180426D79
0x180426d6f  mov     ebx, 80004005h
0x180426d74  jmp     loc_180426E4D
0x180426d79  call    cs:__imp_GetLastError
0x180426d80  nop     dword ptr [rax+rax+00h]
0x180426d85  mov     ebx, eax
0x180426d87  test    eax, eax
0x180426d89  jle     loc_180426E49
0x180426d8f  movzx   ebx, ax
0x180426d92  or      ebx, 80070000h
0x180426d98  jmp     loc_180426E49
0x180426d9d  xor     ebx, ebx
0x180426d9f  jmp     loc_180426E49
0x180426da4  mov     rax, cs:qword_18082DCD0
0x180426dab  test    rax, rax
0x180426dae  jz      loc_180426E49
0x180426db4  mov     rax, cs:qword_18082DC20
0x180426dbb  test    rax, rax
0x180426dbe  jz      loc_180426E49
0x180426dc4  xor     edx, edx; Val
0x180426dc6  mov     [rsp+148h+var_118], 0
0x180426dcf  mov     r8d, 0B8h; Size
0x180426dd5  lea     rcx, [rsp+148h+var_F8]; void *
0x180426dda  call    memset
0x180426ddf  cmp     r14d, 0FFFFFFFFh
0x180426de3  jnz     short loc_180426DEF
0x180426de5  mov     dword ptr [rsp+148h+var_118+4], 80000000h
0x180426ded  jmp     short loc_180426DFB
0x180426def  imul    rcx, r14, 0FFFFFFFFFFFFD8F0h
0x180426df6  mov     [rsp+148h+var_118], rcx
0x180426dfb  mov     rax, cs:qword_18082DCD0
0x180426e02  lea     r9, [rsp+148h+var_F8]
0x180426e07  mov     rcx, [rsi+180h]
0x180426e0e  lea     r8, [rsp+148h+var_118]
0x180426e13  xor     edx, edx
0x180426e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180426e1a  mov     ebx, eax
0x180426e1c  cmp     eax, 102h
0x180426e21  jz      loc_180426D58
0x180426e27  test    eax, eax
0x180426e29  js      short loc_180426E45
0x180426e2b  mov     rax, cs:qword_18082DC20
0x180426e32  lea     rcx, [rsp+148h+var_F8]
0x180426e37  mov     rdx, rdi
0x180426e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180426e3f  mov     ebx, eax
0x180426e41  test    eax, eax
0x180426e43  jns     short loc_180426E64
0x180426e45  bts     ebx, 1Ch
0x180426e49  test    ebx, ebx
0x180426e4b  jz      short loc_180426E64
0x180426e4d  mov     rcx, rsi; this
0x180426e50  call    ?TryAttachToNextPendingPlmBackgroundTask@LiveUserDebugServices@@AEAA_NXZ; LiveUserDebugServices::TryAttachToNextPendingPlmBackgroundTask(void)
0x180426e55  test    al, al
0x180426e57  jnz     loc_180426D06
0x180426e5d  mov     eax, ebx
0x180426e5f  jmp     loc_180426F18
0x180426e64  cmp     dword ptr [rsi+168h], 0
0x180426e6b  mov     eax, [rdi+4]
0x180426e6e  mov     [rsi+16Ch], eax
0x180426e74  mov     eax, [rdi+8]
0x180426e77  mov     [rsi+170h], eax
0x180426e7d  jz      short loc_180426EA1
0x180426e7f  cmp     dword ptr [rdi], 3
0x180426e82  jz      short loc_180426E89
0x180426e84  cmp     dword ptr [rdi], 6
0x180426e87  jnz     short loc_180426EA1
0x180426e89  mov     rcx, [rdi+10h]; hObject
0x180426e8d  call    cs:__imp_CloseHandle
0x180426e94  nop     dword ptr [rax+rax+00h]
0x180426e99  mov     qword ptr [rdi+10h], 0
0x180426ea1  cmp     dword ptr [rdi], 3
0x180426ea4  jnz     short loc_180426F06
0x180426ea6  mov     rdx, [rsi+1A8h]
0x180426ead  lea     rcx, [rsp+148h+var_110]; this
0x180426eb2  mov     ebx, [rdi+4]
0x180426eb5  add     rdx, 8; struct _RTL_CRITICAL_SECTION *
0x180426eb9  xor     r8d, r8d; bool
0x180426ebc  call    ??0SmartEnterCS@Utils@Debugger@@QEAA@QEAU_RTL_CRITICAL_SECTION@@_N@Z; Debugger::Utils::SmartEnterCS::SmartEnterCS(_RTL_CRITICAL_SECTION * const,bool)
0x180426ec1  lea     rcx, [rsi+1F0h]
0x180426ec8  mov     rdx, [rcx]
0x180426ecb  test    rdx, rdx
0x180426ece  jz      short loc_180426EE2
0x180426ed0  cmp     ebx, [rdx+18h]
0x180426ed3  jz      short loc_180426EDB
0x180426ed5  mov     rdx, [rdx+20h]
0x180426ed9  jmp     short loc_180426ECB
0x180426edb  call    ?DeleteNode@?$DbsSingleList@UPlmProcessItem@LiveUserDebugServices@@$0CA@@@QEAAXPEAUPlmProcessItem@LiveUserDebugServices@@@Z; DbsSingleList<LiveUserDebugServices::PlmProcessItem,32>::DeleteNode(LiveUserDebugServices::PlmProcessItem *)
0x180426ee0  jmp     short loc_180426EE5
0x180426ee2  xor     bpl, bpl
0x180426ee5  lea     rcx, [rsp+148h+var_110]; this
0x180426eea  call    ??1SmartEnterCS@Utils@Debugger@@UEAA@XZ; Debugger::Utils::SmartEnterCS::~SmartEnterCS(void)
0x180426eef  test    bpl, bpl
0x180426ef2  jz      short loc_180426F16
0x180426ef4  mov     rcx, [rdi+20h]; hThread
0x180426ef8  call    cs:__imp_ResumeThread
0x180426eff  nop     dword ptr [rax+rax+00h]
0x180426f04  jmp     short loc_180426F16
0x180426f06  cmp     dword ptr [rdi], 5
0x180426f09  jnz     short loc_180426F16
0x180426f0b  mov     edx, [rdi+4]; unsigned int
0x180426f0e  mov     rcx, rsi; this
0x180426f11  call    ?RemoveProcessFromAllPlmLists@LiveUserDebugServices@@AEAAXK@Z; LiveUserDebugServices::RemoveProcessFromAllPlmLists(ulong)
0x180426f16  xor     eax, eax
0x180426f18  mov     rcx, [rsp+148h+var_38]
0x180426f20  xor     rcx, rsp; StackCookie
0x180426f23  call    __security_check_cookie
0x180426f28  add     rsp, 120h
0x180426f2f  pop     r14
0x180426f31  pop     rdi
0x180426f32  pop     rsi
0x180426f33  pop     rbp
0x180426f34  pop     rbx
0x180426f35  retn
```
