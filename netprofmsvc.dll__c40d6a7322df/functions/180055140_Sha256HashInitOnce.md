# Sha256HashInitOnce

- ea: `0x180055140`
- end: `0x180055235`
- name: `Sha256HashInitOnce`
- size: `245`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180043488`
- `0x180043e80`
- `0x180055140`
- `0x1800a88a0`
- `0x18012c220`
- `0x18012da60`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18005520b`
- `ntdll!RtlNtStatusToDosError` at `0x18005520b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055213`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055213`
- `bcrypt!BCryptGetProperty` at `0x1800551e4`
- `bcrypt!BCryptGetProperty` at `0x1800551e4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18005519c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18005519c`

## string_xrefs

- `0x1800551fa`: `onecore\net\netprofiles\service\src\common\sha256hash.cpp`

## pseudocode

```c
__int64 __fastcall Sha256HashInitOnce(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  wil::details *v3; // rbx
  void *v4; // rdx
  NTSTATUS Property; // eax
  NTSTATUS v6; // ebx
  __int64 v7; // rdx
  ULONG v8; // eax
  int pcbResult; // [rsp+20h] [rbp-28h]
  ULONG v11; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v3 = (wil::details *)hObject;
  if ( hObject )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
    wil::details::BCryptCloseAlgorithmProviderNoFlags(v3, v4);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
  }
  hObject = 0;
  Property = BCryptOpenAlgorithmProvider(&hObject, L"SHA256", 0, 0);
  v6 = Property;
  if ( Property < 0 )
  {
    v7 = 42;
LABEL_7:
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\common\\sha256hash.cpp",
      (const char *)(unsigned int)Property,
      pcbResult);
    v8 = RtlNtStatusToDosError(v6);
    SetLastError(v8);
    return 0;
  }
  v11 = 0;
  Property = BCryptGetProperty(hObject, L"ObjectLength", (PUCHAR)&Size, 4u, &v11, 0);
  v6 = Property;
  if ( Property < 0 )
  {
    v7 = 48;
    goto LABEL_7;
  }
  return 1;
}

```

## disassembly

```asm
0x180055140  push    rbx
0x180055142  sub     rsp, 40h
0x180055146  mov     rax, cs:__security_cookie
0x18005514d  xor     rax, rsp
0x180055150  mov     [rsp+48h+var_10], rax
0x180055155  mov     rbx, cs:hObject
0x18005515c  test    rbx, rbx
0x18005515f  jz      short loc_18005517D
0x180055161  lea     rcx, [rsp+48h+var_18]; this
0x180055166  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005516b  mov     rcx, rbx; this
0x18005516e  call    ?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAXPEAX@Z; wil::details::BCryptCloseAlgorithmProviderNoFlags(void *)
0x180055173  lea     rcx, [rsp+48h+var_18]; this
0x180055178  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005517d  xor     r9d, r9d; dwFlags
0x180055180  mov     cs:hObject, 0
0x18005518b  xor     r8d, r8d; pszImplementation
0x18005518e  lea     rdx, pszAlgId; "SHA256"
0x180055195  lea     rcx, hObject; phAlgorithm
0x18005519c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800551a2  mov     ebx, eax
0x1800551a4  test    eax, eax
0x1800551a6  jns     short loc_1800551AF
0x1800551a8  mov     edx, 2Ah ; '*'
0x1800551ad  jmp     short loc_1800551F5
0x1800551af  mov     rcx, cs:hObject; hObject
0x1800551b6  lea     rax, [rsp+48h+var_18]
0x1800551bb  mov     [rsp+48h+dwFlags], 0; dwFlags
0x1800551c3  lea     r8, Size; pbOutput
0x1800551ca  mov     r9d, 4; cbOutput
0x1800551d0  mov     [rsp+48h+pcbResult], rax; int
0x1800551d5  lea     rdx, pszProperty; "ObjectLength"
0x1800551dc  mov     [rsp+48h+var_18], 0
0x1800551e4  call    cs:__imp_BCryptGetProperty
0x1800551ea  mov     ebx, eax
0x1800551ec  test    eax, eax
0x1800551ee  jns     short loc_18005521D
0x1800551f0  mov     edx, 30h ; '0'; void *
0x1800551f5  mov     rcx, [rsp+48h]; this
0x1800551fa  lea     r8, aOnecoreNetNetp_37; "onecore\\net\\netprofiles\\service\\src"...
0x180055201  mov     r9d, eax; char *
0x180055204  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180055209  mov     ecx, ebx; Status
0x18005520b  call    cs:__imp_RtlNtStatusToDosError
0x180055211  mov     ecx, eax; dwErrCode
0x180055213  call    cs:__imp_SetLastError
0x180055219  xor     eax, eax
0x18005521b  jmp     short loc_180055222
0x18005521d  mov     eax, 1
0x180055222  mov     rcx, [rsp+48h+var_10]
0x180055227  xor     rcx, rsp; StackCookie
0x18005522a  call    __security_check_cookie
0x18005522f  add     rsp, 40h
0x180055233  pop     rbx
0x180055234  retn
```
