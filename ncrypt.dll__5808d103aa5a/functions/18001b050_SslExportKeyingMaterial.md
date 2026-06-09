# SslExportKeyingMaterial

- ea: `0x18001b050`
- end: `0x18001b137`
- name: `SslExportKeyingMaterial`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009a70`
- `0x180009ea0`
- `0x18000c8e0`
- `0x18000e120`
- `0x18001b050`
- `0x180020010`

## string_xrefs

- `0x18001b118`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslExportKeyingMaterial(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        BYTE *a5,
        DWORD *a6,
        DWORD *a7)
{
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // r10
  unsigned int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rcx
  int v13; // eax
  NCRYPT_KEY_HANDLE *v14; // rdx
  NCryptKeyName **v15; // r8
  NCryptAlgorithmName **v16; // r9

  ValidateSslProvHandle(a1);
  v8 = ValidateSslKeyHandle(v7);
  if ( !v9 || !v8 )
  {
    v10 = -2146893786;
    v11 = 381;
    v12 = 2148073510LL;
    goto LABEL_8;
  }
  if ( *(_WORD *)(v9 + 32) < 3u )
  {
    v10 = -2146893783;
    v11 = 395;
    v12 = 2148073513LL;
LABEL_8:
    DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v11);
    return NormalizeNteStatus(v10, v14, v15, v16, a5, a6, a7);
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(v9 + 272))(*(_QWORD *)(v9 + 424), *(_QWORD *)(v8 + 16));
  v10 = v13;
  if ( v13 < 0 )
  {
    v11 = 416;
    v12 = (unsigned int)v13;
    goto LABEL_8;
  }
  return NormalizeNteStatus(v10, v14, v15, v16, a5, a6, a7);
}

```

## disassembly

```asm
0x18001b050  push    rbx
0x18001b052  sub     rsp, 60h
0x18001b056  call    ValidateSslProvHandle
0x18001b05b  mov     rcx, rdx
0x18001b05e  mov     r10, rax
0x18001b061  call    ValidateSslKeyHandle
0x18001b066  mov     rdx, rax
0x18001b069  test    r10, r10
0x18001b06c  jz      loc_18001B108
0x18001b072  test    rax, rax
0x18001b075  jz      loc_18001B108
0x18001b07b  mov     eax, 3
0x18001b080  cmp     ax, [r10+20h]
0x18001b085  jbe     short loc_18001B099
0x18001b087  mov     ebx, 80090029h
0x18001b08c  mov     r9d, 18Bh
0x18001b092  mov     ecx, 80090029h
0x18001b097  jmp     short loc_18001B118
0x18001b099  mov     eax, [rsp+68h+arg_48]
0x18001b0a0  mov     ecx, [rsp+68h+arg_40]
0x18001b0a7  mov     rdx, [rdx+10h]
0x18001b0ab  mov     [rsp+68h+var_20], eax
0x18001b0af  mov     rax, [r10+110h]
0x18001b0b6  mov     [rsp+68h+var_28], ecx
0x18001b0ba  mov     rcx, [rsp+68h+arg_38]
0x18001b0c2  mov     [rsp+68h+var_30], rcx
0x18001b0c7  movzx   ecx, word ptr [rsp+68h+arg_30]
0x18001b0cf  mov     [rsp+68h+var_38], cx
0x18001b0d4  mov     rcx, [rsp+68h+arg_28]
0x18001b0dc  mov     [rsp+68h+var_40], rcx
0x18001b0e1  mov     ecx, dword ptr [rsp+68h+arg_20]
0x18001b0e8  mov     [rsp+68h+var_48], ecx
0x18001b0ec  mov     rcx, [r10+1A8h]
0x18001b0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0f8  mov     ebx, eax
0x18001b0fa  test    eax, eax
0x18001b0fc  jns     short loc_18001B12B
0x18001b0fe  mov     r9d, 1A0h
0x18001b104  mov     ecx, eax
0x18001b106  jmp     short loc_18001B118
0x18001b108  mov     ebx, 80090026h
0x18001b10d  mov     r9d, 17Dh
0x18001b113  mov     ecx, 80090026h
0x18001b118  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001b11f  lea     rdx, aStatus; "Status"
0x18001b126  call    DebugTraceError
0x18001b12b  mov     ecx, ebx
0x18001b12d  add     rsp, 60h
0x18001b131  pop     rbx
0x18001b132  jmp     NormalizeNteStatus
```
