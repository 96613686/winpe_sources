# FCpEncVolumeCleanup

- ea: `0x14000d370`
- end: `0x14000d390`
- name: `FCpEncVolumeCleanup`
- size: `32`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d050`
- `0x14000d398`

## callees

- `0x14000d370`

## import_xrefs

- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14000d37e`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14000d37e`

## pseudocode

```c
NTSTATUS __fastcall FCpEncVolumeCleanup(void **a1)
{
  void *v1; // rcx
  NTSTATUS result; // eax

  v1 = *a1;
  if ( v1 )
    return BCryptCloseAlgorithmProvider(v1, 0);
  return result;
}

```

## disassembly

```asm
0x14000d370  sub     rsp, 28h
0x14000d374  mov     rcx, [rcx]; hAlgorithm
0x14000d377  test    rcx, rcx
0x14000d37a  jz      short loc_14000D38A
0x14000d37c  xor     edx, edx; dwFlags
0x14000d37e  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14000d385  nop     dword ptr [rax+rax+00h]
0x14000d38a  add     rsp, 28h
0x14000d38e  retn
```
