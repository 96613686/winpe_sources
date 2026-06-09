# UpdateStatisticsFromMiniport

- ea: `0x14000bd10`
- end: `0x14000bd48`
- name: `UpdateStatisticsFromMiniport`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140028f60`

## callees

- `0x14000bd10`

## pseudocode

```c
__int64 __fastcall UpdateStatisticsFromMiniport(int a1, unsigned int *a2, _DWORD *a3)
{
  __int64 result; // rax

  if ( a1 == 14 )
  {
    a3[38] = a2[3];
    a3[39] = a2[2];
  }
  else if ( a1 != 15 )
  {
    return result;
  }
  a3[26] = a2[1];
  result = *a2;
  a3[20] = result;
  return result;
}

```

## disassembly

```asm
0x14000bd10  cmp     ecx, 0Eh
0x14000bd13  jz      short loc_14000BD26
0x14000bd15  cmp     ecx, 0Fh
0x14000bd18  jnz     short locret_14000BD47
0x14000bd1a  sub     ecx, 0Eh
0x14000bd1d  jz      short loc_14000BD26
0x14000bd1f  cmp     ecx, 1
0x14000bd22  jnz     short locret_14000BD47
0x14000bd24  jmp     short loc_14000BD3A
0x14000bd26  mov     eax, [rdx+0Ch]
0x14000bd29  mov     [r8+98h], eax
0x14000bd30  mov     eax, [rdx+8]
0x14000bd33  mov     [r8+9Ch], eax
0x14000bd3a  mov     eax, [rdx+4]
0x14000bd3d  mov     [r8+68h], eax
0x14000bd41  mov     eax, [rdx]
0x14000bd43  mov     [r8+50h], eax
0x14000bd47  retn
```
