# RtlGetCurrentServiceSessionId

- ea: `0x18006f0d0`
- end: `0x18006f0ea`
- name: `RtlGetCurrentServiceSessionId`
- size: `26`
- prototype: `__int64(void)`
- caller_count: `170`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180003aa4`
- `0x180004770`
- `0x180004c58`
- `0x180008124`
- `0x180008488`
- `0x180013330`
- `0x180015d00`
- `0x180016fa0`
- `0x180018bc0`
- `0x18001dc60`
- `0x18001eb80`
- `0x180023e10`
- `0x1800267a4`
- `0x180027070`
- `0x180027290`
- `0x180028510`
- `0x180028ac0`
- `0x180029a60`
- `0x180029eb0`
- `0x18002a2a8`
- `0x18002aef0`
- `0x18002bc70`
- `0x18002e000`
- `0x18002ef00`
- `0x18002f280`
- `0x18002f9ec`
- `0x18002fa74`
- `0x18002fb00`
- `0x180030500`
- `0x180036690`
- `0x180042b14`
- `0x1800444ac`
- `0x180044c10`
- `0x180044cd0`
- `0x180044fbc`
- `0x1800451b0`
- `0x180045608`
- `0x1800492d0`
- `0x18004ab88`
- `0x18004bbf0`
- `0x18004bc90`
- `0x18004be50`
- `0x18004cd20`
- `0x18004ceb8`
- `0x18004d00c`
- `0x18004d838`
- `0x18004fde0`
- `0x180057020`
- `0x180057180`
- `0x180058fb0`

## callees

- `0x18006f0d0`

## pseudocode

```c
unsigned int *RtlGetCurrentServiceSessionId()
{
  unsigned int *result; // rax

  result = (unsigned int *)NtCurrentPeb()->SharedData;
  if ( result )
    return (unsigned int *)*result;
  return result;
}

```

## disassembly

```asm
0x18006f0d0  mov     rax, gs:60h
0x18006f0d9  mov     rax, [rax+90h]
0x18006f0e0  test    rax, rax
0x18006f0e3  jnz     short loc_18006F0E7
0x18006f0e5  retn
0x18006f0e7  mov     eax, [rax]
0x18006f0e9  retn
```
