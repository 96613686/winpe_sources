# WdipDeleteParameter

- ea: `0x180009660`
- end: `0x1800096b6`
- name: `WdipDeleteParameter`
- size: `86`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180017b20`
- `0x180017d7c`
- `0x180018680`

## callees

- `0x180008ea0`
- `0x180009660`

## pseudocode

```c
__int64 __fastcall WdipDeleteParameter(_QWORD *a1)
{
  __int64 v1; // rdi
  __int64 v3; // rcx
  __int64 result; // rax

  if ( a1 )
  {
    v1 = *a1;
    if ( *a1 )
    {
      WdipFree(*(_QWORD *)(v1 + 48));
      v3 = *(_QWORD *)(v1 + 56);
      *(_QWORD *)(v1 + 48) = 0;
      WdipFree(v3);
      *(_QWORD *)(v1 + 56) = 0;
    }
    result = WdipFree(*a1);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009660  test    rcx, rcx
0x180009663  jz      short locret_1800096B5
0x180009665  mov     [rsp+arg_0], rbx
0x18000966a  push    rdi
0x18000966b  sub     rsp, 20h
0x18000966f  mov     rdi, [rcx]
0x180009672  mov     rbx, rcx
0x180009675  test    rdi, rdi
0x180009678  jz      short loc_18000969C
0x18000967a  mov     rcx, [rdi+30h]
0x18000967e  call    WdipFree
0x180009683  mov     rcx, [rdi+38h]
0x180009687  mov     qword ptr [rdi+30h], 0
0x18000968f  call    WdipFree
0x180009694  mov     qword ptr [rdi+38h], 0
0x18000969c  mov     rcx, [rbx]
0x18000969f  call    WdipFree
0x1800096a4  mov     qword ptr [rbx], 0
0x1800096ab  mov     rbx, [rsp+28h+arg_0]
0x1800096b0  add     rsp, 20h
0x1800096b4  pop     rdi
0x1800096b5  retn
```
