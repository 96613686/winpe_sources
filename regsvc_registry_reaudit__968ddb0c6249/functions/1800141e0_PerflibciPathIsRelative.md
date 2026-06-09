# PerflibciPathIsRelative

- ea: `0x1800141e0`
- end: `0x180014224`
- name: `PerflibciPathIsRelative`
- size: `68`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800136b0`

## callees

- `0x180008012`
- `0x1800141e0`

## pseudocode

```c
_BOOL8 __fastcall PerflibciPathIsRelative(wint_t *a1)
{
  wint_t v2; // cx
  _BOOL8 result; // rax

  result = 1;
  if ( a1 )
  {
    v2 = *a1;
    if ( v2 )
    {
      if ( v2 == 92 || iswalpha(v2) && a1[1] == 58 )
        return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800141e0  mov     [rsp+arg_0], rbx
0x1800141e5  push    rdi
0x1800141e6  sub     rsp, 20h
0x1800141ea  mov     rbx, rcx
0x1800141ed  test    rcx, rcx
0x1800141f0  jz      short loc_180014214
0x1800141f2  movzx   ecx, word ptr [rcx]; C
0x1800141f5  test    cx, cx
0x1800141f8  jz      short loc_180014214
0x1800141fa  cmp     cx, 5Ch ; '\'
0x1800141fe  jz      short loc_180014210
0x180014200  call    iswalpha
0x180014205  test    eax, eax
0x180014207  jz      short loc_180014214
0x180014209  cmp     word ptr [rbx+2], 3Ah ; ':'
0x18001420e  jnz     short loc_180014214
0x180014210  xor     eax, eax
0x180014212  jmp     short loc_180014219
0x180014214  mov     eax, 1
0x180014219  mov     rbx, [rsp+28h+arg_0]
0x18001421e  add     rsp, 20h
0x180014222  pop     rdi
0x180014223  retn
```
