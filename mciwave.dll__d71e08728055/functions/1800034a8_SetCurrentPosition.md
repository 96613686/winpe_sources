# SetCurrentPosition

- ea: `0x1800034a8`
- end: `0x18000350e`
- name: `SetCurrentPosition`
- size: `102`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003614`
- `0x180003d64`
- `0x18000492c`
- `0x1800050b0`
- `0x180005170`

## callees

- `0x1800034a8`

## pseudocode

```c
void __fastcall SetCurrentPosition(__int64 a1, unsigned int a2)
{
  __int64 v2; // r10
  unsigned int v4; // r9d
  unsigned int v5; // eax
  __int64 v6; // r11
  int v7; // ecx
  __int64 v8; // rax

  v2 = *(_QWORD *)(a1 + 104);
  if ( v2 )
  {
    v4 = *(_DWORD *)(a1 + 124);
    if ( a2 < v4 )
    {
      v5 = *(_DWORD *)(a1 + 116);
      v4 = 0;
      *(_QWORD *)(a1 + 120) = v5;
    }
    else
    {
      v5 = *(_DWORD *)(a1 + 120);
    }
    v6 = v2 + 16LL * v5;
    v7 = *(_DWORD *)(v6 + 4);
    while ( a2 > v4 + v7 )
    {
      v4 += *(_DWORD *)(v6 + 4);
      *(_DWORD *)(a1 + 124) = v4;
      v8 = *(unsigned int *)(v6 + 12);
      *(_DWORD *)(a1 + 120) = v8;
      v8 *= 2;
      v7 = *(_DWORD *)(v2 + 8 * v8 + 4);
      v6 = v2 + 8 * v8;
    }
    *(_DWORD *)(a1 + 68) = a2;
    *(_DWORD *)(a1 + 64) = a2;
  }
}

```

## disassembly

```asm
0x1800034a8  mov     r10, [rcx+68h]
0x1800034ac  mov     r8, rcx
0x1800034af  test    r10, r10
0x1800034b2  jz      short locret_18000350D
0x1800034b4  mov     r9d, [rcx+7Ch]
0x1800034b8  cmp     edx, r9d
0x1800034bb  jb      short loc_1800034C2
0x1800034bd  mov     eax, [rcx+78h]
0x1800034c0  jmp     short loc_1800034D2
0x1800034c2  mov     eax, [rcx+74h]
0x1800034c5  xor     r9d, r9d
0x1800034c8  mov     [rcx+78h], eax
0x1800034cb  mov     dword ptr [rcx+7Ch], 0
0x1800034d2  mov     r11d, eax
0x1800034d5  shl     r11, 4
0x1800034d9  add     r11, r10
0x1800034dc  mov     ecx, [r11+4]
0x1800034e0  jmp     short loc_1800034FE
0x1800034e2  add     r9d, [r11+4]
0x1800034e6  mov     [r8+7Ch], r9d
0x1800034ea  mov     eax, [r11+0Ch]
0x1800034ee  mov     [r8+78h], eax
0x1800034f2  add     rax, rax
0x1800034f5  mov     ecx, [r10+rax*8+4]
0x1800034fa  lea     r11, [r10+rax*8]
0x1800034fe  add     ecx, r9d
0x180003501  cmp     edx, ecx
0x180003503  ja      short loc_1800034E2
0x180003505  mov     [r8+44h], edx
0x180003509  mov     [r8+40h], edx
0x18000350d  retn
```
