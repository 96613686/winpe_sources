# DestroyDynamicArray

- ea: `0x14000e634`
- end: `0x14000e6b6`
- name: `DestroyDynamicArray`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140001fec`
- `0x140007834`
- `0x140007be0`
- `0x140008320`
- `0x14000d8b4`
- `0x14000e718`
- `0x14000ebc8`

## callees

- `0x14000c9c0`
- `0x14000e634`
- `0x14000ebc8`

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
0x14000e634  mov     [rsp+arg_8], rbx
0x14000e639  mov     [rsp+arg_10], rsi
0x14000e63e  push    rdi
0x14000e63f  sub     rsp, 20h
0x14000e643  mov     rbx, [rcx]
0x14000e646  mov     rdi, rcx
0x14000e649  test    rbx, rbx
0x14000e64c  jz      short loc_14000E6A6
0x14000e64e  cmp     dword ptr [rbx], 9
0x14000e651  jnz     short loc_14000E6A6
0x14000e653  mov     rax, [rbx+8]
0x14000e657  mov     [rsp+28h+arg_0], rax
0x14000e65c  test    rax, rax
0x14000e65f  jz      short loc_14000E687
0x14000e661  mov     rsi, rax
0x14000e664  mov     rsi, [rsi+18h]
0x14000e668  mov     rcx, rax
0x14000e66b  call    __DynArrayFreeItemValue
0x14000e670  lea     rcx, [rsp+28h+arg_0]
0x14000e675  call    FreeMemory
0x14000e67a  mov     rax, rsi
0x14000e67d  mov     [rsp+28h+arg_0], rax
0x14000e682  test    rsi, rsi
0x14000e685  jnz     short loc_14000E664
0x14000e687  mov     rcx, rdi
0x14000e68a  mov     dword ptr [rbx+4], 0
0x14000e691  mov     qword ptr [rbx+8], 0
0x14000e699  mov     qword ptr [rbx+10h], 0
0x14000e6a1  call    FreeMemory
0x14000e6a6  mov     rbx, [rsp+28h+arg_8]
0x14000e6ab  mov     rsi, [rsp+28h+arg_10]
0x14000e6b0  add     rsp, 20h
0x14000e6b4  pop     rdi
0x14000e6b5  retn
```
