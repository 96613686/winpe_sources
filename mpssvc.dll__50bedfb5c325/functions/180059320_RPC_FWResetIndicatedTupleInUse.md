# RPC_FWResetIndicatedTupleInUse

- ea: `0x180059320`
- end: `0x1800596da`
- name: `RPC_FWResetIndicatedTupleInUse`
- size: `954`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, installer_update`

## callees

- `0x180007b58`
- `0x180008a80`
- `0x180008d60`
- `0x1800097b0`
- `0x18000a710`
- `0x180026cd0`
- `0x1800560f4`
- `0x180059320`
- `0x18005d5ec`
- `0x180071684`
- `0x1800716d4`
- `0x1800729c0`
- `0x1800cc918`
- `0x1800ccf38`
- `0x1800cd1c8`
- `0x1800cd258`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x180059372`
- `fwbase!FwHResultToWindowsError` at `0x18005938a`
- `fwbase!FwHResultToWindowsError` at `0x1800593e6`
- `fwbase!FwHResultToWindowsError` at `0x18005963f`
- `fwbase!FwHResultToWindowsError` at `0x180059372`
- `fwbase!FwHResultToWindowsError` at `0x18005938a`
- `fwbase!FwHResultToWindowsError` at `0x1800593e6`
- `fwbase!FwHResultToWindowsError` at `0x18005963f`
- `fwbase!FwHashtableEmpty` at `0x180059453`
- `fwbase!FwHashtableEmpty` at `0x180059453`
- `fwbase!FwHashtableRemove` at `0x18005956b`
- `fwbase!FwHashtableRemove` at `0x18005956b`
- `fwbase!FwUpdateHash` at `0x1800594dc`
- `fwbase!FwUpdateHash` at `0x1800594dc`
- `fwbase!FwRestructureHashtable` at `0x18005957b`
- `fwbase!FwRestructureHashtable` at `0x18005957b`
- `fwbase!FwInitializeHashContext` at `0x1800594b8`
- `fwbase!FwInitializeHashContext` at `0x1800594b8`
- `fwbase!FwAddrChangeSourceSignal` at `0x1800596a6`
- `fwbase!FwAddrChangeSourceSignal` at `0x1800596a6`
- `fwbase!FwFinalHash` at `0x1800594ed`
- `fwbase!FwFinalHash` at `0x1800594ed`

## pseudocode

