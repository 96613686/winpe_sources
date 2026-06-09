# AttemptToFreePage

- ea: `0x100259e1`
- end: `0x10025a41`
- name: `AttemptToFreePage`
- size: `96`
- prototype: `int __thiscall(_DWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x10007510`
- `0x1000daa0`
- `0x100175a0`
- `0x10025a47`
- `0x10025ab7`

## callees

- `0x10025797`
- `0x100259e1`

## pseudocode

```c
int __thiscall AttemptToFreePage(_DWORD *this)
{
  int v1; // eax
  int v2; // edx
  int v3; // edx
  int v4; // edx

  if ( this[1] != 8180 )
    return 0;
  v1 = dword_1003AE64;
  v2 = 0;
  while ( v1 && (_DWORD *)v1 != this )
  {
    v2 = v1;
    v1 = *(_DWORD *)(v1 + 8);
  }
  if ( v2 )
    *(_DWORD *)(v2 + 8) = this[2];
  else
    dword_1003AE64 = this[2];
  v3 = *(this - 1);
  if ( v3 )
    *(_DWORD *)(v3 + 8) = *(this - 2);
  else
    dword_1003AE60 = *(this - 2);
  v4 = *(this - 2);
  if ( v4 )
    *(_DWORD *)(v4 + 12) = *(this - 1);
  FreeSpace((HGLOBAL)*(this - 4));
  return 1;
}

```

## disassembly

```asm
0x100259e1  cmp     dword ptr [ecx+4], 1FF4h
0x100259e8  jnz     short loc_10025A3E
0x100259ea  mov     eax, dword_1003AE64
0x100259ef  xor     edx, edx
0x100259f1  jmp     short loc_100259FC
0x100259f3  cmp     eax, ecx
0x100259f5  jz      short loc_10025A00
0x100259f7  mov     edx, eax
0x100259f9  mov     eax, [eax+8]
0x100259fc  test    eax, eax
0x100259fe  jnz     short loc_100259F3
0x10025a00  mov     eax, [ecx+8]
0x10025a03  test    edx, edx
0x10025a05  jnz     short loc_10025A0E
0x10025a07  mov     dword_1003AE64, eax
0x10025a0c  jmp     short loc_10025A11
0x10025a0e  mov     [edx+8], eax
0x10025a11  mov     edx, [ecx-4]
0x10025a14  mov     eax, [ecx-8]
0x10025a17  test    edx, edx
0x10025a19  jz      short loc_10025A20
0x10025a1b  mov     [edx+8], eax
0x10025a1e  jmp     short loc_10025A25
0x10025a20  mov     dword_1003AE60, eax
0x10025a25  mov     edx, [ecx-8]
0x10025a28  test    edx, edx
0x10025a2a  jz      short loc_10025A32
0x10025a2c  mov     eax, [ecx-4]
0x10025a2f  mov     [edx+0Ch], eax
0x10025a32  mov     ecx, [ecx-10h]; hMem
0x10025a35  call    _FreeSpace@4; FreeSpace(x)
0x10025a3a  xor     eax, eax
0x10025a3c  inc     eax
0x10025a3d  retn
0x10025a3e  xor     eax, eax
0x10025a40  retn
```
