# CRemoteAssistanceApp::PostBadTicketToObject(ushort const *)

- ea: `0x140013b44`
- end: `0x140013c49`
- name: `?PostBadTicketToObject@CRemoteAssistanceApp@@QEAAJPEBG@Z`
- size: `261`
- prototype: `__int64 __fastcall(CRemoteAssistanceApp *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140012794`

## callees

- `0x1400044f8`
- `0x140013b44`
- `0x140034ce4`
- `0x14003500c`
- `0x14004d010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x140013b7e`
- `ole32!CoCreateInstance` at `0x140013b7e`
- `OLEAUT32!__imp_SysAllocString` at `0x140013bde`
- `OLEAUT32!__imp_SysAllocString` at `0x140013bde`
- `OLEAUT32!__imp_SysFreeString` at `0x140013c0a`
- `OLEAUT32!__imp_SysFreeString` at `0x140013c0a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRemoteAssistanceApp::PostBadTicketToObject(CRemoteAssistanceApp *this, const unsigned __int16 *a2)
{
  HRESULT Instance; // eax
  CEventLogger *v3; // rcx
  unsigned int v4; // edi
  CEventLogger *v5; // rcx
  __int64 *v6; // rsi
  __int64 v7; // rbp
  BSTR v8; // rax
  OLECHAR *v9; // rbx
  __int64 *v11; // [rsp+58h] [rbp+10h] BYREF

  v11 = 0;
  Instance = CoCreateInstance(
               &CLSID_RemoteAssistance,
               0,
               4u,
               &GUID_59308e66_7cde_478a_8eba_4d73fdce3545,
               (LPVOID *)&v11);
  v4 = Instance;
  if ( Instance >= 0 )
  {
    v6 = v11;
    v7 = *v11;
    v8 = SysAllocString(&String);
    v9 = v8;
    if ( !v8 )
      ATL::AtlThrowImpl(-2147024882);
    (*(void (__fastcall **)(__int64 *, BSTR))(v7 + 72))(v6, v8);
    SysFreeString(v9);
  }
  else
  {
    CEventLogger::LogError(
      v3,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\app.cpp",
      0x633u,
      L"CRemoteAssistanceApp::PostBadTicketToObject",
      Instance);
    CEventLogger::LogEvent(v5, &COM_Problem, L"69127644-2511-4df5-bc6a-26178254aa40");
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64 *))(*v11 + 16))(v11);
  return v4;
}

```

## disassembly

```asm
0x140013b44  mov     r11, rsp
0x140013b47  mov     [r11+18h], rbx
0x140013b4b  mov     [r11+10h], rdx
0x140013b4f  mov     [r11+8], rcx
0x140013b53  push    rbp
0x140013b54  push    rsi
0x140013b55  push    rdi
0x140013b56  sub     rsp, 30h
0x140013b5a  mov     qword ptr [r11+10h], 0
0x140013b62  lea     rax, [r11+10h]
0x140013b66  mov     [r11-28h], rax
0x140013b6a  lea     r9, _GUID_59308e66_7cde_478a_8eba_4d73fdce3545; riid
0x140013b71  xor     edx, edx; pUnkOuter
0x140013b73  lea     r8d, [rdx+4]; dwClsContext
0x140013b77  lea     rcx, CLSID_RemoteAssistance; rclsid
0x140013b7e  call    cs:__imp_CoCreateInstance
0x140013b85  nop     dword ptr [rax+rax+00h]
0x140013b8a  mov     edi, eax
0x140013b8c  test    eax, eax
0x140013b8e  jns     short loc_140013BCF
0x140013b90  mov     [rsp+48h+var_20], eax; unsigned int
0x140013b94  lea     rax, aCremoteassista; "CRemoteAssistanceApp::PostBadTicketToOb"...
0x140013b9b  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x140013ba0  mov     r9d, 633h; unsigned int
0x140013ba6  lea     r8, aBaseDiagnosisR_14; "base\\diagnosis\\ra\\ui\\app.cpp"
0x140013bad  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140013bb4  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140013bb9  lea     r8, a6912764425114d; "69127644-2511-4df5-bc6a-26178254aa40"
0x140013bc0  lea     rdx, COM_Problem; struct _EVENT_DESCRIPTOR *
0x140013bc7  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,ushort *)
0x140013bcc  nop
0x140013bcd  jmp     short loc_140013C17
0x140013bcf  mov     rsi, [rsp+48h+arg_8]
0x140013bd4  mov     rbp, [rsi]
0x140013bd7  lea     rcx, String; psz
0x140013bde  call    cs:__imp_SysAllocString
0x140013be5  nop     dword ptr [rax+rax+00h]
0x140013bea  mov     rbx, rax
0x140013bed  mov     [rsp+48h+arg_0], rax
0x140013bf2  test    rax, rax
0x140013bf5  jz      short loc_140013C3E
0x140013bf7  mov     rdx, rax
0x140013bfa  mov     rcx, rsi
0x140013bfd  mov     rax, [rbp+48h]
0x140013c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013c06  nop
0x140013c07  mov     rcx, rbx; bstrString
0x140013c0a  call    cs:__imp_SysFreeString
0x140013c11  nop     dword ptr [rax+rax+00h]
0x140013c16  nop
0x140013c17  mov     rcx, [rsp+48h+arg_8]
0x140013c1c  test    rcx, rcx
0x140013c1f  jz      short loc_140013C2E
0x140013c21  mov     rax, [rcx]
0x140013c24  mov     rax, [rax+10h]
0x140013c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013c2d  nop
0x140013c2e  mov     eax, edi
0x140013c30  mov     rbx, [rsp+48h+arg_10]
0x140013c35  add     rsp, 30h
0x140013c39  pop     rdi
0x140013c3a  pop     rsi
0x140013c3b  pop     rbp
0x140013c3c  retn
0x140013c3e  mov     ecx, 8007000Eh; int
0x140013c43  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
