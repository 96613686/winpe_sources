# wil::details::ScopeExitFnGuard__lambda_b77dc92ef505b91b2d7e2ba3e88216b8___::operator()

- ea: `0x18001874c`
- end: `0x180018793`
- name: `wil::details::ScopeExitFnGuard__lambda_b77dc92ef505b91b2d7e2ba3e88216b8___::operator()`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018678`
- `0x1800187a0`

## callees

- `0x18001069c`
- `0x18001874c`

## import_xrefs

- `ncrypt!NCryptDeleteKey` at `0x180018768`
- `ncrypt!NCryptDeleteKey` at `0x180018768`

## string_xrefs

- `0x18001877a`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\softwarekeytranskey.cpp`

## pseudocode

```c
void __fastcall wil::details::ScopeExitFnGuard__lambda_b77dc92ef505b91b2d7e2ba3e88216b8___::operator()(_BYTE *a1)
{
  SECURITY_STATUS v1; // eax
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a1[9] )
  {
    a1[9] = 0;
    v1 = NCryptDeleteKey(*(_QWORD *)(*(_QWORD *)a1 + 8LL), 0);
    if ( v1 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\softwarekeytranskey.cpp",
        (const char *)(unsigned int)v1,
        v2);
  }
}

```

## disassembly

```asm
0x18001874c  mov     [rsp+arg_0], rcx
0x180018751  sub     rsp, 28h
0x180018755  cmp     byte ptr [rcx+9], 0
0x180018759  jz      short loc_18001878C
0x18001875b  mov     byte ptr [rcx+9], 0
0x18001875f  mov     rcx, [rcx]
0x180018762  xor     edx, edx; dwFlags
0x180018764  mov     rcx, [rcx+8]; hKey
0x180018768  call    cs:__imp_NCryptDeleteKey
0x18001876e  mov     rcx, [rsp+28h]; this
0x180018773  test    eax, eax
0x180018775  jns     short loc_18001878C
0x180018777  mov     r9d, eax; char *
0x18001877a  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180018781  mov     edx, 48h ; 'H'; void *
0x180018786  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001878b  nop
0x18001878c  jmp     short $+2
0x18001878e  add     rsp, 28h
0x180018792  retn
```
