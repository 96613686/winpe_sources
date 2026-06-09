# OAuthTokenRequestBase::GetErrorCodeForOAuthError(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x140014988`
- end: `0x140014ae5`
- name: `?GetErrorCodeForOAuthError@OAuthTokenRequestBase@@KAKAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `349`
- prototype: `__int64 __fastcall(const wchar_t **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140014ea4`

## callees

- `0x140014988`
- `0x14002c3d0`

## string_xrefs

- `0x140014991`: `access_denied`
- `0x140014a76`: `temporarily_unavailable`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OAuthTokenRequestBase::GetErrorCodeForOAuthError(const wchar_t **a1)
{
  const wchar_t *v1; // rbx

  v1 = *a1;
  if ( !wcscmp_0(*a1, L"access_denied") )
    return 3399614468LL;
  if ( !wcscmp_0(v1, L"interaction_required") )
    return 3399614476LL;
  if ( !wcscmp_0(v1, L"invalid_client") )
    return 3399614473LL;
  if ( !wcscmp_0(v1, L"invalid_grant") )
    return 3399614467LL;
  if ( !wcscmp_0(v1, L"invalid_request") )
    return 3399614466LL;
  if ( !wcscmp_0(v1, L"invalid_resource") )
    return 3399614475LL;
  if ( !wcscmp_0(v1, L"invalid_scope") )
    return 3399614471LL;
  if ( !wcscmp_0(v1, L"server_error") )
    return 3399614472LL;
  if ( !wcscmp_0(v1, L"temporarily_unavailable") )
    return 3399614469LL;
  if ( !wcscmp_0(v1, L"unauthorized_client") )
    return 3399614465LL;
  if ( !wcscmp_0(v1, L"unsupported_grant_type") )
    return 3399614474LL;
  return wcscmp_0(v1, L"unsupported_response_type") != 0 ? -895352732 : -895352826;
}

```

## disassembly

```asm
0x140014988  push    rbx
0x14001498a  sub     rsp, 20h
0x14001498e  mov     rbx, [rcx]
0x140014991  lea     rdx, aAccessDenied; "access_denied"
0x140014998  mov     rcx, rbx; String1
0x14001499b  call    wcscmp_0
0x1400149a0  test    eax, eax
0x1400149a2  jnz     short loc_1400149AE
0x1400149a4  mov     eax, 0CAA20004h
0x1400149a9  jmp     loc_140014ADF
0x1400149ae  lea     rdx, aInteractionReq; "interaction_required"
0x1400149b5  mov     rcx, rbx; String1
0x1400149b8  call    wcscmp_0
0x1400149bd  test    eax, eax
0x1400149bf  jnz     short loc_1400149CB
0x1400149c1  mov     eax, 0CAA2000Ch
0x1400149c6  jmp     loc_140014ADF
0x1400149cb  lea     rdx, aInvalidClient; "invalid_client"
0x1400149d2  mov     rcx, rbx; String1
0x1400149d5  call    wcscmp_0
0x1400149da  test    eax, eax
0x1400149dc  jnz     short loc_1400149E8
0x1400149de  mov     eax, 0CAA20009h
0x1400149e3  jmp     loc_140014ADF
0x1400149e8  lea     rdx, aInvalidGrant; "invalid_grant"
0x1400149ef  mov     rcx, rbx; String1
0x1400149f2  call    wcscmp_0
0x1400149f7  test    eax, eax
0x1400149f9  jnz     short loc_140014A05
0x1400149fb  mov     eax, 0CAA20003h
0x140014a00  jmp     loc_140014ADF
0x140014a05  lea     rdx, aInvalidRequest; "invalid_request"
0x140014a0c  mov     rcx, rbx; String1
0x140014a0f  call    wcscmp_0
0x140014a14  test    eax, eax
0x140014a16  jnz     short loc_140014A22
0x140014a18  mov     eax, 0CAA20002h
0x140014a1d  jmp     loc_140014ADF
0x140014a22  lea     rdx, aInvalidResourc; "invalid_resource"
0x140014a29  mov     rcx, rbx; String1
0x140014a2c  call    wcscmp_0
0x140014a31  test    eax, eax
0x140014a33  jnz     short loc_140014A3F
0x140014a35  mov     eax, 0CAA2000Bh
0x140014a3a  jmp     loc_140014ADF
0x140014a3f  lea     rdx, aInvalidScope; "invalid_scope"
0x140014a46  mov     rcx, rbx; String1
0x140014a49  call    wcscmp_0
0x140014a4e  test    eax, eax
0x140014a50  jnz     short loc_140014A5C
0x140014a52  mov     eax, 0CAA20007h
0x140014a57  jmp     loc_140014ADF
0x140014a5c  lea     rdx, aServerError; "server_error"
0x140014a63  mov     rcx, rbx; String1
0x140014a66  call    wcscmp_0
0x140014a6b  test    eax, eax
0x140014a6d  jnz     short loc_140014A76
0x140014a6f  mov     eax, 0CAA20008h
0x140014a74  jmp     short loc_140014ADF
0x140014a76  lea     rdx, aTemporarilyUna; "temporarily_unavailable"
0x140014a7d  mov     rcx, rbx; String1
0x140014a80  call    wcscmp_0
0x140014a85  test    eax, eax
0x140014a87  jnz     short loc_140014A90
0x140014a89  mov     eax, 0CAA20005h
0x140014a8e  jmp     short loc_140014ADF
0x140014a90  lea     rdx, aUnauthorizedCl; "unauthorized_client"
0x140014a97  mov     rcx, rbx; String1
0x140014a9a  call    wcscmp_0
0x140014a9f  test    eax, eax
0x140014aa1  jnz     short loc_140014AAA
0x140014aa3  mov     eax, 0CAA20001h
0x140014aa8  jmp     short loc_140014ADF
0x140014aaa  lea     rdx, aUnsupportedGra; "unsupported_grant_type"
0x140014ab1  mov     rcx, rbx; String1
0x140014ab4  call    wcscmp_0
0x140014ab9  test    eax, eax
0x140014abb  jnz     short loc_140014AC4
0x140014abd  mov     eax, 0CAA2000Ah
0x140014ac2  jmp     short loc_140014ADF
0x140014ac4  lea     rdx, aUnsupportedRes; "unsupported_response_type"
0x140014acb  mov     rcx, rbx; String1
0x140014ace  call    wcscmp_0
0x140014ad3  neg     eax
0x140014ad5  sbb     eax, eax
0x140014ad7  and     eax, 5Eh
0x140014ada  add     eax, 0CAA20006h
0x140014adf  add     rsp, 20h
0x140014ae3  pop     rbx
0x140014ae4  retn
```
