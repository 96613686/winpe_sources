# SPSslImportMasterKey

- ea: `0x180011f10`
- end: `0x1800121dc`
- name: `SPSslImportMasterKey`
- size: `716`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180003ef0`
- `0x180005e50`
- `0x1800066f0`
- `0x1800068e0`
- `0x180007940`
- `0x180007de4`
- `0x18000b594`
- `0x18000b654`
- `0x180011f10`
- `0x1800121f0`
- `0x180025660`

## string_xrefs

- `0x18001205d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800120ad`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800120f5`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18001210b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180012164`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslImportMasterKey(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        int a8,
        int a9)
{
  int v12; // edx
  unsigned int v13; // r9d
  __int64 v14; // r13
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r15
  _DWORD *v19; // rax
  _DWORD *v20; // rdi
  int v21; // eax
  unsigned int v22; // ebx
  __int64 v24; // rcx
  _QWORD *v25; // rcx
  __int64 v26; // r9
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // r9
  char v30; // [rsp+20h] [rbp-68h]
  char v31; // [rsp+30h] [rbp-58h]

  v14 = SslpValidateProvHandle(a1);
  if ( !v14 )
  {
    v22 = -2146893786;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v22;
    v31 = 58;
    v30 = 38;
    goto LABEL_21;
  }
  v15 = LookupCipherSuite(v13, a5);
  if ( !v15 )
  {
    v22 = -2146893783;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v22;
    v24 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v31 = 67;
    v30 = 41;
LABEL_17:
    WPP_SF_sDsd(
      v24,
      v12,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
      (unsigned int)"Status",
      v30,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
      v31);
    return v22;
  }
  v16 = SslpValidateKeyPairHandle(a2);
  if ( !v16 )
  {
    v16 = SslpValidateEphemeralHandle(v17);
    if ( !v16 )
    {
      v22 = -2146893786;
      v26 = 3922;
      v27 = 2148073510LL;
LABEL_30:
      DebugTraceError(v27, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v26);
      return v22;
    }
  }
  v18 = *(_QWORD *)(v16 + 24);
  if ( !a3 )
  {
    v22 = -2146893785;
    v26 = 3935;
    v27 = 2148073511LL;
    goto LABEL_30;
  }
  if ( *(_DWORD *)(v15 + 100) != 1 )
  {
    v22 = -2146893816;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v22;
    v31 = 104;
    v30 = 8;
LABEL_21:
    v24 = v25[2];
    goto LABEL_17;
  }
  if ( a7 && a8 )
  {
    if ( (a9 & 0xFFFFFFFD) != 0 )
    {
      v22 = -2146893815;
      v26 = 3958;
      v27 = 2148073481LL;
      goto LABEL_30;
    }
    v19 = (_DWORD *)SafeAllocaAllocateFromHeap(80);
    v20 = v19;
    if ( v19 )
    {
      memset(v19, 0, 0x50u);
      *v20 = 80;
      v20[1] = 1936944181;
      v20[2] = a4;
      *((_QWORD *)v20 + 2) = v15;
      if ( a4 == 2 )
      {
        v22 = -2146893783;
        v28 = 2148073513LL;
        v29 = 3991;
      }
      else
      {
        v21 = TlsDecryptMasterKey(v14, v18, v20, a6, a7, *(_DWORD *)(v15 + 112), a8);
        v22 = v21;
        if ( v21 >= 0 )
        {
          *a3 = v20;
          return 0;
        }
        v28 = (unsigned int)v21;
        v29 = 4006;
      }
    }
    else
    {
      v22 = -2146893810;
      v28 = 2148073486LL;
      v29 = 3972;
    }
  }
  else
  {
    v20 = 0;
    v22 = -2146893785;
    v28 = 2148073511LL;
    v29 = 3951;
  }
  DebugTraceError(v28, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v29);
  if ( v20 )
    MSCryptFree(v20);
  return v22;
}

```

## disassembly

