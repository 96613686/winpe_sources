# StoreSettingsCallback(_GUID const *,_GUID const *,_GUID const *,_GUID const *,void *)

- ea: `0x18008ed10`
- end: `0x18008ee6f`
- name: `?StoreSettingsCallback@@YAKPEBU_GUID@@000PEAX@Z`
- size: `351`
- prototype: `unsigned int __fastcall(const struct _GUID *, const struct _GUID *, const struct _GUID *, const struct _GUID *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18008e26c`
- `0x18008e3dc`
- `0x18008e54c`
- `0x18008e6bc`
- `0x18008ec68`
- `0x18008ed10`

## import_xrefs

- `POWRPROF!PowerReadACValueIndexEx` at `0x18008ed79`
- `POWRPROF!PowerReadACValueIndexEx` at `0x18008ed79`
- `POWRPROF!PowerReadDCValueIndexEx` at `0x18008eda8`
- `POWRPROF!PowerReadDCValueIndexEx` at `0x18008eda8`

## pseudocode

```c
__int64 __fastcall StoreSettingsCallback(
        struct _GUID *a1,
        struct _GUID *a2,
        struct _GUID *a3,
        struct _GUID *a4,
        float *a5)
{
  struct _GUID *v7; // rbx
  bool v9; // r14
  char v10; // si
  unsigned __int8 v11; // di
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rax
  GUID *v15; // r8
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // eax
  int v20; // [rsp+20h] [rbp-51h]
  int v21; // [rsp+40h] [rbp-31h] BYREF
  int v22; // [rsp+44h] [rbp-2Dh] BYREF
  __int64 v23; // [rsp+48h] [rbp-29h] BYREF
  __int64 v24; // [rsp+50h] [rbp-21h]
  int v25; // [rsp+58h] [rbp-19h]
  _BYTE v26[16]; // [rsp+60h] [rbp-11h] BYREF
  _BYTE v27[80]; // [rsp+70h] [rbp-1h] BYREF

  v21 = 0;
  v23 = 0;
  v7 = a2;
  v22 = 0;
  v9 = 0;
  v10 = 0;
  v11 = IsOverlaySchemeValid(a1);
  LODWORD(v7) = PowerReadACValueIndexEx(a1, v7, a3, a4, v11, &v23, &v21);
  LOBYTE(v20) = v11;
  v12 = PowerReadDCValueIndexEx(a1, a2, a3, a4, v20, (char *)&v23 + 4, &v22);
  if ( !(_DWORD)v7 )
    v9 = v21 == 2;
  if ( !v12 && v22 == 2 )
    v10 = 1;
  if ( v9 || v10 )
  {
    v24 = v23;
    HIWORD(v25) = 0;
    LOBYTE(v25) = v9;
    BYTE1(v25) = v10;
    v13 = ____Try_emplace_AEBU_GUID____V____Hash_V___Umap_traits_U_GUID__V__unordered_map_U_GUID__V__unordered_map_U_GUID__V__unordered_map_U_GUID__U_SETTING_OVERRIDES__U__hash_U_GUID___std__U__equal_to_U_GUID___4_V__allocator_U__pair___CBU_GUID__U_SETTING_OVERRIDES___std___4__std__U__hash_U_GUID___3_U__equal_to_U_GUID___3_V__allocator_U__pair___CBU_GUID__V__unordered_map_U_GUID__U_SETTING_OVERRIDES__U__hash_U_GUID___std__U__equal_to_U_GUID___4_V__allocator_U__pair___CBU_GUID__U_SETTING_OVERRIDES___std___4__std___std___3__std__U__hash_U_GUID___3_U__equal_to_U_GUID___3_V__allocator_U__pair___CBU_GUID__V__unordered_map_U_GUID__V__unordered_map_U_GUID__U_SETTING_OVERRIDES__U__hash_U_GUID___std__U__equal_to_U_GUID___4_V__allocator_U__pair___CBU_GUID__U_SETTING_OVERRIDES___std___4__std__U__hash_U_GUID___3_U__equal_to_U_GUID___3_V__allocator_U__pair___CBU_GUID__V__unordered_map_U_GUID__U_SETTING_OVERRIDES__U__hash_U_GUID___std__U__equal_to_U_GUID___4_V__allocator_U__pair___CBU_GUID__U_SETTING_OVERRIDES___std___4__std___std___3__std___std___3__std__V___Uhash_compare_U_GUID__U__hash_U_GUID___std__U__equal_to_U_GUID___3__3_V__allocator_U__pair___CBU_GUID__V__unordered_map_U_GUID__V__unordered_map_U_GUID__V__unordered_map_U_GUID__U_SETTING_OVERRIDES__U__hash_U_GUID___std__U__equal_to_U_GUID___4_V__allocator_U__pair___CBU_GUID__U_SETTING_OVERRIDES___std___4__std__U__hash_U_GUID___3_U__equal_to_U_GUID___3_V__allocator_U__pair___CBU_GUID__V__unordered_map_U_GUID__U_SETTING_OVERRIDES__U__hash_U_GUID___std__U__equal_to_U_GUID___4_V__allocator_U__pair___CBU_GUID__U_SETTING_OVERRIDES___std___4__std___std___3__std__U__hash_U_GUID___3_U__equal_to_U_GUID___3_V__allocator_U__pair___CBU_GUID__V__unordered_map_U_GUID__V__unordered_map_U_GUID__U_SETTING_OVERRIDES__U__hash_U_GUID___std__U__equal_to_U_GUID___4_V__allocator_U__pair___CBU_GUID__U_SETTING_OVERRIDES___std___4__std__U__hash_U_GUID___3_U__equal_to_U_GUID___3_V__allocator_U__pair___CBU_GUID__V__unordered_map_U_GUID__U_SETTING_OVERRIDES__U__hash_U_GUID___std__U__equal_to_U_GUID___4_V__allocator_U__pair___CBU_GUID__U_SETTING_OVERRIDES___std___4__std___std___3__std___std___3__std___std___3__0A__std___std__IEAA_AU__pair_PEAU___List_node_U__pair___CBU_GUID__V__unordered_map_U_GUID__V__unordered_map_U_GUID__V__unordered_map_U_GUID__U_SETTING_OVERRIDES__U__hash_U_GUID___std__U__equal_to_U_GUID___4_V__allocator_U__pair___CBU_GUID__U_SETTING_OVERRIDES___std___4__std__U__hash_U_GUID___3_U__equal_to_U_GUID___3_V__allocator_U__pair___CBU_GUID__V__unordered_map_U_GUID__U_SETTING_OVERRIDES__U__hash_U_GUID___std__U__equal_to_U_GUID___4_V__allocator_U__pair___CBU_GUID__U_SETTING_OVERRIDES___std___4__std___std___3__std__U__hash_U_GUID___3_U__equal_to_U_GUID___3_V__allocator_U__pair___CBU_GUID__V__unordered_map_U_GUID__V__unordered_map_U_GUID__U_SETTING_OVERRIDES__U__hash_U_GUID___std__U__equal_to_U_GUID___4_V__allocator_U__pair___CBU_GUID__U_SETTING_OVERRIDES___std___4__std__U__hash_U_GUID___3_U__equal_to_U_GUID___3_V__allocator_U__pair___CBU_GUID__V__unordered_map_U_GUID__U_SETTING_OVERRIDES__U__hash_U_GUID___std__U__equal_to_U_GUID___4_V__allocator_U__pair___CBU_GUID__U_SETTING_OVERRIDES___std___4__std___std___3__std___std___3__std___std__PEAX_std___N_1_AEBU_GUID___Z(
            a5,
            (__int64)v26,
            a2);
    v14 = std::_Hash<std::_Umap_traits<_GUID,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>>>>,0>>::_Try_emplace<_GUID const &,>(
            (float *)(*(_QWORD *)v13 + 32LL),
            (__int64)v27,
            a1);
    v15 = &GUID_POWER_POLICY_PROFILE_DEFAULT;
    if ( a3 )
      v15 = a3;
    v16 = std::_Hash<std::_Umap_traits<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::unordered_map<_GUID,_SETTING_OVERRIDES>>>,0>>::_Try_emplace<_GUID const &,>(
            (float *)(*(_QWORD *)v14 + 32LL),
            (__int64)v26,
            v15);
    v17 = *(_QWORD *)std::_Hash<std::_Umap_traits<_GUID,_SETTING_OVERRIDES,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,_SETTING_OVERRIDES>>,0>>::_Try_emplace<_GUID const &,>(
                       (float *)(*(_QWORD *)v16 + 32LL),
                       (__int64)v27,
                       a4);
    v18 = v25;
    *(_QWORD *)(v17 + 32) = v24;
    *(_DWORD *)(v17 + 40) = v18;
  }
  return 0;
}

```

