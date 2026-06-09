# EapDeleteAggregatedEventConditionVisitNode

- ea: `0x180008940`
- end: `0x180008983`
- name: `EapDeleteAggregatedEventConditionVisitNode`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002130`
- `0x180002e30`
- `0x180008940`

## pseudocode

```c
__int64 __fastcall EapDeleteAggregatedEventConditionVisitNode(int *a1, int *a2)
{
  int v3; // edx

  v3 = *a2;
  if ( v3 )
  {
    if ( v3 == 1 )
      EaLibFree(*((_QWORD *)a2 + 2));
  }
  else
  {
    BriDeleteBrokeredEvent(a2 + 4, *a1);
    *((_QWORD *)a2 + 2) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180008940  mov     [rsp+arg_0], rbx
0x180008945  push    rdi
0x180008946  sub     rsp, 20h
0x18000894a  mov     rdi, rdx
0x18000894d  mov     edx, [rdx]
0x18000894f  test    edx, edx
0x180008951  jz      short loc_180008963
0x180008953  cmp     edx, 1
0x180008956  jnz     short loc_180008976
0x180008958  mov     rcx, [rdi+10h]
0x18000895c  call    EaLibFree
0x180008961  jmp     short loc_180008976
0x180008963  mov     edx, [rcx]
0x180008965  lea     rcx, [rdi+10h]; Source1
0x180008969  call    BriDeleteBrokeredEvent
0x18000896e  mov     qword ptr [rdi+10h], 0
0x180008976  mov     rbx, [rsp+28h+arg_0]
0x18000897b  xor     eax, eax
0x18000897d  add     rsp, 20h
0x180008981  pop     rdi
0x180008982  retn
```
