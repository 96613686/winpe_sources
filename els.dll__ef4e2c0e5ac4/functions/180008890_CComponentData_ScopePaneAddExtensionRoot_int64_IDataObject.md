# CComponentData::_ScopePaneAddExtensionRoot(__int64,IDataObject *)

- ea: `0x180008890`
- end: `0x180008952`
- name: `?_ScopePaneAddExtensionRoot@CComponentData@@AEAAJ_JPEAUIDataObject@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(CComponentData *__hidden this, __int64, struct IDataObject *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007990`

## callees

- `0x180006fc0`
- `0x180007488`
- `0x180008890`
- `0x18001f57c`
- `0x180024010`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x1800088de`
- `KERNEL32!GlobalFree` at `0x1800088de`

## pseudocode

```c
int __fastcall CComponentData::_ScopePaneAddExtensionRoot(CComponentData *this, __int64 a2, struct IDataObject *a3)
{
  __int64 v6; // rcx
  int result; // eax
  __int64 v8; // r8
  _QWORD v9[2]; // [rsp+20h] [rbp-48h] BYREF
  int v10; // [rsp+30h] [rbp-38h]
  int v11; // [rsp+34h] [rbp-34h]
  __int64 v12; // [rsp+38h] [rbp-30h]
  __int64 v13; // [rsp+40h] [rbp-28h]
  __int64 v14; // [rsp+48h] [rbp-20h]
  __int64 v15; // [rsp+50h] [rbp-18h]
  HGLOBAL hMem; // [rsp+90h] [rbp+28h] BYREF

  *((_WORD *)this + 28) |= 0x10u;
  hMem = 0;
  if ( ExtractFromDataObject(a3, CDataObject::s_cfMachineName, 0x20Cu, &hMem) >= 0 )
  {
    CComponentData::SetServerFocus(this, (STRSAFE_PCNZWCH)hMem);
    GlobalFree(hMem);
  }
  v9[0] = 38;
  v9[1] = -1;
  v13 = -1;
  v12 = 0;
  v15 = 0;
  v6 = *((_QWORD *)this + 145);
  v10 = 3;
  v11 = 3;
  v14 = a2;
  result = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v6 + 24LL))(v6, v9);
  if ( result >= 0 )
  {
    v8 = v15;
    *((_QWORD *)this + 142) = v15;
    return CComponentData::_CreateLogSet(this, a3, v8, a2);
  }
  return result;
}

```

## disassembly

```asm
0x180008890  push    rbp
0x180008892  push    rbx
0x180008893  push    rsi
0x180008894  push    rdi
0x180008895  mov     rbp, rsp
0x180008898  sub     rsp, 68h
0x18000889c  or      word ptr [rcx+38h], 10h
0x1800088a1  lea     r9, [rbp+hMem]; void **
0x1800088a5  mov     rsi, r8
0x1800088a8  mov     [rbp+hMem], 0
0x1800088b0  mov     rdi, rdx
0x1800088b3  mov     rbx, rcx
0x1800088b6  mov     edx, cs:?s_cfMachineName@CDataObject@@2IB; unsigned int
0x1800088bc  mov     rcx, rsi; struct IDataObject *
0x1800088bf  mov     r8d, 20Ch; unsigned int
0x1800088c5  call    ?ExtractFromDataObject@@YAJPEAUIDataObject@@IKPEAPEAX@Z; ExtractFromDataObject(IDataObject *,uint,ulong,void * *)
0x1800088ca  test    eax, eax
0x1800088cc  js      short loc_1800088E4
0x1800088ce  mov     rdx, [rbp+hMem]; pszSrc
0x1800088d2  mov     rcx, rbx; this
0x1800088d5  call    ?SetServerFocus@CComponentData@@QEAAXPEBG@Z; CComponentData::SetServerFocus(ushort const *)
0x1800088da  mov     rcx, [rbp+hMem]; hMem
0x1800088de  call    cs:__imp_GlobalFree
0x1800088e4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800088e8  mov     [rbp+var_48], 26h ; '&'
0x1800088f0  mov     [rbp+var_40], rcx
0x1800088f4  lea     rdx, [rbp+var_48]
0x1800088f8  mov     [rbp+var_28], rcx
0x1800088fc  mov     [rbp+var_30], 0
0x180008904  lea     eax, [rcx+4]
0x180008907  mov     [rbp+var_18], 0
0x18000890f  mov     rcx, [rbx+488h]
0x180008916  mov     [rbp+var_38], eax
0x180008919  mov     [rbp+var_34], eax
0x18000891c  mov     [rbp+var_20], rdi
0x180008920  mov     rax, [rcx]
0x180008923  mov     rax, [rax+18h]
0x180008927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000892c  test    eax, eax
0x18000892e  js      short loc_180008949
0x180008930  mov     r8, [rbp+var_18]; __int64
0x180008934  mov     r9, rdi; __int64
0x180008937  mov     rdx, rsi; struct IDataObject *
0x18000893a  mov     [rbx+470h], r8
0x180008941  mov     rcx, rbx; this
0x180008944  call    ?_CreateLogSet@CComponentData@@AEAAJPEAUIDataObject@@_J1@Z; CComponentData::_CreateLogSet(IDataObject *,__int64,__int64)
0x180008949  add     rsp, 68h
0x18000894d  pop     rdi
0x18000894e  pop     rsi
0x18000894f  pop     rbx
0x180008950  pop     rbp
0x180008951  retn
```
