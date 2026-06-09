# AccWrap_Annotate::get_accName(tagVARIANT,ushort * *)

- ea: `0x18000d540`
- end: `0x18000d6cc`
- name: `?get_accName@AccWrap_Annotate@@UEAAJUtagVARIANT@@PEAPEAG@Z`
- size: `396`
- prototype: `__int64 __fastcall(AccWrap_Annotate *__hidden this, struct tagVARIANT *__struct_ptr, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d540`
- `0x18000f2b0`
- `0x180049010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000d6b8`
- `OLEAUT32!__imp_VariantClear` at `0x18000d6b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d654`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d654`

## pseudocode

```c
__int64 __fastcall AccWrap_Annotate::get_accName(AccWrap_Annotate *this, struct tagVARIANT *a2, unsigned __int16 **a3)
{
  bool v3; // zf
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 Lo; // rdx
  GUID *v10; // rcx
  int v11; // edi
  __int64 *v12; // rcx
  IRecordInfo *pRecInfo; // xmm1_8
  __int64 v14; // rax
  unsigned int v15; // ecx
  __int64 result; // rax
  struct _GUID v17; // [rsp+30h] [rbp-68h] BYREF
  IRecordInfo *v18; // [rsp+40h] [rbp-58h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-48h] BYREF
  unsigned int v20; // [rsp+A8h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp+20h] BYREF

  v3 = a2->vt == 3;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( v3 )
  {
    if ( !*((_DWORD *)this + 34) )
    {
      *(_QWORD *)&v17.Data1 = 0;
      if ( !(**(unsigned int (__fastcall ***)(AccWrap_Annotate *, GUID *, struct _GUID *))this)(
              this,
              &IID_IAccIdentity,
              &v17) )
      {
        v7 = *(_QWORD *)&v17.Data1;
        if ( *(_QWORD *)&v17.Data1 )
        {
          *((_QWORD *)this + 18) = *(_QWORD *)&v17.Data1;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        }
      }
    }
    v8 = *((_QWORD *)this + 18);
    *((_DWORD *)this + 34) = 1;
    if ( v8 )
    {
      Lo = a2->cyVal.Lo;
      pv = 0;
      v20 = 0;
      if ( !(*(unsigned int (__fastcall **)(__int64, __int64, LPVOID *, unsigned int *))(*(_QWORD *)v8 + 24LL))(
              v8,
              Lo,
              &pv,
              &v20) )
      {
        if ( pv )
        {
          v17 = PROPID_ACC_NAME;
          v11 = MapReaderMgr::LookupProp(v10, (const unsigned __int8 *)pv, v20, &v17, &pvarg);
          CoTaskMemFree(pv);
          if ( v11 )
          {
            if ( pvarg.vt == 8 )
            {
              *a3 = pvarg.bstrVal;
              return 0;
            }
            VariantClear(&pvarg);
          }
        }
      }
    }
  }
  v12 = (__int64 *)*((_QWORD *)this + 8);
  pRecInfo = a2->pRecInfo;
  v14 = *v12;
  v17 = *(struct _GUID *)&a2->vt;
  v18 = pRecInfo;
  v15 = (*(__int64 (__fastcall **)(__int64 *, struct _GUID *, unsigned __int16 **))(v14 + 80))(v12, &v17, a3);
  result = 0;
  if ( v15 )
    return v15;
  return result;
}

