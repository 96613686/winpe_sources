# CRowset::InternalQueryInterface(CRowset *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180021128`
- end: `0x18002128b`
- name: `?InternalQueryInterface@CRowset@@QEAAJPEAV1@PEBU_ATL_INTMAP_ENTRY@ATL@@AEBU_GUID@@PEAPEAX@Z`
- size: `355`
- prototype: `int(CRowset *__hidden this, struct CRowset *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x18000c4f0`

## callees

- `0x18001910c`
- `0x180021128`
- `0x18002bd7c`
- `0x18002dc20`
- `0x18002f0e0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002124e`
- `ole32!CoTaskMemFree` at `0x180021260`
- `ole32!CoTaskMemFree` at `0x18002124e`
- `ole32!CoTaskMemFree` at `0x180021260`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRowset::InternalQueryInterface(
        CRowset *this,
        struct CRowset *a2,
        const struct ATL::_ATL_INTMAP_ENTRY *a3,
        const struct _GUID *a4,
        void **a5)
{
  unsigned int Interface; // ebx
  unsigned int v9; // edx
  __int64 v10; // r8
  int v11; // eax
  int v13; // [rsp+30h] [rbp-78h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-70h] BYREF
  unsigned int v15[2]; // [rsp+40h] [rbp-68h] BYREF
  unsigned int v16; // [rsp+48h] [rbp-60h] BYREF
  struct tagDBPROPIDSET v17; // [rsp+50h] [rbp-58h] BYREF

  Interface = -2147467262;
  memset(&v17, 0, sizeof(v17));
  v13 = 0;
  pv = 0;
  v15[0] = 0;
  if ( (unsigned int)IsSame(a4, &IID_IRowsetUpdate) )
  {
    v11 = 134;
  }
  else
  {
    if ( !(unsigned int)IsSame(a4, &IID_IRowsetChange) )
    {
      Interface = ATL::AtlInternalQueryInterface(a2, a3, a4, a5);
      goto LABEL_8;
    }
    v11 = 127;
  }
  try
  {
    v13 = v11;
    v17.cPropertyIDs = 1;
    v17.guidPropertySet = DBPROPSET_ROWSET;
    v17.rgPropertyIDs = (DBPROPID *)&v13;
    CUtlProps::GetProperties(
      (CUtlProps *)(v10 + 400),
      v9,
      &v17,
      v15,
      (struct tagDBPROPSET **)&pv,
      (const struct CBidGenericBase *)(v10 + 112));
    if ( *(_WORD *)(*(_QWORD *)pv + 56LL) == 0xFFFF )
      Interface = ATL::AtlInternalQueryInterface(a2, a3, a4, a5);
  }
  catch ( long v16 )
  {
    v15[1] = v16;
    Interface = v16;
  }
LABEL_8:
  if ( pv )
    CoTaskMemFree(*(LPVOID *)pv);
  CoTaskMemFree(pv);
  return Interface;
}

