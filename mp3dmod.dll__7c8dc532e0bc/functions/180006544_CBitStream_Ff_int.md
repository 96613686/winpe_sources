# CBitStream::Ff(int)

- ea: `0x180006544`
- end: `0x18000656d`
- name: `?Ff@CBitStream@@QEAA_NH@Z`
- size: `41`
- prototype: `char __fastcall(CBitStream *this, int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000625c`
- `0x180006574`
- `0x180006628`
- `0x18000de5c`

## callees

- `0x180006544`

## pseudocode

```c
char __fastcall CBitStream::Ff(CBitStream *this, int a2)
{
  int v2; // r8d
  int v3; // r8d
  char v4; // dl

  if ( a2 <= 0 )
    return 0;
  v2 = *((_DWORD *)this + 9);
  *((_DWORD *)this + 8) += a2;
  v3 = a2 + v2;
  *((_DWORD *)this + 6) -= a2;
  v4 = 1;
  *((_DWORD *)this + 9) = (*((_DWORD *)this + 5) - 1) & v3;
  return v4;
}

```

## disassembly

```asm
0x180006544  test    edx, edx
0x180006546  jle     short loc_180006569
0x180006548  mov     r8d, [rcx+24h]
0x18000654c  add     [rcx+20h], edx
0x18000654f  add     r8d, edx
0x180006552  sub     [rcx+18h], edx
0x180006555  mov     edx, 1
0x18000655a  mov     eax, [rcx+14h]
0x18000655d  sub     eax, edx
0x18000655f  and     r8d, eax
0x180006562  mov     [rcx+24h], r8d
0x180006566  mov     al, dl
0x180006568  retn
0x180006569  xor     dl, dl
0x18000656b  jmp     short loc_180006566
```
