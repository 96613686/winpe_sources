# CreateLocationNode

- ea: `0x18002615c`
- end: `0x1800261a3`
- name: `CreateLocationNode`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025740`

## callees

- `0x180026058`
- `0x18002615c`

## pseudocode

```c
_QWORD *__fastcall CreateLocationNode(int a1, int a2, int a3)
{
  _QWORD *result; // rax
  _QWORD *v7; // r9
  _DWORD *v8; // rax

  result = DtlCreateSizedNode(0xCu);
  v7 = result;
  if ( result )
  {
    v8 = (_DWORD *)result[2];
    *v8 = a1;
    v8[1] = a2;
    v8[2] = a3;
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x18002615c  mov     [rsp+arg_0], rbx
0x180026161  mov     [rsp+arg_8], rsi
0x180026166  push    rdi
0x180026167  sub     rsp, 20h
0x18002616b  mov     esi, ecx
0x18002616d  mov     ebx, r8d
0x180026170  mov     ecx, 0Ch
0x180026175  mov     edi, edx
0x180026177  call    DtlCreateSizedNode
0x18002617c  mov     r9, rax
0x18002617f  test    rax, rax
0x180026182  jz      short loc_180026193
0x180026184  mov     rax, [rax+10h]
0x180026188  mov     [rax], esi
0x18002618a  mov     [rax+4], edi
0x18002618d  mov     [rax+8], ebx
0x180026190  mov     rax, r9
0x180026193  mov     rbx, [rsp+28h+arg_0]
0x180026198  mov     rsi, [rsp+28h+arg_8]
0x18002619d  add     rsp, 20h
0x1800261a1  pop     rdi
0x1800261a2  retn
```
