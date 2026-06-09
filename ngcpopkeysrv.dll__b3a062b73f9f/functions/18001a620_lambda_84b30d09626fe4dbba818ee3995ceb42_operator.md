# _lambda_84b30d09626fe4dbba818ee3995ceb42_::operator()

- ea: `0x18001a620`
- end: `0x18001a690`
- name: `_lambda_84b30d09626fe4dbba818ee3995ceb42_::operator()`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a968`

## callees

- `0x18001069c`
- `0x18001a620`
- `0x18001c984`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001a636`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001a636`
- `ncrypt!NCryptDeleteKey` at `0x18001a667`
- `ncrypt!NCryptDeleteKey` at `0x18001a667`

## string_xrefs

- `0x18001a645`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001a676`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
void __fastcall lambda_84b30d09626fe4dbba818ee3995ceb42_::operator()(__int64 a1)
{
  unsigned int v2; // eax
  NCRYPT_KEY_HANDLE v3; // rcx
  SECURITY_STATUS v4; // eax
  unsigned int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = RegDeleteValueW(**(HKEY **)a1, **(LPCWSTR **)(a1 + 8));
  if ( v2 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x347,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)v2,
      v5);
  v3 = **(_QWORD **)(a1 + 16);
  if ( v3 )
  {
    v4 = NCryptDeleteKey(v3, 0);
    if ( v4 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x34D,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
        (const char *)(unsigned int)v4,
        v5);
  }
}

```

## disassembly

```asm
0x18001a620  push    rbx; int
0x18001a622  sub     rsp, 20h
0x18001a626  mov     rdx, [rcx+8]
0x18001a62a  mov     rbx, rcx
0x18001a62d  mov     rcx, [rcx]
0x18001a630  mov     rdx, [rdx]; lpValueName
0x18001a633  mov     rcx, [rcx]; hKey
0x18001a636  call    cs:__imp_RegDeleteValueW
0x18001a63c  test    eax, eax
0x18001a63e  jz      short loc_18001A659
0x18001a640  mov     rcx, [rsp+28h]; this
0x18001a645  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001a64c  mov     r9d, eax; char *
0x18001a64f  mov     edx, 347h; void *
0x18001a654  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18001a659  mov     rax, [rbx+10h]
0x18001a65d  mov     rcx, [rax]; hKey
0x18001a660  test    rcx, rcx
0x18001a663  jz      short loc_18001A68A
0x18001a665  xor     edx, edx; dwFlags
0x18001a667  call    cs:__imp_NCryptDeleteKey
0x18001a66d  test    eax, eax
0x18001a66f  jns     short loc_18001A68A
0x18001a671  mov     rcx, [rsp+28h]; this
0x18001a676  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001a67d  mov     r9d, eax; char *
0x18001a680  mov     edx, 34Dh; void *
0x18001a685  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001a68a  add     rsp, 20h
0x18001a68e  pop     rbx
0x18001a68f  retn
```