```c
__int64 __fastcall RPC_FWResetIndicatedTupleInUse(void *a1, int a2, __int64 a3, unsigned __int64 a4)
{
  __int64 v4; // rbp
  int v8; // eax
  unsigned int v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // ebx
  unsigned int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rdi
  __int64 v17; // r9
  __int64 v18; // rdx
  __int64 v19; // rax
  struct _tag_FW_RESRC_TUPLE_PER_PACKAGEID *v20; // rsi
  _QWORD *v21; // rbx
  struct _LIST_ENTRY *v22; // rcx
  __int64 (__fastcall *v23)(const struct _tag_FW_RULE *, const void *); // rbx
  unsigned int updated; // eax
  struct _tag_FW_RESRC_TUPLE_PER_PACKAGEID *v25; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v26; // [rsp+48h] [rbp-50h] BYREF
  __int64 v27; // [rsp+50h] [rbp-48h] BYREF

  v4 = a2;
  v25 = 0;
  v27 = 0;
  v26 = 0;
  v8 = FwAcquireRPCSharedLock("RPC_FWResetIndicatedTupleInUse");
  if ( v8 < 0 )
    return FwHResultToWindowsError((unsigned int)v8);
  v10 = FwLock();
  v12 = FwHResultToWindowsError(v10);
  if ( v12 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 56, WPP_3b1e4392722f3ffab86eacb96e939df9_Traceguids, v12);
    goto LABEL_45;
  }
  v13 = FwResrcIndicationTupleAccessCheckForClient((unsigned int)v4, v11, a1);
  v12 = FwHResultToWindowsError(v13);
  if ( v12 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_44;
    v15 = 57;
    goto LABEL_42;
  }
  if ( a3 || (v16 = 12 * v4, !*((_DWORD *)&TupleCollection + 24 * v4 + 3)) )
  {
    v16 = 12 * v4;
    if ( *((_DWORD *)&TupleCollection + 24 * v4 + 3) )
    {
      if ( !a3 )
      {
        v17 = 87;
        v12 = 87;
        v14 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_44;
        v15 = 58;
        goto LABEL_43;
      }
      FwInitializeHashContext(&v27);
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)(a3 + 2 * v18) );
      FwUpdateHash(a3, (unsigned int)(2 * v18), &v27);
      v19 = FwFinalHash(&v27);
      FwResrcPerPackageCollFindByPackageIdSignature(v19, (unsigned int)v4, a3, &v25);
      v20 = v25;
      if ( !v25 )
      {
        v12 = 1168;
        v14 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_44;
        v15 = (unsigned int)((_DWORD)v25 + 59);
        goto LABEL_42;
      }
      if ( !a4
        || (v21 = (_QWORD *)((char *)v25 + 32),
            FwTupleRemoveTupleEntryByCookie((struct _LIST_ENTRY *)v25 + 2, a4),
            (_QWORD *)*v21 == v21) )
      {
        FwHashtableRemove((char *)&TupleCollection + v16 * 8 + 32, v20);
        FwRestructureHashtable((char *)&TupleCollection + v16 * 8 + 32);
        FwTuplePerPackageIdFree(v20);
      }
    }
    else
    {
      if ( a3 )
      {
        v17 = 87;
        v12 = 87;
        v14 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_44;
        v15 = 60;
        goto LABEL_43;
      }
      v22 = (struct _LIST_ENTRY *)&qword_18012FCD0[v16 + 6];
      if ( a4 )
        FwTupleRemoveTupleEntryByCookie(v22, a4);
      else
        FwTupleCollectionFree(v22);
    }
  }
  else
  {
    FwHashtableEmpty(&qword_18012FCD0[v16], FwTuplePerPackageIdEntryFree);
  }
  if ( *(_DWORD *)((char *)&TupleCollection + v16 * 8 + 8) == 1 )
  {
    v23 = FwFWRuleMatchesAddrKeywords;
    v26 = FwAddressKeywordFromTupleCollection((unsigned int)v4);
    FwDynDataNLADeleteAddressStoreByProfileAndAddressKeyword(0x7FFFFFFF, v26);
  }
  else
  {
    v23 = FwFWRuleMatchesTrustTupleKeywords;
    v26 = FwTupleKeywordFromTupleCollection((unsigned int)v4);
  }
  updated = FwUpdateAllWithCriteria((_DWORD)v23, 0, 0, (unsigned int)&v26, 0, 0, 0);
  v12 = FwHResultToWindowsError(updated);
  if ( !v12 )
    goto LABEL_44;
  v14 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
    goto LABEL_44;
  v15 = 61;
LABEL_42:
  v17 = v12;
LABEL_43:
  WPP_SF_d(*(_QWORD *)(v14 + 16), v15, WPP_3b1e4392722f3ffab86eacb96e939df9_Traceguids, v17);
LABEL_44:
  FwUnlockInternal(a1, "RPC_FWResetIndicatedTupleInUse");
LABEL_45:
  FwReleaseRPCSharedLock((__int64)"RPC_FWResetIndicatedTupleInUse");
  if ( !v12 && (_DWORD)v4 == 7 )
    FwAddrChangeSourceSignal();
  return v12;
}

```

## disassembly

