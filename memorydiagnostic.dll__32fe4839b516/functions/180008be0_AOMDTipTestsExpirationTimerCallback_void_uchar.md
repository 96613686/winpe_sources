# AOMDTipTestsExpirationTimerCallback(void *,uchar)

- ea: `0x180008be0`
- end: `0x180008cbd`
- name: `?AOMDTipTestsExpirationTimerCallback@@YAXPEAXE@Z`
- size: `221`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001008`
- `0x180008be0`
- `0x18000f144`
- `0x1800165dc`
- `0x180016740`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180008c78`
- `KERNEL32!LeaveCriticalSection` at `0x180008c78`
- `KERNEL32!EnterCriticalSection` at `0x180008c46`
- `KERNEL32!EnterCriticalSection` at `0x180008c46`

## string_xrefs

- `0x180008c84`: `AOMDUsageTipTestCompletionReason::Expired`

## pseudocode

```c
void __fastcall AOMDTipTestsExpirationTimerCallback(PVOID a1)
{
  const struct _tlgProvider_t *v1; // rax
  __int64 v2; // r8
  __int64 v3; // r9
  char *v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  const char *v6; // rcx
  const char *v7; // r8
  char v8; // dl
  const char *v9; // rax
  const wchar_t *v10; // [rsp+50h] [rbp+18h] BYREF

  v1 = TlgHelper::Provider();
  if ( *(_DWORD *)v1 > 4u && (*((_BYTE *)v1 + 16) & 2) != 0 && (*((_QWORD *)v1 + 3) & 2LL) == *((_QWORD *)v1 + 3) )
  {
    v10 = L"AOMDTipTestsExpirationTimerCallback_TIPTestExpired";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v1,
      byte_18002AB01,
      v2,
      v3,
      (void **)&v10);
  }
  if ( g_reliabilityTipTest )
  {
    v4 = (char *)g_reliabilityTipTest + 8;
    v5 = (struct _RTL_CRITICAL_SECTION *)((char *)g_reliabilityTipTest + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)g_reliabilityTipTest + 5);
    *((_DWORD *)v4 + 16) |= 0x300u;
    if ( *((_QWORD *)v4 + 30) )
      tip2::details::shared_data<0,0,0>::complete_helper((__int64)v4, 2);
    if ( v5 )
      LeaveCriticalSection(v5);
  }
  v6 = "AOMDUsageTipTestCompletionReason::Expired";
  v7 = "AOMDUsageTipTestCompletionReason::Expired";
  v8 = 65;
  do
  {
    v9 = ++v6;
    if ( v8 != 58 )
      v9 = v7;
    v7 = v9;
    v8 = *v6;
  }
  while ( *v6 );
  tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
    v6,
    100,
    v9);
}

```

## disassembly

```asm
0x180008be0  mov     [rsp+arg_0], rbx
0x180008be5  push    rdi
0x180008be6  sub     rsp, 30h
0x180008bea  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x180008bef  cmp     dword ptr [rax], 4
0x180008bf2  jbe     short loc_180008C2C
0x180008bf4  test    byte ptr [rax+10h], 2
0x180008bf8  jz      short loc_180008C2C
0x180008bfa  mov     rcx, [rax+18h]
0x180008bfe  and     ecx, 2
0x180008c01  cmp     rcx, [rax+18h]
0x180008c05  jnz     short loc_180008C2C
0x180008c07  lea     rcx, aAomdtiptestsex; "AOMDTipTestsExpirationTimerCallback_TIP"...
0x180008c0e  mov     [rsp+38h+arg_10], rcx
0x180008c13  lea     rcx, [rsp+38h+arg_10]
0x180008c18  mov     [rsp+38h+var_18], rcx
0x180008c1d  lea     rdx, byte_18002AB01
0x180008c24  mov     rcx, rax
0x180008c27  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180008c2c  mov     rax, cs:?g_reliabilityTipTest@@3V?$tip_test@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@A; tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>> g_reliabilityTipTest
0x180008c33  test    rax, rax
0x180008c36  jz      short loc_180008C84
0x180008c38  lea     rbx, [rax+8]
0x180008c3c  lea     rdi, [rbx+0C0h]
0x180008c43  mov     rcx, rdi; lpCriticalSection
0x180008c46  call    cs:__imp_EnterCriticalSection
0x180008c4d  nop     dword ptr [rax+rax+00h]
0x180008c52  or      dword ptr [rbx+40h], 300h
0x180008c59  cmp     qword ptr [rbx+0F0h], 0
0x180008c61  jz      short loc_180008C70
0x180008c63  mov     edx, 2
0x180008c68  mov     rcx, rbx
0x180008c6b  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180008c70  test    rdi, rdi
0x180008c73  jz      short loc_180008C84
0x180008c75  mov     rcx, rdi; lpCriticalSection
0x180008c78  call    cs:__imp_LeaveCriticalSection
0x180008c7f  nop     dword ptr [rax+rax+00h]
0x180008c84  lea     rcx, aAomdusagetipte; "AOMDUsageTipTestCompletionReason::Expir"...
0x180008c8b  mov     r8, rcx
0x180008c8e  mov     dl, 41h ; 'A'
0x180008c90  inc     rcx
0x180008c93  mov     rax, rcx
0x180008c96  cmp     dl, 3Ah ; ':'
0x180008c99  cmovnz  rax, r8
0x180008c9d  mov     r8, rax
0x180008ca0  mov     dl, [rcx]
0x180008ca2  test    dl, dl
0x180008ca4  jnz     short loc_180008C90
0x180008ca6  mov     edx, 64h ; 'd'
0x180008cab  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x180008cb0  nop
0x180008cb1  mov     rbx, [rsp+38h+arg_0]
0x180008cb6  add     rsp, 30h
0x180008cba  pop     rdi
0x180008cbb  retn
```
