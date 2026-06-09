# std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_hint<HWSecurityRegistryManager::RegKeys>(std::_Tree_node<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *> * const,HWSecurityRegistryManager::RegKeys const &)

- ea: `0x18001dec4`
- end: `0x18001e0ae`
- name: `??$_Find_hint@W4RegKeys@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@U?$less@W4RegKeys@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_hint_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@std@@@1@QEAU?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@1@AEBW4RegKeys@HWSecurityRegistryManager@@@Z`
- size: `490`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001dc0c`

## callees

- `0x18001dec4`
- `0x18001e2a4`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<enum HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_hint<enum HWSecurityRegistryManager::RegKeys>(
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
    if ( a3 == *(__int64 **)HWSecurityRegistryManager::m_RegKeyTable )
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
  v6 = (__int64 **)(HWSecurityRegistryManager::m_RegKeyTable + 16);
  if ( *(_BYTE *)(*(_QWORD *)(HWSecurityRegistryManager::m_RegKeyTable + 8) + 25LL)
    || (a1 = *v6, *((_DWORD *)*v6 + 8) < *a4) )
  {
    *(_QWORD *)v5 = *v6;
    *(_QWORD *)(v5 + 8) = 0;
    goto LABEL_5;
  }
LABEL_36:
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<enum HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegKeys>(
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
0x18001dec4  mov     [rsp+arg_0], rbx
0x18001dec9  push    rdi
0x18001deca  sub     rsp, 40h
0x18001dece  mov     rax, qword ptr cs:?m_RegKeyTable@HWSecurityRegistryManager@@0V?$map@W4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@U?$less@W4RegKeys@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@5@@std@@A; std::map<HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry> HWSecurityRegistryManager::m_RegKeyTable
0x18001ded5  xor     edi, edi
0x18001ded7  mov     r11, r9
0x18001deda  mov     r10, rdx
0x18001dedd  cmp     [r8+19h], dil
0x18001dee1  jz      short loc_18001DF22
0x18001dee3  lea     rdx, [rax+10h]
0x18001dee7  mov     rax, [rax+8]
0x18001deeb  cmp     [rax+19h], dil
0x18001deef  jnz     short loc_18001DF00
0x18001def1  mov     rcx, [rdx]
0x18001def4  mov     eax, [r9]
0x18001def7  cmp     [rcx+20h], eax
0x18001defa  jnb     loc_18001E016
0x18001df00  mov     rax, [rdx]
0x18001df03  mov     [r10], rax
0x18001df06  mov     [r10+8], rdi
0x18001df0a  mov     [r10+10h], dil
0x18001df0e  xor     eax, eax
0x18001df10  mov     [r10+11h], eax
0x18001df14  mov     [r10+15h], ax
0x18001df19  mov     [r10+17h], al
0x18001df1d  jmp     loc_18001E0A0
0x18001df22  cmp     r8, [rax]
0x18001df25  jnz     short loc_18001DF45
0x18001df27  mov     eax, [r8+20h]
0x18001df2b  cmp     [r9], eax
0x18001df2e  jnb     loc_18001E016
0x18001df34  mov     qword ptr [rdx+8], 1
0x18001df3c  mov     [rdx+10h], dil
0x18001df40  jmp     loc_18001E091
0x18001df45  mov     r9d, [r9]
0x18001df48  cmp     r9d, [r8+20h]
0x18001df4c  jnb     short loc_18001DFBB
0x18001df4e  mov     rax, [r8]
0x18001df51  cmp     [rax+19h], dil
0x18001df55  jz      short loc_18001DF80
0x18001df57  mov     rax, [r8+8]
0x18001df5b  mov     rcx, r8
0x18001df5e  jmp     short loc_18001DF6C
0x18001df60  cmp     rcx, [rax]
0x18001df63  jnz     short loc_18001DF72
0x18001df65  mov     rcx, rax
0x18001df68  mov     rax, [rax+8]
0x18001df6c  cmp     [rax+19h], dil
0x18001df70  jz      short loc_18001DF60
0x18001df72  cmp     [rcx+19h], dil
0x18001df76  cmovnz  rax, rcx
0x18001df7a  jmp     short loc_18001DF8A
0x18001df7c  mov     rax, [rax+10h]
0x18001df80  mov     rcx, [rax+10h]
0x18001df84  cmp     [rcx+19h], dil
0x18001df88  jz      short loc_18001DF7C
0x18001df8a  cmp     [rax+20h], r9d
0x18001df8e  jnb     loc_18001E016
0x18001df94  mov     rcx, [rax+10h]
0x18001df98  cmp     [rcx+19h], dil
0x18001df9c  mov     [rdx+10h], dil
0x18001dfa0  jz      short loc_18001DFAE
0x18001dfa2  mov     [rdx], rax
0x18001dfa5  mov     [rdx+8], rdi
0x18001dfa9  jmp     loc_18001E094
0x18001dfae  mov     qword ptr [rdx+8], 1
0x18001dfb6  jmp     loc_18001E091
0x18001dfbb  jbe     loc_18001E089
0x18001dfc1  mov     rcx, [r8+10h]
0x18001dfc5  mov     bl, [rcx+19h]
0x18001dfc8  test    bl, bl
0x18001dfca  jz      short loc_18001DFF2
0x18001dfcc  mov     rcx, [r8+8]
0x18001dfd0  cmp     [rcx+19h], dil
0x18001dfd4  jnz     loc_18001E063
0x18001dfda  mov     rax, r8
0x18001dfdd  cmp     rax, [rcx+10h]
0x18001dfe1  jnz     short loc_18001E00A
0x18001dfe3  mov     rax, rcx
0x18001dfe6  mov     rcx, [rcx+8]
0x18001dfea  cmp     [rcx+19h], dil
0x18001dfee  jz      short loc_18001DFDD
0x18001dff0  jmp     short loc_18001E00A
0x18001dff2  mov     rdx, [rcx]
0x18001dff5  cmp     [rdx+19h], dil
0x18001dff9  jnz     short loc_18001E00A
0x18001dffb  mov     rax, [rdx]
0x18001dffe  mov     rcx, rdx
0x18001e001  mov     rdx, rax
0x18001e004  cmp     [rax+19h], dil
0x18001e008  jz      short loc_18001DFFB
0x18001e00a  cmp     [rcx+19h], dil
0x18001e00e  jnz     short loc_18001E063
0x18001e010  cmp     r9d, [rcx+20h]
0x18001e014  jb      short loc_18001E063
0x18001e016  mov     r8, r11
0x18001e019  lea     rdx, [rsp+48h+var_28]
0x18001e01e  call    ??$_Find_lower_bound@W4RegKeys@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@U?$less@W4RegKeys@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@std@@@1@AEBW4RegKeys@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegKeys>(HWSecurityRegistryManager::RegKeys const &)
0x18001e023  mov     rcx, [rsp+48h+var_18]
0x18001e028  cmp     [rcx+19h], dil
0x18001e02c  jnz     short loc_18001E038
0x18001e02e  mov     eax, [rcx+20h]
0x18001e031  cmp     [r11], eax
0x18001e034  mov     al, 1
0x18001e036  jnb     short loc_18001E03B
0x18001e038  mov     al, dil
0x18001e03b  test    al, al
0x18001e03d  jz      short loc_18001E054
0x18001e03f  mov     [r10], rcx
0x18001e042  mov     qword ptr [r10+8], 2
0x18001e04a  mov     byte ptr [r10+10h], 1
0x18001e04f  jmp     loc_18001DF0E
0x18001e054  movups  xmm0, [rsp+48h+var_28]
0x18001e059  movdqu  xmmword ptr [r10], xmm0
0x18001e05e  jmp     loc_18001DF0A
0x18001e063  xor     eax, eax
0x18001e065  mov     [r10+10h], dil
0x18001e069  test    bl, bl
0x18001e06b  jz      short loc_18001E079
0x18001e06d  mov     [r10], r8
0x18001e070  mov     [r10+8], rdi
0x18001e074  jmp     loc_18001DF10
0x18001e079  mov     [r10], rcx
0x18001e07c  mov     qword ptr [r10+8], 1
0x18001e084  jmp     loc_18001DF10
0x18001e089  mov     [rdx+8], rdi
0x18001e08d  mov     byte ptr [rdx+10h], 1
0x18001e091  mov     [rdx], r8
0x18001e094  xor     eax, eax
0x18001e096  mov     [rdx+11h], eax
0x18001e099  mov     [rdx+15h], ax
0x18001e09d  mov     [rdx+17h], al
0x18001e0a0  mov     rbx, [rsp+48h+arg_0]
0x18001e0a5  mov     rax, r10
0x18001e0a8  add     rsp, 40h
0x18001e0ac  pop     rdi
0x18001e0ad  retn
```
