# CNodeInitObject::IsScopeNodeVisuallyExpanded(__int64,int *)

- ea: `0x180066a40`
- end: `0x180066cb2`
- name: `?IsScopeNodeVisuallyExpanded@CNodeInitObject@@UEAAJ_JPEAH@Z`
- size: `626`
- prototype: `__int64 __fastcall(CNodeInitObject *__hidden this, __int64, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18002a9c8`
- `0x18002e0c0`
- `0x1800304c0`
- `0x18003f978`
- `0x180057074`
- `0x180066a40`
- `0x18007cf28`
- `0x18013f010`

## import_xrefs

- `mmcbase!?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ` at `0x180066a93`
- `mmcbase!?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ` at `0x180066a93`
- `mmcbase!?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180066a89`
- `mmcbase!?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180066a89`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x180066ac6`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x180066b4c`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x180066bd2`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x180066c58`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x180066c93`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x180066ac6`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x180066b4c`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x180066bd2`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x180066c58`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x180066c93`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180066a5d`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180066a5d`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180066ab2`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180066b38`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180066bbe`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180066c44`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180066ab2`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180066b38`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180066bbe`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180066c44`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180066a6e`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180066a6e`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180066abc`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180066b42`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180066bc8`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180066c4e`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180066c9f`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180066abc`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180066b42`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180066bc8`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180066c4e`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180066c9f`

## string_xrefs

- `0x180066a63`: `IConsole4::IsScopeNodeVisuallyExpanded`

## pseudocode

```c
__int64 __fastcall CNodeInitObject::IsScopeNodeVisuallyExpanded(CNodeInitObject *this, __int64 a2, int *a3)
{
  const unsigned __int16 *v6; // rdx
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rdx
  struct CMTNode *v11; // r14
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rdx
  struct CConsoleView *ConsoleView; // rsi
  __int64 v17; // rax
  struct HNODE__ *v18; // rax
  struct CNode *v19; // rsi
  __int64 v20; // rax
  unsigned int v21; // ebx
  _BYTE v23[24]; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v24[24]; // [rsp+48h] [rbp-18h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v23, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v23, L"IConsole4::IsScopeNodeVisuallyExpanded");
  v6 = (const unsigned __int16 *)((char *)this + 216);
  if ( *((_QWORD *)this + 30) >= 8u )
    v6 = *(const unsigned __int16 **)v6;
  mmcerror::SC::SetSnapinName((mmcerror::SC *)v23, v6);
  mmcerror::SC::CheckCallingThreadID((mmcerror::SC *)v23);
  v7 = ScCheckPointers(v24, a3, 2147942487LL);
  mmcerror::SC::operator=(v23, v7);
  mmcerror::SC::~SC((mmcerror::SC *)v24);
  v8 = mmcerror::SC::ToHr((mmcerror::SC *)v23);
  if ( v8 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v10 = 22;
LABEL_7:
      WPP_SF_d(*(_QWORD *)(v9 + 16), v10, WPP_2a17de6afd653f090834b24b9a46db2a_Traceguids, (unsigned int)v8);
      goto LABEL_22;
    }
    goto LABEL_22;
  }
  *a3 = 0;
  v11 = CMTNode::FromScopeItem(a2);
  v12 = ScCheckPointers(v24, v11, 2147942487LL);
  mmcerror::SC::operator=(v23, v12);
  mmcerror::SC::~SC((mmcerror::SC *)v24);
  v13 = mmcerror::SC::ToHr((mmcerror::SC *)v23);
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_22;
    v15 = 23;
    goto LABEL_12;
  }
  ConsoleView = CNodeInitObject::GetConsoleView(this, 1);
  v17 = ScCheckPointers(v24, ConsoleView, 2147549183LL);
  mmcerror::SC::operator=(v23, v17);
  mmcerror::SC::~SC((mmcerror::SC *)v24);
  v8 = mmcerror::SC::ToHr((mmcerror::SC *)v23);
  if ( v8 >= 0 )
  {
    v18 = (struct HNODE__ *)(*(__int64 (__fastcall **)(struct CConsoleView *, _QWORD))(*(_QWORD *)ConsoleView + 248LL))(
                              ConsoleView,
                              *((unsigned int *)v11 + 32));
    v19 = CNode::FromHandle(v18);
    v20 = ScCheckPointers(v24, v19, 2147942487LL);
    mmcerror::SC::operator=(v23, v20);
    mmcerror::SC::~SC((mmcerror::SC *)v24);
    v13 = mmcerror::SC::ToHr((mmcerror::SC *)v23);
    if ( v13 >= 0 )
    {
      *a3 = (*((_DWORD *)v19 + 12) >> 1) & 1;
      goto LABEL_22;
    }
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_22;
    v15 = 25;
LABEL_12:
    WPP_SF_qd(*(_QWORD *)(v14 + 16), v15, WPP_2a17de6afd653f090834b24b9a46db2a_Traceguids, a2, v13);
    goto LABEL_22;
  }
  v9 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v10 = 24;
    goto LABEL_7;
  }
LABEL_22:
  v21 = mmcerror::SC::ToHr((mmcerror::SC *)v23);
  mmcerror::SC::~SC((mmcerror::SC *)v23);
  return v21;
}

```

