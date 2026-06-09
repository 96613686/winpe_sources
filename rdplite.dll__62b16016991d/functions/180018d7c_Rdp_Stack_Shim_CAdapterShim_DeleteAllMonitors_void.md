# Rdp::Stack::Shim::CAdapterShim::DeleteAllMonitors(void)

- ea: `0x180018d7c`
- end: `0x180018f88`
- name: `?DeleteAllMonitors@CAdapterShim@Shim@Stack@Rdp@@AEAAXXZ`
- size: `524`
- prototype: `void __fastcall(Rdp::Stack::Shim::CAdapterShim *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019894`
- `0x18001a8a8`

## callees

- `0x18000141c`
- `0x1800023fc`
- `0x18000d98c`
- `0x180018090`
- `0x180018388`
- `0x1800187f8`
- `0x180018d7c`
- `0x18001ec84`

## string_xrefs

- `0x180018e69`: `AdapterShimDeleteMonitors: %d`
- `0x180018e62`: `Rdp::Stack::Shim::CAdapterShim::DeleteAllMonitors`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Rdp::Stack::Shim::CAdapterShim::DeleteAllMonitors(Rdp::Stack::Shim::CAdapterShim *this)
{
  int v2; // r8d
  int v3; // r9d
  char *v4; // rsi
  __int64 *v5; // rbx
  __int64 *v6; // rdi
  __int64 *v7; // rcx
  __int64 *v8; // rax
  __int64 *v9; // rdx
  __int64 v10; // rax
  __int64 *i; // rax
  __int64 j; // rax
  __int64 *v13; // rbx
  __int64 v14; // [rsp+50h] [rbp-20h] BYREF
  _QWORD v15[3]; // [rsp+58h] [rbp-18h] BYREF
  int v16; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v17; // [rsp+A8h] [rbp+38h] BYREF
  __int128 *v18; // [rsp+B0h] [rbp+40h] BYREF
  const char *v19; // [rsp+B8h] [rbp+48h] BYREF

  if ( (unsigned int)dword_18003C058 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003C058, 0x470000000000LL) )
  {
    v17 = *((_QWORD *)this + 21);
    v16 = *((_DWORD *)this + 84);
    v18 = &xmmword_18003CA50;
    v19 = "RdpLite";
    v14 = 0x1000000;
    v15[0] = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)word_1800356BA,
      v2,
      v3,
      (__int64)v15,
      (__int64)&v14,
      (__int64)&v19,
      (__int64)&v18,
      (__int64)&v16,
      (__int64)&v17);
  }
  v4 = (char *)this + 160;
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"AdapterShimDeleteMonitors: %d",
    "Rdp::Stack::Shim::CAdapterShim::DeleteAllMonitors",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    0x252u,
    *((_QWORD *)this + 21));
  std::unique_lock<std::shared_mutex>::unique_lock<std::shared_mutex>(v15, (char *)this + 176);
  v5 = (__int64 *)*((_QWORD *)this + 20);
  v6 = **(__int64 ***)v4;
  while ( v5 != v6 )
  {
    if ( *((_BYTE *)v5 + 25) )
    {
      v7 = (__int64 *)v5[2];
    }
    else
    {
      v7 = (__int64 *)*v5;
      if ( *(_BYTE *)(*v5 + 25) )
      {
        v7 = v5;
        v8 = (__int64 *)v5[1];
        if ( !*((_BYTE *)v8 + 25) )
        {
          v9 = v5;
          do
          {
            if ( v9 != (__int64 *)*v8 )
              break;
            v9 = v8;
            v7 = v8;
            v8 = (__int64 *)v8[1];
          }
          while ( !*((_BYTE *)v8 + 25) );
        }
        if ( !*((_BYTE *)v7 + 25) )
          v7 = v8;
      }
      else
      {
        while ( !*(_BYTE *)(v7[2] + 25) )
          v7 = (__int64 *)v7[2];
      }
    }
    Rdp::Stack::Shim::CMonitorShim::Stop((Rdp::Stack::Shim::CMonitorShim *)v7[6]);
    if ( *((_BYTE *)v5 + 25) )
    {
      v5 = (__int64 *)v5[2];
    }
    else
    {
      v10 = *v5;
      if ( *(_BYTE *)(*v5 + 25) )
      {
        for ( i = (__int64 *)v5[1]; !*((_BYTE *)i + 25) && v5 == (__int64 *)*i; i = (__int64 *)i[1] )
          v5 = i;
        if ( !*((_BYTE *)v5 + 25) )
          v5 = i;
      }
      else
      {
        v5 = (__int64 *)*v5;
        for ( j = *(_QWORD *)(v10 + 16); !*(_BYTE *)(j + 25); j = v5[2] )
          v5 = (__int64 *)v5[2];
      }
    }
  }
  v13 = *(__int64 **)v4;
  std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *>>>(
    v4,
    v4,
    *(_QWORD *)(*(_QWORD *)v4 + 8LL));
  v13[1] = (__int64)v13;
  *v13 = (__int64)v13;
  v13[2] = (__int64)v13;
  *((_QWORD *)v4 + 1) = 0;
  std::unique_lock<std::shared_mutex>::~unique_lock<std::shared_mutex>(v15);
}

