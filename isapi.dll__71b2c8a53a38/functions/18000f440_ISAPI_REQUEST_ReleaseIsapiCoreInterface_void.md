# ISAPI_REQUEST::ReleaseIsapiCoreInterface(void)

- ea: `0x18000f440`
- end: `0x18000f4ed`
- name: `?ReleaseIsapiCoreInterface@ISAPI_REQUEST@@UEAAXXZ`
- size: `173`
- prototype: `void __fastcall(ISAPI_REQUEST *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x18000b30c`
- `0x18000c0b4`
- `0x18000c2b4`
- `0x18000c3cc`
- `0x18000f440`
- `0x180013010`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x18000f468`
- `iisutil!WriteRefTraceLog` at `0x18000f468`

## pseudocode

```c
void __fastcall ISAPI_REQUEST::ReleaseIsapiCoreInterface(ISAPI_REQUEST *this)
{
  unsigned __int32 v2; // ebx
  __int64 v3; // rbx
  __int64 v4; // rcx
  struct IHttpTraceContext *v5; // rax
  struct IHttpTraceContext *v6; // rax
  const struct _GUID *v7; // rdx

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 3);
  if ( ISAPI_REQUEST::sm_pTraceLog )
    WriteRefTraceLog(ISAPI_REQUEST::sm_pTraceLog, v2, this);
  if ( !v2 )
  {
    v3 = *((_QWORD *)this + 4);
    ISAPI_REQUEST::~ISAPI_REQUEST(this);
    v4 = *(_QWORD *)(v3 + 8);
    *(_QWORD *)(v3 + 16) = 0;
    v5 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 272LL))(v4);
    if ( (unsigned int)WWWIsapiExtensionTraceProvider::CheckTracingEnabled(v5, 0) )
    {
      v6 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v3 + 8) + 272LL))(*(_QWORD *)(v3 + 8));
      W3IsapiEvents::ISAPI_EXTENSION_DONE::RaiseEvent(v6, v7);
    }
    if ( *(_DWORD *)(v3 + 40) == 2 )
    {
      W3_ISAPI_HANDLER::SetRequestHandledAndTrace((W3_ISAPI_HANDLER *)v3);
      (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v3 + 8) + 64LL))(*(_QWORD *)(v3 + 8), 0);
    }
  }
}

```

## disassembly

```asm
0x18000f440  mov     [rsp+arg_0], rbx
0x18000f445  push    rdi
0x18000f446  sub     rsp, 20h
0x18000f44a  mov     rdi, rcx
0x18000f44d  or      ebx, 0FFFFFFFFh
0x18000f450  lock xadd [rcx+0Ch], ebx
0x18000f455  mov     rcx, cs:?sm_pTraceLog@ISAPI_REQUEST@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * ISAPI_REQUEST::sm_pTraceLog
0x18000f45c  dec     ebx
0x18000f45e  test    rcx, rcx
0x18000f461  jz      short loc_18000F46E
0x18000f463  mov     r8, rdi
0x18000f466  mov     edx, ebx
0x18000f468  call    cs:__imp_WriteRefTraceLog
0x18000f46e  test    ebx, ebx
0x18000f470  jnz     short loc_18000F4E2
0x18000f472  mov     rbx, [rdi+20h]
0x18000f476  mov     rcx, rdi; this
0x18000f479  call    ??1ISAPI_REQUEST@@AEAA@XZ; ISAPI_REQUEST::~ISAPI_REQUEST(void)
0x18000f47e  mov     rcx, [rbx+8]
0x18000f482  mov     qword ptr [rbx+10h], 0
0x18000f48a  mov     rax, [rcx]
0x18000f48d  mov     rax, [rax+110h]
0x18000f494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f499  xor     edx, edx; unsigned int
0x18000f49b  mov     rcx, rax; struct IHttpTraceContext *
0x18000f49e  call    ?CheckTracingEnabled@WWWIsapiExtensionTraceProvider@@SAHPEAVIHttpTraceContext@@K@Z; WWWIsapiExtensionTraceProvider::CheckTracingEnabled(IHttpTraceContext *,ulong)
0x18000f4a3  test    eax, eax
0x18000f4a5  jz      short loc_18000F4C2
0x18000f4a7  mov     rcx, [rbx+8]
0x18000f4ab  mov     rax, [rcx]
0x18000f4ae  mov     rax, [rax+110h]
0x18000f4b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4ba  mov     rcx, rax; struct IHttpTraceContext *
0x18000f4bd  call    ?RaiseEvent@ISAPI_EXTENSION_DONE@W3IsapiEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z; W3IsapiEvents::ISAPI_EXTENSION_DONE::RaiseEvent(IHttpTraceContext *,_GUID const *)
0x18000f4c2  cmp     dword ptr [rbx+28h], 2
0x18000f4c6  jnz     short loc_18000F4E2
0x18000f4c8  mov     rcx, rbx; this
0x18000f4cb  call    ?SetRequestHandledAndTrace@W3_ISAPI_HANDLER@@AEAAJXZ; W3_ISAPI_HANDLER::SetRequestHandledAndTrace(void)
0x18000f4d0  mov     rcx, [rbx+8]
0x18000f4d4  xor     edx, edx
0x18000f4d6  mov     rax, [rcx]
0x18000f4d9  mov     rax, [rax+40h]
0x18000f4dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4e2  mov     rbx, [rsp+28h+arg_0]
0x18000f4e7  add     rsp, 20h
0x18000f4eb  pop     rdi
0x18000f4ec  retn
```
