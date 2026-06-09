# CPrepareTask::TaskRoutine(void)

- ea: `0x18009f6e0`
- end: `0x18009f84c`
- name: `?TaskRoutine@CPrepareTask@@UEAAXXZ`
- size: `364`
- prototype: `void __fastcall(CPrepareTask *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800063b0`
- `0x18009e0e8`
- `0x18009f6e0`
- `0x1800a06b8`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f748`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f748`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f723`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f723`

## string_xrefs

- `0x18009f78b`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009f7f0`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009f764`: `CPrepareTask::TaskRoutine - calling xa_prepare - DLL=%S`
- `0x18009f7d0`: `CPrepareTask::TaskRoutine - returned from xa_prepare with error=%d - DLL=%S`
- `0x18009f779`: `CPrepareTask::TaskRoutine`

## pseudocode

```c
void __fastcall CPrepareTask::TaskRoutine(CPrepareTask *this)
{
  unsigned int v2; // edi
  int v3; // [rsp+20h] [rbp-38h]
  __int64 v4; // [rsp+38h] [rbp-20h]

  v2 = XaRmId(*((_DWORD *)this + 20));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 32LL))(*((_QWORD *)this + 11));
  **((_DWORD **)this + 15) = 0;
  EnterCriticalSection(&stru_180153898);
  if ( *((_DWORD *)CTaskManager::GetMyXaOpenState(*((_DWORD *)this + 20)) + 29) )
    **((_DWORD **)this + 15) = -3;
  LeaveCriticalSection(&stru_180153898);
  if ( !**((_DWORD **)this + 15) )
  {
    try
    {
      TraceStringInline(
        11,
        4,
        L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
        1256,
        L"CPrepareTask::TaskRoutine",
        0,
        L"CPrepareTask::TaskRoutine - calling xa_prepare - DLL=%S",
        *((_QWORD *)this + 8));
      **((_DWORD **)this + 15) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*((_QWORD *)this + 13) + 80LL))(
                                   *((_QWORD *)this + 14),
                                   v2,
                                   0);
      LODWORD(v4) = **((_DWORD **)this + 15);
      TraceStringInline(
        11,
        4,
        L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
        1260,
        L"CPrepareTask::TaskRoutine",
        0,
        L"CPrepareTask::TaskRoutine - returned from xa_prepare with error=%d - DLL=%S",
        v4,
        *((_QWORD *)this + 8));
    }
    catch ( ... )
    {
      TraceStringInline(
        11,
        1,
        L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
        1265,
        L"CPrepareTask::TaskRoutine",
        -2147430314,
        L"CPrepareTask::TaskRoutine - exception thrown calling xa_prepare - DLL=%S",
        *((_QWORD *)this + 8));
      XA_TRACE_WARNING(0x8000D056, "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp", 1266, *((char **)this + 8), v3);
      DtcXaException("xa_prepare");
    }
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 40LL))(*((_QWORD *)this + 11));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 24LL))(*((_QWORD *)this + 11));
  *((_QWORD *)this + 11) = 0;
  (*(void (__fastcall **)(CPrepareTask *))(*(_QWORD *)this + 16LL))(this);
}

```

## disassembly

