# SslProtectSessionTicket

- ea: `0x18001b500`
- end: `0x18001b5ae`
- name: `SslProtectSessionTicket`
- size: `174`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009a70`
- `0x180009ea0`
- `0x18000c8e0`
- `0x18000e120`
- `0x18001b500`
- `0x180020010`

## string_xrefs

- `0x18001b58f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
__int64 SslProtectSessionTicket()
{
  __int64 v0; // rdx
  __int64 v1; // rax
  __int64 v2; // r10
  unsigned int v3; // ebx
  __int64 v4; // r9
  __int64 v5; // rcx
  int v6; // eax

  ValidateSslProvHandle();
  v1 = ValidateSslKeyHandle(v0);
  if ( *(_WORD *)(v2 + 32) < 7u )
  {
    v3 = -2146893783;
    v4 = 5041;
    v5 = 2148073513LL;
LABEL_7:
    DebugTraceError(v5, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v4);
    return NormalizeNteStatus(v3);
  }
  if ( !v1 )
  {
    v3 = -2146893786;
    v4 = 5053;
    v5 = 2148073510LL;
    goto LABEL_7;
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(v2 + 392))(*(_QWORD *)(v2 + 424), *(_QWORD *)(v1 + 16));
  v3 = v6;
  if ( v6 < 0 )
  {
    v4 = 5072;
    v5 = (unsigned int)v6;
    goto LABEL_7;
  }
  return NormalizeNteStatus(v3);
}

```

## disassembly

```asm
0x18001b500  push    rbx
0x18001b502  sub     rsp, 40h
0x18001b506  call    ValidateSslProvHandle
0x18001b50b  mov     rcx, rdx
0x18001b50e  mov     r10, rax
0x18001b511  call    ValidateSslKeyHandle
0x18001b516  mov     ecx, 7
0x18001b51b  cmp     cx, [r10+20h]
0x18001b520  jbe     short loc_18001B534
0x18001b522  mov     ebx, 80090029h
0x18001b527  mov     r9d, 13B1h
0x18001b52d  mov     ecx, 80090029h
0x18001b532  jmp     short loc_18001B58F
0x18001b534  test    rax, rax
0x18001b537  jz      short loc_18001B57F
0x18001b539  mov     ecx, [rsp+48h+arg_30]
0x18001b540  mov     rdx, [rax+10h]
0x18001b544  mov     rax, [r10+188h]
0x18001b54b  mov     [rsp+48h+var_18], ecx
0x18001b54f  mov     rcx, [rsp+48h+arg_28]
0x18001b554  mov     [rsp+48h+var_20], rcx
0x18001b559  mov     rcx, [rsp+48h+arg_20]
0x18001b55e  mov     [rsp+48h+var_28], rcx
0x18001b563  mov     rcx, [r10+1A8h]
0x18001b56a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b56f  mov     ebx, eax
0x18001b571  test    eax, eax
0x18001b573  jns     short loc_18001B5A2
0x18001b575  mov     r9d, 13D0h
0x18001b57b  mov     ecx, eax
0x18001b57d  jmp     short loc_18001B58F
0x18001b57f  mov     ebx, 80090026h
0x18001b584  mov     r9d, 13BDh
0x18001b58a  mov     ecx, 80090026h
0x18001b58f  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001b596  lea     rdx, aStatus; "Status"
0x18001b59d  call    DebugTraceError
0x18001b5a2  mov     ecx, ebx
0x18001b5a4  add     rsp, 40h
0x18001b5a8  pop     rbx
0x18001b5a9  jmp     NormalizeNteStatus
```
