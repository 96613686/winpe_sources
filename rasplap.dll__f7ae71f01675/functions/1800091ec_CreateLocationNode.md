# CreateLocationNode

- ea: `0x1800091ec`
- end: `0x180009233`
- name: `CreateLocationNode`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009784`

## callees

- `0x1800091ec`
- `0x18000ab44`

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
0x1800091ec  mov     [rsp+arg_0], rbx
0x1800091f1  mov     [rsp+arg_8], rsi
0x1800091f6  push    rdi
0x1800091f7  sub     rsp, 20h
0x1800091fb  mov     esi, ecx
0x1800091fd  mov     ebx, r8d
0x180009200  mov     ecx, 0Ch
0x180009205  mov     edi, edx
0x180009207  call    DtlCreateSizedNode
0x18000920c  mov     r9, rax
0x18000920f  test    rax, rax
0x180009212  jz      short loc_180009223
0x180009214  mov     rax, [rax+10h]
0x180009218  mov     [rax], esi
0x18000921a  mov     [rax+4], edi
0x18000921d  mov     [rax+8], ebx
0x180009220  mov     rax, r9
0x180009223  mov     rbx, [rsp+28h+arg_0]
0x180009228  mov     rsi, [rsp+28h+arg_8]
0x18000922d  add     rsp, 20h
0x180009231  pop     rdi
0x180009232  retn
```
