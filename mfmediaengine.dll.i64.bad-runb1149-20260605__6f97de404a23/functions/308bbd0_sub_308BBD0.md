# sub_308BBD0

- ea: `0x308bbd0`
- end: `0x308bbf1`
- name: `sub_308BBD0`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall sub_308BBD0(__int64 a1, __int64 a2, _DWORD *a3, _DWORD *a4)
{
  _DWORD *v4; // rax
  char v5; // bh
  bool v6; // cf

  v6 = __CFADD__((_DWORD)v4, *v4);
  *v4 += (_DWORD)v4;
  *a4 += (_DWORD)v4 + v6;
  LOBYTE(a3) = BYTE1(a4) + (_BYTE)a3;
  v6 = __CFADD__((_DWORD)v4, *v4);
  *v4 += (_DWORD)v4;
  *a3 += (_DWORD)v4 + v6;
  *(_BYTE *)(a2 + 285213058) += v5;
  *v4 += (_DWORD)v4;
  LOBYTE(v4) = MEMORY[0x134BD0002110001];
  *(_BYTE *)a4 += (_BYTE)a3;
  *v4 += (_DWORD)v4;
  __asm { iret }
}

```

## disassembly

```asm
0x308bbd0  push    rbx
0x308bbd1  add     [rax], eax
0x308bbd3  adc     [rcx], eax
0x308bbd5  add     dl, ch
0x308bbd7  add     [rax], eax
0x308bbd9  adc     [rdx], eax
0x308bbdb  add     [rsi+11000182h], bh
0x308bbe1  add     [rax], eax
0x308bbe3  mov     al, ds:134BD0002110001h
0x308bbec  add     [rcx], dl
0x308bbee  add     [rax], eax
0x308bbf0  iret
```
