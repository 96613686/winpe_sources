# SslComputeEapKeyBlock

- ea: `0x18001aa60`
- end: `0x18001ab0f`
- name: `SslComputeEapKeyBlock`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009a70`
- `0x180009ea0`
- `0x18000c8e0`
- `0x18000e120`
- `0x18001aa60`
- `0x180020010`

## string_xrefs

- `0x18001aa8a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslComputeEapKeyBlock(
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
    v8 = 292;
LABEL_3:
    v9 = -2146893786;
    v10 = 2148073510LL;
    goto LABEL_4;
  }
  v14 = ValidateSslKeyHandle(v7);
  if ( !v14 )
  {
    v8 = 300;
    goto LABEL_3;
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(v15 + 48))(*(_QWORD *)(v15 + 424), *(_QWORD *)(v14 + 16));
  v9 = v16;
  if ( v16 >= 0 )
  {
    v9 = 0;
    return NormalizeNteStatus(v9, v11, v12, v13, a5, a6, a7);
  }
  v8 = 319;
  v10 = (unsigned int)v16;
LABEL_4:
  DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v8);
  return NormalizeNteStatus(v9, v11, v12, v13, a5, a6, a7);
}

```

## disassembly

```asm
0x18001aa60  push    rbx
0x18001aa62  sub     rsp, 50h
0x18001aa66  call    ValidateSslProvHandle
0x18001aa6b  mov     r10, rax
0x18001aa6e  test    rax, rax
0x18001aa71  jnz     short loc_18001AA98
0x18001aa73  mov     r9d, 124h
0x18001aa79  mov     ebx, 80090026h
0x18001aa7e  mov     ecx, 80090026h
0x18001aa83  lea     rdx, aStatus; "Status"
0x18001aa8a  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001aa91  call    DebugTraceError
0x18001aa96  jmp     short loc_18001AB03
0x18001aa98  mov     rcx, rdx
0x18001aa9b  call    ValidateSslKeyHandle
0x18001aaa0  test    rax, rax
0x18001aaa3  jnz     short loc_18001AAAD
0x18001aaa5  mov     r9d, 12Ch
0x18001aaab  jmp     short loc_18001AA79
0x18001aaad  mov     ecx, [rsp+58h+arg_38]
0x18001aab4  mov     rdx, [rax+10h]
0x18001aab8  mov     rax, [r10+30h]
0x18001aabc  mov     [rsp+58h+var_20], ecx
0x18001aac0  mov     rcx, [rsp+58h+arg_30]
0x18001aac8  mov     [rsp+58h+var_28], rcx
0x18001aacd  mov     ecx, dword ptr [rsp+58h+arg_28]
0x18001aad4  mov     [rsp+58h+var_30], ecx
0x18001aad8  mov     rcx, [rsp+58h+arg_20]
0x18001aae0  mov     [rsp+58h+var_38], rcx
0x18001aae5  mov     rcx, [r10+1A8h]
0x18001aaec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aaf1  mov     ebx, eax
0x18001aaf3  test    eax, eax
0x18001aaf5  jns     short loc_18001AB01
0x18001aaf7  mov     r9d, 13Fh
0x18001aafd  mov     ecx, eax
0x18001aaff  jmp     short loc_18001AA83
0x18001ab01  xor     ebx, ebx
0x18001ab03  mov     ecx, ebx
0x18001ab05  add     rsp, 50h
0x18001ab09  pop     rbx
0x18001ab0a  jmp     NormalizeNteStatus
```
