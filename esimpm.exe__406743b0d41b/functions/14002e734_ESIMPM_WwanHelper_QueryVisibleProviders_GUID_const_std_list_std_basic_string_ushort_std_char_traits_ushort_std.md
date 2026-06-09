# ESIMPM::WwanHelper::QueryVisibleProviders(_GUID const &,std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x14002e734`
- end: `0x14002ea61`
- name: `?QueryVisibleProviders@WwanHelper@ESIMPM@@QEAAKAEBU_GUID@@AEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `813`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x140029040`

## callees

- `0x1400015c4`
- `0x140002f60`
- `0x14000dd20`
- `0x140013df8`
- `0x140014f64`
- `0x140020620`
- `0x14002e734`
- `0x14002ec60`

## import_xrefs

- `wwapi!WwanQueryInterface` at `0x14002e795`
- `wwapi!WwanQueryInterface` at `0x14002e795`
- `wwapi!WwanFreeMemory` at `0x14002ea32`
- `wwapi!WwanFreeMemory` at `0x14002ea32`

## string_xrefs

- `0x14002e906`: `Operator #%d: name %s Id %s stats %d dataclass 0x%x`
- `0x14002e9c7`: `Operator #%d: name %s Id %s stats %d dataclass 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ESIMPM::WwanHelper::QueryVisibleProviders(_QWORD *a1, unsigned __int16 *a2, __int64 a3)
{
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rbx
  int v10; // eax
  __int64 v11; // r12
  unsigned int v12; // r15d
  __int64 v13; // rcx
  _WORD *v14; // r14
  unsigned __int64 v15; // r8
  __int64 v16; // r12
  unsigned int v17; // r15d
  __int64 v18; // rcx
  _WORD *v19; // r14
  unsigned __int64 v20; // r8
  __int64 v22; // [rsp+20h] [rbp-59h]
  __int64 v23; // [rsp+30h] [rbp-49h]
  __int64 v24; // [rsp+38h] [rbp-41h]
  unsigned int v25; // [rsp+40h] [rbp-39h] BYREF
  __int64 v26; // [rsp+48h] [rbp-31h] BYREF
  unsigned int v27; // [rsp+50h] [rbp-29h] BYREF
  const char *v28; // [rsp+58h] [rbp-21h] BYREF
  const char *v29; // [rsp+60h] [rbp-19h] BYREF
  char v30; // [rsp+68h] [rbp-11h]
  __int128 v31; // [rsp+70h] [rbp-9h] BYREF
  __int128 v32; // [rsp+80h] [rbp+7h]

  v27 = 0;
  v26 = 0;
  v6 = WwanQueryInterface(*a1, a2, 7, 0, &v27, &v26, 0, 0);
  v29 = (const char *)&v26;
  v30 = 1;
  if ( v6 )
  {
    if ( (unsigned int)dword_140075078 > 2 )
    {
      v28 = "ESIMPM::WwanHelper::QueryVisibleProviders";
      v29 = (const char *)a2;
      v25 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
        (unsigned int)dword_140075078,
        (__int64)word_14006C0B2,
        v7,
        v8,
        (__int64)&v25,
        (__int64 *)&v29,
        (const unsigned __int16 **)&v28);
    }
  }
  else
  {
    v9 = v26;
    if ( v26 )
    {
      if ( v27 >= 0x8E8 )
      {
        LODWORD(v22) = *(_DWORD *)(v26 + 1408);
        ESIMPM::Log::Info(
          "ESIMPM::WwanHelper::QueryVisibleProviders",
          (const struct _GUID *)a2,
          L"visible operators: count %d type %d",
          *(unsigned int *)(v26 + 1412),
          v22);
        v10 = *(_DWORD *)(v9 + 1408);
        if ( v10 == 2 )
        {
          v11 = *(_QWORD *)(v9 + 1416) + v26;
          v12 = 0;
          while ( v12 < *(_DWORD *)(v9 + 1412) )
          {
            v13 = 68LL * v12;
            v14 = (_WORD *)(v13 + v11);
            ++v12;
            LODWORD(v24) = *(_DWORD *)(v13 + v11 + 64);
            LODWORD(v23) = *(_DWORD *)(v13 + v11 + 16);
            ESIMPM::Log::Info(
              "ESIMPM::WwanHelper::QueryVisibleProviders",
              (const struct _GUID *)a2,
              L"Operator #%d: name %s Id %s stats %d dataclass 0x%x",
              v12,
              v13 + v11 + 20,
              v13 + v11,
              v23,
              v24);
            v31 = 0;
            v32 = 0;
            v15 = -1;
            do
              ++v15;
            while ( v14[v15] );
            std::wstring::_Construct<1,unsigned short const *>(&v31, v14, v15);
            std::list<std::wstring>::push_back(a3, &v31);
            std::wstring::_Tidy_deallocate((char **)&v31);
          }
        }
        else if ( v10 == 10 )
        {
          v16 = *(_QWORD *)(v9 + 1416) + v26;
          v17 = 0;
          while ( v17 < *(_DWORD *)(v9 + 1412) )
          {
            v18 = 80LL * v17;
            v19 = (_WORD *)(v18 + v16);
            ++v17;
            LODWORD(v24) = *(_DWORD *)(v18 + v16 + 64);
            LODWORD(v23) = *(_DWORD *)(v18 + v16 + 16);
            ESIMPM::Log::Info(
              "ESIMPM::WwanHelper::QueryVisibleProviders",
              (const struct _GUID *)a2,
              L"Operator #%d: name %s Id %s stats %d dataclass 0x%x",
              v17,
              v18 + v16 + 20,
              v18 + v16,
              v23,
              v24);
            v31 = 0;
            v32 = 0;
            v20 = -1;
            do
              ++v20;
            while ( v19[v20] );
            std::wstring::_Construct<1,unsigned short const *>(&v31, v19, v20);
            std::list<std::wstring>::push_back(a3, &v31);
            std::wstring::_Tidy_deallocate((char **)&v31);
          }
        }
        v6 = 0;
      }
      else
      {
        ESIMPM::Log::Error(
          "ESIMPM::WwanHelper::QueryVisibleProviders",
          a2,
          L"WwanIntfOpcodeInterfaceObject query return bad data: dwDataSize %d min size %d");
        v6 = 13;
      }
      WwanFreeMemory(v26);
    }
    else
    {
      if ( (unsigned int)dword_140075078 > 2 )
      {
        v29 = "ESIMPM::WwanHelper::QueryVisibleProviders";
        v28 = (const char *)a2;
        v25 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
          v5,
          (__int64)&word_14006C056,
          v7,
          v8,
          (__int64)&v25,
          (__int64 *)&v28,
          (const unsigned __int16 **)&v29);
      }
      return 13;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x14002e734  mov     [rsp-8+arg_18], rbx
0x14002e739  push    rbp
0x14002e73a  push    rsi
0x14002e73b  push    rdi
0x14002e73c  push    r12
0x14002e73e  push    r13
0x14002e740  push    r14
0x14002e742  push    r15
0x14002e744  lea     rbp, [rsp-27h]
0x14002e749  sub     rsp, 0A0h
0x14002e750  mov     rax, cs:__security_cookie
0x14002e757  xor     rax, rsp
0x14002e75a  mov     [rbp+57h+var_40], rax
0x14002e75e  mov     r13, r8
0x14002e761  mov     rsi, rdx
0x14002e764  xor     r14d, r14d
0x14002e767  mov     [rbp+57h+var_80], r14d
0x14002e76b  mov     [rbp+57h+var_88], r14
0x14002e76f  mov     [rsp+0D0h+var_98], r14
0x14002e774  mov     [rsp+0D0h+var_A0], r14
0x14002e779  lea     rax, [rbp+57h+var_88]
0x14002e77d  mov     [rsp+0D0h+var_A8], rax
0x14002e782  lea     rax, [rbp+57h+var_80]
0x14002e786  mov     [rsp+0D0h+var_B0], rax
0x14002e78b  xor     r9d, r9d
0x14002e78e  lea     r8d, [r14+7]
0x14002e792  mov     rcx, [rcx]
0x14002e795  call    cs:__imp_WwanQueryInterface
0x14002e79b  mov     ebx, eax
0x14002e79d  lea     rax, [rbp+57h+var_88]
0x14002e7a1  mov     [rbp+57h+var_70], rax
0x14002e7a5  mov     [rbp+57h+var_68], 1
0x14002e7a9  test    ebx, ebx
0x14002e7ab  jz      short loc_14002E7F7
0x14002e7ad  mov     ecx, cs:dword_140075078
0x14002e7b3  cmp     ecx, 2
0x14002e7b6  jbe     loc_14002E84A
0x14002e7bc  lea     rdi, aEsimpmWwanhelp_9; "ESIMPM::WwanHelper::QueryVisibleProvide"...
0x14002e7c3  mov     [rbp+57h+var_78], rdi
0x14002e7c7  mov     [rbp+57h+var_70], rsi
0x14002e7cb  mov     [rbp+57h+var_90], ebx
0x14002e7ce  lea     rax, [rbp+57h+var_78]
0x14002e7d2  mov     [rsp+0D0h+var_A0], rax
0x14002e7d7  lea     rax, [rbp+57h+var_70]
0x14002e7db  mov     [rsp+0D0h+var_A8], rax
0x14002e7e0  lea     rax, [rbp+57h+var_90]
0x14002e7e4  mov     [rsp+0D0h+var_B0], rax
0x14002e7e9  lea     rdx, word_14006C0B2
0x14002e7f0  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x14002e7f5  jmp     short loc_14002E84A
0x14002e7f7  mov     rbx, [rbp+57h+var_88]
0x14002e7fb  test    rbx, rbx
0x14002e7fe  jnz     short loc_14002E84F
0x14002e800  mov     eax, cs:dword_140075078
0x14002e806  cmp     eax, 2
0x14002e809  jbe     short loc_14002E845
0x14002e80b  lea     rdi, aEsimpmWwanhelp_9; "ESIMPM::WwanHelper::QueryVisibleProvide"...
0x14002e812  mov     [rbp+57h+var_70], rdi
0x14002e816  mov     [rbp+57h+var_78], rsi
0x14002e81a  mov     [rbp+57h+var_90], r14d
0x14002e81e  lea     rax, [rbp+57h+var_70]
0x14002e822  mov     [rsp+0D0h+var_A0], rax
0x14002e827  lea     rax, [rbp+57h+var_78]
0x14002e82b  mov     [rsp+0D0h+var_A8], rax
0x14002e830  lea     rax, [rbp+57h+var_90]
0x14002e834  mov     [rsp+0D0h+var_B0], rax
0x14002e839  lea     rdx, word_14006C056
0x14002e840  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x14002e845  mov     ebx, 0Dh
0x14002e84a  jmp     loc_14002EA38
0x14002e84f  mov     r9d, [rbp+57h+var_80]
0x14002e853  mov     eax, 8E8h
0x14002e858  mov     rdx, rsi; struct _GUID *
0x14002e85b  cmp     r9d, eax
0x14002e85e  jnb     short loc_14002E882
0x14002e860  mov     [rsp+0D0h+var_B0], rax
0x14002e865  lea     r8, aWwanintfopcode_4; "WwanIntfOpcodeInterfaceObject query ret"...
0x14002e86c  lea     rcx, aEsimpmWwanhelp_9; "ESIMPM::WwanHelper::QueryVisibleProvide"...
0x14002e873  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x14002e878  mov     ebx, 0Dh
0x14002e87d  jmp     loc_14002EA2E
0x14002e882  mov     eax, [rbx+580h]
0x14002e888  mov     dword ptr [rsp+0D0h+var_B0], eax
0x14002e88c  mov     r9d, [rbx+584h]
0x14002e893  lea     r8, aVisibleOperato; "visible operators: count %d type %d"
0x14002e89a  lea     rdi, aEsimpmWwanhelp_9; "ESIMPM::WwanHelper::QueryVisibleProvide"...
0x14002e8a1  mov     rcx, rdi; char *
0x14002e8a4  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14002e8a9  mov     eax, [rbx+580h]
0x14002e8af  cmp     eax, 2
0x14002e8b2  jnz     loc_14002E96C
0x14002e8b8  mov     r12, [rbp+57h+var_88]
0x14002e8bc  add     r12, [rbx+588h]
0x14002e8c3  mov     r15d, r14d
0x14002e8c6  cmp     [rbx+584h], r14d
0x14002e8cd  jbe     loc_14002EA2B
0x14002e8d3  mov     eax, r15d
0x14002e8d6  imul    rcx, rax, 44h ; 'D'
0x14002e8da  lea     r14, [rcx+r12]
0x14002e8de  inc     r15d
0x14002e8e1  lea     rdx, [r12+14h]
0x14002e8e6  add     rdx, rcx
0x14002e8e9  mov     eax, [r14+40h]
0x14002e8ed  mov     dword ptr [rsp+0D0h+var_98], eax
0x14002e8f1  mov     eax, [r14+10h]
0x14002e8f5  mov     dword ptr [rsp+0D0h+var_A0], eax
0x14002e8f9  mov     [rsp+0D0h+var_A8], r14
0x14002e8fe  mov     [rsp+0D0h+var_B0], rdx
0x14002e903  mov     r9d, r15d
0x14002e906  lea     r8, aOperatorDNameS; "Operator #%d: name %s Id %s stats %d da"...
0x14002e90d  mov     rdx, rsi; struct _GUID *
0x14002e910  mov     rcx, rdi; char *
0x14002e913  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14002e918  xorps   xmm0, xmm0
0x14002e91b  movups  [rbp+57h+var_60], xmm0
0x14002e91f  xorps   xmm1, xmm1
0x14002e922  movdqu  [rbp+57h+var_50], xmm1
0x14002e927  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002e92b  xor     eax, eax
0x14002e92d  inc     r8
0x14002e930  cmp     [r14+r8*2], ax
0x14002e935  jnz     short loc_14002E92D
0x14002e937  mov     rdx, r14
0x14002e93a  lea     rcx, [rbp+57h+var_60]
0x14002e93e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14002e943  nop
0x14002e944  lea     rdx, [rbp+57h+var_60]
0x14002e948  mov     rcx, r13
0x14002e94b  call    ?push_back@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::list<std::wstring>::push_back(std::wstring const &)
0x14002e950  nop
0x14002e951  lea     rcx, [rbp+57h+var_60]
0x14002e955  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002e95a  cmp     r15d, [rbx+584h]
0x14002e961  jb      loc_14002E8D3
0x14002e967  jmp     loc_14002EA28
0x14002e96c  cmp     eax, 0Ah
0x14002e96f  jnz     loc_14002EA2B
0x14002e975  mov     r12, [rbp+57h+var_88]
0x14002e979  add     r12, [rbx+588h]
0x14002e980  mov     r15d, r14d
0x14002e983  cmp     [rbx+584h], r14d
0x14002e98a  jbe     loc_14002EA2B
0x14002e990  mov     eax, r15d
0x14002e993  lea     rcx, [rax+rax*4]
0x14002e997  shl     rcx, 4
0x14002e99b  lea     r14, [rcx+r12]
0x14002e99f  inc     r15d
0x14002e9a2  lea     rdx, [r12+14h]
0x14002e9a7  add     rdx, rcx
0x14002e9aa  mov     eax, [r14+40h]
0x14002e9ae  mov     dword ptr [rsp+0D0h+var_98], eax
0x14002e9b2  mov     eax, [r14+10h]
0x14002e9b6  mov     dword ptr [rsp+0D0h+var_A0], eax
0x14002e9ba  mov     [rsp+0D0h+var_A8], r14
0x14002e9bf  mov     [rsp+0D0h+var_B0], rdx
0x14002e9c4  mov     r9d, r15d
0x14002e9c7  lea     r8, aOperatorDNameS; "Operator #%d: name %s Id %s stats %d da"...
0x14002e9ce  mov     rdx, rsi; struct _GUID *
0x14002e9d1  mov     rcx, rdi; char *
0x14002e9d4  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14002e9d9  xorps   xmm0, xmm0
0x14002e9dc  movups  [rbp+57h+var_60], xmm0
0x14002e9e0  xorps   xmm1, xmm1
0x14002e9e3  movdqu  [rbp+57h+var_50], xmm1
0x14002e9e8  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002e9ec  xor     eax, eax
0x14002e9ee  inc     r8
0x14002e9f1  cmp     [r14+r8*2], ax
0x14002e9f6  jnz     short loc_14002E9EE
0x14002e9f8  mov     rdx, r14
0x14002e9fb  lea     rcx, [rbp+57h+var_60]
0x14002e9ff  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14002ea04  nop
0x14002ea05  lea     rdx, [rbp+57h+var_60]
0x14002ea09  mov     rcx, r13
0x14002ea0c  call    ?push_back@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::list<std::wstring>::push_back(std::wstring const &)
0x14002ea11  nop
0x14002ea12  lea     rcx, [rbp+57h+var_60]
0x14002ea16  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002ea1b  cmp     r15d, [rbx+584h]
0x14002ea22  jb      loc_14002E990
0x14002ea28  xor     r14d, r14d
0x14002ea2b  mov     ebx, r14d
0x14002ea2e  mov     rcx, [rbp+57h+var_88]
0x14002ea32  call    cs:__imp_WwanFreeMemory
0x14002ea38  mov     eax, ebx
0x14002ea3a  mov     rcx, [rbp+57h+var_40]
0x14002ea3e  xor     rcx, rsp; StackCookie
0x14002ea41  call    __security_check_cookie
0x14002ea46  mov     rbx, [rsp+0D0h+arg_18]
0x14002ea4e  add     rsp, 0A0h
0x14002ea55  pop     r15
0x14002ea57  pop     r14
0x14002ea59  pop     r13
0x14002ea5b  pop     r12
0x14002ea5d  pop     rdi
0x14002ea5e  pop     rsi
0x14002ea5f  pop     rbp
0x14002ea60  retn
```
