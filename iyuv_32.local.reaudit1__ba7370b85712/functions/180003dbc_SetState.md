# SetState

- ea: `0x180003dbc`
- end: `0x180003dfc`
- name: `SetState`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002710`

## callees

- `0x180003dbc`

## pseudocode

```c
__int64 __fastcall SetState(__int64 a1, _OWORD *a2, unsigned int a3)
{
  __int64 result; // rax
  _OWORD *v4; // rcx

  result = 96;
  if ( a3 < 0x60 )
    return 0;
  v4 = *(_OWORD **)(a1 + 8);
  *v4 = *a2;
  v4[1] = a2[1];
  v4[2] = a2[2];
  v4[3] = a2[3];
  v4[4] = a2[4];
  v4[5] = a2[5];
  return result;
}

```

## disassembly

```asm
0x180003dbc  mov     eax, 60h ; '`'
0x180003dc1  cmp     r8d, eax
0x180003dc4  jnb     short loc_180003DC9
0x180003dc6  xor     eax, eax
0x180003dc8  retn
0x180003dc9  movups  xmm0, xmmword ptr [rdx]
0x180003dcc  mov     rcx, [rcx+8]
0x180003dd0  movups  xmmword ptr [rcx], xmm0
0x180003dd3  movups  xmm1, xmmword ptr [rdx+10h]
0x180003dd7  movups  xmmword ptr [rcx+10h], xmm1
0x180003ddb  movups  xmm0, xmmword ptr [rdx+20h]
0x180003ddf  movups  xmmword ptr [rcx+20h], xmm0
0x180003de3  movups  xmm1, xmmword ptr [rdx+30h]
0x180003de7  movups  xmmword ptr [rcx+30h], xmm1
0x180003deb  movups  xmm0, xmmword ptr [rdx+40h]
0x180003def  movups  xmmword ptr [rcx+40h], xmm0
0x180003df3  movups  xmm1, xmmword ptr [rdx+50h]
0x180003df7  movups  xmmword ptr [rcx+50h], xmm1
0x180003dfb  retn
```
