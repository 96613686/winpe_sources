# RPC_FWResetIndicatedTupleInUse

- ea: `0x1800540a0`
- end: `0x180054413`
- name: `RPC_FWResetIndicatedTupleInUse`
- size: `883`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, installer_update`

## callees

- `0x180008618`
- `0x180009460`
- `0x180009720`
- `0x18000a0c0`
- `0x18000af3c`
- `0x1800247d0`
- `0x180051d10`
- `0x1800540a0`
- `0x1800585b4`
- `0x18006e278`
- `0x18006e2c8`
- `0x18006f520`
- `0x1800c5584`
- `0x1800c5a88`
- `0x1800c5cf8`
- `0x1800c5d84`

## import_xrefs

- `fwbase!FwHashtableEmpty` at `0x1800541c1`
- `fwbase!FwHashtableEmpty` at `0x1800541c1`
- `fwbase!FwHResultToWindowsError` at `0x1800540f2`
- `fwbase!FwHResultToWindowsError` at `0x180054104`
- `fwbase!FwHResultToWindowsError` at `0x18005415a`
- `fwbase!FwHResultToWindowsError` at `0x180054385`
- `fwbase!FwHResultToWindowsError` at `0x1800540f2`
- `fwbase!FwHResultToWindowsError` at `0x180054104`
- `fwbase!FwHResultToWindowsError` at `0x18005415a`
- `fwbase!FwHResultToWindowsError` at `0x180054385`
- `fwbase!FwHashtableRemove` at `0x1800542bd`
- `fwbase!FwHashtableRemove` at `0x1800542bd`
- `fwbase!FwUpdateHash` at `0x18005423e`
- `fwbase!FwUpdateHash` at `0x18005423e`
- `fwbase!FwRestructureHashtable` at `0x1800542c7`
- `fwbase!FwRestructureHashtable` at `0x1800542c7`
- `fwbase!FwInitializeHashContext` at `0x180054220`
- `fwbase!FwInitializeHashContext` at `0x180054220`
- `fwbase!FwFinalHash` at `0x180054249`
- `fwbase!FwFinalHash` at `0x180054249`
- `fwbase!FwAddrChangeSourceSignal` at `0x1800543e6`
- `fwbase!FwAddrChangeSourceSignal` at `0x1800543e6`

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
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 56, WPP_b7c33e85cf4d34b1ab1e131583d2c8f9_Traceguids, v12);
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
      v22 = (struct _LIST_ENTRY *)&qword_180129BE0[v16 + 6];
      if ( a4 )
        FwTupleRemoveTupleEntryByCookie(v22, a4);
      else
        FwTupleCollectionFree(v22);
    }
  }
  else
  {
    FwHashtableEmpty(&qword_180129BE0[v16], FwTuplePerPackageIdEntryFree);
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
  WPP_SF_d(*(_QWORD *)(v14 + 16), v15, WPP_b7c33e85cf4d34b1ab1e131583d2c8f9_Traceguids, v17);
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
0x1800540a0  mov     r11, rsp
0x1800540a3  mov     [r11+20h], rbx
0x1800540a7  push    rbp
0x1800540a8  push    rsi
0x1800540a9  push    rdi
0x1800540aa  push    r12
0x1800540ac  push    r13
0x1800540ae  push    r14
0x1800540b0  push    r15
0x1800540b2  sub     rsp, 60h
0x1800540b6  mov     rax, cs:__security_cookie
0x1800540bd  xor     rax, rsp
0x1800540c0  mov     [rsp+98h+var_40], rax
0x1800540c5  xor     r12d, r12d
0x1800540c8  movsxd  rbp, edx
0x1800540cb  mov     r15, rcx
0x1800540ce  mov     [r11-58h], r12
0x1800540d2  lea     rcx, aRpcFwresetindi; "RPC_FWResetIndicatedTupleInUse"
0x1800540d9  mov     [r11-48h], r12
0x1800540dd  mov     [r11-50h], r12d
0x1800540e1  mov     r14, r9
0x1800540e4  mov     rsi, r8
0x1800540e7  call    FwAcquireRPCSharedLock
0x1800540ec  test    eax, eax
0x1800540ee  jns     short loc_1800540FD
0x1800540f0  mov     ecx, eax
0x1800540f2  call    cs:__imp_FwHResultToWindowsError
0x1800540f8  jmp     loc_1800543EE
0x1800540fd  call    FwLock
0x180054102  mov     ecx, eax
0x180054104  call    cs:__imp_FwHResultToWindowsError
0x18005410a  mov     ebx, eax
0x18005410c  test    eax, eax
0x18005410e  jz      short loc_18005414E
0x180054110  mov     rcx, cs:WPP_GLOBAL_Control
0x180054117  lea     rax, WPP_GLOBAL_Control
0x18005411e  cmp     rcx, rax
0x180054121  jz      loc_1800543D1
0x180054127  test    byte ptr [rcx+1Ch], 1
0x18005412b  jz      loc_1800543D1
0x180054131  mov     rcx, [rcx+10h]
0x180054135  lea     r8, WPP_b7c33e85cf4d34b1ab1e131583d2c8f9_Traceguids
0x18005413c  mov     edx, 38h ; '8'
0x180054141  mov     r9d, ebx
0x180054144  call    WPP_SF_d
0x180054149  jmp     loc_1800543D1
0x18005414e  mov     r8, r15
0x180054151  mov     ecx, ebp
0x180054153  call    ?FwResrcIndicationTupleAccessCheckForClient@@YAJW4_tag_FW_TUPLE_COLLECTION_TYPE@@KPEAX@Z; FwResrcIndicationTupleAccessCheckForClient(_tag_FW_TUPLE_COLLECTION_TYPE,ulong,void *)
0x180054158  mov     ecx, eax
0x18005415a  call    cs:__imp_FwHResultToWindowsError
0x180054160  mov     ebx, eax
0x180054162  test    eax, eax
0x180054164  jz      short loc_180054191
0x180054166  mov     rcx, cs:WPP_GLOBAL_Control
0x18005416d  lea     rax, WPP_GLOBAL_Control
0x180054174  cmp     rcx, rax
0x180054177  jz      loc_1800543C2
0x18005417d  test    byte ptr [rcx+1Ch], 1
0x180054181  jz      loc_1800543C2
0x180054187  mov     edx, 39h ; '9'
0x18005418c  jmp     loc_1800543AF
0x180054191  lea     r13, ?TupleCollection@@3PAU_tag_FW_RESRC_TUPLE_COLLECTION@@A; _tag_FW_RESRC_TUPLE_COLLECTION near * TupleCollection
0x180054198  test    rsi, rsi
0x18005419b  jnz     short loc_1800541CC
0x18005419d  lea     rdi, ds:0[rbp*2]
0x1800541a5  add     rdi, rbp
0x1800541a8  shl     rdi, 5
0x1800541ac  cmp     [rdi+r13+0Ch], r12d
0x1800541b1  jz      short loc_1800541CC
0x1800541b3  lea     rcx, [r13+20h]
0x1800541b7  add     rcx, rdi
0x1800541ba  lea     rdx, ?FwTuplePerPackageIdEntryFree@@YAXPEAPEAU_RTL_DYNAMIC_HASH_TABLE_ENTRY@@@Z; FwTuplePerPackageIdEntryFree(_RTL_DYNAMIC_HASH_TABLE_ENTRY * *)
0x1800541c1  call    cs:__imp_FwHashtableEmpty
0x1800541c7  jmp     loc_18005432A
0x1800541cc  lea     rdi, ds:0[rbp*2]
0x1800541d4  add     rdi, rbp
0x1800541d7  shl     rdi, 5
0x1800541db  cmp     [rdi+r13+0Ch], r12d
0x1800541e0  jz      loc_1800542D7
0x1800541e6  test    rsi, rsi
0x1800541e9  jnz     short loc_18005421B
0x1800541eb  lea     r9d, [rsi+57h]
0x1800541ef  mov     ebx, r9d
0x1800541f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800541f9  lea     rax, WPP_GLOBAL_Control
0x180054200  cmp     rcx, rax
0x180054203  jz      loc_1800543C2
0x180054209  test    byte ptr [rcx+1Ch], 1
0x18005420d  jz      loc_1800543C2
0x180054213  lea     edx, [rsi+3Ah]
0x180054216  jmp     loc_1800543B2
0x18005421b  lea     rcx, [rsp+98h+var_48]
0x180054220  call    cs:__imp_FwInitializeHashContext
0x180054226  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18005422a  inc     rdx
0x18005422d  cmp     [rsi+rdx*2], r12w
0x180054232  jnz     short loc_18005422A
0x180054234  add     edx, edx
0x180054236  lea     r8, [rsp+98h+var_48]
0x18005423b  mov     rcx, rsi
0x18005423e  call    cs:__imp_FwUpdateHash
0x180054244  lea     rcx, [rsp+98h+var_48]
0x180054249  call    cs:__imp_FwFinalHash
0x18005424f  lea     r9, [rsp+98h+var_58]
0x180054254  mov     r8, rsi
0x180054257  mov     rcx, rax
0x18005425a  mov     edx, ebp
0x18005425c  call    ?FwResrcPerPackageCollFindByPackageIdSignature@@YAK_KW4_tag_FW_TUPLE_COLLECTION_TYPE@@PEBGPEAPEAU_tag_FW_RESRC_TUPLE_PER_PACKAGEID@@@Z; FwResrcPerPackageCollFindByPackageIdSignature(unsigned __int64,_tag_FW_TUPLE_COLLECTION_TYPE,ushort const *,_tag_FW_RESRC_TUPLE_PER_PACKAGEID * *)
0x180054261  mov     rsi, [rsp+98h+var_58]
0x180054266  test    rsi, rsi
0x180054269  jnz     short loc_180054299
0x18005426b  mov     ebx, 490h
0x180054270  mov     rcx, cs:WPP_GLOBAL_Control
0x180054277  lea     rax, WPP_GLOBAL_Control
0x18005427e  cmp     rcx, rax
0x180054281  jz      loc_1800543C2
0x180054287  test    byte ptr [rcx+1Ch], 1
0x18005428b  jz      loc_1800543C2
0x180054291  lea     edx, [rsi+3Bh]
0x180054294  jmp     loc_1800543AF
0x180054299  test    r14, r14
0x18005429c  jz      short loc_1800542B2
0x18005429e  lea     rbx, [rsi+20h]
0x1800542a2  mov     rdx, r14; unsigned __int64
0x1800542a5  mov     rcx, rbx; struct _LIST_ENTRY *
0x1800542a8  call    ?FwTupleRemoveTupleEntryByCookie@@YAXPEAU_LIST_ENTRY@@_K@Z; FwTupleRemoveTupleEntryByCookie(_LIST_ENTRY *,unsigned __int64)
0x1800542ad  cmp     [rbx], rbx
0x1800542b0  jnz     short loc_18005432A
0x1800542b2  lea     rbx, [rdi+r13]
0x1800542b6  mov     rdx, rsi
0x1800542b9  lea     rcx, [rbx+20h]
0x1800542bd  call    cs:__imp_FwHashtableRemove
0x1800542c3  lea     rcx, [rbx+20h]
0x1800542c7  call    cs:__imp_FwRestructureHashtable
0x1800542cd  mov     rcx, rsi; struct _tag_FW_RESRC_TUPLE_PER_PACKAGEID *
0x1800542d0  call    ?FwTuplePerPackageIdFree@@YAXPEAU_tag_FW_RESRC_TUPLE_PER_PACKAGEID@@@Z; FwTuplePerPackageIdFree(_tag_FW_RESRC_TUPLE_PER_PACKAGEID *)
0x1800542d5  jmp     short loc_18005432A
0x1800542d7  test    rsi, rsi
0x1800542da  jz      short loc_18005430F
0x1800542dc  mov     r9d, 57h ; 'W'
0x1800542e2  mov     ebx, r9d
0x1800542e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800542ec  lea     rax, WPP_GLOBAL_Control
0x1800542f3  cmp     rcx, rax
0x1800542f6  jz      loc_1800543C2
0x1800542fc  test    byte ptr [rcx+1Ch], 1
0x180054300  jz      loc_1800543C2
0x180054306  lea     edx, [r9-1Bh]
0x18005430a  jmp     loc_1800543B2
0x18005430f  lea     rcx, [r13+50h]
0x180054313  add     rcx, rdi; struct _LIST_ENTRY *
0x180054316  test    r14, r14
0x180054319  jnz     short loc_180054322
0x18005431b  call    ?FwTupleCollectionFree@@YAXPEAU_LIST_ENTRY@@@Z; FwTupleCollectionFree(_LIST_ENTRY *)
0x180054320  jmp     short loc_18005432A
0x180054322  mov     rdx, r14; unsigned __int64
0x180054325  call    ?FwTupleRemoveTupleEntryByCookie@@YAXPEAU_LIST_ENTRY@@_K@Z; FwTupleRemoveTupleEntryByCookie(_LIST_ENTRY *,unsigned __int64)
0x18005432a  cmp     dword ptr [rdi+r13+8], 1
0x180054330  mov     ecx, ebp
0x180054332  jnz     short loc_180054352
0x180054334  lea     rbx, ?FwFWRuleMatchesAddrKeywords@@YAHPEBU_tag_FW_RULE@@PEBX@Z; FwFWRuleMatchesAddrKeywords(_tag_FW_RULE const *,void const *)
0x18005433b  call    ?FwAddressKeywordFromTupleCollection@@YA?AW4_tag_FW_ADDRESS_KEYWORD@@W4_tag_FW_TUPLE_COLLECTION_TYPE@@@Z; FwAddressKeywordFromTupleCollection(_tag_FW_TUPLE_COLLECTION_TYPE)
0x180054340  mov     edx, eax
0x180054342  mov     [rsp+98h+var_50], eax
0x180054346  mov     ecx, 7FFFFFFFh
0x18005434b  call    FwDynDataNLADeleteAddressStoreByProfileAndAddressKeyword
0x180054350  jmp     short loc_180054362
0x180054352  lea     rbx, ?FwFWRuleMatchesTrustTupleKeywords@@YAHPEBU_tag_FW_RULE@@PEBX@Z; FwFWRuleMatchesTrustTupleKeywords(_tag_FW_RULE const *,void const *)
0x180054359  call    ?FwTupleKeywordFromTupleCollection@@YA?AW4_tag_FW_TRUST_TUPLE_KEYWORD@@W4_tag_FW_TUPLE_COLLECTION_TYPE@@@Z; FwTupleKeywordFromTupleCollection(_tag_FW_TUPLE_COLLECTION_TYPE)
0x18005435e  mov     [rsp+98h+var_50], eax
0x180054362  mov     [rsp+98h+var_68], r12d
0x180054367  lea     r9, [rsp+98h+var_50]
0x18005436c  mov     [rsp+98h+var_70], r12d
0x180054371  xor     r8d, r8d
0x180054374  xor     edx, edx
0x180054376  mov     [rsp+98h+var_78], r12d
0x18005437b  mov     rcx, rbx
0x18005437e  call    FwUpdateAllWithCriteria
0x180054383  mov     ecx, eax
0x180054385  call    cs:__imp_FwHResultToWindowsError
0x18005438b  mov     ebx, eax
0x18005438d  test    eax, eax
0x18005438f  jz      short loc_1800543C2
0x180054391  mov     rcx, cs:WPP_GLOBAL_Control
0x180054398  lea     rax, WPP_GLOBAL_Control
0x18005439f  cmp     rcx, rax
0x1800543a2  jz      short loc_1800543C2
0x1800543a4  test    byte ptr [rcx+1Ch], 1
0x1800543a8  jz      short loc_1800543C2
0x1800543aa  mov     edx, 3Dh ; '='
0x1800543af  mov     r9d, ebx
0x1800543b2  mov     rcx, [rcx+10h]
0x1800543b6  lea     r8, WPP_b7c33e85cf4d34b1ab1e131583d2c8f9_Traceguids
0x1800543bd  call    WPP_SF_d
0x1800543c2  lea     rdx, aRpcFwresetindi; "RPC_FWResetIndicatedTupleInUse"
0x1800543c9  mov     rcx, r15; void *
0x1800543cc  call    FwUnlockInternal
0x1800543d1  lea     rcx, aRpcFwresetindi; "RPC_FWResetIndicatedTupleInUse"
0x1800543d8  call    FwReleaseRPCSharedLock
0x1800543dd  test    ebx, ebx
0x1800543df  jnz     short loc_1800543EC
0x1800543e1  cmp     ebp, 7
0x1800543e4  jnz     short loc_1800543EC
0x1800543e6  call    cs:__imp_FwAddrChangeSourceSignal
0x1800543ec  mov     eax, ebx
0x1800543ee  mov     rcx, [rsp+98h+var_40]
0x1800543f3  xor     rcx, rsp; StackCookie
0x1800543f6  call    __security_check_cookie
0x1800543fb  mov     rbx, [rsp+98h+arg_18]
0x180054403  add     rsp, 60h
0x180054407  pop     r15
0x180054409  pop     r14
0x18005440b  pop     r13
0x18005440d  pop     r12
0x18005440f  pop     rdi
0x180054410  pop     rsi
0x180054411  pop     rbp
0x180054412  retn
```
