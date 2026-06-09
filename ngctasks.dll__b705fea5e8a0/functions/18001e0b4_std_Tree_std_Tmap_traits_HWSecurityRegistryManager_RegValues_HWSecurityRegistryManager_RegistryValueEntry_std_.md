# std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_hint<HWSecurityRegistryManager::RegValues>(std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * const,HWSecurityRegistryManager::RegValues const &)

- ea: `0x18001e0b4`
- end: `0x18001e29e`
- name: `??$_Find_hint@W4RegValues@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_hint_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@QEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@1@AEBW4RegValues@HWSecurityRegistryManager@@@Z`
- size: `490`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001dd0c`

## callees

- `0x18001e0b4`
- `0x18001e2fc`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<enum HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_hint<enum HWSecurityRegistryManager::RegValues>(
        __int64 *a1,
        __int64 a2,
        __int64 *a3,
        unsigned int *a4)
{
  __int64 v5; // r10
  __int64 **v6; // rdx
  unsigned int v7; // r9d
  __int64 *v8; // rax
  bool v9; // zf
  char v10; // bl
  __int64 *v11; // rax
  __int64 *v12; // rdx
  _DWORD *v13; // r11
  char v14; // al
  __int128 v16; // [rsp+20h] [rbp-28h] BYREF
  __int64 v17; // [rsp+30h] [rbp-18h]

  v5 = a2;
  if ( !*((_BYTE *)a3 + 25) )
  {
    if ( a3 == *(__int64 **)HWSecurityRegistryManager::m_RegValueTable )
    {
      if ( *a4 >= *((_DWORD *)a3 + 8) )
        goto LABEL_36;
      *(_QWORD *)(a2 + 8) = 1;
      *(_BYTE *)(a2 + 16) = 0;
      goto LABEL_46;
    }
    v7 = *a4;
    if ( v7 < *((_DWORD *)a3 + 8) )
    {
      v8 = (__int64 *)*a3;
      if ( *(_BYTE *)(*a3 + 25) )
      {
        v8 = (__int64 *)a3[1];
        a1 = a3;
        while ( !*((_BYTE *)v8 + 25) && a1 == (__int64 *)*v8 )
        {
          a1 = v8;
          v8 = (__int64 *)v8[1];
        }
        if ( *((_BYTE *)a1 + 25) )
          v8 = a1;
      }
      else
      {
        while ( 1 )
        {
          a1 = (__int64 *)v8[2];
          if ( *((_BYTE *)a1 + 25) )
            break;
          v8 = (__int64 *)v8[2];
        }
      }
      if ( *((_DWORD *)v8 + 8) >= v7 )
        goto LABEL_36;
      v9 = *(_BYTE *)(v8[2] + 25) == 0;
      *(_BYTE *)(a2 + 16) = 0;
      if ( !v9 )
      {
        *(_QWORD *)a2 = v8;
        *(_QWORD *)(a2 + 8) = 0;
LABEL_47:
        *(_DWORD *)(a2 + 17) = 0;
        *(_WORD *)(a2 + 21) = 0;
        *(_BYTE *)(a2 + 23) = 0;
        return v5;
      }
      *(_QWORD *)(a2 + 8) = 1;
LABEL_46:
      *(_QWORD *)a2 = a3;
      goto LABEL_47;
    }
    if ( v7 <= *((_DWORD *)a3 + 8) )
    {
      *(_QWORD *)(a2 + 8) = 0;
      *(_BYTE *)(a2 + 16) = 1;
      goto LABEL_46;
    }
    a1 = (__int64 *)a3[2];
    v10 = *((_BYTE *)a1 + 25);
    if ( v10 )
    {
      a1 = (__int64 *)a3[1];
      if ( *((_BYTE *)a1 + 25) )
        goto LABEL_42;
      v11 = a3;
      do
      {
        if ( v11 != (__int64 *)a1[2] )
          break;
        v11 = a1;
        a1 = (__int64 *)a1[1];
      }
      while ( !*((_BYTE *)a1 + 25) );
    }
    else
    {
      v12 = (__int64 *)*a1;
      if ( !*(_BYTE *)(*a1 + 25) )
      {
        do
        {
          a1 = v12;
          v12 = (__int64 *)*v12;
        }
        while ( !*((_BYTE *)v12 + 25) );
      }
    }
    if ( !*((_BYTE *)a1 + 25) && v7 >= *((_DWORD *)a1 + 8) )
      goto LABEL_36;
LABEL_42:
    *(_BYTE *)(v5 + 16) = 0;
    if ( v10 )
    {
      *(_QWORD *)v5 = a3;
      *(_QWORD *)(v5 + 8) = 0;
    }
    else
    {
      *(_QWORD *)v5 = a1;
      *(_QWORD *)(v5 + 8) = 1;
    }
    goto LABEL_6;
  }
  v6 = (__int64 **)(HWSecurityRegistryManager::m_RegValueTable + 16);
  if ( *(_BYTE *)(*(_QWORD *)(HWSecurityRegistryManager::m_RegValueTable + 8) + 25LL)
    || (a1 = *v6, *((_DWORD *)*v6 + 8) < *a4) )
  {
    *(_QWORD *)v5 = *v6;
    *(_QWORD *)(v5 + 8) = 0;
    goto LABEL_5;
  }
LABEL_36:
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<enum HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegValues>(
    a1,
    &v16,
    a4);
  if ( *(_BYTE *)(v17 + 25) || (v14 = 1, *v13 < *(_DWORD *)(v17 + 32)) )
    v14 = 0;
  if ( v14 )
  {
    *(_QWORD *)v5 = v17;
    *(_QWORD *)(v5 + 8) = 2;
    *(_BYTE *)(v5 + 16) = 1;
    goto LABEL_6;
  }
  *(_OWORD *)v5 = v16;
LABEL_5:
  *(_BYTE *)(v5 + 16) = 0;
LABEL_6:
  *(_DWORD *)(v5 + 17) = 0;
  *(_WORD *)(v5 + 21) = 0;
  *(_BYTE *)(v5 + 23) = 0;
  return v5;
}

```

