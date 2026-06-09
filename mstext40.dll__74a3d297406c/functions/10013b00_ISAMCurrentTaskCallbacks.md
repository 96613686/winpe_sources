# ISAMCurrentTaskCallbacks()

- ea: `0x10013b00`
- end: `0x10013b21`
- name: `_ISAMCurrentTaskCallbacks@0`
- size: `33`
- prototype: `_DWORD __stdcall()`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1000a1d0`
- `0x1000a1f0`
- `0x1000a260`
- `0x1000a350`

## callees

- `0x1000bf60`
- `0x10013b00`

## pseudocode

```c
int __stdcall ISAMCurrentTaskCallbacks()
{
  DWORD v0; // ecx
  _DWORD *v1; // eax

  v0 = CurrentTaskHandle();
  v1 = (_DWORD *)dword_10040FBC;
  if ( dword_10040FBC )
  {
    while ( v1[4] != v0 )
    {
      v1 = (_DWORD *)*v1;
      if ( !v1 )
        goto LABEL_4;
    }
  }
  else
  {
LABEL_4:
    v1 = 0;
  }
  return v1[7];
}

```

## disassembly

```asm
0x10013b00  call    _CurrentTaskHandle@0; CurrentTaskHandle()
0x10013b05  mov     ecx, eax
0x10013b07  mov     eax, dword_10040FBC
0x10013b0c  test    eax, eax
0x10013b0e  jz      short loc_10013B1B
0x10013b10  cmp     [eax+10h], ecx
0x10013b13  jz      short loc_10013B1D
0x10013b15  mov     eax, [eax]
0x10013b17  test    eax, eax
0x10013b19  jnz     short loc_10013B10
0x10013b1b  xor     eax, eax
0x10013b1d  mov     eax, [eax+1Ch]
0x10013b20  retn
```
