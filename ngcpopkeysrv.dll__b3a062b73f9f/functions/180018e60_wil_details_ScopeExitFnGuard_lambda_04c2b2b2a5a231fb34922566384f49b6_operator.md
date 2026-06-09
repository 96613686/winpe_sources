# wil::details::ScopeExitFnGuard__lambda_04c2b2b2a5a231fb34922566384f49b6___::operator()

- ea: `0x180018e60`
- end: `0x180018ea7`
- name: `wil::details::ScopeExitFnGuard__lambda_04c2b2b2a5a231fb34922566384f49b6___::operator()`
- size: `71`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018de0`
- `0x180018eec`

## callees

- `0x18001069c`
- `0x180018e60`

## import_xrefs

- `ncrypt!NCryptDeleteKey` at `0x180018e7c`
- `ncrypt!NCryptDeleteKey` at `0x180018e7c`

## string_xrefs

- `0x180018e8e`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\keytranskeybase.cpp`

## pseudocode

```c
void __fastcall wil::details::ScopeExitFnGuard__lambda_04c2b2b2a5a231fb34922566384f49b6___::operator()(_BYTE *a1)
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
        (void *)0xBC,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\keytranskeybase.cpp",
        (const char *)(unsigned int)v1,
        v2);
  }
}

```

## disassembly

```asm
0x180018e60  mov     [rsp+arg_0], rcx
0x180018e65  sub     rsp, 28h
0x180018e69  cmp     byte ptr [rcx+9], 0
0x180018e6d  jz      short loc_180018EA0
0x180018e6f  mov     byte ptr [rcx+9], 0
0x180018e73  mov     rcx, [rcx]
0x180018e76  xor     edx, edx; dwFlags
0x180018e78  mov     rcx, [rcx+8]; hKey
0x180018e7c  call    cs:__imp_NCryptDeleteKey
0x180018e82  mov     rcx, [rsp+28h]; this
0x180018e87  test    eax, eax
0x180018e89  jns     short loc_180018EA0
0x180018e8b  mov     r9d, eax; char *
0x180018e8e  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180018e95  mov     edx, 0BCh; void *
0x180018e9a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180018e9f  nop
0x180018ea0  jmp     short $+2
0x180018ea2  add     rsp, 28h
0x180018ea6  retn
```
