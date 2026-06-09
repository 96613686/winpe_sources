# OOBE::Health::details::OOBEHealthTracker::HandleEvent<4,long>(long)

- ea: `0x18000bfc8`
- end: `0x18000c0cc`
- name: `??$HandleEvent@$03J@OOBEHealthTracker@details@Health@OOBE@@SAXJ@Z`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010160`

## callees

- `0x180009814`
- `0x18000b098`
- `0x18000b200`
- `0x18000bfc8`
- `0x18000cc0c`
- `0x18000cc90`
- `0x18000e870`
- `0x18000ef04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c063`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c063`

## string_xrefs

- `0x18000bff5`: `OOBECompletedForOOBEHealth`
- `0x18000bfee`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompletedForOOBEHealth`
- `0x18000c051`: `AnyoneReadOOBECompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall OOBE::Health::details::OOBEHealthTracker::HandleEvent<4,long>(int a1)
{
  int RedirectionKeyPath; // eax
  __int64 v3; // rcx
  __int64 v4; // rcx
  OOBE::Health::details::OOBEScenarioEvents *v5; // rcx
  int pdwType; // [rsp+20h] [rbp-30h]
  int v7; // [rsp+40h] [rbp-10h] BYREF
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  bool v10; // [rsp+68h] [rbp+18h] BYREF
  int pvData; // [rsp+70h] [rbp+20h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+28h] BYREF

  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    (void **)&lpSubKey,
    0);
  RedirectionKeyPath = GetRedirectionKeyPath(
                         L"OOBECompletedForOOBEHealth",
                         L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\OOBECompletedForOOBEHealth",
                         (unsigned __int16 **)&lpSubKey);
  if ( RedirectionKeyPath >= 0 )
  {
    pvData = 0;
    pcbData = 4;
    RegGetValueW(HKEY_LOCAL_MACHINE, lpSubKey, L"AnyoneReadOOBECompleted", 0x20000010u, 0, &pvData, &pcbData);
    if ( !pvData )
    {
      v7 = a1;
      v10 = a1 < 0;
      OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>(v3, (char *)&qword_1800A6D91 + 5, &v10);
      v10 = 1;
      OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>(v4, (char *)&qword_1800A6D91 + 6, &v10);
      if ( a1 < 0 )
        OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<long>(
          v5,
          (char *)&xmmword_1800A6DD0 + 12,
          &v7);
      OOBE::Health::details::OOBEScenarioEvents::Evaluate(v5);
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4D4,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBEHealthTracker.h",
      (const char *)(unsigned int)RedirectionKeyPath,
      pdwType);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpSubKey);
}

```

## disassembly

```asm
0x18000bfc8  mov     [rsp-8+arg_0], rbx
0x18000bfcd  push    rbp
0x18000bfce  mov     rbp, rsp
0x18000bfd1  sub     rsp, 50h
0x18000bfd5  mov     ebx, ecx
0x18000bfd7  mov     [rbp+lpSubKey], 0
0x18000bfdf  xor     edx, edx
0x18000bfe1  lea     rcx, [rbp+lpSubKey]
0x18000bfe5  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000bfea  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x18000bfee  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000bff5  lea     rcx, aOobecompletedf; "OOBECompletedForOOBEHealth"
0x18000bffc  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x18000c001  mov     rcx, [rbp+8]; this
0x18000c005  test    eax, eax
0x18000c007  jns     short loc_18000C022
0x18000c009  mov     r9d, eax; char *
0x18000c00c  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x18000c013  mov     edx, 4D4h; void *
0x18000c018  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000c01d  jmp     loc_18000C0B8
0x18000c022  mov     [rbp+arg_10], 0
0x18000c029  mov     [rbp+arg_18], 4
0x18000c030  lea     rax, [rbp+arg_18]
0x18000c034  mov     [rsp+50h+pcbData], rax; pcbData
0x18000c039  lea     rax, [rbp+arg_10]
0x18000c03d  mov     [rsp+50h+pvData], rax; pvData
0x18000c042  mov     [rsp+50h+pdwType], 0; pdwType
0x18000c04b  mov     r9d, 20000010h; dwFlags
0x18000c051  lea     r8, Value; "AnyoneReadOOBECompleted"
0x18000c058  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18000c05c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000c063  call    cs:__imp_RegGetValueW
0x18000c069  cmp     [rbp+arg_10], 0
0x18000c06d  jnz     short loc_18000C0B8
0x18000c06f  mov     [rbp+var_10], ebx
0x18000c072  mov     eax, ebx
0x18000c074  shr     eax, 1Fh
0x18000c077  mov     [rbp+arg_8], al
0x18000c07a  lea     r8, [rbp+arg_8]
0x18000c07e  lea     rdx, qword_1800A6D91+5
0x18000c085  call    ??$SetHealthEventValueMember@_N@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEA_NAEB_N@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>(bool &,bool const &)
0x18000c08a  mov     [rbp+arg_8], 1
0x18000c08e  lea     r8, [rbp+arg_8]
0x18000c092  lea     rdx, qword_1800A6D91+6
0x18000c099  call    ??$SetHealthEventValueMember@_N@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEA_NAEB_N@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>(bool &,bool const &)
0x18000c09e  test    ebx, ebx
0x18000c0a0  jns     short loc_18000C0B2
0x18000c0a2  lea     r8, [rbp+var_10]
0x18000c0a6  lea     rdx, xmmword_1800A6DD0+0Ch
0x18000c0ad  call    ??$SetHealthEventValueMember@J@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAJAEBJ@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<long>(long &,long const &)
0x18000c0b2  call    ?Evaluate@OOBEScenarioEvents@details@Health@OOBE@@AEAAJXZ; OOBE::Health::details::OOBEScenarioEvents::Evaluate(void)
0x18000c0b7  nop
0x18000c0b8  lea     rcx, [rbp+lpSubKey]
0x18000c0bc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000c0c1  mov     rbx, [rsp+50h+arg_0]
0x18000c0c6  add     rsp, 50h
0x18000c0ca  pop     rbp
0x18000c0cb  retn
```
