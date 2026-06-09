# ATL::_dynamic_atexit_destructor_for___AtlBaseModule__

- ea: `0x180034750`
- end: `0x18003478d`
- name: `ATL::_dynamic_atexit_destructor_for___AtlBaseModule__`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180012564`
- `0x180034750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003475b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003475b`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlBaseModule__()
{
  DeleteCriticalSection(&stru_180049588);
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_1800495B8 = 0;
}

```

## disassembly

```asm
0x180034750  sub     rsp, 28h
0x180034754  lea     rcx, stru_180049588; lpCriticalSection
0x18003475b  call    cs:__imp_DeleteCriticalSection
0x180034761  mov     rcx, cs:Block; Block
0x180034768  test    rcx, rcx
0x18003476b  jz      short loc_18003477D
0x18003476d  call    free
0x180034772  mov     cs:Block, 0
0x18003477d  mov     cs:qword_1800495B8, 0
0x180034788  add     rsp, 28h
0x18003478c  retn
```