```asm
0x18009f6e0  mov     [rsp+arg_8], rbx
0x18009f6e5  mov     [rsp+arg_10], rdi
0x18009f6ea  mov     [rsp+arg_0], rcx
0x18009f6ef  push    r12
0x18009f6f1  sub     rsp, 50h
0x18009f6f5  mov     rbx, rcx
0x18009f6f8  mov     ecx, [rcx+50h]; unsigned int
0x18009f6fb  call    ?XaRmId@@YAKI@Z; XaRmId(uint)
0x18009f700  mov     edi, eax
0x18009f702  mov     rcx, [rbx+58h]
0x18009f706  mov     rdx, [rcx]
0x18009f709  mov     rax, [rdx+20h]
0x18009f70d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f712  mov     rcx, [rbx+78h]
0x18009f716  mov     dword ptr [rcx], 0
0x18009f71c  lea     rcx, stru_180153898; lpCriticalSection
0x18009f723  call    cs:__imp_EnterCriticalSection
0x18009f729  mov     ecx, [rbx+50h]; unsigned int
0x18009f72c  call    ?GetMyXaOpenState@CTaskManager@@SAPEAVCXaOpenState@@I@Z; CTaskManager::GetMyXaOpenState(uint)
0x18009f731  cmp     dword ptr [rax+74h], 0
0x18009f735  jz      short loc_18009F741
0x18009f737  mov     rax, [rbx+78h]
0x18009f73b  mov     dword ptr [rax], 0FFFFFFFDh
0x18009f741  lea     rcx, stru_180153898; lpCriticalSection
0x18009f748  call    cs:__imp_LeaveCriticalSection
0x18009f74e  mov     rax, [rbx+78h]
0x18009f752  cmp     dword ptr [rax], 0
0x18009f755  jnz     loc_18009F805
0x18009f75b  mov     rax, [rbx+40h]
0x18009f75f  mov     [rsp+58h+var_20], rax
0x18009f764  lea     rax, aCpreparetaskTa; "CPrepareTask::TaskRoutine - calling xa_"...
0x18009f76b  mov     [rsp+58h+var_28], rax
0x18009f770  mov     [rsp+58h+var_30], 0
0x18009f779  lea     r12, aCpreparetaskTa_2; "CPrepareTask::TaskRoutine"
0x18009f780  mov     [rsp+58h+var_38], r12
0x18009f785  mov     r9d, 4E8h
0x18009f78b  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009f792  mov     edx, 4
0x18009f797  lea     ecx, [rdx+7]
0x18009f79a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009f79f  mov     rax, [rbx+68h]
0x18009f7a3  xor     r8d, r8d
0x18009f7a6  mov     edx, edi
0x18009f7a8  mov     rcx, [rbx+70h]
0x18009f7ac  mov     rax, [rax+50h]
0x18009f7b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f7b5  mov     r9, [rbx+78h]
0x18009f7b9  mov     [r9], eax
0x18009f7bc  mov     r9, [rbx+78h]
0x18009f7c0  mov     rax, [rbx+40h]
0x18009f7c4  mov     [rsp+58h+var_18], rax
0x18009f7c9  mov     eax, [r9]
0x18009f7cc  mov     dword ptr [rsp+58h+var_20], eax
0x18009f7d0  lea     rax, aCpreparetaskTa_1; "CPrepareTask::TaskRoutine - returned fr"...
0x18009f7d7  mov     [rsp+58h+var_28], rax
0x18009f7dc  mov     [rsp+58h+var_30], 0
0x18009f7e5  mov     [rsp+58h+var_38], r12
0x18009f7ea  mov     r9d, 4ECh
0x18009f7f0  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009f7f7  mov     edx, 4
0x18009f7fc  lea     ecx, [rdx+7]
0x18009f7ff  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009f804  nop
0x18009f805  mov     rcx, [rbx+58h]
0x18009f809  mov     rax, [rcx]
0x18009f80c  mov     rax, [rax+28h]
0x18009f810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f815  mov     rcx, [rbx+58h]
0x18009f819  mov     rax, [rcx]
0x18009f81c  mov     rax, [rax+18h]
0x18009f820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f825  mov     qword ptr [rbx+58h], 0
0x18009f82d  mov     rax, [rbx]
0x18009f830  mov     rcx, rbx
0x18009f833  mov     rax, [rax+10h]
0x18009f837  mov     rbx, [rsp+58h+arg_8]
0x18009f83c  mov     rdi, [rsp+58h+arg_10]
0x18009f841  add     rsp, 50h
0x18009f845  pop     r12
0x18009f847  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
