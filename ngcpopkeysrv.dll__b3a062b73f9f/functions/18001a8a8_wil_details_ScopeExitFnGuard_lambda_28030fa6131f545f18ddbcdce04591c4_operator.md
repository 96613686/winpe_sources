# wil::details::ScopeExitFnGuard__lambda_28030fa6131f545f18ddbcdce04591c4___::operator()

- ea: `0x18001a8a8`
- end: `0x18001a8f3`
- name: `wil::details::ScopeExitFnGuard__lambda_28030fa6131f545f18ddbcdce04591c4___::operator()`
- size: `75`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001985c`
- `0x18001b0b4`

## callees

- `0x18001069c`
- `0x18001a8a8`

## import_xrefs

- `ncrypt!NCryptDeleteKey` at `0x18001a8ca`
- `ncrypt!NCryptDeleteKey` at `0x18001a8ca`

## string_xrefs

- `0x18001a8dc`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
void __fastcall wil::details::ScopeExitFnGuard__lambda_28030fa6131f545f18ddbcdce04591c4___::operator()(__int64 a1)
{
  NCRYPT_KEY_HANDLE *v1; // rax
  NCRYPT_KEY_HANDLE v2; // rcx
  SECURITY_STATUS v3; // eax
  wil *v4; // rcx
  unsigned int v5; // eax
  unsigned int v6; // eax
  void *v7; // rdx
  unsigned int v8; // r8d
  unsigned int v9; // eax
  int v10; // [rsp+20h] [rbp-8h]
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_BYTE *)(a1 + 9) )
  {
    *(_BYTE *)(a1 + 9) = 0;
    v1 = *(NCRYPT_KEY_HANDLE **)a1;
    v2 = **(_QWORD **)a1;
    *v1 = 0;
    try
    {
      v3 = NCryptDeleteKey(v2, 0);
      v4 = retaddr;
      if ( v3 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x54A,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
          (const char *)(unsigned int)v3,
          v11);
    }
    catch ( ... )
    {
      if ( *(_BYTE *)(a1 + 8) == 2 )
      {
        v5 = wil::ResultFromCaughtException(v4);
        v6 = wil::verify_hresult<long>(v5);
        wil::details::in1diag3::FailFast_Hr(retaddr, v7, v8, (const char *)v6, v10);
      }
      if ( *(_BYTE *)(a1 + 8) == 1 )
      {
        v9 = wil::ResultFromCaughtException(v4);
        wil::details::in1diag3::Log_Hr(retaddr, (void *)0x245, (unsigned int)"wil", (const char *)v9, v10);
      }
    }
  }
}

```

## disassembly

```asm
0x18001a8a8  mov     [rsp+arg_0], rcx
0x18001a8ad  sub     rsp, 28h
0x18001a8b1  cmp     byte ptr [rcx+9], 0
0x18001a8b5  jz      short loc_18001A8EE
0x18001a8b7  mov     byte ptr [rcx+9], 0
0x18001a8bb  mov     rax, [rcx]
0x18001a8be  mov     rcx, [rax]; hKey
0x18001a8c1  mov     qword ptr [rax], 0
0x18001a8c8  xor     edx, edx; dwFlags
0x18001a8ca  call    cs:__imp_NCryptDeleteKey
0x18001a8d0  mov     rcx, [rsp+28h]; this
0x18001a8d5  test    eax, eax
0x18001a8d7  jns     short loc_18001A8EE
0x18001a8d9  mov     r9d, eax; char *
0x18001a8dc  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001a8e3  mov     edx, 54Ah; void *
0x18001a8e8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001a8ed  nop
0x18001a8ee  add     rsp, 28h
0x18001a8f2  retn
```
