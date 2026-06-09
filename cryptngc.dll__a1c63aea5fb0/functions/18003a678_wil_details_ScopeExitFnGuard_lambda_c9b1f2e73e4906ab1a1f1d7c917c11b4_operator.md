# wil::details::ScopeExitFnGuard__lambda_c9b1f2e73e4906ab1a1f1d7c917c11b4___::operator()

- ea: `0x18003a678`
- end: `0x18003a6c3`
- name: `wil::details::ScopeExitFnGuard__lambda_c9b1f2e73e4906ab1a1f1d7c917c11b4___::operator()`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180039c18`

## callees

- `0x180032fcc`
- `0x18003a678`

## import_xrefs

- `ncrypt!NCryptDeleteKey` at `0x18003a69a`
- `ncrypt!NCryptDeleteKey` at `0x18003a69a`

## string_xrefs

- `0x18003a6ac`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`

## pseudocode

```c
void __fastcall wil::details::ScopeExitFnGuard__lambda_c9b1f2e73e4906ab1a1f1d7c917c11b4___::operator()(__int64 a1)
{
  NCRYPT_KEY_HANDLE *v1; // rax
  NCRYPT_KEY_HANDLE v2; // rcx
  SECURITY_STATUS v3; // eax
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_BYTE *)(a1 + 9) )
  {
    *(_BYTE *)(a1 + 9) = 0;
    v1 = *(NCRYPT_KEY_HANDLE **)a1;
    v2 = **(_QWORD **)a1;
    *v1 = 0;
    v3 = NCryptDeleteKey(v2, 0);
    if ( v3 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2B3,
        (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
        (const char *)(unsigned int)v3,
        v4);
  }
}

```

## disassembly

```asm
0x18003a678  mov     [rsp+arg_0], rcx
0x18003a67d  sub     rsp, 28h
0x18003a681  cmp     byte ptr [rcx+9], 0
0x18003a685  jz      short loc_18003A6BE
0x18003a687  mov     byte ptr [rcx+9], 0
0x18003a68b  mov     rax, [rcx]
0x18003a68e  mov     rcx, [rax]; hKey
0x18003a691  mov     qword ptr [rax], 0
0x18003a698  xor     edx, edx; dwFlags
0x18003a69a  call    cs:__imp_NCryptDeleteKey
0x18003a6a0  mov     rcx, [rsp+28h]; this
0x18003a6a5  test    eax, eax
0x18003a6a7  jns     short loc_18003A6BE
0x18003a6a9  mov     r9d, eax; char *
0x18003a6ac  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18003a6b3  mov     edx, 2B3h; void *
0x18003a6b8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003a6bd  nop
0x18003a6be  add     rsp, 28h
0x18003a6c2  retn
```
