# Int_FwValidatePhase2CryptoSuite

- ea: `0x180017718`
- end: `0x180017b2f`
- name: `Int_FwValidatePhase2CryptoSuite`
- size: `1047`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016650`

## callees

- `0x18000ccd4`
- `0x180017718`
- `0x180017d1c`
- `0x18002f38c`

## string_xrefs

- `0x1800177d2`: `MPSSVC.dll`

## pseudocode

```c
__int64 __fastcall Int_FwValidatePhase2CryptoSuite(__int64 a1, _DWORD *a2)
{
  __int64 v4; // rcx
  unsigned int v5; // edi
  unsigned int v6; // r15d
  __int64 v7; // r14
  int v8; // edx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v11; // edx
  unsigned int v12; // r8d
  unsigned int v13; // edx
  int v14; // edx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 436, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
  if ( !*(_DWORD *)(a1 + 52) || (v4 = *(_QWORD *)(a1 + 56)) == 0 )
  {
    *a2 = 1052704;
    v5 = 87;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v5;
    v10 = 437;
LABEL_73:
    WPP_SF_d(v9[2], v10, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
    return v5;
  }
  if ( (unsigned int)(*(_DWORD *)(a1 + 48) - 1) > 7 )
  {
    *a2 = 1069088;
    v5 = 87;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v5;
    v10 = 438;
    goto LABEL_73;
  }
  v5 = 0;
  v6 = 0;
  while ( 1 )
  {
    v7 = 28LL * v6;
    if ( (unsigned int)(*(_DWORD *)(v7 + v4) - 1) > 3 )
      break;
    if ( *(_DWORD *)(v7 + v4) == 1 )
    {
      v14 = *(_DWORD *)(v7 + v4 + 4);
      if ( (unsigned int)(v14 - 1) > 6 || v14 == 4 )
      {
        *a2 = 1069091;
        v5 = 87;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 440;
          goto LABEL_73;
        }
        return v5;
      }
    }
    else
    {
      if ( *(_DWORD *)(v7 + v4) != 2 )
      {
        if ( *(_DWORD *)(v7 + v4) != 3 )
        {
          if ( *(_DWORD *)(v7 + v4) == 4 )
          {
            v8 = *(_DWORD *)(v7 + v4 + 8);
            if ( (unsigned int)(v8 - 1) > 6 || v8 == 4 )
            {
              *a2 = 1069091;
              v5 = 87;
              v9 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v10 = 441;
                goto LABEL_73;
              }
              return v5;
            }
          }
          else
          {
            MicrosoftTelemetryAssertTriggeredArgs((__int64)"MPSSVC.dll", *(_DWORD *)(v7 + v4), 0);
          }
          goto LABEL_39;
        }
        v11 = *(_DWORD *)(v7 + v4 + 4);
        if ( v11 != *(_DWORD *)(v7 + v4 + 8) || (unsigned int)(v11 - 1) > 6 || v11 == 4 )
        {
          *a2 = 1069091;
          v5 = 87;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v10 = 442;
            goto LABEL_73;
          }
          return v5;
        }
      }
      v12 = *(_DWORD *)(v7 + v4 + 8);
      if ( v12 > 7 || v12 == 4 )
      {
        *a2 = 1069091;
        v5 = 87;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 443;
          goto LABEL_73;
        }
        return v5;
      }
      v13 = *(_DWORD *)(v7 + v4 + 12);
      if ( v13 > 8 )
      {
        *a2 = 1069090;
        v5 = 87;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 444;
          goto LABEL_73;
        }
        return v5;
      }
      if ( !v12 && !v13 )
      {
        *a2 = 1069120;
        v5 = 87;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 445;
          goto LABEL_73;
        }
        return v5;
      }
      if ( v13 - 6 <= 2 && (v13 != 6 || v12 != 5) && (v13 != 7 || v12 != 6) && (v13 != 8 || v12 != 7) )
      {
        *a2 = 1069121;
        v5 = 87;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 446;
          goto LABEL_73;
        }
        return v5;
      }
    }
