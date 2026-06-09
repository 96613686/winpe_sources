# RtMgrRdConfigStore::SetRtmRegistrationInfo(_GUID *,ulong,_RTM_ENTITY_REGISTRATION_INFO *)

- ea: `0x1800569e4`
- end: `0x180056be3`
- name: `?SetRtmRegistrationInfo@RtMgrRdConfigStore@@QEAAXPEAU_GUID@@KPEAU_RTM_ENTITY_REGISTRATION_INFO@@@Z`
- size: `511`
- prototype: `void(RtMgrRdConfigStore *__hidden this, struct _GUID *, unsigned int, struct _RTM_ENTITY_REGISTRATION_INFO *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180057e14`

## callees

- `0x180002fd4`
- `0x180054fc4`
- `0x180055b5c`
- `0x1800569e4`
- `0x180056bec`
- `0x180056f3c`
- `0x180056fdc`
- `0x180057590`
- `0x1800576fc`
- `0x180057860`
- `0x1800578dc`
- `0x180058068`
- `0x180058124`
- `0x180058536`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180056a71`
- `ntdll!RtlAcquireResourceExclusive` at `0x180056a71`
- `ntdll!RtlReleaseResource` at `0x180056ba2`
- `ntdll!RtlReleaseResource` at `0x180056ba2`

## string_xrefs

- `0x180056a4f`: `RtMgrRdConfigStore::SetRtmRegistrationInfo`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RtMgrRdConfigStore::SetRtmRegistrationInfo(
        RtMgrRdConfigStore *this,
        struct _GUID *a2,
        unsigned int a3,
        struct _RTM_ENTITY_REGISTRATION_INFO *a4)
{
  __int64 v8; // rsi
  unsigned int *v9; // r8
  void (*v10)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  struct _GUID *v11; // r14
  char *v12; // r13
  _QWORD **v13; // rbx
  _QWORD *v14; // rdi
  _QWORD *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdi
  __int64 v18; // rbx
  char *v19; // rsi
  __int64 i; // rdi
  _QWORD *v21; // rbx
  _QWORD *v22; // rax
  _QWORD *v23; // r8
  unsigned __int16 *v24; // [rsp+28h] [rbp-D8h]
  unsigned int v25; // [rsp+30h] [rbp-D0h]
  _QWORD *v26; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v27; // [rsp+48h] [rbp-B8h]
  PRTL_RESOURCE Resource; // [rsp+50h] [rbp-B0h]
  _QWORD v29[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+68h] [rbp-98h] BYREF
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int128 v32; // [rsp+80h] [rbp-80h]
  __int64 v33; // [rsp+90h] [rbp-70h]
  int v34; // [rsp+98h] [rbp-68h]
  int v35; // [rsp+9Ch] [rbp-64h]
  __int64 v36; // [rsp+A0h] [rbp-60h] BYREF
  int v37; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v38[156]; // [rsp+B4h] [rbp-4Ch] BYREF
  __int64 v39; // [rsp+160h] [rbp+60h] BYREF

  v8 = 0;
  v37 = 0;
  memset_0(v38, 0, 0x5Cu);
  v31 = 0;
  v30 = 0;
  v32 = 0;
  v33 = 0;
  v34 = -1;
  v35 = 0;
  if ( *((_QWORD *)&xmmword_18008B450 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v30,
      L"RtMgrRdConfigStore::SetRtmRegistrationInfo",
      v9,
      v10,
      a2,
      v24,
      v25);
  Resource = (PRTL_RESOURCE)((char *)this + 184);
  RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 184), 1u);
  std::_Hash<std::tr1::_Umap_traits<_GUID,RtMgrRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>,0>>::lower_bound(
    (char *)this + 8,
    &v39,
    a2);
  if ( v39 != *((_QWORD *)this + 2) )
  {
    v11 = *(struct _GUID **)(v39 + 32);
    if ( a4 )
    {
      v12 = (char *)this + 96;
      v13 = (_QWORD **)((char *)this + 104);
      do
      {
        v14 = (_QWORD *)*((_QWORD *)a4 + v8 + 10);
        v26 = v14;
        std::_Hash<std::tr1::_Umap_traits<void *,RtMgrRoutingDomainConfig *,std::_Hash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>,0>>::lower_bound(
          v12,
          &v39,
          &v26);
        v15 = *v13;
        v16 = v39;
        if ( (_QWORD *)v39 == *v13 )
        {
          v29[0] = v14;
          v29[1] = 0;
          v17 = *v15;
          v18 = std::_List_val<std::pair<void * const,RtMgrRoutingDomainConfig *>>::_Buynode<std::pair<void * const,RtMgrRoutingDomainConfig *>>(
                  v15,
                  *v15,
                  *(_QWORD *)(*v15 + 8LL),
                  v29);
          std::list<std::pair<void * const,RtMgrRoutingDomainConfig *>>::_Incsize(v12 + 8);
          *(_QWORD *)(v17 + 8) = v18;
          **(_QWORD **)(v18 + 8) = v18;
          v13 = (_QWORD **)(v12 + 8);
          std::_Hash<std::tr1::_Umap_traits<void *,RtMgrRoutingDomainConfig *,std::_Hash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>,0>>::_Insert(
            v12,
            &v36,
            **((_QWORD **)v12 + 1) + 16LL);
          v16 = v36;
          v39 = v36;
        }
        *(_QWORD *)(v16 + 24) = v11;
        ++v8;
      }
      while ( v8 != 2 );
      RtMgrRoutingDomainConfig::SetRtmRegistrationInfo(v11, a3, a4);
    }
    else
    {
      RtMgrRoutingDomainConfig::GetAllRtmRegistrationHandles(
        *(RtMgrRoutingDomainConfig **)(v39 + 32),
        a3,
        (struct _RTM_ENTITY_REGISTRATION_INFO *)&v37);
      v19 = (char *)this + 96;
      for ( i = 0; i != 2; ++i )
      {
        std::_Hash<std::tr1::_Umap_traits<void *,RtMgrRoutingDomainConfig *,std::_Hash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>,0>>::equal_range(
          v19,
          &v26,
          &v38[8 * i + 76]);
        v21 = v26;
        v22 = (_QWORD *)*((_QWORD *)v19 + 1);
        if ( v26 == (_QWORD *)*v22 && v27 == v22 )
        {
          std::_Hash<std::tr1::_Umap_traits<void *,RtMgrRoutingDomainConfig *,std::_Hash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>,0>>::clear(v19);
        }
        else
        {
          while ( v21 != v27 )
          {
            v23 = v21;
            v21 = (_QWORD *)*v21;
            std::_Hash<std::tr1::_Umap_traits<void *,RtMgrRoutingDomainConfig *,std::_Hash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>,0>>::erase(
              v19,
              &v39,
              v23);
          }
        }
      }
    }
  }
  RtlReleaseResource(Resource);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v30);
}

```