## disassembly

```asm
0x18001e0b4  mov     [rsp+arg_0], rbx
0x18001e0b9  push    rdi
0x18001e0ba  sub     rsp, 40h
0x18001e0be  mov     rax, qword ptr cs:?m_RegValueTable@HWSecurityRegistryManager@@0V?$map@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@@std@@A; std::map<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry> HWSecurityRegistryManager::m_RegValueTable
0x18001e0c5  xor     edi, edi
0x18001e0c7  mov     r11, r9
0x18001e0ca  mov     r10, rdx
0x18001e0cd  cmp     [r8+19h], dil
0x18001e0d1  jz      short loc_18001E112
0x18001e0d3  lea     rdx, [rax+10h]
0x18001e0d7  mov     rax, [rax+8]
0x18001e0db  cmp     [rax+19h], dil
0x18001e0df  jnz     short loc_18001E0F0
0x18001e0e1  mov     rcx, [rdx]
0x18001e0e4  mov     eax, [r9]
0x18001e0e7  cmp     [rcx+20h], eax
0x18001e0ea  jnb     loc_18001E206
0x18001e0f0  mov     rax, [rdx]
0x18001e0f3  mov     [r10], rax
0x18001e0f6  mov     [r10+8], rdi
0x18001e0fa  mov     [r10+10h], dil
0x18001e0fe  xor     eax, eax
0x18001e100  mov     [r10+11h], eax
0x18001e104  mov     [r10+15h], ax
0x18001e109  mov     [r10+17h], al
0x18001e10d  jmp     loc_18001E290
0x18001e112  cmp     r8, [rax]
0x18001e115  jnz     short loc_18001E135
0x18001e117  mov     eax, [r8+20h]
0x18001e11b  cmp     [r9], eax
0x18001e11e  jnb     loc_18001E206
0x18001e124  mov     qword ptr [rdx+8], 1
0x18001e12c  mov     [rdx+10h], dil
0x18001e130  jmp     loc_18001E281
0x18001e135  mov     r9d, [r9]
0x18001e138  cmp     r9d, [r8+20h]
0x18001e13c  jnb     short loc_18001E1AB
0x18001e13e  mov     rax, [r8]
0x18001e141  cmp     [rax+19h], dil
0x18001e145  jz      short loc_18001E170
0x18001e147  mov     rax, [r8+8]
0x18001e14b  mov     rcx, r8
0x18001e14e  jmp     short loc_18001E15C
0x18001e150  cmp     rcx, [rax]
0x18001e153  jnz     short loc_18001E162
0x18001e155  mov     rcx, rax
0x18001e158  mov     rax, [rax+8]
0x18001e15c  cmp     [rax+19h], dil
0x18001e160  jz      short loc_18001E150
0x18001e162  cmp     [rcx+19h], dil
0x18001e166  cmovnz  rax, rcx
0x18001e16a  jmp     short loc_18001E17A
0x18001e16c  mov     rax, [rax+10h]
0x18001e170  mov     rcx, [rax+10h]
0x18001e174  cmp     [rcx+19h], dil
0x18001e178  jz      short loc_18001E16C
0x18001e17a  cmp     [rax+20h], r9d
0x18001e17e  jnb     loc_18001E206
0x18001e184  mov     rcx, [rax+10h]
0x18001e188  cmp     [rcx+19h], dil
0x18001e18c  mov     [rdx+10h], dil
0x18001e190  jz      short loc_18001E19E
0x18001e192  mov     [rdx], rax
0x18001e195  mov     [rdx+8], rdi
0x18001e199  jmp     loc_18001E284
0x18001e19e  mov     qword ptr [rdx+8], 1
0x18001e1a6  jmp     loc_18001E281
0x18001e1ab  jbe     loc_18001E279
0x18001e1b1  mov     rcx, [r8+10h]
0x18001e1b5  mov     bl, [rcx+19h]
0x18001e1b8  test    bl, bl
0x18001e1ba  jz      short loc_18001E1E2
0x18001e1bc  mov     rcx, [r8+8]
0x18001e1c0  cmp     [rcx+19h], dil
0x18001e1c4  jnz     loc_18001E253
0x18001e1ca  mov     rax, r8
0x18001e1cd  cmp     rax, [rcx+10h]
0x18001e1d1  jnz     short loc_18001E1FA
0x18001e1d3  mov     rax, rcx
0x18001e1d6  mov     rcx, [rcx+8]
0x18001e1da  cmp     [rcx+19h], dil
0x18001e1de  jz      short loc_18001E1CD
0x18001e1e0  jmp     short loc_18001E1FA
0x18001e1e2  mov     rdx, [rcx]
0x18001e1e5  cmp     [rdx+19h], dil
0x18001e1e9  jnz     short loc_18001E1FA
0x18001e1eb  mov     rax, [rdx]
0x18001e1ee  mov     rcx, rdx
0x18001e1f1  mov     rdx, rax
0x18001e1f4  cmp     [rax+19h], dil
0x18001e1f8  jz      short loc_18001E1EB
0x18001e1fa  cmp     [rcx+19h], dil
0x18001e1fe  jnz     short loc_18001E253
0x18001e200  cmp     r9d, [rcx+20h]
0x18001e204  jb      short loc_18001E253
0x18001e206  mov     r8, r11
0x18001e209  lea     rdx, [rsp+48h+var_28]
0x18001e20e  call    ??$_Find_lower_bound@W4RegValues@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@AEBW4RegValues@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegValues>(HWSecurityRegistryManager::RegValues const &)
0x18001e213  mov     rcx, [rsp+48h+var_18]
0x18001e218  cmp     [rcx+19h], dil
0x18001e21c  jnz     short loc_18001E228
0x18001e21e  mov     eax, [rcx+20h]
0x18001e221  cmp     [r11], eax
0x18001e224  mov     al, 1
0x18001e226  jnb     short loc_18001E22B
0x18001e228  mov     al, dil
0x18001e22b  test    al, al
0x18001e22d  jz      short loc_18001E244
0x18001e22f  mov     [r10], rcx
0x18001e232  mov     qword ptr [r10+8], 2
0x18001e23a  mov     byte ptr [r10+10h], 1
0x18001e23f  jmp     loc_18001E0FE
0x18001e244  movups  xmm0, [rsp+48h+var_28]
0x18001e249  movdqu  xmmword ptr [r10], xmm0
0x18001e24e  jmp     loc_18001E0FA
0x18001e253  xor     eax, eax
0x18001e255  mov     [r10+10h], dil
0x18001e259  test    bl, bl
0x18001e25b  jz      short loc_18001E269
0x18001e25d  mov     [r10], r8
0x18001e260  mov     [r10+8], rdi
0x18001e264  jmp     loc_18001E100
0x18001e269  mov     [r10], rcx
0x18001e26c  mov     qword ptr [r10+8], 1
0x18001e274  jmp     loc_18001E100
0x18001e279  mov     [rdx+8], rdi
0x18001e27d  mov     byte ptr [rdx+10h], 1
0x18001e281  mov     [rdx], r8
0x18001e284  xor     eax, eax
0x18001e286  mov     [rdx+11h], eax
0x18001e289  mov     [rdx+15h], ax
0x18001e28d  mov     [rdx+17h], al
0x18001e290  mov     rbx, [rsp+48h+arg_0]
0x18001e295  mov     rax, r10
0x18001e298  add     rsp, 40h
0x18001e29c  pop     rdi
0x18001e29d  retn
```
