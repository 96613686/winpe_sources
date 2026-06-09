# LuafvReplaceElementTable

- ea: `0x14001fd54`
- end: `0x14001fda1`
- name: `LuafvReplaceElementTable`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001ddc4`

## callees

- `0x14001fd54`

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
0x14001fd54  mov     rax, [rdx]
0x14001fd57  mov     r10, [rdx+8]
0x14001fd5b  mov     r9, [rdx+10h]
0x14001fd5f  cmp     rax, rdx
0x14001fd62  jz      short loc_14001FD93
0x14001fd64  cmp     [rax+8], rdx
0x14001fd68  jz      short loc_14001FD9B
0x14001fd6a  mov     [rax+10h], r8
0x14001fd6e  mov     [r8], rax
0x14001fd71  test    r10, r10
0x14001fd74  jz      short loc_14001FD79
0x14001fd76  mov     [r10], r8
0x14001fd79  test    r9, r9
0x14001fd7c  jz      short loc_14001FD81
0x14001fd7e  mov     [r9], r8
0x14001fd81  mov     rax, [rdx+8]
0x14001fd85  mov     [r8+8], rax
0x14001fd89  mov     rax, [rdx+10h]
0x14001fd8d  mov     [r8+10h], rax
0x14001fd91  retn
0x14001fd93  mov     [rcx], r8
0x14001fd96  mov     rax, r8
0x14001fd99  jmp     short loc_14001FD6E
0x14001fd9b  mov     [rax+8], r8
0x14001fd9f  jmp     short loc_14001FD6E
```
