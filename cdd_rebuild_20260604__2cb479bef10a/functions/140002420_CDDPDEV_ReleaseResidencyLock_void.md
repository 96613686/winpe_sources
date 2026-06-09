# CDDPDEV::ReleaseResidencyLock(void)

- ea: `0x140002420`
- end: `0x14000245c`
- name: `?ReleaseResidencyLock@CDDPDEV@@QEAAXXZ`
- size: `60`
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

- `0x140002420`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000244a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000244a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000243e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000243e`

## pseudocode

```c
void __fastcall CDDPDEV::ReleaseResidencyLock(CDDPDEV *this)
{
  __int64 v1; // rcx

  if ( *((_BYTE *)this + 12716) )
  {
    v1 = *((_QWORD *)this + 1600);
    *(_QWORD *)(v1 + 8) = 0;
    ExReleasePushLockExclusiveEx(v1, 0);
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x140002420  sub     rsp, 28h
0x140002424  cmp     byte ptr [rcx+31ACh], 0
0x14000242b  jz      short loc_140002456
0x14000242d  mov     rcx, [rcx+3200h]
0x140002434  xor     edx, edx
0x140002436  mov     qword ptr [rcx+8], 0
0x14000243e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140002445  nop     dword ptr [rax+rax+00h]
0x14000244a  call    cs:__imp_KeLeaveCriticalRegion
0x140002451  nop     dword ptr [rax+rax+00h]
0x140002456  add     rsp, 28h
0x14000245a  retn
```
