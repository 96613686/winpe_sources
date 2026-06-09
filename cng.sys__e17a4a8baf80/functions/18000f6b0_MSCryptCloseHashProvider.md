# MSCryptCloseHashProvider

- ea: `0x18000f6b0`
- end: `0x18000f75e`
- name: `MSCryptCloseHashProvider`
- size: `174`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000bde4`
- `0x18000e940`
- `0x1800871c4`
- `0x180087530`
- `0x18008a398`
- `0x18008ae48`

## callees

- `0x18000f6b0`
- `0x18000f764`
- `0x180010590`
- `0x18001155c`
- `0x1800123d0`

## string_xrefs

- `0x18000f70f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18000f73f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

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
0x18000f6b0  push    rbx
0x18000f6b2  sub     rsp, 40h
0x18000f6b6  xor     ebx, ebx
0x18000f6b8  test    edx, edx
0x18000f6ba  jnz     short loc_18000F6EC
0x18000f6bc  call    validateMSCryptHashAlgorithm
0x18000f6c1  test    rax, rax
0x18000f6c4  jz      short loc_18000F739
0x18000f6c6  mov     ecx, [rax]
0x18000f6c8  mov     rdx, rax
0x18000f6cb  test    rcx, rcx
0x18000f6ce  jz      short loc_18000F6DB
0x18000f6d0  mov     [rdx], bl
0x18000f6d2  inc     rdx
0x18000f6d5  sub     rcx, 1
0x18000f6d9  jnz     short loc_18000F6D0
0x18000f6db  mov     rcx, rax; P
0x18000f6de  call    MSCryptFree
0x18000f6e3  mov     eax, ebx
0x18000f6e5  add     rsp, 40h
0x18000f6e9  pop     rbx
0x18000f6ea  retn
0x18000f6ec  mov     ebx, 0C000000Dh
0x18000f6f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f6f8  lea     rax, WPP_GLOBAL_Control
0x18000f6ff  cmp     rcx, rax
0x18000f702  jz      short loc_18000F6E3
0x18000f704  mov     eax, [rcx+2Ch]
0x18000f707  test    al, 1
0x18000f709  jz      short loc_18000F6E3
0x18000f70b  mov     rcx, [rcx+18h]
0x18000f70f  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f716  mov     [rsp+48h+var_18], 37Bh
0x18000f71e  lea     r9, aStatus; "Status"
0x18000f725  mov     [rsp+48h+var_20], r8
0x18000f72a  mov     [rsp+48h+var_28], 0C000000Dh
0x18000f732  call    WPP_SF_sDsd
0x18000f737  jmp     short loc_18000F6E3
0x18000f739  mov     r9d, 384h
0x18000f73f  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f746  lea     rdx, aStatus; "Status"
0x18000f74d  mov     ecx, 0C0000008h
0x18000f752  mov     ebx, 0C0000008h
0x18000f757  call    DebugTraceError
0x18000f75c  jmp     short loc_18000F6E3
```
