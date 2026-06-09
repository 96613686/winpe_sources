# SslVerifySignature

- ea: `0x18001b680`
- end: `0x18001b71f`
- name: `SslVerifySignature`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009a70`
- `0x180009ea0`
- `0x18000c8e0`
- `0x18000e120`
- `0x18001b680`
- `0x180020010`

## string_xrefs

- `0x18001b6aa`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslVerifySignature(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        BYTE *a5,
        DWORD *a6,
        DWORD *a7)
{
  __int64 v7; // rdx
  __int64 v8; // r9
  unsigned int v9; // ebx
  __int64 v10; // rcx
  NCRYPT_KEY_HANDLE *v11; // rdx
  NCryptKeyName **v12; // r8
  NCryptAlgorithmName **v13; // r9
  __int64 v14; // rax
  __int64 v15; // r10
  int v16; // eax

  if ( !ValidateSslProvHandle(a1) )
  {
    v8 = 3243;
LABEL_3:
    v9 = -2146893786;
    v10 = 2148073510LL;
    goto LABEL_4;
  }
  v14 = ValidateSslKeyHandle(v7);
  if ( !v14 )
  {
    v8 = 3251;
    goto LABEL_3;
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(v15 + 216))(*(_QWORD *)(v15 + 424), *(_QWORD *)(v14 + 16));
  v9 = v16;
  if ( v16 >= 0 )
  {
    v9 = 0;
    return NormalizeNteStatus(v9, v11, v12, v13, a5, a6, a7);
  }
  v8 = 3269;
  v10 = (unsigned int)v16;
LABEL_4:
  DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v8);
  return NormalizeNteStatus(v9, v11, v12, v13, a5, a6, a7);
}

```

## disassembly

```asm
0x18001b680  push    rbx
0x18001b682  sub     rsp, 40h
0x18001b686  call    ValidateSslProvHandle
0x18001b68b  mov     r10, rax
0x18001b68e  test    rax, rax
0x18001b691  jnz     short loc_18001B6B8
0x18001b693  mov     r9d, 0CABh
0x18001b699  mov     ebx, 80090026h
0x18001b69e  mov     ecx, 80090026h
0x18001b6a3  lea     rdx, aStatus; "Status"
0x18001b6aa  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001b6b1  call    DebugTraceError
0x18001b6b6  jmp     short loc_18001B713
0x18001b6b8  mov     rcx, rdx
0x18001b6bb  call    ValidateSslKeyHandle
0x18001b6c0  test    rax, rax
0x18001b6c3  jnz     short loc_18001B6CD
0x18001b6c5  mov     r9d, 0CB3h
0x18001b6cb  jmp     short loc_18001B699
0x18001b6cd  mov     ecx, [rsp+48h+arg_30]
0x18001b6d4  mov     rdx, [rax+10h]
0x18001b6d8  mov     rax, [r10+0D8h]
0x18001b6df  mov     [rsp+48h+var_18], ecx
0x18001b6e3  mov     ecx, dword ptr [rsp+48h+arg_28]
0x18001b6e7  mov     [rsp+48h+var_20], ecx
0x18001b6eb  mov     rcx, [rsp+48h+arg_20]
0x18001b6f0  mov     [rsp+48h+var_28], rcx
0x18001b6f5  mov     rcx, [r10+1A8h]
0x18001b6fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b701  mov     ebx, eax
0x18001b703  test    eax, eax
0x18001b705  jns     short loc_18001B711
0x18001b707  mov     r9d, 0CC5h
0x18001b70d  mov     ecx, eax
0x18001b70f  jmp     short loc_18001B6A3
0x18001b711  xor     ebx, ebx
0x18001b713  mov     ecx, ebx
0x18001b715  add     rsp, 40h
0x18001b719  pop     rbx
0x18001b71a  jmp     NormalizeNteStatus
```
