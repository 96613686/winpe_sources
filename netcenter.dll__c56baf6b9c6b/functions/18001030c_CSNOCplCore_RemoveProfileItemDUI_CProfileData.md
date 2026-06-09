# CSNOCplCore::RemoveProfileItemDUI(CProfileData *)

- ea: `0x18001030c`
- end: `0x1800104a5`
- name: `?RemoveProfileItemDUI@CSNOCplCore@@AEAAJPEAVCProfileData@@@Z`
- size: `409`
- prototype: `int(CSNOCplCore *__hidden this, struct CProfileData *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000a1f0`
- `0x18000f9ec`

## callees

- `0x180002270`
- `0x18001030c`
- `0x180012580`
- `0x180014274`
- `0x1800142b4`
- `0x180014448`
- `0x18001bec0`

## import_xrefs

- `DUI70!StrToID` at `0x18001038b`
- `DUI70!StrToID` at `0x18001038b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180010397`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180010397`
- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x1800103bd`
- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x1800103bd`
- `DUI70!?DestroyAll@Element@DirectUI@@QEAAJ_N@Z` at `0x1800103dc`
- `DUI70!?DestroyAll@Element@DirectUI@@QEAAJ_N@Z` at `0x1800103dc`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800103ac`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800103ac`

## string_xrefs

- `0x1800103fc`: `REMOVED`

## pseudocode

```c
__int64 __fastcall CSNOCplCore::RemoveProfileItemDUI(CSNOCplCore *this, struct CProfileData *a2, __int64 a3)
{
  unsigned int v6; // esi
  DirectUI::Element *v7; // rbx
  unsigned __int16 v8; // ax
  DirectUI::Element *Descendent; // rax
  __int64 v10; // r8
  struct DirectUI::Element *v11; // rbx
  DirectUI::Element *Parent; // rax
  int v13; // r8d
  PVOID *v14; // rcx
  __int64 v15; // rdx
  unsigned __int16 v16[40]; // [rsp+30h] [rbp-78h] BYREF

  if ( !a2 )
    return 2147500035LL;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, a3, *((_QWORD *)a2 + 2));
  v6 = -2147418113;
  StringFromGUID2((struct _GUID *)a2, v16, a3);
  v7 = (DirectUI::Element *)*((_QWORD *)this + 40);
  v8 = StrToID(v16);
  Descendent = DirectUI::Element::FindDescendent(v7, v8);
  v11 = Descendent;
  if ( !Descendent )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v6;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_19;
    v15 = 121;
    goto LABEL_17;
  }
  Parent = DirectUI::Element::GetParent(Descendent);
  if ( !Parent )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v6;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_19;
    v15 = 120;
LABEL_17:
    WPP_SF_S(v14[2], v15, v10, v16);
LABEL_18:
    v14 = (PVOID *)WPP_GLOBAL_Control;
LABEL_19:
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 8) != 0 )
      WPP_SF_d(v14[2], 122, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids, v6);
    return v6;
  }
  v6 = DirectUI::Element::Remove(Parent, v11);
  DUI_WalkIUnknownElements(v11, (void (*)(struct IUnknown *, __int64))DUI_SetSiteOnUnknown, 0);
  DirectUI::Element::DestroyAll(v11, 0);
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_19;
    WPP_SF_Ss(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, v13, *((_QWORD *)a2 + 2), (__int64)"REMOVED");
    goto LABEL_18;
  }
  return v6;
}

