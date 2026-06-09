# FreeUpdateHpkpJob

- ea: `0x18000d788`
- end: `0x18000d79b`
- name: `FreeUpdateHpkpJob`
- size: `19`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180001868`

## callees

- `0x1800068b0`
- `0x18000d788`

## pseudocode

```c
__int64 __fastcall FreeUpdateHpkpJob(void *a1)
{
  __int64 result; // rax

  if ( a1 )
    return PkiFree(a1);
  return result;
}

```

## disassembly

```asm
0x18000d788  sub     rsp, 28h
0x18000d78c  test    rcx, rcx
0x18000d78f  jz      short loc_18000D796
0x18000d791  call    PkiFree
0x18000d796  add     rsp, 28h
0x18000d79a  retn
```
