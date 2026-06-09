# LuafvMarkVirtualDirectoryEntries

- ea: `0x140002650`
- end: `0x140002696`
- name: `LuafvMarkVirtualDirectoryEntries`
- size: `70`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002f10`
- `0x140016410`

## callees

- `0x140002650`

## pseudocode

```c
__int64 __fastcall LuafvMarkVirtualDirectoryEntries(char *a1, int a2)
{
  char *v2; // rdx
  unsigned __int64 v3; // r9
  unsigned int v4; // r8d
  __int64 v5; // rax

  v2 = &a1[a2];
  v3 = -1;
  if ( v2 >= a1 )
    v3 = (unsigned __int64)v2;
  v4 = v2 < a1 ? 0xC0000095 : 0;
  if ( v2 >= a1 )
  {
    while ( (unsigned __int64)(a1 + 72) <= v3 )
    {
      *((_DWORD *)a1 + 14) |= 0x10000u;
      v5 = *(unsigned int *)a1;
      if ( !(_DWORD)v5 )
        break;
      a1 += v5;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x140002650  mov     edx, edx
0x140002652  add     rdx, rcx
0x140002655  or      r9, 0FFFFFFFFFFFFFFFFh
0x140002659  cmp     rdx, rcx
0x14000265c  cmovnb  r9, rdx
0x140002660  sbb     r8d, r8d
0x140002663  and     r8d, 0C0000095h
0x14000266a  cmp     rdx, rcx
0x14000266d  jb      short loc_140002692
0x14000266f  lea     rax, [rcx+48h]
0x140002673  cmp     rax, r9
0x140002676  ja      short loc_14000268D
0x140002678  bts     dword ptr [rcx+38h], 10h
0x14000267d  mov     eax, [rcx]
0x14000267f  test    eax, eax
0x140002681  jz      short loc_14000268D
0x140002683  add     rcx, rax
0x140002686  mov     [rsp+arg_0], rcx
0x14000268b  jmp     short loc_14000266F
0x14000268d  jmp     short loc_140002692
0x14000268f  mov     r8d, eax
0x140002692  mov     eax, r8d
0x140002695  retn
```
