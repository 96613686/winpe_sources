# Rdp::Stack::Graphics::CChannelPipeline::ProcessReadBuffer(wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy> const &,uint)

- ea: `0x1800118a4`
- end: `0x180011a16`
- name: `?ProcessReadBuffer@CChannelPipeline@Graphics@Stack@Rdp@@IEAAJAEBV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@I@Z`
- size: `370`
- prototype: `__int64 __fastcall(__int64, _QWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010cbc`

## callees

- `0x1800014e8`
- `0x180001fe4`
- `0x1800118a4`
- `0x180012728`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Rdp::Stack::Graphics::CChannelPipeline::ProcessReadBuffer(__int64 a1, _QWORD *a2, unsigned int a3)
{
  int v6; // esi
  __int64 v7; // r15
  _DWORD *v8; // rdi
  _DWORD *v9; // rcx
  int v10; // r8d
  int v11; // r9d
  _DWORD *v12; // rcx
  int v13; // r8d
  int v14; // r9d
  const char *v16; // [rsp+80h] [rbp+8h] BYREF
  const char *v17; // [rsp+88h] [rbp+10h] BYREF

  v6 = 0;
  v7 = *(_QWORD *)(*a2 + 120LL);
  v8 = (_DWORD *)(a1 + 528);
  if ( !*(_DWORD *)(a1 + 804) )
  {
    v6 = 1;
    if ( !*v8 )
    {
      v9 = *(_DWORD **)(wil::details::static_lazy<RdpGrfxPipelinePerfProvider>::get() + 8);
      if ( *v9 > 5u )
      {
        v16 = "Begin";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (_DWORD)v9,
          (unsigned int)byte_180035101,
          v10,
          v11,
          (__int64)&v16);
      }
    }
    *(_DWORD *)(a1 + 800) = **(_DWORD **)(*a2 + 120LL) - 16;
    v7 += 16;
    a3 -= 16;
  }
  *(_DWORD *)(*a2 + 144LL) = a3;
  *(_DWORD *)(a1 + 804) += a3;
  if ( *(_DWORD *)(a1 + 804) == *(_DWORD *)(a1 + 800) )
  {
    v6 |= 2u;
    *(_DWORD *)(a1 + 804) = 0;
  }
  if ( !*v8 )
  {
    v12 = *(_DWORD **)(wil::details::static_lazy<RdpGrfxPipelinePerfProvider>::get() + 8);
    if ( *v12 > 5u )
    {
      v16 = *(const char **)(*a2 + 128LL);
      v17 = "Begin";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        (_DWORD)v12,
        (unsigned int)byte_1800350D1,
        v13,
        v14,
        (__int64)&v17,
        (__int64)&v16);
    }
  }
  *(_DWORD *)(*a2 + 136LL) = v6;
  return (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64, int, _DWORD, int, _QWORD))(**(_QWORD **)(a1 + 792)
                                                                                               + 24LL))(
           *(_QWORD *)(a1 + 792),
           a3,
           v7,
           2,
           1,
           *(_DWORD *)(a1 + 800),
           v6,
           *a2);
}

