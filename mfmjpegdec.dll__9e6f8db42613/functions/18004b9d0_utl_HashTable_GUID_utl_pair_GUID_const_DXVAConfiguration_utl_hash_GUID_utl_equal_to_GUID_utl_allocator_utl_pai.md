# utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_InsertAt(utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_InsertPosResult const &,utl::_HashNode<utl::pair<_GUID const,DXVAConfiguration>> *)

- ea: `0x18004b9d0`
- end: `0x18004ba6c`
- name: `?_InsertAt@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@utl@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@2@@2@AEBU_InsertPosResult@12@PEAU?$_HashNode@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@2@@Z`
- size: `156`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18004bd00`
- `0x18004c424`
- `0x18004e054`

## callees

- `0x18004b9d0`
- `0x18004ba74`

## pseudocode

```c
__int64 **__fastcall utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_InsertAt(
        __int64 a1,
        __int64 **a2,
        __int64 *a3,
        __int64 *a4)
{
  __int64 v4; // rax
  char v6; // cl
  __int64 v8; // rdx
  __int64 v9; // r10
  __int64 **v10; // rcx
  char v11; // cl

  v4 = *a3;
  v6 = *(_BYTE *)(a1 + 32);
  v8 = *(_QWORD *)(a1 + 16);
  v9 = 2 * (a3[1] & ((8LL << v6) - 1));
  if ( !*a3 )
  {
    *(_QWORD *)(v8 + 16 * (a3[1] & ((8LL << v6) - 1))) = a4;
    v4 = a1;
LABEL_6:
    *(_QWORD *)(v8 + 8 * v9 + 8) = a4;
    goto LABEL_7;
  }
  if ( *(_QWORD *)(v8 + 16 * (a3[1] & ((8LL << v6) - 1))) == v4 )
  {
    *(_QWORD *)(v8 + 16 * (a3[1] & ((8LL << v6) - 1))) = a4;
    goto LABEL_7;
  }
  if ( **(_QWORD **)(v8 + 16 * (a3[1] & ((8LL << v6) - 1)) + 8) == v4 )
    goto LABEL_6;
LABEL_7:
  a4[2] = a3[1];
  v10 = *(__int64 ***)(v4 + 8);
  a4[1] = (__int64)v10;
  *a4 = v4;
  *a2 = a4;
  *v10 = a4;
  *(_QWORD *)(v4 + 8) = a4;
  ++*(_QWORD *)(a1 + 24);
  v11 = *(_BYTE *)(a1 + 32);
  if ( (unsigned __int64)*(unsigned __int8 *)(a1 + 33) < *(_QWORD *)(a1 + 24) >> v11 )
    utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_Rehash(
      a1,
      v11 + 1);
  return a2;
}

```

## disassembly

```asm
0x18004b9d0  push    rbx
0x18004b9d2  sub     rsp, 20h
0x18004b9d6  mov     rax, [r8]
0x18004b9d9  mov     r11, rcx
0x18004b9dc  mov     cl, [rcx+20h]
0x18004b9df  mov     r10d, 8
0x18004b9e5  shl     r10, cl
0x18004b9e8  mov     rbx, rdx
0x18004b9eb  dec     r10
0x18004b9ee  and     r10, [r8+8]
0x18004b9f2  mov     rdx, [r11+10h]
0x18004b9f6  add     r10, r10
0x18004b9f9  test    rax, rax
0x18004b9fc  jnz     short loc_18004BA07
0x18004b9fe  mov     [rdx+r10*8], r9
0x18004ba02  mov     rax, r11
0x18004ba05  jmp     short loc_18004BA1D
0x18004ba07  cmp     [rdx+r10*8], rax
0x18004ba0b  jnz     short loc_18004BA13
0x18004ba0d  mov     [rdx+r10*8], r9
0x18004ba11  jmp     short loc_18004BA22
0x18004ba13  mov     rcx, [rdx+r10*8+8]
0x18004ba18  cmp     [rcx], rax
0x18004ba1b  jnz     short loc_18004BA22
0x18004ba1d  mov     [rdx+r10*8+8], r9
0x18004ba22  mov     rcx, [r8+8]
0x18004ba26  mov     [r9+10h], rcx
0x18004ba2a  mov     rcx, [rax+8]
0x18004ba2e  mov     [r9+8], rcx
0x18004ba32  mov     [r9], rax
0x18004ba35  mov     [rbx], r9
0x18004ba38  mov     [rcx], r9
0x18004ba3b  mov     [rax+8], r9
0x18004ba3f  inc     qword ptr [r11+18h]
0x18004ba43  mov     r8, [r11+18h]
0x18004ba47  mov     cl, [r11+20h]
0x18004ba4b  movzx   eax, byte ptr [r11+21h]
0x18004ba50  shr     r8, cl
0x18004ba53  cmp     rax, r8
0x18004ba56  jnb     short loc_18004BA63
0x18004ba58  lea     edx, [rcx+1]
0x18004ba5b  mov     rcx, r11
0x18004ba5e  call    ?_Rehash@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAA_NE@Z; utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_Rehash(uchar)
0x18004ba63  mov     rax, rbx
0x18004ba66  add     rsp, 20h
0x18004ba6a  pop     rbx
0x18004ba6b  retn
```
