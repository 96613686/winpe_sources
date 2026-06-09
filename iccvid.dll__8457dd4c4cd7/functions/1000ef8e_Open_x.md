# Open(x)

- ea: `0x1000ef8e`
- end: `0x1000effb`
- name: `_Open@4`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x100093a0`

## callees

- `0x1000ef8e`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1000efda`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1000efda`

## pseudocode

```c
_DWORD *__thiscall Open(_DWORD *this)
{
  _DWORD *result; // eax

  if ( this[1] == 1667524982 )
  {
    if ( this[4] == 1 || this[4] == 2 || this[4] == 3 || this[4] == 4 || this[4] == 5 || this[4] == 8 )
    {
      result = LocalAlloc(0x40u, 0xA0u);
      if ( result )
      {
        *result = this[4];
        this[5] = 0;
      }
      else
      {
        this[5] = -3;
      }
    }
    else
    {
      this[5] = -100;
      return 0;
    }
  }
  else
  {
    this[5] = -100;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1000ef8e  mov     edi, edi
0x1000ef90  push    esi
0x1000ef91  mov     esi, ecx
0x1000ef93  cmp     dword ptr [esi+4], 63646976h
0x1000ef9a  jz      short loc_1000EFA7
0x1000ef9c  mov     dword ptr [esi+14h], 0FFFFFF9Ch
0x1000efa3  xor     eax, eax
0x1000efa5  pop     esi
0x1000efa6  retn
0x1000efa7  mov     eax, [esi+10h]
0x1000efaa  sub     eax, 1
0x1000efad  jz      short loc_1000EFD3
0x1000efaf  sub     eax, 1
0x1000efb2  jz      short loc_1000EFD3
0x1000efb4  sub     eax, 1
0x1000efb7  jz      short loc_1000EFD3
0x1000efb9  sub     eax, 1
0x1000efbc  jz      short loc_1000EFD3
0x1000efbe  sub     eax, 1
0x1000efc1  jz      short loc_1000EFD3
0x1000efc3  sub     eax, 3
0x1000efc6  jz      short loc_1000EFD3
0x1000efc8  mov     dword ptr [esi+14h], 0FFFFFF9Ch
0x1000efcf  xor     eax, eax
0x1000efd1  pop     esi
0x1000efd2  retn
0x1000efd3  push    0A0h; uBytes
0x1000efd8  push    40h ; '@'; uFlags
0x1000efda  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x1000efe0  test    eax, eax
0x1000efe2  jz      short loc_1000EFF2
0x1000efe4  mov     ecx, [esi+10h]
0x1000efe7  mov     [eax], ecx
0x1000efe9  mov     dword ptr [esi+14h], 0
0x1000eff0  pop     esi
0x1000eff1  retn
0x1000eff2  mov     dword ptr [esi+14h], 0FFFFFFFDh
0x1000eff9  pop     esi
0x1000effa  retn
```