```

## disassembly

```asm
0x18000d540  push    rbx
0x18000d542  push    rsi
0x18000d543  push    r14
0x18000d545  sub     rsp, 80h
0x18000d54c  xor     eax, eax
0x18000d54e  movaps  [rsp+98h+var_28], xmm6
0x18000d553  cmp     word ptr [rdx], 3
0x18000d557  xorps   xmm0, xmm0
0x18000d55a  mov     r14, r8
0x18000d55d  mov     qword ptr [rsp+98h+pvarg+10h], rax
0x18000d562  mov     rsi, rdx
0x18000d565  mov     rbx, rcx
0x18000d568  movups  xmmword ptr [rsp+98h+pvarg], xmm0
0x18000d56d  jnz     loc_18000D666
0x18000d573  movups  xmm6, xmmword ptr cs:PROPID_ACC_NAME.Data1
0x18000d57a  cmp     [rcx+88h], eax
0x18000d580  jnz     short loc_18000D5BF
0x18000d582  mov     qword ptr [rsp+98h+var_68.Data1], rax
0x18000d587  lea     r8, [rsp+98h+var_68]
0x18000d58c  mov     rax, [rcx]
0x18000d58f  lea     rdx, IID_IAccIdentity
0x18000d596  mov     rax, [rax]
0x18000d599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d59e  test    eax, eax
0x18000d5a0  jnz     short loc_18000D5BF
0x18000d5a2  mov     rcx, qword ptr [rsp+98h+var_68.Data1]
0x18000d5a7  test    rcx, rcx
0x18000d5aa  jz      short loc_18000D5BF
0x18000d5ac  mov     [rbx+90h], rcx
0x18000d5b3  mov     rax, [rcx]
0x18000d5b6  mov     rax, [rax+10h]
0x18000d5ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5bf  mov     rcx, [rbx+90h]
0x18000d5c6  mov     dword ptr [rbx+88h], 1
0x18000d5d0  test    rcx, rcx
0x18000d5d3  jz      loc_18000D666
0x18000d5d9  mov     edx, [rsi+8]
0x18000d5dc  lea     r9, [rsp+98h+arg_8]
0x18000d5e4  mov     [rsp+98h+pv], 0
0x18000d5f0  lea     r8, [rsp+98h+pv]
0x18000d5f8  mov     [rsp+98h+arg_8], 0
0x18000d603  mov     rax, [rcx]
0x18000d606  mov     rax, [rax+18h]
0x18000d60a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d60f  test    eax, eax
0x18000d611  jnz     short loc_18000D666
0x18000d613  mov     rdx, [rsp+98h+pv]; unsigned __int8 *
0x18000d61b  test    rdx, rdx
0x18000d61e  jz      short loc_18000D666
0x18000d620  mov     r8d, [rsp+98h+arg_8]; unsigned int
0x18000d628  lea     rax, [rsp+98h+pvarg]
0x18000d62d  lea     r9, [rsp+98h+var_68]; struct _GUID
0x18000d632  mov     [rsp+98h+var_78], rax; struct tagVARIANT *
0x18000d637  mov     [rsp+98h+arg_0], rdi
0x18000d63f  movdqa  xmmword ptr [rsp+98h+var_68.Data1], xmm6
0x18000d645  call    ?LookupProp@MapReaderMgr@@QEAAHPEBEKU_GUID@@PEAUtagVARIANT@@@Z; MapReaderMgr::LookupProp(uchar const *,ulong,_GUID,tagVARIANT *)
0x18000d64a  mov     rcx, [rsp+98h+pv]; pv
0x18000d652  mov     edi, eax
0x18000d654  call    cs:__imp_CoTaskMemFree
0x18000d65a  test    edi, edi
0x18000d65c  mov     rdi, [rsp+98h+arg_0]
0x18000d664  jnz     short loc_18000D6AB
0x18000d666  mov     rcx, [rbx+40h]
0x18000d66a  lea     rdx, [rsp+98h+var_68]
0x18000d66f  movups  xmm0, xmmword ptr [rsi]
0x18000d672  mov     r8, r14
0x18000d675  movsd   xmm1, qword ptr [rsi+10h]
0x18000d67a  mov     rax, [rcx]
0x18000d67d  movaps  xmmword ptr [rsp+98h+var_68.Data1], xmm0
0x18000d682  movsd   [rsp+98h+var_58], xmm1
0x18000d688  mov     rax, [rax+50h]
0x18000d68c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d691  mov     ecx, eax
0x18000d693  xor     eax, eax
0x18000d695  test    ecx, ecx
0x18000d697  cmovnz  eax, ecx
0x18000d69a  movaps  xmm6, [rsp+98h+var_28]
0x18000d69f  add     rsp, 80h
0x18000d6a6  pop     r14
0x18000d6a8  pop     rsi
0x18000d6a9  pop     rbx
0x18000d6aa  retn
0x18000d6ab  cmp     word ptr [rsp+98h+pvarg], 8
0x18000d6b1  jz      short loc_18000D6C0
0x18000d6b3  lea     rcx, [rsp+98h+pvarg]; pvarg
0x18000d6b8  call    cs:__imp_VariantClear
0x18000d6be  jmp     short loc_18000D666
0x18000d6c0  mov     rax, qword ptr [rsp+98h+pvarg+8]
0x18000d6c5  mov     [r14], rax
0x18000d6c8  xor     eax, eax
0x18000d6ca  jmp     short loc_18000D69A
```
