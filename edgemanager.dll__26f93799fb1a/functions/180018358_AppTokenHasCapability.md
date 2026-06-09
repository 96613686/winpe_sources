# AppTokenHasCapability

- ea: `0x180018358`
- end: `0x1800183cd`
- name: `AppTokenHasCapability`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001646c`
- `0x180017668`

## callees

- `0x180018358`
- `0x180037b5c`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001836a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001836a`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18001839f`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18001839f`

## pseudocode

```c
bool __fastcall AppTokenHasCapability(const WCHAR *a1)
{
  const char *v1; // r9
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v5; // [rsp+38h] [rbp+10h] BYREF
  PSID Sid; // [rsp+40h] [rbp+18h] BYREF

  Sid = 0;
  if ( !ConvertStringSidToSidW(a1, &Sid) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewhostprocess.cpp",
      v1);
  v5 = 0;
  if ( !(unsigned int)CheckTokenCapability(0, Sid, &v5) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x8A,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewhostprocess.cpp",
      v2);
  return v5 != 0;
}

```

## disassembly

```asm
0x180018358  sub     rsp, 28h
0x18001835c  lea     rdx, [rsp+28h+Sid]; Sid
0x180018361  mov     [rsp+28h+Sid], 0
0x18001836a  call    cs:__imp_ConvertStringSidToSidW
0x180018370  test    eax, eax
0x180018372  jnz     short loc_18001838B
0x180018374  mov     rcx, [rsp+28h]; this
0x180018379  lea     r8, aOnecoreuapInet_39; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180018380  mov     edx, 84h; void *
0x180018385  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001838b  mov     rdx, [rsp+28h+Sid]
0x180018390  lea     r8, [rsp+28h+arg_8]
0x180018395  xor     ecx, ecx
0x180018397  mov     [rsp+28h+arg_8], 0
0x18001839f  call    cs:__imp_CheckTokenCapability
0x1800183a5  test    eax, eax
0x1800183a7  jnz     short loc_1800183C0
0x1800183a9  mov     rcx, [rsp+28h]; this
0x1800183ae  lea     r8, aOnecoreuapInet_39; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800183b5  mov     edx, 8Ah; void *
0x1800183ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800183c0  cmp     [rsp+28h+arg_8], 0
0x1800183c5  setnz   al
0x1800183c8  add     rsp, 28h
0x1800183cc  retn
```
