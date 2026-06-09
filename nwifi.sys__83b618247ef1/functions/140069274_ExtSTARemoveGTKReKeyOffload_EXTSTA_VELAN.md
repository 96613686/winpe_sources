# ExtSTARemoveGTKReKeyOffload(EXTSTA_VELAN *)

- ea: `0x140069274`
- end: `0x1400693f3`
- name: `?ExtSTARemoveGTKReKeyOffload@@YAHPEAUEXTSTA_VELAN@@@Z`
- size: `383`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140061680`
- `0x140068fb4`
- `0x1400697c4`

## callees

- `0x14000d22c`
- `0x140019bbc`
- `0x140020dc0`
- `0x140020f20`
- `0x140069274`
- `0x1400693fc`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140069371`
- `ntoskrnl!KeGetCurrentIrql` at `0x140069371`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400692a3`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400692a3`
- `NDIS!NdisReleaseRWLock` at `0x1400692f5`
- `NDIS!NdisReleaseRWLock` at `0x140069338`
- `NDIS!NdisReleaseRWLock` at `0x1400692f5`
- `NDIS!NdisReleaseRWLock` at `0x140069338`

## pseudocode

```c
__int64 __fastcall ExtSTARemoveGTKReKeyOffload(struct EXTSTA_VELAN *a1)
{
  _VELAN *pGenVElan; // rcx
  int Rw; // ecx
  _VELAN *v5; // rcx
  unsigned int v6; // eax
  unsigned int v7; // ebx
  struct _LOCK_STATE_EX LockState; // [rsp+40h] [rbp+8h] BYREF
  unsigned int uRsnReKeyProtocolId; // [rsp+48h] [rbp+10h] BYREF

  LockState.OldIrql = 0;
  pGenVElan = a1->pGenVElan;
  *(_WORD *)&LockState.LockState = 0;
  NdisAcquireRWLockWrite(pGenVElan->pRWLock, &LockState, 0);
  Rw = (int)a1->Rw;
  if ( (Rw & 8) != 0 )
  {
    uRsnReKeyProtocolId = a1->Rw.uRsnReKeyProtocolId;
    *(_DWORD *)&a1->Rw = Rw & 0xFFFFFFF7;
    v5 = a1->pGenVElan;
    a1->Rw.uRsnReKeyProtocolId = 0;
    NdisReleaseRWLock(v5->pRWLock, &LockState);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        41,
        WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids,
        uRsnReKeyProtocolId);
    if ( KeGetCurrentIrql() )
    {
      return (unsigned int)ExtSTARequestAsyncRemoveGTKReKeyOffload(a1, uRsnReKeyProtocolId);
    }
    else
    {
      v6 = PtRequestAdapterSync(a1->pGenVElan->pAdapt, 1u, 0xFD01010F, &uRsnReKeyProtocolId, 4u);
      v7 = v6;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          42,
          WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids,
          uRsnReKeyProtocolId,
          v6);
    }
    return v7;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids);
    NdisReleaseRWLock(a1->pGenVElan->pRWLock, &LockState);
    return 0;
  }
}

```

## disassembly

