# MSCryptPqDsaFinalizeKeyPair

- ea: `0x180078e60`
- end: `0x180078fc3`
- name: `MSCryptPqDsaFinalizeKeyPair`
- size: `355`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000743c`
- `0x180048770`
- `0x180078e60`
- `0x18007a11c`
- `0x18008cc54`
- `0x18008cd14`
- `0x18008cd5c`
- `0x18008e070`
- `0x18008e0f4`
- `0x18008e120`

## string_xrefs

- `0x180078e7f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`
- `0x180078f2e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`
- `0x180078f83`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptPqDsaFinalizeKeyPair(__int64 a1, int a2)
{
  __int64 v2; // r9
  unsigned int v3; // ebx
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rdi
  unsigned int v10; // eax
  __int64 v11; // rax
  unsigned int v12; // eax

  if ( a1 )
  {
    if ( a2 )
    {
      v2 = 1060;
      goto LABEL_3;
    }
    v5 = validatePqDsaKey(a1, 0);
    v6 = v5;
    if ( !v5 )
    {
      v2 = 1068;
LABEL_9:
      v3 = -1073741816;
      v4 = 3221225480LL;
      goto LABEL_4;
    }
    v7 = *(_QWORD *)(v5 + 24);
    if ( !v7 )
    {
      v2 = 1078;
      goto LABEL_9;
    }
    if ( *(_DWORD *)(v5 + 8) == 196620 )
    {
      v11 = SymCryptMlDsakeyAllocate(*(unsigned int *)(v7 + 24));
      v9 = v11;
      if ( !v11 )
      {
        v2 = 1089;
        goto LABEL_17;
      }
      v12 = SymCryptMlDsakeyGenerate(v11, *(unsigned int *)(v6 + 36));
      if ( v12 )
      {
        v3 = SymcryptErrorCodeToNtStatus(v12);
        DebugTraceError(v3, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", 1097);
        SymCryptMlDsakeyFree(v9);
        return v3;
      }
    }
    else
    {
      if ( *(_DWORD *)(v5 + 8) != 196621 )
      {
        v2 = 1129;
        goto LABEL_9;
      }
      v8 = SymCryptCompositeMlDsakeyAllocate(*(unsigned int *)(v7 + 24));
      v9 = v8;
      if ( !v8 )
      {
        v2 = 1110;
LABEL_17:
        v3 = -1073741801;
        v4 = 3221225495LL;
        goto LABEL_4;
      }
      v10 = SymCryptCompositeMlDsakeyGenerate(v8, *(unsigned int *)(v6 + 36));
      if ( v10 )
      {
        v3 = SymcryptErrorCodeToNtStatus(v10);
        DebugTraceError(v3, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", 1118);
        SymCryptCompositeMlDsakeyFree(v9);
        return v3;
      }
    }
    *(_QWORD *)(v6 + 40) = v9;
    *(_DWORD *)(v6 + 32) = 1;
    return 0;
  }
  v2 = 1053;
LABEL_3:
  v3 = -1073741811;
  v4 = 3221225485LL;
LABEL_4:
  DebugTraceError(v4, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", v2);
  return v3;
}

```

## disassembly

