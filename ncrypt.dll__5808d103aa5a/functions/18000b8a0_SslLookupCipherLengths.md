# SslLookupCipherLengths

- ea: `0x18000b8a0`
- end: `0x18000ba1c`
- name: `SslLookupCipherLengths`
- size: `380`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18000b8a0`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180020010`

## string_xrefs

- `0x18000b8f0`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000b9a4`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000b9e3`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000ba02`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslLookupCipherLengths(
        __int64 a1,
        NCRYPT_KEY_HANDLE *a2,
        NCryptKeyName **a3,
        PVOID *a4,
        __int64 a5,
        unsigned int a6)
{
  unsigned int v6; // ebx
  int v7; // eax

  if ( a1 && *(_DWORD *)a1 >= 0x1B0u && *(_DWORD *)(a1 + 4) == 1145324609 && !*(_DWORD *)(a1 + 12) )
  {
    if ( a5 && a6 >= 0x14 )
    {
      if ( *(_WORD *)(a1 + 32) < 2u )
      {
        v6 = -2146893783;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)a2,
            (_DWORD)a3,
            (unsigned int)"Status",
            41,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
            190);
      }
      else
      {
        v7 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 224))(*(_QWORD *)(a1 + 424));
        v6 = v7;
        if ( v7 < 0 )
          DebugTraceError((unsigned int)v7, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 976);
        else
          v6 = 0;
      }
    }
    else
    {
      v6 = -2146893785;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)a2,
          (_DWORD)a3,
          (unsigned int)"Status",
          39,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          176);
    }
  }
  else
  {
    v6 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        168);
  }
  return NormalizeNteStatus(v6, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000b8a0  push    rbx
0x18000b8a2  sub     rsp, 40h
0x18000b8a6  test    rcx, rcx
0x18000b8a9  jz      short loc_18000B8C2
0x18000b8ab  cmp     dword ptr [rcx], 1B0h
0x18000b8b1  jb      short loc_18000B8C2
0x18000b8b3  cmp     dword ptr [rcx+4], 44444441h
0x18000b8ba  jnz     short loc_18000B8C2
0x18000b8bc  cmp     dword ptr [rcx+0Ch], 0
0x18000b8c0  jz      short loc_18000B916
0x18000b8c2  mov     ebx, 80090026h
0x18000b8c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8ce  lea     rax, WPP_GLOBAL_Control
0x18000b8d5  cmp     rcx, rax
0x18000b8d8  jz      loc_18000B972
0x18000b8de  test    byte ptr [rcx+1Ch], 1
0x18000b8e2  jz      loc_18000B972
0x18000b8e8  mov     [rsp+48h+var_18], 3A8h
0x18000b8f0  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b8f7  mov     [rsp+48h+var_20], rax
0x18000b8fc  mov     dword ptr [rsp+48h+var_28], 80090026h
0x18000b904  mov     rcx, [rcx+10h]
0x18000b908  lea     r9, aStatus; "Status"
0x18000b90f  call    WPP_SF_sDsd
0x18000b914  jmp     short loc_18000B972
0x18000b916  mov     r11, [rsp+48h+arg_20]
0x18000b91b  test    r11, r11
0x18000b91e  jz      loc_18000B9BD
0x18000b924  mov     ebx, [rsp+48h+arg_28]
0x18000b928  cmp     ebx, 14h
0x18000b92b  jb      loc_18000B9BD
0x18000b931  mov     eax, 2
0x18000b936  cmp     ax, [rcx+20h]
0x18000b93a  ja      short loc_18000B97E
0x18000b93c  mov     r10, [rcx+0E0h]
0x18000b943  mov     eax, [rsp+48h+arg_30]
0x18000b94a  mov     rcx, [rcx+1A8h]
0x18000b951  mov     [rsp+48h+var_18], eax
0x18000b955  mov     rax, r10
0x18000b958  mov     dword ptr [rsp+48h+var_20], ebx
0x18000b95c  mov     [rsp+48h+var_28], r11
0x18000b961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b966  mov     ebx, eax
0x18000b968  test    eax, eax
0x18000b96a  js      loc_18000B9FC
0x18000b970  xor     ebx, ebx
0x18000b972  mov     ecx, ebx
0x18000b974  add     rsp, 40h
0x18000b978  pop     rbx
0x18000b979  jmp     NormalizeNteStatus
0x18000b97e  mov     ebx, 80090029h
0x18000b983  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b98a  lea     rax, WPP_GLOBAL_Control
0x18000b991  cmp     rcx, rax
0x18000b994  jz      short loc_18000B972
0x18000b996  test    byte ptr [rcx+1Ch], 1
0x18000b99a  jz      short loc_18000B972
0x18000b99c  mov     [rsp+48h+var_18], 3BEh
0x18000b9a4  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b9ab  mov     [rsp+48h+var_20], rax
0x18000b9b0  mov     dword ptr [rsp+48h+var_28], 80090029h
0x18000b9b8  jmp     loc_18000B904
0x18000b9bd  mov     ebx, 80090027h
0x18000b9c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b9c9  lea     rax, WPP_GLOBAL_Control
0x18000b9d0  cmp     rcx, rax
0x18000b9d3  jz      short loc_18000B972
0x18000b9d5  test    byte ptr [rcx+1Ch], 1
0x18000b9d9  jz      short loc_18000B972
0x18000b9db  mov     [rsp+48h+var_18], 3B0h
0x18000b9e3  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b9ea  mov     [rsp+48h+var_20], rax
0x18000b9ef  mov     dword ptr [rsp+48h+var_28], 80090027h
0x18000b9f7  jmp     loc_18000B904
0x18000b9fc  mov     r9d, 3D0h
0x18000ba02  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ba09  lea     rdx, aStatus; "Status"
0x18000ba10  mov     ecx, eax
0x18000ba12  call    DebugTraceError
0x18000ba17  jmp     loc_18000B972
```
