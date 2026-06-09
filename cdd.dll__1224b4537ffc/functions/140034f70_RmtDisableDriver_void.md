# RmtDisableDriver(void)

- ea: `0x140034f70`
- end: `0x1400350d4`
- name: `?RmtDisableDriver@@YAXXZ`
- size: `356`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140036b30`

## callees

- `0x14002bf08`
- `0x14003443c`
- `0x140034f70`
- `0x1400372d0`

## import_xrefs

- `ntoskrnl!ZwSetSystemInformation` at `0x140035016`
- `ntoskrnl!ZwSetSystemInformation` at `0x140035016`
- `WIN32K!W32GetSessionState` at `0x140034f76`
- `WIN32K!W32GetSessionState` at `0x140034f90`
- `WIN32K!W32GetSessionState` at `0x140034fac`
- `WIN32K!W32GetSessionState` at `0x140034fc3`
- `WIN32K!W32GetSessionState` at `0x140034fdc`
- `WIN32K!W32GetSessionState` at `0x140034ff6`
- `WIN32K!W32GetSessionState` at `0x140035022`
- `WIN32K!W32GetSessionState` at `0x14003503d`
- `WIN32K!W32GetSessionState` at `0x140035070`
- `WIN32K!W32GetSessionState` at `0x14003508b`
- `WIN32K!W32GetSessionState` at `0x1400350a5`
- `WIN32K!W32GetSessionState` at `0x140034f76`
- `WIN32K!W32GetSessionState` at `0x140034f90`
- `WIN32K!W32GetSessionState` at `0x140034fac`
- `WIN32K!W32GetSessionState` at `0x140034fc3`
- `WIN32K!W32GetSessionState` at `0x140034fdc`
- `WIN32K!W32GetSessionState` at `0x140034ff6`
- `WIN32K!W32GetSessionState` at `0x140035022`
- `WIN32K!W32GetSessionState` at `0x14003503d`
- `WIN32K!W32GetSessionState` at `0x140035070`
- `WIN32K!W32GetSessionState` at `0x14003508b`
- `WIN32K!W32GetSessionState` at `0x1400350a5`
- `WIN32K!EngDeleteSemaphore` at `0x1400350bc`
- `WIN32K!EngDeleteSemaphore` at `0x1400350bc`
- `WIN32K!EngFreeMem` at `0x140035064`
- `WIN32K!EngFreeMem` at `0x140035064`

## pseudocode

```c
void __fastcall RmtDisableDriver(__int64 a1, __int64 a2)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 SessionState; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  void *v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rax

  v3 = *(_QWORD *)(W32GetSessionState(a1, a2) + 72);
  if ( *(_QWORD *)(v3 + 904) )
  {
    SessionState = W32GetSessionState(v3, v2);
    (*(void (**)(void))(*(_QWORD *)(SessionState + 72) + 904LL))();
  }
  v6 = *(_QWORD *)(W32GetSessionState(v3, v2) + 72);
  if ( *(_QWORD *)(v6 + 72) )
  {
    v7 = W32GetSessionState(v6, v5);
    (*(void (**)(void))(*(_QWORD *)(v7 + 72) + 72LL))();
  }
  v9 = *(_QWORD *)(W32GetSessionState(v6, v5) + 72);
  if ( *(_QWORD *)(v9 + 3360) )
  {
    v10 = W32GetSessionState(v9, v8);
    ZwSetSystemInformation(SystemUnloadGdiDriverInformation, (PVOID)(*(_QWORD *)(v10 + 72) + 3360LL), 8u);
    v9 = *(_QWORD *)(W32GetSessionState(v12, v11) + 72);
    *(_QWORD *)(v9 + 3360) = 0;
  }
  v14 = *(_QWORD *)(W32GetSessionState(v9, v8) + 72);
  v15 = *(void **)(v14 + 3352);
  if ( v15 )
  {
    RemotePDevMgr::~RemotePDevMgr(*(RemotePDevMgr **)(v14 + 3352));
    EngFreeMem(v15);
  }
  v16 = *(_QWORD *)(W32GetSessionState(v14, v13) + 72);
  *(_QWORD *)(v16 + 3352) = 0;
  v19 = *(_QWORD *)(W32GetSessionState(v16, v17) + 72);
  if ( *(_QWORD *)(v19 + 3344) )
  {
    v20 = W32GetSessionState(v19, v18);
    EngDeleteSemaphore(*(HSEMAPHORE *)(*(_QWORD *)(v20 + 72) + 3344LL));
  }
  CddSessionDataAccessor<CddSessionData>::RemoveSessionReference();
}

