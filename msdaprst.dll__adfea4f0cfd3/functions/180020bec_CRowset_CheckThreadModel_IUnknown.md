# CRowset::CheckThreadModel(IUnknown *)

- ea: `0x180020bec`
- end: `0x180020cd9`
- name: `?CheckThreadModel@CRowset@@QEAAXPEAUIUnknown@@@Z`
- size: `237`
- prototype: `void __fastcall(CRowset *__hidden this, struct IUnknown *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000f58c`
- `0x180026dc0`

## callees

- `0x180020bec`
- `0x18002d9a4`
- `0x18002f0aa`
- `0x18002f0e0`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180020c78`
- `OLEAUT32!__imp_VariantInit` at `0x180020c78`

## pseudocode

```c
void __fastcall CRowset::CheckThreadModel(CRowset *this, struct IUnknown *a2)
{
  struct IUnknownVtbl *lpVtbl; // rax
  unsigned int v4; // edx
  __int64 v5; // [rsp+30h] [rbp-39h] BYREF
  struct tagDBPROPSET v6; // [rsp+38h] [rbp-31h] BYREF
  _QWORD v7[6]; // [rsp+60h] [rbp-9h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp+27h] BYREF

  lpVtbl = a2->lpVtbl;
  v5 = 0;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
         a2,
         &IID_IAsyncAllowed,
         &v5) < 0 )
  {
    *((_DWORD *)&v6.guidPropertySet + 4) = 0;
    memset_0(v7, 0, 0x48u);
    v6.cProperties = 1;
    v6.rgProperties = (DBPROP *)v7;
    v6.guidPropertySet = DBPROPSET_ROWSET;
    v7[0] = 105;
    VariantInit(&pvarg);
    pvarg.vt = 3;
    pvarg.lVal = 4;
    CUtlProps::utlSetProperties((CRowset *)((char *)this + 400), v4, 1u, &v6, (CRowset *)((char *)this + 112), 1);
  }
}

```

## disassembly

```asm
0x180020bec  mov     [rsp-8+arg_10], rbx
0x180020bf1  push    rbp
0x180020bf2  lea     rbp, [rsp-57h]
0x180020bf7  sub     rsp, 0C0h
0x180020bfe  mov     rax, cs:__security_cookie
0x180020c05  xor     rax, rsp
0x180020c08  mov     [rbp+57h+var_10], rax
0x180020c0c  mov     rax, [rdx]
0x180020c0f  lea     r8, [rbp+57h+var_90]
0x180020c13  mov     r9, rdx
0x180020c16  mov     [rbp+57h+var_90], 0
0x180020c1e  mov     rbx, rcx
0x180020c21  lea     rdx, ?IID_IAsyncAllowed@@3U_GUID@@B; _GUID const IID_IAsyncAllowed
0x180020c28  mov     rcx, r9
0x180020c2b  mov     rax, [rax]
0x180020c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c33  test    eax, eax
0x180020c35  jns     loc_180020CBB
0x180020c3b  xor     edx, edx; Val
0x180020c3d  mov     dword ptr [rbp+57h+var_88+1Ch], 0
0x180020c44  lea     rcx, [rbp+57h+var_60]; void *
0x180020c48  lea     r8d, [rdx+48h]; Size
0x180020c4c  call    memset_0
0x180020c51  movups  xmm0, xmmword ptr cs:DBPROPSET_ROWSET.Data1
0x180020c58  lea     rax, [rbp+57h+var_60]
0x180020c5c  mov     [rbp+57h+var_88.cProperties], 1
0x180020c63  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180020c67  mov     [rbp+57h+var_88.rgProperties], rax
0x180020c6b  movdqu  xmmword ptr [rbp+57h+var_88.guidPropertySet.Data1], xmm0
0x180020c70  mov     [rbp+57h+var_60], 69h ; 'i'
0x180020c78  call    cs:__imp_VariantInit
0x180020c7f  nop     dword ptr [rax+rax+00h]
0x180020c84  mov     eax, 3
0x180020c89  mov     [rsp+0C0h+var_98], 1; int
0x180020c91  mov     word ptr [rbp+57h+pvarg], ax
0x180020c95  lea     rcx, [rbx+190h]; this
0x180020c9c  lea     rax, [rbx+70h]
0x180020ca0  mov     dword ptr [rbp+57h+pvarg+8], 4
0x180020ca7  lea     r9, [rbp+57h+var_88]; struct tagDBPROPSET *
0x180020cab  mov     [rsp+0C0h+var_A0], rax; struct CBidGenericBase *
0x180020cb0  mov     r8d, 1; unsigned int
0x180020cb6  call    ?utlSetProperties@CUtlProps@@QEAAJKKQEBUtagDBPROPSET@@AEBVCBidGenericBase@@H@Z; CUtlProps::utlSetProperties(ulong,ulong,tagDBPROPSET const * const,CBidGenericBase const &,int)
0x180020cbb  mov     rcx, [rbp+57h+var_10]
0x180020cbf  xor     rcx, rsp; StackCookie
0x180020cc2  call    __security_check_cookie
0x180020cc7  mov     rbx, [rsp+0C0h+arg_10]
0x180020ccf  add     rsp, 0C0h
0x180020cd6  pop     rbp
0x180020cd7  retn
```
