# ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Clone(IEnumConnections * *)

- ea: `0x1800175ec`
- end: `0x180017702`
- name: `?Clone@?$CComEnumImpl@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@UEAAJPEAPEAUIEnumConnections@@@Z`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180017480`

## callees

- `0x180005800`
- `0x18000ea20`
- `0x18000fc0c`
- `0x1800168a4`
- `0x1800175ec`
- `0x1800177a0`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Clone(
        __int64 a1,
        void **a2)
{
  int Interface; // ebx
  int v5; // ebp
  __int64 v6; // r9
  int v7; // r15d
  _QWORD *v8; // rsi
  void *v10; // [rsp+68h] [rbp+10h] BYREF
  __int64 v11; // [rsp+70h] [rbp+18h] BYREF
  __int64 v12; // [rsp+78h] [rbp+20h] BYREF

  Interface = -2147467261;
  if ( a2 )
  {
    *a2 = 0;
    v10 = 0;
    Interface = ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>::CreateInstance(&v10);
    if ( Interface >= 0 )
    {
      v5 = 2;
      if ( (*(_BYTE *)(a1 + 40) & 2) != 0 )
      {
        ATL::CComPtrBase<IUnknown>::CComPtrBase<IUnknown>(&v12, a1);
        v6 = v12;
        v5 = 0;
        v7 = 1;
      }
      else
      {
        ATL::CComPtrBase<IUnknown>::CComPtrBase<IUnknown>(&v11, *(_QWORD *)(a1 + 8));
        v6 = v11;
        v7 = 0;
      }
      v8 = v10;
      Interface = ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Init(
                    v10,
                    *(_QWORD *)(a1 + 16),
                    *(_QWORD *)(a1 + 24),
                    v6,
                    0);
      if ( v5 )
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
      if ( v7 )
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
      if ( Interface < 0
        || (v8[4] = *(_QWORD *)(a1 + 32),
            Interface = ATL::AtlInternalQueryInterface(
                          v8,
                          (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>::_GetEntries'::`2'::_entries,
                          &GUID_b196b287_bab4_101a_b69c_00aa00341d07,
                          a2),
            Interface < 0) )
      {
        if ( v8 )
          (*(void (__fastcall **)(_QWORD *, __int64))(*v8 + 56LL))(v8, 1);
      }
    }
  }
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x1800175ec  mov     [rsp+arg_0], rbx
0x1800175f1  push    rbp
0x1800175f2  push    rsi
0x1800175f3  push    rdi
0x1800175f4  push    r14
0x1800175f6  push    r15
0x1800175f8  sub     rsp, 30h
0x1800175fc  mov     r14, rdx
0x1800175ff  mov     rdi, rcx
0x180017602  mov     ebx, 80004003h
0x180017607  test    rdx, rdx
0x18001760a  jz      loc_1800176EF
0x180017610  lea     rcx, [rsp+58h+arg_8]
0x180017615  mov     qword ptr [rdx], 0
0x18001761c  mov     [rsp+58h+arg_8], 0
0x180017625  call    ?CreateInstance@?$CComObject@V?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>::CreateInstance(ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>> * *)
0x18001762a  mov     ebx, eax
0x18001762c  test    eax, eax
0x18001762e  js      loc_1800176EF
0x180017634  mov     ebp, 2
0x180017639  test    [rdi+28h], bpl
0x18001763d  jz      short loc_180017659
0x18001763f  mov     rdx, rdi
0x180017642  lea     rcx, [rsp+58h+arg_18]
0x180017647  call    ??0?$CComPtrBase@UIUnknown@@@ATL@@IEAA@PEAUIUnknown@@@Z; ATL::CComPtrBase<IUnknown>::CComPtrBase<IUnknown>(IUnknown *)
0x18001764c  mov     r9, [rsp+58h+arg_18]
0x180017651  xor     ebp, ebp
0x180017653  lea     r15d, [rbp+1]
0x180017657  jmp     short loc_18001766F
0x180017659  mov     rdx, [rdi+8]
0x18001765d  lea     rcx, [rsp+58h+arg_10]
0x180017662  call    ??0?$CComPtrBase@UIUnknown@@@ATL@@IEAA@PEAUIUnknown@@@Z; ATL::CComPtrBase<IUnknown>::CComPtrBase<IUnknown>(IUnknown *)
0x180017667  mov     r9, [rsp+58h+arg_10]
0x18001766c  xor     r15d, r15d
0x18001766f  mov     rsi, [rsp+58h+arg_8]
0x180017674  mov     r8, [rdi+18h]
0x180017678  mov     rcx, rsi
0x18001767b  mov     rdx, [rdi+10h]
0x18001767f  mov     [rsp+58h+var_38], 0
0x180017687  call    ?Init@?$CComEnumImpl@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@QEAAJPEAUtagCONNECTDATA@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z; ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Init(tagCONNECTDATA *,tagCONNECTDATA *,IUnknown *,ATL::CComEnumFlags)
0x18001768c  mov     ebx, eax
0x18001768e  test    ebp, ebp
0x180017690  jz      short loc_18001769C
0x180017692  lea     rcx, [rsp+58h+arg_10]
0x180017697  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001769c  test    r15d, r15d
0x18001769f  jz      short loc_1800176AB
0x1800176a1  lea     rcx, [rsp+58h+arg_18]
0x1800176a6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800176ab  test    ebx, ebx
0x1800176ad  js      short loc_1800176D6
0x1800176af  mov     rax, [rdi+20h]
0x1800176b3  lea     r8, _GUID_b196b287_bab4_101a_b69c_00aa00341d07; struct _GUID *
0x1800176ba  mov     r9, r14; void **
0x1800176bd  mov     [rsi+20h], rax
0x1800176c1  lea     rdx, ?_entries@?1??_GetEntries@?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800176c8  mov     rcx, rsi; void *
0x1800176cb  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800176d0  mov     ebx, eax
0x1800176d2  test    eax, eax
0x1800176d4  jns     short loc_1800176EF
0x1800176d6  test    rsi, rsi
0x1800176d9  jz      short loc_1800176EF
0x1800176db  mov     rax, [rsi]
0x1800176de  mov     edx, 1
0x1800176e3  mov     rcx, rsi
0x1800176e6  mov     rax, [rax+38h]
0x1800176ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176ef  mov     eax, ebx
0x1800176f1  mov     rbx, [rsp+58h+arg_0]
0x1800176f6  add     rsp, 30h
0x1800176fa  pop     r15
0x1800176fc  pop     r14
0x1800176fe  pop     rdi
0x1800176ff  pop     rsi
0x180017700  pop     rbp
0x180017701  retn
```
