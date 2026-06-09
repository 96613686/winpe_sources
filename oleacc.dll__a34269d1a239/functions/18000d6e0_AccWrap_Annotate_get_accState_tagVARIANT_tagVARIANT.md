# AccWrap_Annotate::get_accState(tagVARIANT,tagVARIANT *)

- ea: `0x18000d6e0`
- end: `0x18000d84a`
- name: `?get_accState@AccWrap_Annotate@@UEAAJUtagVARIANT@@PEAU2@@Z`
- size: `362`
- prototype: `int(AccWrap_Annotate *__hidden this, struct tagVARIANT *__struct_ptr, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d6e0`
- `0x18000f2b0`
- `0x180049010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000d83e`
- `OLEAUT32!__imp_VariantClear` at `0x18000d83e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d7e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d7e1`

## pseudocode

```c
__int64 __fastcall AccWrap_Annotate::get_accState(
        unsigned int (__fastcall ***this)(AccWrap_Annotate *, GUID *, struct _GUID *),
        struct tagVARIANT *a2,
        struct tagVARIANT *a3)
{
  unsigned int (__fastcall **v6)(AccWrap_Annotate *, GUID *, struct _GUID *); // rax
  __int64 v7; // rcx
  unsigned int (__fastcall **v8)(AccWrap_Annotate *, GUID *, struct _GUID *); // rcx
  __int64 Lo; // rdx
  GUID *v10; // rcx
  int v11; // edi
  unsigned int (__fastcall **v12)(AccWrap_Annotate *, GUID *, struct _GUID *); // rcx
  IRecordInfo *pRecInfo; // xmm1_8
  unsigned int (__fastcall *v14)(AccWrap_Annotate *, GUID *, struct _GUID *); // rax
  unsigned int v15; // ecx
  __int64 result; // rax
  struct _GUID v17; // [rsp+30h] [rbp-48h] BYREF
  IRecordInfo *v18; // [rsp+40h] [rbp-38h]
  unsigned int v19; // [rsp+88h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+20h] BYREF

  if ( a2->vt == 3 )
  {
    if ( !*((_DWORD *)this + 34) )
    {
      v6 = *this;
      *(_QWORD *)&v17.Data1 = 0;
      if ( !(*v6)((AccWrap_Annotate *)this, &IID_IAccIdentity, &v17) )
      {
        v7 = *(_QWORD *)&v17.Data1;
        if ( *(_QWORD *)&v17.Data1 )
        {
          this[18] = *(unsigned int (__fastcall ***)(AccWrap_Annotate *, GUID *, struct _GUID *))&v17.Data1;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        }
      }
    }
    v8 = this[18];
    *((_DWORD *)this + 34) = 1;
    if ( v8 )
    {
      Lo = a2->cyVal.Lo;
      pv = 0;
      v19 = 0;
      if ( !(*((unsigned int (__fastcall **)(unsigned int (__fastcall **)(AccWrap_Annotate *, GUID *, struct _GUID *), __int64, LPVOID *, unsigned int *))*v8
             + 3))(
              v8,
              Lo,
              &pv,
              &v19) )
      {
        if ( pv )
        {
          v17 = PROPID_ACC_STATE;
          v11 = MapReaderMgr::LookupProp(v10, (const unsigned __int8 *)pv, v19, &v17, a3);
          CoTaskMemFree(pv);
          if ( v11 )
          {
            if ( a3->vt == 3 )
              return 0;
            VariantClear(a3);
          }
        }
      }
    }
  }
  v12 = this[8];
  pRecInfo = a2->pRecInfo;
  v14 = *v12;
  v17 = *(struct _GUID *)&a2->vt;
  v18 = pRecInfo;
  v15 = (*((__int64 (__fastcall **)(_QWORD *, struct _GUID *, struct tagVARIANT *))v14 + 14))(v12, &v17, a3);
  result = 0;
  if ( v15 )
    return v15;
  return result;
}

```

## disassembly

