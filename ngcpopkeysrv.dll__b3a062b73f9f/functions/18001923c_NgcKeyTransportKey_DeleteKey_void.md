# NgcKeyTransportKey::DeleteKey(void)

- ea: `0x18001923c`
- end: `0x1800192e3`
- name: `?DeleteKey@NgcKeyTransportKey@@QEAAJXZ`
- size: `167`
- prototype: `__int64 __fastcall(const unsigned __int16 **this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e940`

## callees

- `0x18001069c`
- `0x1800176a4`
- `0x18001923c`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019285`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800192cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019285`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800192cd`
- `ncrypt!NCryptDeleteKey` at `0x18001929e`
- `ncrypt!NCryptDeleteKey` at `0x18001929e`

## string_xrefs

- `0x18001926d`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\keytranskeybase.cpp`
- `0x1800192ad`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\keytranskeybase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcKeyTransportKey::DeleteKey(const unsigned __int16 **this)
{
  const WCHAR *v2; // rax
  int v3; // eax
  NCRYPT_KEY_HANDLE v4; // rcx
  SECURITY_STATUS v5; // eax
  __int64 result; // rax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( this[3] )
  {
    v2 = (const WCHAR *)(*((__int64 (__fastcall **)(const unsigned __int16 **))*this + 3))(this);
    v3 = DeleteRegistryValueAndSubkeyIfEmpty(this[3], v2);
    if ( v3 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x10E,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\keytranskeybase.cpp",
        (const char *)(unsigned int)v3,
        v7);
    LocalFree((HLOCAL)this[3]);
    this[3] = 0;
  }
  v4 = (NCRYPT_KEY_HANDLE)this[1];
  if ( v4 )
  {
    v5 = NCryptDeleteKey(v4, 0);
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x118,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\keytranskeybase.cpp",
        (const char *)(unsigned int)v5,
        v7);
    this[1] = 0;
  }
  LocalFree((HLOCAL)this[4]);
  result = 0;
  this[4] = 0;
  return result;
}

```

## disassembly

```asm
0x18001923c  push    rbx; int
0x18001923e  sub     rsp, 20h
0x180019242  cmp     qword ptr [rcx+18h], 0
0x180019247  mov     rbx, rcx
0x18001924a  jz      short loc_180019293
0x18001924c  mov     rax, [rcx]
0x18001924f  mov     rax, [rax+18h]
0x180019253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019258  mov     rcx, [rbx+18h]; unsigned __int16 *
0x18001925c  mov     rdx, rax; lpValueName
0x18001925f  call    ?DeleteRegistryValueAndSubkeyIfEmpty@@YAJPEBG0@Z; DeleteRegistryValueAndSubkeyIfEmpty(ushort const *,ushort const *)
0x180019264  test    eax, eax
0x180019266  jns     short loc_180019281
0x180019268  mov     rcx, [rsp+28h]; this
0x18001926d  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180019274  mov     r9d, eax; char *
0x180019277  mov     edx, 10Eh; void *
0x18001927c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180019281  mov     rcx, [rbx+18h]; hMem
0x180019285  call    cs:__imp_LocalFree
0x18001928b  mov     qword ptr [rbx+18h], 0
0x180019293  mov     rcx, [rbx+8]; hKey
0x180019297  test    rcx, rcx
0x18001929a  jz      short loc_1800192C9
0x18001929c  xor     edx, edx; dwFlags
0x18001929e  call    cs:__imp_NCryptDeleteKey
0x1800192a4  test    eax, eax
0x1800192a6  jns     short loc_1800192C1
0x1800192a8  mov     rcx, [rsp+28h]; this
0x1800192ad  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800192b4  mov     r9d, eax; char *
0x1800192b7  mov     edx, 118h; void *
0x1800192bc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800192c1  mov     qword ptr [rbx+8], 0
0x1800192c9  mov     rcx, [rbx+20h]; hMem
0x1800192cd  call    cs:__imp_LocalFree
0x1800192d3  xor     eax, eax
0x1800192d5  mov     qword ptr [rbx+20h], 0
0x1800192dd  add     rsp, 20h
0x1800192e1  pop     rbx
0x1800192e2  retn
```
