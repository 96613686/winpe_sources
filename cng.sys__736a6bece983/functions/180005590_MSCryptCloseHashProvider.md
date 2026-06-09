# MSCryptCloseHashProvider

- ea: `0x180005590`
- end: `0x18000563e`
- name: `MSCryptCloseHashProvider`
- size: `174`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001cc4`
- `0x180004820`
- `0x18007dfb4`
- `0x18007e320`
- `0x180081198`
- `0x180081c48`

## callees

- `0x180005590`
- `0x180005644`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`

## string_xrefs

- `0x1800055ef`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18000561f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptCloseHashProvider(__int64 a1, int a2)
{
  unsigned int v2; // ebx
  unsigned int *v3; // rax
  __int64 v4; // rcx
  _BYTE *v5; // rdx

  v2 = 0;
  if ( a2 )
  {
    v2 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        123);
  }
  else
  {
    v3 = (unsigned int *)validateMSCryptHashAlgorithm(a1);
    if ( v3 )
    {
      v4 = *v3;
      v5 = v3;
      if ( *v3 )
      {
        do
        {
          *v5++ = 0;
          --v4;
        }
        while ( v4 );
      }
      MSCryptFree(v3);
    }
    else
    {
      v2 = -1073741816;
      DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", 900);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180005590  push    rbx
0x180005592  sub     rsp, 40h
0x180005596  xor     ebx, ebx
0x180005598  test    edx, edx
0x18000559a  jnz     short loc_1800055CC
0x18000559c  call    validateMSCryptHashAlgorithm
0x1800055a1  test    rax, rax
0x1800055a4  jz      short loc_180005619
0x1800055a6  mov     ecx, [rax]
0x1800055a8  mov     rdx, rax
0x1800055ab  test    rcx, rcx
0x1800055ae  jz      short loc_1800055BB
0x1800055b0  mov     [rdx], bl
0x1800055b2  inc     rdx
0x1800055b5  sub     rcx, 1
0x1800055b9  jnz     short loc_1800055B0
0x1800055bb  mov     rcx, rax; P
0x1800055be  call    MSCryptFree
0x1800055c3  mov     eax, ebx
0x1800055c5  add     rsp, 40h
0x1800055c9  pop     rbx
0x1800055ca  retn
0x1800055cc  mov     ebx, 0C000000Dh
0x1800055d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055d8  lea     rax, WPP_GLOBAL_Control
0x1800055df  cmp     rcx, rax
0x1800055e2  jz      short loc_1800055C3
0x1800055e4  mov     eax, [rcx+2Ch]
0x1800055e7  test    al, 1
0x1800055e9  jz      short loc_1800055C3
0x1800055eb  mov     rcx, [rcx+18h]
0x1800055ef  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800055f6  mov     [rsp+48h+var_18], 37Bh
0x1800055fe  lea     r9, aStatus; "Status"
0x180005605  mov     [rsp+48h+var_20], r8
0x18000560a  mov     [rsp+48h+var_28], 0C000000Dh
0x180005612  call    WPP_SF_sDsd
0x180005617  jmp     short loc_1800055C3
0x180005619  mov     r9d, 384h
0x18000561f  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005626  lea     rdx, aStatus; "Status"
0x18000562d  mov     ecx, 0C0000008h
0x180005632  mov     ebx, 0C0000008h
0x180005637  call    DebugTraceError
0x18000563c  jmp     short loc_1800055C3
```
