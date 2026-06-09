# DiscpRemoveFilters

- ea: `0x180016b2c`
- end: `0x180016bac`
- name: `DiscpRemoveFilters`
- size: `128`
- prototype: `__int64 __fastcall(char, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f310`
- `0x1800151b0`

## callees

- `0x180016b2c`

## import_xrefs

- `fwpuclnt!FwpmTransactionCommit0` at `0x180016b99`
- `fwpuclnt!FwpmTransactionCommit0` at `0x180016b99`
- `fwpuclnt!FwpmIPsecTunnelDeleteByKey0` at `0x180016b5a`
- `fwpuclnt!FwpmIPsecTunnelDeleteByKey0` at `0x180016b5a`
- `fwpuclnt!FwpmTransactionBegin0` at `0x180016b6d`
- `fwpuclnt!FwpmTransactionBegin0` at `0x180016b6d`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x180016b8f`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x180016b8f`

## pseudocode

```c
__int64 __fastcall DiscpRemoveFilters(char a1, unsigned int a2, __int64 a3)
{
  unsigned int v5; // ebx
  DWORD v6; // edi
  unsigned int v7; // ebx

  if ( (a1 & 0x41) == 0x41 )
  {
    v5 = 0;
    v6 = 0;
    while ( v5 < a2 )
      FwpmIPsecTunnelDeleteByKey0(DiscpEngineHandle, (const GUID *)(a3 + 16LL * v5++));
  }
  else
  {
    v7 = 0;
    v6 = FwpmTransactionBegin0(DiscpEngineHandle, 0);
    if ( !v6 )
    {
      while ( v7 < a2 )
        FwpmFilterDeleteByKey0(DiscpEngineHandle, (const GUID *)(a3 + 16LL * v7++));
      return FwpmTransactionCommit0(DiscpEngineHandle);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180016b2c  push    rbx
0x180016b2e  push    rbp
0x180016b2f  push    rsi
0x180016b30  push    rdi
0x180016b31  sub     rsp, 28h
0x180016b35  and     cl, 41h
0x180016b38  mov     rbp, r8
0x180016b3b  mov     esi, edx
0x180016b3d  cmp     cl, 41h ; 'A'
0x180016b40  jnz     short loc_180016B64
0x180016b42  xor     ebx, ebx
0x180016b44  mov     edi, ebx
0x180016b46  cmp     ebx, esi
0x180016b48  jnb     short loc_180016BA1
0x180016b4a  mov     rcx, cs:DiscpEngineHandle; engineHandle
0x180016b51  mov     edx, ebx
0x180016b53  shl     rdx, 4
0x180016b57  add     rdx, rbp; key
0x180016b5a  call    cs:__imp_FwpmIPsecTunnelDeleteByKey0
0x180016b60  inc     ebx
0x180016b62  jmp     short loc_180016B46
0x180016b64  mov     rcx, cs:DiscpEngineHandle; engineHandle
0x180016b6b  xor     edx, edx; flags
0x180016b6d  call    cs:__imp_FwpmTransactionBegin0
0x180016b73  xor     ebx, ebx
0x180016b75  mov     edi, eax
0x180016b77  test    eax, eax
0x180016b79  jnz     short loc_180016BA1
0x180016b7b  mov     rcx, cs:DiscpEngineHandle; engineHandle
0x180016b82  cmp     ebx, esi
0x180016b84  jnb     short loc_180016B99
0x180016b86  mov     edx, ebx
0x180016b88  shl     rdx, 4
0x180016b8c  add     rdx, rbp; key
0x180016b8f  call    cs:__imp_FwpmFilterDeleteByKey0
0x180016b95  inc     ebx
0x180016b97  jmp     short loc_180016B7B
0x180016b99  call    cs:__imp_FwpmTransactionCommit0
0x180016b9f  mov     edi, eax
0x180016ba1  mov     eax, edi
0x180016ba3  add     rsp, 28h
0x180016ba7  pop     rdi
0x180016ba8  pop     rsi
0x180016ba9  pop     rbp
0x180016baa  pop     rbx
0x180016bab  retn
```
