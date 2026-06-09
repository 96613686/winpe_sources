# UpdateTenantRestrictionsListTimerRoutine(void *,uchar)

- ea: `0x18000ba60`
- end: `0x18000bca9`
- name: `?UpdateTenantRestrictionsListTimerRoutine@@YAXPEAXE@Z`
- size: `585`
- prototype: `void __fastcall(PVOID)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800012a8`
- `0x180001a50`
- `0x180003e84`
- `0x180004518`
- `0x180008570`
- `0x180009d60`
- `0x18000b67c`
- `0x18000ba60`
- `0x18000c338`
- `0x18000c400`
- `0x18000c498`
- `0x18000ce9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18000baec`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18000bb8d`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18000baec`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18000bb8d`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18000ba9f`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18000ba9f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000ba97`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000ba97`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18000bc49`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18000bc49`

## string_xrefs

- `0x18000bc96`: `onecoreuap\ds\ext\common\ntservice\lib\tenantrestrictions.cpp`
- `0x18000ba85`: `TenantRestrictionsListUpdateCallback`

## pseudocode

```c
void __fastcall UpdateTenantRestrictionsListTimerRoutine(PVOID a1)
{
  char v1; // di
  DWORD TickCount; // eax
  int updated; // eax
  __int64 v4; // rcx
  __int64 v5; // r8
  char v6; // r14
  ULONG v7; // esi
  TenantRestrictions *v8; // rbx
  unsigned int v9; // eax
  int v10; // eax
  int v11; // edx
  int v12; // ecx
  const char *v13; // r9
  int v14; // [rsp+30h] [rbp-188h] BYREF
  _BYTE v15[244]; // [rsp+40h] [rbp-178h] BYREF
  int v16; // [rsp+134h] [rbp-84h]
  _BYTE v17[32]; // [rsp+150h] [rbp-68h] BYREF
  int *v18; // [rsp+170h] [rbp-48h]
  __int64 v19; // [rsp+178h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v1 = 0;
  v14 = 0;
  TenantRestrictionsLoggers::AutoMeasureLogger::AutoMeasureLogger(
    (TenantRestrictionsLoggers::AutoMeasureLogger *)v15,
    "TenantRestrictionsListUpdateCallback");
  TickCount = GetTickCount();
  _o_srand(TickCount);
  updated = TenantRestrictions::UpdateTenantRestrictionsList(g_trGlobals);
  try
  {
    v6 = updated;
    if ( updated )
    {
      if ( (unsigned int)dword_180019048 > 5 )
      {
        v14 = *((_DWORD *)g_trGlobals + 24);
        v18 = &v14;
        v19 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_180019048, &word_18001530E, 0);
      }
      v8 = g_trGlobals;
      v7 = rand() % 1000 + *((_DWORD *)v8 + 24);
      v9 = *((_DWORD *)g_trGlobals + 24);
      if ( v9 >= 0x5265C00 )
      {
        if ( (Microsoft_Windows_TenantRestrictionsEnableBits & 8) != 0 )
        {
          std::wstring::wstring((__int64)v17, (__int64)g_trGlobals + 184);
          v1 = 3;
          v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
          McTemplateU0zdd_EventWriteTransfer(v12, v11, v10, v7 / 0x36EE80, v6);
        }
        if ( (v1 & 1) != 0 )
          std::wstring::_Tidy_deallocate((__int64)v17);
      }
      else
      {
        *((_DWORD *)g_trGlobals + 24) = 2 * v9;
      }
    }
    else
    {
      if ( (Microsoft_Windows_TenantRestrictionsEnableBits & 4) != 0 )
        McGenEventWrite_EventWriteTransfer(v4, EndpointSyncSuccess, v5, 1, v17);
      *((_DWORD *)g_trGlobals + 24) = 1000;
      v7 = 60000 * (rand() % 960 + 1440);
    }
    if ( !ChangeTimerQueueTimer(*((HANDLE *)g_trGlobals + 14), *((HANDLE *)g_trGlobals + 13), v7, v7) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xA1,
        (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\tenantrestrictions.cpp",
        v13);
    v15[240] = 1;
    v16 = 0;
    TenantRestrictionsLoggers::AutoMeasureLogger::~AutoMeasureLogger((TenantRestrictionsLoggers::AutoMeasureLogger *)v15);
  }
  catch ( ... )
  {
  }
}

```

## disassembly

