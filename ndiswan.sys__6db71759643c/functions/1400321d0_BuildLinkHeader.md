# BuildLinkHeader

- ea: `0x1400321d0`
- end: `0x1400322f7`
- name: `BuildLinkHeader`
- size: `295`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140003970`
- `0x140030144`
- `0x140031b80`

## callees

- `0x1400321d0`

## pseudocode

```c
char __fastcall BuildLinkHeader(int *a1, _WORD *a2)
{
  int v2; // r10d
  int v3; // r9d
  int v4; // r8d
  _BYTE *v5; // r11
  int v6; // r8d
  int v7; // eax
  _BYTE *v8; // r11
  int v9; // edx

  v2 = *a1;
  v3 = 0;
  v4 = a1[3];
  v5 = a2;
  a1[16] = 0;
  a1[12] = 0;
  a1[8] = 0;
  a1[4] = 0;
  a1[2] = 0;
  if ( (v2 & 0x100) != 0 )
  {
    if ( (v2 & 0x200) == 0 )
    {
      *((_QWORD *)a1 + 3) = a2;
      v5 = a2 + 1;
      *a2 = 1023;
      a1[2] += 2;
      v3 = a1[2];
      a1[4] = 2;
    }
    if ( (v4 & 8) == 0 )
    {
      if ( (v4 & 1) != 0 && (v2 & 0x10) != 0 )
      {
        *((_QWORD *)a1 + 5) = v5;
        if ( (v2 & 0x400) == 0 )
        {
          *v5++ = 0;
          ++a1[8];
        }
        *v5 = 61;
        v8 = v5 + 1;
        v9 = a1[8] + 1;
        if ( (v2 & 0x20) == 0 )
        {
          v8 += 2;
          v9 = a1[8] + 3;
        }
        v5 = v8 + 2;
        a1[8] = v9 + 2;
        LOBYTE(v7) = v9 + 2;
        a1[2] += v9 + 2;
        v3 = a1[2];
      }
      if ( (v4 & 0x10) != 0 )
      {
        v6 = v4 & 6;
        if ( v6 )
        {
          *((_QWORD *)a1 + 7) = v5;
          if ( (v2 & 0x400) == 0 )
          {
            *v5++ = 0;
            ++a1[12];
          }
          *v5 = -3;
          v5 += 3;
          a1[12] += 3;
          v3 = a1[2] + a1[12];
        }
        *((_QWORD *)a1 + 9) = v5;
        LOBYTE(v7) = (v2 & 0x400) != 0;
        if ( ((v6 == 0) & (unsigned __int8)v7) == 0 )
          ++a1[16];
        ++a1[16];
        a1[2] = v3 + a1[16];
      }
    }
  }
  else if ( (v2 & 1) != 0 && (v4 & 6) != 0 )
  {
    *((_QWORD *)a1 + 7) = a2;
    *(_BYTE *)a2 = -3;
    a1[12] += 3;
    v7 = a1[12];
    a1[2] += v7;
  }
  return v7;
}

```

## disassembly

```asm
0x1400321d0  mov     r10d, [rcx]
0x1400321d3  xor     r9d, r9d
0x1400321d6  mov     r8d, [rcx+0Ch]
0x1400321da  mov     r11, rdx
0x1400321dd  mov     [rcx+40h], r9d
0x1400321e1  mov     [rcx+30h], r9d
0x1400321e5  mov     [rcx+20h], r9d
0x1400321e9  mov     [rcx+10h], r9d
0x1400321ed  mov     [rcx+8], r9d
0x1400321f1  bt      r10d, 8
0x1400321f6  jnb     short loc_14003225C
0x1400321f8  bt      r10d, 9
0x1400321fd  jb      short loc_14003221B
0x1400321ff  mov     [rcx+18h], rdx
0x140032203  lea     r11, [rdx+2]
0x140032207  mov     word ptr [rdx], 3FFh
0x14003220c  add     dword ptr [rcx+8], 2
0x140032210  mov     r9d, [rcx+8]
0x140032214  mov     dword ptr [rcx+10h], 2
0x14003221b  test    r8b, 8
0x14003221f  jnz     short locret_140032255
0x140032221  test    r8b, 1
0x140032225  jnz     short loc_1400322A6
0x140032227  test    r8b, 10h
0x14003222b  jz      short locret_140032255
0x14003222d  and     r8d, 6
0x140032231  jnz     short loc_14003227B
0x140032233  test    r8d, r8d
0x140032236  mov     [rcx+48h], r11
0x14003223a  setz    dl
0x14003223d  bt      r10d, 0Ah
0x140032242  setb    al
0x140032245  test    al, dl
0x140032247  jz      short loc_140032257
0x140032249  inc     dword ptr [rcx+40h]
0x14003224c  mov     edx, [rcx+40h]
0x14003224f  add     edx, r9d
0x140032252  mov     [rcx+8], edx
0x140032255  retn
0x140032257  inc     dword ptr [rcx+40h]
0x14003225a  jmp     short loc_140032249
0x14003225c  test    r10b, 1
0x140032260  jz      short locret_140032255
0x140032262  test    r8b, 6
0x140032266  jz      short locret_140032255
0x140032268  mov     [rcx+38h], rdx
0x14003226c  mov     byte ptr [rdx], 0FDh
0x14003226f  add     dword ptr [rcx+30h], 3
0x140032273  mov     eax, [rcx+30h]
0x140032276  add     [rcx+8], eax
0x140032279  retn
0x14003227b  mov     [rcx+38h], r11
0x14003227f  bt      r10d, 0Ah
0x140032284  jb      short loc_140032290
0x140032286  mov     byte ptr [r11], 0
0x14003228a  inc     r11
0x14003228d  inc     dword ptr [rcx+30h]
0x140032290  mov     byte ptr [r11], 0FDh
0x140032294  add     r11, 3
0x140032298  add     dword ptr [rcx+30h], 3
0x14003229c  mov     r9d, [rcx+30h]
0x1400322a0  add     r9d, [rcx+8]
0x1400322a4  jmp     short loc_140032233
0x1400322a6  test    r10b, 10h
0x1400322aa  jz      loc_140032227
0x1400322b0  mov     [rcx+28h], r11
0x1400322b4  bt      r10d, 0Ah
0x1400322b9  jb      short loc_1400322C5
0x1400322bb  mov     byte ptr [r11], 0
0x1400322bf  inc     r11
0x1400322c2  inc     dword ptr [rcx+20h]
0x1400322c5  mov     byte ptr [r11], 3Dh ; '='
0x1400322c9  inc     r11
0x1400322cc  mov     edx, [rcx+20h]
0x1400322cf  inc     edx
0x1400322d1  test    r10b, 20h
0x1400322d5  jnz     short loc_1400322DE
0x1400322d7  add     r11, 2
0x1400322db  add     edx, 2
0x1400322de  lea     eax, [rdx+2]
0x1400322e1  add     r11, 2
0x1400322e5  mov     [rcx+20h], eax
0x1400322e8  lea     eax, [rdx+2]
0x1400322eb  add     [rcx+8], eax
0x1400322ee  mov     r9d, [rcx+8]
0x1400322f2  jmp     loc_140032227
```