## disassembly

```asm
0x1800569e4  push    rbp
0x1800569e6  push    rbx
0x1800569e7  push    rsi
0x1800569e8  push    rdi
0x1800569e9  push    r12
0x1800569eb  push    r13
0x1800569ed  push    r14
0x1800569ef  push    r15
0x1800569f1  lea     rbp, [rsp-18h]
0x1800569f6  sub     rsp, 118h
0x1800569fd  mov     r15, r9
0x180056a00  mov     r12d, r8d
0x180056a03  mov     rdi, rdx
0x180056a06  mov     rbx, rcx
0x180056a09  xor     esi, esi
0x180056a0b  mov     [rbp+50h+var_A0], esi
0x180056a0e  xor     edx, edx; Val
0x180056a10  lea     r8d, [rsi+5Ch]; Size
0x180056a14  lea     rcx, [rbp+50h+var_9C]; void *
0x180056a18  call    memset_0
0x180056a1d  xorps   xmm0, xmm0
0x180056a20  movdqu  [rsp+150h+var_E0], xmm0
0x180056a26  mov     [rsp+150h+var_E8], rsi
0x180056a2b  xorps   xmm1, xmm1
0x180056a2e  movdqu  [rbp+50h+var_D0], xmm1
0x180056a33  mov     [rbp+50h+var_C0], rsi
0x180056a37  mov     [rbp+50h+var_B8], 0FFFFFFFFh
0x180056a3e  mov     [rbp+50h+var_B4], esi
0x180056a41  cmp     qword ptr cs:xmmword_18008B450+8, rsi
0x180056a48  jz      short loc_180056A60
0x180056a4a  mov     [rsp+150h+var_130], rdi; struct _GUID *
0x180056a4f  lea     rdx, aRtmgrrdconfigs; "RtMgrRdConfigStore::SetRtmRegistrationI"...
0x180056a56  lea     rcx, [rsp+150h+var_E8]; this
0x180056a5b  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180056a60  lea     rax, [rbx+0B8h]
0x180056a67  mov     [rsp+150h+Resource], rax
0x180056a6c  mov     dl, 1; Wait
0x180056a6e  mov     rcx, rax; Resource
0x180056a71  call    cs:__imp_RtlAcquireResourceExclusive
0x180056a77  lea     rcx, [rbx+8]
0x180056a7b  mov     r8, rdi
0x180056a7e  lea     rdx, [rbp+50h+arg_0]
0x180056a82  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRtMgrRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RtMgrRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x180056a87  mov     rax, [rbp+50h+arg_0]
0x180056a8b  cmp     rax, [rbx+10h]
0x180056a8f  jz      loc_180056B9D
0x180056a95  mov     r14, [rax+20h]
0x180056a99  test    r15, r15
0x180056a9c  jz      loc_180056B4D
0x180056aa2  lea     r13, [rbx+60h]
0x180056aa6  lea     rbx, [r13+8]
0x180056aaa  mov     rdi, [r15+rsi*8+50h]
0x180056aaf  mov     [rsp+150h+var_110], rdi
0x180056ab4  lea     r8, [rsp+150h+var_110]
0x180056ab9  lea     rdx, [rbp+50h+arg_0]
0x180056abd  mov     rcx, r13
0x180056ac0  call    ?lower_bound@?$_Hash@V?$_Umap_traits@PEAXPEAVRtMgrRoutingDomainConfig@@V?$_Hash_compare@PEAXV?$hash@PEAX@std@@U?$equal_to@PEAX@2@@std@@V?$allocator@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@@3@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@V?$allocator@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@@2@@std@@@2@AEBQEAX@Z; std::_Hash<std::tr1::_Umap_traits<void *,RtMgrRoutingDomainConfig *,std::_Hash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>,0>>::lower_bound(void * const &)
0x180056ac5  mov     rcx, [rbx]
0x180056ac8  mov     rax, [rbp+50h+arg_0]
0x180056acc  cmp     rax, rcx
0x180056acf  jnz     short loc_180056B2C
0x180056ad1  mov     [rsp+150h+var_F8], rdi
0x180056ad6  mov     [rsp+150h+var_F0], 0
0x180056adf  mov     rdi, [rcx]
0x180056ae2  lea     r9, [rsp+150h+var_F8]
0x180056ae7  mov     r8, [rdi+8]
0x180056aeb  mov     rdx, rdi
0x180056aee  call    ??$_Buynode@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@@?$_List_val@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@V?$allocator@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@@2@@std@@QEAAPEAU_Node@?$_List_nod@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@V?$allocator@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@@2@@1@PEAU231@0$$QEAU?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@1@@Z; std::_List_val<std::pair<void * const,RtMgrRoutingDomainConfig *>>::_Buynode<std::pair<void * const,RtMgrRoutingDomainConfig *>>(std::_List_nod<std::pair<void * const,RtMgrRoutingDomainConfig *>>::_Node *,std::_List_nod<std::pair<void * const,RtMgrRoutingDomainConfig *>>::_Node *,std::pair<void * const,RtMgrRoutingDomainConfig *> &&)
0x180056af3  mov     rbx, rax
0x180056af6  lea     rcx, [r13+8]
0x180056afa  call    ?_Incsize@?$list@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@V?$allocator@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@@2@@std@@QEAAX_K@Z; std::list<std::pair<void * const,RtMgrRoutingDomainConfig *>>::_Incsize(unsigned __int64)
0x180056aff  mov     [rdi+8], rbx
0x180056b03  mov     rcx, [rbx+8]
0x180056b07  mov     [rcx], rbx
0x180056b0a  lea     rbx, [r13+8]
0x180056b0e  mov     r9, [rbx]
0x180056b11  mov     r9, [r9]
0x180056b14  lea     r8, [r9+10h]
0x180056b18  lea     rdx, [rbp+50h+var_B0]
0x180056b1c  mov     rcx, r13
0x180056b1f  call    ?_Insert@?$_Hash@V?$_Umap_traits@PEAXPEAVRtMgrRoutingDomainConfig@@V?$_Hash_compare@PEAXV?$hash@PEAX@std@@U?$equal_to@PEAX@2@@std@@V?$allocator@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@@3@$0A@@tr1@std@@@std@@IEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@V?$allocator@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@@2@@std@@@std@@_N@2@AEBU?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@2@V?$_List_iterator@V?$_List_val@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@V?$allocator@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@@2@@std@@@2@@Z; std::_Hash<std::tr1::_Umap_traits<void *,RtMgrRoutingDomainConfig *,std::_Hash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>,0>>::_Insert(std::pair<void * const,RtMgrRoutingDomainConfig *> const &,std::_List_iterator<std::_List_val<std::pair<void * const,RtMgrRoutingDomainConfig *>>>)
0x180056b24  mov     rax, [rbp+50h+var_B0]
0x180056b28  mov     [rbp+50h+arg_0], rax
0x180056b2c  mov     [rax+18h], r14
0x180056b30  inc     rsi
0x180056b33  cmp     rsi, 2
0x180056b37  jnz     loc_180056AAA
0x180056b3d  mov     r8, r15; struct _RTM_ENTITY_REGISTRATION_INFO *
0x180056b40  mov     edx, r12d; unsigned int
0x180056b43  mov     rcx, r14; this
0x180056b46  call    ?SetRtmRegistrationInfo@RtMgrRoutingDomainConfig@@QEAAXKPEAU_RTM_ENTITY_REGISTRATION_INFO@@@Z; RtMgrRoutingDomainConfig::SetRtmRegistrationInfo(ulong,_RTM_ENTITY_REGISTRATION_INFO *)
0x180056b4b  jmp     short loc_180056B9D
0x180056b4d  lea     r8, [rbp+50h+var_A0]; struct _RTM_ENTITY_REGISTRATION_INFO *
0x180056b51  mov     edx, r12d; unsigned int
0x180056b54  mov     rcx, r14; this
0x180056b57  call    ?GetAllRtmRegistrationHandles@RtMgrRoutingDomainConfig@@QEAAXKPEAU_RTM_ENTITY_REGISTRATION_INFO@@@Z; RtMgrRoutingDomainConfig::GetAllRtmRegistrationHandles(ulong,_RTM_ENTITY_REGISTRATION_INFO *)
0x180056b5c  lea     rsi, [rbx+60h]
0x180056b60  xor     edi, edi
0x180056b62  lea     r8, [rbp+50h+var_50]
0x180056b66  lea     r8, [r8+rdi*8]
0x180056b6a  lea     rdx, [rsp+150h+var_110]
0x180056b6f  mov     rcx, rsi
0x180056b72  call    ?equal_range@?$_Hash@V?$_Umap_traits@PEAXPEAVRtMgrRoutingDomainConfig@@V?$_Hash_compare@PEAXV?$hash@PEAX@std@@U?$equal_to@PEAX@2@@std@@V?$allocator@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@@3@$0A@@tr1@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@V?$allocator@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@@2@@std@@@std@@V12@@2@AEBQEAX@Z; std::_Hash<std::tr1::_Umap_traits<void *,RtMgrRoutingDomainConfig *,std::_Hash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>,0>>::equal_range(void * const &)
0x180056b77  mov     rbx, [rsp+150h+var_110]
0x180056b7c  mov     rax, [rsi+8]
0x180056b80  cmp     rbx, [rax]
0x180056b83  jnz     short loc_180056BC7
0x180056b85  cmp     [rsp+150h+var_108], rax
0x180056b8a  jnz     short loc_180056BC7
0x180056b8c  mov     rcx, rsi
0x180056b8f  call    ?clear@?$_Hash@V?$_Umap_traits@PEAXPEAVRtMgrRoutingDomainConfig@@V?$_Hash_compare@PEAXV?$hash@PEAX@std@@U?$equal_to@PEAX@2@@std@@V?$allocator@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@@3@$0A@@tr1@std@@@std@@QEAAXXZ; std::_Hash<std::tr1::_Umap_traits<void *,RtMgrRoutingDomainConfig *,std::_Hash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>,0>>::clear(void)
0x180056b94  inc     rdi
0x180056b97  cmp     rdi, 2
0x180056b9b  jnz     short loc_180056B62
0x180056b9d  mov     rcx, [rsp+150h+Resource]; Resource
0x180056ba2  call    cs:__imp_RtlReleaseResource
0x180056ba8  nop
0x180056ba9  lea     rcx, [rsp+150h+var_E8]; this
0x180056bae  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180056bb3  add     rsp, 118h
0x180056bba  pop     r15
0x180056bbc  pop     r14
0x180056bbe  pop     r13
0x180056bc0  pop     r12
0x180056bc2  pop     rdi
0x180056bc3  pop     rsi
0x180056bc4  pop     rbx
0x180056bc5  pop     rbp
0x180056bc6  retn
0x180056bc7  cmp     rbx, [rsp+150h+var_108]
0x180056bcc  jz      short loc_180056B94
0x180056bce  mov     r8, rbx
0x180056bd1  mov     rbx, [rbx]
0x180056bd4  lea     rdx, [rbp+50h+arg_0]
0x180056bd8  mov     rcx, rsi
0x180056bdb  call    ?erase@?$_Hash@V?$_Umap_traits@PEAXPEAVRtMgrRoutingDomainConfig@@V?$_Hash_compare@PEAXV?$hash@PEAX@std@@U?$equal_to@PEAX@2@@std@@V?$allocator@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@@3@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@V?$allocator@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@@2@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@V?$allocator@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@@2@@std@@@2@@Z; std::_Hash<std::tr1::_Umap_traits<void *,RtMgrRoutingDomainConfig *,std::_Hash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>,0>>::erase(std::_List_const_iterator<std::_List_val<std::pair<void * const,RtMgrRoutingDomainConfig *>>>)
0x180056be0  jmp     short loc_180056BC7
```
