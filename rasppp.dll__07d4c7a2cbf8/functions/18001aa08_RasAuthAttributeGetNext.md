# RasAuthAttributeGetNext

- ea: `0x18001aa08`
- end: `0x18001aa2b`
- name: `RasAuthAttributeGetNext`
- size: `35`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `1`
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

- `0x18001aa08`

## pseudocode

```c
_DWORD *__fastcall RasAuthAttributeGetNext(_DWORD **a1, int a2)
{
  _DWORD *result; // rax

  result = *a1;
  if ( *a1 )
  {
    while ( 1 )
    {
      result += 4;
      if ( !*result )
        break;
      if ( *result == a2 )
      {
        *a1 = result;
        return result;
      }
    }
    *a1 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18001aa08  mov     rax, [rcx]
0x18001aa0b  test    rax, rax
0x18001aa0e  jz      short loc_18001AA28
0x18001aa10  add     rax, 10h
0x18001aa14  cmp     dword ptr [rax], 0
0x18001aa17  jz      short loc_18001AA21
0x18001aa19  cmp     [rax], edx
0x18001aa1b  jnz     short loc_18001AA10
0x18001aa1d  mov     [rcx], rax
0x18001aa20  retn
0x18001aa21  mov     qword ptr [rcx], 0
0x18001aa28  xor     eax, eax
0x18001aa2a  retn
```