```asm
0x180011f10  push    rbx
0x180011f12  push    rbp
0x180011f13  push    rsi
0x180011f14  push    rdi
0x180011f15  push    r12
0x180011f17  push    r13
0x180011f19  push    r14
0x180011f1b  push    r15
0x180011f1d  sub     rsp, 48h
0x180011f21  mov     r12d, r9d
0x180011f24  mov     r14, r8
0x180011f27  mov     rdi, rdx
0x180011f2a  call    SslpValidateProvHandle
0x180011f2f  mov     r13, rax
0x180011f32  test    rax, rax
0x180011f35  jz      loc_180012087
0x180011f3b  mov     edx, [rsp+88h+arg_20]
0x180011f42  mov     ecx, r9d
0x180011f45  call    LookupCipherSuite
0x180011f4a  mov     rbx, rax
0x180011f4d  test    rax, rax
0x180011f50  jz      loc_18001203A
0x180011f56  mov     rcx, rdi
0x180011f59  call    SslpValidateKeyPairHandle
0x180011f5e  test    rax, rax
0x180011f61  jz      loc_180012134
0x180011f67  mov     r15, [rax+18h]
0x180011f6b  test    r14, r14
0x180011f6e  jz      loc_18001217C
0x180011f74  cmp     dword ptr [rbx+64h], 1
0x180011f78  jnz     loc_1800120C7
0x180011f7e  mov     rsi, [rsp+88h+arg_30]
0x180011f86  test    rsi, rsi
0x180011f89  jz      loc_1800121C5
0x180011f8f  mov     ebp, [rsp+88h+arg_38]
0x180011f96  test    ebp, ebp
0x180011f98  jz      loc_1800121C5
0x180011f9e  test    [rsp+88h+arg_40], 0FFFFFFFDh
0x180011fa9  jnz     loc_180012154
0x180011faf  mov     ecx, 50h ; 'P'
0x180011fb4  call    SafeAllocaAllocateFromHeap
0x180011fb9  mov     rdi, rax
0x180011fbc  test    rax, rax
0x180011fbf  jz      loc_18001218E
0x180011fc5  xor     edx, edx; Val
0x180011fc7  mov     rcx, rax; void *
0x180011fca  lea     r8d, [rdx+50h]; Size
0x180011fce  call    memset
0x180011fd3  mov     dword ptr [rdi], 50h ; 'P'
0x180011fd9  mov     dword ptr [rdi+4], 73736C35h
0x180011fe0  mov     [rdi+8], r12d
0x180011fe4  mov     [rdi+10h], rbx
0x180011fe8  cmp     r12d, 2
0x180011fec  jz      loc_1800121A3
0x180011ff2  mov     eax, [rbx+70h]
0x180011ff5  mov     r8, rdi
0x180011ff8  mov     r9, [rsp+88h+arg_28]
0x180012000  mov     rdx, r15
0x180012003  mov     dword ptr [rsp+88h+var_58], ebp
0x180012007  mov     rcx, r13
0x18001200a  mov     dword ptr [rsp+88h+var_60], eax
0x18001200e  mov     [rsp+88h+var_68], rsi
0x180012013  call    TlsDecryptMasterKey
0x180012018  mov     ebx, eax
0x18001201a  test    eax, eax
0x18001201c  js      loc_1800121B8
0x180012022  mov     [r14], rdi
0x180012025  xor     ebx, ebx
0x180012027  mov     eax, ebx
0x180012029  add     rsp, 48h
0x18001202d  pop     r15
0x18001202f  pop     r14
0x180012031  pop     r13
0x180012033  pop     r12
0x180012035  pop     rdi
0x180012036  pop     rsi
0x180012037  pop     rbp
0x180012038  pop     rbx
0x180012039  retn
0x18001203a  mov     ebx, 80090029h
0x18001203f  mov     r10, cs:WPP_GLOBAL_Control
0x180012046  lea     rax, WPP_GLOBAL_Control
0x18001204d  cmp     r10, rax
0x180012050  jz      short loc_180012027
0x180012052  test    byte ptr [r10+1Ch], 1
0x180012057  jz      short loc_180012027
0x180012059  mov     rcx, [r10+10h]
0x18001205d  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012064  mov     dword ptr [rsp+88h+var_58], 0F43h
0x18001206c  mov     [rsp+88h+var_60], r8
0x180012071  mov     dword ptr [rsp+88h+var_68], 80090029h
0x180012079  lea     r9, aStatus; "Status"
0x180012080  call    WPP_SF_sDsd
0x180012085  jmp     short loc_180012027
0x180012087  mov     ebx, 80090026h
0x18001208c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012093  lea     rax, WPP_GLOBAL_Control
0x18001209a  cmp     rcx, rax
0x18001209d  jz      short loc_180012027
0x18001209f  test    byte ptr [rcx+1Ch], 1
0x1800120a3  jz      short loc_180012027
0x1800120a5  mov     dword ptr [rsp+88h+var_58], 0F3Ah
0x1800120ad  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800120b4  mov     [rsp+88h+var_60], r8
0x1800120b9  mov     dword ptr [rsp+88h+var_68], 80090026h
0x1800120c1  mov     rcx, [rcx+10h]
0x1800120c5  jmp     short loc_180012079
0x1800120c7  mov     ebx, 80090008h
0x1800120cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800120d3  lea     rax, WPP_GLOBAL_Control
0x1800120da  cmp     rcx, rax
0x1800120dd  jz      loc_180012027
0x1800120e3  test    byte ptr [rcx+1Ch], 1
0x1800120e7  jz      loc_180012027
0x1800120ed  mov     dword ptr [rsp+88h+var_58], 0F68h
0x1800120f5  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800120fc  mov     [rsp+88h+var_60], r8
0x180012101  mov     dword ptr [rsp+88h+var_68], 80090008h
0x180012109  jmp     short loc_1800120C1
0x18001210b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012112  lea     rdx, aStatus; "Status"
0x180012119  call    DebugTraceError
0x18001211e  test    rdi, rdi
0x180012121  jz      loc_180012027
0x180012127  mov     rcx, rdi
0x18001212a  call    MSCryptFree
0x18001212f  jmp     loc_180012027
0x180012134  call    SslpValidateEphemeralHandle
0x180012139  test    rax, rax
0x18001213c  jnz     loc_180011F67
0x180012142  mov     ebx, 80090026h
0x180012147  mov     r9d, 0F52h
0x18001214d  mov     ecx, 80090026h
0x180012152  jmp     short loc_180012164
0x180012154  mov     ebx, 80090009h
0x180012159  mov     r9d, 0F76h
0x18001215f  mov     ecx, 80090009h
0x180012164  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001216b  lea     rdx, aStatus; "Status"
0x180012172  call    DebugTraceError
0x180012177  jmp     loc_180012027
0x18001217c  mov     ebx, 80090027h
0x180012181  mov     r9d, 0F5Fh
0x180012187  mov     ecx, 80090027h
0x18001218c  jmp     short loc_180012164
0x18001218e  mov     ebx, 8009000Eh
0x180012193  mov     ecx, 8009000Eh
0x180012198  mov     r9d, 0F84h
0x18001219e  jmp     loc_18001210B
0x1800121a3  mov     ebx, 80090029h
0x1800121a8  mov     ecx, 80090029h
0x1800121ad  mov     r9d, 0F97h
0x1800121b3  jmp     loc_18001210B
0x1800121b8  mov     ecx, eax
0x1800121ba  mov     r9d, 0FA6h
0x1800121c0  jmp     loc_18001210B
0x1800121c5  xor     edi, edi
0x1800121c7  mov     ebx, 80090027h
0x1800121cc  mov     ecx, 80090027h
0x1800121d1  mov     r9d, 0F6Fh
0x1800121d7  jmp     loc_18001210B
```
