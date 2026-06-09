# SvchostPushServiceGlobals

- ea: `0x180002e40`
- end: `0x180002e7d`
- name: `SvchostPushServiceGlobals`
- size: `61`
- prototype: `PVOID *__fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180002e40`
- `0x180004f04`

## pseudocode

```c
PVOID *__fastcall SvchostPushServiceGlobals(__int64 a1)
{
  PVOID *result; // rax

  qword_180028B48 = *(_QWORD *)(a1 + 192);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    return (PVOID *)WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
  return result;
}

```

## disassembly

```asm
0x180002e40  mov     rax, [rcx+0C0h]
0x180002e47  mov     cs:qword_180028B48, rax
0x180002e4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e55  lea     rax, WPP_GLOBAL_Control
0x180002e5c  cmp     rcx, rax
0x180002e5f  jz      short locret_180002E7C
0x180002e61  test    byte ptr [rcx+1Ch], 4
0x180002e65  jz      short locret_180002E7C
0x180002e67  mov     rcx, [rcx+10h]
0x180002e6b  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x180002e72  mov     edx, 37h ; '7'
0x180002e77  jmp     WPP_SF_
0x180002e7c  retn
```
