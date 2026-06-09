# DynArrayRemove

- ea: `0x14000e928`
- end: `0x14000e98e`
- name: `DynArrayRemove`
- size: `102`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140007be0`
- `0x140008320`
- `0x14000d8b4`

## callees

- `0x14000c9c0`
- `0x14000e928`
- `0x14000ebc8`
- `0x14000ec3c`

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
0x14000e928  sub     rsp, 28h
0x14000e92c  lea     r8, [rsp+28h+arg_0]
0x14000e931  mov     [rsp+28h+arg_0], 0
0x14000e93a  mov     r10, rcx
0x14000e93d  call    __DynArrayGetItem
0x14000e942  mov     [rsp+28h+arg_10], rax
0x14000e947  mov     rcx, rax
0x14000e94a  test    rax, rax
0x14000e94d  jz      short loc_14000E989
0x14000e94f  mov     rdx, [rsp+28h+arg_0]
0x14000e954  mov     rax, [rax+18h]
0x14000e958  test    rdx, rdx
0x14000e95b  jz      short loc_14000E963
0x14000e95d  mov     [rdx+18h], rax
0x14000e961  jmp     short loc_14000E967
0x14000e963  mov     [r10+8], rax
0x14000e967  cmp     rcx, [r10+10h]
0x14000e96b  jnz     short loc_14000E971
0x14000e96d  mov     [r10+10h], rdx
0x14000e971  dec     dword ptr [r10+4]
0x14000e975  call    __DynArrayFreeItemValue
0x14000e97a  lea     rcx, [rsp+28h+arg_10]
0x14000e97f  call    FreeMemory
0x14000e984  mov     eax, 1
0x14000e989  add     rsp, 28h
0x14000e98d  retn
```
