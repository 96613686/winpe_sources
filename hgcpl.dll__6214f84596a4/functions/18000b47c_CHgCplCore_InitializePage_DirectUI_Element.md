# CHgCplCore::InitializePage(DirectUI::Element *)

- ea: `0x18000b47c`
- end: `0x18000b663`
- name: `?InitializePage@CHgCplCore@@QEAAJPEAVElement@DirectUI@@@Z`
- size: `487`
- prototype: `__int64 __fastcall(CHgCplCore *__hidden this, struct DirectUI::Element *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000f410`

## callees

- `0x18000766c`
- `0x18000b18c`
- `0x18000b280`
- `0x18000b47c`
- `0x18000b8ec`
- `0x180016b70`
- `0x180018a80`
- `0x18001a010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_GetSite` at `0x18000b5fc`
- `SHLWAPI!__imp_IUnknown_GetSite` at `0x18000b5fc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b4f3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b4f3`
- `DUI70!StrToID` at `0x18000b55f`
- `DUI70!StrToID` at `0x18000b55f`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x18000b54f`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x18000b54f`

## pseudocode

```c
__int64 __fastcall CHgCplCore::InitializePage(CHgCplCore *this, struct DirectUI::Element *a2, __int64 a3)
{
  __int64 *v5; // r15
  HRESULT Instance; // edi
  void (__fastcall ***v7)(_QWORD, __int64); // rcx
  unsigned __int16 ID; // bx
  unsigned __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  _QWORD *v12; // rax
  __int64 v13; // r14
  __int64 v14; // rbx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HWND, __int64, __int64); // rsi
  HWND ParentWindow; // rax
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+30h] [rbp-48h] BYREF

  if ( (Microsoft_Windows_HomeGroup_ControlPanelEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (__int64)this,
      (const EVENT_DESCRIPTOR *)Perf_Initialization_Page_Start,
      a3,
      1u,
      &v19);
  v5 = (__int64 *)((char *)this + 16);
  *((_QWORD *)this + 3) = a2;
  SafeRelease<IUnknown>((char *)this + 16);
  Instance = CoCreateInstance(
               &CLSID_StdGlobalInterfaceTable,
               0,
               1u,
               &GUID_00000146_0000_0000_c000_000000000046,
               (LPVOID *)this + 7);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(_QWORD, CHgCplCore *, GUID *, char *))(**((_QWORD **)this + 7) + 24LL))(
                 *((_QWORD *)this + 7),
                 this,
                 &IID_IHomeGroupCplUpdate,
                 (char *)this + 64);
    if ( Instance >= 0 )
      **((_DWORD **)this + 5) = *((_DWORD *)this + 16);
  }
  v7 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 4);
  if ( v7 )
    (**v7)(v7, 1);
  *((_QWORD *)this + 4) = 0;
  ID = DirectUI::Element::GetID(a2);
  if ( ID == (unsigned __int16)StrToID(L"Advanced") )
  {
    v12 = DirectUI::HAllocAndZero((DirectUI *)0x80, v9);
    if ( !v12 )
    {
      *((_QWORD *)this + 4) = 0;
      Instance = -2147024882;
      goto LABEL_18;
    }
    *v12 = &CAdvancedPage::`vftable';
    *((_QWORD *)this + 4) = v12;
  }
  else if ( Instance < 0 )
  {
    goto LABEL_18;
  }
  v13 = *((_QWORD *)this + 4);
  v14 = *((_QWORD *)this + 5);
  v15 = *((_QWORD *)this + 3);
  v16 = *(__int64 (__fastcall **)(__int64, HWND, __int64, __int64))(*(_QWORD *)v13 + 8LL);
  ParentWindow = CHgCplCore::_GetParentWindow(this);
  Instance = v16(v13, ParentWindow, v15, v14);
  if ( Instance >= 0 )
  {
    if ( *v5 )
    {
      Instance = 0;
    }
    else
    {
      Instance = IUnknown_GetSite(
                   (IUnknown *)((*((_QWORD *)this + 3) + 208LL) & -(__int64)(*((_QWORD *)this + 3) != 0)),
                   &GUID_00000000_0000_0000_c000_000000000046,
                   (void **)this + 2);
      if ( Instance < 0 )
        goto LABEL_18;
    }
    DUI_WalkIUnknownElements(
      *((struct DirectUI::Element **)this + 3),
      (void (*)(struct IUnknown *, __int64))DUI_SetSiteOnUnknown,
      *v5);
  }
