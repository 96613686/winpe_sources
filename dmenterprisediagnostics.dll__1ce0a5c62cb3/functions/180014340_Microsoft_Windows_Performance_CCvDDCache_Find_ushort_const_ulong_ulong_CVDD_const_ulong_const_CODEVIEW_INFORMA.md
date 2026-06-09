# Microsoft::Windows::Performance::CCvDDCache::Find(ushort const *,ulong,ulong *,_CVDD const * *,ulong const * *,CODEVIEW_INFORMATION_1 const * *,ulong *,ulong *,EMBEDDED_PDB_INFORMATION &,bool &,ushort *,ulong)

- ea: `0x180014340`
- end: `0x1800144ac`
- name: `?Find@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGKPEAKPEAPEBT_CVDD@@PEAPEBKPEAPEBUCODEVIEW_INFORMATION_1@@11AEAUEMBEDDED_PDB_INFORMATION@@AEA_NPEAGK@Z`
- size: `364`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CCvDDCache *__hidden this, const unsigned __int16 *, unsigned int, unsigned int *, const union _CVDD **, const unsigned int **, const struct CODEVIEW_INFORMATION_1 **, unsigned int *, unsigned int *, struct EMBEDDED_PDB_INFORMATION *, bool *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800121e8`

## callees

- `0x1800069ec`
- `0x1800104f0`
- `0x180014340`
- `0x180017f24`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CCvDDCache::Find(
        Microsoft::Windows::Performance::CCvDDCache *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int *a4,
        const union _CVDD **a5,
        const unsigned int **a6,
        const struct CODEVIEW_INFORMATION_1 **a7,
        unsigned int *a8,
        unsigned int *a9,
        struct EMBEDDED_PDB_INFORMATION *a10,
        bool *a11,
        unsigned __int16 *a12)
{
  __int64 v13; // rdi
  char v14; // si
  bool *v15; // r14
  __int64 v16; // rbx
  __int64 *v17; // rax
  __int64 v18; // rcx
  _QWORD *v19; // rbx
  __int64 *v20; // rax
  struct EMBEDDED_PDB_INFORMATION *v21; // rcx
  size_t *v22; // r8
  __int64 result; // rax
  __int64 v24; // [rsp+20h] [rbp-28h] BYREF
  const unsigned __int16 *v25; // [rsp+58h] [rbp+10h] BYREF
  unsigned int v26; // [rsp+60h] [rbp+18h] BYREF

  v26 = a3;
  v25 = a2;
  try
  {
    v13 = 0;
    v14 = 0;
    v15 = a11;
    *a11 = 0;
    if ( a3 )
    {
      v16 = *(_QWORD *)std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::_Try_emplace<unsigned long const &,>(
                         (_QWORD *)this + 2,
                         (__int64)&v24,
                         &v26);
      v17 = (__int64 *)std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::find(
                         v16 + 40,
                         &a11,
                         &v25);
      v18 = *v17;
      if ( *v17 == *(_QWORD *)(v16 + 40) )
      {
LABEL_7:
        if ( !v14 )
          return 2147943568LL;
        if ( !v13 )
          return 2147500037LL;
        *a4 = *(_DWORD *)(v13 + 64);
        *a5 = *(const union _CVDD **)(v13 + 72);
        *a6 = *(const unsigned int **)(v13 + 80);
        if ( a7 )
          *a7 = *(const struct CODEVIEW_INFORMATION_1 **)(v13 + 88);
        *a8 = *(_DWORD *)(v13 + 132);
        *a9 = *(_DWORD *)(v13 + 136);
        v21 = a10;
        *(_DWORD *)a10 = *(_DWORD *)(v13 + 104) - *(_DWORD *)(v13 + 96);
        *((_QWORD *)v21 + 1) = *(_QWORD *)(v13 + 96);
        *((_WORD *)v21 + 8) = *(_WORD *)(v13 + 122);
        *((_WORD *)v21 + 9) = *(_WORD *)(v13 + 120);
        *v15 = *(_BYTE *)(v13 + 124);
        v22 = (size_t *)(v13 + 32);
        if ( *(_QWORD *)(v13 + 56) > 7u )
          v22 = (size_t *)*v22;
        return StringCchCopyW(a12, 0x30Cu, v22);
      }
    }
    else
    {
      v19 = (_QWORD *)((char *)this + 32);
      v20 = (__int64 *)std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::find(
                         (char *)this + 32,
                         &a11,
                         &v25);
      v18 = *v20;
      if ( *v20 == *v19 )
        goto LABEL_7;
    }
    v14 = 1;
    v13 = *(_QWORD *)(v18 + 40);
    goto LABEL_7;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180014340  mov     rax, rsp
0x180014343  mov     [rax+8], rbx
0x180014347  mov     [rax+20h], rsi
0x18001434b  mov     [rax+18h], r8d
0x18001434f  mov     [rax+10h], rdx
0x180014353  push    rdi
0x180014354  push    r14
0x180014356  push    r15
0x180014358  sub     rsp, 30h
0x18001435c  mov     r15, r9
0x18001435f  xor     edi, edi
0x180014361  xor     sil, sil
0x180014364  mov     r14, [rsp+48h+arg_50]
0x18001436c  mov     [r14], sil
0x18001436f  test    r8d, r8d
0x180014372  jz      short loc_1800143A9
0x180014374  add     rcx, 10h
0x180014378  lea     r8, [rax+18h]
0x18001437c  lea     rdx, [rax-28h]
0x180014380  call    ??$_Try_emplace@AEBK$$V@?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBK@Z; std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::_Try_emplace<ulong const &,>(ulong const &)
0x180014385  mov     rbx, [rax]
0x180014388  lea     r8, [rsp+48h+arg_8]
0x18001438d  lea     rdx, [rsp+48h+arg_50]
0x180014395  lea     rcx, [rbx+28h]
0x180014399  call    ?find@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@2@AEBQEBG@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::find(ushort const * const &)
0x18001439e  mov     rcx, [rax]
0x1800143a1  cmp     rcx, [rbx+28h]
0x1800143a5  jnz     short loc_1800143CA
0x1800143a7  jmp     short loc_1800143D1
0x1800143a9  lea     rbx, [rcx+20h]
0x1800143ad  lea     r8, [rsp+48h+arg_8]
0x1800143b2  lea     rdx, [rsp+48h+arg_50]
0x1800143ba  mov     rcx, rbx
0x1800143bd  call    ?find@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@2@AEBQEBG@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::find(ushort const * const &)
0x1800143c2  mov     rcx, [rax]
0x1800143c5  cmp     rcx, [rbx]
0x1800143c8  jz      short loc_1800143D1
0x1800143ca  mov     sil, 1
0x1800143cd  mov     rdi, [rcx+28h]
0x1800143d1  test    sil, sil
0x1800143d4  jz      loc_18001448C
0x1800143da  test    rdi, rdi
0x1800143dd  jz      loc_180014485
0x1800143e3  mov     eax, [rdi+40h]
0x1800143e6  mov     [r15], eax
0x1800143e9  mov     rcx, [rdi+48h]
0x1800143ed  mov     rax, [rsp+48h+arg_20]
0x1800143f2  mov     [rax], rcx
0x1800143f5  mov     rcx, [rdi+50h]
0x1800143f9  mov     rax, [rsp+48h+arg_28]
0x1800143fe  mov     [rax], rcx
0x180014401  mov     rcx, [rsp+48h+arg_30]
0x180014409  test    rcx, rcx
0x18001440c  jz      short loc_180014415
0x18001440e  mov     rax, [rdi+58h]
0x180014412  mov     [rcx], rax
0x180014415  mov     ecx, [rdi+84h]
0x18001441b  mov     rax, [rsp+48h+arg_38]
0x180014423  mov     [rax], ecx
0x180014425  mov     ecx, [rdi+88h]
0x18001442b  mov     rax, [rsp+48h+arg_40]
0x180014433  mov     [rax], ecx
0x180014435  mov     eax, [rdi+68h]
0x180014438  sub     eax, [rdi+60h]
0x18001443b  mov     rcx, [rsp+48h+arg_48]
0x180014443  mov     [rcx], eax
0x180014445  mov     rax, [rdi+60h]
0x180014449  mov     [rcx+8], rax
0x18001444d  movzx   eax, word ptr [rdi+7Ah]
0x180014451  mov     [rcx+10h], ax
0x180014455  movzx   eax, word ptr [rdi+78h]
0x180014459  mov     [rcx+12h], ax
0x18001445d  mov     al, [rdi+7Ch]
0x180014460  mov     [r14], al
0x180014463  lea     r8, [rdi+20h]
0x180014467  cmp     qword ptr [r8+18h], 7
0x18001446c  jbe     short loc_180014471
0x18001446e  mov     r8, [r8]; unsigned __int16 *
0x180014471  mov     edx, 30Ch; unsigned __int64
0x180014476  mov     rcx, [rsp+48h+arg_58]; unsigned __int16 *
0x18001447e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014483  jmp     short loc_180014498
0x180014485  mov     eax, 80004005h
0x18001448a  jmp     short loc_180014498
0x18001448c  mov     eax, 80070490h
0x180014491  jmp     short loc_180014498
0x180014493  mov     eax, 8007000Eh
0x180014498  mov     rbx, [rsp+48h+arg_0]
0x18001449d  mov     rsi, [rsp+48h+arg_18]
0x1800144a2  add     rsp, 30h
0x1800144a6  pop     r15
0x1800144a8  pop     r14
0x1800144aa  pop     rdi
0x1800144ab  retn
```
