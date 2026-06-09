# CSCMNotify::~CSCMNotify(void)

- ea: `0x1800532d0`
- end: `0x1800533e5`
- name: `??1CSCMNotify@@UEAA@XZ`
- size: `277`
- prototype: `void __fastcall(CSCMNotify *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x1800535e0`

## callees

- `0x1800129d0`
- `0x180014a80`
- `0x180014b20`
- `0x18004ec20`
- `0x1800532d0`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x1800533aa`
- `ntdll!RtlDeleteResource` at `0x1800533aa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800532fd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800532fd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180053310`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180053310`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053333`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053333`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSCMNotify::~CSCMNotify(CSCMNotify *this)
{
  struct _TP_WAIT *v2; // rcx
  void *v3; // rcx
  _QWORD **v4; // rdi
  _QWORD *v5; // rcx
  _QWORD *v6; // rax
  _BYTE v7[24]; // [rsp+20h] [rbp-18h] BYREF

  *(_QWORD *)this = &CSCMNotify::`vftable';
  v2 = (struct _TP_WAIT *)*((_QWORD *)this + 215);
  if ( v2 )
  {
    WaitForThreadpoolWaitCallbacks(v2, 1);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 215));
    *((_QWORD *)this + 215) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 214);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 214) = 0;
  }
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v7, (CSCMNotify *)((char *)this + 1592));
  v4 = (_QWORD **)((char *)this + 1696);
  while ( 1 )
  {
    v5 = *v4;
    if ( *v4 == v4 )
      break;
    if ( (_QWORD **)v5[1] != v4 || (v6 = (_QWORD *)*v5, *(_QWORD **)(*v5 + 8LL) != v5) )
      __fastfail(3u);
    *v4 = v6;
    v6[1] = v4;
    operator delete(v5, (const struct std::nothrow_t *)0x18);
  }
  CAutoLock::Unlock((CAutoLock *)v7);
  if ( *((_DWORD *)this + 422) )
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 1592));
  *((_DWORD *)this + 422) = 0;
  *(_QWORD *)this = &CTSPrivateObject<ITSNotifySink>::`vftable';
  RemoveTrackingObject((struct _LIST_ENTRY *)((char *)this + 1576));
}

```

## disassembly

```asm
0x1800532d0  mov     [rsp+arg_0], rbx
0x1800532d5  mov     [rsp+arg_8], rsi
0x1800532da  push    rdi
0x1800532db  sub     rsp, 30h
0x1800532df  mov     rbx, rcx
0x1800532e2  lea     rax, ??_7CSCMNotify@@6B@; const CSCMNotify::`vftable'
0x1800532e9  mov     [rcx], rax
0x1800532ec  mov     rcx, [rcx+6B8h]; pwa
0x1800532f3  test    rcx, rcx
0x1800532f6  jz      short loc_180053327
0x1800532f8  mov     edx, 1; fCancelPendingCallbacks
0x1800532fd  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180053304  nop     dword ptr [rax+rax+00h]
0x180053309  mov     rcx, [rbx+6B8h]; pwa
0x180053310  call    cs:__imp_CloseThreadpoolWait
0x180053317  nop     dword ptr [rax+rax+00h]
0x18005331c  mov     qword ptr [rbx+6B8h], 0
0x180053327  mov     rcx, [rbx+6B0h]; hObject
0x18005332e  test    rcx, rcx
0x180053331  jz      short loc_18005334A
0x180053333  call    cs:__imp_CloseHandle
0x18005333a  nop     dword ptr [rax+rax+00h]
0x18005333f  mov     qword ptr [rbx+6B0h], 0
0x18005334a  lea     rsi, [rbx+638h]
0x180053351  mov     rdx, rsi; struct CResource *
0x180053354  lea     rcx, [rsp+38h+var_18]; this
0x180053359  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x18005335e  lea     rdi, [rbx+6A0h]
0x180053365  mov     rcx, [rdi]; void *
0x180053368  cmp     rcx, rdi
0x18005336b  jz      short loc_180053396
0x18005336d  cmp     [rcx+8], rdi
0x180053371  jnz     short loc_18005338F
0x180053373  mov     rax, [rcx]
0x180053376  cmp     [rax+8], rcx
0x18005337a  jnz     short loc_18005338F
0x18005337c  mov     [rdi], rax
0x18005337f  mov     [rax+8], rdi
0x180053383  mov     edx, 18h; struct std::nothrow_t *
0x180053388  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005338d  jmp     short loc_180053365
0x18005338f  mov     ecx, 3
0x180053394  int     29h; Win8: RtlFailFast(ecx)
0x180053396  lea     rcx, [rsp+38h+var_18]; this
0x18005339b  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800533a0  nop
0x1800533a1  cmp     dword ptr [rsi+60h], 0
0x1800533a5  jz      short loc_1800533B6
0x1800533a7  mov     rcx, rsi; Resource
0x1800533aa  call    cs:__imp_RtlDeleteResource
0x1800533b1  nop     dword ptr [rax+rax+00h]
0x1800533b6  mov     dword ptr [rsi+60h], 0
0x1800533bd  lea     rax, ??_7?$CTSPrivateObject@UITSNotifySink@@@@6B@; const CTSPrivateObject<ITSNotifySink>::`vftable'
0x1800533c4  mov     [rbx], rax
0x1800533c7  lea     rcx, [rbx+628h]; struct _LIST_ENTRY *
0x1800533ce  call    ?RemoveTrackingObject@@YAXPEAU_LIST_ENTRY@@@Z; RemoveTrackingObject(_LIST_ENTRY *)
0x1800533d3  nop
0x1800533d4  mov     rbx, [rsp+38h+arg_0]
0x1800533d9  mov     rsi, [rsp+38h+arg_8]
0x1800533de  add     rsp, 30h
0x1800533e2  pop     rdi
0x1800533e3  retn
```
