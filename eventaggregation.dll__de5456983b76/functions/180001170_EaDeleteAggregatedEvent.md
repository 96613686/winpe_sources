# EaDeleteAggregatedEvent

- ea: `0x180001170`
- end: `0x1800011d0`
- name: `EaDeleteAggregatedEvent`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001170`
- `0x1800011e0`
- `0x1800013a0`
- `0x180002000`

## pseudocode

```c
__int64 __fastcall EaDeleteAggregatedEvent(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  PVOID P; // [rsp+30h] [rbp+8h] BYREF

  P = 0;
  if ( !a1 )
    return 3221225485LL;
  LOBYTE(a2) = 1;
  result = EaiExtractEventAggregation(a1, a2, &P);
  if ( (int)result >= 0 )
  {
    result = EaDeleteAggregation(a1);
    if ( (int)result >= 0 )
      return EapDeleteAggregatedEvent(P);
  }
  return result;
}

```

## disassembly

```asm
0x180001170  mov     [rsp+arg_8], rbx
0x180001175  push    rdi
0x180001176  sub     rsp, 20h
0x18000117a  mov     [rsp+28h+P], 0
0x180001183  mov     edi, edx
0x180001185  mov     rbx, rcx
0x180001188  test    rcx, rcx
0x18000118b  jz      short loc_1800011C0
0x18000118d  lea     r8, [rsp+28h+P]
0x180001192  mov     dl, 1
0x180001194  call    EaiExtractEventAggregation
0x180001199  test    eax, eax
0x18000119b  js      short loc_1800011B5
0x18000119d  mov     rcx, rbx
0x1800011a0  call    EaDeleteAggregation
0x1800011a5  test    eax, eax
0x1800011a7  js      short loc_1800011B5
0x1800011a9  mov     rcx, [rsp+28h+P]; P
0x1800011ae  mov     edx, edi
0x1800011b0  call    EapDeleteAggregatedEvent
0x1800011b5  mov     rbx, [rsp+28h+arg_8]
0x1800011ba  add     rsp, 20h
0x1800011be  pop     rdi
0x1800011bf  retn
0x1800011c0  mov     rbx, [rsp+28h+arg_8]
0x1800011c5  mov     eax, 0C000000Dh
0x1800011ca  add     rsp, 20h
0x1800011ce  pop     rdi
0x1800011cf  retn
```
