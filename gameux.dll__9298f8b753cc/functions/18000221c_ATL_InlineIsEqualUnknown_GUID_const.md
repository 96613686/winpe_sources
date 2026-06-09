# ATL::InlineIsEqualUnknown(_GUID const &)

- ea: `0x18000221c`
- end: `0x18000223f`
- name: `?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z`
- size: `35`
- prototype: `__int64 __fastcall(const struct _GUID *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e28`
- `0x1800021c0`
- `0x180002280`
- `0x180002a80`

## callees

- `0x18000221c`

## pseudocode

```c
_BOOL8 __fastcall ATL::InlineIsEqualUnknown(const struct _GUID *a1)
{
  _BOOL8 result; // rax

  result = 0;
  if ( !a1->Data1 && !*(_DWORD *)&a1->Data2 && *(_DWORD *)a1->Data4 == 192 )
    return *(_DWORD *)&a1->Data4[4] == 1174405120;
  return result;
}

```

## disassembly

```asm
0x18000221c  xor     eax, eax
0x18000221e  cmp     [rcx], eax
0x180002220  jnz     short locret_18000223E
0x180002222  cmp     [rcx+4], eax
0x180002225  jnz     short locret_18000223E
0x180002227  cmp     dword ptr [rcx+8], 0C0h
0x18000222e  jnz     short locret_18000223E
0x180002230  cmp     dword ptr [rcx+0Ch], 46000000h
0x180002237  jnz     short locret_18000223E
0x180002239  mov     eax, 1
0x18000223e  retn
```
