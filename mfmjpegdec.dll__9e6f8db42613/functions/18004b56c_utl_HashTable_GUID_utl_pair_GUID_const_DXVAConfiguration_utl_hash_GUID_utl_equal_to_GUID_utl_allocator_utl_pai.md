# utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_FindInsertPos(_GUID const &)

- ea: `0x18004b56c`
- end: `0x18004b69d`
- name: `?_FindInsertPos@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAA?AU_InsertPosResult@12@AEBU_GUID@@@Z`
- size: `305`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18004bd00`
- `0x18004c424`
- `0x18004e054`

## callees

- `0x18004b53c`
- `0x18004b56c`
- `0x18004b98c`

## pseudocode

```c
__int64 __fastcall utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_FindInsertPos(
        __int64 a1,
        __int64 a2,
        unsigned int *a3)
{
  unsigned __int64 v4; // rdi
  char v5; // cl
  __int64 v7; // r9
  __int64 v8; // rdx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rdi
  __int64 v11; // rax
  _QWORD *v12; // rcx
  _QWORD *v13; // rdx
  __int64 v14; // rax
  __int128 v16; // [rsp+20h] [rbp-28h]
  unsigned __int8 v17; // [rsp+30h] [rbp-18h]

  v4 = (unsigned __int64)*((unsigned __int8 *)a3 + 10) << 24;
  v5 = *(_BYTE *)(a1 + 32);
  *(_OWORD *)a2 = 0;
  v7 = *(_QWORD *)(a1 + 16);
  *(_QWORD *)(a2 + 16) = 0;
  v8 = 8LL << v5;
  v9 = *((unsigned __int16 *)a3 + 3) | ((unsigned __int64)*((unsigned __int16 *)a3 + 2) << 16);
  v10 = *a3 ^ v9 ^ (*((unsigned __int8 *)a3 + 15) | v4);
  if ( v7 )
  {
    v12 = *(_QWORD **)(v7 + 16 * (v10 & (v8 - 1)));
    if ( v12 )
    {
      v13 = **(_QWORD ***)(v7 + 16 * (v10 & (v8 - 1)) + 8);
      while ( v12 != v13 )
      {
        if ( v12[2] >= v10 )
        {
          if ( v12[2] > v10 )
            break;
          v14 = *(_QWORD *)a3 - v12[3];
          if ( *(_QWORD *)a3 == v12[3] )
            v14 = *((_QWORD *)a3 + 1) - v12[4];
          if ( !v14 )
          {
            *(_QWORD *)&v16 = v12;
            v17 = 2;
            goto LABEL_18;
          }
        }
        v12 = (_QWORD *)*v12;
      }
      *(_QWORD *)&v16 = v12;
    }
    else
    {
      *(_QWORD *)&v16 = 0;
    }
    v17 = 0;
LABEL_18:
    *((_QWORD *)&v16 + 1) = v10;
    *(_OWORD *)a2 = v16;
    *(_QWORD *)(a2 + 16) = v17;
  }
  else
  {
    v11 = utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_AllocBuckets(
            v9,
            v8);
    *(_QWORD *)(a1 + 16) = v11;
    if ( v11 )
    {
      utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_InitBuckets(a1);
      *(_QWORD *)(a2 + 8) = v10;
      *(_QWORD *)a2 = 0;
      *(_BYTE *)(a2 + 16) = 0;
      *(_DWORD *)(a2 + 17) = 0;
      *(_WORD *)(a2 + 21) = 0;
      *(_BYTE *)(a2 + 23) = 0;
    }
    else
    {
      *(_QWORD *)a2 = 0;
      *(_DWORD *)(a2 + 17) = 0;
      *(_WORD *)(a2 + 21) = 0;
      *(_BYTE *)(a2 + 23) = 0;
      *(_QWORD *)(a2 + 8) = v10;
      *(_BYTE *)(a2 + 16) = 1;
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18004b56c  push    rbp
0x18004b56e  push    rbx
0x18004b56f  push    rsi
0x18004b570  push    rdi
0x18004b571  mov     rbp, rsp
0x18004b574  sub     rsp, 48h
0x18004b578  movzx   edi, byte ptr [r8+0Ah]
0x18004b57d  xor     eax, eax
0x18004b57f  mov     rsi, rcx
0x18004b582  shl     rdi, 18h
0x18004b586  mov     cl, [rcx+20h]
0x18004b589  mov     rbx, rdx
0x18004b58c  xorps   xmm0, xmm0
0x18004b58f  movups  xmmword ptr [rdx], xmm0
0x18004b592  mov     r9, [rsi+10h]
0x18004b596  mov     [rdx+10h], rax
0x18004b59a  lea     edx, [rax+8]
0x18004b59d  movzx   eax, byte ptr [r8+0Fh]
0x18004b5a2  or      rdi, rax
0x18004b5a5  shl     rdx, cl
0x18004b5a8  movzx   eax, word ptr [r8+6]
0x18004b5ad  movzx   ecx, word ptr [r8+4]
0x18004b5b2  shl     rcx, 10h
0x18004b5b6  or      rcx, rax
0x18004b5b9  mov     eax, [r8]
0x18004b5bc  xor     rdi, rcx
0x18004b5bf  xor     rdi, rax
0x18004b5c2  test    r9, r9
0x18004b5c5  jnz     short loc_18004B615
0x18004b5c7  call    ?_AllocBuckets@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAAPEAU?$_HashBucket@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@2@_K@Z; utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_AllocBuckets(unsigned __int64)
0x18004b5cc  mov     [rsi+10h], rax
0x18004b5d0  test    rax, rax
0x18004b5d3  jz      short loc_18004B5FC
0x18004b5d5  mov     rcx, rsi
0x18004b5d8  call    ?_InitBuckets@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_InitBuckets(void)
0x18004b5dd  xor     eax, eax
0x18004b5df  mov     [rbx+8], rdi
0x18004b5e3  xor     cl, cl
0x18004b5e5  mov     [rbx], rax
0x18004b5e8  xor     edx, edx
0x18004b5ea  mov     [rbx+10h], cl
0x18004b5ed  mov     [rbx+11h], edx
0x18004b5f0  mov     [rbx+15h], dx
0x18004b5f4  mov     [rbx+17h], dl
0x18004b5f7  jmp     loc_18004B691
0x18004b5fc  xor     ecx, ecx
0x18004b5fe  mov     [rbx], rax
0x18004b601  mov     [rbx+11h], ecx
0x18004b604  mov     [rbx+15h], cx
0x18004b608  mov     [rbx+17h], cl
0x18004b60b  mov     [rbx+8], rdi
0x18004b60f  mov     byte ptr [rbx+10h], 1
0x18004b613  jmp     short loc_18004B691
0x18004b615  lea     rax, [rdx-1]
0x18004b619  and     rax, rdi
0x18004b61c  add     rax, rax
0x18004b61f  mov     rcx, [r9+rax*8]
0x18004b623  test    rcx, rcx
0x18004b626  jnz     short loc_18004B62E
0x18004b628  mov     qword ptr [rbp+var_28], rcx
0x18004b62c  jmp     short loc_18004B66C
0x18004b62e  mov     rax, [r9+rax*8+8]
0x18004b633  mov     rdx, [rax]
0x18004b636  cmp     rcx, rdx
0x18004b639  jz      short loc_18004B668
0x18004b63b  cmp     [rcx+10h], rdi
0x18004b63f  jb      short loc_18004B659
0x18004b641  ja      short loc_18004B668
0x18004b643  mov     rax, [r8]
0x18004b646  sub     rax, [rcx+18h]
0x18004b64a  jnz     short loc_18004B654
0x18004b64c  mov     rax, [r8+8]
0x18004b650  sub     rax, [rcx+20h]
0x18004b654  test    rax, rax
0x18004b657  jz      short loc_18004B65E
0x18004b659  mov     rcx, [rcx]
0x18004b65c  jmp     short loc_18004B636
0x18004b65e  mov     qword ptr [rbp+var_28], rcx
0x18004b662  mov     [rbp+var_18], 2
0x18004b666  jmp     short loc_18004B670
0x18004b668  mov     qword ptr [rbp+var_28], rcx
0x18004b66c  mov     [rbp+var_18], 0
0x18004b670  xor     eax, eax
0x18004b672  mov     qword ptr [rbp+var_28+8], rdi
0x18004b676  movups  xmm0, [rbp+var_28]
0x18004b67a  mov     dword ptr [rbp+var_18+1], eax
0x18004b67d  mov     word ptr [rbp+var_18+5], ax
0x18004b681  mov     [rbp+var_18+7], al
0x18004b684  movsd   xmm1, qword ptr [rbp+var_18]
0x18004b689  movups  xmmword ptr [rbx], xmm0
0x18004b68c  movsd   qword ptr [rbx+10h], xmm1
0x18004b691  mov     rax, rbx
0x18004b694  add     rsp, 48h
0x18004b698  pop     rdi
0x18004b699  pop     rsi
0x18004b69a  pop     rbx
0x18004b69b  pop     rbp
0x18004b69c  retn
```
