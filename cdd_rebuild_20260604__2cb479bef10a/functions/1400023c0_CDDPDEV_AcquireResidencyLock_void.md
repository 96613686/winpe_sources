# CDDPDEV::AcquireResidencyLock(void)

- ea: `0x1400023c0`
- end: `0x14000240e`
- name: `?AcquireResidencyLock@CDDPDEV@@QEAAXXZ`
- size: `78`
- prototype: `void __fastcall(CDDPDEV *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140001b6c`
- `0x140010c2c`
- `0x14001b448`
- `0x1400218e4`
- `0x14002d228`

## callees

- `0x1400023c0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400023ea`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400023ea`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400023d9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400023d9`

## pseudocode

```c
void __fastcall CDDPDEV::AcquireResidencyLock(CDDPDEV *this)
{
  __int64 v1; // rbx

  if ( *((_BYTE *)this + 12716) )
  {
    v1 = *((_QWORD *)this + 1600);
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(v1, 0);
    *(_QWORD *)(v1 + 8) = KeGetCurrentThread();
  }
}

```

## disassembly

```asm
0x1400023c0  sub     rsp, 28h
0x1400023c4  cmp     byte ptr [rcx+31ACh], 0
0x1400023cb  jz      short loc_140002408
0x1400023cd  mov     [rsp+28h+var_8], rbx
0x1400023d2  mov     rbx, [rcx+3200h]
0x1400023d9  call    cs:__imp_KeEnterCriticalRegion
0x1400023e0  nop     dword ptr [rax+rax+00h]
0x1400023e5  xor     edx, edx
0x1400023e7  mov     rcx, rbx
0x1400023ea  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400023f1  nop     dword ptr [rax+rax+00h]
0x1400023f6  mov     rax, gs:188h
0x1400023ff  mov     [rbx+8], rax
0x140002403  mov     rbx, [rsp+28h+var_8]
0x140002408  add     rsp, 28h
0x14000240c  retn
```
