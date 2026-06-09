# XList<_IRP,168>::remove(_IRP *)

- ea: `0x1400126bc`
- end: `0x1400126f4`
- name: `?remove@?$XList@U_IRP@@$0KI@@@QEAAXPEAU_IRP@@@Z`
- size: `56`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400121e8`
- `0x140019e5c`
- `0x140021280`

## callees

- `0x1400126bc`

## pseudocode

```c
_QWORD *__fastcall XList<_IRP,168>::remove(__int64 a1, __int64 a2)
{
  _QWORD *v2; // rdx
  __int64 v3; // rcx
  _QWORD *result; // rax

  v2 = (_QWORD *)(a2 + 168);
  v3 = *v2;
  if ( *(_QWORD **)(*v2 + 8LL) != v2 || (result = (_QWORD *)v2[1], (_QWORD *)*result != v2) )
    __fastfail(3u);
  *result = v3;
  *(_QWORD *)(v3 + 8) = result;
  *v2 = 0;
  v2[1] = 0;
  return result;
}

```

## disassembly

```asm
0x1400126bc  add     rdx, 0A8h
0x1400126c3  mov     rcx, [rdx]
0x1400126c6  cmp     [rcx+8], rdx
0x1400126ca  jnz     short loc_1400126ED
0x1400126cc  mov     rax, [rdx+8]
0x1400126d0  cmp     [rax], rdx
0x1400126d3  jnz     short loc_1400126ED
0x1400126d5  mov     [rax], rcx
0x1400126d8  mov     [rcx+8], rax
0x1400126dc  mov     qword ptr [rdx], 0
0x1400126e3  mov     qword ptr [rdx+8], 0
0x1400126eb  retn
0x1400126ed  mov     ecx, 3
0x1400126f2  int     29h; Win8: RtlFailFast(ecx)
```
