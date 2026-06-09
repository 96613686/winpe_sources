# CADMCOMW::DisconnectOrphaned(int)

- ea: `0x18000455c`
- end: `0x18000469c`
- name: `?DisconnectOrphaned@CADMCOMW@@AEAAJH@Z`
- size: `320`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002e60`
- `0x18000dc5c`

## callees

- `0x18000455c`
- `0x1800097e4`
- `0x180010010`

## import_xrefs

- `ole32!CoDisconnectObject` at `0x1800045f7`
- `ole32!CoDisconnectObject` at `0x180004606`
- `ole32!CoDisconnectObject` at `0x1800045f7`
- `ole32!CoDisconnectObject` at `0x180004606`
- `KERNEL32!GetCurrentThreadId` at `0x180004570`
- `KERNEL32!GetCurrentThreadId` at `0x180004570`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x1800045ec`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180004657`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x1800045ec`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180004657`

## pseudocode

```c
__int64 __fastcall CADMCOMW::DisconnectOrphaned(CADMCOMW *this, int a2)
{
  DWORD CurrentThreadId; // edi

  CurrentThreadId = GetCurrentThreadId();
  if ( !*((_DWORD *)this + 3) && !_InterlockedCompareExchange((volatile signed __int32 *)this + 48, CurrentThreadId, 0) )
  {
    (*(void (__fastcall **)(CADMCOMW *))(*(_QWORD *)this + 8LL))(this);
    if ( a2 == 1
      && *((_DWORD *)g_pEtwCoAdminTracer + 2)
      && (*((_BYTE *)g_pEtwCoAdminTracer + 40) & 2) != 0
      && *((_DWORD *)g_pEtwCoAdminTracer + 11) >= 4u )
    {
      CEtwTracer::EtwTraceEvent(
        g_pEtwCoAdminTracer,
        (const struct _GUID *)IISAdminShutdownGuid,
        0xEu,
        (char *)this + 168,
        4,
        0,
        0);
    }
    CoDisconnectObject((LPUNKNOWN)this, 0);
    CoDisconnectObject((LPUNKNOWN)this + 105, 0);
    if ( a2 == 1
      && *((_DWORD *)g_pEtwCoAdminTracer + 2)
      && (*((_BYTE *)g_pEtwCoAdminTracer + 40) & 2) != 0
      && *((_DWORD *)g_pEtwCoAdminTracer + 11) >= 4u )
    {
      CEtwTracer::EtwTraceEvent(
        g_pEtwCoAdminTracer,
        (const struct _GUID *)IISAdminShutdownGuid,
        0xFu,
        (char *)this + 168,
        4,
        0,
        0);
    }
    CADMCOMW::StopNotifications(this, 1);
    if ( (*(unsigned int (__fastcall **)(CADMCOMW *))(*(_QWORD *)this + 16LL))(this) > 1 )
      _InterlockedCompareExchange((volatile signed __int32 *)this + 48, 0, CurrentThreadId);
  }
  return 0;
}

```

## disassembly

```asm
0x18000455c  mov     [rsp+arg_8], rbx
0x180004561  mov     [rsp+arg_10], rsi
0x180004566  push    rdi
0x180004567  sub     rsp, 40h
0x18000456b  mov     esi, edx
0x18000456d  mov     rbx, rcx
0x180004570  call    cs:__imp_GetCurrentThreadId
0x180004576  cmp     dword ptr [rbx+0Ch], 0
0x18000457a  mov     edi, eax
0x18000457c  jnz     loc_18000468A
0x180004582  xor     eax, eax
0x180004584  lock cmpxchg [rbx+0C0h], edi
0x18000458c  jnz     loc_18000468A
0x180004592  mov     rcx, [rbx]
0x180004595  mov     rax, [rcx+8]
0x180004599  mov     rcx, rbx
0x18000459c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045a1  cmp     esi, 1
0x1800045a4  jnz     short loc_1800045F2
0x1800045a6  mov     rcx, cs:?g_pEtwCoAdminTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwCoAdminTracer
0x1800045ad  cmp     dword ptr [rcx+8], 0
0x1800045b1  jz      short loc_1800045F2
0x1800045b3  test    byte ptr [rcx+28h], 2
0x1800045b7  jz      short loc_1800045F2
0x1800045b9  cmp     dword ptr [rcx+2Ch], 4
0x1800045bd  jb      short loc_1800045F2
0x1800045bf  mov     [rsp+48h+var_18], 0
0x1800045c8  lea     r9, [rbx+0A8h]
0x1800045cf  mov     [rsp+48h+var_20], 0
0x1800045d8  lea     r8d, [rsi+0Dh]
0x1800045dc  lea     rdx, IISAdminShutdownGuid
0x1800045e3  mov     [rsp+48h+var_28], 4
0x1800045ec  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x1800045f2  xor     edx, edx; dwReserved
0x1800045f4  mov     rcx, rbx; pUnk
0x1800045f7  call    cs:__imp_CoDisconnectObject
0x1800045fd  lea     rcx, [rbx+348h]; pUnk
0x180004604  xor     edx, edx; dwReserved
0x180004606  call    cs:__imp_CoDisconnectObject
0x18000460c  cmp     esi, 1
0x18000460f  jnz     short loc_18000465D
0x180004611  mov     rcx, cs:?g_pEtwCoAdminTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwCoAdminTracer
0x180004618  cmp     dword ptr [rcx+8], 0
0x18000461c  jz      short loc_18000465D
0x18000461e  test    byte ptr [rcx+28h], 2
0x180004622  jz      short loc_18000465D
0x180004624  cmp     dword ptr [rcx+2Ch], 4
0x180004628  jb      short loc_18000465D
0x18000462a  mov     [rsp+48h+var_18], 0
0x180004633  lea     r9, [rbx+0A8h]
0x18000463a  mov     [rsp+48h+var_20], 0
0x180004643  lea     r8d, [rsi+0Eh]
0x180004647  lea     rdx, IISAdminShutdownGuid
0x18000464e  mov     [rsp+48h+var_28], 4
0x180004657  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x18000465d  mov     edx, 1; int
0x180004662  mov     rcx, rbx; this
0x180004665  call    ?StopNotifications@CADMCOMW@@AEAAJH@Z; CADMCOMW::StopNotifications(int)
0x18000466a  mov     rax, [rbx]
0x18000466d  mov     rcx, rbx
0x180004670  mov     rax, [rax+10h]
0x180004674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004679  cmp     eax, 1
0x18000467c  jbe     short loc_18000468A
0x18000467e  xor     ecx, ecx
0x180004680  mov     eax, edi
0x180004682  lock cmpxchg [rbx+0C0h], ecx
0x18000468a  mov     rbx, [rsp+48h+arg_8]
0x18000468f  xor     eax, eax
0x180004691  mov     rsi, [rsp+48h+arg_10]
0x180004696  add     rsp, 40h
0x18000469a  pop     rdi
0x18000469b  retn
```