```asm
0x18000ba60  push    rbx
0x18000ba62  push    rsi
0x18000ba63  push    rdi
0x18000ba64  push    r14
0x18000ba66  sub     rsp, 198h
0x18000ba6d  mov     rax, cs:__security_cookie
0x18000ba74  xor     rax, rsp
0x18000ba77  mov     [rsp+1B8h+var_38], rax
0x18000ba7f  xor     edi, edi
0x18000ba81  mov     [rsp+1B8h+var_188], edi
0x18000ba85  lea     rdx, aTenantrestrict_1; "TenantRestrictionsListUpdateCallback"
0x18000ba8c  lea     rcx, [rsp+1B8h+var_178]; this
0x18000ba91  call    ??0AutoMeasureLogger@TenantRestrictionsLoggers@@QEAA@PEBD@Z; TenantRestrictionsLoggers::AutoMeasureLogger::AutoMeasureLogger(char const *)
0x18000ba96  nop
0x18000ba97  call    cs:__imp_GetTickCount
0x18000ba9d  mov     ecx, eax
0x18000ba9f  call    cs:__imp__o_srand
0x18000baa5  mov     rcx, cs:?g_trGlobals@@3V?$unique_ptr@VTenantRestrictions@@U?$default_delete@VTenantRestrictions@@@std@@@std@@A; this
0x18000baac  call    ?UpdateTenantRestrictionsList@TenantRestrictions@@QEAAJXZ; TenantRestrictions::UpdateTenantRestrictionsList(void)
0x18000bab1  mov     r14d, eax
0x18000bab4  test    eax, eax
0x18000bab6  jnz     short loc_18000BB26
0x18000bab8  test    cs:Microsoft_Windows_TenantRestrictionsEnableBits, 4
0x18000babf  jz      short loc_18000BADE
0x18000bac1  lea     rax, [rsp+1B8h+var_68]
0x18000bac9  mov     [rsp+1B8h+var_198], rax
0x18000bace  lea     r9d, [rdi+1]
0x18000bad2  lea     rdx, EndpointSyncSuccess
0x18000bad9  call    McGenEventWrite_EventWriteTransfer
0x18000bade  mov     rax, cs:?g_trGlobals@@3V?$unique_ptr@VTenantRestrictions@@U?$default_delete@VTenantRestrictions@@@std@@@std@@A; std::unique_ptr<TenantRestrictions> g_trGlobals
0x18000bae5  mov     dword ptr [rax+60h], 3E8h
0x18000baec  call    cs:__imp_rand
0x18000baf2  mov     r8d, eax
0x18000baf5  mov     eax, 88888889h
0x18000bafa  imul    r8d
0x18000bafd  add     edx, r8d
0x18000bb00  sar     edx, 9
0x18000bb03  mov     ecx, edx
0x18000bb05  shr     ecx, 1Fh
0x18000bb08  add     edx, ecx
0x18000bb0a  imul    ecx, edx, 3C0h
0x18000bb10  sub     r8d, ecx
0x18000bb13  add     r8d, 5A0h
0x18000bb1a  imul    esi, r8d, 0EA60h
0x18000bb21  jmp     loc_18000BC34
0x18000bb26  mov     eax, cs:dword_180019048
0x18000bb2c  cmp     eax, 5
0x18000bb2f  jbe     short loc_18000BB86
0x18000bb31  mov     rax, cs:?g_trGlobals@@3V?$unique_ptr@VTenantRestrictions@@U?$default_delete@VTenantRestrictions@@@std@@@std@@A; std::unique_ptr<TenantRestrictions> g_trGlobals
0x18000bb38  mov     ecx, [rax+60h]
0x18000bb3b  mov     [rsp+1B8h+var_188], ecx
0x18000bb3f  lea     rax, [rsp+1B8h+var_188]
0x18000bb44  mov     [rsp+1B8h+var_48], rax
0x18000bb4c  mov     [rsp+1B8h+var_40], 4
0x18000bb58  lea     rax, [rsp+1B8h+var_68]
0x18000bb60  mov     [rsp+1B8h+var_190], rax
0x18000bb65  mov     dword ptr [rsp+1B8h+var_198], 3
0x18000bb6d  xor     r9d, r9d
0x18000bb70  xor     r8d, r8d
0x18000bb73  lea     rdx, word_18001530E
0x18000bb7a  lea     rcx, dword_180019048
0x18000bb81  call    _tlgWriteTransfer_EventWriteTransfer
0x18000bb86  mov     rbx, cs:?g_trGlobals@@3V?$unique_ptr@VTenantRestrictions@@U?$default_delete@VTenantRestrictions@@@std@@@std@@A; std::unique_ptr<TenantRestrictions> g_trGlobals
0x18000bb8d  call    cs:__imp_rand
0x18000bb93  mov     r8d, eax
0x18000bb96  mov     eax, 10624DD3h
0x18000bb9b  imul    r8d
0x18000bb9e  sar     edx, 6
0x18000bba1  mov     ecx, edx
0x18000bba3  shr     ecx, 1Fh
0x18000bba6  add     edx, ecx
0x18000bba8  imul    ecx, edx, 3E8h
0x18000bbae  sub     r8d, ecx
0x18000bbb1  mov     esi, [rbx+60h]
0x18000bbb4  add     esi, r8d
0x18000bbb7  mov     rcx, cs:?g_trGlobals@@3V?$unique_ptr@VTenantRestrictions@@U?$default_delete@VTenantRestrictions@@@std@@@std@@A; std::unique_ptr<TenantRestrictions> g_trGlobals
0x18000bbbe  mov     eax, [rcx+60h]
0x18000bbc1  cmp     eax, 5265C00h
0x18000bbc6  jnb     short loc_18000BBCF
0x18000bbc8  add     eax, eax
0x18000bbca  mov     [rcx+60h], eax
0x18000bbcd  jmp     short loc_18000BC34
0x18000bbcf  test    cs:Microsoft_Windows_TenantRestrictionsEnableBits, 8
0x18000bbd6  jz      short loc_18000BC21
0x18000bbd8  mov     eax, 95217CB1h
0x18000bbdd  mul     esi
0x18000bbdf  mov     ebx, edx
0x18000bbe1  shr     ebx, 15h
0x18000bbe4  mov     rdx, cs:?g_trGlobals@@3V?$unique_ptr@VTenantRestrictions@@U?$default_delete@VTenantRestrictions@@@std@@@std@@A; std::unique_ptr<TenantRestrictions> g_trGlobals
0x18000bbeb  add     rdx, 0B8h
0x18000bbf2  lea     rcx, [rsp+1B8h+var_68]
0x18000bbfa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000bbff  mov     edi, 3
0x18000bc04  lea     rcx, [rsp+1B8h+var_68]
0x18000bc0c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000bc11  mov     r8, rax
0x18000bc14  mov     dword ptr [rsp+1B8h+var_198], r14d
0x18000bc19  mov     r9d, ebx
0x18000bc1c  call    McTemplateU0zdd_EventWriteTransfer
0x18000bc21  test    dil, 1
0x18000bc25  jz      short loc_18000BC34
0x18000bc27  lea     rcx, [rsp+1B8h+var_68]
0x18000bc2f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000bc34  mov     rcx, cs:?g_trGlobals@@3V?$unique_ptr@VTenantRestrictions@@U?$default_delete@VTenantRestrictions@@@std@@@std@@A; std::unique_ptr<TenantRestrictions> g_trGlobals
0x18000bc3b  mov     r9d, esi; Period
0x18000bc3e  mov     r8d, esi; DueTime
0x18000bc41  mov     rdx, [rcx+68h]; Timer
0x18000bc45  mov     rcx, [rcx+70h]; TimerQueue
0x18000bc49  call    cs:__imp_ChangeTimerQueueTimer
0x18000bc4f  mov     rcx, [rsp+1B8h]; this
0x18000bc57  test    eax, eax
0x18000bc59  jz      short loc_18000BC96
0x18000bc5b  mov     [rsp+1B8h+var_88], 1
0x18000bc63  mov     [rsp+1B8h+var_84], 0
0x18000bc6e  lea     rcx, [rsp+1B8h+var_178]; this
0x18000bc73  call    ??1AutoMeasureLogger@TenantRestrictionsLoggers@@UEAA@XZ; TenantRestrictionsLoggers::AutoMeasureLogger::~AutoMeasureLogger(void)
0x18000bc78  nop
0x18000bc79  mov     rcx, [rsp+1B8h+var_38]
0x18000bc81  xor     rcx, rsp; StackCookie
0x18000bc84  call    __security_check_cookie
0x18000bc89  add     rsp, 198h
0x18000bc90  pop     r14
0x18000bc92  pop     rdi
0x18000bc93  pop     rsi
0x18000bc94  pop     rbx
0x18000bc95  retn
0x18000bc96  lea     r8, aOnecoreuapDsEx_1; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000bc9d  mov     edx, 0A1h; void *
0x18000bca2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
