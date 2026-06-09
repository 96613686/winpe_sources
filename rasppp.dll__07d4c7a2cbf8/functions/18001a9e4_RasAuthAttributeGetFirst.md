# RasAuthAttributeGetFirst

- ea: `0x18001a9e4`
- end: `0x18001aa02`
- name: `RasAuthAttributeGetFirst`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18001016c`
- `0x180018e1c`
- `0x18001a4e8`
- `0x18001a704`
- `0x18001a7c0`
- `0x18001aa34`
- `0x18001b910`

## callees

- `0x18001a4bc`
- `0x18001a9e4`

## pseudocode

```c
_DWORD *__fastcall RasAuthAttributeGetFirst(int a1, __int64 a2)
{
  _DWORD *result; // rax
  _QWORD *v3; // r9

  result = RasAuthAttributeGet(a1, a2);
  if ( result )
    *v3 = result;
  else
    *v3 = 0;
  return result;
}

```

## disassembly

```asm
0x18001a9e4  sub     rsp, 28h
0x18001a9e8  mov     r9, r8
0x18001a9eb  call    RasAuthAttributeGet
0x18001a9f0  test    rax, rax
0x18001a9f3  jnz     short loc_18001A9FA
0x18001a9f5  mov     [r9], rax
0x18001a9f8  jmp     short loc_18001A9FD
0x18001a9fa  mov     [r9], rax
0x18001a9fd  add     rsp, 28h
0x18001aa01  retn
```
