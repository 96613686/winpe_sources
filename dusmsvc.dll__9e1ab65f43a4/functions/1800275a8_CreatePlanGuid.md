# CreatePlanGuid

- ea: `0x1800275a8`
- end: `0x1800276c0`
- name: `CreatePlanGuid`
- size: `280`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002bdf4`

## callees

- `0x180007c90`
- `0x180017cec`
- `0x18001d87c`
- `0x1800275a8`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x180027615`
- `RPCRT4!UuidToStringW` at `0x180027615`
- `RPCRT4!UuidCreate` at `0x1800275ff`
- `RPCRT4!UuidCreate` at `0x1800275ff`
- `RPCRT4!RpcStringFreeW` at `0x18002764f`
- `RPCRT4!RpcStringFreeW` at `0x18002764f`

## string_xrefs

- `0x18002769f`: `CreatePlanGuid::UuidCreate`
- `0x18002767a`: `CreatePlanGuid::UuidToString`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CreatePlanGuid(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // eax
  __int64 v4; // r8
  const char *v6; // [rsp+28h] [rbp-48h]
  RPC_WSTR StringUuid; // [rsp+50h] [rbp-20h] BYREF
  UUID Uuid; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  Uuid = 0;
  StringUuid = 0;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  v2 = UuidCreate(&Uuid);
  if ( v2 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0xB0,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)v2,
      (unsigned int)"CreatePlanGuid::UuidCreate",
      v6);
  v3 = UuidToStringW(&Uuid, &StringUuid);
  if ( v3 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)v3,
      (unsigned int)"CreatePlanGuid::UuidToString",
      v6);
  if ( StringUuid )
  {
    v4 = -1;
    do
      ++v4;
    while ( StringUuid[v4] );
    std::wstring::_Assign<wchar_t>(a1, StringUuid, v4);
  }
  RpcStringFreeW(&StringUuid);
  return a1;
}

```

## disassembly

```asm
0x1800275a8  mov     [rsp-8+arg_8], rbx
0x1800275ad  mov     [rsp-8+arg_10], rdi
0x1800275b2  push    rbp
0x1800275b3  mov     rbp, rsp
0x1800275b6  sub     rsp, 70h
0x1800275ba  mov     rax, cs:__security_cookie
0x1800275c1  xor     rax, rsp
0x1800275c4  mov     [rbp+var_8], rax
0x1800275c8  mov     rbx, rcx
0x1800275cb  mov     [rbp+var_38], rcx
0x1800275cf  xor     edi, edi
0x1800275d1  mov     [rbp+var_40], edi
0x1800275d4  xorps   xmm0, xmm0
0x1800275d7  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x1800275db  mov     [rbp+StringUuid], rdi
0x1800275df  xorps   xmm1, xmm1
0x1800275e2  movups  xmmword ptr [rcx], xmm1
0x1800275e5  mov     [rcx+10h], rdi
0x1800275e9  mov     qword ptr [rcx+18h], 7
0x1800275f1  mov     [rcx], di
0x1800275f4  mov     [rbp+var_40], 1
0x1800275fb  lea     rcx, [rbp+Uuid]; Uuid
0x1800275ff  call    cs:__imp_UuidCreate
0x180027605  test    eax, eax
0x180027607  jnz     loc_18002769B
0x18002760d  lea     rdx, [rbp+StringUuid]; StringUuid
0x180027611  lea     rcx, [rbp+Uuid]; Uuid
0x180027615  call    cs:__imp_UuidToStringW
0x18002761b  test    eax, eax
0x18002761d  jnz     short loc_180027676
0x18002761f  lea     rax, [rbp+StringUuid]
0x180027623  mov     [rbp+var_30], rax
0x180027627  mov     [rbp+var_28], 1
0x18002762b  mov     rdx, [rbp+StringUuid]
0x18002762f  test    rdx, rdx
0x180027632  jz      short loc_18002764B
0x180027634  or      r8, 0FFFFFFFFFFFFFFFFh
0x180027638  inc     r8
0x18002763b  cmp     [rdx+r8*2], di
0x180027640  jnz     short loc_180027638
0x180027642  mov     rcx, rbx
0x180027645  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18002764a  nop
0x18002764b  lea     rcx, [rbp+StringUuid]; String
0x18002764f  call    cs:__imp_RpcStringFreeW
0x180027655  mov     rax, rbx
0x180027658  mov     rcx, [rbp+var_8]
0x18002765c  xor     rcx, rsp; StackCookie
0x18002765f  call    __security_check_cookie
0x180027664  lea     r11, [rsp+70h+var_s0]
0x180027669  mov     rbx, [r11+18h]
0x18002766d  mov     rdi, [r11+20h]
0x180027671  mov     rsp, r11
0x180027674  pop     rbp
0x180027675  retn
0x180027676  mov     rcx, [rbp+8]; this
0x18002767a  lea     rdx, aCreateplanguid_0; "CreatePlanGuid::UuidToString"
0x180027681  mov     qword ptr [rsp+70h+var_50], rdx; unsigned int
0x180027686  mov     r9d, eax; char *
0x180027689  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x180027690  mov     edx, 0B7h; void *
0x180027695  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002769b  mov     rcx, [rbp+8]; this
0x18002769f  lea     rdx, aCreateplanguid; "CreatePlanGuid::UuidCreate"
0x1800276a6  mov     qword ptr [rsp+70h+var_50], rdx; unsigned int
0x1800276ab  mov     r9d, eax; char *
0x1800276ae  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x1800276b5  mov     edx, 0B0h; void *
0x1800276ba  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