## disassembly

```asm
0x180066a40  push    rbp
0x180066a42  push    rbx
0x180066a43  push    rsi
0x180066a44  push    rdi
0x180066a45  push    r14
0x180066a47  mov     rbp, rsp
0x180066a4a  sub     rsp, 60h
0x180066a4e  mov     rbx, rdx
0x180066a51  mov     rsi, rcx
0x180066a54  xor     edx, edx
0x180066a56  lea     rcx, [rbp+var_30]
0x180066a5a  mov     rdi, r8
0x180066a5d  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x180066a63  lea     rdx, aIconsole4Issco; "IConsole4::IsScopeNodeVisuallyExpanded"
0x180066a6a  lea     rcx, [rbp+var_30]
0x180066a6e  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x180066a74  lea     rdx, [rsi+0D8h]
0x180066a7b  cmp     qword ptr [rdx+18h], 8
0x180066a80  jb      short loc_180066A85
0x180066a82  mov     rdx, [rdx]
0x180066a85  lea     rcx, [rbp+var_30]
0x180066a89  call    cs:__imp_?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetSnapinName(ushort const *)
0x180066a8f  lea     rcx, [rbp+var_30]
0x180066a93  call    cs:__imp_?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ; mmcerror::SC::CheckCallingThreadID(void)
0x180066a99  mov     r8d, 80070057h
0x180066a9f  lea     rcx, [rbp+var_18]
0x180066aa3  mov     rdx, rdi
0x180066aa6  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x180066aab  mov     rdx, rax
0x180066aae  lea     rcx, [rbp+var_30]
0x180066ab2  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x180066ab8  lea     rcx, [rbp+var_18]
0x180066abc  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180066ac2  lea     rcx, [rbp+var_30]
0x180066ac6  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x180066acc  test    eax, eax
0x180066ace  jns     short loc_180066B0E
0x180066ad0  mov     rcx, cs:WPP_GLOBAL_Control
0x180066ad7  lea     rdx, WPP_GLOBAL_Control
0x180066ade  cmp     rcx, rdx
0x180066ae1  jz      loc_180066C8F
0x180066ae7  cmp     byte ptr [rcx+19h], 2
0x180066aeb  jb      loc_180066C8F
0x180066af1  mov     edx, 16h
0x180066af6  mov     rcx, [rcx+10h]
0x180066afa  lea     r8, WPP_2a17de6afd653f090834b24b9a46db2a_Traceguids
0x180066b01  mov     r9d, eax
0x180066b04  call    WPP_SF_d
0x180066b09  jmp     loc_180066C8F
0x180066b0e  mov     rcx, rbx; __int64
0x180066b11  mov     dword ptr [rdi], 0
0x180066b17  call    ?FromScopeItem@CMTNode@@SAPEAV1@_J@Z; CMTNode::FromScopeItem(__int64)
0x180066b1c  mov     r8d, 80070057h
0x180066b22  lea     rcx, [rbp+var_18]
0x180066b26  mov     rdx, rax
0x180066b29  mov     r14, rax
0x180066b2c  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x180066b31  mov     rdx, rax
0x180066b34  lea     rcx, [rbp+var_30]
0x180066b38  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x180066b3e  lea     rcx, [rbp+var_18]
0x180066b42  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180066b48  lea     rcx, [rbp+var_30]
0x180066b4c  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x180066b52  test    eax, eax
0x180066b54  jns     short loc_180066B98
0x180066b56  mov     rcx, cs:WPP_GLOBAL_Control
0x180066b5d  lea     rdx, WPP_GLOBAL_Control
0x180066b64  cmp     rcx, rdx
0x180066b67  jz      loc_180066C8F
0x180066b6d  cmp     byte ptr [rcx+19h], 2
0x180066b71  jb      loc_180066C8F
0x180066b77  mov     edx, 17h
0x180066b7c  mov     rcx, [rcx+10h]
0x180066b80  lea     r8, WPP_2a17de6afd653f090834b24b9a46db2a_Traceguids
0x180066b87  mov     r9, rbx
0x180066b8a  mov     [rsp+60h+var_40], eax
0x180066b8e  call    WPP_SF_qd
0x180066b93  jmp     loc_180066C8F
0x180066b98  mov     dl, 1; bool
0x180066b9a  mov     rcx, rsi; this
0x180066b9d  call    ?GetConsoleView@CNodeInitObject@@QEBAPEAVCConsoleView@@_N@Z; CNodeInitObject::GetConsoleView(bool)
0x180066ba2  mov     r8d, 8000FFFFh
0x180066ba8  lea     rcx, [rbp+var_18]
0x180066bac  mov     rdx, rax
0x180066baf  mov     rsi, rax
0x180066bb2  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x180066bb7  mov     rdx, rax
0x180066bba  lea     rcx, [rbp+var_30]
0x180066bbe  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x180066bc4  lea     rcx, [rbp+var_18]
0x180066bc8  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180066bce  lea     rcx, [rbp+var_30]
0x180066bd2  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x180066bd8  test    eax, eax
0x180066bda  jns     short loc_180066C07
0x180066bdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180066be3  lea     rdx, WPP_GLOBAL_Control
0x180066bea  cmp     rcx, rdx
0x180066bed  jz      loc_180066C8F
0x180066bf3  cmp     byte ptr [rcx+19h], 2
0x180066bf7  jb      loc_180066C8F
0x180066bfd  mov     edx, 18h
0x180066c02  jmp     loc_180066AF6
0x180066c07  mov     rax, [rsi]
0x180066c0a  mov     rcx, rsi
0x180066c0d  mov     edx, [r14+80h]
0x180066c14  mov     rax, [rax+0F8h]
0x180066c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066c20  mov     rcx, rax; struct HNODE__ *
0x180066c23  call    ?FromHandle@CNode@@SAPEAV1@PEAUHNODE__@@@Z; CNode::FromHandle(HNODE__ *)
0x180066c28  mov     r8d, 80070057h
0x180066c2e  lea     rcx, [rbp+var_18]
0x180066c32  mov     rdx, rax
0x180066c35  mov     rsi, rax
0x180066c38  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x180066c3d  mov     rdx, rax
0x180066c40  lea     rcx, [rbp+var_30]
0x180066c44  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x180066c4a  lea     rcx, [rbp+var_18]
0x180066c4e  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180066c54  lea     rcx, [rbp+var_30]
0x180066c58  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x180066c5e  test    eax, eax
0x180066c60  jns     short loc_180066C85
0x180066c62  mov     rcx, cs:WPP_GLOBAL_Control
0x180066c69  lea     rdx, WPP_GLOBAL_Control
0x180066c70  cmp     rcx, rdx
0x180066c73  jz      short loc_180066C8F
0x180066c75  cmp     byte ptr [rcx+19h], 2
0x180066c79  jb      short loc_180066C8F
0x180066c7b  mov     edx, 19h
0x180066c80  jmp     loc_180066B7C
0x180066c85  mov     eax, [rsi+30h]
0x180066c88  shr     eax, 1
0x180066c8a  and     eax, 1
0x180066c8d  mov     [rdi], eax
0x180066c8f  lea     rcx, [rbp+var_30]
0x180066c93  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x180066c99  lea     rcx, [rbp+var_30]
0x180066c9d  mov     ebx, eax
0x180066c9f  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180066ca5  mov     eax, ebx
0x180066ca7  add     rsp, 60h
0x180066cab  pop     r14
0x180066cad  pop     rdi
0x180066cae  pop     rsi
0x180066caf  pop     rbx
0x180066cb0  pop     rbp
0x180066cb1  retn
```
