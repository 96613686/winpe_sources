# BriResolveBrokerIdByEventId

- ea: `0x180008c30`
- end: `0x180008c88`
- name: `BriResolveBrokerIdByEventId`
- size: `88`
- prototype: `__int64 __fastcall(void *Source1)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800020b0`
- `0x180008c30`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x180008c5e`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180008c5e`

## pseudocode

```c
__int64 __fastcall BriResolveBrokerIdByEventId(void *Source1, __int64 a2)
{
  __int64 result; // rax

  if ( !Source1 || !a2 )
    return 3221225485LL;
  result = RtlRunOnceExecuteOnce(&BrokerInternalClientInitOnce, BrpInitOnceRunOnceCallback, 0, 0);
  if ( (int)result >= 0 )
    return BripGetEventContextData(Source1);
  return result;
}

```

## disassembly

```asm
0x180008c30  mov     [rsp+arg_0], rbx
0x180008c35  push    rdi
0x180008c36  sub     rsp, 20h
0x180008c3a  mov     rbx, rdx
0x180008c3d  mov     rdi, rcx
0x180008c40  test    rcx, rcx
0x180008c43  jz      short loc_180008C78
0x180008c45  test    rdx, rdx
0x180008c48  jz      short loc_180008C78
0x180008c4a  xor     r9d, r9d
0x180008c4d  lea     rdx, BrpInitOnceRunOnceCallback
0x180008c54  xor     r8d, r8d
0x180008c57  lea     rcx, BrokerInternalClientInitOnce
0x180008c5e  call    cs:__imp_RtlRunOnceExecuteOnce
0x180008c64  test    eax, eax
0x180008c66  js      short loc_180008C7D
0x180008c68  xor     r8d, r8d
0x180008c6b  mov     rdx, rbx
0x180008c6e  mov     rcx, rdi; Source1
0x180008c71  call    BripGetEventContextData
0x180008c76  jmp     short loc_180008C7D
0x180008c78  mov     eax, 0C000000Dh
0x180008c7d  mov     rbx, [rsp+28h+arg_0]
0x180008c82  add     rsp, 20h
0x180008c86  pop     rdi
0x180008c87  retn
```
