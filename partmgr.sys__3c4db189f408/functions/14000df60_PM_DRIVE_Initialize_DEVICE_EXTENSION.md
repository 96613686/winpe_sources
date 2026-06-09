# PM_DRIVE::Initialize(_DEVICE_EXTENSION *)

- ea: `0x14000df60`
- end: `0x14000df88`
- name: `?Initialize@PM_DRIVE@@QEAAJPEAU_DEVICE_EXTENSION@@@Z`
- size: `40`
- prototype: `__int64 __fastcall(PM_DRIVE *__hidden this, struct _DEVICE_EXTENSION *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14002208c`
- `0x1400221e4`

## callees

- `0x1400050c0`
- `0x140009880`
- `0x14000df60`

## pseudocode

```c
__int64 __fastcall PM_DRIVE::Initialize(PM_DRIVE *this, struct _DEVICE_EXTENSION *a2)
{
  __int64 result; // rax

  *((_QWORD *)this + 74) = a2;
  result = SC_DISK::Initialize(this);
  if ( (int)result >= 0 )
    return SC_DISK::InitializePartitionCache(this);
  return result;
}

```

## disassembly

```asm
0x14000df60  push    rbx
0x14000df62  sub     rsp, 20h
0x14000df66  mov     rbx, rcx
0x14000df69  mov     [rcx+250h], rdx
0x14000df70  call    ?Initialize@SC_DISK@@UEAAJXZ; SC_DISK::Initialize(void)
0x14000df75  test    eax, eax
0x14000df77  js      short loc_14000DF81
0x14000df79  mov     rcx, rbx; this
0x14000df7c  call    ?InitializePartitionCache@SC_DISK@@QEAAJXZ; SC_DISK::InitializePartitionCache(void)
0x14000df81  add     rsp, 20h
0x14000df85  pop     rbx
0x14000df86  retn
```
