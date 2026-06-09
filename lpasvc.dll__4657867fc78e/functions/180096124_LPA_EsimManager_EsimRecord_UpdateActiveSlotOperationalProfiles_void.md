# LPA::EsimManager::EsimRecord::UpdateActiveSlotOperationalProfiles(void)

- ea: `0x180096124`
- end: `0x18009626a`
- name: `?UpdateActiveSlotOperationalProfiles@EsimRecord@EsimManager@LPA@@QEAAXXZ`
- size: `326`
- prototype: `void __fastcall(LPA::EsimManager::EsimRecord *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180094ca0`

## callees

- `0x18000199c`
- `0x180065bd4`
- `0x180096124`

## import_xrefs

- `ntdll!RtlQueryWnfStateData` at `0x180096173`
- `ntdll!RtlQueryWnfStateData` at `0x180096173`
- `ntdll!RtlPublishWnfStateData` at `0x1800961f0`
- `ntdll!RtlPublishWnfStateData` at `0x1800961f0`

## string_xrefs

- `0x180096222`: `LpaServiceEsimManager`
- `0x180096217`: `LPA::EsimManager::EsimRecord::UpdateActiveSlotOperationalProfiles`

## pseudocode

```c
void __fastcall LPA::EsimManager::EsimRecord::UpdateActiveSlotOperationalProfiles(LPA::EsimManager::EsimRecord *this)
{
  int v2; // ecx
  int v3; // r8d
  int v4; // r11d
  int v5; // r10d
  int v6; // r9d
  __int64 v7; // rax
  __int64 v8; // rax
  int v9; // [rsp+50h] [rbp-28h] BYREF
  int v10; // [rsp+54h] [rbp-24h] BYREF
  const char *v11; // [rsp+58h] [rbp-20h] BYREF
  const char *v12; // [rsp+60h] [rbp-18h] BYREF
  int v13; // [rsp+90h] [rbp+18h] BYREF
  int v14; // [rsp+98h] [rbp+20h] BYREF
  int v15; // [rsp+A0h] [rbp+28h] BYREF
  __int64 v16; // [rsp+A8h] [rbp+30h] BYREF

  if ( *(_DWORD *)(*((_QWORD *)this + 4) + 112LL) )
  {
    v14 = 0;
    v13 = 0;
    v15 = 0;
    v4 = RtlQueryWnfStateData(
           &v15,
           WNF_CELL_EUICC_OPERATIONAL_PROFILES_UPDATED,
           LPA::EsimManager::EsimRecord::WnfQueryCallback,
           &v14,
           0);
    if ( v4 )
    {
      v5 = 0;
      v14 = 0;
    }
    else
    {
      v5 = v14;
    }
    v6 = v13;
    v7 = **((_QWORD **)this + 10);
    v16 = v7;
    while ( !*(_BYTE *)(v7 + 25) )
    {
      v8 = *(_QWORD *)(*(_QWORD *)(v7 + 64) + 16LL);
      if ( (*(_BYTE *)(v8 + 4) & 4) != 0 && !*(_DWORD *)(v8 + 132) )
        v13 = v6 + 1;
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned long>>>,std::_Iterator_base0>::operator++(&v16);
      v7 = v16;
    }
    if ( v6 != v5 )
      v4 = RtlPublishWnfStateData(WNF_CELL_EUICC_OPERATIONAL_PROFILES_UPDATED, 0, &v13, 4, 0);
    if ( (unsigned int)CallbackContext > 4 )
    {
      v9 = v13;
      v10 = v14;
      v11 = "LPA::EsimManager::EsimRecord::UpdateActiveSlotOperationalProfiles";
      v12 = "LpaServiceEsimManager";
      LODWORD(v16) = v4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v2,
        (unsigned int)&unk_18012CB40,
        v3,
        v6,
        (__int64)&v12,
        (__int64)&v11,
        (__int64)&v10,
        (__int64)&v9,
        (__int64)&v16);
    }
  }
}

```

## disassembly

