# SetMMIOError

- ea: `0x180003514`
- end: `0x180003562`
- name: `SetMMIOError`
- size: `78`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003208`
- `0x180004318`

## callees

- `0x180003514`

## pseudocode

```c
__int64 __fastcall SetMMIOError(__int64 a1, int a2)
{
  int v2; // edx
  int v3; // edx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  __int64 result; // rax

  v2 = a2 - 257;
  if ( !v2 )
    goto LABEL_12;
  v3 = v2 - 1;
  if ( !v3 )
  {
    result = 264;
    goto LABEL_13;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
LABEL_12:
    result = 275;
    goto LABEL_13;
  }
  v5 = v4 - 2;
  if ( !v5 )
    goto LABEL_9;
  v6 = v5 - 1;
  if ( !v6 )
  {
LABEL_10:
    result = 349;
    goto LABEL_13;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
LABEL_9:
    result = 348;
    goto LABEL_13;
  }
  if ( v7 == 1 )
    goto LABEL_10;
  result = 296;
LABEL_13:
  *(_DWORD *)(a1 + 140) = result;
  return result;
}

```

## disassembly

```asm
0x180003514  sub     edx, 101h
0x18000351a  jz      short loc_180003556
0x18000351c  sub     edx, 1
0x18000351f  jz      short loc_18000354F
0x180003521  sub     edx, 1
0x180003524  jz      short loc_180003556
0x180003526  sub     edx, 2
0x180003529  jz      short loc_180003541
0x18000352b  sub     edx, 1
0x18000352e  jz      short loc_180003548
0x180003530  sub     edx, 1
0x180003533  jz      short loc_180003541
0x180003535  cmp     edx, 1
0x180003538  jz      short loc_180003548
0x18000353a  mov     eax, 128h
0x18000353f  jmp     short loc_18000355B
0x180003541  mov     eax, 15Ch
0x180003546  jmp     short loc_18000355B
0x180003548  mov     eax, 15Dh
0x18000354d  jmp     short loc_18000355B
0x18000354f  mov     eax, 108h
0x180003554  jmp     short loc_18000355B
0x180003556  mov     eax, 113h
0x18000355b  mov     [rcx+8Ch], eax
0x180003561  retn
```
