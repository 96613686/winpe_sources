# CLogSet::GetViewsFromDataObject(IDataObject *)

- ea: `0x180015e78`
- end: `0x180015f88`
- name: `?GetViewsFromDataObject@CLogSet@@QEAAXPEAUIDataObject@@@Z`
- size: `272`
- prototype: `void __fastcall(CLogSet *__hidden this, struct IDataObject *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007488`

## callees

- `0x180015e78`
- `0x180015f90`
- `0x180024010`

## import_xrefs

- `ole32!CreateStreamOnHGlobal` at `0x180015f03`
- `ole32!CreateStreamOnHGlobal` at `0x180015f03`
- `ole32!ReleaseStgMedium` at `0x180015f70`
- `ole32!ReleaseStgMedium` at `0x180015f70`

## pseudocode

```c
void __fastcall CLogSet::GetViewsFromDataObject(CLogSet *this, struct IDataObject *a2)
{
  int v3; // edi
  struct IDataObjectVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetData)(IDataObject *, FORMATETC *, STGMEDIUM *); // rax
  STGMEDIUM v6; // [rsp+30h] [rbp-40h] BYREF
  __int16 v7; // [rsp+48h] [rbp-28h] BYREF
  int v8; // [rsp+4Ah] [rbp-26h]
  __int16 v9; // [rsp+4Eh] [rbp-22h]
  __int64 v10; // [rsp+50h] [rbp-20h]
  int v11; // [rsp+58h] [rbp-18h]
  int v12; // [rsp+5Ch] [rbp-14h]
  __int64 v13; // [rsp+60h] [rbp-10h]
  int v14; // [rsp+88h] [rbp+18h] BYREF
  LPSTREAM ppstm; // [rsp+90h] [rbp+20h] BYREF

  v7 = CDataObject::s_cfImportViews;
  *(_QWORD *)&v6.tymed = 1;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  ppstm = 0;
  v3 = 0;
  lpVtbl = a2->lpVtbl;
  *(_OWORD *)&v6.hBitmap = 0;
  v11 = 1;
  v12 = -1;
  GetData = lpVtbl->GetData;
  v13 = 1;
  if ( ((int (__fastcall *)(struct IDataObject *, __int16 *, STGMEDIUM *))GetData)(a2, &v7, &v6) >= 0 )
  {
    if ( v6.hBitmap )
    {
      v3 = 1;
      if ( CreateStreamOnHGlobal(v6.hBitmap, 0, &ppstm) >= 0 )
      {
        v14 = 0;
        if ( (*(int (__fastcall **)(LPSTREAM, int *, __int64, _QWORD))(*(_QWORD *)ppstm + 24LL))(ppstm, &v14, 4, 0) >= 0 )
        {
          if ( v14 )
            *((_WORD *)this + 12) |= 0x20u;
          CLogSet::LoadViewsFromStream(this, ppstm, 0x300u, 0);
        }
      }
    }
  }
  if ( ppstm )
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
  if ( v3 )
    ReleaseStgMedium(&v6);
}

```

## disassembly

```asm
0x180015e78  mov     [rsp-8+arg_0], rbx
0x180015e7d  mov     [rsp-8+arg_18], rdi
0x180015e82  push    rbp
0x180015e83  mov     rbp, rsp
0x180015e86  sub     rsp, 70h
0x180015e8a  movzx   eax, word ptr cs:?s_cfImportViews@CDataObject@@2IB; uint const CDataObject::s_cfImportViews
0x180015e91  lea     r8, [rbp+var_40]
0x180015e95  mov     [rbp+var_28], ax
0x180015e99  mov     r9, rdx
0x180015e9c  xor     eax, eax
0x180015e9e  mov     qword ptr [rbp+var_40.tymed], 1
0x180015ea6  mov     [rbp+var_26], eax
0x180015ea9  mov     rbx, rcx
0x180015eac  mov     [rbp+var_22], ax
0x180015eb0  xorps   xmm0, xmm0
0x180015eb3  mov     [rbp+var_20], rax
0x180015eb7  mov     rcx, r9
0x180015eba  mov     [rbp+ppstm], rax
0x180015ebe  xor     edi, edi
0x180015ec0  mov     rax, [rdx]
0x180015ec3  lea     rdx, [rbp+var_28]
0x180015ec7  movdqu  xmmword ptr [rbp+var_40.8], xmm0
0x180015ecc  mov     [rbp+var_18], 1
0x180015ed3  mov     [rbp+var_14], 0FFFFFFFFh
0x180015eda  mov     rax, [rax+18h]
0x180015ede  mov     [rbp+var_10], 1
0x180015ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015eeb  test    eax, eax
0x180015eed  js      short loc_180015F53
0x180015eef  mov     rcx, qword ptr [rbp+var_40.8]; hGlobal
0x180015ef3  test    rcx, rcx
0x180015ef6  jz      short loc_180015F53
0x180015ef8  lea     r8, [rbp+ppstm]; ppstm
0x180015efc  xor     edx, edx; fDeleteOnRelease
0x180015efe  mov     edi, 1
0x180015f03  call    cs:__imp_CreateStreamOnHGlobal
0x180015f09  test    eax, eax
0x180015f0b  js      short loc_180015F53
0x180015f0d  mov     rcx, [rbp+ppstm]
0x180015f11  lea     r8d, [rdi+3]
0x180015f15  mov     [rbp+arg_8], 0
0x180015f1c  lea     rdx, [rbp+arg_8]
0x180015f20  xor     r9d, r9d
0x180015f23  mov     rax, [rcx]
0x180015f26  mov     rax, [rax+18h]
0x180015f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f2f  test    eax, eax
0x180015f31  js      short loc_180015F53
0x180015f33  cmp     [rbp+arg_8], 0
0x180015f37  jz      short loc_180015F3E
0x180015f39  or      word ptr [rbx+18h], 20h
0x180015f3e  mov     rdx, [rbp+ppstm]; struct IStream *
0x180015f42  mov     r8d, 300h; unsigned __int16
0x180015f48  xor     r9d, r9d; struct IStringTable *
0x180015f4b  mov     rcx, rbx; this
0x180015f4e  call    ?LoadViewsFromStream@CLogSet@@QEAAJPEAUIStream@@GPEAUIStringTable@@@Z; CLogSet::LoadViewsFromStream(IStream *,ushort,IStringTable *)
0x180015f53  mov     rcx, [rbp+ppstm]
0x180015f57  test    rcx, rcx
0x180015f5a  jz      short loc_180015F68
0x180015f5c  mov     rax, [rcx]
0x180015f5f  mov     rax, [rax+10h]
0x180015f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f68  test    edi, edi
0x180015f6a  jz      short loc_180015F76
0x180015f6c  lea     rcx, [rbp+var_40]; LPSTGMEDIUM
0x180015f70  call    cs:__imp_ReleaseStgMedium
0x180015f76  lea     r11, [rsp+70h+var_s0]
0x180015f7b  mov     rbx, [r11+10h]
0x180015f7f  mov     rdi, [r11+28h]
0x180015f83  mov     rsp, r11
0x180015f86  pop     rbp
0x180015f87  retn
```