LABEL_39:
    v4 = *(_QWORD *)(a1 + 56);
    if ( (unsigned int)(*(_DWORD *)(v7 + v4 + 16) - 5) > 0xB3A )
    {
      *a2 = 1069092;
      v5 = 87;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 447;
        goto LABEL_73;
      }
      return v5;
    }
    if ( (unsigned int)(*(_DWORD *)(v7 + v4 + 20) - 20480) > 0x7FFFAFFF )
    {
      *a2 = 1069093;
      v5 = 87;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 448;
        goto LABEL_73;
      }
      return v5;
    }
    if ( ++v6 >= *(_DWORD *)(a1 + 52) )
      return v5;
  }
  *a2 = 1069089;
  v5 = 87;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 439;
    goto LABEL_73;
  }
  return v5;
}

```

## disassembly

```asm
0x180017718  push    rbp
0x18001771a  push    rsi
0x18001771b  push    rdi
0x18001771c  push    r12
0x18001771e  push    r13
0x180017720  push    r14
0x180017722  push    r15
0x180017724  sub     rsp, 20h
0x180017728  mov     rsi, rdx
0x18001772b  mov     rbp, rcx
0x18001772e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017735  lea     r12, WPP_GLOBAL_Control
0x18001773c  lea     r13, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x180017743  cmp     rcx, r12
0x180017746  jz      short loc_18001775F
0x180017748  test    byte ptr [rcx+1Ch], 8
0x18001774c  jz      short loc_18001775F
0x18001774e  mov     rcx, [rcx+10h]
0x180017752  mov     edx, 1B4h
0x180017757  mov     r8, r13
0x18001775a  call    WPP_SF_
0x18001775f  mov     edx, [rbp+34h]
0x180017762  test    edx, edx
0x180017764  jz      loc_180017AEB
0x18001776a  mov     rcx, [rbp+38h]
0x18001776e  test    rcx, rcx
0x180017771  jz      loc_180017AEB
0x180017777  mov     eax, [rbp+30h]
0x18001777a  dec     eax
0x18001777c  cmp     eax, 7
0x18001777f  ja      loc_180017AC3
0x180017785  xor     edi, edi
0x180017787  xor     r15d, r15d
0x18001778a  test    edx, edx
0x18001778c  jz      loc_180017B1D
0x180017792  mov     eax, r15d
0x180017795  imul    r14, rax, 1Ch
0x180017799  mov     eax, [r14+rcx]
0x18001779d  dec     eax
0x18001779f  cmp     eax, 3
0x1800177a2  ja      loc_180017A9B
0x1800177a8  mov     edx, [r14+rcx]
0x1800177ac  mov     r8d, edx
0x1800177af  sub     r8d, 1
0x1800177b3  jz      loc_1800178E1
0x1800177b9  sub     r8d, 1
0x1800177bd  jz      loc_180017851
0x1800177c3  sub     r8d, 1
0x1800177c7  jz      short loc_18001782C
0x1800177c9  cmp     r8d, 1
0x1800177cd  jz      short loc_1800177E3
0x1800177cf  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "FALSE", "pCrypto->pPhase2Suites[dwIndex].Protocol")
0x1800177d2  lea     rcx, aMpssvcDll; "MPSSVC.dll"
0x1800177d9  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800177de  jmp     loc_1800178FB
0x1800177e3  mov     edx, [r14+rcx+8]
0x1800177e8  lea     eax, [rdx-1]
0x1800177eb  cmp     eax, 6
0x1800177ee  ja      short loc_1800177F9
0x1800177f0  cmp     edx, 4
0x1800177f3  jnz     loc_1800178FB
0x1800177f9  mov     r9d, 57h ; 'W'
0x1800177ff  mov     dword ptr [rsi], 105023h
0x180017805  mov     edi, r9d
0x180017808  mov     rcx, cs:WPP_GLOBAL_Control
0x18001780f  cmp     rcx, r12
0x180017812  jz      loc_180017B1D
0x180017818  test    byte ptr [rcx+1Ch], 1
0x18001781c  jz      loc_180017B1D
0x180017822  mov     edx, 1B9h
0x180017827  jmp     loc_180017B11
0x18001782c  mov     edx, [r14+rcx+4]
0x180017831  cmp     edx, [r14+rcx+8]
0x180017836  jnz     loc_180017939
0x18001783c  lea     eax, [rdx-1]
0x18001783f  cmp     eax, 6
0x180017842  ja      loc_180017939
0x180017848  cmp     edx, 4
0x18001784b  jz      loc_180017939
0x180017851  mov     r8d, [r14+rcx+8]
0x180017856  cmp     r8d, 7
0x18001785a  ja      loc_1800179D2
0x180017860  cmp     r8d, 4
0x180017864  jz      loc_1800179D2
0x18001786a  mov     edx, [r14+rcx+0Ch]
0x18001786f  cmp     edx, 8
0x180017872  ja      loc_18001799F
0x180017878  test    r8d, r8d
0x18001787b  jnz     short loc_180017885
0x18001787d  test    edx, edx
0x18001787f  jz      loc_18001796C
0x180017885  lea     eax, [rdx-6]
0x180017888  cmp     eax, 2
0x18001788b  ja      short loc_1800178FB
0x18001788d  cmp     edx, 6
0x180017890  jnz     short loc_180017898
0x180017892  cmp     r8d, 5
0x180017896  jz      short loc_1800178FB
0x180017898  cmp     edx, 7
0x18001789b  jnz     short loc_1800178A3
0x18001789d  cmp     r8d, 6
0x1800178a1  jz      short loc_1800178FB
0x1800178a3  cmp     edx, 8
0x1800178a6  jnz     short loc_1800178AE
0x1800178a8  cmp     r8d, 7
0x1800178ac  jz      short loc_1800178FB
0x1800178ae  mov     r9d, 57h ; 'W'
0x1800178b4  mov     dword ptr [rsi], 105041h
0x1800178ba  mov     edi, r9d
0x1800178bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800178c4  cmp     rcx, r12
0x1800178c7  jz      loc_180017B1D
0x1800178cd  test    byte ptr [rcx+1Ch], 1
0x1800178d1  jz      loc_180017B1D
0x1800178d7  mov     edx, 1BEh
0x1800178dc  jmp     loc_180017B11
0x1800178e1  mov     edx, [r14+rcx+4]
0x1800178e6  lea     eax, [rdx-1]
0x1800178e9  cmp     eax, 6
0x1800178ec  ja      loc_180017A6B
0x1800178f2  cmp     edx, 4
0x1800178f5  jz      loc_180017A6B
0x1800178fb  mov     rcx, [rbp+38h]
0x1800178ff  mov     eax, [r14+rcx+10h]
0x180017904  sub     eax, 5
0x180017907  cmp     eax, 0B3Ah
0x18001790c  ja      loc_180017A38
0x180017912  mov     eax, [r14+rcx+14h]
0x180017917  sub     eax, 5000h
0x18001791c  cmp     eax, 7FFFAFFFh
0x180017921  ja      loc_180017A05
0x180017927  inc     r15d
0x18001792a  cmp     r15d, [rbp+34h]
0x18001792e  jb      loc_180017792
0x180017934  jmp     loc_180017B1D
0x180017939  mov     r9d, 57h ; 'W'
0x18001793f  mov     dword ptr [rsi], 105023h
0x180017945  mov     edi, r9d
0x180017948  mov     rcx, cs:WPP_GLOBAL_Control
0x18001794f  cmp     rcx, r12
0x180017952  jz      loc_180017B1D
0x180017958  test    byte ptr [rcx+1Ch], 1
0x18001795c  jz      loc_180017B1D
0x180017962  mov     edx, 1BAh
0x180017967  jmp     loc_180017B11
0x18001796c  mov     r9d, 57h ; 'W'
0x180017972  mov     dword ptr [rsi], 105040h
0x180017978  mov     edi, r9d
0x18001797b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017982  cmp     rcx, r12
0x180017985  jz      loc_180017B1D
0x18001798b  test    byte ptr [rcx+1Ch], 1
0x18001798f  jz      loc_180017B1D
0x180017995  mov     edx, 1BDh
0x18001799a  jmp     loc_180017B11
0x18001799f  mov     r9d, 57h ; 'W'
0x1800179a5  mov     dword ptr [rsi], 105022h
0x1800179ab  mov     edi, r9d
0x1800179ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800179b5  cmp     rcx, r12
0x1800179b8  jz      loc_180017B1D
0x1800179be  test    byte ptr [rcx+1Ch], 1
0x1800179c2  jz      loc_180017B1D
0x1800179c8  mov     edx, 1BCh
0x1800179cd  jmp     loc_180017B11
0x1800179d2  mov     r9d, 57h ; 'W'
0x1800179d8  mov     dword ptr [rsi], 105023h
0x1800179de  mov     edi, r9d
0x1800179e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800179e8  cmp     rcx, r12
0x1800179eb  jz      loc_180017B1D
0x1800179f1  test    byte ptr [rcx+1Ch], 1
0x1800179f5  jz      loc_180017B1D
0x1800179fb  mov     edx, 1BBh
0x180017a00  jmp     loc_180017B11
0x180017a05  mov     r9d, 57h ; 'W'
0x180017a0b  mov     dword ptr [rsi], 105025h
0x180017a11  mov     edi, r9d
0x180017a14  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a1b  cmp     rcx, r12
0x180017a1e  jz      loc_180017B1D
0x180017a24  test    byte ptr [rcx+1Ch], 1
0x180017a28  jz      loc_180017B1D
0x180017a2e  mov     edx, 1C0h
0x180017a33  jmp     loc_180017B11
0x180017a38  mov     r9d, 57h ; 'W'
0x180017a3e  mov     dword ptr [rsi], 105024h
0x180017a44  mov     edi, r9d
0x180017a47  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a4e  cmp     rcx, r12
0x180017a51  jz      loc_180017B1D
0x180017a57  test    byte ptr [rcx+1Ch], 1
0x180017a5b  jz      loc_180017B1D
0x180017a61  mov     edx, 1BFh
0x180017a66  jmp     loc_180017B11
0x180017a6b  mov     r9d, 57h ; 'W'
0x180017a71  mov     dword ptr [rsi], 105023h
0x180017a77  mov     edi, r9d
0x180017a7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a81  cmp     rcx, r12
0x180017a84  jz      loc_180017B1D
0x180017a8a  test    byte ptr [rcx+1Ch], 1
0x180017a8e  jz      loc_180017B1D
0x180017a94  mov     edx, 1B8h
0x180017a99  jmp     short loc_180017B11
0x180017a9b  mov     r9d, 57h ; 'W'
0x180017aa1  mov     dword ptr [rsi], 105021h
0x180017aa7  mov     edi, r9d
0x180017aaa  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ab1  cmp     rcx, r12
0x180017ab4  jz      short loc_180017B1D
0x180017ab6  test    byte ptr [rcx+1Ch], 1
0x180017aba  jz      short loc_180017B1D
0x180017abc  mov     edx, 1B7h
0x180017ac1  jmp     short loc_180017B11
0x180017ac3  mov     r9d, 57h ; 'W'
0x180017ac9  mov     dword ptr [rsi], 105020h
0x180017acf  mov     edi, r9d
0x180017ad2  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ad9  cmp     rcx, r12
0x180017adc  jz      short loc_180017B1D
0x180017ade  test    byte ptr [rcx+1Ch], 1
0x180017ae2  jz      short loc_180017B1D
0x180017ae4  mov     edx, 1B6h
0x180017ae9  jmp     short loc_180017B11
0x180017aeb  mov     r9d, 57h ; 'W'
0x180017af1  mov     dword ptr [rsi], 101020h
0x180017af7  mov     edi, r9d
0x180017afa  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b01  cmp     rcx, r12
0x180017b04  jz      short loc_180017B1D
0x180017b06  test    byte ptr [rcx+1Ch], 1
0x180017b0a  jz      short loc_180017B1D
0x180017b0c  mov     edx, 1B5h
0x180017b11  mov     rcx, [rcx+10h]
0x180017b15  mov     r8, r13
0x180017b18  call    WPP_SF_d
0x180017b1d  mov     eax, edi
0x180017b1f  add     rsp, 20h
0x180017b23  pop     r15
0x180017b25  pop     r14
0x180017b27  pop     r13
0x180017b29  pop     r12
0x180017b2b  pop     rdi
0x180017b2c  pop     rsi
0x180017b2d  pop     rbp
0x180017b2e  retn
```
