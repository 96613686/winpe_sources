# CNodeInitObject::DeleteItem(__int64,long)

- ea: `0x18005c910`
- end: `0x18005ca66`
- name: `?DeleteItem@CNodeInitObject@@MEAAJ_JJ@Z`
- size: `342`
- prototype: `int(CNodeInitObject *__hidden this, __int64, int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18002a9c8`
- `0x1800304c0`
- `0x18005c910`
- `0x1800f6718`
- `0x18013f010`

## import_xrefs

- `mmcbase!?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ` at `0x18005c961`
- `mmcbase!?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ` at `0x18005c961`
- `mmcbase!?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18005c957`
- `mmcbase!?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18005c957`
- `mmcbase!?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z` at `0x18005c9c9`
- `mmcbase!?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z` at `0x18005c9c9`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18005ca49`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18005ca49`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18005c92b`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18005c92b`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18005c994`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18005c9b8`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18005c994`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18005c9b8`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18005c9f1`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18005ca35`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18005c9f1`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18005ca35`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18005c93c`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18005c93c`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005ca05`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005ca05`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005c9fb`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005ca3f`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005ca55`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005c9fb`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005ca3f`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005ca55`

## string_xrefs

- `0x18005c931`: `IConsoleNameSpace2::DeleteItem`

## pseudocode

```c
__int64 __fastcall CNodeInitObject::DeleteItem(CNodeInitObject *this, __int64 a2, int a3)
{
  const unsigned __int16 *v6; // rdx
  struct CMTNode *v7; // rbx
  CScopeTree *v8; // rdi
  __int64 v9; // rax
  __int64 v10; // rax
  unsigned int v11; // ebx
  _BYTE v13[24]; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v14[32]; // [rsp+48h] [rbp-20h] BYREF
  int v15; // [rsp+90h] [rbp+28h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v13, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v13, L"IConsoleNameSpace2::DeleteItem");
  v6 = (const unsigned __int16 *)((char *)this + 184);
  if ( *((_QWORD *)this + 26) >= 8u )
    v6 = *(const unsigned __int16 **)v6;
  mmcerror::SC::SetSnapinName((mmcerror::SC *)v13, v6);
  mmcerror::SC::CheckCallingThreadID((mmcerror::SC *)v13);
  v15 = 0;
  (*(void (__fastcall **)(char *, int *))(*((_QWORD *)this - 4) + 184LL))((char *)this - 32, &v15);
  if ( v15 == -1 )
  {
    mmcerror::SC::operator=(v13, 2147549183LL);
  }
  else
  {
    v7 = CMTNode::FromScopeItem(a2);
    if ( v7 )
    {
      v8 = CScopeTree::m_pScopeTree;
      v9 = ScCheckPointers(v14, CScopeTree::m_pScopeTree, 2147549183LL);
      mmcerror::SC::operator=(v13, v9);
      mmcerror::SC::~SC((mmcerror::SC *)v14);
      if ( !(unsigned __int8)mmcerror::SC::operator bool(v13) )
      {
        v10 = CScopeTree::ScDelete(v8, v14, v7, a3 != 0, v15);
        mmcerror::SC::operator=(v13, v10);
        mmcerror::SC::~SC((mmcerror::SC *)v14);
      }
    }
    else
    {
      mmcerror::SC::operator=(v13, 2147500035LL);
      TraceSnapinError(L"HSCOPEITEM is not valid", (const struct mmcerror::SC *)v13);
    }
  }
  v11 = mmcerror::SC::ToHr((mmcerror::SC *)v13);
  mmcerror::SC::~SC((mmcerror::SC *)v13);
  return v11;
}

```

## disassembly

