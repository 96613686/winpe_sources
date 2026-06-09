# DestroyDynamicArray

- ea: `0x14000f2c4`
- end: `0x14000f347`
- name: `DestroyDynamicArray`
- size: `131`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002004`
- `0x140007cbc`
- `0x1400080a4`
- `0x140008838`
- `0x14000e3bc`
- `0x14000f3b0`
- `0x14000f874`

## callees

- `0x14000d2d0`
- `0x14000f2c4`
- `0x14000f874`

## pseudocode

```c
void __fastcall DestroyDynamicArray(void **a1)
{
  _QWORD *v1; // rbx
  void *v3; // rax
  _QWORD *v4; // rsi
  void *v5; // [rsp+30h] [rbp+8h] BYREF

  v1 = *a1;
  if ( *a1 && *(_DWORD *)v1 == 9 )
  {
    v3 = (void *)v1[1];
    v5 = v3;
    if ( v3 )
    {
      v4 = v3;
      do
      {
        v4 = (_QWORD *)v4[3];
        _DynArrayFreeItemValue(v3);
        FreeMemory(&v5);
        v3 = v4;
        v5 = v4;
      }
      while ( v4 );
    }
    *((_DWORD *)v1 + 1) = 0;
    v1[1] = 0;
    v1[2] = 0;
    FreeMemory(a1);
  }
}

```

## disassembly

```asm
0x14000f2c4  mov     [rsp+arg_8], rbx
0x14000f2c9  mov     [rsp+arg_10], rsi
0x14000f2ce  push    rdi
0x14000f2cf  sub     rsp, 20h
0x14000f2d3  mov     rbx, [rcx]
0x14000f2d6  mov     rdi, rcx
0x14000f2d9  test    rbx, rbx
0x14000f2dc  jz      short loc_14000F336
0x14000f2de  cmp     dword ptr [rbx], 9
0x14000f2e1  jnz     short loc_14000F336
0x14000f2e3  mov     rax, [rbx+8]
0x14000f2e7  mov     [rsp+28h+arg_0], rax
0x14000f2ec  test    rax, rax
0x14000f2ef  jz      short loc_14000F317
0x14000f2f1  mov     rsi, rax
0x14000f2f4  mov     rsi, [rsi+18h]
0x14000f2f8  mov     rcx, rax
0x14000f2fb  call    __DynArrayFreeItemValue
0x14000f300  lea     rcx, [rsp+28h+arg_0]
0x14000f305  call    FreeMemory
0x14000f30a  mov     rax, rsi
0x14000f30d  mov     [rsp+28h+arg_0], rax
0x14000f312  test    rsi, rsi
0x14000f315  jnz     short loc_14000F2F4
0x14000f317  mov     rcx, rdi
0x14000f31a  mov     dword ptr [rbx+4], 0
0x14000f321  mov     qword ptr [rbx+8], 0
0x14000f329  mov     qword ptr [rbx+10h], 0
0x14000f331  call    FreeMemory
0x14000f336  mov     rbx, [rsp+28h+arg_8]
0x14000f33b  mov     rsi, [rsp+28h+arg_10]
0x14000f340  add     rsp, 20h
0x14000f344  pop     rdi
0x14000f345  retn
```
