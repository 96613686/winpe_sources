# SslFreeObject

- ea: `0x180005ea0`
- end: `0x180006188`
- name: `SslFreeObject`
- size: `744`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180005ea0`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x18003a060`
- `0x18003cdf4`
- `0x18009d860`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180005f2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x180005f2b`
- `ntoskrnl!SkIsSecureKernel` at `0x18000612c`
- `ntoskrnl!SkIsSecureKernel` at `0x18000612c`
- `ntoskrnl!SkFreePool` at `0x18000608b`
- `ntoskrnl!SkFreePool` at `0x18000608b`

## string_xrefs

- `0x180005f7b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180005fe7`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000604d`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180006112`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18009ede1`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

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
0x180005ea0  mov     [rsp+arg_8], rsi
0x180005ea5  push    rdi
0x180005ea6  sub     rsp, 40h
0x180005eaa  mov     rdi, rcx
0x180005ead  test    rcx, rcx
0x180005eb0  jz      loc_180006022
0x180005eb6  mov     eax, [rcx+4]
0x180005eb9  mov     [rsp+48h+arg_0], rbx
0x180005ebe  cmp     eax, 44444442h
0x180005ec3  jnz     loc_180005F5D
0x180005ec9  cmp     dword ptr [rcx], 20h ; ' '
0x180005ecc  jb      loc_180005FAB
0x180005ed2  mov     rbx, [rcx+18h]
0x180005ed6  mov     rcx, [rcx+10h]
0x180005eda  mov     rax, [rbx+78h]
0x180005ede  call    _guard_dispatch_icall
0x180005ee3  mov     esi, eax
0x180005ee5  test    eax, eax
0x180005ee7  js      loc_18000610C
0x180005eed  mov     ecx, [rdi]
0x180005eef  mov     rax, rdi
0x180005ef2  test    rcx, rcx
0x180005ef5  jz      short loc_180005F0D
0x180005ef7  nop     word ptr [rax+rax+00000000h]
0x180005f00  mov     byte ptr [rax], 0
0x180005f03  lea     rax, [rax+1]
0x180005f07  sub     rcx, 1
0x180005f0b  jnz     short loc_180005F00
0x180005f0d  mov     eax, cs:g_TrustedEnvironment
0x180005f13  test    eax, eax
0x180005f15  jz      loc_18000612C
0x180005f1b  test    al, 2
0x180005f1d  jnz     loc_180006083
0x180005f23  mov     edx, 62676E43h; Tag
0x180005f28  mov     rcx, rdi; P
0x180005f2b  call    cs:__imp_ExFreePoolWithTag
0x180005f32  nop     dword ptr [rax+rax+00h]
0x180005f37  mov     eax, 0FFFFFFFFh
0x180005f3c  lock xadd [rbx+10h], eax
0x180005f41  sub     eax, 1
0x180005f44  jle     loc_180006149
0x180005f4a  mov     rbx, [rsp+48h+arg_0]
0x180005f4f  mov     eax, esi
0x180005f51  mov     rsi, [rsp+48h+arg_8]
0x180005f56  add     rsp, 40h
0x180005f5a  pop     rdi
0x180005f5b  retn
0x180005f5d  sub     eax, 44444441h
0x180005f62  jnz     short loc_180005FB3
0x180005f64  cmp     dword ptr [rcx], 1B0h
0x180005f6a  jb      short loc_180005F75
0x180005f6c  cmp     [rcx+0Ch], eax
0x180005f6f  jz      loc_18000609C
0x180005f75  mov     r9d, 771h
0x180005f7b  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005f82  mov     ecx, 80090026h
0x180005f87  lea     rdx, aStatus; "Status"
0x180005f8e  mov     esi, 80090026h
0x180005f93  call    DebugTraceError
0x180005f98  mov     rbx, [rsp+48h+arg_0]
0x180005f9d  mov     eax, esi
0x180005f9f  mov     rsi, [rsp+48h+arg_8]
0x180005fa4  add     rsp, 40h
0x180005fa8  pop     rdi
0x180005fa9  retn
0x180005fab  mov     r9d, 77Dh
0x180005fb1  jmp     short loc_180005F7B
0x180005fb3  cmp     eax, 2
0x180005fb6  jz      loc_1800060F8
0x180005fbc  mov     esi, 80090026h
0x180005fc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fc8  lea     rax, WPP_GLOBAL_Control
0x180005fcf  cmp     rcx, rax
0x180005fd2  jz      loc_180005F4A
0x180005fd8  mov     eax, [rcx+2Ch]
0x180005fdb  test    al, 1
0x180005fdd  jz      loc_180005F4A
0x180005fe3  mov     rcx, [rcx+18h]
0x180005fe7  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005fee  mov     [rsp+48h+var_18], 793h
0x180005ff6  lea     r9, aStatus; "Status"
0x180005ffd  mov     [rsp+48h+var_20], r8
0x180006002  mov     [rsp+48h+var_28], 80090026h
0x18000600a  call    WPP_SF_sDsd
0x18000600f  mov     rbx, [rsp+48h+arg_0]
0x180006014  mov     eax, esi
0x180006016  mov     rsi, [rsp+48h+arg_8]
0x18000601b  add     rsp, 40h
0x18000601f  pop     rdi
0x180006020  retn
0x180006022  mov     esi, 0C0000008h
0x180006027  mov     rcx, cs:WPP_GLOBAL_Control
0x18000602e  lea     rax, WPP_GLOBAL_Control
0x180006035  cmp     rcx, rax
0x180006038  jz      loc_180005F4F
0x18000603e  mov     eax, [rcx+2Ch]
0x180006041  test    al, 1
0x180006043  jz      loc_180005F4F
0x180006049  mov     rcx, [rcx+18h]
0x18000604d  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006054  mov     [rsp+48h+var_18], 764h
0x18000605c  lea     r9, aStatus; "Status"
0x180006063  mov     [rsp+48h+var_20], r8
0x180006068  mov     [rsp+48h+var_28], 0C0000008h
0x180006070  call    WPP_SF_sDsd
0x180006075  mov     eax, esi
0x180006077  mov     rsi, [rsp+48h+arg_8]
0x18000607c  add     rsp, 40h
0x180006080  pop     rdi
0x180006081  retn
0x180006083  mov     rdx, rdi
0x180006086  mov     ecx, 200h
0x18000608b  call    cs:__imp_SkFreePool
0x180006092  nop     dword ptr [rax+rax+00h]
0x180006097  jmp     loc_180005F37
0x18000609c  xor     esi, esi
0x18000609e  mov     edx, 1
0x1800060a3  call    DereferenceSslProvHandle
0x1800060a8  mov     rbx, [rsp+48h+arg_0]
0x1800060ad  mov     eax, esi
0x1800060af  mov     rsi, [rsp+48h+arg_8]
0x1800060b4  add     rsp, 40h
0x1800060b8  pop     rdi
0x1800060b9  retn
0x1800060bb  mov     edx, [rdi]
0x1800060bd  mov     r8, rdi
0x1800060c0  test    rdx, rdx
0x1800060c3  jz      short loc_1800060D3
0x1800060c5  mov     byte ptr [r8], 0
0x1800060c9  lea     r8, [r8+1]
0x1800060cd  sub     rdx, 1
0x1800060d1  jnz     short loc_1800060C5
0x1800060d3  mov     rcx, rdi; P
0x1800060d6  call    MSCryptFree
0x1800060db  xor     edx, edx
0x1800060dd  mov     rcx, rbx; P
0x1800060e0  call    DereferenceSslProvHandle
0x1800060e5  mov     rbx, [rsp+48h+arg_0]
0x1800060ea  mov     eax, esi
0x1800060ec  mov     rsi, [rsp+48h+arg_8]
0x1800060f1  add     rsp, 40h
0x1800060f5  pop     rdi
0x1800060f6  retn
0x1800060f8  cmp     dword ptr [rcx], 20h ; ' '
0x1800060fb  jnb     loc_18009EDC0
0x180006101  mov     r9d, 78Ah
0x180006107  jmp     loc_180005F7B
0x18000610c  mov     r9d, 79Fh
0x180006112  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006119  lea     rdx, aStatus; "Status"
0x180006120  mov     ecx, eax
0x180006122  call    DebugTraceError
0x180006127  jmp     loc_180005EED
0x18000612c  call    cs:__imp_SkIsSecureKernel
0x180006133  nop     dword ptr [rax+rax+00h]
0x180006138  sar     eax, 1Fh
0x18000613b  add     eax, 2
0x18000613e  mov     cs:g_TrustedEnvironment, eax
0x180006144  jmp     loc_180005F1B
0x180006149  cmp     dword ptr [rbx+0Ch], 0
0x18000614d  jz      loc_180005F4A
0x180006153  mov     rax, [rbx+78h]
0x180006157  xor     edx, edx
0x180006159  mov     rcx, [rbx+1A8h]
0x180006160  call    _guard_dispatch_icall
0x180006165  mov     rcx, [rbx+18h]
0x180006169  call    UnloadProvider
0x18000616e  mov     r8d, [rbx]; Size
0x180006171  xor     edx, edx; Val
0x180006173  mov     rcx, rbx; void *
0x180006176  call    memset
0x18000617b  mov     rcx, rbx; P
0x18000617e  call    MSCryptFree
0x180006183  jmp     loc_180005F4A
0x18009edc0  mov     rbx, [rcx+18h]
0x18009edc4  mov     rcx, [rcx+10h]
0x18009edc8  mov     rax, [rbx+78h]
0x18009edcc  call    _guard_dispatch_icall
0x18009edd1  mov     esi, eax
0x18009edd3  test    eax, eax
0x18009edd5  jns     loc_1800060BB
0x18009eddb  mov     r9d, 7AEh
0x18009ede1  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18009ede8  lea     rdx, aStatus; "Status"
0x18009edef  mov     ecx, eax
0x18009edf1  call    DebugTraceError
0x18009edf6  nop
0x18009edf7  jmp     loc_1800060BB
```