```asm
0x18005c910  push    rbp
0x18005c912  push    rbx
0x18005c913  push    rsi
0x18005c914  push    rdi
0x18005c915  mov     rbp, rsp
0x18005c918  sub     rsp, 68h
0x18005c91c  mov     rdi, rdx
0x18005c91f  mov     rbx, rcx
0x18005c922  xor     edx, edx
0x18005c924  lea     rcx, [rbp+var_38]
0x18005c928  mov     esi, r8d
0x18005c92b  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x18005c931  lea     rdx, aIconsolenamesp_4; "IConsoleNameSpace2::DeleteItem"
0x18005c938  lea     rcx, [rbp+var_38]
0x18005c93c  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x18005c942  lea     rdx, [rbx+0B8h]
0x18005c949  cmp     qword ptr [rdx+18h], 8
0x18005c94e  jb      short loc_18005C953
0x18005c950  mov     rdx, [rdx]
0x18005c953  lea     rcx, [rbp+var_38]
0x18005c957  call    cs:__imp_?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetSnapinName(ushort const *)
0x18005c95d  lea     rcx, [rbp+var_38]
0x18005c961  call    cs:__imp_?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ; mmcerror::SC::CheckCallingThreadID(void)
0x18005c967  lea     rcx, [rbx-20h]
0x18005c96b  mov     [rbp+arg_0], 0
0x18005c972  mov     rax, [rcx]
0x18005c975  lea     rdx, [rbp+arg_0]
0x18005c979  mov     rax, [rax+0B8h]
0x18005c980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c985  cmp     [rbp+arg_0], 0FFFFFFFFh
0x18005c989  jnz     short loc_18005C99F
0x18005c98b  mov     edx, 8000FFFFh
0x18005c990  lea     rcx, [rbp+var_38]
0x18005c994  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18005c99a  jmp     loc_18005CA45
0x18005c99f  mov     rcx, rdi; __int64
0x18005c9a2  call    ?FromScopeItem@CMTNode@@SAPEAV1@_J@Z; CMTNode::FromScopeItem(__int64)
0x18005c9a7  mov     rbx, rax
0x18005c9aa  test    rax, rax
0x18005c9ad  jnz     short loc_18005C9D1
0x18005c9af  mov     edx, 80004003h
0x18005c9b4  lea     rcx, [rbp+var_38]
0x18005c9b8  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18005c9be  lea     rdx, [rbp+var_38]
0x18005c9c2  lea     rcx, aHscopeitemIsNo; "HSCOPEITEM is not valid"
0x18005c9c9  call    cs:__imp_?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z; TraceSnapinError(ushort const *,mmcerror::SC const &)
0x18005c9cf  jmp     short loc_18005CA45
0x18005c9d1  mov     rdi, cs:?m_pScopeTree@CScopeTree@@0PEAV1@EA; CScopeTree * CScopeTree::m_pScopeTree
0x18005c9d8  lea     rcx, [rbp+var_20]
0x18005c9dc  mov     rdx, rdi
0x18005c9df  mov     r8d, 8000FFFFh
0x18005c9e5  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x18005c9ea  mov     rdx, rax
0x18005c9ed  lea     rcx, [rbp+var_38]
0x18005c9f1  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x18005c9f7  lea     rcx, [rbp+var_20]
0x18005c9fb  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18005ca01  lea     rcx, [rbp+var_38]
0x18005ca05  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18005ca0b  test    al, al
0x18005ca0d  jnz     short loc_18005CA45
0x18005ca0f  mov     eax, [rbp+arg_0]
0x18005ca12  lea     rdx, [rbp+var_20]
0x18005ca16  xor     r9d, r9d
0x18005ca19  mov     [rsp+68h+var_48], eax
0x18005ca1d  test    esi, esi
0x18005ca1f  mov     r8, rbx
0x18005ca22  mov     rcx, rdi
0x18005ca25  setnz   r9b
0x18005ca29  call    ?ScDelete@CScopeTree@@QEAA?AVSC@mmcerror@@PEAVCMTNode@@HJ@Z; CScopeTree::ScDelete(CMTNode *,int,long)
0x18005ca2e  mov     rdx, rax
0x18005ca31  lea     rcx, [rbp+var_38]
0x18005ca35  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x18005ca3b  lea     rcx, [rbp+var_20]
0x18005ca3f  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18005ca45  lea     rcx, [rbp+var_38]
0x18005ca49  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x18005ca4f  lea     rcx, [rbp+var_38]
0x18005ca53  mov     ebx, eax
0x18005ca55  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18005ca5b  mov     eax, ebx
0x18005ca5d  add     rsp, 68h
0x18005ca61  pop     rdi
0x18005ca62  pop     rsi
0x18005ca63  pop     rbx
0x18005ca64  pop     rbp
0x18005ca65  retn
```
