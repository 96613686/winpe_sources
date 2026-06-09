# UninitializeConfig

- ea: `0x18006d310`
- end: `0x18006d35c`
- name: `UninitializeConfig`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18005d750`

## callees

- `0x180021af4`
- `0x18006a680`
- `0x18006d310`
- `0x1800a50b0`
- `0x1800a523c`

## import_xrefs

- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18006d327`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18006d327`

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
    TraceLoggingUnregister_EtwUnregister(&dword_1800CB588);
    TlgUnregisterAggregateProvider();
  }
}

```

## disassembly

```asm
0x18006d310  sub     rsp, 28h
0x18006d314  mov     eax, cs:g_TrustedEnvironment
0x18006d31a  test    eax, eax
0x18006d31c  jnz     short loc_18006D323
0x18006d31e  call    GetTrustedEnvironment
0x18006d323  test    al, 2
0x18006d325  jnz     short loc_18006D34A
0x18006d327  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x18006d32e  nop     dword ptr [rax+rax+00h]
0x18006d333  test    al, al
0x18006d335  jnz     short loc_18006D356
0x18006d337  lea     rcx, dword_1800CB588
0x18006d33e  call    TraceLoggingUnregister_EtwUnregister
0x18006d343  call    TlgUnregisterAggregateProvider
0x18006d348  jmp     short loc_18006D356
0x18006d34a  lea     rcx, ?pGlobalConfigContext@@3U_CNG_CONFIG_CONTEXT@@A; void *
0x18006d351  call    ?CngSiloContextCleanup@@YAXPEAX@Z; CngSiloContextCleanup(void *)
0x18006d356  add     rsp, 28h
0x18006d35a  retn
```
