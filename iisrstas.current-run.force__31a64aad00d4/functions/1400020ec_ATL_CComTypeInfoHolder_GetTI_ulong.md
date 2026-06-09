# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x1400020ec`
- end: `0x140002295`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `425`
- prototype: `int(ATL::CComTypeInfoHolder *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140001e80`
- `0x1400022a0`
- `0x140002360`

## callees

- `0x1400020ec`
- `0x1400023fc`
- `0x140006010`

## import_xrefs

- `ATL!__imp_AtlComPtrAssign` at `0x1400021de`
- `ATL!__imp_AtlComPtrAssign` at `0x1400021de`
- `ATL!__imp_AtlModuleAddTermFunc` at `0x14000220c`
- `ATL!__imp_AtlModuleAddTermFunc` at `0x14000220c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140002285`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140002285`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140002121`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140002121`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x14000215a`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x14000215a`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(struct ITypeInfo *this, LCID a2)
{
  HRESULT NameCache; // ebx
  ATL::CComTypeInfoHolder *v5; // rcx
  int (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rcx
  ITypeLib *pptlib; // [rsp+30h] [rbp-10h] BYREF
  struct ITypeInfo *v8; // [rsp+60h] [rbp+20h] BYREF
  int (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp+30h] BYREF
  __int64 v10; // [rsp+78h] [rbp+38h] BYREF

  v8 = this;
  if ( qword_14000A0A8 && qword_14000A0B8 )
    return 0;
  NameCache = 0;
  EnterCriticalSection(&CriticalSection);
  if ( !qword_14000A0A8 )
  {
    pptlib = 0;
    NameCache = LoadRegTypeLib(rguid, word_14000A0A0, word_14000A0A2, a2, &pptlib);
    if ( NameCache >= 0 )
    {
      v9 = 0;
      NameCache = ((__int64 (__fastcall *)(ITypeLib *, GUID *, _QWORD))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                    pptlib,
                    ATL::IDispatchImpl<IIisServiceControl,&_GUID const IID_IIisServiceControl,&_GUID const LIBID_IISRSTALib,1,0,ATL::CComTypeInfoHolder>::_tih[0],
                    &v9);
      if ( NameCache >= 0 )
      {
        v6 = v9;
        v8 = (struct ITypeInfo *)v9;
        if ( v9 )
        {
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v9)[1])(v9);
          v6 = v9;
        }
        v10 = 0;
        if ( (**v6)(v6, &GUID_00020412_0000_0000_c000_000000000046, &v10) >= 0 )
          AtlComPtrAssign(&v8, v10);
        qword_14000A0A8 = v8;
        v8 = 0;
        AtlModuleAddTermFunc(
          &_Module,
          ATL::CComTypeInfoHolder::Cleanup,
          ATL::IDispatchImpl<IIisServiceControl,&_GUID const IID_IIisServiceControl,&_GUID const LIBID_IISRSTALib,1,0,ATL::CComTypeInfoHolder>::_tih);
        if ( v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        if ( v8 )
          ((void (__fastcall *)(struct ITypeInfo *))v8->lpVtbl->Release)(v8);
      }
      ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
      v5 = (ATL::CComTypeInfoHolder *)v9;
      if ( v9 )
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v9)[2])(v9);
    }
  }
  if ( qword_14000A0A8 )
  {
    if ( !qword_14000A0B8 )
      NameCache = ATL::CComTypeInfoHolder::LoadNameCache(v5, qword_14000A0A8);
  }
  LeaveCriticalSection(&CriticalSection);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x1400020ec  mov     [rsp-18h+arg_0], rcx
0x1400020f1  push    rbp
0x1400020f2  push    rbx
0x1400020f3  push    rdi
0x1400020f4  mov     rbp, rsp
0x1400020f7  sub     rsp, 40h
0x1400020fb  cmp     cs:qword_14000A0A8, 0
0x140002103  mov     edi, edx
0x140002105  jz      short loc_140002118
0x140002107  cmp     cs:qword_14000A0B8, 0
0x14000210f  jz      short loc_140002118
0x140002111  xor     eax, eax
0x140002113  jmp     loc_14000228D
0x140002118  lea     rcx, CriticalSection; lpCriticalSection
0x14000211f  xor     ebx, ebx
0x140002121  call    cs:__imp_EnterCriticalSection
0x140002127  cmp     cs:qword_14000A0A8, rbx
0x14000212e  jnz     loc_140002261
0x140002134  movzx   r8d, cs:word_14000A0A2; wVerMinor
0x14000213c  lea     rax, [rbp+var_10]
0x140002140  movzx   edx, cs:word_14000A0A0; wVerMajor
0x140002147  mov     r9d, edi; lcid
0x14000214a  mov     rcx, cs:rguid; rguid
0x140002151  mov     [rsp+40h+pptlib], rax; pptlib
0x140002156  mov     [rbp+var_10], rbx
0x14000215a  call    cs:__imp_LoadRegTypeLib
0x140002160  mov     ebx, eax
0x140002162  test    eax, eax
0x140002164  js      loc_140002261
0x14000216a  mov     rcx, [rbp+var_10]
0x14000216e  lea     r8, [rbp+arg_10]
0x140002172  mov     rdx, cs:?_tih@?$IDispatchImpl@UIIisServiceControl@@$1?IID_IIisServiceControl@@3U_GUID@@B$1?LIBID_IISRSTALib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; ATL::CComTypeInfoHolder ATL::IDispatchImpl<IIisServiceControl,&_GUID const IID_IIisServiceControl,&_GUID const LIBID_IISRSTALib,1,0,ATL::CComTypeInfoHolder>::_tih
0x140002179  mov     [rbp+arg_10], 0
0x140002181  mov     rax, [rcx]
0x140002184  mov     rax, [rax+30h]
0x140002188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000218d  mov     ebx, eax
0x14000218f  test    eax, eax
0x140002191  js      loc_14000223C
0x140002197  mov     rcx, [rbp+arg_10]
0x14000219b  mov     [rbp+arg_0], rcx
0x14000219f  test    rcx, rcx
0x1400021a2  jz      short loc_1400021B4
0x1400021a4  mov     rax, [rcx]
0x1400021a7  mov     rax, [rax+8]
0x1400021ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400021b0  mov     rcx, [rbp+arg_10]
0x1400021b4  mov     [rbp+arg_18], 0
0x1400021bc  lea     r8, [rbp+arg_18]
0x1400021c0  mov     rax, [rcx]
0x1400021c3  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x1400021ca  mov     rax, [rax]
0x1400021cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400021d2  test    eax, eax
0x1400021d4  js      short loc_1400021E4
0x1400021d6  mov     rdx, [rbp+arg_18]
0x1400021da  lea     rcx, [rbp+arg_0]
0x1400021de  call    cs:__imp_AtlComPtrAssign
0x1400021e4  mov     rax, [rbp+arg_0]
0x1400021e8  lea     r8, ?_tih@?$IDispatchImpl@UIIisServiceControl@@$1?IID_IIisServiceControl@@3U_GUID@@B$1?LIBID_IISRSTALib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; ATL::CComTypeInfoHolder ATL::IDispatchImpl<IIisServiceControl,&_GUID const IID_IIisServiceControl,&_GUID const LIBID_IISRSTALib,1,0,ATL::CComTypeInfoHolder>::_tih
0x1400021ef  lea     rdx, ?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z; ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)
0x1400021f6  mov     cs:qword_14000A0A8, rax
0x1400021fd  lea     rcx, ?_Module@@3VCExeModule@@A; CExeModule _Module
0x140002204  mov     [rbp+arg_0], 0
0x14000220c  call    cs:__imp_AtlModuleAddTermFunc
0x140002212  mov     rcx, [rbp+arg_18]
0x140002216  test    rcx, rcx
0x140002219  jz      short loc_140002227
0x14000221b  mov     rax, [rcx]
0x14000221e  mov     rax, [rax+10h]
0x140002222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002227  mov     rcx, [rbp+arg_0]
0x14000222b  test    rcx, rcx
0x14000222e  jz      short loc_14000223C
0x140002230  mov     rax, [rcx]
0x140002233  mov     rax, [rax+10h]
0x140002237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000223c  mov     rcx, [rbp+var_10]
0x140002240  mov     rax, [rcx]
0x140002243  mov     rax, [rax+10h]
0x140002247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000224c  mov     rcx, [rbp+arg_10]
0x140002250  test    rcx, rcx
0x140002253  jz      short loc_140002261
0x140002255  mov     rax, [rcx]
0x140002258  mov     rax, [rax+10h]
0x14000225c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002261  mov     rdx, cs:qword_14000A0A8; struct ITypeInfo *
0x140002268  test    rdx, rdx
0x14000226b  jz      short loc_14000227E
0x14000226d  cmp     cs:qword_14000A0B8, 0
0x140002275  jnz     short loc_14000227E
0x140002277  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x14000227c  mov     ebx, eax
0x14000227e  lea     rcx, CriticalSection; lpCriticalSection
0x140002285  call    cs:__imp_LeaveCriticalSection
0x14000228b  mov     eax, ebx
0x14000228d  add     rsp, 40h
0x140002291  pop     rdi
0x140002292  pop     rbx
0x140002293  pop     rbp
0x140002294  retn
```
