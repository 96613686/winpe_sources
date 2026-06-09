# CSNOCplCore::CommitNavLinks(void)

- ea: `0x1800091ec`
- end: `0x1800092d7`
- name: `?CommitNavLinks@CSNOCplCore@@AEAAJXZ`
- size: `235`
- prototype: `__int64 __fastcall(CSNOCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019d98`

## callees

- `0x18000400c`
- `0x180007e50`
- `0x1800091ec`
- `0x180013404`
- `0x180023010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000927b`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000927b`
- `PROPSYS!PSPropertyBag_WriteUnknown` at `0x18000929a`
- `PROPSYS!PSPropertyBag_WriteUnknown` at `0x18000929a`

## string_xrefs

- `0x18000928e`: `ControlPanelNavLinks`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSNOCplCore::CommitNavLinks(CSNOCplCore *this)
{
  struct CControlPanelNavLinks *v2; // rdx
  HRESULT v3; // ebx
  void *ppvOut; // [rsp+30h] [rbp+8h] BYREF

  v2 = (struct CControlPanelNavLinks *)*((_QWORD *)this + 45);
  if ( v2
    || ((v2 = (struct CControlPanelNavLinks *)DirectUI::HAllocAndZero((DirectUI *)0x18, 0), (ppvOut = v2) == 0)
      ? (v2 = 0)
      : (struct CControlPanelNavLinks *)(*(_QWORD *)v2 = &CControlPanelNavLinks::`vftable',
                                         *((_QWORD *)v2 + 1) = 0,
                                         *((_DWORD *)v2 + 4) = 1),
        *((_QWORD *)this + 45) = v2,
        v3 = v2 == 0 ? 0x8007000E : 0,
        v2) )
  {
    CSNOCplCore::_AddTaskLinks(this, v2);
    ppvOut = 0;
    v3 = IUnknown_QueryService(
           *((IUnknown **)this + 43),
           (const GUID *const)&SID_PerLayoutPropertyBag,
           &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
           &ppvOut);
    if ( v3 >= 0 )
      v3 = PSPropertyBag_WriteUnknown((IPropertyBag *)ppvOut, L"ControlPanelNavLinks", *((IUnknown **)this + 45));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 45) + 16LL))(*((_QWORD *)this + 45));
    *((_QWORD *)this + 45) = 0;
    ATL::CComPtrBase<IShellFolder2>::~CComPtrBase<IShellFolder2>(&ppvOut);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800091ec  mov     [rsp+arg_8], rbx
0x1800091f1  push    rdi
0x1800091f2  sub     rsp, 20h
0x1800091f6  mov     rdi, rcx
0x1800091f9  mov     rdx, [rcx+168h]; unsigned __int64
0x180009200  test    rdx, rdx
0x180009203  jnz     short loc_180009253
0x180009205  lea     ecx, [rdx+18h]; this
0x180009208  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000920d  mov     rdx, rax
0x180009210  mov     [rsp+28h+ppvOut], rax
0x180009215  test    rax, rax
0x180009218  jz      short loc_180009235
0x18000921a  lea     rax, ??_7CControlPanelNavLinks@@6B@; const CControlPanelNavLinks::`vftable'
0x180009221  mov     [rdx], rax
0x180009224  mov     qword ptr [rdx+8], 0
0x18000922c  mov     dword ptr [rdx+10h], 1
0x180009233  jmp     short loc_180009237
0x180009235  xor     edx, edx; struct CControlPanelNavLinks *
0x180009237  mov     [rdi+168h], rdx
0x18000923e  mov     rax, rdx
0x180009241  neg     rax
0x180009244  sbb     ebx, ebx
0x180009246  not     ebx
0x180009248  and     ebx, 8007000Eh
0x18000924e  test    rdx, rdx
0x180009251  jz      short loc_1800092CA
0x180009253  call    ?_AddTaskLinks@CSNOCplCore@@AEAAJPEAVCControlPanelNavLinks@@@Z; CSNOCplCore::_AddTaskLinks(CControlPanelNavLinks *)
0x180009258  mov     [rsp+28h+ppvOut], 0
0x180009261  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x180009266  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18000926d  lea     rdx, SID_PerLayoutPropertyBag; guidService
0x180009274  mov     rcx, [rdi+158h]; punk
0x18000927b  call    cs:__imp_IUnknown_QueryService
0x180009281  mov     ebx, eax
0x180009283  test    eax, eax
0x180009285  js      short loc_1800092A2
0x180009287  mov     r8, [rdi+168h]; punk
0x18000928e  lea     rdx, propName; "ControlPanelNavLinks"
0x180009295  mov     rcx, [rsp+28h+ppvOut]; propBag
0x18000929a  call    cs:__imp_PSPropertyBag_WriteUnknown
0x1800092a0  mov     ebx, eax
0x1800092a2  mov     rcx, [rdi+168h]
0x1800092a9  mov     rax, [rcx]
0x1800092ac  mov     rax, [rax+10h]
0x1800092b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092b5  mov     qword ptr [rdi+168h], 0
0x1800092c0  lea     rcx, [rsp+28h+ppvOut]
0x1800092c5  call    ??1?$CComPtrBase@UIShellFolder2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IShellFolder2>::~CComPtrBase<IShellFolder2>(void)
0x1800092ca  mov     eax, ebx
0x1800092cc  mov     rbx, [rsp+28h+arg_8]
0x1800092d1  add     rsp, 20h
0x1800092d5  pop     rdi
0x1800092d6  retn
```
