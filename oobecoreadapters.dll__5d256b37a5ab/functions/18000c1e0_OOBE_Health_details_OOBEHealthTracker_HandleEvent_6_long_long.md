# OOBE::Health::details::OOBEHealthTracker::HandleEvent<6,long>(long)

- ea: `0x18000c1e0`
- end: `0x18000c2e4`
- name: `??$HandleEvent@$05J@OOBEHealthTracker@details@Health@OOBE@@SAXJ@Z`
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
- `0x18000c1e0`
- `0x18000cc0c`
- `0x18000cc90`
- `0x18000e870`
- `0x18000ef04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c27b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c27b`

## string_xrefs

- `0x18000c20d`: `OOBECompletedForOOBEHealth`
- `0x18000c206`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompletedForOOBEHealth`
- `0x18000c269`: `AnyoneReadOOBECompleted`

## pseudocode

```c
void __fastcall OOBE::Health::details::OOBEHealthTracker::HandleEvent<6,long>(int a1)
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
      OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>(v3, (char *)&qword_1800A6D99 + 1, &v10);
      v10 = 1;
      OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>(v4, (char *)&qword_1800A6D99 + 2, &v10);
      if ( a1 < 0 )
        OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<long>(
          v5,
          (char *)&xmmword_1800A6DE0 + 4,
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
0x18000c1e0  mov     [rsp-8+arg_0], rbx
0x18000c1e5  push    rbp
0x18000c1e6  mov     rbp, rsp
0x18000c1e9  sub     rsp, 50h
0x18000c1ed  mov     ebx, ecx
0x18000c1ef  mov     [rbp+lpSubKey], 0
0x18000c1f7  xor     edx, edx
0x18000c1f9  lea     rcx, [rbp+lpSubKey]
0x18000c1fd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000c202  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x18000c206  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000c20d  lea     rcx, aOobecompletedf; "OOBECompletedForOOBEHealth"
0x18000c214  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x18000c219  mov     rcx, [rbp+8]; this
0x18000c21d  test    eax, eax
0x18000c21f  jns     short loc_18000C23A
0x18000c221  mov     r9d, eax; char *
0x18000c224  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x18000c22b  mov     edx, 4D4h; void *
0x18000c230  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000c235  jmp     loc_18000C2D0
0x18000c23a  mov     [rbp+arg_10], 0
0x18000c241  mov     [rbp+arg_18], 4
0x18000c248  lea     rax, [rbp+arg_18]
0x18000c24c  mov     [rsp+50h+pcbData], rax; pcbData
0x18000c251  lea     rax, [rbp+arg_10]
0x18000c255  mov     [rsp+50h+pvData], rax; pvData
0x18000c25a  mov     [rsp+50h+pdwType], 0; pdwType
0x18000c263  mov     r9d, 20000010h; dwFlags
0x18000c269  lea     r8, Value; "AnyoneReadOOBECompleted"
0x18000c270  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18000c274  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000c27b  call    cs:__imp_RegGetValueW
0x18000c281  cmp     [rbp+arg_10], 0
0x18000c285  jnz     short loc_18000C2D0
0x18000c287  mov     [rbp+var_10], ebx
0x18000c28a  mov     eax, ebx
0x18000c28c  shr     eax, 1Fh
0x18000c28f  mov     [rbp+arg_8], al
0x18000c292  lea     r8, [rbp+arg_8]
0x18000c296  lea     rdx, qword_1800A6D99+1
0x18000c29d  call    ??$SetHealthEventValueMember@_N@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEA_NAEB_N@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>(bool &,bool const &)
0x18000c2a2  mov     [rbp+arg_8], 1
0x18000c2a6  lea     r8, [rbp+arg_8]
0x18000c2aa  lea     rdx, qword_1800A6D99+2
0x18000c2b1  call    ??$SetHealthEventValueMember@_N@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEA_NAEB_N@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<bool>(bool &,bool const &)
0x18000c2b6  test    ebx, ebx
0x18000c2b8  jns     short loc_18000C2CA
0x18000c2ba  lea     r8, [rbp+var_10]
0x18000c2be  lea     rdx, xmmword_1800A6DE0+4
0x18000c2c5  call    ??$SetHealthEventValueMember@J@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAJAEBJ@Z; OOBE::Health::details::OOBEScenarioEvents::SetHealthEventValueMember<long>(long &,long const &)
0x18000c2ca  call    ?Evaluate@OOBEScenarioEvents@details@Health@OOBE@@AEAAJXZ; OOBE::Health::details::OOBEScenarioEvents::Evaluate(void)
0x18000c2cf  nop
0x18000c2d0  lea     rcx, [rbp+lpSubKey]
0x18000c2d4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000c2d9  mov     rbx, [rsp+50h+arg_0]
0x18000c2de  add     rsp, 50h
0x18000c2e2  pop     rbp
0x18000c2e3  retn
```
