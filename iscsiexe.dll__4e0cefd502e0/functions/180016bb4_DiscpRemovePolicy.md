# DiscpRemovePolicy

- ea: `0x180016bb4`
- end: `0x180016c10`
- name: `DiscpRemovePolicy`
- size: `92`
- prototype: `__int64 __fastcall(GUID *key)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f280`
- `0x18000f310`

## callees

- `0x180016bb4`

## import_xrefs

- `fwpuclnt!FwpmTransactionCommit0` at `0x180016bf3`
- `fwpuclnt!FwpmTransactionCommit0` at `0x180016bf3`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x180016be0`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x180016be0`
- `fwpuclnt!FwpmTransactionBegin0` at `0x180016bca`
- `fwpuclnt!FwpmTransactionBegin0` at `0x180016bca`
- `fwpuclnt!FwpmTransactionAbort0` at `0x180016bfd`
- `fwpuclnt!FwpmTransactionAbort0` at `0x180016bfd`

## pseudocode

```c
__int64 __fastcall DiscpRemovePolicy(GUID *key)
{
  DWORD v2; // ebx

  v2 = FwpmTransactionBegin0(DiscpEngineHandle, 0);
  if ( !v2 )
  {
    v2 = FwpmProviderContextDeleteByKey0(DiscpEngineHandle, key);
    if ( v2 )
      FwpmTransactionAbort0(DiscpEngineHandle);
    else
      return FwpmTransactionCommit0(DiscpEngineHandle);
  }
  return v2;
}

```

## disassembly

```asm
0x180016bb4  mov     [rsp+arg_0], rbx
0x180016bb9  push    rdi
0x180016bba  sub     rsp, 20h
0x180016bbe  mov     rdi, rcx
0x180016bc1  xor     edx, edx; flags
0x180016bc3  mov     rcx, cs:DiscpEngineHandle; engineHandle
0x180016bca  call    cs:__imp_FwpmTransactionBegin0
0x180016bd0  mov     ebx, eax
0x180016bd2  test    eax, eax
0x180016bd4  jnz     short loc_180016C03
0x180016bd6  mov     rcx, cs:DiscpEngineHandle; engineHandle
0x180016bdd  mov     rdx, rdi; key
0x180016be0  call    cs:__imp_FwpmProviderContextDeleteByKey0
0x180016be6  mov     rcx, cs:DiscpEngineHandle; engineHandle
0x180016bed  mov     ebx, eax
0x180016bef  test    eax, eax
0x180016bf1  jnz     short loc_180016BFD
0x180016bf3  call    cs:__imp_FwpmTransactionCommit0
0x180016bf9  mov     ebx, eax
0x180016bfb  jmp     short loc_180016C03
0x180016bfd  call    cs:__imp_FwpmTransactionAbort0
0x180016c03  mov     eax, ebx
0x180016c05  mov     rbx, [rsp+28h+arg_0]
0x180016c0a  add     rsp, 20h
0x180016c0e  pop     rdi
0x180016c0f  retn
```
