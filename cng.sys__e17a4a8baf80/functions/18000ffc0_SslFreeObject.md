# SslFreeObject

- ea: `0x18000ffc0`
- end: `0x1800102a8`
- name: `SslFreeObject`
- size: `744`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000ffc0`
- `0x180010590`
- `0x18001155c`
- `0x1800123d0`
- `0x1800440f0`
- `0x180046db4`
- `0x1800a4300`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18001004b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001004b`
- `ntoskrnl!SkIsSecureKernel` at `0x18001024c`
- `ntoskrnl!SkIsSecureKernel` at `0x18001024c`
- `ntoskrnl!SkFreePool` at `0x1800101ab`
- `ntoskrnl!SkFreePool` at `0x1800101ab`

## string_xrefs

- `0x18001009b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180010107`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18001016d`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180010232`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x1800a5b7f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
__int64 __fastcall SslFreeObject(_DWORD *P, int a2)
{
  int v3; // eax
  unsigned int *v4; // rbx
  int v5; // eax
  __int64 v6; // rdx
  unsigned int v7; // esi
  __int64 v8; // rcx
  _BYTE *v9; // rax
  int v10; // eax
  int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  _BYTE *v15; // r8
  __int64 (__fastcall **v16)(_QWORD); // rbx
  int v17; // eax
  unsigned int v18; // esi

  if ( !P )
  {
    v7 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        100);
      return 3221225480LL;
    }
    return v7;
  }
  v3 = P[1];
  if ( v3 == 1145324610 )
  {
    if ( *P >= 0x20u )
    {
      v4 = (unsigned int *)*((_QWORD *)P + 3);
      v5 = (*((__int64 (__fastcall **)(_QWORD))v4 + 15))(*((_QWORD *)P + 2));
      v7 = v5;
      if ( v5 < 0 )
        DebugTraceError((unsigned int)v5, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 1951);
      v8 = (unsigned int)*P;
      v9 = P;
      if ( *P )
      {
        do
        {
          *v9++ = 0;
          --v8;
        }
        while ( v8 );
      }
      LOBYTE(v10) = g_TrustedEnvironment;
      if ( !g_TrustedEnvironment )
      {
        v10 = ((int)SkIsSecureKernel(v8, v6) >> 31) + 2;
        g_TrustedEnvironment = v10;
      }
      if ( (v10 & 2) != 0 )
        SkFreePool(512, P);
      else
        ExFreePoolWithTag(P, 0x62676E43u);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 4, 0xFFFFFFFF) <= 1 )
      {
        if ( v4[3] )
        {
          (*((void (__fastcall **)(_QWORD, _QWORD))v4 + 15))(*((_QWORD *)v4 + 53), 0);
          UnloadProvider(*((_QWORD *)v4 + 3));
          memset(v4, 0, *v4);
          MSCryptFree(v4);
        }
      }
      return v7;
    }
    v13 = 1917;
    goto LABEL_18;
  }
  v12 = v3 - 1145324609;
  if ( !v12 )
  {
    if ( *P < 0x1B0u || P[3] )
    {
      v13 = 1905;
LABEL_18:
      DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v13);
      return 2148073510LL;
    }
    DereferenceSslProvHandle(P);
    return 0;
  }
  if ( v12 != 2 )
  {
    v7 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        147);
      return 2148073510LL;
    }
    return v7;
  }
  if ( *P < 0x20u )
  {
    v13 = 1930;
    goto LABEL_18;
  }
  v16 = (__int64 (__fastcall **)(_QWORD))*((_QWORD *)P + 3);
  v17 = v16[15](*((_QWORD *)P + 2));
  v18 = v17;
  if ( v17 < 0 )
    DebugTraceError((unsigned int)v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 1966);
  v14 = (unsigned int)*P;
  v15 = P;
  if ( *P )
  {
    do
    {
      *v15++ = 0;
      --v14;
    }
    while ( v14 );
  }
  MSCryptFree(P);
  DereferenceSslProvHandle(v16);
  return v18;
}

