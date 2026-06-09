# RtlGetCurrentServiceSessionId

- ea: `0x1800526f0`
- end: `0x18005270a`
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
- `0x180023e20`
- `0x1800267b4`
- `0x180027080`
- `0x1800272a0`
- `0x180028620`
- `0x180028bd0`
- `0x180029b70`
- `0x180029fc0`
- `0x18002a3b8`
- `0x18002a640`
- `0x18002bbf0`
- `0x18002c970`
- `0x18002ed00`
- `0x18002fc00`
- `0x18002ff80`
- `0x1800306ec`
- `0x180030774`
- `0x180030800`
- `0x180031200`
- `0x1800370b0`
- `0x18003806c`
- `0x18003aa70`
- `0x18003c328`
- `0x18003d390`
- `0x18003d430`
- `0x18003d5f0`
- `0x18003e4c0`
- `0x18003e658`
- `0x18003e7ac`
- `0x18003eb5c`
- `0x18003ee4c`
- `0x18003f734`
- `0x18003f7f4`
- `0x18003ff58`
- `0x1800460e4`
- `0x180046b50`
- `0x180046e20`
- `0x1800474f0`
- `0x180048acc`

## callees

- `0x1800526f0`

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
0x1800526f0  mov     rax, gs:60h
0x1800526f9  mov     rax, [rax+90h]
0x180052700  test    rax, rax
0x180052703  jnz     short loc_180052707
0x180052705  retn
0x180052707  mov     eax, [rax]
0x180052709  retn
```
