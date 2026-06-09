# W3_CONTEXT_BASE::StartNotificationLoop(NOTIFICATION_CONTEXT *,int)

- ea: `0x1800020d0`
- end: `0x180002204`
- name: `?StartNotificationLoop@W3_CONTEXT_BASE@@QEAA?AW4ASYNC_STATUS@@PEAVNOTIFICATION_CONTEXT@@H@Z`
- size: `308`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180001b60`
- `0x180021af0`
- `0x180022ff0`
- `0x180034700`

## callees

- `0x1800020d0`
- `0x18000220c`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000216a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000216a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180002188`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180002188`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800021f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800021f6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800021e3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800021e3`
- `iisutil!WriteRefTraceLog` at `0x180002115`
- `iisutil!WriteRefTraceLog` at `0x180002115`

## pseudocode

```c
__int64 __fastcall W3_CONTEXT_BASE::StartNotificationLoop(__int64 a1, HANDLE *a2, int a3)
{
  volatile signed __int32 *v6; // rbx
  unsigned int v7; // ebx
  int v9; // eax

  if ( !a3 || (v9 = NOTIFICATION_CONTEXT::SetupSynchronousCall((NOTIFICATION_CONTEXT *)a2), v9 >= 0) )
  {
    v6 = *(volatile signed __int32 **)(a1 + 80);
    if ( v6 )
    {
      _InterlockedIncrement(v6 + 9);
      if ( NOTIFICATION_CONTEXT::sm_pTraceLog )
        WriteRefTraceLog(NOTIFICATION_CONTEXT::sm_pTraceLog, *((unsigned int *)v6 + 9), v6);
      _InterlockedIncrement(v6 + 13);
    }
    a2[7] = (HANDLE)v6;
    *(_QWORD *)(a1 + 80) = a2;
    (*((void (__fastcall **)(HANDLE *))*a2 + 3))(a2);
    v7 = (*((__int64 (__fastcall **)(HANDLE *, _QWORD, _QWORD, _QWORD, _DWORD))*a2 + 1))(a2, 0, 0, 0, 0);
    if ( v7 == 1 )
    {
      if ( a3 )
      {
        WaitForSingleObject(a2[8], 0xFFFFFFFF);
        v7 = 0;
        goto LABEL_8;
      }
    }
    else if ( a3 )
    {
LABEL_8:
      if ( TlsGetValue(g_TlsEventIndex) )
        CloseHandle(a2[8]);
      else
        TlsSetValue(g_TlsEventIndex, a2[8]);
      a2[8] = 0;
    }
    return v7;
  }
  *((_DWORD *)a2 + 18) = v9;
  return 0;
}

```

## disassembly

```asm
0x1800020d0  mov     [rsp+arg_8], rbp
0x1800020d5  mov     [rsp+arg_10], rsi
0x1800020da  push    rdi
0x1800020db  sub     rsp, 30h
0x1800020df  mov     esi, r8d
0x1800020e2  mov     rdi, rdx
0x1800020e5  mov     rbp, rcx
0x1800020e8  test    r8d, r8d
0x1800020eb  jnz     loc_1800021B0
0x1800020f1  mov     [rsp+38h+arg_0], rbx
0x1800020f6  mov     rbx, [rbp+50h]
0x1800020fa  test    rbx, rbx
0x1800020fd  jz      short loc_180002125
0x1800020ff  lock inc dword ptr [rbx+24h]
0x180002103  mov     rcx, cs:?sm_pTraceLog@NOTIFICATION_CONTEXT@@2PEAU_TRACE_LOG@@EA; _TRACE_LOG * NOTIFICATION_CONTEXT::sm_pTraceLog
0x18000210a  test    rcx, rcx
0x18000210d  jz      short loc_180002121
0x18000210f  mov     edx, [rbx+24h]
0x180002112  mov     r8, rbx
0x180002115  call    cs:__imp_WriteRefTraceLog
0x18000211c  nop     dword ptr [rax+rax+00h]
0x180002121  lock inc dword ptr [rbx+34h]
0x180002125  mov     [rdi+38h], rbx
0x180002129  mov     rcx, rdi
0x18000212c  mov     [rbp+50h], rdi
0x180002130  mov     rax, [rdi]
0x180002133  mov     rax, [rax+18h]
0x180002137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000213c  mov     rax, [rdi]
0x18000213f  xor     ebp, ebp
0x180002141  xor     r9d, r9d
0x180002144  mov     [rsp+38h+var_18], ebp
0x180002148  xor     r8d, r8d
0x18000214b  xor     edx, edx
0x18000214d  mov     rcx, rdi
0x180002150  mov     rax, [rax+8]
0x180002154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002159  mov     ebx, eax
0x18000215b  cmp     eax, 1
0x18000215e  jz      short loc_1800021D6
0x180002160  test    esi, esi
0x180002162  jz      short loc_180002198
0x180002164  mov     ecx, cs:?g_TlsEventIndex@@3KA; dwTlsIndex
0x18000216a  call    cs:__imp_TlsGetValue
0x180002171  nop     dword ptr [rax+rax+00h]
0x180002176  mov     rcx, [rdi+40h]; hObject
0x18000217a  test    rax, rax
0x18000217d  jnz     short loc_1800021F6
0x18000217f  mov     rdx, rcx; lpTlsValue
0x180002182  mov     ecx, cs:?g_TlsEventIndex@@3KA; dwTlsIndex
0x180002188  call    cs:__imp_TlsSetValue
0x18000218f  nop     dword ptr [rax+rax+00h]
0x180002194  mov     [rdi+40h], rbp
0x180002198  mov     eax, ebx
0x18000219a  mov     rbx, [rsp+38h+arg_0]
0x18000219f  mov     rbp, [rsp+38h+arg_8]
0x1800021a4  mov     rsi, [rsp+38h+arg_10]
0x1800021a9  add     rsp, 30h
0x1800021ad  pop     rdi
0x1800021ae  retn
0x1800021b0  mov     rcx, rdi; this
0x1800021b3  call    ?SetupSynchronousCall@NOTIFICATION_CONTEXT@@QEAAJXZ; NOTIFICATION_CONTEXT::SetupSynchronousCall(void)
0x1800021b8  test    eax, eax
0x1800021ba  jns     loc_1800020F1
0x1800021c0  mov     rbp, [rsp+38h+arg_8]
0x1800021c5  mov     rsi, [rsp+38h+arg_10]
0x1800021ca  mov     [rdi+48h], eax
0x1800021cd  xor     eax, eax
0x1800021cf  add     rsp, 30h
0x1800021d3  pop     rdi
0x1800021d4  retn
0x1800021d6  test    esi, esi
0x1800021d8  jz      short loc_180002198
0x1800021da  mov     rcx, [rdi+40h]; hHandle
0x1800021de  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800021e3  call    cs:__imp_WaitForSingleObject
0x1800021ea  nop     dword ptr [rax+rax+00h]
0x1800021ef  mov     ebx, ebp
0x1800021f1  jmp     loc_180002164
0x1800021f6  call    cs:__imp_CloseHandle
0x1800021fd  nop     dword ptr [rax+rax+00h]
0x180002202  jmp     short loc_180002194
```
