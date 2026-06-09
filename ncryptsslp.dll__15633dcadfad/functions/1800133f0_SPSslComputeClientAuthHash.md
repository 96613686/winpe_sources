# SPSslComputeClientAuthHash

- ea: `0x1800133f0`
- end: `0x180013556`
- name: `SPSslComputeClientAuthHash`
- size: `358`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, unsigned int, __int64, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800068e0`
- `0x180007960`
- `0x18000b594`
- `0x18000b654`
- `0x180011580`
- `0x180011630`
- `0x1800133f0`
- `0x18001f5cc`

## string_xrefs

- `0x180013430`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18001347d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslComputeClientAuthHash(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7,
        int a8)
{
  __int64 v8; // rdx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r10
  __int64 v17; // r11
  int v18; // eax

  if ( SslpValidateProvHandle(a1) )
  {
    v10 = SslpValidateMasterKeyHandle(v8);
    if ( !v10 )
    {
      v12 = 197;
LABEL_7:
      v9 = -2146893786;
      v13 = 2148073510LL;
LABEL_8:
      DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v12);
      return v9;
    }
    v14 = SslpValidateHashHandle(v11, v10);
    if ( !v14 )
    {
      v12 = 206;
      goto LABEL_7;
    }
    if ( a8 )
    {
      v9 = -2146893815;
      v12 = 213;
      v13 = 2148073481LL;
      goto LABEL_8;
    }
    if ( *(_DWORD *)(v15 + 8) < 0x301u )
    {
      if ( *(_DWORD *)(v15 + 8) != 768 )
        return (unsigned int)-2146893783;
      v18 = Ssl3ComputeClientAuthHash(v17, v15, v14);
      v9 = v18;
      if ( v18 < 0 )
      {
        v12 = 246;
        goto LABEL_16;
      }
    }
    else
    {
      v18 = Tls1ComputeClientAuthHash(v14, v16, a5, a6, a7);
      v9 = v18;
      if ( v18 < 0 )
      {
        v12 = 230;
LABEL_16:
        v13 = (unsigned int)v18;
        goto LABEL_8;
      }
    }
    return 0;
  }
  v9 = -2146893786;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
      (unsigned int)"Status",
      38,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
      188);
  return v9;
}

```

## disassembly

```asm
0x1800133f0  push    rbx
0x1800133f2  sub     rsp, 40h
0x1800133f6  mov     r10, r9
0x1800133f9  call    SslpValidateProvHandle
0x1800133fe  mov     r11, rax
0x180013401  test    rax, rax
0x180013404  jnz     short loc_18001345D
0x180013406  mov     ebx, 80090026h
0x18001340b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013412  lea     rax, WPP_GLOBAL_Control
0x180013419  cmp     rcx, rax
0x18001341c  jz      loc_18001354E
0x180013422  test    byte ptr [rcx+1Ch], 1
0x180013426  jz      loc_18001354E
0x18001342c  mov     rcx, [rcx+10h]
0x180013430  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013437  mov     dword ptr [rsp+48h+var_18], 0BCh
0x18001343f  lea     r9, aStatus; "Status"
0x180013446  mov     [rsp+48h+var_20], r8
0x18001344b  mov     dword ptr [rsp+48h+var_28], 80090026h
0x180013453  call    WPP_SF_sDsd
0x180013458  jmp     loc_18001354E
0x18001345d  mov     rcx, rdx
0x180013460  call    SslpValidateMasterKeyHandle
0x180013465  mov     rdx, rax
0x180013468  test    rax, rax
0x18001346b  jnz     short loc_180013495
0x18001346d  mov     r9d, 0C5h
0x180013473  mov     ebx, 80090026h
0x180013478  mov     ecx, 80090026h
0x18001347d  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013484  lea     rdx, aStatus; "Status"
0x18001348b  call    DebugTraceError
0x180013490  jmp     loc_18001354E
0x180013495  mov     rcx, r8
0x180013498  call    SslpValidateHashHandle
0x18001349d  mov     rcx, rax
0x1800134a0  test    rax, rax
0x1800134a3  jnz     short loc_1800134AD
0x1800134a5  mov     r9d, 0CEh
0x1800134ab  jmp     short loc_180013473
0x1800134ad  cmp     [rsp+48h+arg_38], 0
0x1800134b5  jz      short loc_1800134C9
0x1800134b7  mov     ebx, 80090009h
0x1800134bc  mov     r9d, 0D5h
0x1800134c2  mov     ecx, 80090009h
0x1800134c7  jmp     short loc_18001347D
0x1800134c9  cmp     dword ptr [rdx+8], 301h
0x1800134d0  jb      short loc_180013504
0x1800134d2  mov     rax, [rsp+48h+arg_30]
0x1800134da  mov     rdx, r10
0x1800134dd  mov     r9d, [rsp+48h+arg_28]
0x1800134e2  mov     r8, [rsp+48h+arg_20]
0x1800134e7  mov     [rsp+48h+var_28], rax
0x1800134ec  call    Tls1ComputeClientAuthHash
0x1800134f1  mov     ebx, eax
0x1800134f3  test    eax, eax
0x1800134f5  jns     short loc_180013545
0x1800134f7  mov     r9d, 0E6h
0x1800134fd  mov     ecx, eax
0x1800134ff  jmp     loc_18001347D
0x180013504  cmp     dword ptr [rdx+8], 300h
0x18001350b  jnz     short loc_180013549
0x18001350d  mov     rax, [rsp+48h+arg_30]
0x180013515  mov     r8, rcx
0x180013518  mov     [rsp+48h+var_18], rax
0x18001351d  mov     rcx, r11
0x180013520  mov     eax, [rsp+48h+arg_28]
0x180013524  mov     dword ptr [rsp+48h+var_20], eax
0x180013528  mov     rax, [rsp+48h+arg_20]
0x18001352d  mov     [rsp+48h+var_28], rax
0x180013532  call    Ssl3ComputeClientAuthHash
0x180013537  mov     ebx, eax
0x180013539  test    eax, eax
0x18001353b  jns     short loc_180013545
0x18001353d  mov     r9d, 0F6h
0x180013543  jmp     short loc_1800134FD
0x180013545  xor     ebx, ebx
0x180013547  jmp     short loc_18001354E
0x180013549  mov     ebx, 80090029h
0x18001354e  mov     eax, ebx
0x180013550  add     rsp, 40h
0x180013554  pop     rbx
0x180013555  retn
```
