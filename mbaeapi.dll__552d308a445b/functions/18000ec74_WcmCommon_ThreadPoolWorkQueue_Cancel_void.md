# WcmCommon::ThreadPoolWorkQueue::Cancel(void)

- ea: `0x18000ec74`
- end: `0x18000ee0f`
- name: `?Cancel@ThreadPoolWorkQueue@WcmCommon@@QEAAXXZ`
- size: `411`
- prototype: `void __fastcall(WcmCommon::ThreadPoolWorkQueue *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000d3c0`
- `0x18001b2c0`

## callees

- `0x180002efc`
- `0x18000ec74`
- `0x1800136ec`
- `0x1800137e4`
- `0x1800138f8`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ed64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000edfc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ed64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000edfc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ec8b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ec8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ed6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ed9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000edcc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ed6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ed9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000edcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edb9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000ed8e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000ed8e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000ed97`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000ed97`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000edc4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000edc4`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall WcmCommon::ThreadPoolWorkQueue::Cancel(WcmCommon::ThreadPoolWorkQueue *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  bool v3; // zf
  __int64 v4; // rbx
  __int64 v5; // r15
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // r14
  _BYTE *v9; // rcx
  DWORD LastError; // ebx
  struct _TP_WORK *v11; // rsi
  DWORD v12; // ebx
  struct _TP_POOL *v13; // rbp
  DWORD v14; // ebx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v3 = *((_QWORD *)this + 16) == 0;
  *((_BYTE *)this + 272) = 1;
  if ( v3 )
  {
    if ( v1 )
      LeaveCriticalSection(v1);
  }
  else
  {
    if ( *(_DWORD *)this == 1 )
    {
      v4 = *((_QWORD *)this + 27);
      v5 = v4 + *((_QWORD *)this + 28);
      while ( v4 != v5 )
      {
        v6 = **(_QWORD **)(*((_QWORD *)this + 25) + 8 * (v4 & (*((_QWORD *)this + 26) - 1LL)));
        if ( v6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        ++v4;
      }
      std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Tidy((_QWORD *)this + 24);
      std::deque<std::function<void (void)>>::_Tidy((char *)this + 152);
    }
    else
    {
      v7 = *((_QWORD *)this + 32);
      v8 = v7 + *((_QWORD *)this + 33);
      while ( v7 != v8 )
      {
        v9 = *(_BYTE **)(*((_QWORD *)this + 30) + 8 * (v7 & (*((_QWORD *)this + 31) - 1LL)));
        if ( v9 && v9[64] == 1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v9 + 16LL))(*(_QWORD *)v9);
        ++v7;
      }
      std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Tidy((_QWORD *)this + 29);
    }
    if ( v1 )
    {
      LastError = GetLastError();
      LeaveCriticalSection(v1);
      SetLastError(LastError);
    }
    v11 = (struct _TP_WORK *)*((_QWORD *)this + 16);
    if ( v11 )
    {
      v12 = GetLastError();
      WaitForThreadpoolWorkCallbacks(v11, 1);
      CloseThreadpoolWork(v11);
      SetLastError(v12);
    }
    *((_QWORD *)this + 16) = 0;
    v13 = (struct _TP_POOL *)*((_QWORD *)this + 15);
    if ( v13 )
    {
      v14 = GetLastError();
      CloseThreadpool(v13);
      SetLastError(v14);
    }
    *((_QWORD *)this + 15) = 0;
    memset_0((char *)this + 48, 0, 0x48u);
    _InterlockedExchange64((volatile __int64 *)this + 17, 0);
  }
}

```

## disassembly

