# HvStatsPageUtil::details::GetGroupTrait(_HV_STATS_OBJECT_TYPE,ushort)

- ea: `0x1800012c0`
- end: `0x180001349`
- name: `?GetGroupTrait@details@HvStatsPageUtil@@YA@W4_HV_STATS_OBJECT_TYPE@@G@Z`
- size: `137`
- prototype: `char *__fastcall(int, unsigned __int16)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800013a0`
- `0x180001540`
- `0x180001828`
- `0x1800072d4`

## callees

- `0x1800012c0`

## pseudocode

```c
char *__fastcall HvStatsPageUtil::details::GetGroupTrait(int a1, unsigned __int16 a2)
{
  __int64 v2; // rax
  __int64 v3; // r8
  __int64 v4; // rax

  v2 = 4;
  v3 = 4;
  if ( a1 != 65538 )
  {
    v2 = 3;
    if ( a1 != 65537 )
    {
      v2 = 2;
      if ( a1 != 2 )
        v2 = a1 == 1;
    }
  }
  v4 = v2 << 6;
  if ( *(_WORD *)&byte_18000B920[v4 + 52] != a2 )
  {
    v3 = 3;
    if ( *(_WORD *)&byte_18000B920[v4 + 40] != a2 )
    {
      v3 = 2;
      if ( *(_WORD *)&byte_18000B920[v4 + 28] != a2 )
        v3 = *(_WORD *)&byte_18000B920[v4 + 16] == a2;
    }
  }
  return (char *)&dword_18000B924[3 * v3] + v4;
}

```

## disassembly

```asm
0x1800012c0  mov     eax, 4
0x1800012c5  mov     r9d, ecx
0x1800012c8  mov     r8d, eax
0x1800012cb  cmp     ecx, 10002h
0x1800012d1  jnz     short loc_180001322
0x1800012d3  shl     rax, 6
0x1800012d7  lea     rcx, byte_18000B920
0x1800012de  cmp     [rax+rcx+34h], dx
0x1800012e3  jz      short loc_18000130F
0x1800012e5  mov     r8d, 3
0x1800012eb  cmp     [rax+rcx+28h], dx
0x1800012f0  jz      short loc_18000130F
0x1800012f2  mov     r8d, 2
0x1800012f8  cmp     [rax+rcx+1Ch], dx
0x1800012fd  jz      short loc_18000130F
0x1800012ff  mov     r8d, 1
0x180001305  cmp     [rax+rcx+10h], dx
0x18000130a  jz      short loc_18000130F
0x18000130c  xor     r8d, r8d
0x18000130f  lea     rcx, [r8+r8*2]
0x180001313  lea     rax, [rax+rcx*4]
0x180001317  lea     rcx, dword_18000B924
0x18000131e  add     rax, rcx
0x180001321  retn
0x180001322  mov     eax, 3
0x180001327  cmp     r9d, 10001h
0x18000132e  jz      short loc_1800012D3
0x180001330  mov     eax, 2
0x180001335  cmp     r9d, eax
0x180001338  jz      short loc_1800012D3
0x18000133a  mov     eax, 1
0x18000133f  xor     ecx, ecx
0x180001341  cmp     r9d, eax
0x180001344  cmovnz  eax, ecx
0x180001347  jmp     short loc_1800012D3
```
