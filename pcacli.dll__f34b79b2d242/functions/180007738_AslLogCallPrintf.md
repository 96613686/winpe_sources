# AslLogCallPrintf

- ea: `0x180007738`
- end: `0x180007769`
- name: `AslLogCallPrintf`
- size: `49`
- prototype: ``
- caller_count: `26`
- callee_count: `2`
- tags: ``

## callers

- `0x1800012c0`
- `0x180001430`
- `0x180001870`
- `0x180001bd0`
- `0x180002210`
- `0x180002ca0`
- `0x180004bf0`
- `0x1800050e0`
- `0x180005620`
- `0x1800068a0`
- `0x1800069e0`
- `0x180006a90`
- `0x180006c80`
- `0x180007040`
- `0x1800082c0`
- `0x180008480`
- `0x1800086c0`
- `0x1800088a8`
- `0x18000a39c`
- `0x18000a5b8`
- `0x18000a67c`
- `0x18000a7c4`
- `0x18000b50c`
- `0x18000b6dc`
- `0x18000b8dc`
- `0x18000bb94`

## callees

- `0x180007738`
- `0x18000d010`

## pseudocode

```c
__int64 (__fastcall *AslLogCallPrintf(__int64 a1, _QWORD a2, _QWORD a3, const char *a4, ...))(_QWORD)
{
  __int64 (__fastcall *result)(_QWORD); // rax

  result = g_AslLogPfnVPrintf;
  if ( g_AslLogPfnVPrintf )
    return (__int64 (__fastcall *)(_QWORD))g_AslLogPfnVPrintf(a1);
  return result;
}

```

## disassembly

```asm
0x180007738  mov     r11, rsp
0x18000773b  mov     [r11+20h], r9
0x18000773f  sub     rsp, 48h
0x180007743  mov     rax, cs:g_AslLogPfnVPrintf
0x18000774a  mov     qword ptr [r11-18h], 0
0x180007752  test    rax, rax
0x180007755  jz      short loc_180007764
0x180007757  lea     r10, [r11+28h]
0x18000775b  mov     [r11-28h], r10
0x18000775f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007764  add     rsp, 48h
0x180007768  retn
```
