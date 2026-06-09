# NCryptFinalizeKey

- ea: `0x18000c5b0`
- end: `0x18000c6ec`
- name: `NCryptFinalizeKey`
- size: `316`
- prototype: `SECURITY_STATUS __stdcall(NCRYPT_KEY_HANDLE hKey, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18000a71c`
- `0x18000c5b0`
- `0x18000c8e0`
- `0x18000e120`
- `0x180010684`
- `0x180020010`

## string_xrefs

- `0x18000c5fa`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000c6a0`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
SECURITY_STATUS __stdcall NCryptFinalizeKey(NCRYPT_KEY_HANDLE hKey, DWORD dwFlags)
{
  __int64 v2; // r8
  unsigned int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rcx
  NCRYPT_KEY_HANDLE *v8; // rdx
  NCryptKeyName **v9; // r8
  NCryptAlgorithmName **v10; // r9
  unsigned int v12; // eax
  int v13; // r9d
  DWORD v14; // [rsp+20h] [rbp-18h]
  BYTE *v15; // [rsp+60h] [rbp+28h]
  DWORD *v16; // [rsp+68h] [rbp+30h]
  DWORD *v17; // [rsp+70h] [rbp+38h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v14 = dwFlags;
    WPP_SF_PD(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, v2, hKey);
  }
  if ( hKey && *(_DWORD *)hKey == 1145307138 )
  {
    while ( 1 )
    {
      v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)(hKey + 8) + 80LL))(
              *(_QWORD *)(*(_QWORD *)(hKey + 8) + 272LL),
              *(_QWORD *)(hKey + 16),
              dwFlags);
      v5 = v12;
      if ( v12 != -2146893778 )
      {
        if ( !v12 )
          return NormalizeNteStatus(v5, v8, v9, v10, v15, v16, v17);
LABEL_14:
        DebugTraceError(v5, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", 2113);
        EtwLogNCryptOperationFailed(11, *(_QWORD *)(*(_QWORD *)(hKey + 8) + 280LL), *(_QWORD *)(hKey + 24), v13, v5);
        return NormalizeNteStatus(v5, v8, v9, v10, v15, v16, v17);
      }
      if ( (dwFlags & 0x40) != 0 )
        break;
      v5 = (*(__int64 (__fastcall **)(_QWORD, NCRYPT_KEY_HANDLE, const wchar_t *, _QWORD, DWORD))(*(_QWORD *)(hKey + 8)
                                                                                                + 192LL))(
             *(_QWORD *)(*(_QWORD *)(hKey + 8) + 272LL),
             hKey,
             L"NCryptFinalizeKey",
             0,
             v14);
      if ( v5 )
        goto LABEL_14;
    }
    v5 = -2146893790;
    v6 = 2095;
    v7 = 2148073506LL;
  }
  else
  {
    v5 = -2146893786;
    v6 = 2075;
    v7 = 2148073510LL;
  }
  DebugTraceError(v7, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", v6);
  return NormalizeNteStatus(v5, v8, v9, v10, v15, v16, v17);
}

```

## disassembly

```asm
0x18000c5b0  mov     [rsp+arg_0], rbx
0x18000c5b5  mov     [rsp+arg_8], rsi
0x18000c5ba  push    rdi
0x18000c5bb  sub     rsp, 30h
0x18000c5bf  mov     esi, edx
0x18000c5c1  mov     rdi, rcx
0x18000c5c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5cb  lea     rax, WPP_GLOBAL_Control
0x18000c5d2  cmp     rcx, rax
0x18000c5d5  jz      short loc_18000C5DD
0x18000c5d7  test    byte ptr [rcx+1Ch], 4
0x18000c5db  jnz     short loc_18000C623
0x18000c5dd  test    rdi, rdi
0x18000c5e0  jz      short loc_18000C5EA
0x18000c5e2  cmp     dword ptr [rdi], 44440002h
0x18000c5e8  jz      short loc_18000C640
0x18000c5ea  mov     ebx, 80090026h
0x18000c5ef  mov     r9d, 81Bh
0x18000c5f5  mov     ecx, 80090026h
0x18000c5fa  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c601  lea     rdx, aStatus; "Status"
0x18000c608  call    DebugTraceError
0x18000c60d  mov     ecx, ebx
0x18000c60f  mov     rbx, [rsp+38h+arg_0]
0x18000c614  mov     rsi, [rsp+38h+arg_8]
0x18000c619  add     rsp, 30h
0x18000c61d  pop     rdi
0x18000c61e  jmp     NormalizeNteStatus
0x18000c623  mov     rcx, [rcx+10h]
0x18000c627  mov     edx, 12h
0x18000c62c  mov     r9, rdi
0x18000c62f  mov     [rsp+38h+var_18], esi
0x18000c633  call    WPP_SF_PD
0x18000c638  jmp     short loc_18000C5DD
0x18000c640  mov     rcx, [rdi+8]
0x18000c644  mov     r8d, esi
0x18000c647  mov     rdx, [rdi+10h]
0x18000c64b  mov     rax, [rcx+50h]
0x18000c64f  mov     rcx, [rcx+110h]
0x18000c656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c65b  mov     ebx, eax
0x18000c65d  cmp     eax, 8009002Eh
0x18000c662  jz      short loc_18000C66A
0x18000c664  test    eax, eax
0x18000c666  jnz     short loc_18000C69A
0x18000c668  jmp     short loc_18000C60D
0x18000c66a  test    sil, 40h
0x18000c66e  jnz     short loc_18000C6D7
0x18000c670  mov     rcx, [rdi+8]
0x18000c674  lea     r8, aNcryptfinalize_0; "NCryptFinalizeKey"
0x18000c67b  xor     r9d, r9d
0x18000c67e  mov     rdx, rdi
0x18000c681  mov     rax, [rcx+0C0h]
0x18000c688  mov     rcx, [rcx+110h]
0x18000c68f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c694  mov     ebx, eax
0x18000c696  test    eax, eax
0x18000c698  jz      short loc_18000C640
0x18000c69a  mov     r9d, 841h
0x18000c6a0  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c6a7  lea     rdx, aStatus; "Status"
0x18000c6ae  mov     ecx, ebx
0x18000c6b0  call    DebugTraceError
0x18000c6b5  mov     rdx, [rdi+8]
0x18000c6b9  mov     ecx, 0Bh
0x18000c6be  mov     r8, [rdi+18h]
0x18000c6c2  mov     [rsp+38h+var_18], ebx
0x18000c6c6  mov     rdx, [rdx+118h]
0x18000c6cd  call    EtwLogNCryptOperationFailed
0x18000c6d2  jmp     loc_18000C60D
0x18000c6d7  mov     ebx, 80090022h
0x18000c6dc  mov     r9d, 82Fh
0x18000c6e2  mov     ecx, 80090022h
0x18000c6e7  jmp     loc_18000C5FA
```
