# NCryptNotifyChangeKey

- ea: `0x18001c2c0`
- end: `0x18001c38b`
- name: `NCryptNotifyChangeKey`
- size: `203`
- prototype: `SECURITY_STATUS __stdcall(NCRYPT_PROV_HANDLE hProvider, HANDLE *phEvent, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18000a71c`
- `0x18000c8e0`
- `0x18000cb50`
- `0x18000e120`
- `0x180011cb0`
- `0x18001c2c0`
- `0x180020010`

## string_xrefs

- `0x18001c317`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18001c35b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
SECURITY_STATUS __stdcall NCryptNotifyChangeKey(NCRYPT_PROV_HANDLE hProvider, HANDLE *phEvent, DWORD dwFlags)
{
  __int64 v6; // rax
  __int64 v7; // rdi
  unsigned int v8; // ebx
  NCRYPT_KEY_HANDLE *v9; // rdx
  NCryptKeyName **v10; // r8
  NCryptAlgorithmName **v11; // r9
  unsigned int v12; // eax
  BYTE *v14; // [rsp+80h] [rbp+28h]
  DWORD *v15; // [rsp+88h] [rbp+30h]
  DWORD *v16; // [rsp+90h] [rbp+38h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_PD(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, *(_QWORD *)&dwFlags, hProvider);
  v6 = ValidateAndReferenceProvider(hProvider);
  v7 = v6;
  if ( v6 )
  {
    v12 = (*(__int64 (__fastcall **)(_QWORD, HANDLE *, _QWORD))(v6 + 200))(*(_QWORD *)(v6 + 272), phEvent, dwFlags);
    v8 = v12;
    if ( v12 )
      DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", 4219);
    else
      v8 = 0;
    DereferenceProvider(v7);
  }
  else
  {
    v8 = -2146893786;
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", 4208);
  }
  return NormalizeNteStatus(v8, v9, v10, v11, v14, v15, v16);
}

```

## disassembly

```asm
0x18001c2c0  push    rbx
0x18001c2c2  push    rbp
0x18001c2c3  push    rsi
0x18001c2c4  push    rdi
0x18001c2c5  sub     rsp, 38h
0x18001c2c9  mov     esi, r8d
0x18001c2cc  mov     rbp, rdx
0x18001c2cf  mov     rbx, rcx
0x18001c2d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2d9  lea     rax, WPP_GLOBAL_Control
0x18001c2e0  cmp     rcx, rax
0x18001c2e3  jz      short loc_18001C301
0x18001c2e5  test    byte ptr [rcx+1Ch], 4
0x18001c2e9  jz      short loc_18001C301
0x18001c2eb  mov     rcx, [rcx+10h]
0x18001c2ef  mov     edx, 22h ; '"'
0x18001c2f4  mov     r9, rbx
0x18001c2f7  mov     [rsp+58h+var_38], r8d
0x18001c2fc  call    WPP_SF_PD
0x18001c301  mov     rcx, rbx
0x18001c304  call    ValidateAndReferenceProvider
0x18001c309  mov     rdi, rax
0x18001c30c  test    rax, rax
0x18001c30f  jnz     short loc_18001C336
0x18001c311  mov     r9d, 1070h
0x18001c317  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001c31e  lea     rdx, aStatus; "Status"
0x18001c325  mov     ecx, 80090026h
0x18001c32a  mov     ebx, 80090026h
0x18001c32f  call    DebugTraceError
0x18001c334  jmp     short loc_18001C37C
0x18001c336  mov     rcx, [rax+110h]
0x18001c33d  mov     r8d, esi
0x18001c340  mov     rax, [rax+0C8h]
0x18001c347  mov     rdx, rbp
0x18001c34a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c34f  mov     ebx, eax
0x18001c351  test    eax, eax
0x18001c353  jz      short loc_18001C372
0x18001c355  mov     r9d, 107Bh
0x18001c35b  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001c362  lea     rdx, aStatus; "Status"
0x18001c369  mov     ecx, eax
0x18001c36b  call    DebugTraceError
0x18001c370  jmp     short loc_18001C374
0x18001c372  xor     ebx, ebx
0x18001c374  mov     rcx, rdi
0x18001c377  call    DereferenceProvider
0x18001c37c  mov     ecx, ebx
0x18001c37e  add     rsp, 38h
0x18001c382  pop     rdi
0x18001c383  pop     rsi
0x18001c384  pop     rbp
0x18001c385  pop     rbx
0x18001c386  jmp     NormalizeNteStatus
```
