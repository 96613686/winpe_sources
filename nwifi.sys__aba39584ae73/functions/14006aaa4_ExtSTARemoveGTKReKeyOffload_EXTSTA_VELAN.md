# ExtSTARemoveGTKReKeyOffload(EXTSTA_VELAN *)

- ea: `0x14006aaa4`
- end: `0x14006ac23`
- name: `?ExtSTARemoveGTKReKeyOffload@@YAHPEAUEXTSTA_VELAN@@@Z`
- size: `383`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140062eb0`
- `0x14006a7e4`
- `0x14006aff4`

## callees

- `0x14000d21c`
- `0x140019bbc`
- `0x140020dc0`
- `0x140020f20`
- `0x14006aaa4`
- `0x14006ac2c`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14006aba1`
- `ntoskrnl!KeGetCurrentIrql` at `0x14006aba1`
- `NDIS!NdisAcquireRWLockWrite` at `0x14006aad3`
- `NDIS!NdisAcquireRWLockWrite` at `0x14006aad3`
- `NDIS!NdisReleaseRWLock` at `0x14006ab25`
- `NDIS!NdisReleaseRWLock` at `0x14006ab68`
- `NDIS!NdisReleaseRWLock` at `0x14006ab25`
- `NDIS!NdisReleaseRWLock` at `0x14006ab68`

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
0x14006aaa4  mov     [rsp+arg_10], rbx
0x14006aaa9  push    rdi
0x14006aaaa  sub     rsp, 30h
0x14006aaae  mov     rbx, rcx
0x14006aab1  mov     [rsp+38h+LockState.OldIrql], 0
0x14006aab6  mov     rcx, [rcx+0A38h]
0x14006aabd  lea     rdx, [rsp+38h+LockState]; LockState
0x14006aac2  xor     eax, eax
0x14006aac4  xor     r8d, r8d; Flags
0x14006aac7  mov     word ptr [rsp+38h+LockState.LockState], ax
0x14006aacc  mov     rcx, [rcx+90h]; Lock
0x14006aad3  call    cs:__imp_NdisAcquireRWLockWrite
0x14006aada  nop     dword ptr [rax+rax+00h]
0x14006aadf  mov     ecx, [rbx+6B8h]
0x14006aae5  test    cl, 8
0x14006aae8  jnz     short loc_14006AB38
0x14006aaea  mov     rcx, cs:WPP_GLOBAL_Control
0x14006aaf1  lea     rdi, WPP_GLOBAL_Control
0x14006aaf8  cmp     rcx, rdi
0x14006aafb  jz      short loc_14006AB12
0x14006aafd  mov     rcx, [rcx+18h]
0x14006ab01  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x14006ab08  mov     edx, 28h ; '('
0x14006ab0d  call    WPP_SF_
0x14006ab12  mov     rcx, [rbx+0A38h]
0x14006ab19  lea     rdx, [rsp+38h+LockState]; LockState
0x14006ab1e  mov     rcx, [rcx+90h]; Lock
0x14006ab25  call    cs:__imp_NdisReleaseRWLock
0x14006ab2c  nop     dword ptr [rax+rax+00h]
0x14006ab31  xor     eax, eax
0x14006ab33  jmp     loc_14006AC17
0x14006ab38  mov     eax, [rbx+714h]
0x14006ab3e  lea     rdx, [rsp+38h+LockState]; LockState
0x14006ab43  and     ecx, 0FFFFFFF7h
0x14006ab46  mov     [rsp+38h+arg_8], eax
0x14006ab4a  mov     [rbx+6B8h], ecx
0x14006ab50  mov     rcx, [rbx+0A38h]
0x14006ab57  mov     dword ptr [rbx+714h], 0
0x14006ab61  mov     rcx, [rcx+90h]; Lock
0x14006ab68  call    cs:__imp_NdisReleaseRWLock
0x14006ab6f  nop     dword ptr [rax+rax+00h]
0x14006ab74  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ab7b  lea     rdi, WPP_GLOBAL_Control
0x14006ab82  cmp     rcx, rdi
0x14006ab85  jz      short loc_14006ABA1
0x14006ab87  mov     r9d, [rsp+38h+arg_8]
0x14006ab8c  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x14006ab93  mov     rcx, [rcx+18h]
0x14006ab97  mov     edx, 29h ; ')'
0x14006ab9c  call    WPP_SF_d
0x14006aba1  call    cs:__imp_KeGetCurrentIrql
0x14006aba8  nop     dword ptr [rax+rax+00h]
0x14006abad  test    al, al
0x14006abaf  jnz     short loc_14006AC07
0x14006abb1  mov     rcx, [rbx+0A38h]
0x14006abb8  lea     r9, [rsp+38h+arg_8]; void *
0x14006abbd  mov     edx, 1; unsigned int
0x14006abc2  mov     [rsp+38h+var_18], 4; unsigned int
0x14006abca  mov     r8d, 0FD01010Fh; unsigned int
0x14006abd0  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14006abd4  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14006abd9  mov     ebx, eax
0x14006abdb  mov     rcx, cs:WPP_GLOBAL_Control
0x14006abe2  cmp     rcx, rdi
0x14006abe5  jz      short loc_14006AC15
0x14006abe7  mov     r9d, [rsp+38h+arg_8]
0x14006abec  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x14006abf3  mov     rcx, [rcx+18h]
0x14006abf7  mov     edx, 2Ah ; '*'
0x14006abfc  mov     [rsp+38h+var_18], eax
0x14006ac00  call    WPP_SF_Dd
0x14006ac05  jmp     short loc_14006AC15
0x14006ac07  mov     edx, [rsp+38h+arg_8]; unsigned int
0x14006ac0b  mov     rcx, rbx; struct EXTSTA_VELAN *
0x14006ac0e  call    ?ExtSTARequestAsyncRemoveGTKReKeyOffload@@YAHPEAUEXTSTA_VELAN@@K@Z; ExtSTARequestAsyncRemoveGTKReKeyOffload(EXTSTA_VELAN *,ulong)
0x14006ac13  mov     ebx, eax
0x14006ac15  mov     eax, ebx
0x14006ac17  mov     rbx, [rsp+38h+arg_10]
0x14006ac1c  add     rsp, 30h
0x14006ac20  pop     rdi
0x14006ac21  retn
```
