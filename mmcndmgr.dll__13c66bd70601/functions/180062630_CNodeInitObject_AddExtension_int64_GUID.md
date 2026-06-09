# CNodeInitObject::AddExtension(__int64,_GUID *)

- ea: `0x180062630`
- end: `0x180062812`
- name: `?AddExtension@CNodeInitObject@@MEAAJ_JPEAU_GUID@@@Z`
- size: `482`
- prototype: `int(CNodeInitObject *__hidden this, __int64, struct _GUID *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180016ba0`
- `0x18002a9c8`
- `0x180062630`
- `0x1800743dc`
- `0x18007ed44`
- `0x1800a5088`
- `0x18013f010`

## import_xrefs

- `mmcbase!?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ` at `0x18006268a`
- `mmcbase!?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ` at `0x18006268a`
- `mmcbase!?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180062680`
- `mmcbase!?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180062680`
- `mmcbase!?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z` at `0x1800626da`
- `mmcbase!?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z` at `0x1800626da`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1800626e4`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18006276b`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1800627db`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1800626e4`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18006276b`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1800627db`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180062654`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180062654`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800626c9`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006270a`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180062734`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180062761`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800627d1`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800626c9`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006270a`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180062734`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180062761`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800627d1`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180062665`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180062665`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800627f5`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800627f5`

## string_xrefs

- `0x18006265a`: `IConsoleNameSpace2::AddExtension`
- `0x1800626cf`: `NULL LPCLSID ptr`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNodeInitObject::AddExtension(CNodeInitObject *this, __int64 a2, struct _GUID *a3)
{
  const unsigned __int16 *v6; // rdx
  __int64 v7; // rdx
  const unsigned __int16 *v8; // rcx
  unsigned int v9; // ebx
  struct CMTNode *v10; // rax
  CMTNode *v11; // rbx
  int v12; // eax
  unsigned int v13; // eax
  int v14; // edi
  unsigned int v15; // eax
  void **v17; // [rsp+30h] [rbp-30h] BYREF
  struct CSnapInReference *v18; // [rsp+38h] [rbp-28h]
  _BYTE v19[32]; // [rsp+40h] [rbp-20h] BYREF
  int v20; // [rsp+80h] [rbp+20h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v19, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v19, L"IConsoleNameSpace2::AddExtension");
  v6 = (const unsigned __int16 *)((char *)this + 184);
  if ( *((_QWORD *)this + 26) >= 8u )
    v6 = *(const unsigned __int16 **)v6;
  mmcerror::SC::SetSnapinName((mmcerror::SC *)v19, v6);
  mmcerror::SC::CheckCallingThreadID((mmcerror::SC *)v19);
  v20 = 0;
  (*(void (__fastcall **)(char *, int *))(*((_QWORD *)this - 4) + 184LL))((char *)this - 32, &v20);
  if ( v20 == -1 )
  {
    v7 = 2147549183LL;
LABEL_14:
    mmcerror::SC::operator=(v19, v7);
    goto LABEL_8;
  }
  if ( !a3 )
  {
    mmcerror::SC::operator=(v19, 2147500035LL);
    v8 = L"NULL LPCLSID ptr";
LABEL_7:
    TraceSnapinError(v8, (const struct mmcerror::SC *)v19);
LABEL_8:
    v9 = mmcerror::SC::ToHr((mmcerror::SC *)v19);
    goto LABEL_21;
  }
  v10 = CMTNode::FromScopeItem(a2);
  v11 = v10;
  if ( !v10 )
  {
    mmcerror::SC::operator=(v19, 2147942487LL);
    v8 = L"Invalid hItem";
    goto LABEL_7;
  }
  v12 = *((_DWORD *)v10 + 60);
  if ( v12 != v20 && v12 != 60102025 )
  {
    v7 = 2147942487LL;
    goto LABEL_14;
  }
  v17 = &CSnapInReferencePtr::`vftable';
  v18 = 0;
  v13 = CSnapInReferencePtr::Create((CSnapInReferencePtr *)&v17, a3);
  mmcerror::SC::operator=(v19, v13);
  v14 = mmcerror::SC::ToHr((mmcerror::SC *)v19);
  if ( v14 >= 0 )
  {
    v15 = CMTNode::AddExtension(v11, v18);
    mmcerror::SC::operator=(v19, v15);
    v9 = mmcerror::SC::ToHr((mmcerror::SC *)v19);
    v17 = &CSnapInReferencePtr::`vftable';
    CSnapInReferencePtr::Clear((CSnapInReferencePtr *)&v17);
  }
  else
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      WPP_SF__guid_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        15,
        WPP_2a17de6afd653f090834b24b9a46db2a_Traceguids,
        a3,
        v14);
    v17 = &CSnapInReferencePtr::`vftable';
    CSnapInReferencePtr::Clear((CSnapInReferencePtr *)&v17);
    v9 = v14;
  }
LABEL_21:
  mmcerror::SC::~SC((mmcerror::SC *)v19);
  return v9;
}

```

