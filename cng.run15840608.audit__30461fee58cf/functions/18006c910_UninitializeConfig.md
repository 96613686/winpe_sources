# UninitializeConfig

- ea: `0x18006c910`
- end: `0x18006c95c`
- name: `UninitializeConfig`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18005ce60`

## callees

- `0x180024a34`
- `0x180069c80`
- `0x18006c910`
- `0x1800a3280`
- `0x1800a340c`

## import_xrefs

- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18006c927`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18006c927`

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
    TraceLoggingUnregister_EtwUnregister(&dword_1800C9588);
    TlgUnregisterAggregateProvider();
  }
}

```

## disassembly

```asm
0x18006c910  sub     rsp, 28h
0x18006c914  mov     eax, cs:g_TrustedEnvironment
0x18006c91a  test    eax, eax
0x18006c91c  jnz     short loc_18006C923
0x18006c91e  call    GetTrustedEnvironment
0x18006c923  test    al, 2
0x18006c925  jnz     short loc_18006C94A
0x18006c927  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x18006c92e  nop     dword ptr [rax+rax+00h]
0x18006c933  test    al, al
0x18006c935  jnz     short loc_18006C956
0x18006c937  lea     rcx, dword_1800C9588
0x18006c93e  call    TraceLoggingUnregister_EtwUnregister
0x18006c943  call    TlgUnregisterAggregateProvider
0x18006c948  jmp     short loc_18006C956
0x18006c94a  lea     rcx, ?pGlobalConfigContext@@3U_CNG_CONFIG_CONTEXT@@A; void *
0x18006c951  call    ?CngSiloContextCleanup@@YAXPEAX@Z; CngSiloContextCleanup(void *)
0x18006c956  add     rsp, 28h
0x18006c95a  retn
```
