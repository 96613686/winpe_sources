# CClfsLogFcbPhysical::WriteRestartDone(uchar)

- ea: `0x14004af70`
- end: `0x14004b0a7`
- name: `?WriteRestartDone@CClfsLogFcbPhysical@@UEAAXE@Z`
- size: `311`
- prototype: `void __fastcall(CClfsLogFcbPhysical *__hidden this, unsigned __int8)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140005840`
- `0x14000a29c`
- `0x140017f20`
- `0x14004af70`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004afa9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004afc5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004afa9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004afc5`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x14004b016`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x14004b016`

## pseudocode

```c
void __fastcall CClfsLogFcbPhysical::WriteRestartDone(CClfsLogFcbPhysical *this, char a2)
{
  char *v4; // rsi
  BOOLEAN v5; // r14
  BOOLEAN v6; // r15
  PIRP v7; // rax
  struct _LIST_ENTRY *Flink; // rbx
  __int64 PeekContext; // [rsp+20h] [rbp-38h] BYREF
  __int64 v10; // [rsp+28h] [rbp-30h]

  PeekContext = 0;
  v10 = 0;
  v4 = (char *)this - 408;
  v5 = ExAcquireResourceExclusiveLite((PERESOURCE)((char *)this - 408), 1u);
  v6 = ExAcquireResourceExclusiveLite(*((PERESOURCE *)this + 100), 1u);
  CClfsLogFcbCommon::NotifyObservers((CClfsLogFcbPhysical *)((char *)this - 608), 0xCF00u, (char *)this - 120, 0);
  *((_DWORD *)this - 61) &= ~0x100u;
  LODWORD(v10) = -2147014625;
  LOBYTE(PeekContext) = a2;
  BYTE4(v10) = 0;
  v7 = IoCsqRemoveNextIrp((PIO_CSQ)((char *)this + 392), &PeekContext);
  if ( v7 )
  {
    Flink = v7->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
    ((void (__fastcall *)(struct _LIST_ENTRY *))Flink->Flink[7].Flink)(Flink);
    ((void (__fastcall *)(struct _LIST_ENTRY *))Flink->Flink->Blink)(Flink);
  }
  *((CLFS_LSN *)this - 11) = CLFS_LSN_INVALID;
  *((CLFS_LSN *)this - 10) = CLFS_LSN_INVALID;
  *((CLFS_LSN *)this - 9) = CLFS_LSN_INVALID;
  *((CLFS_LSN *)this - 8) = CLFS_LSN_INVALID;
  if ( v6 )
    ClfsReleaseResourceLite(*((_QWORD *)this + 100));
  if ( v5 )
    ClfsReleaseResourceLite(v4);
}

