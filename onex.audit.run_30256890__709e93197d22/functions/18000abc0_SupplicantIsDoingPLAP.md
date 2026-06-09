# SupplicantIsDoingPLAP

- ea: `0x18000abc0`
- end: `0x18000abf4`
- name: `SupplicantIsDoingPLAP`
- size: `52`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180001510`
- `0x180002f64`
- `0x180009540`
- `0x18000a318`
- `0x18000a550`
- `0x180015f90`
- `0x1800167d4`
- `0x18001c80c`
- `0x18001d888`
- `0x18001e290`
- `0x180027ae4`
- `0x18002a22c`

## callees

- `0x18000abc0`

## pseudocode

```c
_BOOL8 __fastcall SupplicantIsDoingPLAP(__int64 a1)
{
  _BOOL8 result; // rax
  __int64 v2; // rax

  result = 0;
  if ( (*(_BYTE *)(*(_QWORD *)(a1 + 360) + 12LL) & 4) != 0 )
  {
    v2 = *(_QWORD *)(a1 + 408);
    if ( v2 )
    {
      if ( (*(_BYTE *)v2 & 2) != 0 && *(_QWORD *)(v2 + 24) && *(_DWORD *)(v2 + 16) )
        return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000abc0  mov     rax, [rcx+168h]
0x18000abc7  test    byte ptr [rax+0Ch], 4
0x18000abcb  jnz     short loc_18000ABD0
0x18000abcd  xor     eax, eax
0x18000abcf  retn
0x18000abd0  mov     rax, [rcx+198h]
0x18000abd7  test    rax, rax
0x18000abda  jz      short loc_18000ABCD
0x18000abdc  test    byte ptr [rax], 2
0x18000abdf  jz      short loc_18000ABCD
0x18000abe1  cmp     qword ptr [rax+18h], 0
0x18000abe6  jz      short loc_18000ABCD
0x18000abe8  cmp     dword ptr [rax+10h], 0
0x18000abec  jz      short loc_18000ABCD
0x18000abee  mov     eax, 1
0x18000abf3  retn
```
