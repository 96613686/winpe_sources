# CToolbar::DeleteButton(int)

- ea: `0x180113470`
- end: `0x18011358e`
- name: `?DeleteButton@CToolbar@@UEAAJH@Z`
- size: `286`
- prototype: `__int64 __fastcall(CToolbar *__hidden this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800304c0`
- `0x1800407cc`
- `0x180113470`
- `0x18013f010`

## import_xrefs

- `mmcbase!?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ` at `0x1801134bd`
- `mmcbase!?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ` at `0x1801134bd`
- `mmcbase!?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1801134b3`
- `mmcbase!?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1801134b3`
- `mmcbase!?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z` at `0x1801134e1`
- `mmcbase!?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z` at `0x1801134e1`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18011356a`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18011356a`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18011348d`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18011348d`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1801134d0`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1801134d0`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180113503`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18011354c`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180113503`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18011354c`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18011349e`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18011349e`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180113517`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180113560`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180113517`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180113560`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18011350d`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180113556`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180113576`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18011350d`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180113556`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180113576`

## string_xrefs

- `0x180113493`: `IToolbar::DeleteButton`

## pseudocode

```c
__int64 __fastcall CToolbar::DeleteButton(CToolbar *this, int a2)
{
  const unsigned __int16 *SnapinName; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  unsigned int v7; // ebx
  _BYTE v9[24]; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v10[24]; // [rsp+48h] [rbp-18h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v9, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v9, L"IToolbar::DeleteButton");
  SnapinName = CToolbar::GetSnapinName(this);
  mmcerror::SC::SetSnapinName((mmcerror::SC *)v9, SnapinName);
  mmcerror::SC::CheckCallingThreadID((mmcerror::SC *)v9);
  if ( a2 >= 0 )
  {
    v5 = ScCheckPointers(v10, *((_QWORD *)this + 10), 2147549183LL);
    mmcerror::SC::operator=(v9, v5);
    mmcerror::SC::~SC((mmcerror::SC *)v10);
    if ( !(unsigned __int8)mmcerror::SC::operator bool(v9) )
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, unsigned __int64, _QWORD))(**((_QWORD **)this + 10) + 24LL))(
             *((_QWORD *)this + 10),
             v10,
             ((unsigned __int64)this + 8) & -(__int64)(this != 0),
             (unsigned int)a2);
      mmcerror::SC::operator=(v9, v6);
      mmcerror::SC::~SC((mmcerror::SC *)v10);
      mmcerror::SC::operator bool(v9);
    }
  }
  else
  {
    mmcerror::SC::operator=(v9, 2147942487LL);
    TraceSnapinError(L"Invalid index", (const struct mmcerror::SC *)v9);
  }
  v7 = mmcerror::SC::ToHr((mmcerror::SC *)v9);
  mmcerror::SC::~SC((mmcerror::SC *)v9);
  return v7;
}

```

## disassembly

```asm
0x180113470  mov     [rsp-8+arg_0], rbx
0x180113475  mov     [rsp-8+arg_8], rdi
0x18011347a  push    rbp
0x18011347b  mov     rbp, rsp
0x18011347e  sub     rsp, 60h
0x180113482  mov     edi, edx
0x180113484  mov     rbx, rcx
0x180113487  xor     edx, edx
0x180113489  lea     rcx, [rbp+var_30]
0x18011348d  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x180113493  lea     rdx, aItoolbarDelete; "IToolbar::DeleteButton"
0x18011349a  lea     rcx, [rbp+var_30]
0x18011349e  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x1801134a4  mov     rcx, rbx; this
0x1801134a7  call    ?GetSnapinName@CToolbar@@QEAAPEBGXZ; CToolbar::GetSnapinName(void)
0x1801134ac  mov     rdx, rax
0x1801134af  lea     rcx, [rbp+var_30]
0x1801134b3  call    cs:__imp_?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetSnapinName(ushort const *)
0x1801134b9  lea     rcx, [rbp+var_30]
0x1801134bd  call    cs:__imp_?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ; mmcerror::SC::CheckCallingThreadID(void)
0x1801134c3  test    edi, edi
0x1801134c5  jns     short loc_1801134E9
0x1801134c7  mov     edx, 80070057h
0x1801134cc  lea     rcx, [rbp+var_30]
0x1801134d0  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1801134d6  lea     rdx, [rbp+var_30]
0x1801134da  lea     rcx, aInvalidIndex; "Invalid index"
0x1801134e1  call    cs:__imp_?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z; TraceSnapinError(ushort const *,mmcerror::SC const &)
0x1801134e7  jmp     short loc_180113566
0x1801134e9  mov     rdx, [rbx+50h]
0x1801134ed  lea     rcx, [rbp+var_18]
0x1801134f1  mov     r8d, 8000FFFFh
0x1801134f7  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x1801134fc  mov     rdx, rax
0x1801134ff  lea     rcx, [rbp+var_30]
0x180113503  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x180113509  lea     rcx, [rbp+var_18]
0x18011350d  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180113513  lea     rcx, [rbp+var_30]
0x180113517  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18011351d  test    al, al
0x18011351f  jnz     short loc_180113566
0x180113521  mov     rcx, [rbx+50h]
0x180113525  lea     rax, [rbx+8]
0x180113529  neg     rbx
0x18011352c  mov     r9d, edi
0x18011352f  sbb     r8, r8
0x180113532  mov     rdx, [rcx]
0x180113535  and     r8, rax
0x180113538  mov     rax, [rdx+18h]
0x18011353c  lea     rdx, [rbp+var_18]
0x180113540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113545  mov     rdx, rax
0x180113548  lea     rcx, [rbp+var_30]
0x18011354c  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x180113552  lea     rcx, [rbp+var_18]
0x180113556  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18011355c  lea     rcx, [rbp+var_30]
0x180113560  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180113566  lea     rcx, [rbp+var_30]
0x18011356a  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x180113570  lea     rcx, [rbp+var_30]
0x180113574  mov     ebx, eax
0x180113576  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18011357c  mov     rdi, [rsp+60h+arg_8]
0x180113581  mov     eax, ebx
0x180113583  mov     rbx, [rsp+60h+arg_0]
0x180113588  add     rsp, 60h
0x18011358c  pop     rbp
0x18011358d  retn
```
