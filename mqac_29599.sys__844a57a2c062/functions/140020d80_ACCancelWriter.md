# ACCancelWriter

- ea: `0x140020d80`
- end: `0x140020eb6`
- name: `ACCancelWriter`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140003d84`
- `0x140011cc8`
- `0x140012754`
- `0x140020d80`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140020dcb`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140020dcb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140020e09`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140020e09`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140020e19`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140020e19`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140020e66`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140020e66`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140020e72`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140020e72`
- `ntoskrnl!IofCompleteRequest` at `0x140020e56`
- `ntoskrnl!IofCompleteRequest` at `0x140020e56`

## pseudocode

```c
void __fastcall ACCancelWriter(__int64 a1, __int64 a2)
{
  _QWORD *v2; // rax
  __int64 v4; // r8
  _QWORD *v5; // rdx
  __int64 v6; // rbx
  struct CPacket *AttachedPacketsHead; // rax
  _QWORD *v8; // rcx

  v2 = (_QWORD *)(a2 + 168);
  v4 = *(_QWORD *)(a2 + 168);
  if ( *(_QWORD *)(v4 + 8) != a2 + 168 || (v5 = *(_QWORD **)(a2 + 176), (_QWORD *)*v5 != v2) )
    __fastfail(3u);
  v6 = *(_QWORD *)(a1 + 64);
  *v5 = v4;
  *(_QWORD *)(v4 + 8) = v5;
  *v2 = 0;
  v2[1] = 0;
  IoReleaseCancelSpinLock(*(_BYTE *)(a2 + 69));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 10, &WPP_154e3a669a6d37aaa7a9816475bffab0_Traceguids, a2);
  }
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v6 + 8));
  while ( (*(_DWORD *)(a2 + 144) & 0x80) != 0 )
  {
    AttachedPacketsHead = CIrp2Pkt::GetAttachedPacketsHead((struct _IRP *)a2);
    v8 = (_QWORD *)(a2 + 56);
    if ( !AttachedPacketsHead )
      goto LABEL_9;
LABEL_12:
    *((_DWORD *)AttachedPacketsHead + 13) &= ~0x80000u;
    CBaseObject::Release(AttachedPacketsHead);
  }
  v8 = (_QWORD *)(a2 + 56);
  AttachedPacketsHead = *(struct CPacket **)(a2 + 56);
  if ( AttachedPacketsHead )
  {
    *v8 = 0;
    goto LABEL_12;
  }
LABEL_9:
  *v8 = 0;
  *(_DWORD *)(a2 + 48) = -1073741536;
  IofCompleteRequest((PIRP)a2, 0);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v6 + 8));
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x140020d80  mov     [rsp+arg_0], rbx
0x140020d85  push    rdi
0x140020d86  sub     rsp, 20h
0x140020d8a  lea     rax, [rdx+0A8h]
0x140020d91  mov     rdi, rdx
0x140020d94  mov     r8, [rax]
0x140020d97  cmp     [r8+8], rax
0x140020d9b  jnz     loc_140020EAF
0x140020da1  mov     rdx, [rax+8]
0x140020da5  cmp     [rdx], rax
0x140020da8  jnz     loc_140020EAF
0x140020dae  mov     rbx, [rcx+40h]
0x140020db2  mov     [rdx], r8
0x140020db5  mov     [r8+8], rdx
0x140020db9  mov     qword ptr [rax], 0
0x140020dc0  mov     qword ptr [rax+8], 0
0x140020dc8  mov     cl, [rdi+45h]; Irql
0x140020dcb  call    cs:__imp_IoReleaseCancelSpinLock
0x140020dd2  nop     dword ptr [rax+rax+00h]
0x140020dd7  mov     rcx, cs:WPP_GLOBAL_Control
0x140020dde  lea     rax, WPP_GLOBAL_Control
0x140020de5  cmp     rcx, rax
0x140020de8  jz      short loc_140020E09
0x140020dea  mov     eax, [rcx+6Ch]
0x140020ded  test    al, 4
0x140020def  jz      short loc_140020E09
0x140020df1  mov     rcx, [rcx+58h]
0x140020df5  lea     r8, WPP_154e3a669a6d37aaa7a9816475bffab0_Traceguids
0x140020dfc  mov     edx, 0Ah
0x140020e01  mov     r9, rdi
0x140020e04  call    WPP_SF_q
0x140020e09  call    cs:__imp_KeEnterCriticalRegion
0x140020e10  nop     dword ptr [rax+rax+00h]
0x140020e15  lea     rcx, [rbx+8]; FastMutex
0x140020e19  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140020e20  nop     dword ptr [rax+rax+00h]
0x140020e25  mov     eax, [rdi+90h]
0x140020e2b  shr     eax, 7
0x140020e2e  test    al, 1
0x140020e30  jz      short loc_140020E8A
0x140020e32  mov     rcx, rdi; struct _IRP *
0x140020e35  call    ?GetAttachedPacketsHead@CIrp2Pkt@@SAPEAVCPacket@@PEAU_IRP@@@Z; CIrp2Pkt::GetAttachedPacketsHead(_IRP *)
0x140020e3a  lea     rcx, [rdi+38h]
0x140020e3e  test    rax, rax
0x140020e41  jnz     short loc_140020E9D
0x140020e43  mov     qword ptr [rcx], 0
0x140020e4a  xor     edx, edx; PriorityBoost
0x140020e4c  mov     rcx, rdi; Irp
0x140020e4f  mov     dword ptr [rdi+30h], 0C0000120h
0x140020e56  call    cs:__imp_IofCompleteRequest
0x140020e5d  nop     dword ptr [rax+rax+00h]
0x140020e62  lea     rcx, [rbx+8]; FastMutex
0x140020e66  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140020e6d  nop     dword ptr [rax+rax+00h]
0x140020e72  call    cs:__imp_KeLeaveCriticalRegion
0x140020e79  nop     dword ptr [rax+rax+00h]
0x140020e7e  mov     rbx, [rsp+28h+arg_0]
0x140020e83  add     rsp, 20h
0x140020e87  pop     rdi
0x140020e88  retn
0x140020e8a  lea     rcx, [rdi+38h]
0x140020e8e  mov     rax, [rcx]
0x140020e91  test    rax, rax
0x140020e94  jz      short loc_140020E43
0x140020e96  mov     qword ptr [rcx], 0
0x140020e9d  btr     dword ptr [rax+34h], 13h
0x140020ea2  mov     rcx, rax; this
0x140020ea5  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x140020eaa  jmp     loc_140020E25
0x140020eaf  mov     ecx, 3
0x140020eb4  int     29h; Win8: RtlFailFast(ecx)
```
