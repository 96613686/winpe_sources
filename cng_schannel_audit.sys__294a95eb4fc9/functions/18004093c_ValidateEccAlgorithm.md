# ValidateEccAlgorithm

- ea: `0x18004093c`
- end: `0x180040a65`
- name: `ValidateEccAlgorithm`
- size: `297`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800407c8`
- `0x1800762c4`
- `0x1800767f0`
- `0x1800768dc`
- `0x180076fd8`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18004093c`
- `0x180040a6c`

## string_xrefs

- `0x1800409f3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800a1f3a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall ValidateEccAlgorithm(_DWORD *a1, int a2, unsigned int a3, _DWORD *a4, _QWORD *a5)
{
  int v7; // edx
  int v8; // r8d
  __int64 v9; // r11
  _QWORD *v10; // rcx
  int v11; // edx
  int v12; // ecx
  unsigned int v13; // ebx
  __int64 v15; // r9

  if ( a1 && a5 )
  {
    if ( a1[1] != 1297301836 || *a1 != 24 )
    {
      v15 = 497;
      goto LABEL_22;
    }
    if ( CryptAuditTranslateAlgID((unsigned int)a1[2], a3) )
    {
      v10 = *(_QWORD **)(v9 + 16);
      if ( v10 )
      {
        v11 = *(_DWORD *)(v10[1] + 12LL);
        v12 = *(_DWORD *)(*v10 + 12LL);
      }
      else
      {
        v11 = 0;
        v12 = 0;
      }
      *a4 = v12;
      if ( a2 && v11 != a2 )
      {
        v15 = 526;
LABEL_22:
        v13 = -1073741811;
        DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v15);
        return v13;
      }
      *a5 = v9;
      return 0;
    }
    else
    {
      v13 = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v7,
          v8,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          249);
    }
  }
  else
  {
    v13 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        231);
  }
  return v13;
}

```

## disassembly

```asm
0x18004093c  mov     [rsp+arg_0], rbx
0x180040941  mov     [rsp+arg_8], rsi
0x180040946  push    rdi
0x180040947  sub     rsp, 40h
0x18004094b  mov     rsi, r9
0x18004094e  mov     edi, edx
0x180040950  mov     r11, rcx
0x180040953  test    rcx, rcx
0x180040956  jz      short loc_1800409C8
0x180040958  mov     rbx, [rsp+48h+arg_20]
0x18004095d  test    rbx, rbx
0x180040960  jz      short loc_1800409C8
0x180040962  cmp     dword ptr [rcx+4], 4D53414Ch
0x180040969  jnz     loc_180040A5A
0x18004096f  cmp     dword ptr [rcx], 18h
0x180040972  jnz     loc_180040A5A
0x180040978  mov     ecx, [rcx+8]
0x18004097b  mov     edx, r8d
0x18004097e  call    CryptAuditTranslateAlgID
0x180040983  test    rax, rax
0x180040986  jz      loc_180040A15
0x18004098c  mov     rcx, [r11+10h]
0x180040990  test    rcx, rcx
0x180040993  jz      loc_180040A3E
0x180040999  mov     rax, [rcx+8]
0x18004099d  mov     edx, [rax+0Ch]
0x1800409a0  mov     rax, [rcx]
0x1800409a3  mov     ecx, [rax+0Ch]
0x1800409a6  mov     [rsi], ecx
0x1800409a8  test    edi, edi
0x1800409aa  jnz     loc_180040A47
0x1800409b0  mov     [rbx], r11
0x1800409b3  xor     ebx, ebx
0x1800409b5  mov     rsi, [rsp+48h+arg_8]
0x1800409ba  mov     eax, ebx
0x1800409bc  mov     rbx, [rsp+48h+arg_0]
0x1800409c1  add     rsp, 40h
0x1800409c5  pop     rdi
0x1800409c6  retn
0x1800409c8  mov     ebx, 0C000000Dh
0x1800409cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800409d4  lea     rax, WPP_GLOBAL_Control
0x1800409db  cmp     rcx, rax
0x1800409de  jz      short loc_1800409B5
0x1800409e0  mov     eax, [rcx+2Ch]
0x1800409e3  test    al, 1
0x1800409e5  jz      short loc_1800409B5
0x1800409e7  mov     [rsp+48h+var_18], 1E7h
0x1800409ef  mov     rcx, [rcx+18h]
0x1800409f3  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800409fa  mov     [rsp+48h+var_20], rax
0x1800409ff  lea     r9, aStatus; "Status"
0x180040a06  mov     [rsp+48h+var_28], 0C000000Dh
0x180040a0e  call    WPP_SF_sDsd
0x180040a13  jmp     short loc_1800409B5
0x180040a15  mov     ebx, 0C000000Dh
0x180040a1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180040a21  lea     rax, WPP_GLOBAL_Control
0x180040a28  cmp     rcx, rax
0x180040a2b  jz      short loc_1800409B5
0x180040a2d  mov     eax, [rcx+2Ch]
0x180040a30  test    al, 1
0x180040a32  jz      short loc_1800409B5
0x180040a34  mov     [rsp+48h+var_18], 1F9h
0x180040a3c  jmp     short loc_1800409EF
0x180040a3e  xor     edx, edx
0x180040a40  xor     ecx, ecx
0x180040a42  jmp     loc_1800409A6
0x180040a47  cmp     edx, edi
0x180040a49  jz      loc_1800409B0
0x180040a4f  mov     r9d, 20Eh
0x180040a55  jmp     loc_1800A1F3A
0x180040a5a  mov     r9d, 1F1h
0x180040a60  jmp     loc_1800A1F3A
0x1800a1f3a  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a1f41  mov     ecx, 0C000000Dh
0x1800a1f46  lea     rdx, aStatus; "Status"
0x1800a1f4d  mov     ebx, 0C000000Dh
0x1800a1f52  call    DebugTraceError
0x1800a1f57  nop
0x1800a1f58  jmp     loc_1800409B5
```
