# RRasIPAddressMgr::UpdateTenantIdInMap(_GUID *,int)

- ea: `0x180064388`
- end: `0x180064659`
- name: `?UpdateTenantIdInMap@RRasIPAddressMgr@@QEAAKPEAU_GUID@@H@Z`
- size: `721`
- prototype: `unsigned int __fastcall(RRasIPAddressMgr *__hidden this, struct _GUID *, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180053854`

## callees

- `0x180027ec0`
- `0x180060d98`
- `0x180062854`
- `0x180063ac8`
- `0x180063b04`
- `0x180064388`
- `0x180067c24`
- `0x180069334`
- `0x1800753f4`
- `0x1800754ac`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `msvcrt!wcschr` at `0x180064533`
- `msvcrt!wcschr` at `0x18006454a`
- `msvcrt!wcschr` at `0x180064533`
- `msvcrt!wcschr` at `0x18006454a`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800645da`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800645da`
- `KERNEL32!LocalAlloc` at `0x1800644fb`
- `KERNEL32!LocalAlloc` at `0x1800644fb`

## string_xrefs

- `0x180064427`: `RRasIPAddressMgr::UpdateTenantIdInMap`
- `0x1800644b3`: `GetRoutingDomainConfigData (for dial in config) returned error %d`

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
  if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v22,
      L"RRasIPAddressMgr::UpdateTenantIdInMap",
      &v21,
      v7);
    v6 = v21;
  }
  if ( dword_1800CF650
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
        if ( (_QWORD)xmmword_1800D0740 )
        {
          LOWORD(v35) = 0;
          FormatRRASErrorString(
            &v35,
            L"GetRoutingDomainConfigData (for dial in config) returned error %d",
            RoutingDomainConfigData);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800D0740,
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
    if ( qword_1800CF690 )
      qword_1800CF690(0x4000, v29);
    RRasIPAddressMgr::ReleaseRdInfoListLock(this);
    v6 = v21;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v22);
  return v6;
}

