# ISAMDBDeleteVTDef(x,x)

- ea: `0x10014400`
- end: `0x1001445b`
- name: `_ISAMDBDeleteVTDef@8`
- size: `91`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x10011870`
- `0x100170e0`
- `0x100178b0`
- `0x10017ea0`
- `0x10018160`
- `0x10018200`

## callees

- `0x1000b200`
- `0x10014400`

## pseudocode

```c
int __stdcall ISAMDBDeleteVTDef(int a1, _DWORD *a2)
{
  _DWORD *v2; // ecx
  _DWORD *v3; // eax
  int v5; // eax
  _DWORD *v6; // eax
  _DWORD *v7; // esi

  v2 = 0;
  v3 = *(_DWORD **)(a1 + 8);
  if ( !v3 )
    return -1310;
  while ( v3 != a2 )
  {
    v2 = v3;
    v3 = (_DWORD *)*v3;
    if ( !v3 )
      return -1310;
  }
  v5 = *v3;
  if ( v2 )
    *v2 = v5;
  else
    *(_DWORD *)(a1 + 8) = v5;
  v6 = (_DWORD *)a2[140];
  if ( v6 )
  {
    do
    {
      v7 = (_DWORD *)*v6;
      MemFree(v6);
      v6 = v7;
    }
    while ( v7 );
  }
  MemFree(a2);
  return 0;
}

```

## disassembly

```asm
0x10014400  mov     edx, [esp+arg_0]
0x10014404  xor     ecx, ecx
0x10014406  push    edi
0x10014407  mov     eax, [edx+8]
0x1001440a  test    eax, eax
0x1001440c  jz      short loc_1001441E
0x1001440e  mov     edi, [esp+4+arg_4]
0x10014412  cmp     eax, edi
0x10014414  jz      short loc_10014427
0x10014416  mov     ecx, eax
0x10014418  mov     eax, [eax]
0x1001441a  test    eax, eax
0x1001441c  jnz     short loc_10014412
0x1001441e  mov     eax, 0FFFFFAE2h
0x10014423  pop     edi
0x10014424  retn    8
0x10014427  mov     eax, [eax]
0x10014429  test    ecx, ecx
0x1001442b  jnz     short loc_10014432
0x1001442d  mov     [edx+8], eax
0x10014430  jmp     short loc_10014434
0x10014432  mov     [ecx], eax
0x10014434  mov     eax, [edi+230h]
0x1001443a  test    eax, eax
0x1001443c  jz      short loc_1001444F
0x1001443e  push    esi
0x1001443f  nop
0x10014440  mov     esi, [eax]
0x10014442  push    eax
0x10014443  call    _MemFree@4; MemFree(x)
0x10014448  mov     eax, esi
0x1001444a  test    esi, esi
0x1001444c  jnz     short loc_10014440
0x1001444e  pop     esi
0x1001444f  push    edi
0x10014450  call    _MemFree@4; MemFree(x)
0x10014455  xor     eax, eax
0x10014457  pop     edi
0x10014458  retn    8
```