```

## disassembly

```asm
0x18001030c  mov     [rsp+arg_10], rbx
0x180010311  push    rbp
0x180010312  push    rsi
0x180010313  push    rdi
0x180010314  sub     rsp, 90h
0x18001031b  mov     rax, cs:__security_cookie
0x180010322  xor     rax, rsp
0x180010325  mov     [rsp+0A8h+var_28], rax
0x18001032d  mov     rdi, rdx
0x180010330  mov     rbx, rcx
0x180010333  test    rdx, rdx
0x180010336  jnz     short loc_180010342
0x180010338  mov     eax, 80004003h
0x18001033d  jmp     loc_180010482
0x180010342  mov     rcx, cs:WPP_GLOBAL_Control
0x180010349  lea     rbp, WPP_GLOBAL_Control
0x180010350  cmp     rcx, rbp
0x180010353  jz      short loc_18001036D
0x180010355  test    byte ptr [rcx+1Ch], 4
0x180010359  jz      short loc_18001036D
0x18001035b  mov     r9, [rdi+10h]
0x18001035f  mov     edx, 76h ; 'v'
0x180010364  mov     rcx, [rcx+10h]
0x180010368  call    WPP_SF_S
0x18001036d  lea     rdx, [rsp+0A8h+var_78]; unsigned __int16 *
0x180010372  mov     rcx, rdi; struct _GUID *
0x180010375  mov     esi, 8000FFFFh
0x18001037a  call    ?StringFromGUID2@@YAXAEAU_GUID@@PEAGK@Z; StringFromGUID2(_GUID &,ushort *,ulong)
0x18001037f  mov     rbx, [rbx+140h]
0x180010386  lea     rcx, [rsp+0A8h+var_78]
0x18001038b  call    cs:__imp_StrToID
0x180010391  movzx   edx, ax
0x180010394  mov     rcx, rbx
0x180010397  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001039d  mov     rbx, rax
0x1800103a0  test    rax, rax
0x1800103a3  jz      loc_180010431
0x1800103a9  mov     rcx, rax
0x1800103ac  call    cs:__imp_?GetParent@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetParent(void)
0x1800103b2  test    rax, rax
0x1800103b5  jz      short loc_180010418
0x1800103b7  mov     rdx, rbx
0x1800103ba  mov     rcx, rax
0x1800103bd  call    cs:__imp_?Remove@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Remove(DirectUI::Element *)
0x1800103c3  xor     r8d, r8d; __int64
0x1800103c6  lea     rdx, ?DUI_SetSiteOnUnknown@@YAXPEAUIUnknown@@_J@Z; void (*)(struct IUnknown *, __int64)
0x1800103cd  mov     rcx, rbx; struct DirectUI::Element *
0x1800103d0  mov     esi, eax
0x1800103d2  call    ?DUI_WalkIUnknownElements@@YAXPEAVElement@DirectUI@@P6AXPEAUIUnknown@@_J@Z2@Z; DUI_WalkIUnknownElements(DirectUI::Element *,void (*)(IUnknown *,__int64),__int64)
0x1800103d7  xor     edx, edx
0x1800103d9  mov     rcx, rbx
0x1800103dc  call    cs:__imp_?DestroyAll@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::DestroyAll(bool)
0x1800103e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103e9  cmp     rcx, rbp
0x1800103ec  jz      loc_180010480
0x1800103f2  test    byte ptr [rcx+1Ch], 4
0x1800103f6  jz      short loc_18001045D
0x1800103f8  mov     r9, [rdi+10h]
0x1800103fc  lea     rax, aRemoved; "REMOVED"
0x180010403  mov     rcx, [rcx+10h]
0x180010407  mov     edx, 77h ; 'w'
0x18001040c  mov     [rsp+0A8h+var_88], rax
0x180010411  call    WPP_SF_Ss
0x180010416  jmp     short loc_180010456
0x180010418  mov     rcx, cs:WPP_GLOBAL_Control
0x18001041f  cmp     rcx, rbp
0x180010422  jz      short loc_180010480
0x180010424  test    byte ptr [rcx+1Ch], 2
0x180010428  jz      short loc_18001045D
0x18001042a  mov     edx, 78h ; 'x'
0x18001042f  jmp     short loc_180010448
0x180010431  mov     rcx, cs:WPP_GLOBAL_Control
0x180010438  cmp     rcx, rbp
0x18001043b  jz      short loc_180010480
0x18001043d  test    byte ptr [rcx+1Ch], 2
0x180010441  jz      short loc_18001045D
0x180010443  mov     edx, 79h ; 'y'
0x180010448  mov     rcx, [rcx+10h]
0x18001044c  lea     r9, [rsp+0A8h+var_78]
0x180010451  call    WPP_SF_S
0x180010456  mov     rcx, cs:WPP_GLOBAL_Control
0x18001045d  cmp     rcx, rbp
0x180010460  jz      short loc_180010480
0x180010462  test    byte ptr [rcx+1Ch], 8
0x180010466  jz      short loc_180010480
0x180010468  mov     rcx, [rcx+10h]
0x18001046c  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x180010473  mov     edx, 7Ah ; 'z'
0x180010478  mov     r9d, esi
0x18001047b  call    WPP_SF_d
0x180010480  mov     eax, esi
0x180010482  mov     rcx, [rsp+0A8h+var_28]
0x18001048a  xor     rcx, rsp; StackCookie
0x18001048d  call    __security_check_cookie
0x180010492  mov     rbx, [rsp+0A8h+arg_10]
0x18001049a  add     rsp, 90h
0x1800104a1  pop     rdi
0x1800104a2  pop     rsi
0x1800104a3  pop     rbp
0x1800104a4  retn
```
