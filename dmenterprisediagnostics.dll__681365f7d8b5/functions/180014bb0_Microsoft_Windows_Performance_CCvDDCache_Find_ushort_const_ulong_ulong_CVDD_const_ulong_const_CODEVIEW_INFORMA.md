# Microsoft::Windows::Performance::CCvDDCache::Find(ushort const *,ulong,ulong *,_CVDD const * *,ulong const * *,CODEVIEW_INFORMATION_1 const * *,ulong *,ulong *,EMBEDDED_PDB_INFORMATION &,bool &,ushort *,ulong)

- ea: `0x180014bb0`
- end: `0x180014d1d`
- name: `?Find@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGKPEAKPEAPEBT_CVDD@@PEAPEBKPEAPEBUCODEVIEW_INFORMATION_1@@11AEAUEMBEDDED_PDB_INFORMATION@@AEA_NPEAGK@Z`
- size: `365`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CCvDDCache *__hidden this, const unsigned __int16 *, unsigned int, unsigned int *, const union _CVDD **, const unsigned int **, const struct CODEVIEW_INFORMATION_1 **, unsigned int *, unsigned int *, struct EMBEDDED_PDB_INFORMATION *, bool *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800129cc`

## callees

- `0x180006c6c`
- `0x180010c84`
- `0x180014bb0`
- `0x18001896c`

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
0x180014bb0  mov     rax, rsp
0x180014bb3  mov     [rax+8], rbx
0x180014bb7  mov     [rax+20h], rsi
0x180014bbb  mov     [rax+18h], r8d
0x180014bbf  mov     [rax+10h], rdx
0x180014bc3  push    rdi
0x180014bc4  push    r14
0x180014bc6  push    r15
0x180014bc8  sub     rsp, 30h
0x180014bcc  mov     r15, r9
0x180014bcf  xor     edi, edi
0x180014bd1  xor     sil, sil
0x180014bd4  mov     r14, [rsp+48h+arg_50]
0x180014bdc  mov     [r14], sil
0x180014bdf  test    r8d, r8d
0x180014be2  jz      short loc_180014C19
0x180014be4  add     rcx, 10h
0x180014be8  lea     r8, [rax+18h]
0x180014bec  lea     rdx, [rax-28h]
0x180014bf0  call    ??$_Try_emplace@AEBK$$V@?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBK@Z; std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::_Try_emplace<ulong const &,>(ulong const &)
0x180014bf5  mov     rbx, [rax]
0x180014bf8  lea     r8, [rsp+48h+arg_8]
0x180014bfd  lea     rdx, [rsp+48h+arg_50]
0x180014c05  lea     rcx, [rbx+28h]
0x180014c09  call    ?find@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@2@AEBQEBG@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::find(ushort const * const &)
0x180014c0e  mov     rcx, [rax]
0x180014c11  cmp     rcx, [rbx+28h]
0x180014c15  jnz     short loc_180014C3A
0x180014c17  jmp     short loc_180014C41
0x180014c19  lea     rbx, [rcx+20h]
0x180014c1d  lea     r8, [rsp+48h+arg_8]
0x180014c22  lea     rdx, [rsp+48h+arg_50]
0x180014c2a  mov     rcx, rbx
0x180014c2d  call    ?find@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@2@AEBQEBG@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::find(ushort const * const &)
0x180014c32  mov     rcx, [rax]
0x180014c35  cmp     rcx, [rbx]
0x180014c38  jz      short loc_180014C41
0x180014c3a  mov     sil, 1
0x180014c3d  mov     rdi, [rcx+28h]
0x180014c41  test    sil, sil
0x180014c44  jz      loc_180014CFC
0x180014c4a  test    rdi, rdi
0x180014c4d  jz      loc_180014CF5
0x180014c53  mov     eax, [rdi+40h]
0x180014c56  mov     [r15], eax
0x180014c59  mov     rcx, [rdi+48h]
0x180014c5d  mov     rax, [rsp+48h+arg_20]
0x180014c62  mov     [rax], rcx
0x180014c65  mov     rcx, [rdi+50h]
0x180014c69  mov     rax, [rsp+48h+arg_28]
0x180014c6e  mov     [rax], rcx
0x180014c71  mov     rcx, [rsp+48h+arg_30]
0x180014c79  test    rcx, rcx
0x180014c7c  jz      short loc_180014C85
0x180014c7e  mov     rax, [rdi+58h]
0x180014c82  mov     [rcx], rax
0x180014c85  mov     ecx, [rdi+84h]
0x180014c8b  mov     rax, [rsp+48h+arg_38]
0x180014c93  mov     [rax], ecx
0x180014c95  mov     ecx, [rdi+88h]
0x180014c9b  mov     rax, [rsp+48h+arg_40]
0x180014ca3  mov     [rax], ecx
0x180014ca5  mov     eax, [rdi+68h]
0x180014ca8  sub     eax, [rdi+60h]
0x180014cab  mov     rcx, [rsp+48h+arg_48]
0x180014cb3  mov     [rcx], eax
0x180014cb5  mov     rax, [rdi+60h]
0x180014cb9  mov     [rcx+8], rax
0x180014cbd  movzx   eax, word ptr [rdi+7Ah]
0x180014cc1  mov     [rcx+10h], ax
0x180014cc5  movzx   eax, word ptr [rdi+78h]
0x180014cc9  mov     [rcx+12h], ax
0x180014ccd  mov     al, [rdi+7Ch]
0x180014cd0  mov     [r14], al
0x180014cd3  lea     r8, [rdi+20h]
0x180014cd7  cmp     qword ptr [r8+18h], 7
0x180014cdc  jbe     short loc_180014CE1
0x180014cde  mov     r8, [r8]; unsigned __int16 *
0x180014ce1  mov     edx, 30Ch; unsigned __int64
0x180014ce6  mov     rcx, [rsp+48h+arg_58]; unsigned __int16 *
0x180014cee  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014cf3  jmp     short loc_180014D08
0x180014cf5  mov     eax, 80004005h
0x180014cfa  jmp     short loc_180014D08
0x180014cfc  mov     eax, 80070490h
0x180014d01  jmp     short loc_180014D08
0x180014d03  mov     eax, 8007000Eh
0x180014d08  mov     rbx, [rsp+48h+arg_0]
0x180014d0d  mov     rsi, [rsp+48h+arg_18]
0x180014d12  add     rsp, 30h
0x180014d16  pop     r15
0x180014d18  pop     r14
0x180014d1a  pop     rdi
0x180014d1b  retn
```