```asm
0x140069274  mov     [rsp+arg_10], rbx
0x140069279  push    rdi
0x14006927a  sub     rsp, 30h
0x14006927e  mov     rbx, rcx
0x140069281  mov     [rsp+38h+LockState.OldIrql], 0
0x140069286  mov     rcx, [rcx+0A38h]
0x14006928d  lea     rdx, [rsp+38h+LockState]; LockState
0x140069292  xor     eax, eax
0x140069294  xor     r8d, r8d; Flags
0x140069297  mov     word ptr [rsp+38h+LockState.LockState], ax
0x14006929c  mov     rcx, [rcx+90h]; Lock
0x1400692a3  call    cs:__imp_NdisAcquireRWLockWrite
0x1400692aa  nop     dword ptr [rax+rax+00h]
0x1400692af  mov     ecx, [rbx+6B8h]
0x1400692b5  test    cl, 8
0x1400692b8  jnz     short loc_140069308
0x1400692ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400692c1  lea     rdi, WPP_GLOBAL_Control
0x1400692c8  cmp     rcx, rdi
0x1400692cb  jz      short loc_1400692E2
0x1400692cd  mov     rcx, [rcx+18h]
0x1400692d1  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x1400692d8  mov     edx, 28h ; '('
0x1400692dd  call    WPP_SF_
0x1400692e2  mov     rcx, [rbx+0A38h]
0x1400692e9  lea     rdx, [rsp+38h+LockState]; LockState
0x1400692ee  mov     rcx, [rcx+90h]; Lock
0x1400692f5  call    cs:__imp_NdisReleaseRWLock
0x1400692fc  nop     dword ptr [rax+rax+00h]
0x140069301  xor     eax, eax
0x140069303  jmp     loc_1400693E7
0x140069308  mov     eax, [rbx+714h]
0x14006930e  lea     rdx, [rsp+38h+LockState]; LockState
0x140069313  and     ecx, 0FFFFFFF7h
0x140069316  mov     [rsp+38h+arg_8], eax
0x14006931a  mov     [rbx+6B8h], ecx
0x140069320  mov     rcx, [rbx+0A38h]
0x140069327  mov     dword ptr [rbx+714h], 0
0x140069331  mov     rcx, [rcx+90h]; Lock
0x140069338  call    cs:__imp_NdisReleaseRWLock
0x14006933f  nop     dword ptr [rax+rax+00h]
0x140069344  mov     rcx, cs:WPP_GLOBAL_Control
0x14006934b  lea     rdi, WPP_GLOBAL_Control
0x140069352  cmp     rcx, rdi
0x140069355  jz      short loc_140069371
0x140069357  mov     r9d, [rsp+38h+arg_8]
0x14006935c  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x140069363  mov     rcx, [rcx+18h]
0x140069367  mov     edx, 29h ; ')'
0x14006936c  call    WPP_SF_d
0x140069371  call    cs:__imp_KeGetCurrentIrql
0x140069378  nop     dword ptr [rax+rax+00h]
0x14006937d  test    al, al
0x14006937f  jnz     short loc_1400693D7
0x140069381  mov     rcx, [rbx+0A38h]
0x140069388  lea     r9, [rsp+38h+arg_8]; void *
0x14006938d  mov     edx, 1; unsigned int
0x140069392  mov     [rsp+38h+var_18], 4; unsigned int
0x14006939a  mov     r8d, 0FD01010Fh; unsigned int
0x1400693a0  mov     rcx, [rcx+10h]; struct _ADAPT *
0x1400693a4  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x1400693a9  mov     ebx, eax
0x1400693ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400693b2  cmp     rcx, rdi
0x1400693b5  jz      short loc_1400693E5
0x1400693b7  mov     r9d, [rsp+38h+arg_8]
0x1400693bc  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x1400693c3  mov     rcx, [rcx+18h]
0x1400693c7  mov     edx, 2Ah ; '*'
0x1400693cc  mov     [rsp+38h+var_18], eax
0x1400693d0  call    WPP_SF_Dd
0x1400693d5  jmp     short loc_1400693E5
0x1400693d7  mov     edx, [rsp+38h+arg_8]; unsigned int
0x1400693db  mov     rcx, rbx; struct EXTSTA_VELAN *
0x1400693de  call    ?ExtSTARequestAsyncRemoveGTKReKeyOffload@@YAHPEAUEXTSTA_VELAN@@K@Z; ExtSTARequestAsyncRemoveGTKReKeyOffload(EXTSTA_VELAN *,ulong)
0x1400693e3  mov     ebx, eax
0x1400693e5  mov     eax, ebx
0x1400693e7  mov     rbx, [rsp+38h+arg_10]
0x1400693ec  add     rsp, 30h
0x1400693f0  pop     rdi
0x1400693f1  retn
```
