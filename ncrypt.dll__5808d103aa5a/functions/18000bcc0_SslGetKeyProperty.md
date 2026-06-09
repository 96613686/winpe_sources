# SslGetKeyProperty

- ea: `0x18000bcc0`
- end: `0x18000be5a`
- name: `SslGetKeyProperty`
- size: `410`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18000bcc0`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180020010`

## string_xrefs

- `0x18000bd07`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000bd66`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000bdf9`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000be18`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000be40`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslGetKeyProperty(
        __int64 a1,
        NCRYPT_KEY_HANDLE *a2,
        NCryptKeyName **a3,
        PVOID *a4,
        DWORD a5)
{
  unsigned int v5; // ebx
  unsigned __int64 v6; // rax
  int v8; // eax
  NCRYPT_KEY_HANDLE *v9; // rdx
  NCryptKeyName **v10; // r8
  PVOID *v11; // r9

  if ( !a1 || *(_DWORD *)a1 < 0x20u || *(_DWORD *)(a1 + 4) != 1145324610 )
  {
    v5 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        232);
    return NormalizeNteStatus(v5, a2, a3, a4, a5);
  }
  if ( !a2 )
  {
    v5 = -2146893785;
    DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 2287);
    return NormalizeNteStatus(v5, a2, a3, a4, a5);
  }
  v6 = -1;
  do
    ++v6;
  while ( *((_WORD *)a2 + v6) );
  if ( v6 > 0x40 )
  {
    v5 = -2146893785;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        245);
    return NormalizeNteStatus(v5, a2, a3, a4, a5);
  }
  if ( !a3 || !a4 )
  {
    v5 = -2146893785;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        252);
    return NormalizeNteStatus(v5, a2, a3, a4, a5);
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)(a1 + 24) + 144LL))(*(_QWORD *)(a1 + 16));
  v5 = v8;
  if ( v8 < 0 )
  {
    DebugTraceError((unsigned int)v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 2316);
    return NormalizeNteStatus(v5, a2, a3, a4, a5);
  }
  return NormalizeNteStatus(0, v9, v10, v11, a5);
}

```

## disassembly

```asm
0x18000bcc0  push    rbx
0x18000bcc2  sub     rsp, 40h
0x18000bcc6  test    rcx, rcx
0x18000bcc9  jz      short loc_18000BCD9
0x18000bccb  cmp     dword ptr [rcx], 20h ; ' '
0x18000bcce  jb      short loc_18000BCD9
0x18000bcd0  cmp     dword ptr [rcx+4], 44444442h
0x18000bcd7  jz      short loc_18000BD1D
0x18000bcd9  mov     ebx, 80090026h
0x18000bcde  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bce5  lea     rax, WPP_GLOBAL_Control
0x18000bcec  cmp     rcx, rax
0x18000bcef  jz      loc_18000BD8A
0x18000bcf5  test    byte ptr [rcx+1Ch], 1
0x18000bcf9  jz      loc_18000BD8A
0x18000bcff  mov     [rsp+48h+var_18], 8E8h
0x18000bd07  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bd0e  mov     [rsp+48h+var_20], rax
0x18000bd13  mov     [rsp+48h+var_28], 80090026h
0x18000bd1b  jmp     short loc_18000BD7A
0x18000bd1d  test    rdx, rdx
0x18000bd20  jz      loc_18000BE12
0x18000bd26  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000bd2d  nop     dword ptr [rax]
0x18000bd30  inc     rax
0x18000bd33  cmp     word ptr [rdx+rax*2], 0
0x18000bd38  jnz     short loc_18000BD30
0x18000bd3a  cmp     rax, 40h ; '@'
0x18000bd3e  jbe     short loc_18000BD96
0x18000bd40  mov     ebx, 80090027h
0x18000bd45  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd4c  lea     rax, WPP_GLOBAL_Control
0x18000bd53  cmp     rcx, rax
0x18000bd56  jz      short loc_18000BD8A
0x18000bd58  test    byte ptr [rcx+1Ch], 1
0x18000bd5c  jz      short loc_18000BD8A
0x18000bd5e  mov     [rsp+48h+var_18], 8F5h
0x18000bd66  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bd6d  mov     [rsp+48h+var_20], rax
0x18000bd72  mov     [rsp+48h+var_28], 80090027h
0x18000bd7a  mov     rcx, [rcx+10h]
0x18000bd7e  lea     r9, aStatus; "Status"
0x18000bd85  call    WPP_SF_sDsd
0x18000bd8a  mov     ecx, ebx
0x18000bd8c  add     rsp, 40h
0x18000bd90  pop     rbx
0x18000bd91  jmp     NormalizeNteStatus
0x18000bd96  test    r8, r8
0x18000bd99  jz      short loc_18000BDD3
0x18000bd9b  test    r9, r9
0x18000bd9e  jz      short loc_18000BDD3
0x18000bda0  mov     rax, [rcx+18h]
0x18000bda4  mov     rcx, [rcx+10h]
0x18000bda8  mov     r10, [rax+90h]
0x18000bdaf  mov     eax, [rsp+48h+arg_20]
0x18000bdb3  mov     [rsp+48h+var_28], eax
0x18000bdb7  mov     rax, r10
0x18000bdba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdbf  mov     ebx, eax
0x18000bdc1  test    eax, eax
0x18000bdc3  js      short loc_18000BE3A
0x18000bdc5  xor     ebx, ebx
0x18000bdc7  mov     ecx, ebx
0x18000bdc9  add     rsp, 40h
0x18000bdcd  pop     rbx
0x18000bdce  jmp     NormalizeNteStatus
0x18000bdd3  mov     ebx, 80090027h
0x18000bdd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bddf  lea     rax, WPP_GLOBAL_Control
0x18000bde6  cmp     rcx, rax
0x18000bde9  jz      short loc_18000BD8A
0x18000bdeb  test    byte ptr [rcx+1Ch], 1
0x18000bdef  jz      short loc_18000BD8A
0x18000bdf1  mov     [rsp+48h+var_18], 8FCh
0x18000bdf9  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000be00  mov     [rsp+48h+var_20], rax
0x18000be05  mov     [rsp+48h+var_28], 80090027h
0x18000be0d  jmp     loc_18000BD7A
0x18000be12  mov     r9d, 8EFh
0x18000be18  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000be1f  lea     rdx, aStatus; "Status"
0x18000be26  mov     ecx, 80090027h
0x18000be2b  mov     ebx, 80090027h
0x18000be30  call    DebugTraceError
0x18000be35  jmp     loc_18000BD8A
0x18000be3a  mov     r9d, 90Ch
0x18000be40  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000be47  lea     rdx, aStatus; "Status"
0x18000be4e  mov     ecx, eax
0x18000be50  call    DebugTraceError
0x18000be55  jmp     loc_18000BD8A
```