## disassembly

```asm
0x180062630  mov     [rsp-18h+arg_8], rbx
0x180062635  mov     [rsp-18h+arg_10], rsi
0x18006263a  push    rbp
0x18006263b  push    rdi
0x18006263c  push    r14
0x18006263e  mov     rbp, rsp
0x180062641  sub     rsp, 60h
0x180062645  mov     rsi, r8
0x180062648  mov     rdi, rdx
0x18006264b  mov     rbx, rcx
0x18006264e  xor     edx, edx
0x180062650  lea     rcx, [rbp+var_20]
0x180062654  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x18006265a  lea     rdx, aIconsolenamesp_5; "IConsoleNameSpace2::AddExtension"
0x180062661  lea     rcx, [rbp+var_20]
0x180062665  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x18006266b  lea     rdx, [rbx+0B8h]
0x180062672  cmp     qword ptr [rdx+18h], 8
0x180062677  jb      short loc_18006267C
0x180062679  mov     rdx, [rdx]
0x18006267c  lea     rcx, [rbp+var_20]
0x180062680  call    cs:__imp_?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetSnapinName(ushort const *)
0x180062686  lea     rcx, [rbp+var_20]
0x18006268a  call    cs:__imp_?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ; mmcerror::SC::CheckCallingThreadID(void)
0x180062690  mov     [rbp+arg_0], 0
0x180062697  lea     rcx, [rbx-20h]
0x18006269b  mov     rax, [rcx]
0x18006269e  lea     rdx, [rbp+arg_0]
0x1800626a2  mov     rax, [rax+0B8h]
0x1800626a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800626ae  cmp     [rbp+arg_0], 0FFFFFFFFh
0x1800626b2  jnz     short loc_1800626BB
0x1800626b4  mov     edx, 8000FFFFh
0x1800626b9  jmp     short loc_180062730
0x1800626bb  test    rsi, rsi
0x1800626be  jnz     short loc_1800626F1
0x1800626c0  mov     edx, 80004003h
0x1800626c5  lea     rcx, [rbp+var_20]
0x1800626c9  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1800626cf  lea     rcx, aNullLpclsidPtr; "NULL LPCLSID ptr"
0x1800626d6  lea     rdx, [rbp+var_20]
0x1800626da  call    cs:__imp_?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z; TraceSnapinError(ushort const *,mmcerror::SC const &)
0x1800626e0  lea     rcx, [rbp+var_20]
0x1800626e4  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x1800626ea  mov     ebx, eax
0x1800626ec  jmp     loc_1800627F1
0x1800626f1  mov     rcx, rdi; __int64
0x1800626f4  call    ?FromScopeItem@CMTNode@@SAPEAV1@_J@Z; CMTNode::FromScopeItem(__int64)
0x1800626f9  mov     rbx, rax
0x1800626fc  test    rax, rax
0x1800626ff  jnz     short loc_180062719
0x180062701  mov     edx, 80070057h
0x180062706  lea     rcx, [rbp+var_20]
0x18006270a  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x180062710  lea     rcx, aInvalidHitem; "Invalid hItem"
0x180062717  jmp     short loc_1800626D6
0x180062719  mov     eax, [rax+0F0h]
0x18006271f  cmp     eax, [rbp+arg_0]
0x180062722  jz      short loc_18006273C
0x180062724  cmp     eax, 3951589h
0x180062729  jz      short loc_18006273C
0x18006272b  mov     edx, 80070057h
0x180062730  lea     rcx, [rbp+var_20]
0x180062734  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18006273a  jmp     short loc_1800626E0
0x18006273c  lea     r14, ??_7CSnapInReferencePtr@@6B@; const CSnapInReferencePtr::`vftable'
0x180062743  mov     [rbp+var_30], r14
0x180062747  mov     [rbp+var_28], 0
0x18006274f  mov     rdx, rsi; struct _GUID *
0x180062752  lea     rcx, [rbp+var_30]; this
0x180062756  call    ?Create@CSnapInReferencePtr@@QEAAJAEBU_GUID@@@Z; CSnapInReferencePtr::Create(_GUID const &)
0x18006275b  mov     edx, eax
0x18006275d  lea     rcx, [rbp+var_20]
0x180062761  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x180062767  lea     rcx, [rbp+var_20]
0x18006276b  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x180062771  mov     edi, eax
0x180062773  test    eax, eax
0x180062775  jns     short loc_1800627BF
0x180062777  lea     rax, WPP_GLOBAL_Control
0x18006277e  mov     rcx, cs:WPP_GLOBAL_Control
0x180062785  cmp     rcx, rax
0x180062788  jz      short loc_1800627AD
0x18006278a  cmp     byte ptr [rcx+19h], 2
0x18006278e  jb      short loc_1800627AD
0x180062790  mov     edx, 0Fh
0x180062795  mov     [rsp+60h+var_40], edi
0x180062799  mov     r9, rsi
0x18006279c  lea     r8, WPP_2a17de6afd653f090834b24b9a46db2a_Traceguids
0x1800627a3  mov     rcx, [rcx+10h]
0x1800627a7  call    WPP_SF__guid_d
0x1800627ac  nop
0x1800627ad  mov     [rbp+var_30], r14
0x1800627b1  lea     rcx, [rbp+var_30]; this
0x1800627b5  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
0x1800627ba  nop
0x1800627bb  mov     ebx, edi
0x1800627bd  jmp     short loc_1800627F1
0x1800627bf  mov     rdx, [rbp+var_28]; struct CSnapInReference *
0x1800627c3  mov     rcx, rbx; this
0x1800627c6  call    ?AddExtension@CMTNode@@QEAAJAEBVCSnapInReference@@@Z; CMTNode::AddExtension(CSnapInReference const &)
0x1800627cb  mov     edx, eax
0x1800627cd  lea     rcx, [rbp+var_20]
0x1800627d1  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1800627d7  lea     rcx, [rbp+var_20]
0x1800627db  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x1800627e1  mov     ebx, eax
0x1800627e3  mov     [rbp+var_30], r14
0x1800627e7  lea     rcx, [rbp+var_30]; this
0x1800627eb  call    ?Clear@CSnapInReferencePtr@@AEAAXXZ; CSnapInReferencePtr::Clear(void)
0x1800627f0  nop
0x1800627f1  lea     rcx, [rbp+var_20]
0x1800627f5  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1800627fb  mov     eax, ebx
0x1800627fd  lea     r11, [rsp+60h+var_s0]
0x180062802  mov     rbx, [r11+28h]
0x180062806  mov     rsi, [r11+30h]
0x18006280a  mov     rsp, r11
0x18006280d  pop     r14
0x18006280f  pop     rdi
0x180062810  pop     rbp
0x180062811  retn
```
