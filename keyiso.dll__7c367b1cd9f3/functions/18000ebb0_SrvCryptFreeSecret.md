# SrvCryptFreeSecret

- ea: `0x18000ebb0`
- end: `0x18000ec2a`
- name: `SrvCryptFreeSecret`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180008e98`
- `0x180008f00`
- `0x18000ebb0`
- `0x1800112e0`

## string_xrefs

- `0x18000ebcb`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptFreeSecret(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r9
  unsigned int v5; // ebx
  __int64 v6; // rax
  __int64 v7; // rdi

  if ( a1 )
  {
    v6 = SrvLookupAndReferenceSecret(a1, a3, 1);
    v7 = v6;
    if ( v6 )
    {
      SrvRemoveSecretFromList(a1, v6);
      return (unsigned int)SrvDereferenceSecret(v7);
    }
    v4 = 3052;
  }
  else
  {
    v4 = 3037;
  }
  v5 = -2146893786;
  DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v4);
  return v5;
}

```

## disassembly

```asm
0x18000ebb0  mov     [rsp+arg_0], rbx
0x18000ebb5  push    rdi
0x18000ebb6  sub     rsp, 20h
0x18000ebba  mov     rax, r8
0x18000ebbd  mov     rbx, rcx
0x18000ebc0  test    rcx, rcx
0x18000ebc3  jnz     short loc_18000EBEA
0x18000ebc5  mov     r9d, 0BDDh
0x18000ebcb  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ebd2  mov     ecx, 80090026h
0x18000ebd7  lea     rdx, aStatus; "Status"
0x18000ebde  mov     ebx, 80090026h
0x18000ebe3  call    DebugTraceError
0x18000ebe8  jmp     short loc_18000EC1D
0x18000ebea  mov     r8d, 1
0x18000ebf0  mov     rdx, rax
0x18000ebf3  call    SrvLookupAndReferenceSecret
0x18000ebf8  mov     rdi, rax
0x18000ebfb  test    rax, rax
0x18000ebfe  jnz     short loc_18000EC08
0x18000ec00  mov     r9d, 0BECh
0x18000ec06  jmp     short loc_18000EBCB
0x18000ec08  mov     rdx, rdi
0x18000ec0b  mov     rcx, rbx
0x18000ec0e  call    SrvRemoveSecretFromList
0x18000ec13  mov     rcx, rdi
0x18000ec16  call    SrvDereferenceSecret
0x18000ec1b  mov     ebx, eax
0x18000ec1d  mov     eax, ebx
0x18000ec1f  mov     rbx, [rsp+28h+arg_0]
0x18000ec24  add     rsp, 20h
0x18000ec28  pop     rdi
0x18000ec29  retn
```