```asm
0x18000d6e0  push    rbx
0x18000d6e2  push    rbp
0x18000d6e3  push    rsi
0x18000d6e4  sub     rsp, 60h
0x18000d6e8  cmp     word ptr [rdx], 3
0x18000d6ec  mov     rbp, r8
0x18000d6ef  movaps  [rsp+78h+var_28], xmm6
0x18000d6f4  mov     rsi, rdx
0x18000d6f7  mov     rbx, rcx
0x18000d6fa  jnz     loc_18000D7F3
0x18000d700  cmp     dword ptr [rcx+88h], 0
0x18000d707  movups  xmm6, xmmword ptr cs:PROPID_ACC_STATE.Data1
0x18000d70e  jnz     short loc_18000D751
0x18000d710  mov     rax, [rcx]
0x18000d713  lea     r8, [rsp+78h+var_48]
0x18000d718  lea     rdx, IID_IAccIdentity
0x18000d71f  mov     qword ptr [rsp+78h+var_48.Data1], 0
0x18000d728  mov     rax, [rax]
0x18000d72b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d730  test    eax, eax
0x18000d732  jnz     short loc_18000D751
0x18000d734  mov     rcx, qword ptr [rsp+78h+var_48.Data1]
0x18000d739  test    rcx, rcx
0x18000d73c  jz      short loc_18000D751
0x18000d73e  mov     [rbx+90h], rcx
0x18000d745  mov     rax, [rcx]
0x18000d748  mov     rax, [rax+10h]
0x18000d74c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d751  mov     rcx, [rbx+90h]
0x18000d758  mov     dword ptr [rbx+88h], 1
0x18000d762  test    rcx, rcx
0x18000d765  jz      loc_18000D7F3
0x18000d76b  mov     edx, [rsi+8]
0x18000d76e  lea     r9, [rsp+78h+arg_8]
0x18000d776  mov     [rsp+78h+pv], 0
0x18000d782  lea     r8, [rsp+78h+pv]
0x18000d78a  mov     [rsp+78h+arg_8], 0
0x18000d795  mov     rax, [rcx]
0x18000d798  mov     rax, [rax+18h]
0x18000d79c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7a1  test    eax, eax
0x18000d7a3  jnz     short loc_18000D7F3
0x18000d7a5  mov     rdx, [rsp+78h+pv]; unsigned __int8 *
0x18000d7ad  test    rdx, rdx
0x18000d7b0  jz      short loc_18000D7F3
0x18000d7b2  mov     r8d, [rsp+78h+arg_8]; unsigned int
0x18000d7ba  lea     r9, [rsp+78h+var_48]; struct _GUID
0x18000d7bf  mov     [rsp+78h+arg_0], rdi
0x18000d7c7  movdqa  xmmword ptr [rsp+78h+var_48.Data1], xmm6
0x18000d7cd  mov     [rsp+78h+var_58], rbp; struct tagVARIANT *
0x18000d7d2  call    ?LookupProp@MapReaderMgr@@QEAAHPEBEKU_GUID@@PEAUtagVARIANT@@@Z; MapReaderMgr::LookupProp(uchar const *,ulong,_GUID,tagVARIANT *)
0x18000d7d7  mov     rcx, [rsp+78h+pv]; pv
0x18000d7df  mov     edi, eax
0x18000d7e1  call    cs:__imp_CoTaskMemFree
0x18000d7e7  test    edi, edi
0x18000d7e9  mov     rdi, [rsp+78h+arg_0]
0x18000d7f1  jnz     short loc_18000D834
0x18000d7f3  mov     rcx, [rbx+40h]
0x18000d7f7  lea     rdx, [rsp+78h+var_48]
0x18000d7fc  movups  xmm0, xmmword ptr [rsi]
0x18000d7ff  mov     r8, rbp
0x18000d802  movsd   xmm1, qword ptr [rsi+10h]
0x18000d807  mov     rax, [rcx]
0x18000d80a  movaps  xmmword ptr [rsp+78h+var_48.Data1], xmm0
0x18000d80f  movsd   [rsp+78h+var_38], xmm1
0x18000d815  mov     rax, [rax+70h]
0x18000d819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d81e  mov     ecx, eax
0x18000d820  xor     eax, eax
0x18000d822  test    ecx, ecx
0x18000d824  cmovnz  eax, ecx
0x18000d827  movaps  xmm6, [rsp+78h+var_28]
0x18000d82c  add     rsp, 60h
0x18000d830  pop     rsi
0x18000d831  pop     rbp
0x18000d832  pop     rbx
0x18000d833  retn
0x18000d834  cmp     word ptr [rbp+0], 3
0x18000d839  jz      short loc_18000D846
0x18000d83b  mov     rcx, rbp; pvarg
0x18000d83e  call    cs:__imp_VariantClear
0x18000d844  jmp     short loc_18000D7F3
0x18000d846  xor     eax, eax
0x18000d848  jmp     short loc_18000D827
```