LABEL_18:
  if ( (Microsoft_Windows_HomeGroup_ControlPanelEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(v10, (const EVENT_DESCRIPTOR *)Perf_Initialization_Page_Stop, v11, 1u, &v19);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000b47c  mov     [rsp+arg_10], rbx
0x18000b481  push    rbp
0x18000b482  push    rsi
0x18000b483  push    rdi
0x18000b484  push    r14
0x18000b486  push    r15
0x18000b488  sub     rsp, 50h
0x18000b48c  mov     rax, cs:__security_cookie
0x18000b493  xor     rax, rsp
0x18000b496  mov     [rsp+78h+var_38], rax
0x18000b49b  test    cs:Microsoft_Windows_HomeGroup_ControlPanelEnableBits, 4
0x18000b4a2  mov     rbx, rdx
0x18000b4a5  mov     rbp, rcx
0x18000b4a8  jz      short loc_18000B4C6
0x18000b4aa  lea     rax, [rsp+78h+var_48]
0x18000b4af  mov     r9d, 1
0x18000b4b5  lea     rdx, Perf_Initialization_Page_Start
0x18000b4bc  mov     [rsp+78h+ppv], rax
0x18000b4c1  call    McGenEventWrite_EventWriteTransfer
0x18000b4c6  lea     r15, [rbp+10h]
0x18000b4ca  mov     [rbp+18h], rbx
0x18000b4ce  mov     rcx, r15
0x18000b4d1  call    ??$SafeRelease@UIUnknown@@@@YAXPEAPEAUIUnknown@@@Z; SafeRelease<IUnknown>(IUnknown * *)
0x18000b4d6  xor     edx, edx; pUnkOuter
0x18000b4d8  lea     rsi, [rbp+38h]
0x18000b4dc  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000b4e3  mov     [rsp+78h+ppv], rsi; ppv
0x18000b4e8  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000b4ef  lea     r8d, [rdx+1]; dwClsContext
0x18000b4f3  call    cs:__imp_CoCreateInstance
0x18000b4f9  mov     edi, eax
0x18000b4fb  test    eax, eax
0x18000b4fd  js      short loc_18000B52B
0x18000b4ff  mov     rcx, [rsi]
0x18000b502  lea     r9, [rbp+40h]
0x18000b506  lea     r8, IID_IHomeGroupCplUpdate
0x18000b50d  mov     rdx, rbp
0x18000b510  mov     rax, [rcx]
0x18000b513  mov     rax, [rax+18h]
0x18000b517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b51c  mov     edi, eax
0x18000b51e  test    eax, eax
0x18000b520  js      short loc_18000B52B
0x18000b522  mov     rcx, [rbp+28h]
0x18000b526  mov     eax, [rbp+40h]
0x18000b529  mov     [rcx], eax
0x18000b52b  mov     rcx, [rbp+20h]
0x18000b52f  test    rcx, rcx
0x18000b532  jz      short loc_18000B544
0x18000b534  mov     rax, [rcx]
0x18000b537  mov     edx, 1
0x18000b53c  mov     rax, [rax]
0x18000b53f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b544  mov     rcx, rbx
0x18000b547  mov     qword ptr [rbp+20h], 0
0x18000b54f  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x18000b555  lea     rcx, aAdvanced; "Advanced"
0x18000b55c  movzx   ebx, ax
0x18000b55f  call    cs:__imp_StrToID
0x18000b565  cmp     bx, ax
0x18000b568  jnz     short loc_18000B59B
0x18000b56a  mov     ecx, 80h; this
0x18000b56f  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000b574  test    rax, rax
0x18000b577  jz      short loc_18000B589
0x18000b579  lea     rcx, ??_7CAdvancedPage@@6B@; const CAdvancedPage::`vftable'
0x18000b580  mov     [rax], rcx
0x18000b583  mov     [rbp+20h], rax
0x18000b587  jmp     short loc_18000B59F
0x18000b589  mov     qword ptr [rbp+20h], 0
0x18000b591  mov     edi, 8007000Eh
0x18000b596  jmp     loc_18000B61B
0x18000b59b  test    edi, edi
0x18000b59d  js      short loc_18000B61B
0x18000b59f  mov     r14, [rbp+20h]
0x18000b5a3  mov     rcx, rbp; this
0x18000b5a6  mov     rbx, [rbp+28h]
0x18000b5aa  mov     rdi, [rbp+18h]
0x18000b5ae  mov     rax, [r14]
0x18000b5b1  mov     rsi, [rax+8]
0x18000b5b5  call    ?_GetParentWindow@CHgCplCore@@AEAAPEAUHWND__@@XZ; CHgCplCore::_GetParentWindow(void)
0x18000b5ba  mov     rdx, rax
0x18000b5bd  mov     r9, rbx
0x18000b5c0  mov     rax, rsi
0x18000b5c3  mov     r8, rdi
0x18000b5c6  mov     rcx, r14
0x18000b5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5ce  mov     edi, eax
0x18000b5d0  test    eax, eax
0x18000b5d2  js      short loc_18000B61B
0x18000b5d4  cmp     qword ptr [r15], 0
0x18000b5d8  jz      short loc_18000B5DE
0x18000b5da  xor     edi, edi
0x18000b5dc  jmp     short loc_18000B608
0x18000b5de  mov     rax, [rbp+18h]
0x18000b5e2  mov     r8, r15; ppv
0x18000b5e5  lea     rdx, [rax+0D0h]
0x18000b5ec  neg     rax
0x18000b5ef  sbb     rcx, rcx
0x18000b5f2  and     rcx, rdx; punk
0x18000b5f5  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18000b5fc  call    cs:__imp_IUnknown_GetSite
0x18000b602  mov     edi, eax
0x18000b604  test    eax, eax
0x18000b606  js      short loc_18000B61B
0x18000b608  mov     r8, [r15]; __int64
0x18000b60b  lea     rdx, ?DUI_SetSiteOnUnknown@@YAXPEAUIUnknown@@_J@Z; void (*)(struct IUnknown *, __int64)
0x18000b612  mov     rcx, [rbp+18h]; struct DirectUI::Element *
0x18000b616  call    ?DUI_WalkIUnknownElements@@YAXPEAVElement@DirectUI@@P6AXPEAUIUnknown@@_J@Z2@Z; DUI_WalkIUnknownElements(DirectUI::Element *,void (*)(IUnknown *,__int64),__int64)
0x18000b61b  test    cs:Microsoft_Windows_HomeGroup_ControlPanelEnableBits, 4
0x18000b622  jz      short loc_18000B640
0x18000b624  lea     rax, [rsp+78h+var_48]
0x18000b629  mov     r9d, 1
0x18000b62f  lea     rdx, Perf_Initialization_Page_Stop
0x18000b636  mov     [rsp+78h+ppv], rax
0x18000b63b  call    McGenEventWrite_EventWriteTransfer
0x18000b640  mov     eax, edi
0x18000b642  mov     rcx, [rsp+78h+var_38]
0x18000b647  xor     rcx, rsp; StackCookie
0x18000b64a  call    __security_check_cookie
0x18000b64f  mov     rbx, [rsp+78h+arg_10]
0x18000b657  add     rsp, 50h
0x18000b65b  pop     r15
0x18000b65d  pop     r14
0x18000b65f  pop     rdi
0x18000b660  pop     rsi
0x18000b661  pop     rbp
0x18000b662  retn
```
