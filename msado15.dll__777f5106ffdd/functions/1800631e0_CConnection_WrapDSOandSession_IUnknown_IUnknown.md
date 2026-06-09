# CConnection::WrapDSOandSession(IUnknown *,IUnknown *)

- ea: `0x1800631e0`
- end: `0x1800633e2`
- name: `?WrapDSOandSession@CConnection@@UEAAJPEAUIUnknown@@0@Z`
- size: `514`
- prototype: `__int64 __fastcall(CConnection *__hidden this, struct IUnknown *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x18002ec00`
- `0x180046774`
- `0x1800631e0`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180063387`
- `ole32!CoTaskMemFree` at `0x180063397`
- `ole32!CoTaskMemFree` at `0x180063387`
- `ole32!CoTaskMemFree` at `0x180063397`
- `OLEAUT32!__imp_VariantClear` at `0x180063374`
- `OLEAUT32!__imp_VariantClear` at `0x180063374`

## pseudocode

```c
__int64 __fastcall CConnection::WrapDSOandSession(CConnection *this, struct IUnknown *a2, struct IUnknown *a3)
{
  bool v3; // zf
  struct IUnknown *v4; // r9
  int (__fastcall ***v7)(_QWORD, GUID *, __int64 *, struct IUnknown *); // rcx
  int v8; // eax
  int v9; // edi
  VARIANTARG **v10; // rcx
  LPVOID pv; // [rsp+30h] [rbp-48h] BYREF
  int v12; // [rsp+38h] [rbp-40h] BYREF
  int v13; // [rsp+3Ch] [rbp-3Ch] BYREF
  __int64 v14; // [rsp+40h] [rbp-38h] BYREF
  int *v15; // [rsp+48h] [rbp-30h] BYREF
  int v16; // [rsp+50h] [rbp-28h]
  GUID v17; // [rsp+54h] [rbp-24h]
  int v18; // [rsp+64h] [rbp-14h]

  v3 = *((_QWORD *)this + 119) == 0;
  v4 = a3;
  v14 = 0;
  if ( !v3 )
    return 2147942405LL;
  *((_QWORD *)this + 119) = a2;
  *((_QWORD *)this + 120) = a3;
  if ( a3 )
  {
    ((void (__fastcall *)(struct IUnknown *, GUID *, char *))a3->lpVtbl->QueryInterface)(
      a3,
      &IID_ISessionProperties,
      (char *)this + 984);
    (***((void (__fastcall ****)(_QWORD, GUID *, char *))this + 120))(
      *((_QWORD *)this + 120),
      &IID_IBindResource,
      (char *)this + 272);
    (***((void (__fastcall ****)(_QWORD, GUID *, char *))this + 120))(
      *((_QWORD *)this + 120),
      &IID_ICreateRow,
      (char *)this + 280);
  }
  v7 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *, struct IUnknown *))*((_QWORD *)this + 119);
  *((_BYTE *)this + 374) = 1;
  *((_BYTE *)this + 372) = 1;
  if ( !v7 || (**v7)(v7, &IID_IDBProperties, &v14, v4) < 0 )
    return CConnection::SetInternalProperties((CConnection *)((char *)this - 16));
  v15 = &v12;
  v17 = DBPROPSET_MSDSDBINIT;
  v18 = 0;
  pv = 0;
  v13 = 0;
  v16 = 1;
  v12 = 2;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64, int **, int *, LPVOID *))(*(_QWORD *)v14 + 24LL))(
         v14,
         1,
         &v15,
         &v13,
         &pv);
  v9 = 0;
  if ( v8 < 0 )
  {
    if ( v8 != -2147217887 )
      goto LABEL_17;
  }
  else
  {
    v10 = (VARIANTARG **)pv;
    if ( *(_DWORD *)(*(_QWORD *)pv + 8LL) )
      goto LABEL_13;
    CMPString::operator=((char *)this + 336, L"MSDATASHAPE");
    if ( (*((_BYTE *)this + 344) & 4) == 0 )
      v9 = -2147024882;
  }
  v10 = (VARIANTARG **)pv;
LABEL_13:
  if ( v10 )
  {
    if ( *v10 )
    {
      VariantClear(*v10 + 2);
      CoTaskMemFree(*(LPVOID *)pv);
      v10 = (VARIANTARG **)pv;
    }
    CoTaskMemFree(v10);
    pv = 0;
  }
LABEL_17:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v9 < 0 )
    return (unsigned int)v9;
  return CConnection::SetInternalProperties((CConnection *)((char *)this - 16));
}

