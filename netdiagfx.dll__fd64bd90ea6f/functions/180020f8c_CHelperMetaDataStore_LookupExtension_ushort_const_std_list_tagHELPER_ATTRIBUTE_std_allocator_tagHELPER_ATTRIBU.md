# CHelperMetaDataStore::LookupExtension(ushort const *,std::list<tagHELPER_ATTRIBUTE,std::allocator<tagHELPER_ATTRIBUTE>> *)

- ea: `0x180020f8c`
- end: `0x18002108d`
- name: `?LookupExtension@CHelperMetaDataStore@@QEAAPEBVCExtensionHelperInfo@@PEBGPEAV?$list@UtagHELPER_ATTRIBUTE@@V?$allocator@UtagHELPER_ATTRIBUTE@@@std@@@std@@@Z`
- size: `257`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001dfa4`

## callees

- `0x180005048`
- `0x18001f418`
- `0x180020f8c`

## import_xrefs

- `KERNEL32!lstrcmpW` at `0x180020fed`
- `KERNEL32!lstrcmpW` at `0x180020fed`

## pseudocode

```c
__int64 __fastcall CHelperMetaDataStore::LookupExtension(__int64 a1, const WCHAR *a2, __m128i **a3)
{
  _QWORD *v6; // rbx
  __int64 v7; // rbp
  _QWORD *v8; // rdi
  __int64 v9; // rsi
  __int64 v10; // rcx
  _QWORD *i; // rax
  __int64 v12; // rcx
  _QWORD *j; // rax

  if ( a2 && a3 )
  {
    v6 = **(_QWORD ***)(a1 + 64);
    while ( v6 != *(_QWORD **)(a1 + 64) )
    {
      v7 = v6[5];
      if ( v7 )
      {
        v8 = **(_QWORD ***)(v7 + 8);
        while ( v8 != *(_QWORD **)(v7 + 8) )
        {
          v9 = v8[5];
          if ( v9 && !lstrcmpW(a2, *(LPCWSTR *)(v9 + 24)) && CExtensionHelperInfo::IsAttributesMatched(v9, a3) )
            return v9;
          if ( !*((_BYTE *)v8 + 25) )
          {
            v10 = v8[2];
            if ( *(_BYTE *)(v10 + 25) )
            {
              for ( i = (_QWORD *)v8[1]; !*((_BYTE *)i + 25) && v8 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
                v8 = i;
            }
            else
            {
              i = std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CExtensionHelperInfoContainer *>>>::_Min((_QWORD *)v10);
            }
            v8 = i;
          }
        }
      }
      if ( !*((_BYTE *)v6 + 25) )
      {
        v12 = v6[2];
        if ( *(_BYTE *)(v12 + 25) )
        {
          for ( j = (_QWORD *)v6[1]; !*((_BYTE *)j + 25) && v6 == (_QWORD *)j[2]; j = (_QWORD *)j[1] )
            v6 = j;
        }
        else
        {
          j = std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CExtensionHelperInfoContainer *>>>::_Min((_QWORD *)v12);
        }
        v6 = j;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180020f8c  push    rbx
0x180020f8e  push    rbp
0x180020f8f  push    rsi
0x180020f90  push    rdi
0x180020f91  push    r12
0x180020f93  push    r14
0x180020f95  push    r15
0x180020f97  sub     rsp, 20h
0x180020f9b  mov     r15, r8
0x180020f9e  mov     r12, rdx
0x180020fa1  mov     r14, rcx
0x180020fa4  test    rdx, rdx
0x180020fa7  jz      loc_18002107C
0x180020fad  test    r8, r8
0x180020fb0  jz      loc_18002107C
0x180020fb6  mov     rbx, [rcx+40h]
0x180020fba  mov     rbx, [rbx]
0x180020fbd  cmp     rbx, [r14+40h]
0x180020fc1  jz      loc_18002107C
0x180020fc7  mov     rbp, [rbx+28h]
0x180020fcb  test    rbp, rbp
0x180020fce  jz      short loc_18002103B
0x180020fd0  mov     rdi, [rbp+8]
0x180020fd4  mov     rdi, [rdi]
0x180020fd7  cmp     rdi, [rbp+8]
0x180020fdb  jz      short loc_18002103B
0x180020fdd  mov     rsi, [rdi+28h]
0x180020fe1  test    rsi, rsi
0x180020fe4  jz      short loc_180021006
0x180020fe6  mov     rdx, [rsi+18h]; lpString2
0x180020fea  mov     rcx, r12; lpString1
0x180020fed  call    cs:__imp_lstrcmpW
0x180020ff3  test    eax, eax
0x180020ff5  jnz     short loc_180021006
0x180020ff7  mov     rdx, r15
0x180020ffa  mov     rcx, rsi
0x180020ffd  call    ?IsAttributesMatched@CExtensionHelperInfo@@QEAA_NPEAV?$list@UtagHELPER_ATTRIBUTE@@V?$allocator@UtagHELPER_ATTRIBUTE@@@std@@@std@@@Z; CExtensionHelperInfo::IsAttributesMatched(std::list<tagHELPER_ATTRIBUTE> *)
0x180021002  test    al, al
0x180021004  jnz     short loc_180021077
0x180021006  cmp     byte ptr [rdi+19h], 0
0x18002100a  jnz     short loc_180020FD7
0x18002100c  mov     rcx, [rdi+10h]
0x180021010  cmp     byte ptr [rcx+19h], 0
0x180021014  jnz     short loc_18002101D
0x180021016  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfoContainer@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfoContainer@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfoContainer *>>>::_Min(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfoContainer *>,void *> *)
0x18002101b  jmp     short loc_180021036
0x18002101d  mov     rax, [rdi+8]
0x180021021  jmp     short loc_180021030
0x180021023  cmp     rdi, [rax+10h]
0x180021027  jnz     short loc_180021036
0x180021029  mov     rdi, rax
0x18002102c  mov     rax, [rax+8]
0x180021030  cmp     byte ptr [rax+19h], 0
0x180021034  jz      short loc_180021023
0x180021036  mov     rdi, rax
0x180021039  jmp     short loc_180020FD7
0x18002103b  cmp     byte ptr [rbx+19h], 0
0x18002103f  jnz     loc_180020FBD
0x180021045  mov     rcx, [rbx+10h]
0x180021049  cmp     byte ptr [rcx+19h], 0
0x18002104d  jnz     short loc_180021056
0x18002104f  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfoContainer@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfoContainer@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfoContainer *>>>::_Min(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfoContainer *>,void *> *)
0x180021054  jmp     short loc_18002106F
0x180021056  mov     rax, [rbx+8]
0x18002105a  jmp     short loc_180021069
0x18002105c  cmp     rbx, [rax+10h]
0x180021060  jnz     short loc_18002106F
0x180021062  mov     rbx, rax
0x180021065  mov     rax, [rax+8]
0x180021069  cmp     byte ptr [rax+19h], 0
0x18002106d  jz      short loc_18002105C
0x18002106f  mov     rbx, rax
0x180021072  jmp     loc_180020FBD
0x180021077  mov     rax, rsi
0x18002107a  jmp     short loc_18002107E
0x18002107c  xor     eax, eax
0x18002107e  add     rsp, 20h
0x180021082  pop     r15
0x180021084  pop     r14
0x180021086  pop     r12
0x180021088  pop     rdi
0x180021089  pop     rsi
0x18002108a  pop     rbp
0x18002108b  pop     rbx
0x18002108c  retn
```
