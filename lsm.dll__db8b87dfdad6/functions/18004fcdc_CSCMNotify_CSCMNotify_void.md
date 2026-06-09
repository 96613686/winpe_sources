# CSCMNotify::~CSCMNotify(void)

- ea: `0x18004fcdc`
- end: `0x18004fdd8`
- name: `??1CSCMNotify@@UEAA@XZ`
- size: `252`
- prototype: `void __fastcall(CSCMNotify *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18004ffc0`

## callees

- `0x180010f20`
- `0x180010fb0`
- `0x18001ce00`
- `0x18004b830`
- `0x18004fcdc`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x18004fda4`
- `ntdll!RtlDeleteResource` at `0x18004fda4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18004fd09`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18004fd09`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18004fd16`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18004fd16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fd33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fd33`

## pseudocode

```c
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
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v7, (struct _RTL_RESOURCE *)((char *)this + 1592));
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
0x18004fcdc  mov     [rsp+arg_0], rbx
0x18004fce1  mov     [rsp+arg_8], rsi
0x18004fce6  push    rdi
0x18004fce7  sub     rsp, 30h
0x18004fceb  mov     rbx, rcx
0x18004fcee  lea     rax, ??_7CSCMNotify@@6B@; const CSCMNotify::`vftable'
0x18004fcf5  mov     [rcx], rax
0x18004fcf8  mov     rcx, [rcx+6B8h]; pwa
0x18004fcff  test    rcx, rcx
0x18004fd02  jz      short loc_18004FD27
0x18004fd04  mov     edx, 1; fCancelPendingCallbacks
0x18004fd09  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18004fd0f  mov     rcx, [rbx+6B8h]; pwa
0x18004fd16  call    cs:__imp_CloseThreadpoolWait
0x18004fd1c  mov     qword ptr [rbx+6B8h], 0
0x18004fd27  mov     rcx, [rbx+6B0h]; hObject
0x18004fd2e  test    rcx, rcx
0x18004fd31  jz      short loc_18004FD44
0x18004fd33  call    cs:__imp_CloseHandle
0x18004fd39  mov     qword ptr [rbx+6B0h], 0
0x18004fd44  lea     rsi, [rbx+638h]
0x18004fd4b  mov     rdx, rsi; struct CResource *
0x18004fd4e  lea     rcx, [rsp+38h+var_18]; this
0x18004fd53  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x18004fd58  lea     rdi, [rbx+6A0h]
0x18004fd5f  mov     rcx, [rdi]; void *
0x18004fd62  cmp     rcx, rdi
0x18004fd65  jz      short loc_18004FD90
0x18004fd67  cmp     [rcx+8], rdi
0x18004fd6b  jnz     short loc_18004FD89
0x18004fd6d  mov     rax, [rcx]
0x18004fd70  cmp     [rax+8], rcx
0x18004fd74  jnz     short loc_18004FD89
0x18004fd76  mov     [rdi], rax
0x18004fd79  mov     [rax+8], rdi
0x18004fd7d  mov     edx, 18h; struct std::nothrow_t *
0x18004fd82  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004fd87  jmp     short loc_18004FD5F
0x18004fd89  mov     ecx, 3
0x18004fd8e  int     29h; Win8: RtlFailFast(ecx)
0x18004fd90  lea     rcx, [rsp+38h+var_18]; this
0x18004fd95  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18004fd9a  nop
0x18004fd9b  cmp     dword ptr [rsi+60h], 0
0x18004fd9f  jz      short loc_18004FDAA
0x18004fda1  mov     rcx, rsi; Resource
0x18004fda4  call    cs:__imp_RtlDeleteResource
0x18004fdaa  mov     dword ptr [rsi+60h], 0
0x18004fdb1  lea     rax, ??_7?$CTSPrivateObject@UITSNotifySink@@@@6B@; const CTSPrivateObject<ITSNotifySink>::`vftable'
0x18004fdb8  mov     [rbx], rax
0x18004fdbb  lea     rcx, [rbx+628h]; struct _LIST_ENTRY *
0x18004fdc2  call    ?RemoveTrackingObject@@YAXPEAU_LIST_ENTRY@@@Z; RemoveTrackingObject(_LIST_ENTRY *)
0x18004fdc7  nop
0x18004fdc8  mov     rbx, [rsp+38h+arg_0]
0x18004fdcd  mov     rsi, [rsp+38h+arg_8]
0x18004fdd2  add     rsp, 30h
0x18004fdd6  pop     rdi
0x18004fdd7  retn
```
