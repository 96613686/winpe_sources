# ATL::IConnectionPointImpl<CMSMQEvent,&_GUID const DIID__DMSMQEventEvents,ATL::CComDynamicUnkArray>::EnumConnections(IEnumConnections * *)

- ea: `0x180009af0`
- end: `0x180009c81`
- name: `?EnumConnections@?$IConnectionPointImpl@VCMSMQEvent@@$1?DIID__DMSMQEventEvents@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJPEAPEAUIEnumConnections@@@Z`
- size: `401`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000173c`
- `0x180009374`
- `0x18000962c`
- `0x180009af0`
- `0x18000a1a8`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall ATL::IConnectionPointImpl<CMSMQEvent,&_GUID const DIID__DMSMQEventEvents,ATL::CComDynamicUnkArray>::EnumConnections(
        __int64 a1,
        void **a2)
{
  _QWORD *v5; // rax
  void *v6; // rbx
  __int64 v7; // rcx
  int *v8; // rdi
  __int64 *v9; // rdx
  __int64 v10; // rax
  void *v11; // rax
  void *v12; // rbp
  _DWORD *v13; // r15
  __int64 *v14; // rsi
  __int64 *v15; // rax
  __int64 *v16; // rcx
  int Interface; // edi

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = operator new(0x40u);
  v6 = v5;
  if ( !v5 )
    return 2147942414LL;
  v5[1] = 0;
  v5[4] = 0;
  v5[3] = 0;
  v5[2] = 0;
  *((_DWORD *)v5 + 10) = 0;
  *((_DWORD *)v5 + 12) = 0;
  *v5 = &ATL::CComObject<ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::`vftable';
  _InterlockedIncrement(&dword_180038608);
  v7 = *(int *)(a1 + 16);
  v8 = (int *)(a1 + 8);
  if ( v8[2] >= 2 )
  {
    v9 = *(__int64 **)v8;
    v10 = *(_QWORD *)v8 + 8 * v7;
  }
  else
  {
    v9 = (__int64 *)v8;
    v10 = (__int64)&v8[2 * v7];
  }
  v11 = operator new(saturated_mul((unsigned int)((v10 - (__int64)v9) >> 3), 0x10u));
  v12 = v11;
  if ( !v11 )
  {
    ATL::CComObject<ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::`scalar deleting destructor'(v6);
    return 2147942414LL;
  }
  v13 = v11;
  v14 = (__int64 *)v8;
  if ( v8[2] >= 2 )
    v14 = *(__int64 **)v8;
  while ( 1 )
  {
    v15 = (__int64 *)v8;
    if ( v8[2] >= 2 )
      v15 = *(__int64 **)v8;
    if ( v14 >= &v15[v8[2]] )
      break;
    if ( *v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)*v14 + 8LL))(*v14);
      v16 = (__int64 *)v8;
      *(_QWORD *)v13 = *v14;
      if ( v8[2] >= 2 )
        v16 = *(__int64 **)v8;
      v13[2] = v14 - v16 + 1;
      v13 += 4;
    }
    ++v14;
  }
  ATL::CComEnumImpl<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::Init(
    v6,
    v12,
    v13,
    0,
    2);
  Interface = ATL::AtlInternalQueryInterface(
                v6,
                (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>::_GetEntries'::`2'::_entries,
                &IID_IEnumConnections,
                a2);
  if ( Interface < 0 )
    ATL::CComObject<ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::`scalar deleting destructor'(v6);
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x180009af0  push    rbx
0x180009af2  push    rbp
0x180009af3  push    rsi
0x180009af4  push    rdi
0x180009af5  push    r14
0x180009af7  push    r15
0x180009af9  sub     rsp, 38h
0x180009afd  mov     r14, rdx
0x180009b00  mov     rdi, rcx
0x180009b03  test    rdx, rdx
0x180009b06  jnz     short loc_180009B12
0x180009b08  mov     eax, 80004003h
0x180009b0d  jmp     loc_180009BC5
0x180009b12  mov     ecx, 40h ; '@'; Size
0x180009b17  mov     qword ptr [rdx], 0
0x180009b1e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009b23  mov     rbx, rax
0x180009b26  test    rax, rax
0x180009b29  jz      loc_180009BC0
0x180009b2f  mov     qword ptr [rax+8], 0
0x180009b37  mov     qword ptr [rax+20h], 0
0x180009b3f  mov     qword ptr [rax+18h], 0
0x180009b47  mov     qword ptr [rax+10h], 0
0x180009b4f  mov     dword ptr [rax+28h], 0
0x180009b56  mov     dword ptr [rax+30h], 0
0x180009b5d  lea     rax, ??_7?$CComObject@V?$CComEnum@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@6B@; const ATL::CComObject<ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::`vftable'
0x180009b64  mov     [rbx], rax
0x180009b67  lock inc cs:dword_180038608
0x180009b6e  movsxd  rcx, dword ptr [rdi+10h]
0x180009b72  add     rdi, 8
0x180009b76  cmp     dword ptr [rdi+8], 2
0x180009b7a  jge     short loc_180009B85
0x180009b7c  mov     rdx, rdi
0x180009b7f  lea     rax, [rdi+rcx*8]
0x180009b83  jmp     short loc_180009B8C
0x180009b85  mov     rdx, [rdi]
0x180009b88  lea     rax, [rdx+rcx*8]
0x180009b8c  sub     rax, rdx
0x180009b8f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180009b96  sar     rax, 3
0x180009b9a  mov     edx, eax
0x180009b9c  mov     eax, 10h
0x180009ba1  mul     rdx
0x180009ba4  cmovb   rax, rcx
0x180009ba8  mov     rcx, rax; Size
0x180009bab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009bb0  mov     rbp, rax
0x180009bb3  test    rax, rax
0x180009bb6  jnz     short loc_180009BD2
0x180009bb8  mov     rcx, rbx; Block
0x180009bbb  call    ??_G?$CComObject@V?$CComEnum@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::`scalar deleting destructor'(uint)
0x180009bc0  mov     eax, 8007000Eh
0x180009bc5  add     rsp, 38h
0x180009bc9  pop     r15
0x180009bcb  pop     r14
0x180009bcd  pop     rdi
0x180009bce  pop     rsi
0x180009bcf  pop     rbp
0x180009bd0  pop     rbx
0x180009bd1  retn
0x180009bd2  cmp     dword ptr [rdi+8], 2
0x180009bd6  mov     r15, rbp
0x180009bd9  mov     rsi, rdi
0x180009bdc  jl      short loc_180009BE1
0x180009bde  mov     rsi, [rdi]
0x180009be1  cmp     dword ptr [rdi+8], 2
0x180009be5  mov     rax, rdi
0x180009be8  movsxd  rcx, dword ptr [rdi+8]
0x180009bec  jl      short loc_180009BF1
0x180009bee  mov     rax, [rdi]
0x180009bf1  lea     rax, [rax+rcx*8]
0x180009bf5  cmp     rsi, rax
0x180009bf8  jnb     short loc_180009C3A
0x180009bfa  mov     rcx, [rsi]
0x180009bfd  test    rcx, rcx
0x180009c00  jz      short loc_180009C34
0x180009c02  mov     rax, [rcx]
0x180009c05  mov     rax, [rax+8]
0x180009c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c0e  mov     rax, [rsi]
0x180009c11  mov     rcx, rdi
0x180009c14  mov     [r15], rax
0x180009c17  cmp     dword ptr [rdi+8], 2
0x180009c1b  jl      short loc_180009C20
0x180009c1d  mov     rcx, [rdi]
0x180009c20  mov     rax, rsi
0x180009c23  sub     rax, rcx
0x180009c26  sar     rax, 3
0x180009c2a  inc     eax
0x180009c2c  mov     [r15+8], eax
0x180009c30  add     r15, 10h
0x180009c34  add     rsi, 8
0x180009c38  jmp     short loc_180009BE1
0x180009c3a  xor     r9d, r9d
0x180009c3d  mov     [rsp+68h+var_48], 2
0x180009c45  mov     r8, r15
0x180009c48  mov     rdx, rbp
0x180009c4b  mov     rcx, rbx
0x180009c4e  call    ?Init@?$CComEnumImpl@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@V?$CComEnum@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@QEAAJPEAUtagCONNECTDATA@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z; ATL::CComEnumImpl<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::Init(tagCONNECTDATA *,tagCONNECTDATA *,IUnknown *,ATL::CComEnumFlags)
0x180009c53  mov     r9, r14; void **
0x180009c56  lea     r8, IID_IEnumConnections; struct _GUID *
0x180009c5d  lea     rdx, ?_entries@?1??_GetEntries@?$CComEnum@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180009c64  mov     rcx, rbx; void *
0x180009c67  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180009c6c  mov     edi, eax
0x180009c6e  test    eax, eax
0x180009c70  jns     short loc_180009C7A
0x180009c72  mov     rcx, rbx; Block
0x180009c75  call    ??_G?$CComObject@V?$CComEnum@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::`scalar deleting destructor'(uint)
0x180009c7a  mov     eax, edi
0x180009c7c  jmp     loc_180009BC5
```
