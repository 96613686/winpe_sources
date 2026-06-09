# W3_CONTEXT_BASE::StartNotificationLoop(NOTIFICATION_CONTEXT *,int)

- ea: `0x180002040`
- end: `0x180002151`
- name: `?StartNotificationLoop@W3_CONTEXT_BASE@@QEAA?AW4ASYNC_STATUS@@PEAVNOTIFICATION_CONTEXT@@H@Z`
- size: `273`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180001acc`
- `0x18001ff10`
- `0x180021380`
- `0x1800318e0`

## callees

- `0x180002040`
- `0x180002158`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800020d4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800020d4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800020ec`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800020ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002149`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002149`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000213f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000213f`
- `iisutil!WriteRefTraceLog` at `0x180002085`
- `iisutil!WriteRefTraceLog` at `0x180002085`

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
0x180002040  mov     [rsp+arg_8], rbp
0x180002045  mov     [rsp+arg_10], rsi
0x18000204a  push    rdi
0x18000204b  sub     rsp, 30h
0x18000204f  mov     esi, r8d
0x180002052  mov     rdi, rdx
0x180002055  mov     rbp, rcx
0x180002058  test    r8d, r8d
0x18000205b  jnz     loc_18000210D
0x180002061  mov     [rsp+38h+arg_0], rbx
0x180002066  mov     rbx, [rbp+50h]
0x18000206a  test    rbx, rbx
0x18000206d  jz      short loc_18000208F
0x18000206f  lock inc dword ptr [rbx+24h]
0x180002073  mov     rcx, cs:?sm_pTraceLog@NOTIFICATION_CONTEXT@@2PEAU_TRACE_LOG@@EA; _TRACE_LOG * NOTIFICATION_CONTEXT::sm_pTraceLog
0x18000207a  test    rcx, rcx
0x18000207d  jz      short loc_18000208B
0x18000207f  mov     edx, [rbx+24h]
0x180002082  mov     r8, rbx
0x180002085  call    cs:__imp_WriteRefTraceLog
0x18000208b  lock inc dword ptr [rbx+34h]
0x18000208f  mov     [rdi+38h], rbx
0x180002093  mov     rcx, rdi
0x180002096  mov     [rbp+50h], rdi
0x18000209a  mov     rax, [rdi]
0x18000209d  mov     rax, [rax+18h]
0x1800020a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020a6  mov     rax, [rdi]
0x1800020a9  xor     ebp, ebp
0x1800020ab  xor     r9d, r9d
0x1800020ae  mov     [rsp+38h+var_18], ebp
0x1800020b2  xor     r8d, r8d
0x1800020b5  xor     edx, edx
0x1800020b7  mov     rcx, rdi
0x1800020ba  mov     rax, [rax+8]
0x1800020be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020c3  mov     ebx, eax
0x1800020c5  cmp     eax, 1
0x1800020c8  jz      short loc_180002132
0x1800020ca  test    esi, esi
0x1800020cc  jz      short loc_1800020F6
0x1800020ce  mov     ecx, cs:?g_TlsEventIndex@@3KA; dwTlsIndex
0x1800020d4  call    cs:__imp_TlsGetValue
0x1800020da  mov     rcx, [rdi+40h]; hObject
0x1800020de  test    rax, rax
0x1800020e1  jnz     short loc_180002149
0x1800020e3  mov     rdx, rcx; lpTlsValue
0x1800020e6  mov     ecx, cs:?g_TlsEventIndex@@3KA; dwTlsIndex
0x1800020ec  call    cs:__imp_TlsSetValue
0x1800020f2  mov     [rdi+40h], rbp
0x1800020f6  mov     eax, ebx
0x1800020f8  mov     rbx, [rsp+38h+arg_0]
0x1800020fd  mov     rbp, [rsp+38h+arg_8]
0x180002102  mov     rsi, [rsp+38h+arg_10]
0x180002107  add     rsp, 30h
0x18000210b  pop     rdi
0x18000210c  retn
0x18000210d  mov     rcx, rdi; this
0x180002110  call    ?SetupSynchronousCall@NOTIFICATION_CONTEXT@@QEAAJXZ; NOTIFICATION_CONTEXT::SetupSynchronousCall(void)
0x180002115  test    eax, eax
0x180002117  jns     loc_180002061
0x18000211d  mov     rbp, [rsp+38h+arg_8]
0x180002122  mov     rsi, [rsp+38h+arg_10]
0x180002127  mov     [rdi+48h], eax
0x18000212a  xor     eax, eax
0x18000212c  add     rsp, 30h
0x180002130  pop     rdi
0x180002131  retn
0x180002132  test    esi, esi
0x180002134  jz      short loc_1800020F6
0x180002136  mov     rcx, [rdi+40h]; hHandle
0x18000213a  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000213f  call    cs:__imp_WaitForSingleObject
0x180002145  mov     ebx, ebp
0x180002147  jmp     short loc_1800020CE
0x180002149  call    cs:__imp_CloseHandle
0x18000214f  jmp     short loc_1800020F2
```
