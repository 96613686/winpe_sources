# wil::details::ScopeExitFnGuard__lambda_0bac2ce823ad4db9ffe1585967a02367___::operator()

- ea: `0x180017ebc`
- end: `0x180017f03`
- name: `wil::details::ScopeExitFnGuard__lambda_0bac2ce823ad4db9ffe1585967a02367___::operator()`
- size: `71`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180017f60`

## callees

- `0x18001069c`
- `0x180017ebc`

## import_xrefs

- `ncrypt!NCryptDeleteKey` at `0x180017ed8`
- `ncrypt!NCryptDeleteKey` at `0x180017ed8`

## string_xrefs

- `0x180017eea`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\tpmkeytranskey.cpp`

## pseudocode

```c
void __fastcall wil::details::ScopeExitFnGuard__lambda_0bac2ce823ad4db9ffe1585967a02367___::operator()(wil *a1)
{
  SECURITY_STATUS v1; // eax
  unsigned int v2; // eax
  void *v3; // rdx
  unsigned int v4; // r8d
  unsigned int v5; // eax
  int v6; // [rsp+20h] [rbp-8h]
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  wil *v9; // [rsp+30h] [rbp+8h]

  v9 = a1;
  try
  {
    if ( *((_BYTE *)a1 + 9) )
    {
      *((_BYTE *)a1 + 9) = 0;
      v1 = NCryptDeleteKey(*(_QWORD *)(*(_QWORD *)a1 + 8LL), 0);
      a1 = retaddr;
      if ( v1 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x5A,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\tpmkeytranskey.cpp",
          (const char *)(unsigned int)v1,
          v7);
    }
  }
  catch ( ... )
  {
    if ( *((_BYTE *)v9 + 8) == 2 )
    {
      v2 = wil::ResultFromCaughtException(a1);
      wil::details::in1diag3::FailFast_Hr(retaddr, v3, v4, (const char *)v2, v6);
    }
    if ( *((_BYTE *)v9 + 8) == 1 )
    {
      v5 = wil::ResultFromCaughtException(a1);
      wil::details::in1diag3::Log_Hr(retaddr, (void *)0x245, (unsigned int)"wil", (const char *)v5, v6);
    }
  }
}

```

## disassembly

```asm
0x180017ebc  mov     [rsp+arg_0], rcx
0x180017ec1  sub     rsp, 28h
0x180017ec5  cmp     byte ptr [rcx+9], 0
0x180017ec9  jz      short loc_180017EFC
0x180017ecb  mov     byte ptr [rcx+9], 0
0x180017ecf  mov     rcx, [rcx]
0x180017ed2  xor     edx, edx; dwFlags
0x180017ed4  mov     rcx, [rcx+8]; hKey
0x180017ed8  call    cs:__imp_NCryptDeleteKey
0x180017ede  mov     rcx, [rsp+28h]; this
0x180017ee3  test    eax, eax
0x180017ee5  jns     short loc_180017EFC
0x180017ee7  mov     r9d, eax; char *
0x180017eea  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180017ef1  mov     edx, 5Ah ; 'Z'; void *
0x180017ef6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017efb  nop
0x180017efc  jmp     short $+2
0x180017efe  add     rsp, 28h
0x180017f02  retn
```
