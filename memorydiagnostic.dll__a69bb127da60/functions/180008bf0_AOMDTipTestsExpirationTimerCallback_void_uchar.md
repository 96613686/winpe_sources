# AOMDTipTestsExpirationTimerCallback(void *,uchar)

- ea: `0x180008bf0`
- end: `0x180008cc2`
- name: `?AOMDTipTestsExpirationTimerCallback@@YAXPEAXE@Z`
- size: `210`
- prototype: `void __fastcall(PVOID)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001008`
- `0x180008bf0`
- `0x18000e7ec`
- `0x1800158a0`
- `0x180015a4c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180008c89`
- `KERNEL32!LeaveCriticalSection` at `0x180008c89`
- `KERNEL32!EnterCriticalSection` at `0x180008c5d`
- `KERNEL32!EnterCriticalSection` at `0x180008c5d`

## string_xrefs

- `0x180008c8f`: `AOMDUsageTipTestCompletionReason::Expired`

## pseudocode

```c
void __fastcall AOMDTipTestsExpirationTimerCallback(PVOID a1)
{
  const struct _tlgProvider_t *v1; // rax
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 v4; // rcx
  char *v5; // rbx
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  const char *v7; // rax
  const char *v8; // r8
  const wchar_t *v9; // [rsp+50h] [rbp+18h] BYREF

  v1 = TlgHelper::Provider();
  v4 = *(unsigned int *)v1;
  if ( (unsigned int)v4 > 4 )
  {
    v4 = *((_QWORD *)v1 + 2);
    if ( (v4 & 2) != 0 )
    {
      v4 = *((_QWORD *)v1 + 3) & 2LL;
      if ( v4 == *((_QWORD *)v1 + 3) )
      {
        v9 = L"AOMDTipTestsExpirationTimerCallback_TIPTestExpired";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v1,
          (__int64)byte_180029A45,
          v2,
          v3,
          (int **)&v9);
      }
    }
  }
  if ( g_reliabilityTipTest )
  {
    v5 = (char *)g_reliabilityTipTest + 8;
    v6 = (struct _RTL_CRITICAL_SECTION *)((char *)g_reliabilityTipTest + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)g_reliabilityTipTest + 5);
    *((_DWORD *)v5 + 16) |= 0x300u;
    if ( *((_QWORD *)v5 + 30) )
      tip2::details::shared_data<0,0,0>::complete_helper(v5, 2);
    if ( v6 )
      LeaveCriticalSection(v6);
  }
  v7 = "AOMDUsageTipTestCompletionReason::Expired";
  v8 = "AOMDUsageTipTestCompletionReason::Expired";
  LOBYTE(v4) = 65;
  do
  {
    ++v7;
    if ( (_BYTE)v4 == 58 )
      v8 = v7;
    LOBYTE(v4) = *v7;
  }
  while ( *v7 );
  tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
    v4,
    100,
    v8);
}

```

## disassembly

```asm
0x180008bf0  mov     [rsp+arg_0], rbx
0x180008bf5  push    rdi
0x180008bf6  sub     rsp, 30h
0x180008bfa  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x180008bff  mov     ecx, [rax]
0x180008c01  cmp     ecx, 4
0x180008c04  jbe     short loc_180008C43
0x180008c06  mov     rdx, [rax+18h]
0x180008c0a  mov     rcx, [rax+10h]
0x180008c0e  test    cl, 2
0x180008c11  jz      short loc_180008C43
0x180008c13  mov     rcx, rdx
0x180008c16  and     ecx, 2
0x180008c19  cmp     rcx, rdx
0x180008c1c  jnz     short loc_180008C43
0x180008c1e  lea     rcx, aAomdtiptestsex; "AOMDTipTestsExpirationTimerCallback_TIP"...
0x180008c25  mov     [rsp+38h+arg_10], rcx
0x180008c2a  lea     rcx, [rsp+38h+arg_10]
0x180008c2f  mov     [rsp+38h+var_18], rcx
0x180008c34  lea     rdx, byte_180029A45
0x180008c3b  mov     rcx, rax
0x180008c3e  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180008c43  mov     rax, cs:?g_reliabilityTipTest@@3V?$tip_test@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@A; tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>> g_reliabilityTipTest
0x180008c4a  test    rax, rax
0x180008c4d  jz      short loc_180008C8F
0x180008c4f  lea     rbx, [rax+8]
0x180008c53  lea     rdi, [rbx+0C0h]
0x180008c5a  mov     rcx, rdi; lpCriticalSection
0x180008c5d  call    cs:__imp_EnterCriticalSection
0x180008c63  or      dword ptr [rbx+40h], 300h
0x180008c6a  cmp     qword ptr [rbx+0F0h], 0
0x180008c72  jz      short loc_180008C81
0x180008c74  mov     edx, 2
0x180008c79  mov     rcx, rbx
0x180008c7c  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180008c81  test    rdi, rdi
0x180008c84  jz      short loc_180008C8F
0x180008c86  mov     rcx, rdi; lpCriticalSection
0x180008c89  call    cs:__imp_LeaveCriticalSection
0x180008c8f  lea     rax, aAomdusagetipte; "AOMDUsageTipTestCompletionReason::Expir"...
0x180008c96  mov     r8, rax
0x180008c99  mov     cl, 41h ; 'A'
0x180008c9b  inc     rax
0x180008c9e  cmp     cl, 3Ah ; ':'
0x180008ca1  jnz     short loc_180008CA6
0x180008ca3  mov     r8, rax
0x180008ca6  mov     cl, [rax]
0x180008ca8  test    cl, cl
0x180008caa  jnz     short loc_180008C9B
0x180008cac  mov     edx, 64h ; 'd'
0x180008cb1  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x180008cb6  nop
0x180008cb7  mov     rbx, [rsp+38h+arg_0]
0x180008cbc  add     rsp, 30h
0x180008cc0  pop     rdi
0x180008cc1  retn
```
