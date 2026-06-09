# FREB_LOG_NT_EVENT_TABLE::CacheFlushByTTL(FREB_LOG_NT_EVENT *,void *)

- ea: `0x18000a2c0`
- end: `0x18000a2e0`
- name: `?CacheFlushByTTL@FREB_LOG_NT_EVENT_TABLE@@CA?AW4LK_PREDICATE@@PEAVFREB_LOG_NT_EVENT@@PEAX@Z`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000a2c0`
- `0x18000a7e0`

## pseudocode

```c
__int64 __fastcall FREB_LOG_NT_EVENT_TABLE::CacheFlushByTTL(FREB_LOG_NT_EVENT *a1)
{
  if ( !*((_DWORD *)a1 + 1) )
    return 3;
  FREB_LOG_NT_EVENT::RealLogEvent(a1);
  return 2;
}

```

## disassembly

```asm
0x18000a2c0  sub     rsp, 28h
0x18000a2c4  cmp     dword ptr [rcx+4], 0
0x18000a2c8  jnz     short loc_18000A2D1
0x18000a2ca  mov     eax, 3
0x18000a2cf  jmp     short loc_18000A2DB
0x18000a2d1  call    ?RealLogEvent@FREB_LOG_NT_EVENT@@QEAAXXZ; FREB_LOG_NT_EVENT::RealLogEvent(void)
0x18000a2d6  mov     eax, 2
0x18000a2db  add     rsp, 28h
0x18000a2df  retn
```
