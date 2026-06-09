# RemoveCopyItem

- ea: `0x10016a10`
- end: `0x10016a69`
- name: `RemoveCopyItem`
- size: `89`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x100161d0`
- `0x10016280`
- `0x10016300`
- `0x10016380`
- `0x10016400`
- `0x10016480`
- `0x10016500`
- `0x10016580`
- `0x100165a0`
- `0x10016620`
- `0x100166e0`
- `0x10016760`
- `0x100167e0`

## callees

- `0x1000b200`
- `0x10016a10`

## pseudocode

```c
void __stdcall RemoveCopyItem(int a1, int a2)
{
  _DWORD *v2; // ecx
  _DWORD *v3; // esi
  int v4; // eax

  v2 = 0;
  v3 = *(_DWORD **)(a1 + 68);
  if ( v3 )
  {
    while ( v3[1] != *(_DWORD *)(a2 + 24) )
    {
      v2 = v3;
      v3 = (_DWORD *)*v3;
      if ( !v3 )
        return;
    }
    v4 = *v3;
    if ( v2 )
      *v2 = v4;
    else
      *(_DWORD *)(a1 + 68) = v4;
    if ( v3[2] == 12 )
      MemFree(v3[7]);
    if ( v3[2] == 9 )
      MemFree(v3[7]);
    MemFree(v3);
  }
}

```

## disassembly

```asm
0x10016a10  mov     edx, [esp+arg_0]
0x10016a14  xor     ecx, ecx
0x10016a16  push    esi
0x10016a17  mov     esi, [edx+44h]
0x10016a1a  test    esi, esi
0x10016a1c  jz      short loc_10016A65
0x10016a1e  mov     eax, [esp+4+arg_4]
0x10016a22  mov     eax, [eax+18h]
0x10016a25  cmp     [esi+4], eax
0x10016a28  jz      short loc_10016A36
0x10016a2a  mov     ecx, esi
0x10016a2c  mov     esi, [esi]
0x10016a2e  test    esi, esi
0x10016a30  jnz     short loc_10016A25
0x10016a32  pop     esi
0x10016a33  retn    8
0x10016a36  mov     eax, [esi]
0x10016a38  test    ecx, ecx
0x10016a3a  jnz     short loc_10016A41
0x10016a3c  mov     [edx+44h], eax
0x10016a3f  jmp     short loc_10016A43
0x10016a41  mov     [ecx], eax
0x10016a43  cmp     dword ptr [esi+8], 0Ch
0x10016a47  jnz     short loc_10016A51
0x10016a49  push    dword ptr [esi+1Ch]
0x10016a4c  call    _MemFree@4; MemFree(x)
0x10016a51  cmp     dword ptr [esi+8], 9
0x10016a55  jnz     short loc_10016A5F
0x10016a57  push    dword ptr [esi+1Ch]
0x10016a5a  call    _MemFree@4; MemFree(x)
0x10016a5f  push    esi
0x10016a60  call    _MemFree@4; MemFree(x)
0x10016a65  pop     esi
0x10016a66  retn    8
```
