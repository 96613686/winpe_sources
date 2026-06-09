# ValidateHandle

- ea: `0x180003ec0`
- end: `0x180003f08`
- name: `ValidateHandle`
- size: `72`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `27`
- callee_count: `1`
- tags: ``

## callers

- `0x180001940`
- `0x180001f90`
- `0x180002400`
- `0x180002470`
- `0x180002540`
- `0x180002b00`
- `0x180002e70`
- `0x180003560`
- `0x1800037b0`
- `0x1800039a0`
- `0x180003b40`
- `0x180007ef0`
- `0x180008160`
- `0x1800089c0`
- `0x180008d00`
- `0x18000b2c0`
- `0x18000b360`
- `0x18000b420`
- `0x18000b8d0`
- `0x18000bca0`
- `0x18000c130`
- `0x18000ca28`
- `0x18000cfe0`
- `0x18000d7b0`
- `0x18000da50`
- `0x18000dde0`
- `0x18000de70`

## callees

- `0x180003ec0`

## pseudocode

```c
_BOOL8 __fastcall ValidateHandle(int *a1, int a2)
{
  int v2; // r8d

  if ( !a1 )
    return 0;
  v2 = *a1;
  if ( a2 )
    return a2 == v2;
  return v2 == 3 || (unsigned int)(v2 - 1) < 2;
}

```

## disassembly

```asm
0x180003ec0  sub     rsp, 18h
0x180003ec4  test    rcx, rcx
0x180003ec7  jz      short loc_180003F01
0x180003ec9  mov     r8d, [rcx]
0x180003ecc  test    edx, edx
0x180003ece  jz      short loc_180003EDA
0x180003ed0  xor     eax, eax
0x180003ed2  cmp     edx, r8d
0x180003ed5  setz    al
0x180003ed8  jmp     short loc_180003EF5
0x180003eda  cmp     r8d, 3
0x180003ede  jnz     short loc_180003EE7
0x180003ee0  mov     eax, 1
0x180003ee5  jmp     short loc_180003EF5
0x180003ee7  sub     r8d, 1
0x180003eeb  jz      short loc_180003EE0
0x180003eed  cmp     r8d, 1
0x180003ef1  jz      short loc_180003EE0
0x180003ef3  xor     eax, eax
0x180003ef5  mov     [rsp+18h+var_18], eax
0x180003ef8  jmp     short loc_180003EFC
0x180003efa  xor     eax, eax
0x180003efc  add     rsp, 18h
0x180003f00  retn
0x180003f01  xor     eax, eax
0x180003f03  add     rsp, 18h
0x180003f07  retn
```
