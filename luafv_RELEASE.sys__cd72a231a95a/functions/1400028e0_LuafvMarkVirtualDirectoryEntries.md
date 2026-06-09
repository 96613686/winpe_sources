# LuafvMarkVirtualDirectoryEntries

- ea: `0x1400028e0`
- end: `0x140002926`
- name: `LuafvMarkVirtualDirectoryEntries`
- size: `70`
- prototype: `__int64 __fastcall(char *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003140`
- `0x140016410`

## callees

- `0x1400028e0`

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
0x1400028e0  mov     edx, edx
0x1400028e2  add     rdx, rcx
0x1400028e5  or      r9, 0FFFFFFFFFFFFFFFFh
0x1400028e9  cmp     rdx, rcx
0x1400028ec  cmovnb  r9, rdx
0x1400028f0  sbb     r8d, r8d
0x1400028f3  and     r8d, 0C0000095h
0x1400028fa  cmp     rdx, rcx
0x1400028fd  jb      short loc_140002922
0x1400028ff  lea     rax, [rcx+48h]
0x140002903  cmp     rax, r9
0x140002906  ja      short loc_14000291D
0x140002908  bts     dword ptr [rcx+38h], 10h
0x14000290d  mov     eax, [rcx]
0x14000290f  test    eax, eax
0x140002911  jz      short loc_14000291D
0x140002913  add     rcx, rax
0x140002916  mov     [rsp+arg_0], rcx
0x14000291b  jmp     short loc_1400028FF
0x14000291d  jmp     short loc_140002922
0x14000291f  mov     r8d, eax
0x140002922  mov     eax, r8d
0x140002925  retn
```
