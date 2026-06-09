# Windows::Compat::Ids::IdsOneSettings::ParseEvent(void *)

- ea: `0x1800d5898`
- end: `0x1800d5ac0`
- name: `?ParseEvent@IdsOneSettings@Ids@Compat@Windows@@AEAAJPEAX@Z`
- size: `552`
- prototype: `__int64 __fastcall(Windows::Compat::Ids::IdsOneSettings *__hidden this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d5ac8`

## callees

- `0x180012920`
- `0x18008cd3c`
- `0x1800bbf0c`
- `0x1800d5898`
- `0x1800f1f10`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d593b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d59e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5a16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5a25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5a47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5a56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d593b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d59e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5a16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5a25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5a47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5a56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d58d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d596e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5a89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5a9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d58d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d596e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5a89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5a9b`

## string_xrefs

- `0x1800d5953`: `Windows::Compat::Ids::IdsOneSettings::ParseEvent`
- `0x1800d59c9`: `Windows::Compat::Ids::IdsOneSettings::ParseEvent`
- `0x1800d59fd`: `Windows::Compat::Ids::IdsOneSettings::ParseEvent`
- `0x1800d5a73`: `Windows::Compat::Ids::IdsOneSettings::ParseEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Compat::Ids::IdsOneSettings::ParseEvent(Windows::Compat::Ids::IdsEngine **this, void *a2)
{
  __int64 (__fastcall *v4)(void *, __int64, HSTRING *); // rbx
  int v5; // ebx
  const char *v6; // r9
  int v7; // r8d
  __int64 (__fastcall *v8)(void *, __int64, HSTRING *); // rbx
  Windows::Compat::Ids::IdsEngine *v9; // rdi
  unsigned __int16 *StringRawBuffer; // rbx
  unsigned __int16 *v11; // rax
  HSTRING v13; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  struct Windows::Compat::Ids::IdsEvent *v15; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v17; // [rsp+60h] [rbp-10h]

  string = 0;
  v13 = 0;
  v4 = *(__int64 (__fastcall **)(void *, __int64, HSTRING *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v17 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Type", 5u, 4u);
  v5 = v4(a2, v17, &string);
  if ( v5 < 0 )
  {
    v6 = "Failed to get the event type [%x]";
    v7 = 76;
LABEL_5:
    AslLogCallPrintf(1, (unsigned int)"Windows::Compat::Ids::IdsOneSettings::ParseEvent", v7, (_DWORD)v6);
    goto LABEL_9;
  }
  WindowsGetStringRawBuffer(string, 0);
  AslLogCallPrintf(
    3,
    (unsigned int)"Windows::Compat::Ids::IdsOneSettings::ParseEvent",
    79,
    (unsigned int)"Got event type [%ws]");
  v8 = *(__int64 (__fastcall **)(void *, __int64, HSTRING *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(v13);
  v13 = 0;
  v17 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"DATA", 5u, 4u);
  v5 = v8(a2, v17, &v13);
  if ( v5 < 0 )
  {
    v6 = "Failed to get the event data [%x]";
    v7 = 84;
    goto LABEL_5;
  }
  WindowsGetStringRawBuffer(v13, 0);
  AslLogCallPrintf(
    3,
    (unsigned int)"Windows::Compat::Ids::IdsOneSettings::ParseEvent",
    87,
    (unsigned int)"Got event data [%ws]");
  v9 = *this;
  StringRawBuffer = (unsigned __int16 *)WindowsGetStringRawBuffer(v13, 0);
  v11 = (unsigned __int16 *)WindowsGetStringRawBuffer(string, 0);
  if ( Windows::Compat::Ids::IdsEngine::GetEvent(v9, v11, StringRawBuffer, &v15) )
  {
    WindowsGetStringRawBuffer(v13, 0);
    WindowsGetStringRawBuffer(string, 0);
    AslLogCallPrintf(
      3,
      (unsigned int)"Windows::Compat::Ids::IdsOneSettings::ParseEvent",
      92,
      (unsigned int)"Failed to get event for [%ws], [%ws]");
  }
  v5 = 0;
LABEL_9:
  WindowsDeleteString(v13);
  v13 = 0;
  WindowsDeleteString(string);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800d5898  mov     [rsp-18h+arg_10], rbx
0x1800d589d  push    rbp
0x1800d589e  push    rdi
0x1800d589f  push    r14
0x1800d58a1  mov     rbp, rsp
0x1800d58a4  sub     rsp, 70h
0x1800d58a8  mov     rax, cs:__security_cookie
0x1800d58af  xor     rax, rsp
0x1800d58b2  mov     [rbp+var_8], rax
0x1800d58b6  mov     rdi, rdx
0x1800d58b9  mov     r14, rcx
0x1800d58bc  mov     [rbp+string], 0
0x1800d58c4  mov     [rbp+var_40], 0
0x1800d58cc  mov     rax, [rdx]
0x1800d58cf  mov     rbx, [rax+50h]
0x1800d58d3  xor     ecx, ecx; string
0x1800d58d5  call    cs:__imp_WindowsDeleteString
0x1800d58db  mov     [rbp+string], 0
0x1800d58e3  mov     [rbp+var_10], 0
0x1800d58eb  mov     r9d, 4; unsigned int
0x1800d58f1  lea     r8d, [r9+1]; unsigned int
0x1800d58f5  lea     rdx, aType_0; "Type"
0x1800d58fc  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800d5900  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d5905  nop
0x1800d5906  lea     r8, [rbp+string]
0x1800d590a  mov     rdx, [rbp+var_10]
0x1800d590e  mov     rcx, rdi
0x1800d5911  mov     rax, rbx
0x1800d5914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5919  mov     ebx, eax
0x1800d591b  test    eax, eax
0x1800d591d  jns     short loc_1800D5935
0x1800d591f  mov     dword ptr [rsp+70h+var_50], eax
0x1800d5923  lea     r9, aFailedToGetThe_2; "Failed to get the event type [%x]"
0x1800d592a  mov     r8d, 4Ch ; 'L'
0x1800d5930  jmp     loc_1800D59C9
0x1800d5935  xor     edx, edx; length
0x1800d5937  mov     rcx, [rbp+string]; string
0x1800d593b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d5941  mov     [rsp+70h+var_50], rax
0x1800d5946  lea     r9, aGotEventTypeWs; "Got event type [%ws]"
0x1800d594d  mov     r8d, 4Fh ; 'O'
0x1800d5953  lea     rdx, aWindowsCompatI_55; "Windows::Compat::Ids::IdsOneSettings::P"...
0x1800d595a  lea     ecx, [r8-4Ch]
0x1800d595e  call    AslLogCallPrintf
0x1800d5963  mov     rax, [rdi]
0x1800d5966  mov     rbx, [rax+50h]
0x1800d596a  mov     rcx, [rbp+var_40]; string
0x1800d596e  call    cs:__imp_WindowsDeleteString
0x1800d5974  mov     [rbp+var_40], 0
0x1800d597c  mov     [rbp+var_10], 0
0x1800d5984  mov     r9d, 4; unsigned int
0x1800d598a  lea     r8d, [r9+1]; unsigned int
0x1800d598e  lea     rdx, aData; "DATA"
0x1800d5995  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800d5999  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d599e  nop
0x1800d599f  lea     r8, [rbp+var_40]
0x1800d59a3  mov     rdx, [rbp+var_10]
0x1800d59a7  mov     rcx, rdi
0x1800d59aa  mov     rax, rbx
0x1800d59ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d59b2  mov     ebx, eax
0x1800d59b4  test    eax, eax
0x1800d59b6  jns     short loc_1800D59DF
0x1800d59b8  mov     dword ptr [rsp+70h+var_50], eax
0x1800d59bc  lea     r9, aFailedToGetThe_28; "Failed to get the event data [%x]"
0x1800d59c3  mov     r8d, 54h ; 'T'
0x1800d59c9  lea     rdx, aWindowsCompatI_55; "Windows::Compat::Ids::IdsOneSettings::P"...
0x1800d59d0  mov     ecx, 1
0x1800d59d5  call    AslLogCallPrintf
0x1800d59da  jmp     loc_1800D5A85
0x1800d59df  xor     edx, edx; length
0x1800d59e1  mov     rcx, [rbp+var_40]; string
0x1800d59e5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d59eb  mov     [rsp+70h+var_50], rax
0x1800d59f0  lea     r9, aGotEventDataWs; "Got event data [%ws]"
0x1800d59f7  mov     r8d, 57h ; 'W'
0x1800d59fd  lea     rdx, aWindowsCompatI_55; "Windows::Compat::Ids::IdsOneSettings::P"...
0x1800d5a04  lea     ecx, [r8-54h]
0x1800d5a08  call    AslLogCallPrintf
0x1800d5a0d  mov     rdi, [r14]
0x1800d5a10  xor     edx, edx; length
0x1800d5a12  mov     rcx, [rbp+var_40]; string
0x1800d5a16  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d5a1c  mov     rbx, rax
0x1800d5a1f  xor     edx, edx; length
0x1800d5a21  mov     rcx, [rbp+string]; string
0x1800d5a25  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d5a2b  lea     r9, [rbp+var_30]; struct Windows::Compat::Ids::IdsEvent **
0x1800d5a2f  mov     r8, rbx; unsigned __int16 *
0x1800d5a32  mov     rdx, rax; unsigned __int16 *
0x1800d5a35  mov     rcx, rdi; this
0x1800d5a38  call    ?GetEvent@IdsEngine@Ids@Compat@Windows@@QEAAKPEAG0PEAPEAVIdsEvent@234@@Z; Windows::Compat::Ids::IdsEngine::GetEvent(ushort *,ushort *,Windows::Compat::Ids::IdsEvent * *)
0x1800d5a3d  test    eax, eax
0x1800d5a3f  jz      short loc_1800D5A83
0x1800d5a41  xor     edx, edx; length
0x1800d5a43  mov     rcx, [rbp+var_40]; string
0x1800d5a47  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d5a4d  mov     rbx, rax
0x1800d5a50  xor     edx, edx; length
0x1800d5a52  mov     rcx, [rbp+string]; string
0x1800d5a56  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d5a5c  mov     [rsp+70h+var_48], rbx
0x1800d5a61  mov     [rsp+70h+var_50], rax
0x1800d5a66  lea     r9, aFailedToGetEve_1; "Failed to get event for [%ws], [%ws]"
0x1800d5a6d  mov     r8d, 5Ch ; '\'
0x1800d5a73  lea     rdx, aWindowsCompatI_55; "Windows::Compat::Ids::IdsOneSettings::P"...
0x1800d5a7a  lea     ecx, [r8-59h]
0x1800d5a7e  call    AslLogCallPrintf
0x1800d5a83  xor     ebx, ebx
0x1800d5a85  mov     rcx, [rbp+var_40]; string
0x1800d5a89  call    cs:__imp_WindowsDeleteString
0x1800d5a8f  mov     [rbp+var_40], 0
0x1800d5a97  mov     rcx, [rbp+string]; string
0x1800d5a9b  call    cs:__imp_WindowsDeleteString
0x1800d5aa1  mov     eax, ebx
0x1800d5aa3  mov     rcx, [rbp+var_8]
0x1800d5aa7  xor     rcx, rsp; StackCookie
0x1800d5aaa  call    __security_check_cookie
0x1800d5aaf  mov     rbx, [rsp+70h+arg_10]
0x1800d5ab7  add     rsp, 70h
0x1800d5abb  pop     r14
0x1800d5abd  pop     rdi
0x1800d5abe  pop     rbp
0x1800d5abf  retn
```
