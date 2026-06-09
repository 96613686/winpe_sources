# SslUnprotectSessionTicket

- ea: `0x18001b5c0`
- end: `0x18001b66e`
- name: `SslUnprotectSessionTicket`
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
- `0x18001b5c0`
- `0x180020010`

## string_xrefs

- `0x18001b64f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
__int64 SslUnprotectSessionTicket()
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
    v4 = 5106;
    v5 = 2148073513LL;
LABEL_7:
    DebugTraceError(v5, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v4);
    return NormalizeNteStatus(v3);
  }
  if ( !v1 )
  {
    v3 = -2146893786;
    v4 = 5118;
    v5 = 2148073510LL;
    goto LABEL_7;
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(v2 + 400))(*(_QWORD *)(v2 + 424), *(_QWORD *)(v1 + 16));
  v3 = v6;
  if ( v6 < 0 )
  {
    v4 = 5137;
    v5 = (unsigned int)v6;
    goto LABEL_7;
  }
  return NormalizeNteStatus(v3);
}

```

## disassembly

```asm
0x18001b5c0  push    rbx
0x18001b5c2  sub     rsp, 40h
0x18001b5c6  call    ValidateSslProvHandle
0x18001b5cb  mov     rcx, rdx
0x18001b5ce  mov     r10, rax
0x18001b5d1  call    ValidateSslKeyHandle
0x18001b5d6  mov     ecx, 7
0x18001b5db  cmp     cx, [r10+20h]
0x18001b5e0  jbe     short loc_18001B5F4
0x18001b5e2  mov     ebx, 80090029h
0x18001b5e7  mov     r9d, 13F2h
0x18001b5ed  mov     ecx, 80090029h
0x18001b5f2  jmp     short loc_18001B64F
0x18001b5f4  test    rax, rax
0x18001b5f7  jz      short loc_18001B63F
0x18001b5f9  mov     ecx, [rsp+48h+arg_30]
0x18001b600  mov     rdx, [rax+10h]
0x18001b604  mov     rax, [r10+190h]
0x18001b60b  mov     [rsp+48h+var_18], ecx
0x18001b60f  mov     rcx, [rsp+48h+arg_28]
0x18001b614  mov     [rsp+48h+var_20], rcx
0x18001b619  mov     rcx, [rsp+48h+arg_20]
0x18001b61e  mov     [rsp+48h+var_28], rcx
0x18001b623  mov     rcx, [r10+1A8h]
0x18001b62a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b62f  mov     ebx, eax
0x18001b631  test    eax, eax
0x18001b633  jns     short loc_18001B662
0x18001b635  mov     r9d, 1411h
0x18001b63b  mov     ecx, eax
0x18001b63d  jmp     short loc_18001B64F
0x18001b63f  mov     ebx, 80090026h
0x18001b644  mov     r9d, 13FEh
0x18001b64a  mov     ecx, 80090026h
0x18001b64f  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001b656  lea     rdx, aStatus; "Status"
0x18001b65d  call    DebugTraceError
0x18001b662  mov     ecx, ebx
0x18001b664  add     rsp, 40h
0x18001b668  pop     rbx
0x18001b669  jmp     NormalizeNteStatus
```
