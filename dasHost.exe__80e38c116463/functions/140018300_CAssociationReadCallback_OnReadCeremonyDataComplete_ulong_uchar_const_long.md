# CAssociationReadCallback::OnReadCeremonyDataComplete(ulong,uchar const *,long)

- ea: `0x140018300`
- end: `0x14001835b`
- name: `?OnReadCeremonyDataComplete@CAssociationReadCallback@@UEAAJKPEBEJ@Z`
- size: `91`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, unsigned int, const unsigned __int8 *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000b994`
- `0x140018300`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140018348`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140018348`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14001831e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14001831e`

## pseudocode

```c
__int64 __fastcall CAssociationReadCallback::OnReadCeremonyDataComplete(
        RTL_SRWLOCK *this,
        unsigned int a2,
        const unsigned __int8 *a3,
        int a4)
{
  RTL_SRWLOCK *v4; // rdi
  unsigned int CeremonyDataCompleteStub; // ebx

  v4 = this + 3;
  AcquireSRWLockShared(this + 3);
  if ( LODWORD(this[4].Ptr) )
    CeremonyDataCompleteStub = OnReadCeremonyDataCompleteStub(a2, a3, a4, this[2].Ptr);
  else
    CeremonyDataCompleteStub = -2140930029;
  ReleaseSRWLockShared(v4);
  return CeremonyDataCompleteStub;
}

```

## disassembly

```asm
0x140018300  push    rbx
0x140018302  push    rbp
0x140018303  push    rsi
0x140018304  push    rdi
0x140018305  push    r14
0x140018307  sub     rsp, 20h
0x14001830b  lea     rdi, [rcx+18h]
0x14001830f  mov     rbx, rcx
0x140018312  mov     rcx, rdi; SRWLock
0x140018315  mov     esi, r9d
0x140018318  mov     rbp, r8
0x14001831b  mov     r14d, edx
0x14001831e  call    cs:__imp_AcquireSRWLockShared
0x140018324  cmp     dword ptr [rbx+20h], 0
0x140018328  jz      short loc_140018340
0x14001832a  mov     r9, [rbx+10h]; void *
0x14001832e  mov     r8d, esi; int
0x140018331  mov     rdx, rbp; Src
0x140018334  mov     ecx, r14d; Size
0x140018337  call    ?OnReadCeremonyDataCompleteStub@@YAJKPEBEJPEAX@Z; OnReadCeremonyDataCompleteStub(ulong,uchar const *,long,void *)
0x14001833c  mov     ebx, eax
0x14001833e  jmp     short loc_140018345
0x140018340  mov     ebx, 80640013h
0x140018345  mov     rcx, rdi; SRWLock
0x140018348  call    cs:__imp_ReleaseSRWLockShared
0x14001834e  mov     eax, ebx
0x140018350  add     rsp, 20h
0x140018354  pop     r14
0x140018356  pop     rdi
0x140018357  pop     rsi
0x140018358  pop     rbp
0x140018359  pop     rbx
0x14001835a  retn
```
