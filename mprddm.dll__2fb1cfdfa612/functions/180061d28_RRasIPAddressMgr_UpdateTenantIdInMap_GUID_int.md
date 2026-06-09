# RRasIPAddressMgr::UpdateTenantIdInMap(_GUID *,int)

- ea: `0x180061d28`
- end: `0x180061fdb`
- name: `?UpdateTenantIdInMap@RRasIPAddressMgr@@QEAAKPEAU_GUID@@H@Z`
- size: `691`
- prototype: `unsigned int __fastcall(RRasIPAddressMgr *__hidden this, struct _GUID *, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180051e20`

## callees

- `0x180025c98`
- `0x18005e918`
- `0x180060238`
- `0x180061470`
- `0x1800614a0`
- `0x180061d28`
- `0x180065548`
- `0x180066b44`
- `0x180071b1c`
- `0x180071bd8`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!wcschr` at `0x180061ed0`
- `msvcrt!wcschr` at `0x180061ee1`
- `msvcrt!wcschr` at `0x180061ed0`
- `msvcrt!wcschr` at `0x180061ee1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180061f63`
- `msvcrt!??3@YAXPEAX@Z` at `0x180061f63`
- `KERNEL32!LocalAlloc` at `0x180061e9e`
- `KERNEL32!LocalAlloc` at `0x180061e9e`

## string_xrefs

- `0x180061dca`: `RRasIPAddressMgr::UpdateTenantIdInMap`
- `0x180061e56`: `GetRoutingDomainConfigData (for dial in config) returned error %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RRasIPAddressMgr::UpdateTenantIdInMap(RRasIPAddressMgr *this, struct _GUID *a2, int a3)
{
  unsigned int v6; // ebx
  void (*v7)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int RoutingDomainConfigData; // eax
  unsigned int v9; // esi
  struct _GUID *v10; // rax
  struct _GUID *v11; // rbx
  __int64 v12; // r12
  const wchar_t *v13; // rdi
  bool v14; // zf
  int v15; // eax
  _WORD *v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rbx
  __int64 v19; // rax
  unsigned int v21; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v23; // [rsp+30h] [rbp-D0h]
  __int128 v24; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  int v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+5Ch] [rbp-A4h]
  char v28[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v29[88]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v30; // [rsp+C8h] [rbp-38h]
  __int64 v31; // [rsp+D0h] [rbp-30h]
  void *v32[3]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v33; // [rsp+F8h] [rbp-8h]
  struct _GUID *v34; // [rsp+108h] [rbp+8h]
  int v35; // [rsp+110h] [rbp+10h] BYREF
  char v36[2044]; // [rsp+114h] [rbp+14h] BYREF

  v6 = 0;
  v21 = 0;
  memset_0(v29, 0, 0x68u);
  v35 = 0;
  memset_0(v36, 0, sizeof(v36));
  v23 = 0;
  v22 = 0;
  v24 = 0;
  v25 = 0;
  v26 = -1;
  v27 = 0;
  if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v22,
      L"RRasIPAddressMgr::UpdateTenantIdInMap",
      &v21,
      v7);
    v6 = v21;
  }
  if ( dword_1800C8650
    && (*(_QWORD *)&a2->Data1 != *(_QWORD *)&GUID_NULL.Data1 || *(_QWORD *)a2->Data4 != *(_QWORD *)GUID_NULL.Data4) )
  {
    RRasIPAddressMgr::AcquireRdInfoListLock(this);
    RRasIPAddressMgr::RemoveTenantIdFromMap(this, a2);
    if ( !a3 )
    {
      RoutingDomainConfigData = GetRoutingDomainConfigData(a2, 0x4000, 104, v29);
      v21 = RoutingDomainConfigData;
      if ( RoutingDomainConfigData )
      {
        if ( (_QWORD)xmmword_1800C9740 )
        {
          LOWORD(v35) = 0;
          FormatRRASErrorString(
            &v35,
            L"GetRoutingDomainConfigData (for dial in config) returned error %d",
            RoutingDomainConfigData);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800C9740,
            &v35);
        }
      }
      else
      {
        v9 = 0;
        if ( v30 )
        {
          while ( 1 )
          {
            v10 = (struct _GUID *)LocalAlloc(0x40u, 0x14u);
            v11 = v10;
            if ( !v10 )
              break;
            v12 = 1026LL * v9;
            v13 = (const wchar_t *)(v12 + v31);
            *v10 = *a2;
            if ( wcschr(v13, 0x2Bu) || (v14 = wcschr(v13, 0x2Au) == 0, v15 = 0, !v14) )
              v15 = 1;
            v11[1].Data1 = v15;
            v16 = (_WORD *)(v12 + v31);
            v33 = 7;
            v32[2] = 0;
            LOWORD(v32[0]) = 0;
            v17 = -1;
            do
              ++v17;
            while ( v16[v17] );
            std::wstring::assign(v32, v16);
            v34 = v11;
            v18 = *((_QWORD *)this + 18);
            v19 = std::_Tree_val<std::_Tmap_traits<std::wstring,_TenantIdentifierInfo *,_lessstr,std::allocator<std::pair<std::wstring const,_TenantIdentifierInfo *>>,0>>::_Buynode<std::pair<std::wstring,_TenantIdentifierInfo *> &>(
                    (char *)this + 136,
                    v32);
            std::_Tree<std::_Tmap_traits<std::wstring,_TenantIdentifierInfo *,_lessstr,std::allocator<std::pair<std::wstring const,_TenantIdentifierInfo *>>,0>>::_Insert(
              (char *)this + 136,
              v28,
              v18,
              v19);
            if ( v33 >= 8 )
              operator delete(v32[0]);
            if ( ++v9 >= v30 )
              goto LABEL_22;
          }
          v21 = 8;
        }
      }
    }
