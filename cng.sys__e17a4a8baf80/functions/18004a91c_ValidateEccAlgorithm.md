# ValidateEccAlgorithm

- ea: `0x18004a91c`
- end: `0x18004aa45`
- name: `ValidateEccAlgorithm`
- size: `297`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004a7a8`
- `0x180080464`
- `0x180080990`
- `0x180080a7c`
- `0x180081178`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x18004a91c`
- `0x18004aa4c`

## string_xrefs

- `0x18004a9d3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800a8cd8`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

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
0x18004a91c  mov     [rsp+arg_0], rbx
0x18004a921  mov     [rsp+arg_8], rsi
0x18004a926  push    rdi
0x18004a927  sub     rsp, 40h
0x18004a92b  mov     rsi, r9
0x18004a92e  mov     edi, edx
0x18004a930  mov     r11, rcx
0x18004a933  test    rcx, rcx
0x18004a936  jz      short loc_18004A9A8
0x18004a938  mov     rbx, [rsp+48h+arg_20]
0x18004a93d  test    rbx, rbx
0x18004a940  jz      short loc_18004A9A8
0x18004a942  cmp     dword ptr [rcx+4], 4D53414Ch
0x18004a949  jnz     loc_18004AA3A
0x18004a94f  cmp     dword ptr [rcx], 18h
0x18004a952  jnz     loc_18004AA3A
0x18004a958  mov     ecx, [rcx+8]
0x18004a95b  mov     edx, r8d
0x18004a95e  call    CryptAuditTranslateAlgID
0x18004a963  test    rax, rax
0x18004a966  jz      loc_18004A9F5
0x18004a96c  mov     rcx, [r11+10h]
0x18004a970  test    rcx, rcx
0x18004a973  jz      loc_18004AA1E
0x18004a979  mov     rax, [rcx+8]
0x18004a97d  mov     edx, [rax+0Ch]
0x18004a980  mov     rax, [rcx]
0x18004a983  mov     ecx, [rax+0Ch]
0x18004a986  mov     [rsi], ecx
0x18004a988  test    edi, edi
0x18004a98a  jnz     loc_18004AA27
0x18004a990  mov     [rbx], r11
0x18004a993  xor     ebx, ebx
0x18004a995  mov     rsi, [rsp+48h+arg_8]
0x18004a99a  mov     eax, ebx
0x18004a99c  mov     rbx, [rsp+48h+arg_0]
0x18004a9a1  add     rsp, 40h
0x18004a9a5  pop     rdi
0x18004a9a6  retn
0x18004a9a8  mov     ebx, 0C000000Dh
0x18004a9ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a9b4  lea     rax, WPP_GLOBAL_Control
0x18004a9bb  cmp     rcx, rax
0x18004a9be  jz      short loc_18004A995
0x18004a9c0  mov     eax, [rcx+2Ch]
0x18004a9c3  test    al, 1
0x18004a9c5  jz      short loc_18004A995
0x18004a9c7  mov     [rsp+48h+var_18], 1E7h
0x18004a9cf  mov     rcx, [rcx+18h]
0x18004a9d3  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004a9da  mov     [rsp+48h+var_20], rax
0x18004a9df  lea     r9, aStatus; "Status"
0x18004a9e6  mov     [rsp+48h+var_28], 0C000000Dh
0x18004a9ee  call    WPP_SF_sDsd
0x18004a9f3  jmp     short loc_18004A995
0x18004a9f5  mov     ebx, 0C000000Dh
0x18004a9fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18004aa01  lea     rax, WPP_GLOBAL_Control
0x18004aa08  cmp     rcx, rax
0x18004aa0b  jz      short loc_18004A995
0x18004aa0d  mov     eax, [rcx+2Ch]
0x18004aa10  test    al, 1
0x18004aa12  jz      short loc_18004A995
0x18004aa14  mov     [rsp+48h+var_18], 1F9h
0x18004aa1c  jmp     short loc_18004A9CF
0x18004aa1e  xor     edx, edx
0x18004aa20  xor     ecx, ecx
0x18004aa22  jmp     loc_18004A986
0x18004aa27  cmp     edx, edi
0x18004aa29  jz      loc_18004A990
0x18004aa2f  mov     r9d, 20Eh
0x18004aa35  jmp     loc_1800A8CD8
0x18004aa3a  mov     r9d, 1F1h
0x18004aa40  jmp     loc_1800A8CD8
0x1800a8cd8  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a8cdf  mov     ecx, 0C000000Dh
0x1800a8ce4  lea     rdx, aStatus; "Status"
0x1800a8ceb  mov     ebx, 0C000000Dh
0x1800a8cf0  call    DebugTraceError
0x1800a8cf5  nop
0x1800a8cf6  jmp     loc_18004A995
```
