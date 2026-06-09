# I_GetRecipientIdString

- ea: `0x180019de4`
- end: `0x18001a064`
- name: `I_GetRecipientIdString`
- size: `640`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180005a18`
- `0x18001d7b8`

## callees

- `0x180003a50`
- `0x180005f90`
- `0x18000d02c`
- `0x18000e120`
- `0x180015a40`
- `0x180019de4`
- `0x18001c948`
- `0x18001f175`

## string_xrefs

- `0x180019e56`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`
- `0x180019fdc`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`
- `0x18001a027`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`

## pseudocode

```c
__int64 __fastcall I_GetRecipientIdString(__int64 a1, __int64 a2, wchar_t **a3)
{
  __int64 v5; // rbx
  size_t v6; // rbx
  wchar_t *v7; // rax
  wchar_t *v8; // rsi
  unsigned int v9; // ebx
  bool v10; // zf
  HRESULT v11; // eax
  __int64 v12; // r9
  int v13; // r14d
  STRSAFE_LPWSTR v14; // r12
  int v15; // edx
  __int64 v16; // rcx
  int v17; // eax
  int v18; // r14d
  unsigned int v19; // r10d
  size_t pcchRemaining; // [rsp+80h] [rbp+40h] BYREF
  __int64 v22; // [rsp+88h] [rbp+48h] BYREF
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+90h] [rbp+50h] BYREF

  v22 = a2;
  *a3 = 0;
  if ( *(_DWORD *)a1 == 2 )
  {
    v5 = (unsigned int)(2 * *(_DWORD *)(a1 + 8)) + 5LL;
    goto LABEL_5;
  }
  if ( *(_DWORD *)a1 == 1 )
  {
    v5 = (unsigned int)(2 * *(_DWORD *)(a1 + 24)) + 16LL + (unsigned int)(2 * *(_DWORD *)(a1 + 8));
LABEL_5:
    v6 = v5 + 8;
    pcchRemaining = v6;
    v7 = (wchar_t *)I_DefaultExtrenalAlloc(2 * v6);
    v8 = v7;
    if ( !v7 )
    {
      v9 = -2146893810;
      DebugTraceError(
        2148073486LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
        1139);
      return v9;
    }
    memset_0(v7, 0, 2 * v6);
    v10 = *(_DWORD *)a1 == 2;
    ppszDestEnd = v8;
    if ( v10 )
    {
      v11 = StringCchPrintfExW(v8, v6, &ppszDestEnd, &pcchRemaining, 0, L"%ls:", L"KeyId");
      v9 = v11;
      if ( v11 < 0 )
      {
        v12 = 1160;
LABEL_20:
        v19 = v11;
        goto LABEL_21;
      }
      v11 = CNG_BinToHex(
              *(_QWORD *)(a1 + 16),
              *(_DWORD *)(a1 + 8),
              0,
              (_DWORD)ppszDestEnd,
              pcchRemaining,
              (__int64)&v22);
      v9 = v11;
      if ( v11 < 0 )
      {
        v12 = 1176;
        goto LABEL_20;
      }
    }
    else
    {
      v11 = StringCchPrintfExW(v8, v6, &ppszDestEnd, &pcchRemaining, 0, L"%ls:", L"IssuerAndSerial");
      v9 = v11;
      if ( v11 < 0 )
      {
        v12 = 1193;
        goto LABEL_20;
      }
      v13 = pcchRemaining;
      v14 = ppszDestEnd;
      v15 = *(_DWORD *)(a1 + 8);
      v16 = *(_QWORD *)(a1 + 16);
      LODWORD(v22) = pcchRemaining;
      v11 = CNG_BinToHex(v16, v15, 0, (_DWORD)ppszDestEnd, pcchRemaining, (__int64)&v22);
      v9 = v11;
      if ( v11 < 0 )
      {
        v12 = 1209;
        goto LABEL_20;
      }
      v17 = v22;
      v18 = v13 - v22;
      if ( !v18 )
      {
        v9 = -2146893810;
        v19 = -2146893810;
        v12 = 1220;
LABEL_21:
        DebugTraceError(
          v19,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
          v12);
        I_DefaultExtrenalFree(v8);
        return v9;
      }
      v14[(unsigned int)v22] = 44;
      v11 = CNG_BinToHex(
              *(_QWORD *)(a1 + 32),
              *(_DWORD *)(a1 + 24),
              1,
              (int)v14 + 2 * (v17 + 1),
              v18 - 1,
              (__int64)&v22);
      v9 = v11;
      if ( v11 < 0 )
      {
        v12 = 1237;
        goto LABEL_20;
      }
    }
    *a3 = v8;
    return 0;
  }
  v9 = -2146893783;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)WPP_GLOBAL_Control,
      (_DWORD)a3,
      (unsigned int)"Status",
      41,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
      105);
  return v9;
}

```