```

## disassembly

```asm
0x1800631e0  push    rbp
0x1800631e2  push    rbx
0x1800631e3  push    rsi
0x1800631e4  push    rdi
0x1800631e5  mov     rbp, rsp
0x1800631e8  sub     rsp, 78h
0x1800631ec  mov     rax, cs:__security_cookie
0x1800631f3  xor     rax, rsp
0x1800631f6  mov     [rbp+var_10], rax
0x1800631fa  cmp     qword ptr [rcx+3B8h], 0
0x180063202  mov     r9, r8
0x180063205  mov     rbx, rcx
0x180063208  mov     [rbp+var_38], 0
0x180063210  jz      short loc_18006321C
0x180063212  mov     eax, 80070005h
0x180063217  jmp     loc_1800633CC
0x18006321c  mov     [rcx+3B8h], rdx
0x180063223  mov     [rcx+3C0h], r9
0x18006322a  test    r9, r9
0x18006322d  jz      short loc_18006328B
0x18006322f  mov     rax, [r8]
0x180063232  lea     rdx, IID_ISessionProperties
0x180063239  lea     r8, [rcx+3D8h]
0x180063240  mov     rcx, r9
0x180063243  mov     rax, [rax]
0x180063246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006324b  mov     rcx, [rbx+3C0h]
0x180063252  lea     r8, [rbx+110h]
0x180063259  lea     rdx, IID_IBindResource
0x180063260  mov     rax, [rcx]
0x180063263  mov     rax, [rax]
0x180063266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006326b  mov     rcx, [rbx+3C0h]
0x180063272  lea     r8, [rbx+118h]
0x180063279  lea     rdx, IID_ICreateRow
0x180063280  mov     rax, [rcx]
0x180063283  mov     rax, [rax]
0x180063286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006328b  mov     rcx, [rbx+3B8h]
0x180063292  mov     edi, 1
0x180063297  mov     [rbx+176h], dil
0x18006329e  mov     [rbx+174h], dil
0x1800632a5  test    rcx, rcx
0x1800632a8  jz      loc_1800633C3
0x1800632ae  mov     rax, [rcx]
0x1800632b1  lea     r8, [rbp+var_38]
0x1800632b5  lea     rdx, IID_IDBProperties
0x1800632bc  mov     rax, [rax]
0x1800632bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800632c4  test    eax, eax
0x1800632c6  js      loc_1800633C3
0x1800632cc  movups  xmm0, xmmword ptr cs:?DBPROPSET_MSDSDBINIT@@3U_GUID@@B.Data1; _GUID const DBPROPSET_MSDSDBINIT ...
0x1800632d3  mov     rcx, [rbp+var_38]
0x1800632d7  lea     rax, [rbp+var_40]
0x1800632db  mov     [rbp+var_30], rax
0x1800632df  lea     r8, [rbp+pv]
0x1800632e3  movdqu  [rbp+var_24], xmm0
0x1800632e8  mov     [rbp+var_14], 0
0x1800632ef  lea     r9, [rbp+var_3C]
0x1800632f3  mov     [rbp+pv], 0
0x1800632fb  mov     edx, edi
0x1800632fd  mov     [rbp+var_3C], 0
0x180063304  mov     [rbp+var_28], edi
0x180063307  mov     [rbp+var_40], 2
0x18006330e  mov     rax, [rcx]
0x180063311  mov     [rsp+78h+var_58], r8
0x180063316  lea     r8, [rbp+var_30]
0x18006331a  mov     rax, [rax+18h]
0x18006331e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063323  xor     edi, edi
0x180063325  test    eax, eax
0x180063327  js      short loc_180063358
0x180063329  mov     rcx, [rbp+pv]
0x18006332d  mov     rax, [rcx]
0x180063330  cmp     [rax+8], edi
0x180063333  jnz     short loc_180063363
0x180063335  lea     rcx, [rbx+150h]
0x18006333c  lea     rdx, aMsdatashape; "MSDATASHAPE"
0x180063343  call    ??4CMPString@@QEAAAEBV0@PEBG@Z; CMPString::operator=(ushort const *)
0x180063348  test    byte ptr [rbx+158h], 4
0x18006334f  jnz     short loc_18006335F
0x180063351  mov     edi, 8007000Eh
0x180063356  jmp     short loc_18006335F
0x180063358  cmp     eax, 80040E21h
0x18006335d  jnz     short loc_1800633AB
0x18006335f  mov     rcx, [rbp+pv]
0x180063363  test    rcx, rcx
0x180063366  jz      short loc_1800633AB
0x180063368  mov     rax, [rcx]
0x18006336b  test    rax, rax
0x18006336e  jz      short loc_180063397
0x180063370  lea     rcx, [rax+30h]; pvarg
0x180063374  call    cs:__imp_VariantClear
0x18006337b  nop     dword ptr [rax+rax+00h]
0x180063380  mov     rcx, [rbp+pv]
0x180063384  mov     rcx, [rcx]; pv
0x180063387  call    cs:__imp_CoTaskMemFree
0x18006338e  nop     dword ptr [rax+rax+00h]
0x180063393  mov     rcx, [rbp+pv]; pv
0x180063397  call    cs:__imp_CoTaskMemFree
0x18006339e  nop     dword ptr [rax+rax+00h]
0x1800633a3  mov     [rbp+pv], 0
0x1800633ab  mov     rcx, [rbp+var_38]
0x1800633af  mov     rdx, [rcx]
0x1800633b2  mov     rax, [rdx+10h]
0x1800633b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800633bb  test    edi, edi
0x1800633bd  jns     short loc_1800633C3
0x1800633bf  mov     eax, edi
0x1800633c1  jmp     short loc_1800633CC
0x1800633c3  lea     rcx, [rbx-10h]; this
0x1800633c7  call    ?SetInternalProperties@CConnection@@QEAAJXZ; CConnection::SetInternalProperties(void)
0x1800633cc  mov     rcx, [rbp+var_10]
0x1800633d0  xor     rcx, rsp; StackCookie
0x1800633d3  call    __security_check_cookie
0x1800633d8  add     rsp, 78h
0x1800633dc  pop     rdi
0x1800633dd  pop     rsi
0x1800633de  pop     rbx
0x1800633df  pop     rbp
0x1800633e0  retn
```
