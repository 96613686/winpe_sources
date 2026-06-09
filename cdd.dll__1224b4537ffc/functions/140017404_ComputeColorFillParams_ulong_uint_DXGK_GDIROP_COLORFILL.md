# ComputeColorFillParams(ulong,uint &,_DXGK_GDIROP_COLORFILL &)

- ea: `0x140017404`
- end: `0x140017491`
- name: `?ComputeColorFillParams@@YAHKAEAIAEAW4_DXGK_GDIROP_COLORFILL@@@Z`
- size: `141`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *, enum _DXGK_GDIROP_COLORFILL *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140005cc0`
- `0x140007b00`

## callees

- `0x140017404`

## pseudocode

```c
__int64 __fastcall ComputeColorFillParams(int a1, unsigned int *a2, enum _DXGK_GDIROP_COLORFILL *a3)
{
  if ( a1 == 1799 )
  {
    if ( *a2 != -1 )
    {
      *a3 = DXGK_GDIROPCF_PATINVERT;
      return 1;
    }
  }
  else
  {
    if ( a1 != 2570 )
    {
      switch ( a1 )
      {
        case 1542:
          *a3 = DXGK_GDIROPCF_DSTINVERT;
          break;
        case 257:
          break;
        case 1028:
          if ( *a2 != -1 )
          {
            *a2 = ~*a2 & 0xFFFFFF;
            return 1;
          }
          break;
        case 3341:
          if ( *a2 != -1 )
            return 1;
          break;
        case 4112:
          *a2 = 0xFFFFFF;
          return 1;
        default:
          return 0;
      }
      *a2 = 0;
      return 1;
    }
    if ( *a2 != -1 )
    {
      *a3 = DXGK_GDIROPCF_PDXN;
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140017404  cmp     ecx, 707h
0x14001740a  jnz     short loc_14001741F
0x14001740c  cmp     dword ptr [rdx], 0FFFFFFFFh
0x14001740f  jz      short loc_14001744C
0x140017411  mov     dword ptr [r8], 2
0x140017418  mov     eax, 1
0x14001741d  retn
0x14001741f  cmp     ecx, 0A0Ah
0x140017425  jnz     short loc_140017435
0x140017427  cmp     dword ptr [rdx], 0FFFFFFFFh
0x14001742a  jz      short loc_14001744C
0x14001742c  mov     dword ptr [r8], 3
0x140017433  jmp     short loc_140017418
0x140017435  cmp     ecx, 606h
0x14001743b  jnz     short loc_140017450
0x14001743d  mov     dword ptr [r8], 4
0x140017444  mov     dword ptr [rdx], 0
0x14001744a  jmp     short loc_140017418
0x14001744c  xor     eax, eax
0x14001744e  retn
0x140017450  cmp     ecx, 101h
0x140017456  jz      short loc_140017444
0x140017458  cmp     ecx, 404h
0x14001745e  jz      short loc_14001747F
0x140017460  cmp     ecx, 0D0Dh
0x140017466  jz      short loc_140017478
0x140017468  cmp     ecx, 1010h
0x14001746e  jnz     short loc_14001744C
0x140017470  mov     dword ptr [rdx], 0FFFFFFh
0x140017476  jmp     short loc_140017418
0x140017478  cmp     dword ptr [rdx], 0FFFFFFFFh
0x14001747b  jz      short loc_14001744C
0x14001747d  jmp     short loc_140017418
0x14001747f  mov     eax, [rdx]
0x140017481  cmp     eax, 0FFFFFFFFh
0x140017484  jz      short loc_14001744C
0x140017486  not     eax
0x140017488  and     eax, 0FFFFFFh
0x14001748d  mov     [rdx], eax
0x14001748f  jmp     short loc_140017418
```
