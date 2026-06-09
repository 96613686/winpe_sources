# GlobalDoWork(ulong,IHttpEventProvider *)

- ea: `0x180002858`
- end: `0x180002998`
- name: `?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800029b0`

## callees

- `0x180001a08`
- `0x180001cb4`
- `0x180002858`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800028db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800028db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000291d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000291d`

## pseudocode

```c
__int64 __fastcall GlobalDoWork(int a1, __int64 a2)
{
  struct IHttpContext *v4; // rsi
  IIS_REQMON_CONTEXT *v5; // rax
  IIS_REQMON_CONTEXT *v6; // rdi
  _QWORD *v7; // rcx
  __int64 v8; // rax
  int v9; // esi

  if ( a1 != 256 )
  {
    if ( a1 == 4096 )
      return IIS_REQMON_CONTEXT::DumpRequests(a2);
    return 0;
  }
  v4 = (struct IHttpContext *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  v5 = (IIS_REQMON_CONTEXT *)(*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)v4 + 144LL))(v4, 48);
  if ( v5 && (v6 = IIS_REQMON_CONTEXT::IIS_REQMON_CONTEXT(v5, v4)) != 0 )
  {
    EnterCriticalSection(&IIS_REQMON_CONTEXT::sm_csRequestList);
    v7 = (_QWORD *)qword_180007680;
    ++IIS_REQMON_CONTEXT::sm_cRequests;
    if ( *(struct _LIST_ENTRY **)qword_180007680 != &IIS_REQMON_CONTEXT::sm_RequestListHead )
      __fastfail(3u);
    *((_QWORD *)v6 + 2) = qword_180007680;
    *((_QWORD *)v6 + 1) = &IIS_REQMON_CONTEXT::sm_RequestListHead;
    *v7 = (char *)v6 + 8;
    qword_180007680 = (__int64)v6 + 8;
    LeaveCriticalSection(&IIS_REQMON_CONTEXT::sm_csRequestList);
    v8 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v4 + 56LL))(v4);
    v9 = (*(__int64 (__fastcall **)(__int64, IIS_REQMON_CONTEXT *, void *))(*(_QWORD *)v8 + 8LL))(
           v8,
           v6,
           s_pModuleContext);
    if ( v9 >= 0 )
      return 0;
    (**(void (__fastcall ***)(IIS_REQMON_CONTEXT *))v6)(v6);
    (**(void (__fastcall ***)(__int64, _QWORD))a2)(a2, (unsigned int)v9);
  }
  else
  {
    (**(void (__fastcall ***)(__int64, __int64))a2)(a2, 2147942408LL);
  }
  return 1;
}

```

## disassembly

```asm
0x180002858  mov     [rsp+arg_0], rbx
0x18000285d  mov     [rsp+arg_8], rsi
0x180002862  push    rdi
0x180002863  sub     rsp, 20h
0x180002867  mov     rbx, rdx
0x18000286a  cmp     ecx, 100h
0x180002870  jz      short loc_18000288B
0x180002872  cmp     ecx, 1000h
0x180002878  jnz     loc_18000296C
0x18000287e  mov     rcx, rdx
0x180002881  call    ?DumpRequests@IIS_REQMON_CONTEXT@@SA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIGlobalRSCAQueryProvider@@@Z; IIS_REQMON_CONTEXT::DumpRequests(IGlobalRSCAQueryProvider *)
0x180002886  jmp     loc_180002988
0x18000288b  mov     rax, [rdx]
0x18000288e  mov     rcx, rbx
0x180002891  mov     rax, [rax+8]
0x180002895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000289a  mov     rsi, rax
0x18000289d  mov     edx, 30h ; '0'
0x1800028a2  mov     rcx, [rax]
0x1800028a5  mov     rax, [rcx+90h]
0x1800028ac  mov     rcx, rsi
0x1800028af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028b4  test    rax, rax
0x1800028b7  jz      loc_180002970
0x1800028bd  mov     rdx, rsi; struct IHttpContext *
0x1800028c0  mov     rcx, rax; this
0x1800028c3  call    ??0IIS_REQMON_CONTEXT@@QEAA@PEAVIHttpContext@@@Z; IIS_REQMON_CONTEXT::IIS_REQMON_CONTEXT(IHttpContext *)
0x1800028c8  mov     rdi, rax
0x1800028cb  test    rax, rax
0x1800028ce  jz      loc_180002970
0x1800028d4  lea     rcx, ?sm_csRequestList@IIS_REQMON_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800028db  call    cs:__imp_EnterCriticalSection
0x1800028e1  mov     rcx, cs:qword_180007680
0x1800028e8  lea     rdx, ?sm_RequestListHead@IIS_REQMON_CONTEXT@@0U_LIST_ENTRY@@A; _LIST_ENTRY IIS_REQMON_CONTEXT::sm_RequestListHead
0x1800028ef  inc     cs:?sm_cRequests@IIS_REQMON_CONTEXT@@2KA; ulong IIS_REQMON_CONTEXT::sm_cRequests
0x1800028f5  cmp     [rcx], rdx
0x1800028f8  jz      short loc_180002901
0x1800028fa  mov     ecx, 3
0x1800028ff  int     29h; Win8: RtlFailFast(ecx)
0x180002901  lea     rax, [rdi+8]
0x180002905  mov     [rax+8], rcx
0x180002909  mov     [rax], rdx
0x18000290c  mov     [rcx], rax
0x18000290f  lea     rcx, ?sm_csRequestList@IIS_REQMON_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002916  mov     cs:qword_180007680, rax
0x18000291d  call    cs:__imp_LeaveCriticalSection
0x180002923  mov     rax, [rsi]
0x180002926  mov     rcx, rsi
0x180002929  mov     rax, [rax+38h]
0x18000292d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002932  mov     r8, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x180002939  mov     r9, rax
0x18000293c  mov     rdx, rdi
0x18000293f  mov     rcx, [rax]
0x180002942  mov     rax, [rcx+8]
0x180002946  mov     rcx, r9
0x180002949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000294e  mov     esi, eax
0x180002950  test    eax, eax
0x180002952  jns     short loc_18000296C
0x180002954  mov     rcx, [rdi]
0x180002957  mov     rax, [rcx]
0x18000295a  mov     rcx, rdi
0x18000295d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002962  mov     rcx, [rbx]
0x180002965  mov     edx, esi
0x180002967  mov     rax, [rcx]
0x18000296a  jmp     short loc_18000297B
0x18000296c  xor     eax, eax
0x18000296e  jmp     short loc_180002988
0x180002970  mov     rax, [rbx]
0x180002973  mov     edx, 80070008h
0x180002978  mov     rax, [rax]
0x18000297b  mov     rcx, rbx
0x18000297e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002983  mov     eax, 1
0x180002988  mov     rbx, [rsp+28h+arg_0]
0x18000298d  mov     rsi, [rsp+28h+arg_8]
0x180002992  add     rsp, 20h
0x180002996  pop     rdi
0x180002997  retn
```