## disassembly

```asm
0x180019de4  mov     [rsp-38h+arg_8], rdx
0x180019de9  push    rbp
0x180019dea  push    rbx
0x180019deb  push    rsi
0x180019dec  push    rdi
0x180019ded  push    r12
0x180019def  push    r14
0x180019df1  push    r15
0x180019df3  mov     rbp, rsp
0x180019df6  sub     rsp, 40h
0x180019dfa  mov     qword ptr [r8], 0
0x180019e01  mov     r15, r8
0x180019e04  cmp     dword ptr [rcx], 2
0x180019e07  mov     rdi, rcx
0x180019e0a  jnz     short loc_180019E18
0x180019e0c  mov     eax, [rcx+8]
0x180019e0f  lea     ebx, [rax+rax]
0x180019e12  add     rbx, 5
0x180019e16  jmp     short loc_180019E34
0x180019e18  cmp     dword ptr [rcx], 1
0x180019e1b  jnz     loc_18001A009
0x180019e21  mov     eax, [rcx+18h]
0x180019e24  lea     ecx, [rax+rax]
0x180019e27  mov     eax, [rdi+8]
0x180019e2a  add     rcx, 10h
0x180019e2e  lea     ebx, [rax+rax]
0x180019e31  add     rbx, rcx
0x180019e34  add     rbx, 8
0x180019e38  mov     [rbp+pcchRemaining], rbx
0x180019e3c  lea     r14, [rbx+rbx]
0x180019e40  mov     rcx, r14
0x180019e43  call    I_DefaultExtrenalAlloc
0x180019e48  mov     rsi, rax
0x180019e4b  test    rax, rax
0x180019e4e  jnz     short loc_180019E78
0x180019e50  mov     r9d, 473h
0x180019e56  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180019e5d  lea     rdx, aStatus; "Status"
0x180019e64  mov     ecx, 8009000Eh
0x180019e69  mov     ebx, 8009000Eh
0x180019e6e  call    DebugTraceError
0x180019e73  jmp     loc_18001A053
0x180019e78  mov     r8, r14; Size
0x180019e7b  xor     edx, edx; Val
0x180019e7d  mov     rcx, rsi; void *
0x180019e80  call    memset_0
0x180019e85  cmp     dword ptr [rdi], 2
0x180019e88  lea     r9, [rbp+pcchRemaining]; pcchRemaining
0x180019e8c  mov     [rbp+ppszDestEnd], rsi
0x180019e90  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x180019e94  mov     rdx, rbx; cchDest
0x180019e97  mov     rcx, rsi; pszDest
0x180019e9a  jnz     short loc_180019F0B
0x180019e9c  lea     rax, aKeyid; "KeyId"
0x180019ea3  mov     [rsp+40h+var_10], rax
0x180019ea8  lea     rax, aLs_0; "%ls:"
0x180019eaf  mov     [rsp+40h+pszFormat], rax; pszFormat
0x180019eb4  mov     qword ptr [rsp+40h+dwFlags], 0; dwFlags
0x180019ebd  call    StringCchPrintfExW
0x180019ec2  mov     ebx, eax
0x180019ec4  test    eax, eax
0x180019ec6  jns     short loc_180019ED3
0x180019ec8  mov     r9d, 488h
0x180019ece  jmp     loc_180019FD9
0x180019ed3  mov     r9, [rbp+ppszDestEnd]
0x180019ed7  lea     rax, [rbp+arg_8]
0x180019edb  mov     edx, [rdi+8]
0x180019ede  xor     r8d, r8d
0x180019ee1  mov     rcx, [rdi+10h]
0x180019ee5  mov     [rsp+40h+pszFormat], rax
0x180019eea  mov     eax, dword ptr [rbp+pcchRemaining]
0x180019eed  mov     [rsp+40h+dwFlags], eax
0x180019ef1  call    CNG_BinToHex
0x180019ef6  mov     ebx, eax
0x180019ef8  test    eax, eax
0x180019efa  jns     loc_18001A002
0x180019f00  mov     r9d, 498h
0x180019f06  jmp     loc_180019FD9
0x180019f0b  lea     rax, aIssuerandseria; "IssuerAndSerial"
0x180019f12  mov     [rsp+40h+var_10], rax
0x180019f17  lea     rax, aLs_0; "%ls:"
0x180019f1e  mov     [rsp+40h+pszFormat], rax; pszFormat
0x180019f23  mov     qword ptr [rsp+40h+dwFlags], 0; dwFlags
0x180019f2c  call    StringCchPrintfExW
0x180019f31  mov     ebx, eax
0x180019f33  test    eax, eax
0x180019f35  jns     short loc_180019F42
0x180019f37  mov     r9d, 4A9h
0x180019f3d  jmp     loc_180019FD9
0x180019f42  mov     r14, [rbp+pcchRemaining]
0x180019f46  lea     rax, [rbp+arg_8]
0x180019f4a  mov     r12, [rbp+ppszDestEnd]
0x180019f4e  xor     r8d, r8d
0x180019f51  mov     edx, [rdi+8]
0x180019f54  mov     r9, r12
0x180019f57  mov     rcx, [rdi+10h]
0x180019f5b  mov     [rsp+40h+pszFormat], rax
0x180019f60  mov     [rsp+40h+dwFlags], r14d
0x180019f65  mov     dword ptr [rbp+arg_8], r14d
0x180019f69  call    CNG_BinToHex
0x180019f6e  mov     ebx, eax
0x180019f70  test    eax, eax
0x180019f72  jns     short loc_180019F7C
0x180019f74  mov     r9d, 4B9h
0x180019f7a  jmp     short loc_180019FD9
0x180019f7c  mov     eax, dword ptr [rbp+arg_8]
0x180019f7f  sub     r14, rax
0x180019f82  cmp     r14d, 1
0x180019f86  jnb     short loc_180019F9B
0x180019f88  mov     ebx, 8009000Eh
0x180019f8d  mov     r10d, 8009000Eh
0x180019f93  mov     r9d, 4C4h
0x180019f99  jmp     short loc_180019FDC
0x180019f9b  mov     word ptr [r12+rax*2], 2Ch ; ','
0x180019fa2  lea     r9, [rax+1]
0x180019fa6  mov     edx, [rdi+18h]
0x180019fa9  lea     rcx, [rbp+arg_8]
0x180019fad  mov     [rsp+40h+pszFormat], rcx
0x180019fb2  lea     eax, [r14-1]
0x180019fb6  mov     rcx, [rdi+20h]
0x180019fba  lea     r9, [r12+r9*2]
0x180019fbe  mov     r8d, 1
0x180019fc4  mov     [rsp+40h+dwFlags], eax
0x180019fc8  call    CNG_BinToHex
0x180019fcd  mov     ebx, eax
0x180019fcf  test    eax, eax
0x180019fd1  jns     short loc_18001A002
0x180019fd3  mov     r9d, 4D5h
0x180019fd9  mov     r10d, eax
0x180019fdc  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180019fe3  lea     rax, aStatus; "Status"
0x180019fea  mov     r8, rcx
0x180019fed  mov     ecx, r10d
0x180019ff0  mov     rdx, rax
0x180019ff3  call    DebugTraceError
0x180019ff8  mov     rcx, rsi; hMem
0x180019ffb  call    I_DefaultExtrenalFree
0x18001a000  jmp     short loc_18001A053
0x18001a002  mov     [r15], rsi
0x18001a005  xor     ebx, ebx
0x18001a007  jmp     short loc_18001A053
0x18001a009  mov     ebx, 80090029h
0x18001a00e  mov     rdx, cs:WPP_GLOBAL_Control
0x18001a015  lea     rax, WPP_GLOBAL_Control
0x18001a01c  cmp     rdx, rax
0x18001a01f  jz      short loc_18001A053
0x18001a021  test    byte ptr [rdx+1Ch], 1
0x18001a025  jz      short loc_18001A053
0x18001a027  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001a02e  mov     dword ptr [rsp+40h+var_10], 469h
0x18001a036  mov     [rsp+40h+pszFormat], rcx
0x18001a03b  lea     r9, aStatus; "Status"
0x18001a042  mov     rcx, [rdx+10h]
0x18001a046  mov     [rsp+40h+dwFlags], 80090029h
0x18001a04e  call    WPP_SF_sDsd
0x18001a053  mov     eax, ebx
0x18001a055  add     rsp, 40h
0x18001a059  pop     r15
0x18001a05b  pop     r14
0x18001a05d  pop     r12
0x18001a05f  pop     rdi
0x18001a060  pop     rsi
0x18001a061  pop     rbx
0x18001a062  pop     rbp
0x18001a063  retn
```