```

## disassembly

```asm
0x1800118a4  mov     [rsp+arg_10], rbx
0x1800118a9  mov     [rsp+arg_18], rbp
0x1800118ae  push    rsi
0x1800118af  push    rdi
0x1800118b0  push    r13
0x1800118b2  push    r14
0x1800118b4  push    r15
0x1800118b6  sub     rsp, 50h
0x1800118ba  mov     ebp, r8d
0x1800118bd  mov     r14, rdx
0x1800118c0  mov     rbx, rcx
0x1800118c3  xor     esi, esi
0x1800118c5  mov     rax, [rdx]
0x1800118c8  mov     r15, [rax+78h]
0x1800118cc  lea     rdi, [rcx+210h]
0x1800118d3  lea     r13, aBegin; "Begin"
0x1800118da  cmp     [rcx+324h], esi
0x1800118e0  jnz     short loc_180011936
0x1800118e2  mov     esi, 1
0x1800118e7  cmp     dword ptr [rdi], 0
0x1800118ea  jnz     short loc_18001191D
0x1800118ec  call    ?get@?$static_lazy@VRdpGrfxPipelinePerfProvider@@@details@wil@@QEAAPEAVRdpGrfxPipelinePerfProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpGrfxPipelinePerfProvider>::get(void (*)(void))
0x1800118f1  mov     rcx, [rax+8]
0x1800118f5  mov     eax, [rcx]
0x1800118f7  cmp     eax, 5
0x1800118fa  jbe     short loc_18001191D
0x1800118fc  mov     [rsp+78h+arg_0], r13
0x180011904  lea     rax, [rsp+78h+arg_0]
0x18001190c  mov     [rsp+78h+var_58], rax
0x180011911  lea     rdx, byte_180035101
0x180011918  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18001191d  mov     rax, [r14]
0x180011920  mov     rcx, [rax+78h]
0x180011924  mov     eax, [rcx]
0x180011926  sub     eax, 10h
0x180011929  mov     [rbx+320h], eax
0x18001192f  add     r15, 10h
0x180011933  add     ebp, 0FFFFFFF0h
0x180011936  mov     rax, [r14]
0x180011939  mov     [rax+90h], ebp
0x18001193f  add     [rbx+324h], ebp
0x180011945  mov     eax, [rbx+324h]
0x18001194b  cmp     eax, [rbx+320h]
0x180011951  jnz     short loc_180011960
0x180011953  or      esi, 2
0x180011956  mov     dword ptr [rbx+324h], 0
0x180011960  cmp     dword ptr [rdi], 0
0x180011963  jnz     short loc_1800119B5
0x180011965  call    ?get@?$static_lazy@VRdpGrfxPipelinePerfProvider@@@details@wil@@QEAAPEAVRdpGrfxPipelinePerfProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpGrfxPipelinePerfProvider>::get(void (*)(void))
0x18001196a  mov     rcx, [rax+8]
0x18001196e  mov     eax, [rcx]
0x180011970  cmp     eax, 5
0x180011973  jbe     short loc_1800119B5
0x180011975  mov     rax, [r14]
0x180011978  mov     rdx, [rax+80h]
0x18001197f  mov     [rsp+78h+arg_0], rdx
0x180011987  mov     [rsp+78h+arg_8], r13
0x18001198f  lea     rax, [rsp+78h+arg_0]
0x180011997  mov     [rsp+78h+var_50], rax
0x18001199c  lea     rax, [rsp+78h+arg_8]
0x1800119a4  mov     [rsp+78h+var_58], rax
0x1800119a9  lea     rdx, byte_1800350D1
0x1800119b0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800119b5  mov     rax, [r14]
0x1800119b8  mov     [rax+88h], esi
0x1800119be  mov     rcx, [rbx+318h]
0x1800119c5  mov     rax, [rcx]
0x1800119c8  mov     r10, [r14]
0x1800119cb  mov     [rsp+78h+var_40], r10
0x1800119d0  mov     [rsp+78h+var_48], esi
0x1800119d4  mov     r10d, [rbx+320h]
0x1800119db  mov     dword ptr [rsp+78h+var_50], r10d
0x1800119e0  mov     dword ptr [rsp+78h+var_58], 1
0x1800119e8  mov     r9d, 2
0x1800119ee  mov     r8, r15
0x1800119f1  mov     edx, ebp
0x1800119f3  mov     rax, [rax+18h]
0x1800119f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119fc  nop
0x1800119fd  lea     r11, [rsp+78h+var_28]
0x180011a02  mov     rbx, [r11+40h]
0x180011a06  mov     rbp, [r11+48h]
0x180011a0a  mov     rsp, r11
0x180011a0d  pop     r15
0x180011a0f  pop     r14
0x180011a11  pop     r13
0x180011a13  pop     rdi
0x180011a14  pop     rsi
0x180011a15  retn
```