```

## disassembly

```asm
0x180018d7c  push    rbp
0x180018d7e  push    rbx
0x180018d7f  push    rsi
0x180018d80  push    rdi
0x180018d81  push    r14
0x180018d83  mov     rbp, rsp
0x180018d86  sub     rsp, 70h
0x180018d8a  mov     rbx, rcx
0x180018d8d  mov     eax, cs:dword_18003C058
0x180018d93  xor     r14d, r14d
0x180018d96  cmp     eax, 4
0x180018d99  jbe     loc_180018E43
0x180018d9f  mov     rdx, 470000000000h
0x180018da9  lea     rcx, dword_18003C058
0x180018db0  call    _tlgKeywordOn
0x180018db5  test    al, al
0x180018db7  jz      loc_180018E43
0x180018dbd  mov     rax, [rbx+0A8h]
0x180018dc4  mov     [rbp+arg_8], rax
0x180018dc8  mov     eax, [rbx+150h]
0x180018dce  mov     [rbp+arg_0], eax
0x180018dd1  lea     rax, xmmword_18003CA50
0x180018dd8  mov     [rbp+arg_10], rax
0x180018ddc  lea     rax, aRdplite; "RdpLite"
0x180018de3  mov     [rbp+arg_18], rax
0x180018de7  mov     [rbp+var_20], 1000000h
0x180018def  lea     rax, aCheckpoint; "Checkpoint"
0x180018df6  mov     [rbp+var_18], rax
0x180018dfa  lea     rax, [rbp+arg_8]
0x180018dfe  mov     [rsp+70h+var_28], rax
0x180018e03  lea     rax, [rbp+arg_0]
0x180018e07  mov     [rsp+70h+var_30], rax
0x180018e0c  lea     rax, [rbp+arg_10]
0x180018e10  mov     [rsp+70h+var_38], rax
0x180018e15  lea     rax, [rbp+arg_18]
0x180018e19  mov     [rsp+70h+var_40], rax
0x180018e1e  lea     rax, [rbp+var_20]
0x180018e22  mov     [rsp+70h+var_48], rax
0x180018e27  lea     rax, [rbp+var_18]
0x180018e2b  mov     qword ptr [rsp+70h+var_50], rax
0x180018e30  lea     rdx, word_1800356BA
0x180018e37  lea     rcx, dword_18003C058
0x180018e3e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180018e43  lea     rsi, [rbx+0A0h]
0x180018e4a  mov     rax, [rsi+8]
0x180018e4e  mov     [rsp+70h+var_48], rax
0x180018e53  mov     [rsp+70h+var_50], 252h; unsigned int
0x180018e5b  lea     r9, aOnecoreuapTerm_25; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180018e62  lea     r8, aRdpStackShimCa_2; "Rdp::Stack::Shim::CAdapterShim::DeleteA"...
0x180018e69  lea     rdx, aAdaptershimdel; "AdapterShimDeleteMonitors: %d"
0x180018e70  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180018e77  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180018e7c  lea     rdx, [rbx+0B0h]
0x180018e83  lea     rcx, [rbp+var_18]
0x180018e87  call    ??0?$unique_lock@Vshared_mutex@std@@@std@@QEAA@AEAVshared_mutex@1@@Z; std::unique_lock<std::shared_mutex>::unique_lock<std::shared_mutex>(std::shared_mutex &)
0x180018e8c  nop
0x180018e8d  mov     rbx, [rsi]
0x180018e90  mov     rdi, [rbx]
0x180018e93  cmp     rbx, rdi
0x180018e96  jz      loc_180018F53
0x180018e9c  cmp     [rbx+19h], r14b
0x180018ea0  jz      short loc_180018EA8
0x180018ea2  mov     rcx, [rbx+10h]
0x180018ea6  jmp     short loc_180018EEF
0x180018ea8  mov     rcx, [rbx]
0x180018eab  cmp     [rcx+19h], r14b
0x180018eaf  jz      short loc_180018EE5
0x180018eb1  mov     rcx, rbx
0x180018eb4  mov     rax, [rbx+8]
0x180018eb8  cmp     [rax+19h], r14b
0x180018ebc  jnz     short loc_180018ED6
0x180018ebe  mov     rdx, rbx
0x180018ec1  cmp     rdx, [rax]
0x180018ec4  jnz     short loc_180018ED6
0x180018ec6  mov     rdx, rax
0x180018ec9  mov     rcx, rax
0x180018ecc  mov     rax, [rax+8]
0x180018ed0  cmp     [rax+19h], r14b
0x180018ed4  jz      short loc_180018EC1
0x180018ed6  cmp     [rcx+19h], r14b
0x180018eda  jnz     short loc_180018EEF
0x180018edc  mov     rcx, rax
0x180018edf  jmp     short loc_180018EEF
0x180018ee1  mov     rcx, [rcx+10h]
0x180018ee5  mov     rax, [rcx+10h]
0x180018ee9  cmp     [rax+19h], r14b
0x180018eed  jz      short loc_180018EE1
0x180018eef  mov     rcx, [rcx+30h]; this
0x180018ef3  call    ?Stop@CMonitorShim@Shim@Stack@Rdp@@QEAAXXZ; Rdp::Stack::Shim::CMonitorShim::Stop(void)
0x180018ef8  cmp     [rbx+19h], r14b
0x180018efc  jz      short loc_180018F04
0x180018efe  mov     rbx, [rbx+10h]
0x180018f02  jmp     short loc_180018E93
0x180018f04  mov     rax, [rbx]
0x180018f07  cmp     [rax+19h], r14b
0x180018f0b  jz      short loc_180018F37
0x180018f0d  mov     rax, [rbx+8]
0x180018f11  jmp     short loc_180018F1F
0x180018f13  cmp     rbx, [rax]
0x180018f16  jnz     short loc_180018F25
0x180018f18  mov     rbx, rax
0x180018f1b  mov     rax, [rax+8]
0x180018f1f  cmp     [rax+19h], r14b
0x180018f23  jz      short loc_180018F13
0x180018f25  cmp     [rbx+19h], r14b
0x180018f29  jnz     loc_180018E93
0x180018f2f  mov     rbx, rax
0x180018f32  jmp     loc_180018E93
0x180018f37  mov     rbx, rax
0x180018f3a  mov     rax, [rax+10h]
0x180018f3e  jmp     short loc_180018F48
0x180018f40  mov     rbx, [rbx+10h]
0x180018f44  mov     rax, [rbx+10h]
0x180018f48  cmp     [rax+19h], r14b
0x180018f4c  jz      short loc_180018F40
0x180018f4e  jmp     loc_180018E93
0x180018f53  mov     rbx, [rsi]
0x180018f56  mov     r8, [rbx+8]
0x180018f5a  mov     rdx, rsi
0x180018f5d  mov     rcx, rsi
0x180018f60  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *>> &,std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *> *)
0x180018f65  mov     [rbx+8], rbx
0x180018f69  mov     [rbx], rbx
0x180018f6c  mov     [rbx+10h], rbx
0x180018f70  mov     [rsi+8], r14
0x180018f74  lea     rcx, [rbp+var_18]
0x180018f78  call    ??1?$unique_lock@Vshared_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::shared_mutex>::~unique_lock<std::shared_mutex>(void)
0x180018f7d  add     rsp, 70h
0x180018f81  pop     r14
0x180018f83  pop     rdi
0x180018f84  pop     rsi
0x180018f85  pop     rbx
0x180018f86  pop     rbp
0x180018f87  retn
```
