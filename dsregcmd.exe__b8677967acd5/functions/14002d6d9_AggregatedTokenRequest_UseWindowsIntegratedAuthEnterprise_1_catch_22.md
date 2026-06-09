# _AggregatedTokenRequest::UseWindowsIntegratedAuthEnterprise_::_1_::catch$22

- ea: `0x14002d6d9`
- end: `0x14002d755`
- name: `_AggregatedTokenRequest::UseWindowsIntegratedAuthEnterprise_::_1_::catch$22`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140001814`
- `0x140005448`
- `0x140005730`
- `0x14000a1d0`
- `0x140017cb0`
- `0x14002c3e8`
- `0x14002d6d9`

## string_xrefs

- `0x14002d6ed`: `onecore\ds\security\dsreg\win32\adal.native\aggregatedtokenrequest.cpp`

## pseudocode

```c
void __fastcall __noreturn AggregatedTokenRequest::UseWindowsIntegratedAuthEnterprise_::_1_::catch_22(
        __int64 a1,
        __int64 a2)
{
  FailedTokenRequest *v3; // rax
  __int64 v4; // rbx
  __int64 *v5; // rax

  v3 = (FailedTokenRequest *)operator new(
                               0x38u,
                               1,
                               "onecore\\ds\\security\\dsreg\\win32\\adal.native\\aggregatedtokenrequest.cpp");
  *(_QWORD *)(a2 + 232) = v3;
  v4 = *(_QWORD *)(a2 + 208);
  if ( v3 )
    v3 = FailedTokenRequest::FailedTokenRequest(
           v3,
           *(const struct TokenRequest **)(a2 + 208),
           *(const struct Exception **)(a2 + 120));
  v5 = std::unique_ptr<TokenRequest>::unique_ptr<TokenRequest>((_QWORD *)(a2 + 224), (__int64)v3);
  std::unique_ptr<TokenRequest>::operator=<std::default_delete<TokenRequest>,0>((__int64 *)(v4 + 32), v5);
  std::unique_ptr<TokenRequest>::~unique_ptr<TokenRequest>((__int64 *)(a2 + 224));
  throw;
}

```

## disassembly

```asm
0x14002d6d9  mov     [rsp+arg_8], rdx
0x14002d6de  push    rbx
0x14002d6df  push    rbp
0x14002d6e0  sub     rsp, 38h
0x14002d6e4  mov     rbp, rdx
0x14002d6e7  mov     r9d, 0E2h; int
0x14002d6ed  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002d6f4  mov     edx, 1; int
0x14002d6f9  lea     ecx, [rdx+37h]; unsigned __int64
0x14002d6fc  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x14002d701  mov     [rbp+0E8h], rax
0x14002d708  mov     rbx, [rbp+0D0h]
0x14002d70f  test    rax, rax
0x14002d712  jz      short loc_14002D724
0x14002d714  mov     r8, [rbp+78h]; struct Exception *
0x14002d718  mov     rdx, rbx; struct TokenRequest *
0x14002d71b  mov     rcx, rax; this
0x14002d71e  call    ??0FailedTokenRequest@@QEAA@PEBVTokenRequest@@AEBVException@@@Z; FailedTokenRequest::FailedTokenRequest(TokenRequest const *,Exception const &)
0x14002d723  nop
0x14002d724  mov     rdx, rax
0x14002d727  lea     rcx, [rbp+0E0h]
0x14002d72e  call    ??$?0U?$default_delete@VTokenRequest@@@std@@$0A@@?$unique_ptr@VTokenRequest@@U?$default_delete@VTokenRequest@@@std@@@std@@QEAA@PEAVTokenRequest@@@Z; std::unique_ptr<TokenRequest>::unique_ptr<TokenRequest>(TokenRequest *)
0x14002d733  lea     rcx, [rbx+20h]
0x14002d737  mov     rdx, rax
0x14002d73a  call    ??$?4U?$default_delete@VTokenRequest@@@std@@$0A@@?$unique_ptr@VTokenRequest@@U?$default_delete@VTokenRequest@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<TokenRequest>::operator=<std::default_delete<TokenRequest>,0>(std::unique_ptr<TokenRequest> &&)
0x14002d73f  lea     rcx, [rbp+0E0h]
0x14002d746  call    ??1?$unique_ptr@VTokenRequest@@U?$default_delete@VTokenRequest@@@std@@@std@@QEAA@XZ; std::unique_ptr<TokenRequest>::~unique_ptr<TokenRequest>(void)
0x14002d74b  xor     edx, edx; pThrowInfo
0x14002d74d  xor     ecx, ecx; pExceptionObject
0x14002d74f  call    _CxxThrowException_0
```
