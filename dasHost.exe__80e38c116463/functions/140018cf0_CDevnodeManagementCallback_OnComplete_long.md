# CDevnodeManagementCallback::OnComplete(long)

- ea: `0x140018cf0`
- end: `0x140018d2f`
- name: `?OnComplete@CDevnodeManagementCallback@@UEAAJJ@Z`
- size: `63`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140018d1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140018d1c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140018d04`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140018d04`

## pseudocode

```c
__int64 __fastcall CDevnodeManagementCallback::OnComplete(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rdi
  RTL_SRWLOCK *v2; // rbx

  v1 = this + 6;
  v2 = this;
  AcquireSRWLockShared(this + 6);
  LODWORD(v2) = LODWORD(v2[7].Ptr) == 0 ? 0x80640013 : 0;
  ReleaseSRWLockShared(v1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140018cf0  mov     [rsp+arg_0], rbx
0x140018cf5  push    rdi
0x140018cf6  sub     rsp, 20h
0x140018cfa  lea     rdi, [rcx+30h]
0x140018cfe  mov     rbx, rcx
0x140018d01  mov     rcx, rdi; SRWLock
0x140018d04  call    cs:__imp_AcquireSRWLockShared
0x140018d0a  mov     eax, [rbx+38h]
0x140018d0d  mov     rcx, rdi; SRWLock
0x140018d10  neg     eax
0x140018d12  sbb     ebx, ebx
0x140018d14  not     ebx
0x140018d16  and     ebx, 80640013h
0x140018d1c  call    cs:__imp_ReleaseSRWLockShared
0x140018d22  mov     eax, ebx
0x140018d24  mov     rbx, [rsp+28h+arg_0]
0x140018d29  add     rsp, 20h
0x140018d2d  pop     rdi
0x140018d2e  retn
```
