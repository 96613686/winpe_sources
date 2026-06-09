# LuafvReplaceElementTable

- ea: `0x14001fda4`
- end: `0x14001fdf1`
- name: `LuafvReplaceElementTable`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001de14`

## callees

- `0x14001fda4`

## pseudocode

```c
__int64 __fastcall LuafvReplaceElementTable(_QWORD *a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v3; // rax
  _QWORD *v4; // r10
  _QWORD *v5; // r9
  __int64 result; // rax

  v3 = (_QWORD *)*a2;
  v4 = (_QWORD *)a2[1];
  v5 = (_QWORD *)a2[2];
  if ( (_QWORD *)*a2 == a2 )
  {
    *a1 = a3;
    v3 = a3;
  }
  else if ( (_QWORD *)v3[1] == a2 )
  {
    v3[1] = a3;
  }
  else
  {
    v3[2] = a3;
  }
  *a3 = v3;
  if ( v4 )
    *v4 = a3;
  if ( v5 )
    *v5 = a3;
  a3[1] = a2[1];
  result = a2[2];
  a3[2] = result;
  return result;
}

```

## disassembly

```asm
0x14001fda4  mov     rax, [rdx]
0x14001fda7  mov     r10, [rdx+8]
0x14001fdab  mov     r9, [rdx+10h]
0x14001fdaf  cmp     rax, rdx
0x14001fdb2  jz      short loc_14001FDE3
0x14001fdb4  cmp     [rax+8], rdx
0x14001fdb8  jz      short loc_14001FDEB
0x14001fdba  mov     [rax+10h], r8
0x14001fdbe  mov     [r8], rax
0x14001fdc1  test    r10, r10
0x14001fdc4  jz      short loc_14001FDC9
0x14001fdc6  mov     [r10], r8
0x14001fdc9  test    r9, r9
0x14001fdcc  jz      short loc_14001FDD1
0x14001fdce  mov     [r9], r8
0x14001fdd1  mov     rax, [rdx+8]
0x14001fdd5  mov     [r8+8], rax
0x14001fdd9  mov     rax, [rdx+10h]
0x14001fddd  mov     [r8+10h], rax
0x14001fde1  retn
0x14001fde3  mov     [rcx], r8
0x14001fde6  mov     rax, r8
0x14001fde9  jmp     short loc_14001FDBE
0x14001fdeb  mov     [rax+8], r8
0x14001fdef  jmp     short loc_14001FDBE
```