```asm
0x180078e60  mov     [rsp+arg_0], rbx
0x180078e65  push    rdi
0x180078e66  sub     rsp, 20h
0x180078e6a  test    rcx, rcx
0x180078e6d  jnz     short loc_180078E97
0x180078e6f  mov     r9d, 41Dh
0x180078e75  mov     ebx, 0C000000Dh
0x180078e7a  mov     ecx, 0C000000Dh
0x180078e7f  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180078e86  lea     rdx, aStatus_0; "status"
0x180078e8d  call    DebugTraceError
0x180078e92  jmp     loc_180078FB5
0x180078e97  test    edx, edx
0x180078e99  jz      short loc_180078EA3
0x180078e9b  mov     r9d, 424h
0x180078ea1  jmp     short loc_180078E75
0x180078ea3  xor     edx, edx
0x180078ea5  call    validatePqDsaKey
0x180078eaa  mov     rbx, rax
0x180078ead  test    rax, rax
0x180078eb0  jnz     short loc_180078EC4
0x180078eb2  mov     r9d, 42Ch
0x180078eb8  mov     ebx, 0C0000008h
0x180078ebd  mov     ecx, 0C0000008h
0x180078ec2  jmp     short loc_180078E7F
0x180078ec4  mov     rdx, [rax+18h]
0x180078ec8  test    rdx, rdx
0x180078ecb  jnz     short loc_180078ED5
0x180078ecd  mov     r9d, 436h
0x180078ed3  jmp     short loc_180078EB8
0x180078ed5  mov     ecx, [rax+8]
0x180078ed8  sub     ecx, 3000Ch
0x180078ede  jz      short loc_180078F53
0x180078ee0  cmp     ecx, 1
0x180078ee3  jz      short loc_180078EED
0x180078ee5  mov     r9d, 469h
0x180078eeb  jmp     short loc_180078EB8
0x180078eed  mov     ecx, [rdx+18h]
0x180078ef0  call    SymCryptCompositeMlDsakeyAllocate
0x180078ef5  mov     rdi, rax
0x180078ef8  test    rax, rax
0x180078efb  jnz     short loc_180078F12
0x180078efd  mov     r9d, 456h
0x180078f03  mov     ebx, 0C0000017h
0x180078f08  mov     ecx, 0C0000017h
0x180078f0d  jmp     loc_180078E7F
0x180078f12  mov     edx, [rbx+24h]
0x180078f15  mov     rcx, rdi
0x180078f18  call    SymCryptCompositeMlDsakeyGenerate
0x180078f1d  test    eax, eax
0x180078f1f  jz      loc_180078FA8
0x180078f25  mov     ecx, eax
0x180078f27  call    SymcryptErrorCodeToNtStatus
0x180078f2c  mov     ecx, eax
0x180078f2e  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180078f35  mov     r9d, 45Eh
0x180078f3b  lea     rdx, aStatus_0; "status"
0x180078f42  mov     ebx, eax
0x180078f44  call    DebugTraceError
0x180078f49  mov     rcx, rdi
0x180078f4c  call    SymCryptCompositeMlDsakeyFree
0x180078f51  jmp     short loc_180078FB5
0x180078f53  mov     ecx, [rdx+18h]
0x180078f56  call    SymCryptMlDsakeyAllocate
0x180078f5b  mov     rdi, rax
0x180078f5e  test    rax, rax
0x180078f61  jnz     short loc_180078F6B
0x180078f63  mov     r9d, 441h
0x180078f69  jmp     short loc_180078F03
0x180078f6b  mov     edx, [rbx+24h]
0x180078f6e  mov     rcx, rdi
0x180078f71  call    SymCryptMlDsakeyGenerate
0x180078f76  test    eax, eax
0x180078f78  jz      short loc_180078FA8
0x180078f7a  mov     ecx, eax
0x180078f7c  call    SymcryptErrorCodeToNtStatus
0x180078f81  mov     ecx, eax
0x180078f83  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180078f8a  mov     r9d, 449h
0x180078f90  lea     rdx, aStatus_0; "status"
0x180078f97  mov     ebx, eax
0x180078f99  call    DebugTraceError
0x180078f9e  mov     rcx, rdi
0x180078fa1  call    SymCryptMlDsakeyFree
0x180078fa6  jmp     short loc_180078FB5
0x180078fa8  mov     [rbx+28h], rdi
0x180078fac  mov     dword ptr [rbx+20h], 1
0x180078fb3  xor     ebx, ebx
0x180078fb5  mov     eax, ebx
0x180078fb7  mov     rbx, [rsp+28h+arg_0]
0x180078fbc  add     rsp, 20h
0x180078fc0  pop     rdi
0x180078fc1  retn
```
