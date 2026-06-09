# __scrt_dllmain_uninitialize_c

- ea: `0x18000ac7c`
- end: `0x18000acac`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000a918`

## callees

- `0x18000ac7c`
- `0x18000b368`
- `0x18000b3c2`
- `0x18000b3e6`
- `0x18000c0c0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  C1in1outDMO *v0; // rcx
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = C1in1outDMO::Discontinuity(v0);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x18000ac7c  sub     rsp, 28h
0x18000ac80  call    __scrt_is_ucrt_dll_in_use
0x18000ac85  test    eax, eax
0x18000ac87  jz      short loc_18000AC99
0x18000ac89  lea     rcx, Table; Table
0x18000ac90  add     rsp, 28h
0x18000ac94  jmp     _execute_onexit_table
0x18000ac99  call    ?Discontinuity@C1in1outDMO@@MEAAJXZ; C1in1outDMO::Discontinuity(void)
0x18000ac9e  test    eax, eax
0x18000aca0  jnz     short loc_18000ACA7
0x18000aca2  call    _o__cexit_0
0x18000aca7  add     rsp, 28h
0x18000acab  retn
```