```

## disassembly

```asm
0x14004af70  mov     rax, rsp
0x14004af73  mov     [rax+10h], rbx
0x14004af77  mov     [rax+8], rcx
0x14004af7b  push    rsi
0x14004af7c  push    rdi
0x14004af7d  push    r12
0x14004af7f  push    r14
0x14004af81  push    r15
0x14004af83  sub     rsp, 30h
0x14004af87  mov     r12b, dl
0x14004af8a  mov     rdi, rcx
0x14004af8d  mov     qword ptr [rax-38h], 0
0x14004af95  mov     qword ptr [rax-30h], 0
0x14004af9d  lea     rsi, [rcx-198h]
0x14004afa4  mov     dl, 1; Wait
0x14004afa6  mov     rcx, rsi; Resource
0x14004afa9  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004afb0  nop     dword ptr [rax+rax+00h]
0x14004afb5  mov     r14b, al
0x14004afb8  mov     [rsp+58h+arg_18], al
0x14004afbc  mov     dl, 1; Wait
0x14004afbe  mov     rcx, [rdi+320h]; Resource
0x14004afc5  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004afcc  nop     dword ptr [rax+rax+00h]
0x14004afd1  mov     r15b, al
0x14004afd4  mov     [rsp+58h+arg_10], al
0x14004afd8  lea     r8, [rdi-78h]; void *
0x14004afdc  xor     r9d, r9d; void *
0x14004afdf  mov     edx, 0CF00h; unsigned int
0x14004afe4  lea     rcx, [rdi-260h]; this
0x14004afeb  call    ?NotifyObservers@CClfsLogFcbCommon@@QEAAJKPEAX0@Z; CClfsLogFcbCommon::NotifyObservers(ulong,void *,void *)
0x14004aff0  btr     dword ptr [rdi-0F4h], 8
0x14004aff8  mov     [rsp+58h+var_30], 8007281Fh
0x14004b000  mov     byte ptr [rsp+58h+PeekContext], r12b
0x14004b005  mov     [rsp+58h+var_2C], 0
0x14004b00a  lea     rcx, [rdi+188h]; Csq
0x14004b011  lea     rdx, [rsp+58h+PeekContext]; PeekContext
0x14004b016  call    cs:__imp_IoCsqRemoveNextIrp
0x14004b01d  nop     dword ptr [rax+rax+00h]
0x14004b022  test    rax, rax
0x14004b025  jz      short loc_14004B04A
0x14004b027  mov     rbx, [rax+78h]
0x14004b02b  mov     rax, [rbx]
0x14004b02e  mov     rax, [rax+70h]
0x14004b032  mov     rcx, rbx
0x14004b035  call    _guard_dispatch_icall
0x14004b03a  mov     rax, [rbx]
0x14004b03d  mov     rax, [rax+8]
0x14004b041  mov     rcx, rbx
0x14004b044  call    _guard_dispatch_icall
0x14004b049  nop
0x14004b04a  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x14004b051  mov     [rdi-58h], rax
0x14004b055  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x14004b05c  mov     [rdi-50h], rax
0x14004b060  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x14004b067  mov     [rdi-48h], rax
0x14004b06b  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x14004b072  mov     [rdi-40h], rax
0x14004b076  test    r15b, r15b
0x14004b079  jz      short loc_14004B087
0x14004b07b  mov     rcx, [rdi+320h]
0x14004b082  call    ClfsReleaseResourceLite
0x14004b087  test    r14b, r14b
0x14004b08a  jz      short loc_14004B094
0x14004b08c  mov     rcx, rsi
0x14004b08f  call    ClfsReleaseResourceLite
0x14004b094  mov     rbx, [rsp+58h+arg_8]
0x14004b099  add     rsp, 30h
0x14004b09d  pop     r15
0x14004b09f  pop     r14
0x14004b0a1  pop     r12
0x14004b0a3  pop     rdi
0x14004b0a4  pop     rsi
0x14004b0a5  retn
0x1400803ca  push    rbx
0x1400803cc  push    rbp
0x1400803cd  sub     rsp, 28h
0x1400803d1  mov     rbp, rdx
0x1400803d4  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400803db  mov     rbx, [rbp+60h]
0x1400803df  mov     [rbx-58h], rax
0x1400803e3  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400803ea  mov     [rbx-50h], rax
0x1400803ee  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400803f5  mov     [rbx-48h], rax
0x1400803f9  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140080400  mov     [rbx-40h], rax
0x140080404  cmp     byte ptr [rbp+70h], 0
0x140080408  jz      short loc_140080417
0x14008040a  mov     rcx, [rbx+320h]
0x140080411  call    ClfsReleaseResourceLite
0x140080416  nop
0x140080417  cmp     byte ptr [rbp+78h], 0
0x14008041b  jz      short loc_14008042A
0x14008041d  lea     rcx, [rbx-198h]
0x140080424  call    ClfsReleaseResourceLite
0x140080429  nop
0x14008042a  add     rsp, 28h
0x14008042e  pop     rbp
0x14008042f  pop     rbx
0x140080430  retn
```
