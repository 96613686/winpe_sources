# DynArrayRemove

- ea: `0x14000f5c8`
- end: `0x14000f62f`
- name: `DynArrayRemove`
- size: `103`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1400080a4`
- `0x140008838`
- `0x14000e3bc`

## callees

- `0x14000d2d0`
- `0x14000f5c8`
- `0x14000f874`
- `0x14000f8e8`

## pseudocode

```c
__int64 __fastcall DynArrayRemove(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v3; // r10
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+40h] [rbp+18h] BYREF

  v7 = 0;
  result = _DynArrayGetItem(a1, a2, &v7);
  v8 = result;
  v4 = result;
  if ( result )
  {
    v5 = v7;
    v6 = *(_QWORD *)(result + 24);
    if ( v7 )
      *(_QWORD *)(v7 + 24) = v6;
    else
      *(_QWORD *)(v3 + 8) = v6;
    if ( v4 == *(_QWORD *)(v3 + 16) )
      *(_QWORD *)(v3 + 16) = v5;
    --*(_DWORD *)(v3 + 4);
    _DynArrayFreeItemValue();
    FreeMemory(&v8);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x14000f5c8  sub     rsp, 28h
0x14000f5cc  lea     r8, [rsp+28h+arg_0]
0x14000f5d1  mov     [rsp+28h+arg_0], 0
0x14000f5da  mov     r10, rcx
0x14000f5dd  call    __DynArrayGetItem
0x14000f5e2  mov     [rsp+28h+arg_10], rax
0x14000f5e7  mov     rcx, rax
0x14000f5ea  test    rax, rax
0x14000f5ed  jz      short loc_14000F629
0x14000f5ef  mov     rdx, [rsp+28h+arg_0]
0x14000f5f4  mov     rax, [rax+18h]
0x14000f5f8  test    rdx, rdx
0x14000f5fb  jz      short loc_14000F603
0x14000f5fd  mov     [rdx+18h], rax
0x14000f601  jmp     short loc_14000F607
0x14000f603  mov     [r10+8], rax
0x14000f607  cmp     rcx, [r10+10h]
0x14000f60b  jnz     short loc_14000F611
0x14000f60d  mov     [r10+10h], rdx
0x14000f611  dec     dword ptr [r10+4]
0x14000f615  call    __DynArrayFreeItemValue
0x14000f61a  lea     rcx, [rsp+28h+arg_10]
0x14000f61f  call    FreeMemory
0x14000f624  mov     eax, 1
0x14000f629  add     rsp, 28h
0x14000f62d  retn
```