```

## disassembly

```asm
0x180021128  push    rbx
0x18002112a  push    rsi
0x18002112b  push    rdi
0x18002112c  push    r14
0x18002112e  push    r15
0x180021130  sub     rsp, 80h
0x180021137  mov     rax, cs:__security_cookie
0x18002113e  xor     rax, rsp
0x180021141  mov     [rsp+0A8h+var_38], rax
0x180021146  mov     rdi, r9
0x180021149  mov     r14, r8
0x18002114c  mov     rsi, rdx
0x18002114f  mov     r8, rcx
0x180021152  mov     r15, [rsp+0A8h+arg_20]
0x18002115a  mov     ebx, 80004002h
0x18002115f  xorps   xmm0, xmm0
0x180021162  movups  xmmword ptr [rsp+0A8h+var_58.rgPropertyIDs], xmm0
0x180021167  movups  xmmword ptr [rsp+0A8h+var_58.guidPropertySet.Data2], xmm0
0x18002116c  mov     [rsp+0A8h+var_78], 0
0x180021174  mov     [rsp+0A8h+pv], 0
0x18002117d  mov     [rsp+0A8h+var_68], 0
0x180021185  lea     rdx, IID_IRowsetUpdate; struct _GUID *
0x18002118c  mov     rcx, r9; struct _GUID *
0x18002118f  call    ?IsSame@@YAHAEBU_GUID@@0@Z; IsSame(_GUID const &,_GUID const &)
0x180021194  test    eax, eax
0x180021196  jz      short loc_18002119F
0x180021198  mov     eax, 86h
0x18002119d  jmp     short loc_1800211B7
0x18002119f  lea     rdx, IID_IRowsetChange; struct _GUID *
0x1800211a6  mov     rcx, rdi; struct _GUID *
0x1800211a9  call    ?IsSame@@YAHAEBU_GUID@@0@Z; IsSame(_GUID const &,_GUID const &)
0x1800211ae  test    eax, eax
0x1800211b0  jz      short loc_180021228
0x1800211b2  mov     eax, 7Fh
0x1800211b7  mov     [rsp+0A8h+var_78], eax
0x1800211bb  mov     [rsp+0A8h+var_58.cPropertyIDs], 1
0x1800211c3  movups  xmm0, xmmword ptr cs:DBPROPSET_ROWSET.Data1
0x1800211ca  movdqu  xmmword ptr [rsp+0A8h+var_58.guidPropertySet.Data1], xmm0
0x1800211d0  lea     rax, [rsp+0A8h+var_78]
0x1800211d5  mov     [rsp+0A8h+var_58.rgPropertyIDs], rax
0x1800211da  lea     rax, [r8+70h]
0x1800211de  lea     rcx, [r8+190h]; this
0x1800211e5  mov     [rsp+0A8h+var_80], rax; struct CBidGenericBase *
0x1800211ea  lea     rax, [rsp+0A8h+pv]
0x1800211ef  mov     [rsp+0A8h+var_88], rax; struct tagDBPROPSET **
0x1800211f4  lea     r9, [rsp+0A8h+var_68]; unsigned int *
0x1800211f9  lea     r8, [rsp+0A8h+var_58]; struct tagDBPROPIDSET *
0x1800211fe  call    ?GetProperties@CUtlProps@@QEAAXKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@AEBVCBidGenericBase@@@Z; CUtlProps::GetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *,CBidGenericBase const &)
0x180021203  mov     rax, [rsp+0A8h+pv]
0x180021208  mov     r10, [rax]
0x18002120b  cmp     word ptr [r10+38h], 0FFFFh
0x180021211  jnz     short loc_18002123B
0x180021213  mov     r9, r15; void **
0x180021216  mov     r8, rdi; struct _GUID *
0x180021219  mov     rdx, r14; struct ATL::_ATL_INTMAP_ENTRY *
0x18002121c  mov     rcx, rsi; void *
0x18002121f  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180021224  mov     ebx, eax
0x180021226  jmp     short loc_18002123B
0x180021228  mov     r9, r15; void **
0x18002122b  mov     r8, rdi; struct _GUID *
0x18002122e  mov     rdx, r14; struct ATL::_ATL_INTMAP_ENTRY *
0x180021231  mov     rcx, rsi; void *
0x180021234  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180021239  mov     ebx, eax
0x18002123b  jmp     short loc_180021241
0x18002123d  mov     ebx, [rsp+0A8h+var_64]
0x180021241  mov     rcx, [rsp+0A8h+pv]
0x180021246  test    rcx, rcx
0x180021249  jz      short loc_18002125B
0x18002124b  mov     rcx, [rcx]; pv
0x18002124e  call    cs:__imp_CoTaskMemFree
0x180021255  nop     dword ptr [rax+rax+00h]
0x18002125a  nop
0x18002125b  mov     rcx, [rsp+0A8h+pv]; pv
0x180021260  call    cs:__imp_CoTaskMemFree
0x180021267  nop     dword ptr [rax+rax+00h]
0x18002126c  mov     eax, ebx
0x18002126e  mov     rcx, [rsp+0A8h+var_38]
0x180021273  xor     rcx, rsp; StackCookie
0x180021276  call    __security_check_cookie
0x18002127b  add     rsp, 80h
0x180021282  pop     r15
0x180021284  pop     r14
0x180021286  pop     rdi
0x180021287  pop     rsi
0x180021288  pop     rbx
0x180021289  retn
```
