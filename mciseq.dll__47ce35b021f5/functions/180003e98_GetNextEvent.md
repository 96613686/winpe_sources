# GetNextEvent

- ea: `0x180003e98`
- end: `0x180003f11`
- name: `GetNextEvent`
- size: `121`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000484c`
- `0x1800048fc`
- `0x180005990`
- `0x180005a1c`
- `0x180005cd0`
- `0x180005d4c`

## callees

- `0x180003e98`

## pseudocode

```c
__int64 __fastcall GetNextEvent(__int64 a1)
{
  _DWORD *v1; // r10
  int v2; // r9d
  int v3; // r11d
  __int64 v4; // rdx
  _DWORD *i; // r8
  __int64 v6; // r8

  v1 = 0;
  v2 = 0;
  v3 = 0x7FFFFFFF;
  v4 = qword_18000A628[2 * *(unsigned int *)(a1 + 72)];
  for ( i = (_DWORD *)((v4 + 16) & -(__int64)(v4 != 0)); i; i = (_DWORD *)(v6 + 16) )
  {
    if ( !i[14] && i[1] < v3 )
    {
      if ( *i )
      {
        v2 = 1;
      }
      else
      {
        v3 = i[1];
        v1 = i;
      }
    }
    v6 = *((_QWORD *)i - 2);
    if ( !v6 )
      break;
  }
  *(_QWORD *)(a1 + 80) = v1;
  if ( v1 )
    return 256;
  else
    return (unsigned int)(v2 != 0) + 258;
}

```

## disassembly

```asm
0x180003e98  mov     eax, [rcx+48h]
0x180003e9b  lea     rdx, qword_18000A628
0x180003ea2  add     rax, rax
0x180003ea5  xor     r10d, r10d
0x180003ea8  xor     r9d, r9d
0x180003eab  mov     r11d, 7FFFFFFFh
0x180003eb1  mov     rdx, [rdx+rax*8]
0x180003eb5  lea     rax, [rdx+10h]
0x180003eb9  neg     rdx
0x180003ebc  sbb     r8, r8
0x180003ebf  and     r8, rax
0x180003ec2  jz      short loc_180003EF5
0x180003ec4  cmp     dword ptr [r8+38h], 0
0x180003ec9  jnz     short loc_180003EE6
0x180003ecb  cmp     [r8+4], r11d
0x180003ecf  jge     short loc_180003EE6
0x180003ed1  cmp     dword ptr [r8], 0
0x180003ed5  jz      short loc_180003EDF
0x180003ed7  mov     r9d, 1
0x180003edd  jmp     short loc_180003EE6
0x180003edf  mov     r11d, [r8+4]
0x180003ee3  mov     r10, r8
0x180003ee6  mov     r8, [r8-10h]
0x180003eea  test    r8, r8
0x180003eed  jz      short loc_180003EF5
0x180003eef  add     r8, 10h
0x180003ef3  jnz     short loc_180003EC4
0x180003ef5  mov     [rcx+50h], r10
0x180003ef9  test    r10, r10
0x180003efc  jnz     short loc_180003F0B
0x180003efe  neg     r9d
0x180003f01  sbb     eax, eax
0x180003f03  neg     eax
0x180003f05  add     eax, 102h
0x180003f0a  retn
0x180003f0b  mov     eax, 100h
0x180003f10  retn
```
