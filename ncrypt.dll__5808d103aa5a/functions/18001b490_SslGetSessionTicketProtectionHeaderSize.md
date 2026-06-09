# SslGetSessionTicketProtectionHeaderSize

- ea: `0x18001b490`
- end: `0x18001b4f8`
- name: `SslGetSessionTicketProtectionHeaderSize`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009ea0`
- `0x18000c8e0`
- `0x18000e120`
- `0x18001b490`
- `0x180020010`

## string_xrefs

- `0x18001b4d9`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslGetSessionTicketProtectionHeaderSize(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        BYTE *a5,
        DWORD *a6,
        DWORD *a7)
{
  __int64 v7; // rax
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rcx
  int v11; // eax
  NCRYPT_KEY_HANDLE *v12; // rdx
  NCryptKeyName **v13; // r8
  NCryptAlgorithmName **v14; // r9

  v7 = ValidateSslProvHandle(a1);
  if ( *(_WORD *)(v7 + 32) < 7u )
  {
    v8 = -2146893783;
    v9 = 4980;
    v10 = 2148073513LL;
LABEL_5:
    DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v9);
    return NormalizeNteStatus(v8, v12, v13, v14, a5, a6, a7);
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD))(v7 + 384))(*(_QWORD *)(v7 + 424));
  v8 = v11;
  if ( v11 < 0 )
  {
    v9 = 5007;
    v10 = (unsigned int)v11;
    goto LABEL_5;
  }
  return NormalizeNteStatus(v8, v12, v13, v14, a5, a6, a7);
}

```

## disassembly

```asm
0x18001b490  push    rbx
0x18001b492  sub     rsp, 30h
0x18001b496  call    ValidateSslProvHandle
0x18001b49b  mov     ecx, 7
0x18001b4a0  cmp     cx, [rax+20h]
0x18001b4a4  jbe     short loc_18001B4B8
0x18001b4a6  mov     ebx, 80090029h
0x18001b4ab  mov     r9d, 1374h
0x18001b4b1  mov     ecx, 80090029h
0x18001b4b6  jmp     short loc_18001B4D9
0x18001b4b8  mov     rcx, [rax+1A8h]
0x18001b4bf  mov     rax, [rax+180h]
0x18001b4c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4cb  mov     ebx, eax
0x18001b4cd  test    eax, eax
0x18001b4cf  jns     short loc_18001B4EC
0x18001b4d1  mov     r9d, 138Fh
0x18001b4d7  mov     ecx, eax
0x18001b4d9  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001b4e0  lea     rdx, aStatus; "Status"
0x18001b4e7  call    DebugTraceError
0x18001b4ec  mov     ecx, ebx
0x18001b4ee  add     rsp, 30h
0x18001b4f2  pop     rbx
0x18001b4f3  jmp     NormalizeNteStatus
```
