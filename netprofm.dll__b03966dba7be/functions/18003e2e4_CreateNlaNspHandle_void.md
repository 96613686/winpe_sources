# CreateNlaNspHandle(void)

- ea: `0x18003e2e4`
- end: `0x18003e3b6`
- name: `?CreateNlaNspHandle@@YAPEAXXZ`
- size: `210`
- prototype: `HANDLE(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003e3bc`

## callees

- `0x1800120d0`
- `0x180012f40`
- `0x18002a3e4`
- `0x18003e2e4`

## import_xrefs

- `WS2_32!WSALookupServiceBeginW` at `0x18003e373`
- `WS2_32!WSALookupServiceBeginW` at `0x18003e373`
- `WS2_32!__imp_WSAGetLastError` at `0x18003e37e`
- `WS2_32!__imp_WSAGetLastError` at `0x18003e37e`

## string_xrefs

- `0x18003e388`: `onecore\net\netprofiles\service\src\netshnlmplugin\nlansp.cpp`

## pseudocode

```c
HANDLE CreateNlaNspHandle(void)
{
  unsigned int Error; // eax
  HANDLE hLookup; // [rsp+20h] [rbp-59h] BYREF
  _WSAQuerySetW qsRestrictions; // [rsp+30h] [rbp-49h] BYREF
  _DWORD v4[4]; // [rsp+B0h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v4[0] = 3663125;
  v4[1] = 1245951433;
  v4[2] = 1217125050;
  v4[3] = 970095272;
  memset_0(&qsRestrictions, 0, sizeof(qsRestrictions));
  qsRestrictions.dwSize = 120;
  qsRestrictions.lpServiceClassId = (LPGUID)v4;
  qsRestrictions.dwNameSpace = 15;
  qsRestrictions.lpszServiceInstanceName = 0;
  qsRestrictions.lpVersion = 0;
  qsRestrictions.lpafpProtocols = 0;
  qsRestrictions.lpszQueryString = 0;
  qsRestrictions.lpBlob = 0;
  hLookup = 0;
  memset(&qsRestrictions.lpNSProviderId, 0, 20);
  if ( WSALookupServiceBeginW(&qsRestrictions, 0xFF1u, &hLookup) == -1 )
  {
    Error = WSAGetLastError();
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x44,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\nlansp.cpp",
      (const char *)Error,
      (unsigned int)hLookup);
  }
  return hLookup;
}

```

## disassembly

```asm
0x18003e2e4  push    rbp
0x18003e2e6  lea     rbp, [rsp-57h]
0x18003e2eb  sub     rsp, 0D0h
0x18003e2f2  mov     rax, cs:__security_cookie
0x18003e2f9  xor     rax, rsp
0x18003e2fc  mov     [rbp+57h+var_10], rax
0x18003e300  xor     edx, edx; Val
0x18003e302  mov     [rbp+57h+var_20], 37E515h
0x18003e309  lea     rcx, [rbp+57h+qsRestrictions]; void *
0x18003e30d  mov     [rbp+57h+var_1C], 4A43B5C9h
0x18003e314  mov     [rbp+57h+var_18], 488BDABAh
0x18003e31b  mov     [rbp+57h+var_14], 39D27AA8h
0x18003e322  lea     r8d, [rdx+78h]; Size
0x18003e326  call    memset_0
0x18003e32b  lea     rax, [rbp+57h+var_20]
0x18003e32f  mov     [rbp+57h+qsRestrictions.dwSize], 78h ; 'x'
0x18003e336  mov     [rbp+57h+qsRestrictions.lpServiceClassId], rax
0x18003e33a  lea     r8, [rbp+57h+hLookup]; lphLookup
0x18003e33e  xor     eax, eax
0x18003e340  mov     [rbp+57h+qsRestrictions.dwNameSpace], 0Fh
0x18003e347  xorps   xmm0, xmm0
0x18003e34a  mov     [rbp+57h+qsRestrictions.dwNumberOfProtocols], eax
0x18003e34d  mov     edx, 0FF1h; dwControlFlags
0x18003e352  mov     [rbp+57h+qsRestrictions.lpszServiceInstanceName], rax
0x18003e356  lea     rcx, [rbp+57h+qsRestrictions]; lpqsRestrictions
0x18003e35a  mov     [rbp+57h+qsRestrictions.lpVersion], rax
0x18003e35e  mov     [rbp+57h+qsRestrictions.lpafpProtocols], rax
0x18003e362  mov     [rbp+57h+qsRestrictions.lpszQueryString], rax
0x18003e366  mov     [rbp+57h+qsRestrictions.lpBlob], rax
0x18003e36a  mov     [rbp+57h+hLookup], rax
0x18003e36e  movdqa  xmmword ptr [rbp+57h+qsRestrictions.lpNSProviderId], xmm0
0x18003e373  call    cs:__imp_WSALookupServiceBeginW
0x18003e379  cmp     eax, 0FFFFFFFFh
0x18003e37c  jnz     short loc_18003E39D
0x18003e37e  call    cs:__imp_WSAGetLastError
0x18003e384  mov     rcx, [rbp+5Fh]; this
0x18003e388  lea     r8, aOnecoreNetNetp_8; "onecore\\net\\netprofiles\\service\\src"...
0x18003e38f  mov     r9d, eax; char *
0x18003e392  mov     edx, 44h ; 'D'; void *
0x18003e397  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003e39d  mov     rax, [rbp+57h+hLookup]
0x18003e3a1  mov     rcx, [rbp+57h+var_10]
0x18003e3a5  xor     rcx, rsp; StackCookie
0x18003e3a8  call    __security_check_cookie
0x18003e3ad  add     rsp, 0D0h
0x18003e3b4  pop     rbp
0x18003e3b5  retn
```