```

## disassembly

```asm
0x140034f70  push    rbx
0x140034f72  sub     rsp, 20h
0x140034f76  call    cs:__imp_W32GetSessionState
0x140034f7d  nop     dword ptr [rax+rax+00h]
0x140034f82  mov     rcx, [rax+48h]
0x140034f86  cmp     qword ptr [rcx+388h], 0
0x140034f8e  jz      short loc_140034FAC
0x140034f90  call    cs:__imp_W32GetSessionState
0x140034f97  nop     dword ptr [rax+rax+00h]
0x140034f9c  mov     rcx, [rax+48h]
0x140034fa0  mov     rax, [rcx+388h]
0x140034fa7  call    _guard_dispatch_icall
0x140034fac  call    cs:__imp_W32GetSessionState
0x140034fb3  nop     dword ptr [rax+rax+00h]
0x140034fb8  mov     rcx, [rax+48h]
0x140034fbc  cmp     qword ptr [rcx+48h], 0
0x140034fc1  jz      short loc_140034FDC
0x140034fc3  call    cs:__imp_W32GetSessionState
0x140034fca  nop     dword ptr [rax+rax+00h]
0x140034fcf  mov     rcx, [rax+48h]
0x140034fd3  mov     rax, [rcx+48h]
0x140034fd7  call    _guard_dispatch_icall
0x140034fdc  call    cs:__imp_W32GetSessionState
0x140034fe3  nop     dword ptr [rax+rax+00h]
0x140034fe8  mov     rcx, [rax+48h]
0x140034fec  cmp     qword ptr [rcx+0D20h], 0
0x140034ff4  jz      short loc_14003503D
0x140034ff6  call    cs:__imp_W32GetSessionState
0x140034ffd  nop     dword ptr [rax+rax+00h]
0x140035002  mov     ecx, 1Bh; SystemInformationClass
0x140035007  mov     rdx, [rax+48h]
0x14003500b  add     rdx, 0D20h; SystemInformation
0x140035012  lea     r8d, [rcx-13h]; SystemInformationLength
0x140035016  call    cs:__imp_ZwSetSystemInformation
0x14003501d  nop     dword ptr [rax+rax+00h]
0x140035022  call    cs:__imp_W32GetSessionState
0x140035029  nop     dword ptr [rax+rax+00h]
0x14003502e  mov     rcx, [rax+48h]
0x140035032  mov     qword ptr [rcx+0D20h], 0
0x14003503d  call    cs:__imp_W32GetSessionState
0x140035044  nop     dword ptr [rax+rax+00h]
0x140035049  mov     rcx, [rax+48h]
0x14003504d  mov     rbx, [rcx+0D18h]
0x140035054  test    rbx, rbx
0x140035057  jz      short loc_140035070
0x140035059  mov     rcx, rbx; this
0x14003505c  call    ??1RemotePDevMgr@@QEAA@XZ; RemotePDevMgr::~RemotePDevMgr(void)
0x140035061  mov     rcx, rbx; pv
0x140035064  call    cs:__imp_EngFreeMem
0x14003506b  nop     dword ptr [rax+rax+00h]
0x140035070  call    cs:__imp_W32GetSessionState
0x140035077  nop     dword ptr [rax+rax+00h]
0x14003507c  mov     rcx, [rax+48h]
0x140035080  mov     qword ptr [rcx+0D18h], 0
0x14003508b  call    cs:__imp_W32GetSessionState
0x140035092  nop     dword ptr [rax+rax+00h]
0x140035097  mov     rcx, [rax+48h]
0x14003509b  cmp     qword ptr [rcx+0D10h], 0
0x1400350a3  jz      short loc_1400350C8
0x1400350a5  call    cs:__imp_W32GetSessionState
0x1400350ac  nop     dword ptr [rax+rax+00h]
0x1400350b1  mov     rcx, [rax+48h]
0x1400350b5  mov     rcx, [rcx+0D10h]; hsem
0x1400350bc  call    cs:__imp_EngDeleteSemaphore
0x1400350c3  nop     dword ptr [rax+rax+00h]
0x1400350c8  call    ?RemoveSessionReference@?$CddSessionDataAccessor@UCddSessionData@@@@QEAAXXZ; CddSessionDataAccessor<CddSessionData>::RemoveSessionReference(void)
0x1400350cd  add     rsp, 20h
0x1400350d1  pop     rbx
0x1400350d2  retn
```