LABEL_22:
    if ( qword_1800C8690 )
      qword_1800C8690(0x4000, v29);
    RRasIPAddressMgr::ReleaseRdInfoListLock(this);
    v6 = v21;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v22);
  return v6;
}

```

## disassembly

```asm
0x180061d28  mov     [rsp-8+arg_10], rbx
0x180061d2d  push    rbp
0x180061d2e  push    rsi
0x180061d2f  push    rdi
0x180061d30  push    r12
0x180061d32  push    r13
0x180061d34  push    r14
0x180061d36  push    r15
0x180061d38  lea     rbp, [rsp-820h]
0x180061d40  sub     rsp, 920h
0x180061d47  mov     rax, cs:__security_cookie
0x180061d4e  xor     rax, rsp
0x180061d51  mov     [rbp+850h+var_40], rax
0x180061d58  mov     edi, r8d
0x180061d5b  mov     r14, rdx
0x180061d5e  mov     r15, rcx
0x180061d61  xor     r13d, r13d
0x180061d64  mov     ebx, r13d
0x180061d67  mov     [rsp+950h+var_930], ebx
0x180061d6b  lea     esi, [r13+68h]
0x180061d6f  mov     r8d, esi; Size
0x180061d72  xor     edx, edx; Val
0x180061d74  lea     rcx, [rsp+950h+var_8E0]; void *
0x180061d79  call    memset_0
0x180061d7e  mov     [rbp+850h+var_840], r13d
0x180061d82  xor     edx, edx; Val
0x180061d84  mov     r8d, 7FCh; Size
0x180061d8a  lea     rcx, [rbp+850h+var_83C]; void *
0x180061d8e  call    memset_0
0x180061d93  xorps   xmm0, xmm0
0x180061d96  movdqu  [rsp+950h+var_920], xmm0
0x180061d9c  mov     [rsp+950h+var_928], r13
0x180061da1  xorps   xmm1, xmm1
0x180061da4  movdqu  [rsp+950h+var_910], xmm1
0x180061daa  mov     [rsp+950h+var_900], r13
0x180061daf  mov     [rsp+950h+var_8F8], 0FFFFFFFFh
0x180061db7  mov     [rsp+950h+var_8F4], r13d
0x180061dbc  cmp     qword ptr cs:xmmword_1800C9740+8, r13
0x180061dc3  jz      short loc_180061DDF
0x180061dc5  lea     r8, [rsp+950h+var_930]; unsigned int *
0x180061dca  lea     rdx, aRrasipaddressm_13; "RRasIPAddressMgr::UpdateTenantIdInMap"
0x180061dd1  lea     rcx, [rsp+950h+var_928]; this
0x180061dd6  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180061ddb  mov     ebx, [rsp+950h+var_930]
0x180061ddf  cmp     cs:dword_1800C8650, r13d
0x180061de6  jz      loc_180061FA5
0x180061dec  mov     rax, [r14]
0x180061def  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180061df6  jnz     short loc_180061E09
0x180061df8  mov     rax, [r14+8]
0x180061dfc  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180061e03  jz      loc_180061FA5
0x180061e09  mov     rcx, r15; this
0x180061e0c  call    ?AcquireRdInfoListLock@RRasIPAddressMgr@@AEAAXXZ; RRasIPAddressMgr::AcquireRdInfoListLock(void)
0x180061e11  mov     rdx, r14; struct _GUID *
0x180061e14  mov     rcx, r15; this
0x180061e17  call    ?RemoveTenantIdFromMap@RRasIPAddressMgr@@AEAAKPEAU_GUID@@@Z; RRasIPAddressMgr::RemoveTenantIdFromMap(_GUID *)
0x180061e1c  test    edi, edi
0x180061e1e  jnz     loc_180061F7E
0x180061e24  lea     r9, [rsp+950h+var_8E0]
0x180061e29  mov     r8d, esi
0x180061e2c  mov     edx, 4000h
0x180061e31  mov     rcx, r14
0x180061e34  call    GetRoutingDomainConfigData
0x180061e39  mov     r8d, eax
0x180061e3c  mov     [rsp+950h+var_930], eax
0x180061e40  test    eax, eax
0x180061e42  jz      short loc_180061E89
0x180061e44  cmp     qword ptr cs:xmmword_1800C9740, r13
0x180061e4b  jz      loc_180061F7E
0x180061e51  mov     word ptr [rbp+850h+var_840], r13w
0x180061e56  lea     rdx, aGetroutingdoma_0; "GetRoutingDomainConfigData (for dial in"...
0x180061e5d  lea     rcx, [rbp+850h+var_840]
0x180061e61  call    FormatRRASErrorString
0x180061e66  lea     r8, [rbp+850h+var_840]
0x180061e6a  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180061e71  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180061e78  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180061e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061e84  jmp     loc_180061F7E
0x180061e89  mov     esi, r13d
0x180061e8c  cmp     [rbp+850h+var_888], r13d
0x180061e90  jbe     loc_180061F7E
0x180061e96  mov     edx, 14h; uBytes
0x180061e9b  lea     ecx, [rdx+2Ch]; uFlags
0x180061e9e  call    cs:__imp_LocalAlloc
0x180061ea4  mov     rbx, rax
0x180061ea7  test    rax, rax
0x180061eaa  jz      loc_180061F76
0x180061eb0  mov     ecx, esi
0x180061eb2  imul    r12, rcx, 402h
0x180061eb9  mov     rdi, [rbp+850h+var_880]
0x180061ebd  add     rdi, r12
0x180061ec0  movups  xmm0, xmmword ptr [r14]
0x180061ec4  movdqu  xmmword ptr [rax], xmm0
0x180061ec8  mov     edx, 2Bh ; '+'; Ch
0x180061ecd  mov     rcx, rdi; Str
0x180061ed0  call    cs:__imp_wcschr
0x180061ed6  test    rax, rax
0x180061ed9  jnz     short loc_180061EEF
0x180061edb  lea     edx, [rax+2Ah]; Ch
0x180061ede  mov     rcx, rdi; Str
0x180061ee1  call    cs:__imp_wcschr
0x180061ee7  test    rax, rax
0x180061eea  mov     eax, r13d
0x180061eed  jz      short loc_180061EF4
0x180061eef  mov     eax, 1
0x180061ef4  mov     [rbx+10h], eax
0x180061ef7  mov     rdx, [rbp+850h+var_880]
0x180061efb  add     rdx, r12; Src
0x180061efe  mov     [rbp+850h+var_858], 7
0x180061f06  mov     [rbp+850h+var_860], r13
0x180061f0a  mov     word ptr [rbp+850h+var_870], r13w
0x180061f0f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180061f13  inc     r8
0x180061f16  cmp     [rdx+r8*2], r13w
0x180061f1b  jnz     short loc_180061F13
0x180061f1d  lea     rcx, [rbp+850h+var_870]; void *
0x180061f21  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180061f26  mov     [rbp+850h+var_848], rbx
0x180061f2a  lea     rdi, [r15+88h]
0x180061f31  mov     rbx, [r15+90h]
0x180061f38  lea     rdx, [rbp+850h+var_870]
0x180061f3c  mov     rcx, rdi
0x180061f3f  call    ??$_Buynode@AEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@@std@@@?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@U_lessstr@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@@std@@@2@$0A@@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@U_lessstr@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@@std@@@2@$0A@@std@@@1@AEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@@1@@Z; std::_Tree_val<std::_Tmap_traits<std::wstring,_TenantIdentifierInfo *,_lessstr,std::allocator<std::pair<std::wstring const,_TenantIdentifierInfo *>>,0>>::_Buynode<std::pair<std::wstring,_TenantIdentifierInfo *> &>(std::pair<std::wstring,_TenantIdentifierInfo *> &)
0x180061f44  mov     r9, rax
0x180061f47  mov     r8, rbx
0x180061f4a  lea     rdx, [rsp+950h+var_8F0]
0x180061f4f  mov     rcx, rdi
0x180061f52  call    ?_Insert@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@U_lessstr@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@U_lessstr@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@@std@@@2@$0A@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@U_lessstr@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@@std@@@2@$0A@@std@@@std@@@2@PEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@U_lessstr@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@@std@@@2@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,_TenantIdentifierInfo *,_lessstr,std::allocator<std::pair<std::wstring const,_TenantIdentifierInfo *>>,0>>::_Insert(std::_Tree_const_iterator<std::_Tree_val<std::_Tmap_traits<std::wstring,_TenantIdentifierInfo *,_lessstr,std::allocator<std::pair<std::wstring const,_TenantIdentifierInfo *>>,0>>>,std::_Tree_nod<std::_Tmap_traits<std::wstring,_TenantIdentifierInfo *,_lessstr,std::allocator<std::pair<std::wstring const,_TenantIdentifierInfo *>>,0>>::_Node *)
0x180061f57  nop
0x180061f58  cmp     [rbp+850h+var_858], 8
0x180061f5d  jb      short loc_180061F69
0x180061f5f  mov     rcx, [rbp+850h+var_870]
0x180061f63  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180061f69  inc     esi
0x180061f6b  cmp     esi, [rbp+850h+var_888]
0x180061f6e  jb      loc_180061E96
0x180061f74  jmp     short loc_180061F7E
0x180061f76  mov     [rsp+950h+var_930], 8
0x180061f7e  mov     rax, cs:qword_1800C8690
0x180061f85  test    rax, rax
0x180061f88  jz      short loc_180061F99
0x180061f8a  lea     rdx, [rsp+950h+var_8E0]
0x180061f8f  mov     ecx, 4000h
0x180061f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061f99  mov     rcx, r15; this
0x180061f9c  call    ?ReleaseRdInfoListLock@RRasIPAddressMgr@@AEAAXXZ; RRasIPAddressMgr::ReleaseRdInfoListLock(void)
0x180061fa1  mov     ebx, [rsp+950h+var_930]
0x180061fa5  lea     rcx, [rsp+950h+var_928]; this
0x180061faa  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180061faf  mov     eax, ebx
0x180061fb1  mov     rcx, [rbp+850h+var_40]
0x180061fb8  xor     rcx, rsp; StackCookie
0x180061fbb  call    __security_check_cookie
0x180061fc0  mov     rbx, [rsp+950h+arg_10]
0x180061fc8  add     rsp, 920h
0x180061fcf  pop     r15
0x180061fd1  pop     r14
0x180061fd3  pop     r13
0x180061fd5  pop     r12
0x180061fd7  pop     rdi
0x180061fd8  pop     rsi
0x180061fd9  pop     rbp
0x180061fda  retn
```
