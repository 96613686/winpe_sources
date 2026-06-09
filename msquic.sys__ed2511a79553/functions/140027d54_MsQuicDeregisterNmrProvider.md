# MsQuicDeregisterNmrProvider

- ea: `0x140027d54`
- end: `0x140027db2`
- name: `MsQuicDeregisterNmrProvider`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140063360`

## callees

- `0x140027d54`
- `0x1400337e4`

## import_xrefs

- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x140027d98`
- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x140027d98`
- `NETIO!NmrDeregisterProvider` at `0x140027d64`
- `NETIO!NmrDeregisterProvider` at `0x140027d64`

## pseudocode

```c
void MsQuicDeregisterNmrProvider()
{
  if ( NmrProviderHandle )
  {
    if ( NmrDeregisterProvider(NmrProviderHandle) != 259 )
    {
      CxPlatLogAssert(
        "C:\\__w\\1\\s\\msquic\\src\\bin\\winkernel\\nmrprovider.c",
        134,
        "Status == ((NTSTATUS)0x00000103L)");
      __int2c();
    }
    NmrWaitForProviderDeregisterComplete(NmrProviderHandle);
    NmrProviderHandle = 0;
  }
}

```

## disassembly

```asm
0x140027d54  sub     rsp, 28h
0x140027d58  mov     rcx, cs:NmrProviderHandle; NmrProviderHandle
0x140027d5f  test    rcx, rcx
0x140027d62  jz      short loc_140027DAC
0x140027d64  call    cs:__imp_NmrDeregisterProvider
0x140027d6b  nop     dword ptr [rax+rax+00h]
0x140027d70  cmp     eax, 103h
0x140027d75  jz      short loc_140027D91
0x140027d77  lea     r8, aStatusNtstatus; "Status == ((NTSTATUS)0x00000103L)"
0x140027d7e  mov     edx, 86h
0x140027d83  lea     rcx, aCW1SMsquicSrcB; "C:\\__w\\1\\s\\msquic\\src\\bin\\winker"...
0x140027d8a  call    CxPlatLogAssert
0x140027d8f  int     2Ch; Windows NT - assertion failure
0x140027d91  mov     rcx, cs:NmrProviderHandle; NmrProviderHandle
0x140027d98  call    cs:__imp_NmrWaitForProviderDeregisterComplete
0x140027d9f  nop     dword ptr [rax+rax+00h]
0x140027da4  and     cs:NmrProviderHandle, 0
0x140027dac  add     rsp, 28h
0x140027db0  retn
```
