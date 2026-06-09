# OAuthResponse::ParseIdTokenResponse(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x140025110`
- end: `0x1400251cd`
- name: `?ParseIdTokenResponse@OAuthResponse@@AEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400251d4`

## callees

- `0x140001814`
- `0x14000e328`
- `0x14000e548`
- `0x140024e48`
- `0x140025110`

## string_xrefs

- `0x14002513a`: `onecore\ds\security\dsreg\win32\adal.native\oauthtokenresponse.cpp`
- `0x140025188`: `onecore\ds\security\dsreg\win32\adal.native\oauthtokenresponse.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OAuthResponse::ParseIdTokenResponse(__int64 a1, const wchar_t **a2)
{
  __int64 v3; // rdi
  __int64 result; // rax
  IdToken *v5; // rbx
  IdToken *v6; // rax
  IdToken *v7; // rax
  IdToken *v8; // rax

  try
  {
    v3 = a1;
    result = (__int64)*a2;
    v5 = 0;
    if ( *((_DWORD *)*a2 - 4) )
    {
      v6 = (IdToken *)operator new(0x50u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\oauthtokenresponse.cpp");
      if ( v6 )
        v7 = IdToken::IdToken(v6, a2);
      else
        v7 = 0;
      result = std::shared_ptr<IdToken>::reset<IdToken,0>((_QWORD *)(v3 + 112), (__int64)v7);
    }
  }
  catch ( IdToken::IdTokenParseException )
  {
    result = Log::WarnInternal(a1, 3399876620LL, 0);
    v5 = 0;
    v3 = a1;
  }
  if ( !*(_QWORD *)(v3 + 112) )
  {
    v8 = (IdToken *)operator new(0x50u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\oauthtokenresponse.cpp");
    if ( v8 )
      v5 = IdToken::IdToken(v8);
    return std::shared_ptr<IdToken>::reset<IdToken,0>((_QWORD *)(v3 + 112), (__int64)v5);
  }
  return result;
}

```

## disassembly

```asm
0x140025110  mov     [rsp+arg_10], rbx
0x140025115  mov     [rsp+arg_18], rsi
0x14002511a  mov     [rsp+arg_0], rcx
0x14002511f  push    rdi
0x140025120  sub     rsp, 20h
0x140025124  mov     rsi, rdx
0x140025127  mov     rdi, rcx
0x14002512a  mov     rax, [rdx]
0x14002512d  xor     ebx, ebx
0x14002512f  cmp     [rax-10h], ebx
0x140025132  jz      short loc_140025173
0x140025134  mov     r9d, 95h; int
0x14002513a  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x140025141  lea     edx, [rbx+1]; int
0x140025144  lea     ecx, [rbx+50h]; unsigned __int64
0x140025147  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x14002514c  mov     [rsp+28h+arg_8], rax
0x140025151  test    rax, rax
0x140025154  jz      short loc_140025163
0x140025156  mov     rdx, rsi
0x140025159  mov     rcx, rax; this
0x14002515c  call    ??0IdToken@@QEAA@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; IdToken::IdToken(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140025161  jmp     short loc_140025166
0x140025163  mov     rax, rbx
0x140025166  lea     rcx, [rdi+70h]
0x14002516a  mov     rdx, rax
0x14002516d  call    ??$reset@VIdToken@@$0A@@?$shared_ptr@VIdToken@@@std@@QEAAXPEAVIdToken@@@Z; std::shared_ptr<IdToken>::reset<IdToken,0>(IdToken *)
0x140025172  nop
0x140025173  jmp     short loc_14002517C
0x140025175  xor     ebx, ebx
0x140025177  mov     rdi, [rsp+28h+arg_0]
0x14002517c  cmp     [rdi+70h], rbx
0x140025180  jnz     short loc_1400251BD
0x140025182  mov     r9d, 0A1h; int
0x140025188  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002518f  mov     edx, 1; int
0x140025194  lea     ecx, [rdx+4Fh]; unsigned __int64
0x140025197  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x14002519c  mov     [rsp+28h+arg_0], rax
0x1400251a1  test    rax, rax
0x1400251a4  jz      short loc_1400251B1
0x1400251a6  mov     rcx, rax; this
0x1400251a9  call    ??0IdToken@@QEAA@XZ; IdToken::IdToken(void)
0x1400251ae  mov     rbx, rax
0x1400251b1  mov     rdx, rbx
0x1400251b4  lea     rcx, [rdi+70h]
0x1400251b8  call    ??$reset@VIdToken@@$0A@@?$shared_ptr@VIdToken@@@std@@QEAAXPEAVIdToken@@@Z; std::shared_ptr<IdToken>::reset<IdToken,0>(IdToken *)
0x1400251bd  mov     rbx, [rsp+28h+arg_10]
0x1400251c2  mov     rsi, [rsp+28h+arg_18]
0x1400251c7  add     rsp, 20h
0x1400251cb  pop     rdi
0x1400251cc  retn
```
