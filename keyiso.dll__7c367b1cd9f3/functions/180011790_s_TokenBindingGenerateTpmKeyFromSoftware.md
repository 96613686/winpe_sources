# s_TokenBindingGenerateTpmKeyFromSoftware

- ea: `0x180011790`
- end: `0x180011850`
- name: `s_TokenBindingGenerateTpmKeyFromSoftware`
- size: `192`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x1800115a4`
- `0x180011790`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800117a8`
- `RPCRT4!RpcImpersonateClient` at `0x1800117a8`
- `RPCRT4!RpcRevertToSelf` at `0x180011838`
- `RPCRT4!RpcRevertToSelf` at `0x180011838`

## string_xrefs

- `0x1800117b8`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\tokenbindingcryptoapi.c`
- `0x1800117f7`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\tokenbindingcryptoapi.c`
- `0x180011816`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\tokenbindingcryptoapi.c`

## pseudocode

```c
__int64 __fastcall s_TokenBindingGenerateTpmKeyFromSoftware(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  int SoftwareKeyAndImportIntoTpm; // eax

  v8 = RpcImpersonateClient(a1);
  if ( v8 )
  {
    DebugTraceError(
      v8,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\tokenbindingcryptoapi.c",
      231);
    return (unsigned int)-2146893792;
  }
  else
  {
    SoftwareKeyAndImportIntoTpm = TokenBindingGenerateSoftwareKeyAndImportIntoTpm(a2, a3, a4, a5);
    v9 = SoftwareKeyAndImportIntoTpm;
    if ( SoftwareKeyAndImportIntoTpm < 0 )
      DebugTraceError(
        (unsigned int)SoftwareKeyAndImportIntoTpm,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\tokenbindingcryptoapi.c",
        245);
    RpcRevertToSelf();
  }
  return v9;
}

```

## disassembly

```asm
0x180011790  mov     [rsp+arg_0], rbx
0x180011795  mov     [rsp+arg_8], rsi
0x18001179a  push    rdi
0x18001179b  sub     rsp, 30h
0x18001179f  mov     rbx, r9
0x1800117a2  mov     rdi, r8
0x1800117a5  mov     rsi, rdx
0x1800117a8  call    cs:__imp_RpcImpersonateClient
0x1800117ae  test    eax, eax
0x1800117b0  jz      short loc_1800117D4
0x1800117b2  mov     r9d, 0E7h
0x1800117b8  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800117bf  lea     rdx, aStatus; "Status"
0x1800117c6  mov     ecx, eax
0x1800117c8  call    DebugTraceError
0x1800117cd  mov     ebx, 80090020h
0x1800117d2  jmp     short loc_18001183E
0x1800117d4  mov     r9d, [rsp+38h+arg_20]
0x1800117d9  mov     r8, rbx
0x1800117dc  mov     rdx, rdi
0x1800117df  mov     rcx, rsi
0x1800117e2  call    TokenBindingGenerateSoftwareKeyAndImportIntoTpm
0x1800117e7  mov     ebx, eax
0x1800117e9  mov     [rsp+38h+var_18], eax
0x1800117ed  test    eax, eax
0x1800117ef  jns     short loc_18001180C
0x1800117f1  mov     r9d, 0F5h
0x1800117f7  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800117fe  lea     rdx, aStatus; "Status"
0x180011805  mov     ecx, eax
0x180011807  call    DebugTraceError
0x18001180c  jmp     short loc_180011838
0x18001180e  mov     ebx, eax
0x180011810  mov     r9d, 0FBh
0x180011816  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001181d  lea     rdx, aNtstatus; "ntStatus"
0x180011824  mov     ecx, eax
0x180011826  call    DebugTraceError
0x18001182b  mov     ecx, ebx
0x18001182d  call    NormalizeNteStatus
0x180011832  mov     ebx, eax
0x180011834  mov     [rsp+38h+var_18], eax
0x180011838  call    cs:__imp_RpcRevertToSelf
0x18001183e  mov     eax, ebx
0x180011840  mov     rbx, [rsp+38h+arg_0]
0x180011845  mov     rsi, [rsp+38h+arg_8]
0x18001184a  add     rsp, 30h
0x18001184e  pop     rdi
0x18001184f  retn
```
