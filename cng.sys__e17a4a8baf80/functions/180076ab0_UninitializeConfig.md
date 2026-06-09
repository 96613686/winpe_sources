# UninitializeConfig

- ea: `0x180076ab0`
- end: `0x180076afc`
- name: `UninitializeConfig`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180067030`

## callees

- `0x18002eb64`
- `0x180073e20`
- `0x180076ab0`
- `0x1800aa020`
- `0x1800aa1ac`

## import_xrefs

- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x180076ac7`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x180076ac7`

## pseudocode

```c
void UninitializeConfig()
{
  char TrustedEnvironment; // al

  TrustedEnvironment = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    TrustedEnvironment = GetTrustedEnvironment();
  if ( (TrustedEnvironment & 2) != 0 )
  {
    CngSiloContextCleanup(&pGlobalConfigContext);
  }
  else if ( !(unsigned __int8)PsIsCurrentThreadInServerSilo() )
  {
    TraceLoggingUnregister_EtwUnregister(&dword_1800D1588);
    TlgUnregisterAggregateProvider();
  }
}

```

## disassembly

```asm
0x180076ab0  sub     rsp, 28h
0x180076ab4  mov     eax, cs:g_TrustedEnvironment
0x180076aba  test    eax, eax
0x180076abc  jnz     short loc_180076AC3
0x180076abe  call    GetTrustedEnvironment
0x180076ac3  test    al, 2
0x180076ac5  jnz     short loc_180076AEA
0x180076ac7  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x180076ace  nop     dword ptr [rax+rax+00h]
0x180076ad3  test    al, al
0x180076ad5  jnz     short loc_180076AF6
0x180076ad7  lea     rcx, dword_1800D1588
0x180076ade  call    TraceLoggingUnregister_EtwUnregister
0x180076ae3  call    TlgUnregisterAggregateProvider
0x180076ae8  jmp     short loc_180076AF6
0x180076aea  lea     rcx, ?pGlobalConfigContext@@3U_CNG_CONFIG_CONTEXT@@A; void *
0x180076af1  call    ?CngSiloContextCleanup@@YAXPEAX@Z; CngSiloContextCleanup(void *)
0x180076af6  add     rsp, 28h
0x180076afa  retn
```