```asm
0x18000ec74  push    rbx
0x18000ec76  push    rbp
0x18000ec77  push    rsi
0x18000ec78  push    rdi
0x18000ec79  push    r14
0x18000ec7b  push    r15
0x18000ec7d  sub     rsp, 28h
0x18000ec81  lea     rsi, [rcx+8]
0x18000ec85  mov     rdi, rcx
0x18000ec88  mov     rcx, rsi; lpCriticalSection
0x18000ec8b  call    cs:__imp_EnterCriticalSection
0x18000ec91  cmp     qword ptr [rdi+80h], 0
0x18000ec99  lea     r14, [rdi+98h]
0x18000eca0  mov     byte ptr [r14+78h], 1
0x18000eca5  jz      loc_18000EDF4
0x18000ecab  cmp     dword ptr [rdi], 1
0x18000ecae  jnz     short loc_18000ED04
0x18000ecb0  lea     rbp, [rdi+0C0h]
0x18000ecb7  mov     rbx, [rbp+18h]
0x18000ecbb  mov     r15, [rbp+20h]
0x18000ecbf  add     r15, rbx
0x18000ecc2  cmp     rbx, r15
0x18000ecc5  jz      short loc_18000ECF2
0x18000ecc7  mov     rcx, [rbp+10h]
0x18000eccb  mov     rax, [rbp+8]
0x18000eccf  dec     rcx
0x18000ecd2  and     rcx, rbx
0x18000ecd5  mov     rcx, [rax+rcx*8]
0x18000ecd9  mov     rcx, [rcx]
0x18000ecdc  test    rcx, rcx
0x18000ecdf  jz      short loc_18000ECED
0x18000ece1  mov     rax, [rcx]
0x18000ece4  mov     rax, [rax+10h]
0x18000ece8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eced  inc     rbx
0x18000ecf0  jmp     short loc_18000ECC2
0x18000ecf2  mov     rcx, rbp
0x18000ecf5  call    ?_Tidy@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@AEAAXXZ; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Tidy(void)
0x18000ecfa  mov     rcx, r14
0x18000ecfd  call    ?_Tidy@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@AEAAXXZ; std::deque<std::function<void (void)>>::_Tidy(void)
0x18000ed02  jmp     short loc_18000ED54
0x18000ed04  lea     rbp, [rdi+0E8h]
0x18000ed0b  mov     rbx, [rbp+18h]
0x18000ed0f  mov     r14, [rbp+20h]
0x18000ed13  add     r14, rbx
0x18000ed16  cmp     rbx, r14
0x18000ed19  jz      short loc_18000ED4C
0x18000ed1b  mov     rcx, [rbp+10h]
0x18000ed1f  mov     rax, [rbp+8]
0x18000ed23  dec     rcx
0x18000ed26  and     rcx, rbx
0x18000ed29  mov     rcx, [rax+rcx*8]
0x18000ed2d  test    rcx, rcx
0x18000ed30  jz      short loc_18000ED47
0x18000ed32  cmp     byte ptr [rcx+40h], 1
0x18000ed36  jnz     short loc_18000ED47
0x18000ed38  mov     rcx, [rcx]
0x18000ed3b  mov     rax, [rcx]
0x18000ed3e  mov     rax, [rax+10h]
0x18000ed42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed47  inc     rbx
0x18000ed4a  jmp     short loc_18000ED16
0x18000ed4c  mov     rcx, rbp
0x18000ed4f  call    ?_Tidy@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAXXZ; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Tidy(void)
0x18000ed54  test    rsi, rsi
0x18000ed57  jz      short loc_18000ED72
0x18000ed59  call    cs:__imp_GetLastError
0x18000ed5f  mov     rcx, rsi; lpCriticalSection
0x18000ed62  mov     ebx, eax
0x18000ed64  call    cs:__imp_LeaveCriticalSection
0x18000ed6a  mov     ecx, ebx; dwErrCode
0x18000ed6c  call    cs:__imp_SetLastError
0x18000ed72  mov     rsi, [rdi+80h]
0x18000ed79  test    rsi, rsi
0x18000ed7c  jz      short loc_18000EDA5
0x18000ed7e  call    cs:__imp_GetLastError
0x18000ed84  mov     edx, 1; fCancelPendingCallbacks
0x18000ed89  mov     rcx, rsi; pwk
0x18000ed8c  mov     ebx, eax
0x18000ed8e  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000ed94  mov     rcx, rsi; pwk
0x18000ed97  call    cs:__imp_CloseThreadpoolWork
0x18000ed9d  mov     ecx, ebx; dwErrCode
0x18000ed9f  call    cs:__imp_SetLastError
0x18000eda5  mov     qword ptr [rdi+80h], 0
0x18000edb0  mov     rbp, [rdi+78h]
0x18000edb4  test    rbp, rbp
0x18000edb7  jz      short loc_18000EDD2
0x18000edb9  call    cs:__imp_GetLastError
0x18000edbf  mov     rcx, rbp; ptpp
0x18000edc2  mov     ebx, eax
0x18000edc4  call    cs:__imp_CloseThreadpool
0x18000edca  mov     ecx, ebx; dwErrCode
0x18000edcc  call    cs:__imp_SetLastError
0x18000edd2  xor     edx, edx; Val
0x18000edd4  mov     qword ptr [rdi+78h], 0
0x18000eddc  lea     rcx, [rdi+30h]; void *
0x18000ede0  lea     r8d, [rdx+48h]; Size
0x18000ede4  call    memset_0
0x18000ede9  xor     eax, eax
0x18000edeb  xchg    rax, [rdi+88h]
0x18000edf2  jmp     short loc_18000EE02
0x18000edf4  test    rsi, rsi
0x18000edf7  jz      short loc_18000EE02
0x18000edf9  mov     rcx, rsi; lpCriticalSection
0x18000edfc  call    cs:__imp_LeaveCriticalSection
0x18000ee02  add     rsp, 28h
0x18000ee06  pop     r15
0x18000ee08  pop     r14
0x18000ee0a  pop     rdi
0x18000ee0b  pop     rsi
0x18000ee0c  pop     rbp
0x18000ee0d  pop     rbx
0x18000ee0e  retn
```
