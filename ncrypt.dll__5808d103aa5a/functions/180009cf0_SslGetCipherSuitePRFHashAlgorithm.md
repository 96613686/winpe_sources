# SslGetCipherSuitePRFHashAlgorithm

- ea: `0x180009cf0`
- end: `0x180009e41`
- name: `SslGetCipherSuitePRFHashAlgorithm`
- size: `337`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009cf0`
- `0x180009ea0`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180020010`

## string_xrefs

- `0x180009d6e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180009dc4`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180009e00`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180009e1f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslGetCipherSuitePRFHashAlgorithm(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        NCRYPT_KEY_HANDLE *a5)
{
  __int64 v5; // rax
  NCRYPT_KEY_HANDLE *v6; // rdx
  NCryptKeyName **v7; // r8
  PVOID *v8; // r9
  unsigned int v9; // r10d
  int v10; // ebx

  v5 = ValidateSslProvHandle(a1);
  if ( v5 )
  {
    v6 = a5;
    if ( a5 )
    {
      if ( *(_WORD *)(v5 + 32) < 2u )
      {
        v10 = -2146893783;
        DebugTraceError(2148073513LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 882);
      }
      else
      {
        v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(v5 + 240))(*(_QWORD *)(v5 + 424), v9);
        if ( v10 >= 0 )
        {
          v10 = 0;
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)v6,
            (_DWORD)v7,
            (unsigned int)"Status",
            v10,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
            132);
        }
      }
    }
    else
    {
      v10 = -2146893785;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          0,
          (_DWORD)v7,
          (unsigned int)"Status",
          39,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          100);
    }
  }
  else
  {
    v10 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)v6,
        (_DWORD)v7,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        93);
  }
  return NormalizeNteStatus((unsigned int)v10, v6, v7, v8, (DWORD)a5);
}

```

## disassembly

```asm
0x180009cf0  push    rbx
0x180009cf2  sub     rsp, 40h
0x180009cf6  mov     r10d, edx
0x180009cf9  call    ValidateSslProvHandle
0x180009cfe  test    rax, rax
0x180009d01  jz      loc_180009D9E
0x180009d07  mov     rdx, [rsp+48h+arg_20]
0x180009d0c  test    rdx, rdx
0x180009d0f  jz      loc_180009DDA
0x180009d15  mov     ecx, 2
0x180009d1a  cmp     cx, [rax+20h]
0x180009d1e  ja      loc_180009E19
0x180009d24  mov     ecx, [rsp+48h+arg_28]
0x180009d28  mov     dword ptr [rsp+48h+var_20], ecx
0x180009d2c  mov     rcx, [rax+1A8h]
0x180009d33  mov     rax, [rax+0F0h]
0x180009d3a  mov     [rsp+48h+var_28], rdx
0x180009d3f  mov     edx, r10d
0x180009d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d47  mov     ebx, eax
0x180009d49  test    eax, eax
0x180009d4b  jns     short loc_180009D9A
0x180009d4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d54  lea     rax, WPP_GLOBAL_Control
0x180009d5b  cmp     rcx, rax
0x180009d5e  jz      short loc_180009D8E
0x180009d60  test    byte ptr [rcx+1Ch], 1
0x180009d64  jz      short loc_180009D8E
0x180009d66  mov     [rsp+48h+var_18], 384h
0x180009d6e  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009d75  mov     [rsp+48h+var_20], rax
0x180009d7a  mov     dword ptr [rsp+48h+var_28], ebx
0x180009d7e  mov     rcx, [rcx+10h]
0x180009d82  lea     r9, aStatus; "Status"
0x180009d89  call    WPP_SF_sDsd
0x180009d8e  mov     ecx, ebx
0x180009d90  add     rsp, 40h
0x180009d94  pop     rbx
0x180009d95  jmp     NormalizeNteStatus
0x180009d9a  xor     ebx, ebx
0x180009d9c  jmp     short loc_180009D8E
0x180009d9e  mov     ebx, 80090026h
0x180009da3  mov     rcx, cs:WPP_GLOBAL_Control
0x180009daa  lea     rax, WPP_GLOBAL_Control
0x180009db1  cmp     rcx, rax
0x180009db4  jz      short loc_180009D8E
0x180009db6  test    byte ptr [rcx+1Ch], 1
0x180009dba  jz      short loc_180009D8E
0x180009dbc  mov     [rsp+48h+var_18], 35Dh
0x180009dc4  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009dcb  mov     [rsp+48h+var_20], rax
0x180009dd0  mov     dword ptr [rsp+48h+var_28], 80090026h
0x180009dd8  jmp     short loc_180009D7E
0x180009dda  mov     ebx, 80090027h
0x180009ddf  mov     rcx, cs:WPP_GLOBAL_Control
0x180009de6  lea     rax, WPP_GLOBAL_Control
0x180009ded  cmp     rcx, rax
0x180009df0  jz      short loc_180009D8E
0x180009df2  test    byte ptr [rcx+1Ch], 1
0x180009df6  jz      short loc_180009D8E
0x180009df8  mov     [rsp+48h+var_18], 364h
0x180009e00  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009e07  mov     [rsp+48h+var_20], rax
0x180009e0c  mov     dword ptr [rsp+48h+var_28], 80090027h
0x180009e14  jmp     loc_180009D7E
0x180009e19  mov     r9d, 372h
0x180009e1f  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009e26  lea     rdx, aStatus; "Status"
0x180009e2d  mov     ecx, 80090029h
0x180009e32  mov     ebx, 80090029h
0x180009e37  call    DebugTraceError
0x180009e3c  jmp     loc_180009D8E
```
