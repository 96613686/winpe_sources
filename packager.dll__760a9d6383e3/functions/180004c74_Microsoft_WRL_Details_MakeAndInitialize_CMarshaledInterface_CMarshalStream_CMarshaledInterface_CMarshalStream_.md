# Microsoft::WRL::Details::MakeAndInitialize<CMarshaledInterface::CMarshalStream,CMarshaledInterface::CMarshalStream,_GUID const &,IUnknown * &,MARSHAL_KIND &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CMarshaledInterface::CMarshalStream>>,_GUID const &,IUnknown * &,MARSHAL_KIND &)

- ea: `0x180004c74`
- end: `0x180004e2b`
- name: `??$MakeAndInitialize@VCMarshalStream@CMarshaledInterface@@V12@AEBU_GUID@@AEAPEAUIUnknown@@AEAW4MARSHAL_KIND@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCMarshalStream@CMarshaledInterface@@@WRL@Microsoft@@@012@AEBU_GUID@@AEAPEAUIUnknown@@AEAW4MARSHAL_KIND@@@Z`
- size: `439`
- prototype: `__int64 __fastcall(__int64 *, __int64, IUnknown **, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005f5c`

## callees

- `0x180001674`
- `0x180004c74`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d33`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180004d63`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180004d63`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180004ddc`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180004ddc`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CMarshaledInterface::CMarshalStream,CMarshaledInterface::CMarshalStream,_GUID const &,IUnknown * &,enum MARSHAL_KIND &>(
        __int64 *a1,
        __int64 a2,
        IUnknown **a3,
        int *a4)
{
  __int64 v6; // rcx
  _DWORD *v8; // rax
  _DWORD *v9; // rsi
  HRESULT AgileReference; // edi
  struct Microsoft::WRL::Details::ModuleBase *v11; // rcx
  __int64 *v12; // r14
  int v13; // edi
  IUnknown *v14; // rbp
  DWORD CurrentThreadId; // eax
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v22; // [rsp+48h] [rbp+10h] BYREF

  v22 = a2;
  v6 = *a1;
  if ( v6 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  *a1 = 0;
  v8 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( v8 )
  {
    v11 = Microsoft::WRL::Details::ModuleBase::module_;
    v8[3] = 1;
    *(_QWORD *)v8 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable';
    if ( v11 )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v11 + 8LL))(v11);
    v9[6] = 2;
    *(_QWORD *)v9 = &CMarshaledInterface::CMarshalStream::`vftable';
    v12 = (__int64 *)(v9 + 4);
    *((_QWORD *)v9 + 2) = 0;
    *((_QWORD *)v9 + 4) = 0;
    v9[10] = 0;
    v13 = *a4;
    v14 = *a3;
    CurrentThreadId = GetCurrentThreadId();
    v9[6] = v13;
    v9[10] = CurrentThreadId;
    if ( v13 == 2 )
    {
      v16 = 0;
      AgileReference = 0;
      v22 = 0;
      if ( v14 )
      {
        AgileReference = RoGetAgileReference(0, &GUID_b722bccb_4e68_101b_a2bc_00aa00404770, v14, &v22);
        v16 = v22;
      }
      v17 = *((_QWORD *)v9 + 4);
      v18 = 0;
      v22 = 0;
      *((_QWORD *)v9 + 4) = v16;
      if ( v17 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        v18 = v22;
      }
      if ( v18 )
      {
        v22 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
    }
    else
    {
      v19 = *v12;
      if ( *v12 )
      {
        *v12 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      AgileReference = CoMarshalInterThreadInterfaceInStream(
                         &GUID_b722bccb_4e68_101b_a2bc_00aa00404770,
                         v14,
                         (LPSTREAM *)v9 + 2);
    }
    v20 = *(_QWORD *)v9;
    if ( AgileReference >= 0 )
    {
      (*(void (__fastcall **)(_DWORD *))(v20 + 8))(v9);
      *a1 = (__int64)v9;
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
      return 0;
    }
    else
    {
      (*(void (__fastcall **)(_DWORD *))(v20 + 16))(v9);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)AgileReference;
}

```

## disassembly

```asm
0x180004c74  mov     [rsp+arg_0], rbx
0x180004c79  mov     [rsp+arg_10], rbp
0x180004c7e  mov     [rsp+arg_8], rdx
0x180004c83  push    rsi
0x180004c84  push    rdi
0x180004c85  push    r14
0x180004c87  sub     rsp, 20h
0x180004c8b  mov     rbx, rcx
0x180004c8e  mov     rdi, r9
0x180004c91  mov     rcx, [rcx]
0x180004c94  mov     rbp, r8
0x180004c97  test    rcx, rcx
0x180004c9a  jz      short loc_180004CAF
0x180004c9c  mov     qword ptr [rbx], 0
0x180004ca3  mov     rax, [rcx]
0x180004ca6  mov     rax, [rax+10h]
0x180004caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004caf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004cb6  mov     qword ptr [rbx], 0
0x180004cbd  mov     ecx, 30h ; '0'; unsigned __int64
0x180004cc2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004cc7  mov     rsi, rax
0x180004cca  test    rax, rax
0x180004ccd  jnz     short loc_180004CD9
0x180004ccf  mov     edi, 8007000Eh
0x180004cd4  jmp     loc_180004E16
0x180004cd9  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180004ce0  mov     dword ptr [rax+0Ch], 1
0x180004ce7  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable'
0x180004cee  mov     [rsi], rax
0x180004cf1  test    rcx, rcx
0x180004cf4  jz      short loc_180004D02
0x180004cf6  mov     rax, [rcx]
0x180004cf9  mov     rax, [rax+8]
0x180004cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d02  mov     dword ptr [rsi+18h], 2
0x180004d09  lea     rax, ??_7CMarshalStream@CMarshaledInterface@@6B@; const CMarshaledInterface::CMarshalStream::`vftable'
0x180004d10  mov     [rsi], rax
0x180004d13  lea     r14, [rsi+10h]
0x180004d17  mov     qword ptr [r14], 0
0x180004d1e  mov     qword ptr [rsi+20h], 0
0x180004d26  mov     dword ptr [rsi+28h], 0
0x180004d2d  mov     edi, [rdi]
0x180004d2f  mov     rbp, [rbp+0]
0x180004d33  call    cs:__imp_GetCurrentThreadId
0x180004d39  mov     [rsi+18h], edi
0x180004d3c  mov     [rsi+28h], eax
0x180004d3f  cmp     edi, 2
0x180004d42  jnz     short loc_180004DB4
0x180004d44  xor     eax, eax
0x180004d46  xor     edi, edi
0x180004d48  mov     [rsp+38h+arg_8], rax
0x180004d4d  test    rbp, rbp
0x180004d50  jz      short loc_180004D70
0x180004d52  lea     r9, [rsp+38h+arg_8]
0x180004d57  mov     r8, rbp
0x180004d5a  lea     rdx, _GUID_b722bccb_4e68_101b_a2bc_00aa00404770
0x180004d61  xor     ecx, ecx
0x180004d63  call    cs:__imp_RoGetAgileReference
0x180004d69  mov     edi, eax
0x180004d6b  mov     rax, [rsp+38h+arg_8]
0x180004d70  mov     rdx, [rsi+20h]
0x180004d74  xor     ecx, ecx
0x180004d76  mov     [rsp+38h+arg_8], rcx
0x180004d7b  mov     [rsi+20h], rax
0x180004d7f  test    rdx, rdx
0x180004d82  jz      short loc_180004D98
0x180004d84  mov     rax, [rdx]
0x180004d87  mov     rcx, rdx
0x180004d8a  mov     rax, [rax+10h]
0x180004d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d93  mov     rcx, [rsp+38h+arg_8]
0x180004d98  test    rcx, rcx
0x180004d9b  jz      short loc_180004DE4
0x180004d9d  mov     [rsp+38h+arg_8], 0
0x180004da6  mov     rax, [rcx]
0x180004da9  mov     rax, [rax+10h]
0x180004dad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004db2  jmp     short loc_180004DE4
0x180004db4  mov     rcx, [r14]
0x180004db7  test    rcx, rcx
0x180004dba  jz      short loc_180004DCF
0x180004dbc  mov     qword ptr [r14], 0
0x180004dc3  mov     rax, [rcx]
0x180004dc6  mov     rax, [rax+10h]
0x180004dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dcf  mov     r8, r14; ppStm
0x180004dd2  lea     rcx, _GUID_b722bccb_4e68_101b_a2bc_00aa00404770; riid
0x180004dd9  mov     rdx, rbp; pUnk
0x180004ddc  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180004de2  mov     edi, eax
0x180004de4  mov     rax, [rsi]
0x180004de7  mov     rcx, rsi
0x180004dea  test    edi, edi
0x180004dec  jns     short loc_180004DF9
0x180004dee  mov     rax, [rax+10h]
0x180004df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004df7  jmp     short loc_180004E16
0x180004df9  mov     rax, [rax+8]
0x180004dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e02  mov     [rbx], rsi
0x180004e05  mov     rcx, rsi
0x180004e08  mov     rax, [rsi]
0x180004e0b  mov     rax, [rax+10h]
0x180004e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e14  xor     edi, edi
0x180004e16  mov     rbx, [rsp+38h+arg_0]
0x180004e1b  mov     eax, edi
0x180004e1d  mov     rbp, [rsp+38h+arg_10]
0x180004e22  add     rsp, 20h
0x180004e26  pop     r14
0x180004e28  pop     rdi
0x180004e29  pop     rsi
0x180004e2a  retn
```