```

## disassembly

```asm
0x18000ffc0  mov     [rsp+arg_8], rsi
0x18000ffc5  push    rdi
0x18000ffc6  sub     rsp, 40h
0x18000ffca  mov     rdi, rcx
0x18000ffcd  test    rcx, rcx
0x18000ffd0  jz      loc_180010142
0x18000ffd6  mov     eax, [rcx+4]
0x18000ffd9  mov     [rsp+48h+arg_0], rbx
0x18000ffde  cmp     eax, 44444442h
0x18000ffe3  jnz     loc_18001007D
0x18000ffe9  cmp     dword ptr [rcx], 20h ; ' '
0x18000ffec  jb      loc_1800100CB
0x18000fff2  mov     rbx, [rcx+18h]
0x18000fff6  mov     rcx, [rcx+10h]
0x18000fffa  mov     rax, [rbx+78h]
0x18000fffe  call    _guard_dispatch_icall
0x180010003  mov     esi, eax
0x180010005  test    eax, eax
0x180010007  js      loc_18001022C
0x18001000d  mov     ecx, [rdi]
0x18001000f  mov     rax, rdi
0x180010012  test    rcx, rcx
0x180010015  jz      short loc_18001002D
0x180010017  nop     word ptr [rax+rax+00000000h]
0x180010020  mov     byte ptr [rax], 0
0x180010023  lea     rax, [rax+1]
0x180010027  sub     rcx, 1
0x18001002b  jnz     short loc_180010020
0x18001002d  mov     eax, cs:g_TrustedEnvironment
0x180010033  test    eax, eax
0x180010035  jz      loc_18001024C
0x18001003b  test    al, 2
0x18001003d  jnz     loc_1800101A3
0x180010043  mov     edx, 62676E43h; Tag
0x180010048  mov     rcx, rdi; P
0x18001004b  call    cs:__imp_ExFreePoolWithTag
0x180010052  nop     dword ptr [rax+rax+00h]
0x180010057  mov     eax, 0FFFFFFFFh
0x18001005c  lock xadd [rbx+10h], eax
0x180010061  sub     eax, 1
0x180010064  jle     loc_180010269
0x18001006a  mov     rbx, [rsp+48h+arg_0]
0x18001006f  mov     eax, esi
0x180010071  mov     rsi, [rsp+48h+arg_8]
0x180010076  add     rsp, 40h
0x18001007a  pop     rdi
0x18001007b  retn
0x18001007d  sub     eax, 44444441h
0x180010082  jnz     short loc_1800100D3
0x180010084  cmp     dword ptr [rcx], 1B0h
0x18001008a  jb      short loc_180010095
0x18001008c  cmp     [rcx+0Ch], eax
0x18001008f  jz      loc_1800101BC
0x180010095  mov     r9d, 771h
0x18001009b  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800100a2  mov     ecx, 80090026h
0x1800100a7  lea     rdx, aStatus; "Status"
0x1800100ae  mov     esi, 80090026h
0x1800100b3  call    DebugTraceError
0x1800100b8  mov     rbx, [rsp+48h+arg_0]
0x1800100bd  mov     eax, esi
0x1800100bf  mov     rsi, [rsp+48h+arg_8]
0x1800100c4  add     rsp, 40h
0x1800100c8  pop     rdi
0x1800100c9  retn
0x1800100cb  mov     r9d, 77Dh
0x1800100d1  jmp     short loc_18001009B
0x1800100d3  cmp     eax, 2
0x1800100d6  jz      loc_180010218
0x1800100dc  mov     esi, 80090026h
0x1800100e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100e8  lea     rax, WPP_GLOBAL_Control
0x1800100ef  cmp     rcx, rax
0x1800100f2  jz      loc_18001006A
0x1800100f8  mov     eax, [rcx+2Ch]
0x1800100fb  test    al, 1
0x1800100fd  jz      loc_18001006A
0x180010103  mov     rcx, [rcx+18h]
0x180010107  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001010e  mov     [rsp+48h+var_18], 793h
0x180010116  lea     r9, aStatus; "Status"
0x18001011d  mov     [rsp+48h+var_20], r8
0x180010122  mov     [rsp+48h+var_28], 80090026h
0x18001012a  call    WPP_SF_sDsd
0x18001012f  mov     rbx, [rsp+48h+arg_0]
0x180010134  mov     eax, esi
0x180010136  mov     rsi, [rsp+48h+arg_8]
0x18001013b  add     rsp, 40h
0x18001013f  pop     rdi
0x180010140  retn
0x180010142  mov     esi, 0C0000008h
0x180010147  mov     rcx, cs:WPP_GLOBAL_Control
0x18001014e  lea     rax, WPP_GLOBAL_Control
0x180010155  cmp     rcx, rax
0x180010158  jz      loc_18001006F
0x18001015e  mov     eax, [rcx+2Ch]
0x180010161  test    al, 1
0x180010163  jz      loc_18001006F
0x180010169  mov     rcx, [rcx+18h]
0x18001016d  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010174  mov     [rsp+48h+var_18], 764h
0x18001017c  lea     r9, aStatus; "Status"
0x180010183  mov     [rsp+48h+var_20], r8
0x180010188  mov     [rsp+48h+var_28], 0C0000008h
0x180010190  call    WPP_SF_sDsd
0x180010195  mov     eax, esi
0x180010197  mov     rsi, [rsp+48h+arg_8]
0x18001019c  add     rsp, 40h
0x1800101a0  pop     rdi
0x1800101a1  retn
0x1800101a3  mov     rdx, rdi
0x1800101a6  mov     ecx, 200h
0x1800101ab  call    cs:__imp_SkFreePool
0x1800101b2  nop     dword ptr [rax+rax+00h]
0x1800101b7  jmp     loc_180010057
0x1800101bc  xor     esi, esi
0x1800101be  mov     edx, 1
0x1800101c3  call    DereferenceSslProvHandle
0x1800101c8  mov     rbx, [rsp+48h+arg_0]
0x1800101cd  mov     eax, esi
0x1800101cf  mov     rsi, [rsp+48h+arg_8]
0x1800101d4  add     rsp, 40h
0x1800101d8  pop     rdi
0x1800101d9  retn
0x1800101db  mov     edx, [rdi]
0x1800101dd  mov     r8, rdi
0x1800101e0  test    rdx, rdx
0x1800101e3  jz      short loc_1800101F3
0x1800101e5  mov     byte ptr [r8], 0
0x1800101e9  lea     r8, [r8+1]
0x1800101ed  sub     rdx, 1
0x1800101f1  jnz     short loc_1800101E5
0x1800101f3  mov     rcx, rdi; P
0x1800101f6  call    MSCryptFree
0x1800101fb  xor     edx, edx
0x1800101fd  mov     rcx, rbx; P
0x180010200  call    DereferenceSslProvHandle
0x180010205  mov     rbx, [rsp+48h+arg_0]
0x18001020a  mov     eax, esi
0x18001020c  mov     rsi, [rsp+48h+arg_8]
0x180010211  add     rsp, 40h
0x180010215  pop     rdi
0x180010216  retn
0x180010218  cmp     dword ptr [rcx], 20h ; ' '
0x18001021b  jnb     loc_1800A5B5E
0x180010221  mov     r9d, 78Ah
0x180010227  jmp     loc_18001009B
0x18001022c  mov     r9d, 79Fh
0x180010232  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010239  lea     rdx, aStatus; "Status"
0x180010240  mov     ecx, eax
0x180010242  call    DebugTraceError
0x180010247  jmp     loc_18001000D
0x18001024c  call    cs:__imp_SkIsSecureKernel
0x180010253  nop     dword ptr [rax+rax+00h]
0x180010258  sar     eax, 1Fh
0x18001025b  add     eax, 2
0x18001025e  mov     cs:g_TrustedEnvironment, eax
0x180010264  jmp     loc_18001003B
0x180010269  cmp     dword ptr [rbx+0Ch], 0
0x18001026d  jz      loc_18001006A
0x180010273  mov     rax, [rbx+78h]
0x180010277  xor     edx, edx
0x180010279  mov     rcx, [rbx+1A8h]
0x180010280  call    _guard_dispatch_icall
0x180010285  mov     rcx, [rbx+18h]
0x180010289  call    UnloadProvider
0x18001028e  mov     r8d, [rbx]; Size
0x180010291  xor     edx, edx; Val
0x180010293  mov     rcx, rbx; void *
0x180010296  call    memset
0x18001029b  mov     rcx, rbx; P
0x18001029e  call    MSCryptFree
0x1800102a3  jmp     loc_18001006A
0x1800a5b5e  mov     rbx, [rcx+18h]
0x1800a5b62  mov     rcx, [rcx+10h]
0x1800a5b66  mov     rax, [rbx+78h]
0x1800a5b6a  call    _guard_dispatch_icall
0x1800a5b6f  mov     esi, eax
0x1800a5b71  test    eax, eax
0x1800a5b73  jns     loc_1800101DB
0x1800a5b79  mov     r9d, 7AEh
0x1800a5b7f  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a5b86  lea     rdx, aStatus; "Status"
0x1800a5b8d  mov     ecx, eax
0x1800a5b8f  call    DebugTraceError
0x1800a5b94  nop
0x1800a5b95  jmp     loc_1800101DB
```