```asm
0x180096124  push    rbp
0x180096126  push    rbx
0x180096127  mov     rbp, rsp
0x18009612a  sub     rsp, 78h
0x18009612e  mov     rax, [rcx+20h]
0x180096132  mov     rbx, rcx
0x180096135  cmp     dword ptr [rax+70h], 0
0x180096139  jz      loc_180096263
0x18009613f  mov     rdx, cs:WNF_CELL_EUICC_OPERATIONAL_PROFILES_UPDATED
0x180096146  lea     r9, [rbp+arg_8]
0x18009614a  lea     r8, ?WnfQueryCallback@EsimRecord@EsimManager@LPA@@SAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; LPA::EsimManager::EsimRecord::WnfQueryCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180096151  mov     [rbp+arg_8], 0
0x180096158  lea     rcx, [rbp+arg_10]
0x18009615c  mov     [rbp+arg_0], 0
0x180096163  mov     [rbp+arg_10], 0
0x18009616a  mov     [rsp+78h+var_58], 0
0x180096173  call    cs:__imp_RtlQueryWnfStateData
0x180096179  mov     r11d, eax
0x18009617c  test    eax, eax
0x18009617e  jz      short loc_180096189
0x180096180  xor     r10d, r10d
0x180096183  mov     [rbp+arg_8], r10d
0x180096187  jmp     short loc_18009618D
0x180096189  mov     r10d, [rbp+arg_8]
0x18009618d  mov     rax, [rbx+50h]
0x180096191  mov     r9d, [rbp+arg_0]
0x180096195  mov     rax, [rax]
0x180096198  mov     [rbp+arg_18], rax
0x18009619c  cmp     byte ptr [rax+19h], 0
0x1800961a0  jnz     short loc_1800961CF
0x1800961a2  mov     rcx, [rax+40h]
0x1800961a6  mov     rax, [rcx+10h]
0x1800961aa  test    byte ptr [rax+4], 4
0x1800961ae  jz      short loc_1800961C0
0x1800961b0  cmp     dword ptr [rax+84h], 0
0x1800961b7  jnz     short loc_1800961C0
0x1800961b9  inc     r9d
0x1800961bc  mov     [rbp+arg_0], r9d
0x1800961c0  lea     rcx, [rbp+arg_18]
0x1800961c4  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ulong>>>,std::_Iterator_base0>::operator++(void)
0x1800961c9  mov     rax, [rbp+arg_18]
0x1800961cd  jmp     short loc_18009619C
0x1800961cf  cmp     r9d, r10d
0x1800961d2  jz      short loc_1800961F9
0x1800961d4  mov     rcx, cs:WNF_CELL_EUICC_OPERATIONAL_PROFILES_UPDATED
0x1800961db  lea     r8, [rbp+arg_0]
0x1800961df  mov     r9d, 4
0x1800961e5  mov     [rsp+78h+var_58], 0
0x1800961ee  xor     edx, edx
0x1800961f0  call    cs:__imp_RtlPublishWnfStateData
0x1800961f6  mov     r11d, eax
0x1800961f9  mov     eax, cs:CallbackContext
0x1800961ff  cmp     eax, 4
0x180096202  jbe     short loc_180096263
0x180096204  mov     eax, [rbp+arg_0]
0x180096207  lea     rdx, unk_18012CB40
0x18009620e  mov     [rbp+var_28], eax
0x180096211  mov     eax, [rbp+arg_8]
0x180096214  mov     [rbp+var_24], eax
0x180096217  lea     rax, aLpaEsimmanager_17; "LPA::EsimManager::EsimRecord::UpdateAct"...
0x18009621e  mov     [rbp+var_20], rax
0x180096222  lea     rax, aLpaserviceesim; "LpaServiceEsimManager"
0x180096229  mov     [rbp+var_18], rax
0x18009622d  lea     rax, [rbp+arg_18]
0x180096231  mov     [rsp+78h+var_38], rax
0x180096236  lea     rax, [rbp+var_28]
0x18009623a  mov     [rsp+78h+var_40], rax
0x18009623f  lea     rax, [rbp+var_24]
0x180096243  mov     [rsp+78h+var_48], rax
0x180096248  lea     rax, [rbp+var_20]
0x18009624c  mov     [rsp+78h+var_50], rax
0x180096251  lea     rax, [rbp+var_18]
0x180096255  mov     [rsp+78h+var_58], rax
0x18009625a  mov     dword ptr [rbp+arg_18], r11d
0x18009625e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180096263  add     rsp, 78h
0x180096267  pop     rbx
0x180096268  pop     rbp
0x180096269  retn
```