```

## disassembly

```asm
0x180064388  mov     [rsp-8+arg_10], rbx
0x18006438d  push    rbp
0x18006438e  push    rsi
0x18006438f  push    rdi
0x180064390  push    r12
0x180064392  push    r13
0x180064394  push    r14
0x180064396  push    r15
0x180064398  lea     rbp, [rsp-820h]
0x1800643a0  sub     rsp, 920h
0x1800643a7  mov     rax, cs:__security_cookie
0x1800643ae  xor     rax, rsp
0x1800643b1  mov     [rbp+850h+var_40], rax
0x1800643b8  mov     edi, r8d
0x1800643bb  mov     r14, rdx
0x1800643be  mov     r15, rcx
0x1800643c1  xor     r13d, r13d
0x1800643c4  mov     ebx, r13d
0x1800643c7  mov     [rsp+950h+var_930], ebx
0x1800643cb  lea     esi, [r13+68h]
0x1800643cf  mov     r8d, esi; Size
0x1800643d2  xor     edx, edx; Val
0x1800643d4  lea     rcx, [rsp+950h+var_8E0]; void *
0x1800643d9  call    memset_0
0x1800643de  mov     [rbp+850h+var_840], r13d
0x1800643e2  xor     edx, edx; Val
0x1800643e4  mov     r8d, 7FCh; Size
0x1800643ea  lea     rcx, [rbp+850h+var_83C]; void *
0x1800643ee  call    memset_0
0x1800643f3  xorps   xmm0, xmm0
0x1800643f6  movdqu  [rsp+950h+var_920], xmm0
0x1800643fc  mov     [rsp+950h+var_928], r13
0x180064401  xorps   xmm1, xmm1
0x180064404  movdqu  [rsp+950h+var_910], xmm1
0x18006440a  mov     [rsp+950h+var_900], r13
0x18006440f  or      [rsp+950h+var_8F8], 0FFFFFFFFh
0x180064414  mov     [rsp+950h+var_8F4], r13d
0x180064419  cmp     qword ptr cs:xmmword_1800D0740+8, r13
0x180064420  jz      short loc_18006443C
0x180064422  lea     r8, [rsp+950h+var_930]; unsigned int *
0x180064427  lea     rdx, aRrasipaddressm_13; "RRasIPAddressMgr::UpdateTenantIdInMap"
0x18006442e  lea     rcx, [rsp+950h+var_928]; this
0x180064433  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180064438  mov     ebx, [rsp+950h+var_930]
0x18006443c  cmp     cs:dword_1800CF650, r13d
0x180064443  jz      loc_180064622
0x180064449  mov     rax, [r14]
0x18006444c  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180064453  jnz     short loc_180064466
0x180064455  mov     rax, [r14+8]
0x180064459  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180064460  jz      loc_180064622
0x180064466  mov     rcx, r15; this
0x180064469  call    ?AcquireRdInfoListLock@RRasIPAddressMgr@@AEAAXXZ; RRasIPAddressMgr::AcquireRdInfoListLock(void)
0x18006446e  mov     rdx, r14; struct _GUID *
0x180064471  mov     rcx, r15; this
0x180064474  call    ?RemoveTenantIdFromMap@RRasIPAddressMgr@@AEAAKPEAU_GUID@@@Z; RRasIPAddressMgr::RemoveTenantIdFromMap(_GUID *)
0x180064479  test    edi, edi
0x18006447b  jnz     loc_1800645FB
0x180064481  lea     r9, [rsp+950h+var_8E0]
0x180064486  mov     r8d, esi
0x180064489  mov     edx, 4000h
0x18006448e  mov     rcx, r14
0x180064491  call    GetRoutingDomainConfigData
0x180064496  mov     [rsp+950h+var_930], eax
0x18006449a  test    eax, eax
0x18006449c  jz      short loc_1800644E6
0x18006449e  cmp     qword ptr cs:xmmword_1800D0740, r13
0x1800644a5  jz      loc_1800645FB
0x1800644ab  mov     word ptr [rbp+850h+var_840], r13w
0x1800644b0  mov     r8d, eax
0x1800644b3  lea     rdx, aGetroutingdoma_0; "GetRoutingDomainConfigData (for dial in"...
0x1800644ba  lea     rcx, [rbp+850h+var_840]
0x1800644be  call    FormatRRASErrorString
0x1800644c3  lea     r8, [rbp+850h+var_840]
0x1800644c7  mov     rdx, qword ptr cs:xmmword_1800D0740
0x1800644ce  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800644d5  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800644dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800644e1  jmp     loc_1800645FB
0x1800644e6  mov     esi, r13d
0x1800644e9  cmp     [rbp+850h+var_888], r13d
0x1800644ed  jbe     loc_1800645FB
0x1800644f3  mov     edx, 14h; uBytes
0x1800644f8  lea     ecx, [rdx+2Ch]; uFlags
0x1800644fb  call    cs:__imp_LocalAlloc
0x180064502  nop     dword ptr [rax+rax+00h]
0x180064507  mov     rbx, rax
0x18006450a  test    rax, rax
0x18006450d  jz      loc_1800645F3
0x180064513  mov     ecx, esi
0x180064515  imul    r12, rcx, 402h
0x18006451c  mov     rdi, [rbp+850h+var_880]
0x180064520  add     rdi, r12
0x180064523  movups  xmm0, xmmword ptr [r14]
0x180064527  movdqu  xmmword ptr [rax], xmm0
0x18006452b  mov     edx, 2Bh ; '+'; Ch
0x180064530  mov     rcx, rdi; Str
0x180064533  call    cs:__imp_wcschr
0x18006453a  nop     dword ptr [rax+rax+00h]
0x18006453f  test    rax, rax
0x180064542  jnz     short loc_18006455E
0x180064544  lea     edx, [rax+2Ah]; Ch
0x180064547  mov     rcx, rdi; Str
0x18006454a  call    cs:__imp_wcschr
0x180064551  nop     dword ptr [rax+rax+00h]
0x180064556  test    rax, rax
0x180064559  mov     eax, r13d
0x18006455c  jz      short loc_180064563
0x18006455e  mov     eax, 1
0x180064563  mov     edx, 10h
0x180064568  mov     rcx, rbx
0x18006456b  mov     [rdx+rbx], eax
0x18006456e  mov     rdx, [rbp+850h+var_880]
0x180064572  add     rdx, r12; Src
0x180064575  mov     [rbp+850h+var_858], 7
0x18006457d  mov     [rbp+850h+var_860], r13
0x180064581  mov     word ptr [rbp+850h+var_870], r13w
0x180064586  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006458a  inc     r8
0x18006458d  cmp     [rdx+r8*2], r13w
0x180064592  jnz     short loc_18006458A
0x180064594  lea     rcx, [rbp+850h+var_870]; void *
0x180064598  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18006459d  mov     [rbp+850h+var_848], rbx
0x1800645a1  lea     rdi, [r15+88h]
0x1800645a8  mov     rbx, [r15+90h]
0x1800645af  lea     rdx, [rbp+850h+var_870]
0x1800645b3  mov     rcx, rdi
0x1800645b6  call    ??$_Buynode@AEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@@std@@@?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@U_lessstr@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@@std@@@2@$0A@@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@U_lessstr@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@@std@@@2@$0A@@std@@@1@AEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@@1@@Z; std::_Tree_val<std::_Tmap_traits<std::wstring,_TenantIdentifierInfo *,_lessstr,std::allocator<std::pair<std::wstring const,_TenantIdentifierInfo *>>,0>>::_Buynode<std::pair<std::wstring,_TenantIdentifierInfo *> &>(std::pair<std::wstring,_TenantIdentifierInfo *> &)
0x1800645bb  mov     r9, rax
0x1800645be  mov     r8, rbx
0x1800645c1  lea     rdx, [rsp+950h+var_8F0]
0x1800645c6  mov     rcx, rdi
0x1800645c9  call    ?_Insert@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@U_lessstr@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@U_lessstr@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@@std@@@2@$0A@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@U_lessstr@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@@std@@@2@$0A@@std@@@std@@@2@PEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@U_lessstr@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_TenantIdentifierInfo@@@std@@@2@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,_TenantIdentifierInfo *,_lessstr,std::allocator<std::pair<std::wstring const,_TenantIdentifierInfo *>>,0>>::_Insert(std::_Tree_const_iterator<std::_Tree_val<std::_Tmap_traits<std::wstring,_TenantIdentifierInfo *,_lessstr,std::allocator<std::pair<std::wstring const,_TenantIdentifierInfo *>>,0>>>,std::_Tree_nod<std::_Tmap_traits<std::wstring,_TenantIdentifierInfo *,_lessstr,std::allocator<std::pair<std::wstring const,_TenantIdentifierInfo *>>,0>>::_Node *)
0x1800645ce  nop
0x1800645cf  cmp     [rbp+850h+var_858], 8
0x1800645d4  jb      short loc_1800645E6
0x1800645d6  mov     rcx, [rbp+850h+var_870]
0x1800645da  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800645e1  nop     dword ptr [rax+rax+00h]
0x1800645e6  inc     esi
0x1800645e8  cmp     esi, [rbp+850h+var_888]
0x1800645eb  jb      loc_1800644F3
0x1800645f1  jmp     short loc_1800645FB
0x1800645f3  mov     [rsp+950h+var_930], 8
0x1800645fb  mov     rax, cs:qword_1800CF690
0x180064602  test    rax, rax
0x180064605  jz      short loc_180064616
0x180064607  lea     rdx, [rsp+950h+var_8E0]
0x18006460c  mov     ecx, 4000h
0x180064611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064616  mov     rcx, r15; this
0x180064619  call    ?ReleaseRdInfoListLock@RRasIPAddressMgr@@AEAAXXZ; RRasIPAddressMgr::ReleaseRdInfoListLock(void)
0x18006461e  mov     ebx, [rsp+950h+var_930]
0x180064622  lea     rcx, [rsp+950h+var_928]; this
0x180064627  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18006462c  mov     eax, ebx
0x18006462e  mov     rcx, [rbp+850h+var_40]
0x180064635  xor     rcx, rsp; StackCookie
0x180064638  call    __security_check_cookie
0x18006463d  mov     rbx, [rsp+950h+arg_10]
0x180064645  add     rsp, 920h
0x18006464c  pop     r15
0x18006464e  pop     r14
0x180064650  pop     r13
0x180064652  pop     r12
0x180064654  pop     rdi
0x180064655  pop     rsi
0x180064656  pop     rbp
0x180064657  retn
```
