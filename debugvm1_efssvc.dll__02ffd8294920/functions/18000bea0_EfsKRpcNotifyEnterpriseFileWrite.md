# EfsKRpcNotifyEnterpriseFileWrite

- ea: `0x18000bea0`
- end: `0x18000bf8c`
- name: `EfsKRpcNotifyEnterpriseFileWrite`
- size: `236`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000bea0`
- `0x18000c244`

## import_xrefs

- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000bf5f`
- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000bf5f`
- `EFSCORE!EdpDllQueueFileForEncryption` at `0x18000bf38`
- `EFSCORE!EdpDllQueueFileForEncryption` at `0x18000bf38`
- `EFSCORE!EfsDllDisabled` at `0x18000bf10`
- `EFSCORE!EfsDllDisabled` at `0x18000bf10`

## pseudocode

```c
__int64 __fastcall EfsKRpcNotifyEnterpriseFileWrite(void *a1)
{
  EfspValidateClientCall(a1);
  return 3221225506LL;
}

```

## disassembly

```asm
0x18000bea0  push    rbx
0x18000bea2  push    rbp
0x18000bea3  push    rsi
0x18000bea4  push    r14
0x18000bea6  sub     rsp, 48h
0x18000beaa  mov     r14, rdx
0x18000bead  mov     [rsp+68h+var_38], 0
0x18000beb5  lea     rdx, [rsp+68h+var_38]
0x18000beba  mov     rbx, r9
0x18000bebd  mov     rbp, r8
0x18000bec0  call    EfspValidateClientCall
0x18000bec5  test    eax, eax
0x18000bec7  jnz     loc_18000BF7D
0x18000becd  cmp     [rsp+68h+var_38], eax
0x18000bed1  jz      loc_18000BF7D
0x18000bed7  test    rbp, rbp
0x18000beda  jnz     short loc_18000BEF5
0x18000bedc  test    rbx, rbx
0x18000bedf  jnz     short loc_18000BEEB
0x18000bee1  cmp     [rsp+68h+arg_20], rbx
0x18000bee9  jnz     short loc_18000BEFA
0x18000beeb  mov     eax, 0C000000Dh
0x18000bef0  jmp     loc_18000BF82
0x18000bef5  test    rbx, rbx
0x18000bef8  jmp     short loc_18000BEE9
0x18000befa  mov     rsi, [rsp+68h+arg_28]
0x18000bf02  test    rsi, rsi
0x18000bf05  jz      short loc_18000BEEB
0x18000bf07  cmp     cs:EfsServerInitialized, 0
0x18000bf0e  jz      short loc_18000BF76
0x18000bf10  call    cs:__imp_EfsDllDisabled
0x18000bf16  test    al, al
0x18000bf18  jnz     short loc_18000BF76
0x18000bf1a  mov     r9, [rsp+68h+arg_20]
0x18000bf22  mov     r8, rbx
0x18000bf25  mov     rdx, rbp
0x18000bf28  mov     [rsp+68h+var_38], 0
0x18000bf30  mov     rcx, r14
0x18000bf33  mov     [rsp+68h+var_48], rsi
0x18000bf38  call    cs:__imp_EdpDllQueueFileForEncryption
0x18000bf3e  test    eax, eax
0x18000bf40  jns     short loc_18000BF70
0x18000bf42  mov     ecx, eax
0x18000bf44  and     ecx, 1FFF0000h
0x18000bf4a  cmp     ecx, 70000h
0x18000bf50  movzx   ecx, ax
0x18000bf53  jz      short loc_18000BF5A
0x18000bf55  mov     ecx, 54Fh
0x18000bf5a  lea     rdx, [rsp+68h+var_38]
0x18000bf5f  call    cs:__imp_EfsDllErrorToNtStatus
0x18000bf65  test    eax, eax
0x18000bf67  jnz     short loc_18000BF70
0x18000bf69  mov     eax, 0C0000001h
0x18000bf6e  jmp     short loc_18000BF82
0x18000bf70  mov     eax, [rsp+68h+var_38]
0x18000bf74  jmp     short loc_18000BF82
0x18000bf76  mov     eax, 0C00000BBh
0x18000bf7b  jmp     short loc_18000BF82
0x18000bf7d  mov     eax, 0C0000022h
0x18000bf82  add     rsp, 48h
0x18000bf86  pop     r14
0x18000bf88  pop     rsi
0x18000bf89  pop     rbp
0x18000bf8a  pop     rbx
0x18000bf8b  retn
```
