# LuafvQueryCommonDirectoryClass

- ea: `0x140014008`
- end: `0x1400140ad`
- name: `LuafvQueryCommonDirectoryClass`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400240a0`

## callees

- `0x140014008`

## pseudocode

```c
void __fastcall LuafvQueryCommonDirectoryClass(int a1, _DWORD *a2, _DWORD *a3)
{
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx

  if ( a1 <= 60 )
  {
    if ( a1 == 60 )
    {
      *a2 = 88;
      goto LABEL_25;
    }
    v3 = a1 - 1;
    if ( !v3 )
    {
      *a2 = 64;
      goto LABEL_25;
    }
    v4 = v3 - 1;
    if ( !v4 )
    {
      *a2 = 68;
      goto LABEL_25;
    }
    v5 = v4 - 1;
    if ( !v5 )
    {
      *a2 = 94;
      goto LABEL_25;
    }
    v6 = v5 - 9;
    if ( !v6 )
    {
      *a2 = 12;
      *a3 = 8;
      return;
    }
    v7 = v6 - 25;
    if ( !v7 )
    {
      *a2 = 104;
      goto LABEL_25;
    }
    if ( v7 != 1 )
      return;
    goto LABEL_9;
  }
  v8 = a1 - 63;
  if ( !v8 )
  {
    *a2 = 114;
    goto LABEL_25;
  }
  v9 = v8 - 15;
  if ( !v9 )
  {
LABEL_9:
    *a2 = 80;
    goto LABEL_25;
  }
  v10 = v9 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      if ( v11 != 1 )
        return;
      *a2 = 122;
    }
    else
    {
      *a2 = 96;
    }
  }
  else
  {
    *a2 = 106;
  }
LABEL_25:
  *a3 = 60;
}

```

## disassembly

```asm
0x140014008  mov     r9d, 3Ch ; '<'
0x14001400e  cmp     ecx, r9d
0x140014011  jg      short loc_140014072
0x140014013  jz      short loc_14001406A
0x140014015  sub     ecx, 1
0x140014018  jz      short loc_140014062
0x14001401a  sub     ecx, 1
0x14001401d  jz      short loc_14001405A
0x14001401f  sub     ecx, 1
0x140014022  jz      short loc_140014052
0x140014024  sub     ecx, 9
0x140014027  jz      short loc_140014043
0x140014029  sub     ecx, 19h
0x14001402c  jz      short loc_14001403B
0x14001402e  cmp     ecx, 1
0x140014031  jnz     short locret_1400140AC
0x140014033  mov     dword ptr [rdx], 50h ; 'P'
0x140014039  jmp     short loc_1400140A9
0x14001403b  mov     dword ptr [rdx], 68h ; 'h'
0x140014041  jmp     short loc_1400140A9
0x140014043  mov     dword ptr [rdx], 0Ch
0x140014049  mov     dword ptr [r8], 8
0x140014050  retn
0x140014052  mov     dword ptr [rdx], 5Eh ; '^'
0x140014058  jmp     short loc_1400140A9
0x14001405a  mov     dword ptr [rdx], 44h ; 'D'
0x140014060  jmp     short loc_1400140A9
0x140014062  mov     dword ptr [rdx], 40h ; '@'
0x140014068  jmp     short loc_1400140A9
0x14001406a  mov     dword ptr [rdx], 58h ; 'X'
0x140014070  jmp     short loc_1400140A9
0x140014072  sub     ecx, 3Fh ; '?'
0x140014075  jz      short loc_1400140A3
0x140014077  sub     ecx, 0Fh
0x14001407a  jz      short loc_140014033
0x14001407c  sub     ecx, 1
0x14001407f  jz      short loc_14001409B
0x140014081  sub     ecx, 1
0x140014084  jz      short loc_140014093
0x140014086  cmp     ecx, 1
0x140014089  jnz     short locret_1400140AC
0x14001408b  mov     dword ptr [rdx], 7Ah ; 'z'
0x140014091  jmp     short loc_1400140A9
0x140014093  mov     dword ptr [rdx], 60h ; '`'
0x140014099  jmp     short loc_1400140A9
0x14001409b  mov     dword ptr [rdx], 6Ah ; 'j'
0x1400140a1  jmp     short loc_1400140A9
0x1400140a3  mov     dword ptr [rdx], 72h ; 'r'
0x1400140a9  mov     [r8], r9d
0x1400140ac  retn
```
