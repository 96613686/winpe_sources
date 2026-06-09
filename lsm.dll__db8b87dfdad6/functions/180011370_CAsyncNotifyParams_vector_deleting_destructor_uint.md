# CAsyncNotifyParams::`vector deleting destructor'(uint)

- ea: `0x180011370`
- end: `0x180011486`
- name: `??_ECAsyncNotifyParams@@UEAAPEAXI@Z`
- size: `278`
- prototype: `CAsyncNotifyParams *__fastcall(CAsyncNotifyParams *this, char)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800074c0`
- `0x180010fb0`
- `0x180011370`
- `0x18004b830`
- `0x180097010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180011439`
- `ntdll!RtlReleaseResource` at `0x180011439`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800113bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800113bb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800113a1`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800113a1`

## string_xrefs

- `0x180011469`: `RpcAsyncCompleteCall returned: 0x%x`

## pseudocode

```c
CAsyncNotifyParams *__fastcall CAsyncNotifyParams::`vector deleting destructor'(CAsyncNotifyParams *this, char a2)
{
  struct _RPC_ASYNC_STATE *v4; // rcx
  RPC_STATUS v5; // eax
  void *v6; // rcx
  __int64 v7; // rcx
  char *v8; // rdi
  __int64 v9; // rcx
  char **v10; // rax
  PRTL_RESOURCE Resource; // [rsp+20h] [rbp-18h] BYREF
  int v13; // [rsp+28h] [rbp-10h]

  *(_QWORD *)this = &CAsyncNotifyParams::`vftable';
  v4 = (struct _RPC_ASYNC_STATE *)*((_QWORD *)this + 199);
  if ( v4 )
  {
    v5 = RpcAsyncCompleteCall(v4, (char *)this + 1616);
    if ( v5 )
      _DbgPrintMessage(4, "RpcAsyncCompleteCall returned: 0x%x", v5);
  }
  v6 = (void *)*((_QWORD *)this + 204);
  if ( v6 )
    CloseHandle(v6);
  v7 = *((_QWORD *)this + 203);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  *(_QWORD *)this = &CTSPrivateObject<IPublicNotificationCallback>::`vftable';
  if ( g_pObjectTracker )
  {
    v8 = (char *)this + 1576;
    CAutoExclusiveLock::CAutoExclusiveLock(
      (CAutoExclusiveLock *)&Resource,
      (struct CResource *)((char *)g_pObjectTracker + 24));
    v9 = *((_QWORD *)this + 197);
    if ( *(char **)(*(_QWORD *)v8 + 8LL) != v8 || (v10 = (char **)*((_QWORD *)this + 198), *v10 != v8) )
      __fastfail(3u);
    *v10 = (char *)v9;
    *(_QWORD *)(v9 + 8) = v10;
    if ( v13 )
    {
      v13 = 0;
      if ( LODWORD(Resource[1].Lock.DebugInfo) )
        RtlReleaseResource(Resource);
    }
  }
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x670);
  return this;
}

```

## disassembly

```asm
0x180011370  mov     [rsp+arg_0], rbx
0x180011375  mov     [rsp+arg_8], rsi
0x18001137a  push    rdi
0x18001137b  sub     rsp, 30h
0x18001137f  mov     esi, edx
0x180011381  mov     rbx, rcx
0x180011384  lea     rax, ??_7CAsyncNotifyParams@@6B@; const CAsyncNotifyParams::`vftable'
0x18001138b  mov     [rcx], rax
0x18001138e  mov     rcx, [rcx+638h]; pAsync
0x180011395  test    rcx, rcx
0x180011398  jz      short loc_1800113AF
0x18001139a  lea     rdx, [rbx+650h]; Reply
0x1800113a1  call    cs:__imp_RpcAsyncCompleteCall
0x1800113a7  test    eax, eax
0x1800113a9  jnz     loc_180011466
0x1800113af  mov     rcx, [rbx+660h]; hObject
0x1800113b6  test    rcx, rcx
0x1800113b9  jz      short loc_1800113C2
0x1800113bb  call    cs:__imp_CloseHandle
0x1800113c1  nop
0x1800113c2  mov     rcx, [rbx+658h]
0x1800113c9  test    rcx, rcx
0x1800113cc  jz      short loc_1800113DB
0x1800113ce  mov     rax, [rcx]
0x1800113d1  mov     rax, [rax+10h]
0x1800113d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113da  nop
0x1800113db  lea     rax, ??_7?$CTSPrivateObject@VIPublicNotificationCallback@@@@6B@; const CTSPrivateObject<IPublicNotificationCallback>::`vftable'
0x1800113e2  mov     [rbx], rax
0x1800113e5  mov     rdx, cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA; CObjectTracker * g_pObjectTracker
0x1800113ec  test    rdx, rdx
0x1800113ef  jz      short loc_180011440
0x1800113f1  lea     rdi, [rbx+628h]
0x1800113f8  add     rdx, 18h; struct CResource *
0x1800113fc  lea     rcx, [rsp+38h+Resource]; this
0x180011401  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x180011406  mov     rcx, [rdi]
0x180011409  cmp     [rcx+8], rdi
0x18001140d  jnz     short loc_18001147F
0x18001140f  mov     rax, [rdi+8]
0x180011413  cmp     [rax], rdi
0x180011416  jnz     short loc_18001147F
0x180011418  mov     [rax], rcx
0x18001141b  mov     [rcx+8], rax
0x18001141f  cmp     [rsp+38h+var_10], 0
0x180011424  jz      short loc_180011440
0x180011426  mov     [rsp+38h+var_10], 0
0x18001142e  mov     rcx, [rsp+38h+Resource]; Resource
0x180011433  cmp     dword ptr [rcx+60h], 0
0x180011437  jz      short loc_180011440
0x180011439  call    cs:__imp_RtlReleaseResource
0x18001143f  nop
0x180011440  test    sil, 1
0x180011444  jz      short loc_180011453
0x180011446  mov     edx, 670h; struct std::nothrow_t *
0x18001144b  mov     rcx, rbx; void *
0x18001144e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011453  mov     rax, rbx
0x180011456  mov     rbx, [rsp+38h+arg_0]
0x18001145b  mov     rsi, [rsp+38h+arg_8]
0x180011460  add     rsp, 30h
0x180011464  pop     rdi
0x180011465  retn
0x180011466  mov     r8d, eax
0x180011469  lea     rdx, aRpcasynccomple; "RpcAsyncCompleteCall returned: 0x%x"
0x180011470  mov     ecx, 4; int
0x180011475  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001147a  jmp     loc_1800113AF
0x18001147f  mov     ecx, 3
0x180011484  int     29h; Win8: RtlFailFast(ecx)
```