```asm
0x180059320  mov     r11, rsp
0x180059323  mov     [r11+20h], rbx
0x180059327  push    rbp
0x180059328  push    rsi
0x180059329  push    rdi
0x18005932a  push    r12
0x18005932c  push    r13
0x18005932e  push    r14
0x180059330  push    r15
0x180059332  sub     rsp, 60h
0x180059336  mov     rax, cs:__security_cookie
0x18005933d  xor     rax, rsp
0x180059340  mov     [rsp+98h+var_40], rax
0x180059345  xor     r12d, r12d
0x180059348  movsxd  rbp, edx
0x18005934b  mov     r15, rcx
0x18005934e  mov     [r11-58h], r12
0x180059352  lea     rcx, aRpcFwresetindi; "RPC_FWResetIndicatedTupleInUse"
0x180059359  mov     [r11-48h], r12
0x18005935d  mov     [r11-50h], r12d
0x180059361  mov     r14, r9
0x180059364  mov     rsi, r8
0x180059367  call    FwAcquireRPCSharedLock
0x18005936c  test    eax, eax
0x18005936e  jns     short loc_180059383
0x180059370  mov     ecx, eax
0x180059372  call    cs:__imp_FwHResultToWindowsError
0x180059379  nop     dword ptr [rax+rax+00h]
0x18005937e  jmp     loc_1800596B4
0x180059383  call    FwLock
0x180059388  mov     ecx, eax
0x18005938a  call    cs:__imp_FwHResultToWindowsError
0x180059391  nop     dword ptr [rax+rax+00h]
0x180059396  mov     ebx, eax
0x180059398  test    eax, eax
0x18005939a  jz      short loc_1800593DA
0x18005939c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800593a3  lea     rax, WPP_GLOBAL_Control
0x1800593aa  cmp     rcx, rax
0x1800593ad  jz      loc_180059691
0x1800593b3  test    byte ptr [rcx+1Ch], 1
0x1800593b7  jz      loc_180059691
0x1800593bd  mov     rcx, [rcx+10h]
0x1800593c1  lea     r8, WPP_3b1e4392722f3ffab86eacb96e939df9_Traceguids
0x1800593c8  mov     edx, 38h ; '8'
0x1800593cd  mov     r9d, ebx
0x1800593d0  call    WPP_SF_d
0x1800593d5  jmp     loc_180059691
0x1800593da  mov     r8, r15
0x1800593dd  mov     ecx, ebp
0x1800593df  call    ?FwResrcIndicationTupleAccessCheckForClient@@YAJW4_tag_FW_TUPLE_COLLECTION_TYPE@@KPEAX@Z; FwResrcIndicationTupleAccessCheckForClient(_tag_FW_TUPLE_COLLECTION_TYPE,ulong,void *)
0x1800593e4  mov     ecx, eax
0x1800593e6  call    cs:__imp_FwHResultToWindowsError
0x1800593ed  nop     dword ptr [rax+rax+00h]
0x1800593f2  mov     ebx, eax
0x1800593f4  test    eax, eax
0x1800593f6  jz      short loc_180059423
0x1800593f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800593ff  lea     rax, WPP_GLOBAL_Control
0x180059406  cmp     rcx, rax
0x180059409  jz      loc_180059682
0x18005940f  test    byte ptr [rcx+1Ch], 1
0x180059413  jz      loc_180059682
0x180059419  mov     edx, 39h ; '9'
0x18005941e  jmp     loc_18005966F
0x180059423  lea     r13, ?TupleCollection@@3PAU_tag_FW_RESRC_TUPLE_COLLECTION@@A; _tag_FW_RESRC_TUPLE_COLLECTION near * TupleCollection
0x18005942a  test    rsi, rsi
0x18005942d  jnz     short loc_180059464
0x18005942f  lea     rdi, ds:0[rbp*2]
0x180059437  add     rdi, rbp
0x18005943a  shl     rdi, 5
0x18005943e  cmp     [rdi+r13+0Ch], r12d
0x180059443  jz      short loc_180059464
0x180059445  lea     rcx, [r13+20h]
0x180059449  add     rcx, rdi
0x18005944c  lea     rdx, ?FwTuplePerPackageIdEntryFree@@YAXPEAPEAU_RTL_DYNAMIC_HASH_TABLE_ENTRY@@@Z; FwTuplePerPackageIdEntryFree(_RTL_DYNAMIC_HASH_TABLE_ENTRY * *)
0x180059453  call    cs:__imp_FwHashtableEmpty
0x18005945a  nop     dword ptr [rax+rax+00h]
0x18005945f  jmp     loc_1800595E4
0x180059464  lea     rdi, ds:0[rbp*2]
0x18005946c  add     rdi, rbp
0x18005946f  shl     rdi, 5
0x180059473  cmp     [rdi+r13+0Ch], r12d
0x180059478  jz      loc_180059591
0x18005947e  test    rsi, rsi
0x180059481  jnz     short loc_1800594B3
0x180059483  lea     r9d, [rsi+57h]
0x180059487  mov     ebx, r9d
0x18005948a  mov     rcx, cs:WPP_GLOBAL_Control
0x180059491  lea     rax, WPP_GLOBAL_Control
0x180059498  cmp     rcx, rax
0x18005949b  jz      loc_180059682
0x1800594a1  test    byte ptr [rcx+1Ch], 1
0x1800594a5  jz      loc_180059682
0x1800594ab  lea     edx, [rsi+3Ah]
0x1800594ae  jmp     loc_180059672
0x1800594b3  lea     rcx, [rsp+98h+var_48]
0x1800594b8  call    cs:__imp_FwInitializeHashContext
0x1800594bf  nop     dword ptr [rax+rax+00h]
0x1800594c4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800594c8  inc     rdx
0x1800594cb  cmp     [rsi+rdx*2], r12w
0x1800594d0  jnz     short loc_1800594C8
0x1800594d2  add     edx, edx
0x1800594d4  lea     r8, [rsp+98h+var_48]
0x1800594d9  mov     rcx, rsi
0x1800594dc  call    cs:__imp_FwUpdateHash
0x1800594e3  nop     dword ptr [rax+rax+00h]
0x1800594e8  lea     rcx, [rsp+98h+var_48]
0x1800594ed  call    cs:__imp_FwFinalHash
0x1800594f4  nop     dword ptr [rax+rax+00h]
0x1800594f9  lea     r9, [rsp+98h+var_58]
0x1800594fe  mov     r8, rsi
0x180059501  mov     rcx, rax
0x180059504  mov     edx, ebp
0x180059506  call    ?FwResrcPerPackageCollFindByPackageIdSignature@@YAK_KW4_tag_FW_TUPLE_COLLECTION_TYPE@@PEBGPEAPEAU_tag_FW_RESRC_TUPLE_PER_PACKAGEID@@@Z; FwResrcPerPackageCollFindByPackageIdSignature(unsigned __int64,_tag_FW_TUPLE_COLLECTION_TYPE,ushort const *,_tag_FW_RESRC_TUPLE_PER_PACKAGEID * *)
0x18005950b  mov     rsi, [rsp+98h+var_58]
0x180059510  test    rsi, rsi
0x180059513  jnz     short loc_180059543
0x180059515  mov     ebx, 490h
0x18005951a  mov     rcx, cs:WPP_GLOBAL_Control
0x180059521  lea     rax, WPP_GLOBAL_Control
0x180059528  cmp     rcx, rax
0x18005952b  jz      loc_180059682
0x180059531  test    byte ptr [rcx+1Ch], 1
0x180059535  jz      loc_180059682
0x18005953b  lea     edx, [rsi+3Bh]
0x18005953e  jmp     loc_18005966F
0x180059543  test    r14, r14
0x180059546  jz      short loc_180059560
0x180059548  lea     rbx, [rsi+20h]
0x18005954c  mov     rdx, r14; unsigned __int64
0x18005954f  mov     rcx, rbx; struct _LIST_ENTRY *
0x180059552  call    ?FwTupleRemoveTupleEntryByCookie@@YAXPEAU_LIST_ENTRY@@_K@Z; FwTupleRemoveTupleEntryByCookie(_LIST_ENTRY *,unsigned __int64)
0x180059557  cmp     [rbx], rbx
0x18005955a  jnz     loc_1800595E4
0x180059560  lea     rbx, [rdi+r13]
0x180059564  mov     rdx, rsi
0x180059567  lea     rcx, [rbx+20h]
0x18005956b  call    cs:__imp_FwHashtableRemove
0x180059572  nop     dword ptr [rax+rax+00h]
0x180059577  lea     rcx, [rbx+20h]
0x18005957b  call    cs:__imp_FwRestructureHashtable
0x180059582  nop     dword ptr [rax+rax+00h]
0x180059587  mov     rcx, rsi; struct _tag_FW_RESRC_TUPLE_PER_PACKAGEID *
0x18005958a  call    ?FwTuplePerPackageIdFree@@YAXPEAU_tag_FW_RESRC_TUPLE_PER_PACKAGEID@@@Z; FwTuplePerPackageIdFree(_tag_FW_RESRC_TUPLE_PER_PACKAGEID *)
0x18005958f  jmp     short loc_1800595E4
0x180059591  test    rsi, rsi
0x180059594  jz      short loc_1800595C9
0x180059596  mov     r9d, 57h ; 'W'
0x18005959c  mov     ebx, r9d
0x18005959f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800595a6  lea     rax, WPP_GLOBAL_Control
0x1800595ad  cmp     rcx, rax
0x1800595b0  jz      loc_180059682
0x1800595b6  test    byte ptr [rcx+1Ch], 1
0x1800595ba  jz      loc_180059682
0x1800595c0  lea     edx, [r9-1Bh]
0x1800595c4  jmp     loc_180059672
0x1800595c9  lea     rcx, [r13+50h]
0x1800595cd  add     rcx, rdi; struct _LIST_ENTRY *
0x1800595d0  test    r14, r14
0x1800595d3  jnz     short loc_1800595DC
0x1800595d5  call    ?FwTupleCollectionFree@@YAXPEAU_LIST_ENTRY@@@Z; FwTupleCollectionFree(_LIST_ENTRY *)
0x1800595da  jmp     short loc_1800595E4
0x1800595dc  mov     rdx, r14; unsigned __int64
0x1800595df  call    ?FwTupleRemoveTupleEntryByCookie@@YAXPEAU_LIST_ENTRY@@_K@Z; FwTupleRemoveTupleEntryByCookie(_LIST_ENTRY *,unsigned __int64)
0x1800595e4  cmp     dword ptr [rdi+r13+8], 1
0x1800595ea  mov     ecx, ebp
0x1800595ec  jnz     short loc_18005960C
0x1800595ee  lea     rbx, ?FwFWRuleMatchesAddrKeywords@@YAHPEBU_tag_FW_RULE@@PEBX@Z; FwFWRuleMatchesAddrKeywords(_tag_FW_RULE const *,void const *)
0x1800595f5  call    ?FwAddressKeywordFromTupleCollection@@YA?AW4_tag_FW_ADDRESS_KEYWORD@@W4_tag_FW_TUPLE_COLLECTION_TYPE@@@Z; FwAddressKeywordFromTupleCollection(_tag_FW_TUPLE_COLLECTION_TYPE)
0x1800595fa  mov     edx, eax
0x1800595fc  mov     [rsp+98h+var_50], eax
0x180059600  mov     ecx, 7FFFFFFFh
0x180059605  call    FwDynDataNLADeleteAddressStoreByProfileAndAddressKeyword
0x18005960a  jmp     short loc_18005961C
0x18005960c  lea     rbx, ?FwFWRuleMatchesTrustTupleKeywords@@YAHPEBU_tag_FW_RULE@@PEBX@Z; FwFWRuleMatchesTrustTupleKeywords(_tag_FW_RULE const *,void const *)
0x180059613  call    ?FwTupleKeywordFromTupleCollection@@YA?AW4_tag_FW_TRUST_TUPLE_KEYWORD@@W4_tag_FW_TUPLE_COLLECTION_TYPE@@@Z; FwTupleKeywordFromTupleCollection(_tag_FW_TUPLE_COLLECTION_TYPE)
0x180059618  mov     [rsp+98h+var_50], eax
0x18005961c  mov     [rsp+98h+var_68], r12d
0x180059621  lea     r9, [rsp+98h+var_50]
0x180059626  mov     [rsp+98h+var_70], r12d
0x18005962b  xor     r8d, r8d
0x18005962e  xor     edx, edx
0x180059630  mov     [rsp+98h+var_78], r12d
0x180059635  mov     rcx, rbx
0x180059638  call    FwUpdateAllWithCriteria
0x18005963d  mov     ecx, eax
0x18005963f  call    cs:__imp_FwHResultToWindowsError
0x180059646  nop     dword ptr [rax+rax+00h]
0x18005964b  mov     ebx, eax
0x18005964d  test    eax, eax
0x18005964f  jz      short loc_180059682
0x180059651  mov     rcx, cs:WPP_GLOBAL_Control
0x180059658  lea     rax, WPP_GLOBAL_Control
0x18005965f  cmp     rcx, rax
0x180059662  jz      short loc_180059682
0x180059664  test    byte ptr [rcx+1Ch], 1
0x180059668  jz      short loc_180059682
0x18005966a  mov     edx, 3Dh ; '='
0x18005966f  mov     r9d, ebx
0x180059672  mov     rcx, [rcx+10h]
0x180059676  lea     r8, WPP_3b1e4392722f3ffab86eacb96e939df9_Traceguids
0x18005967d  call    WPP_SF_d
0x180059682  lea     rdx, aRpcFwresetindi; "RPC_FWResetIndicatedTupleInUse"
0x180059689  mov     rcx, r15; void *
0x18005968c  call    FwUnlockInternal
0x180059691  lea     rcx, aRpcFwresetindi; "RPC_FWResetIndicatedTupleInUse"
0x180059698  call    FwReleaseRPCSharedLock
0x18005969d  test    ebx, ebx
0x18005969f  jnz     short loc_1800596B2
0x1800596a1  cmp     ebp, 7
0x1800596a4  jnz     short loc_1800596B2
0x1800596a6  call    cs:__imp_FwAddrChangeSourceSignal
0x1800596ad  nop     dword ptr [rax+rax+00h]
0x1800596b2  mov     eax, ebx
0x1800596b4  mov     rcx, [rsp+98h+var_40]
0x1800596b9  xor     rcx, rsp; StackCookie
0x1800596bc  call    __security_check_cookie
0x1800596c1  mov     rbx, [rsp+98h+arg_18]
0x1800596c9  add     rsp, 60h
0x1800596cd  pop     r15
0x1800596cf  pop     r14
0x1800596d1  pop     r13
0x1800596d3  pop     r12
0x1800596d5  pop     rdi
0x1800596d6  pop     rsi
0x1800596d7  pop     rbp
0x1800596d8  retn
```