## disassembly

```asm
0x18008ed10  mov     [rsp-8+arg_8], rdx
0x18008ed15  push    rbp
0x18008ed16  push    rbx
0x18008ed17  push    rsi
0x18008ed18  push    rdi
0x18008ed19  push    r12
0x18008ed1b  push    r13
0x18008ed1d  push    r14
0x18008ed1f  push    r15
0x18008ed21  lea     rbp, [rsp-17h]
0x18008ed26  sub     rsp, 88h
0x18008ed2d  xor     eax, eax
0x18008ed2f  mov     r13, r9
0x18008ed32  mov     [rbp+4Fh+var_80], eax
0x18008ed35  mov     r12, r8
0x18008ed38  mov     dword ptr [rbp+4Fh+var_78], eax
0x18008ed3b  mov     rbx, rdx
0x18008ed3e  mov     [rbp+4Fh+var_7C], eax
0x18008ed41  mov     r15, rcx
0x18008ed44  mov     dword ptr [rbp+4Fh+var_78+4], eax
0x18008ed47  movzx   r14d, al
0x18008ed4b  movzx   esi, al
0x18008ed4e  call    ?IsOverlaySchemeValid@@YAEPEBU_GUID@@@Z; IsOverlaySchemeValid(_GUID const *)
0x18008ed53  mov     dil, al
0x18008ed56  mov     r9, r13
0x18008ed59  lea     rax, [rbp+4Fh+var_80]
0x18008ed5d  mov     r8, r12
0x18008ed60  mov     [rsp+0C0h+var_90], rax
0x18008ed65  mov     rdx, rbx
0x18008ed68  lea     rax, [rbp+4Fh+var_78]
0x18008ed6c  mov     rcx, r15
0x18008ed6f  mov     [rsp+0C0h+var_98], rax
0x18008ed74  mov     [rsp+0C0h+var_A0], dil
0x18008ed79  call    cs:__imp_PowerReadACValueIndexEx
0x18008ed7f  mov     r9, r13
0x18008ed82  mov     r8, r12
0x18008ed85  mov     ebx, eax
0x18008ed87  mov     rcx, r15
0x18008ed8a  lea     rax, [rbp+4Fh+var_7C]
0x18008ed8e  mov     [rsp+0C0h+var_90], rax
0x18008ed93  lea     rax, [rbp+4Fh+var_78+4]
0x18008ed97  mov     [rsp+0C0h+var_98], rax
0x18008ed9c  mov     [rsp+0C0h+var_A0], dil
0x18008eda1  mov     rdi, [rbp+4Fh+arg_8]
0x18008eda5  mov     rdx, rdi
0x18008eda8  call    cs:__imp_PowerReadDCValueIndexEx
0x18008edae  mov     ecx, 1
0x18008edb3  test    ebx, ebx
0x18008edb5  jnz     short loc_18008EDBF
0x18008edb7  cmp     [rbp+4Fh+var_80], 2
0x18008edbb  cmovz   r14d, ecx
0x18008edbf  test    eax, eax
0x18008edc1  jnz     short loc_18008EDCA
0x18008edc3  cmp     [rbp+4Fh+var_7C], 2
0x18008edc7  cmovz   esi, ecx
0x18008edca  test    r14b, r14b
0x18008edcd  jnz     short loc_18008EDD8
0x18008edcf  test    sil, sil
0x18008edd2  jz      loc_18008EE59
0x18008edd8  mov     eax, dword ptr [rbp+4Fh+var_78]
0x18008eddb  lea     rdx, [rbp+4Fh+var_60]
0x18008eddf  mov     rcx, [rbp+4Fh+arg_20]
0x18008ede3  mov     r8, rdi
0x18008ede6  mov     dword ptr [rbp+4Fh+var_70], eax
0x18008ede9  mov     eax, dword ptr [rbp+4Fh+var_78+4]
0x18008edec  mov     dword ptr [rbp+4Fh+var_70+4], eax
0x18008edef  xor     eax, eax
0x18008edf1  mov     word ptr [rbp+4Fh+var_68+2], ax
0x18008edf5  mov     byte ptr [rbp+4Fh+var_68], r14b
0x18008edf9  mov     byte ptr [rbp+4Fh+var_68+1], sil
0x18008edfd  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$_Hash@V?$_Umap_traits@U_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@@std@@@3@@std@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@@std@@@3@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@@std@@@3@@std@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z
0x18008ee02  mov     r8, r15
0x18008ee05  lea     rdx, [rbp+4Fh+var_50]
0x18008ee09  mov     rcx, [rax]
0x18008ee0c  add     rcx, 20h ; ' '
0x18008ee10  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$_Hash@V?$_Umap_traits@U_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>>>>,0>>::_Try_emplace<_GUID const &,>(_GUID const &)
0x18008ee15  test    r12, r12
0x18008ee18  lea     r8, GUID_POWER_POLICY_PROFILE_DEFAULT
0x18008ee1f  lea     rdx, [rbp+4Fh+var_60]
0x18008ee23  cmovnz  r8, r12
0x18008ee27  mov     rcx, [rax]
0x18008ee2a  add     rcx, 20h ; ' '
0x18008ee2e  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$_Hash@V?$_Umap_traits@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::unordered_map<_GUID,_SETTING_OVERRIDES>>>,0>>::_Try_emplace<_GUID const &,>(_GUID const &)
0x18008ee33  mov     r8, r13
0x18008ee36  lea     rdx, [rbp+4Fh+var_50]
0x18008ee3a  mov     rcx, [rax]
0x18008ee3d  add     rcx, 20h ; ' '
0x18008ee41  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$_Hash@V?$_Umap_traits@U_GUID@@U_SETTING_OVERRIDES@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,_SETTING_OVERRIDES,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,_SETTING_OVERRIDES>>,0>>::_Try_emplace<_GUID const &,>(_GUID const &)
0x18008ee46  movsd   xmm0, [rbp+4Fh+var_70]
0x18008ee4b  mov     rcx, [rax]
0x18008ee4e  mov     eax, [rbp+4Fh+var_68]
0x18008ee51  movsd   qword ptr [rcx+20h], xmm0
0x18008ee56  mov     [rcx+28h], eax
0x18008ee59  xor     eax, eax
0x18008ee5b  add     rsp, 88h
0x18008ee62  pop     r15
0x18008ee64  pop     r14
0x18008ee66  pop     r13
0x18008ee68  pop     r12
0x18008ee6a  pop     rdi
0x18008ee6b  pop     rsi
0x18008ee6c  pop     rbx
0x18008ee6d  pop     rbp
0x18008ee6e  retn
```
