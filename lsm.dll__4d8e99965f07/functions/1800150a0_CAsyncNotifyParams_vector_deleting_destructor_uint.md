# CAsyncNotifyParams::`vector deleting destructor'(uint)

- ea: `0x1800150a0`
- end: `0x1800151c9`
- name: `??_ECAsyncNotifyParams@@UEAAPEAXI@Z`
- size: `297`
- prototype: `void *__fastcall(CAsyncNotifyParams *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800077a0`
- `0x180014b20`
- `0x1800150a0`
- `0x18004ec20`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180015175`
- `ntdll!RtlReleaseResource` at `0x180015175`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800150f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800150f1`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800150d1`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800150d1`

## string_xrefs

- `0x1800151ac`: `RpcAsyncCompleteCall returned: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x1800150a0  mov     [rsp+arg_0], rbx
0x1800150a5  mov     [rsp+arg_8], rsi
0x1800150aa  push    rdi
0x1800150ab  sub     rsp, 30h
0x1800150af  mov     esi, edx
0x1800150b1  mov     rbx, rcx
0x1800150b4  lea     rax, ??_7CAsyncNotifyParams@@6B@; const CAsyncNotifyParams::`vftable'
0x1800150bb  mov     [rcx], rax
0x1800150be  mov     rcx, [rcx+638h]; pAsync
0x1800150c5  test    rcx, rcx
0x1800150c8  jz      short loc_1800150E5
0x1800150ca  lea     rdx, [rbx+650h]; Reply
0x1800150d1  call    cs:__imp_RpcAsyncCompleteCall
0x1800150d8  nop     dword ptr [rax+rax+00h]
0x1800150dd  test    eax, eax
0x1800150df  jnz     loc_1800151A9
0x1800150e5  mov     rcx, [rbx+660h]; hObject
0x1800150ec  test    rcx, rcx
0x1800150ef  jz      short loc_1800150FE
0x1800150f1  call    cs:__imp_CloseHandle
0x1800150f8  nop     dword ptr [rax+rax+00h]
0x1800150fd  nop
0x1800150fe  mov     rcx, [rbx+658h]
0x180015105  test    rcx, rcx
0x180015108  jz      short loc_180015117
0x18001510a  mov     rax, [rcx]
0x18001510d  mov     rax, [rax+10h]
0x180015111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015116  nop
0x180015117  lea     rax, ??_7?$CTSPrivateObject@VIPublicNotificationCallback@@@@6B@; const CTSPrivateObject<IPublicNotificationCallback>::`vftable'
0x18001511e  mov     [rbx], rax
0x180015121  mov     rdx, cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA; CObjectTracker * g_pObjectTracker
0x180015128  test    rdx, rdx
0x18001512b  jz      short loc_180015182
0x18001512d  lea     rdi, [rbx+628h]
0x180015134  add     rdx, 18h; struct CResource *
0x180015138  lea     rcx, [rsp+38h+Resource]; this
0x18001513d  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x180015142  mov     rcx, [rdi]
0x180015145  cmp     [rcx+8], rdi
0x180015149  jnz     short loc_1800151C2
0x18001514b  mov     rax, [rdi+8]
0x18001514f  cmp     [rax], rdi
0x180015152  jnz     short loc_1800151C2
0x180015154  mov     [rax], rcx
0x180015157  mov     [rcx+8], rax
0x18001515b  cmp     [rsp+38h+var_10], 0
0x180015160  jz      short loc_180015182
0x180015162  mov     [rsp+38h+var_10], 0
0x18001516a  mov     rcx, [rsp+38h+Resource]; Resource
0x18001516f  cmp     dword ptr [rcx+60h], 0
0x180015173  jz      short loc_180015182
0x180015175  call    cs:__imp_RtlReleaseResource
0x18001517c  nop     dword ptr [rax+rax+00h]
0x180015181  nop
0x180015182  test    sil, 1
0x180015186  jz      short loc_180015195
0x180015188  mov     edx, 670h; struct std::nothrow_t *
0x18001518d  mov     rcx, rbx; void *
0x180015190  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015195  mov     rax, rbx
0x180015198  mov     rbx, [rsp+38h+arg_0]
0x18001519d  mov     rsi, [rsp+38h+arg_8]
0x1800151a2  add     rsp, 30h
0x1800151a6  pop     rdi
0x1800151a7  retn
0x1800151a9  mov     r8d, eax
0x1800151ac  lea     rdx, aRpcasynccomple; "RpcAsyncCompleteCall returned: 0x%x"
0x1800151b3  mov     ecx, 4; int
0x1800151b8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800151bd  jmp     loc_1800150E5
0x1800151c2  mov     ecx, 3
0x1800151c7  int     29h; Win8: RtlFailFast(ecx)
```
