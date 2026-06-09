# utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_Rehash(uchar)

- ea: `0x18004ba74`
- end: `0x18004bb4d`
- name: `?_Rehash@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAA_NE@Z`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004b9d0`
- `0x18004e054`

## callees

- `0x180043170`
- `0x18004b53c`
- `0x18004b98c`
- `0x18004ba74`

## pseudocode

```c
char __fastcall utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_Rehash(
        __int64 a1,
        unsigned __int8 a2)
{
  char v2; // bp
  __int64 v4; // rbx
  __int64 v5; // r14
  _QWORD *v6; // rax
  __int64 v7; // rsi
  __int64 v8; // r9
  _QWORD *v9; // rcx
  _QWORD *v10; // r11
  _QWORD *v11; // r14
  _QWORD *v12; // rdi
  __int64 v13; // r8
  _QWORD *v14; // r10
  _QWORD *v15; // r10
  _QWORD *v16; // rdx

  v2 = 0;
  v4 = a1;
  if ( a2 <= 0x38u )
  {
    LOBYTE(a1) = a2;
    v5 = utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_AllocBuckets(
           a1,
           8LL << a2);
    if ( v5 )
    {
      v2 = 1;
      utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_FreeBuckets(v4);
      *(_QWORD *)(v4 + 16) = v5;
      *(_BYTE *)(v4 + 32) = a2;
      utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_InitBuckets(v4);
      v6 = *(_QWORD **)v4;
      v7 = (8LL << *(_BYTE *)(v4 + 32)) - 1;
      while ( v6 != (_QWORD *)v4 )
      {
        v8 = *(_QWORD *)(v4 + 16);
        v9 = v6;
        v10 = (_QWORD *)*v6;
        v11 = v6;
        v12 = v6;
        v6 = (_QWORD *)*v6;
        v13 = 2 * (v7 & v9[2]);
        v14 = *(_QWORD **)(v8 + 16 * (v7 & v9[2]) + 8);
        if ( v14 )
        {
          v15 = (_QWORD *)*v14;
          if ( v15 != v9 )
          {
            v16 = (_QWORD *)v10[1];
            *(_QWORD *)v12[1] = v10;
            v10[1] = v12[1];
            v12[1] = v15[1];
            *(_QWORD *)v15[1] = v12;
            *v16 = v15;
            v15[1] = v16;
          }
        }
        else
        {
          *(_QWORD *)(v8 + 16 * (v7 & v9[2])) = v9;
        }
        *(_QWORD *)(v8 + 8 * v13 + 8) = v11;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18004ba74  push    rbx
0x18004ba76  push    rbp
0x18004ba77  push    rsi
0x18004ba78  push    rdi
0x18004ba79  push    r14
0x18004ba7b  sub     rsp, 20h
0x18004ba7f  xor     bpl, bpl
0x18004ba82  mov     dil, dl
0x18004ba85  mov     rbx, rcx
0x18004ba88  cmp     dl, 38h ; '8'
0x18004ba8b  ja      loc_18004BB3F
0x18004ba91  mov     cl, dl
0x18004ba93  mov     esi, 8
0x18004ba98  mov     edx, esi
0x18004ba9a  shl     rdx, cl
0x18004ba9d  call    ?_AllocBuckets@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAAPEAU?$_HashBucket@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@2@_K@Z; utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_AllocBuckets(unsigned __int64)
0x18004baa2  mov     r14, rax
0x18004baa5  test    rax, rax
0x18004baa8  jz      loc_18004BB3F
0x18004baae  mov     rcx, rbx
0x18004bab1  lea     ebp, [rsi-7]
0x18004bab4  call    ?_FreeBuckets@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_FreeBuckets(void)
0x18004bab9  mov     rcx, rbx
0x18004babc  mov     [rbx+10h], r14
0x18004bac0  mov     [rbx+20h], dil
0x18004bac4  call    ?_InitBuckets@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_InitBuckets(void)
0x18004bac9  mov     cl, [rbx+20h]
0x18004bacc  mov     rax, [rbx]
0x18004bacf  shl     rsi, cl
0x18004bad2  sub     rsi, rbp
0x18004bad5  cmp     rax, rbx
0x18004bad8  jz      short loc_18004BB3F
0x18004bada  mov     r9, [rbx+10h]
0x18004bade  mov     rcx, rax
0x18004bae1  mov     r11, [rax]
0x18004bae4  mov     r14, rax
0x18004bae7  mov     rdi, rax
0x18004baea  mov     rax, r11
0x18004baed  mov     r8, [rcx+10h]
0x18004baf1  and     r8, rsi
0x18004baf4  add     r8, r8
0x18004baf7  mov     r10, [r9+r8*8+8]
0x18004bafc  test    r10, r10
0x18004baff  jz      short loc_18004BB34
0x18004bb01  mov     r10, [r10]
0x18004bb04  cmp     r10, rcx
0x18004bb07  jz      short loc_18004BB38
0x18004bb09  mov     rcx, [rdi+8]
0x18004bb0d  mov     rdx, [r11+8]
0x18004bb11  mov     [rcx], r11
0x18004bb14  mov     rcx, [rdi+8]
0x18004bb18  mov     [r11+8], rcx
0x18004bb1c  mov     rcx, [r10+8]
0x18004bb20  mov     [rdi+8], rcx
0x18004bb24  mov     rcx, [r10+8]
0x18004bb28  mov     [rcx], rdi
0x18004bb2b  mov     [rdx], r10
0x18004bb2e  mov     [r10+8], rdx
0x18004bb32  jmp     short loc_18004BB38
0x18004bb34  mov     [r9+r8*8], rcx
0x18004bb38  mov     [r9+r8*8+8], r14
0x18004bb3d  jmp     short loc_18004BAD5
0x18004bb3f  mov     al, bpl
0x18004bb42  add     rsp, 20h
0x18004bb46  pop     r14
0x18004bb48  pop     rdi
0x18004bb49  pop     rsi
0x18004bb4a  pop     rbp
0x18004bb4b  pop     rbx
0x18004bb4c  retn
```
