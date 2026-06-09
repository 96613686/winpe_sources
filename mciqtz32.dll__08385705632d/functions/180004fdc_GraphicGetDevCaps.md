# GraphicGetDevCaps

- ea: `0x180004fdc`
- end: `0x1800050b9`
- name: `GraphicGetDevCaps`
- size: `221`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000485c`
- `0x1800062f8`

## callees

- `0x180004fdc`

## pseudocode

```c
__int64 __fastcall GraphicGetDevCaps(__int64 a1, __int16 a2, __int64 a3)
{
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  __int64 result; // rax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax

  if ( (a2 & 0x100) != 0 )
  {
    v3 = *(_DWORD *)(a3 + 12);
    if ( v3 <= 0x4001 )
    {
      if ( v3 != 16385 )
      {
        if ( v3 > 6 )
        {
          v8 = v3 - 7;
          if ( !v8 )
            goto LABEL_28;
          v9 = v8 - 1;
          if ( v9 )
          {
            v10 = v9 - 1;
            if ( v10 && v10 != 16375 )
              goto LABEL_15;
            goto LABEL_28;
          }
        }
        else if ( v3 != 6 )
        {
          v4 = v3 - 1;
          if ( v4 )
          {
            v5 = v4 - 1;
            if ( !v5 )
              goto LABEL_23;
            v6 = v5 - 1;
            if ( !v6 )
              goto LABEL_23;
            v7 = v6 - 1;
            if ( !v7 )
            {
              *(_DWORD *)(a3 + 8) = 34079240;
LABEL_24:
              result = 0x10000;
              goto LABEL_30;
            }
LABEL_22:
            if ( v7 == 1 )
              goto LABEL_23;
LABEL_15:
            result = 274;
            goto LABEL_30;
          }
LABEL_28:
          *(_DWORD *)(a3 + 8) = 34799616;
          goto LABEL_24;
        }
      }
LABEL_23:
      *(_DWORD *)(a3 + 8) = 34865153;
      goto LABEL_24;
    }
    if ( v3 > 0x4008 )
    {
      v15 = v3 - 16393;
      if ( !v15 )
        goto LABEL_23;
      if ( v15 != 247 )
        goto LABEL_15;
      goto LABEL_28;
    }
    if ( v3 == 16392 )
      goto LABEL_28;
    v12 = v3 - 16386;
    if ( !v12 )
      goto LABEL_28;
    v13 = v12 - 1;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        v7 = v14 - 1;
        if ( v7 )
          goto LABEL_22;
      }
      goto LABEL_28;
    }
    result = 0;
    *(_DWORD *)(a3 + 8) = 1;
  }
  else
  {
    result = 273;
  }
LABEL_30:
  if ( (a2 & 0x20) != 0 && !(_WORD)result )
  {
    result = 0;
    *(_DWORD *)(a3 + 8) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004fdc  xor     r9d, r9d
0x180004fdf  bt      edx, 8
0x180004fe3  jnb     loc_1800050A2
0x180004fe9  mov     eax, [r8+0Ch]
0x180004fed  mov     ecx, 4001h
0x180004ff2  cmp     eax, ecx
0x180004ff4  ja      short loc_18000503E
0x180004ff6  jz      short loc_180005064
0x180004ff8  cmp     eax, 6
0x180004ffb  ja      short loc_180005021
0x180004ffd  jz      short loc_180005064
0x180004fff  sub     eax, 1
0x180005002  jz      loc_180005098
0x180005008  sub     eax, 1
0x18000500b  jz      short loc_180005064
0x18000500d  sub     eax, 1
0x180005010  jz      short loc_180005064
0x180005012  sub     eax, 1
0x180005015  jnz     short loc_18000505F
0x180005017  mov     dword ptr [r8+8], 2080208h
0x18000501f  jmp     short loc_18000506C
0x180005021  sub     eax, 7
0x180005024  jz      short loc_180005098
0x180005026  sub     eax, 1
0x180005029  jz      short loc_180005064
0x18000502b  sub     eax, 1
0x18000502e  jz      short loc_180005098
0x180005030  cmp     eax, 3FF7h
0x180005035  jz      short loc_180005098
0x180005037  mov     eax, 112h
0x18000503c  jmp     short loc_1800050A7
0x18000503e  mov     ecx, 4008h
0x180005043  cmp     eax, ecx
0x180005045  ja      short loc_180005080
0x180005047  jz      short loc_180005098
0x180005049  sub     eax, 4002h
0x18000504e  jz      short loc_180005098
0x180005050  sub     eax, 1
0x180005053  jz      short loc_180005073
0x180005055  sub     eax, 1
0x180005058  jz      short loc_180005098
0x18000505a  sub     eax, 1
0x18000505d  jz      short loc_180005098
0x18000505f  cmp     eax, 1
0x180005062  jnz     short loc_180005037
0x180005064  mov     dword ptr [r8+8], 2140001h
0x18000506c  mov     eax, 10000h
0x180005071  jmp     short loc_1800050A7
0x180005073  mov     eax, r9d
0x180005076  mov     dword ptr [r8+8], 1
0x18000507e  jmp     short loc_1800050A7
0x180005080  sub     eax, 4009h
0x180005085  jz      short loc_180005064
0x180005087  sub     eax, 1
0x18000508a  jz      short loc_180005037
0x18000508c  sub     eax, 1
0x18000508f  jz      short loc_180005037
0x180005091  cmp     eax, 0F5h
0x180005096  jnz     short loc_180005037
0x180005098  mov     dword ptr [r8+8], 2130000h
0x1800050a0  jmp     short loc_18000506C
0x1800050a2  mov     eax, 111h
0x1800050a7  test    dl, 20h
0x1800050aa  jz      short locret_1800050B8
0x1800050ac  test    ax, ax
0x1800050af  jnz     short locret_1800050B8
0x1800050b1  mov     eax, r9d
0x1800050b4  mov     [r8+8], r9d
0x1800050b8  retn
```
