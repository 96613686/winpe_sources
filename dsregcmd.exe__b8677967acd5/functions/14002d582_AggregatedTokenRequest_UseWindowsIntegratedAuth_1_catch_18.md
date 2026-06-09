# _AggregatedTokenRequest::UseWindowsIntegratedAuth_::_1_::catch$18

- ea: `0x14002d582`
- end: `0x14002d601`
- name: `_AggregatedTokenRequest::UseWindowsIntegratedAuth_::_1_::catch$18`
- size: `127`
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
- `0x14002d582`

## string_xrefs

- `0x14002d596`: `onecore\ds\security\dsreg\win32\adal.native\aggregatedtokenrequest.cpp`

## pseudocode

```c
void __fastcall __noreturn AggregatedTokenRequest::UseWindowsIntegratedAuth_::_1_::catch_18(__int64 a1, __int64 a2)
{
  FailedTokenRequest *v3; // rax
  __int64 v4; // rbx
  __int64 *v5; // rax

  v3 = (FailedTokenRequest *)operator new(
                               0x38u,
                               1,
                               "onecore\\ds\\security\\dsreg\\win32\\adal.native\\aggregatedtokenrequest.cpp");
  *(_QWORD *)(a2 + 264) = v3;
  v4 = *(_QWORD *)(a2 + 240);
  if ( v3 )
    v3 = FailedTokenRequest::FailedTokenRequest(
           v3,
           *(const struct TokenRequest **)(a2 + 240),
           *(const struct Exception **)(a2 + 128));
  v5 = std::unique_ptr<TokenRequest>::unique_ptr<TokenRequest>((_QWORD *)(a2 + 256), (__int64)v3);
  std::unique_ptr<TokenRequest>::operator=<std::default_delete<TokenRequest>,0>((__int64 *)(v4 + 32), v5);
  std::unique_ptr<TokenRequest>::~unique_ptr<TokenRequest>((__int64 *)(a2 + 256));
  throw;
}

```

## disassembly

```asm
0x14002d582  mov     [rsp+arg_8], rdx
0x14002d587  push    rbx
0x14002d588  push    rbp
0x14002d589  sub     rsp, 38h
0x14002d58d  mov     rbp, rdx
0x14002d590  mov     r9d, 0B8h; int
0x14002d596  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002d59d  mov     edx, 1; int
0x14002d5a2  lea     ecx, [rdx+37h]; unsigned __int64
0x14002d5a5  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x14002d5aa  mov     [rbp+108h], rax
0x14002d5b1  mov     rbx, [rbp+0F0h]
0x14002d5b8  test    rax, rax
0x14002d5bb  jz      short loc_14002D5D0
0x14002d5bd  mov     r8, [rbp+80h]; struct Exception *
0x14002d5c4  mov     rdx, rbx; struct TokenRequest *
0x14002d5c7  mov     rcx, rax; this
0x14002d5ca  call    ??0FailedTokenRequest@@QEAA@PEBVTokenRequest@@AEBVException@@@Z; FailedTokenRequest::FailedTokenRequest(TokenRequest const *,Exception const &)
0x14002d5cf  nop
0x14002d5d0  mov     rdx, rax
0x14002d5d3  lea     rcx, [rbp+100h]
0x14002d5da  call    ??$?0U?$default_delete@VTokenRequest@@@std@@$0A@@?$unique_ptr@VTokenRequest@@U?$default_delete@VTokenRequest@@@std@@@std@@QEAA@PEAVTokenRequest@@@Z; std::unique_ptr<TokenRequest>::unique_ptr<TokenRequest>(TokenRequest *)
0x14002d5df  lea     rcx, [rbx+20h]
0x14002d5e3  mov     rdx, rax
0x14002d5e6  call    ??$?4U?$default_delete@VTokenRequest@@@std@@$0A@@?$unique_ptr@VTokenRequest@@U?$default_delete@VTokenRequest@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<TokenRequest>::operator=<std::default_delete<TokenRequest>,0>(std::unique_ptr<TokenRequest> &&)
0x14002d5eb  lea     rcx, [rbp+100h]
0x14002d5f2  call    ??1?$unique_ptr@VTokenRequest@@U?$default_delete@VTokenRequest@@@std@@@std@@QEAA@XZ; std::unique_ptr<TokenRequest>::~unique_ptr<TokenRequest>(void)
0x14002d5f7  xor     edx, edx; pThrowInfo
0x14002d5f9  xor     ecx, ecx; pExceptionObject
0x14002d5fb  call    _CxxThrowException_0
```
