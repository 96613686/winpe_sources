# MupiApplyUncHardeningConfigurationEntryToPrefixEntry

- ea: `0x140015604`
- end: `0x140015658`
- name: `MupiApplyUncHardeningConfigurationEntryToPrefixEntry`
- size: `84`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140017f50`
- `0x140018570`
- `0x14001a920`

## callees

- `0x140015604`

## pseudocode

```c
__int64 __fastcall MupiApplyUncHardeningConfigurationEntryToPrefixEntry(_DWORD *a1, __int64 a2)
{
  int v2; // r10d
  int v3; // eax
  int v5; // r8d
  int v6; // edx
  int v7; // edx
  __int64 result; // rax

  v2 = a1[20];
  v3 = 0;
  if ( v2 <= 0 )
  {
    v5 = 0;
    v3 = v2 < 0;
  }
  else
  {
    v5 = 1;
  }
  v6 = a1[21];
  if ( v6 <= 0 )
  {
    if ( v6 < 0 )
      v3 |= 2u;
  }
  else
  {
    v5 |= 2u;
  }
  v7 = a1[22];
  if ( v7 <= 0 )
  {
    if ( v7 < 0 )
      v3 |= 4u;
  }
  else
  {
    v5 |= 4u;
  }
  result = v5 | *(_DWORD *)(a2 + 88) & (unsigned int)~v3;
  *(_DWORD *)(a2 + 88) = result;
  return result;
}

```

## disassembly

```asm
0x140015604  mov     r10d, [rcx+50h]
0x140015608  xor     eax, eax
0x14001560a  mov     r11, rdx
0x14001560d  test    r10d, r10d
0x140015610  jle     short loc_140015618
0x140015612  lea     r8d, [rax+1]
0x140015616  jmp     short loc_140015626
0x140015618  xor     r8d, r8d
0x14001561b  test    r10d, r10d
0x14001561e  lea     r9d, [r8+1]
0x140015622  cmovs   eax, r9d
0x140015626  mov     edx, [rcx+54h]
0x140015629  test    edx, edx
0x14001562b  jle     short loc_140015633
0x14001562d  or      r8d, 2
0x140015631  jmp     short loc_140015638
0x140015633  jns     short loc_140015638
0x140015635  or      eax, 2
0x140015638  mov     edx, [rcx+58h]
0x14001563b  test    edx, edx
0x14001563d  jle     short loc_140015645
0x14001563f  or      r8d, 4
0x140015643  jmp     short loc_14001564A
0x140015645  jns     short loc_14001564A
0x140015647  or      eax, 4
0x14001564a  not     eax
0x14001564c  and     eax, [r11+58h]
0x140015650  or      eax, r8d
0x140015653  mov     [r11+58h], eax
0x140015657  retn
```
