# CAssociationWriteCallback::OnWriteCeremonyDataComplete(long)

- ea: `0x1400184b0`
- end: `0x140018506`
- name: `?OnWriteCeremonyDataComplete@CAssociationWriteCallback@@UEAAJJ@Z`
- size: `86`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000bbac`
- `0x1400184b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400184ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400184ee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400184cb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400184cb`

## pseudocode

```c
__int64 __fastcall CAssociationWriteCallback::OnWriteCeremonyDataComplete(RTL_SRWLOCK *this, int a2)
{
  RTL_SRWLOCK *v2; // rdi
  unsigned int v5; // ebx

  v2 = this + 3;
  AcquireSRWLockShared(this + 3);
  if ( LODWORD(this[4].Ptr) )
    v5 = OnWriteCeremonyDataCompleteStub(a2, this[2].Ptr);
  else
    v5 = -2140930029;
  ReleaseSRWLockShared(v2);
  return v5;
}

```

## disassembly

```asm
0x1400184b0  mov     [rsp+arg_0], rbx
0x1400184b5  mov     [rsp+arg_8], rsi
0x1400184ba  push    rdi
0x1400184bb  sub     rsp, 20h
0x1400184bf  lea     rdi, [rcx+18h]
0x1400184c3  mov     rbx, rcx
0x1400184c6  mov     rcx, rdi; SRWLock
0x1400184c9  mov     esi, edx
0x1400184cb  call    cs:__imp_AcquireSRWLockShared
0x1400184d1  cmp     dword ptr [rbx+20h], 0
0x1400184d5  jz      short loc_1400184E6
0x1400184d7  mov     rdx, [rbx+10h]; void *
0x1400184db  mov     ecx, esi; int
0x1400184dd  call    ?OnWriteCeremonyDataCompleteStub@@YAJJPEAX@Z; OnWriteCeremonyDataCompleteStub(long,void *)
0x1400184e2  mov     ebx, eax
0x1400184e4  jmp     short loc_1400184EB
0x1400184e6  mov     ebx, 80640013h
0x1400184eb  mov     rcx, rdi; SRWLock
0x1400184ee  call    cs:__imp_ReleaseSRWLockShared
0x1400184f4  mov     rsi, [rsp+28h+arg_8]
0x1400184f9  mov     eax, ebx
0x1400184fb  mov     rbx, [rsp+28h+arg_0]
0x140018500  add     rsp, 20h
0x140018504  pop     rdi
0x140018505  retn
```
