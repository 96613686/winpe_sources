# MSCryptHashResultInternal

- ea: `0x18001b688`
- end: `0x18001bb91`
- name: `MSCryptHashResultInternal`
- size: `1289`
- prototype: ``
- caller_count: `2`
- callee_count: `31`
- tags: `broker_com_uri`

## callers

- `0x18001bba0`
- `0x180045a00`

## callees

- `0x180001780`
- `0x1800019d0`
- `0x180001c20`
- `0x180001d20`
- `0x18001155c`
- `0x1800123d0`
- `0x18001b688`
- `0x18001cc10`
- `0x180022230`
- `0x180022580`
- `0x180037bd0`
- `0x180037d40`
- `0x18003b42c`
- `0x18003be40`
- `0x18003bf30`
- `0x18003eef0`
- `0x180046440`
- `0x180046ef0`
- `0x18004a370`
- `0x18006ea00`
- `0x18006ea50`
- `0x1800914d0`
- `0x18009a800`
- `0x18009a92c`
- `0x18009abd0`
- `0x18009ac00`
- `0x18009b3d0`
- `0x18009b458`
- `0x18009b8f0`
- `0x18009f5a8`
- `0x18009f630`

## string_xrefs

- `0x18001b78e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18001bb6e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptHashResultInternal(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  __int64 v4; // r15
  unsigned int v7; // esi
  int v8; // ebx
  bool v9; // r14
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rdx

  v4 = a3;
  v7 = 0;
  v8 = 1;
  v9 = (a4 & 1) == 0;
  switch ( *(_DWORD *)(a1 + 8) )
  {
    case 0x20001:
      if ( *(_DWORD *)(a1 + 12) != 16 )
      {
        v10 = 2399;
        goto LABEL_4;
      }
      SymCryptMd5Result(a1 + 128);
      return v7;
    case 0x20002:
      if ( *(_DWORD *)(a1 + 12) != 20 )
      {
        v10 = 2416;
        goto LABEL_4;
      }
      SymCryptSha1Result(a1 + 128, a2);
      return v7;
    case 0x20003:
      if ( *(_DWORD *)(a1 + 12) != 16 )
      {
        v10 = 2433;
        goto LABEL_4;
      }
      SymCryptMd2Result(a1 + 128);
      return v7;
    case 0x20004:
      if ( *(_DWORD *)(a1 + 12) != 16 )
      {
        v10 = 2450;
        goto LABEL_4;
      }
      SymCryptMd4Result(a1 + 128);
      return v7;
    case 0x20005:
      if ( *(_DWORD *)(a1 + 12) == 32 )
      {
        SymCryptSha256Result(a1 + 128);
      }
      else
      {
        v7 = -1073741816;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            a2,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
            (unsigned int)"Status",
            8,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
            163);
      }
      return v7;
    case 0x20006:
      if ( *(_DWORD *)(a1 + 12) != 48 )
      {
        v10 = 2484;
        goto LABEL_4;
      }
      SymCryptSha384Result(a1 + 128);
      return v7;
    case 0x20007:
      if ( *(_DWORD *)(a1 + 12) != 64 )
      {
        v10 = 2501;
        goto LABEL_4;
      }
      SymCryptSha512Result(a1 + 128);
      return v7;
    case 0x20008:
      if ( !*(_DWORD *)(a1 + 116) )
      {
        v7 = -1073740758;
        v10 = 2518;
        v11 = 3221226538LL;
        goto LABEL_83;
      }
      if ( *(_DWORD *)(a1 + 12) != 16 )
      {
        v10 = 2525;
        goto LABEL_4;
      }
      SymCryptGcmEncryptFinal(a1 + 2736, a2, 16);
      *(_DWORD *)(a1 + 116) = 0;
      return v7;
    case 0x20009:
      if ( *(_DWORD *)(a1 + 12) != 20 )
      {
        v10 = 2548;
        goto LABEL_4;
      }
      SymCryptHmacSha1Result(a1 + 208);
      SymCryptHmacSha1Init(a1 + 208, a1 + 128);
      return v7;
    case 0x2000A:
      if ( *(_DWORD *)(a1 + 12) != 16 )
      {
        v10 = 2566;
        goto LABEL_4;
      }
      SymCryptHmacMd5Result(a1 + 176);
      SymCryptHmacMd5Init(a1 + 176, a1 + 128);
      return v7;
    case 0x2000B:
      if ( *(_DWORD *)(a1 + 12) != 32 )
      {
        v10 = 2584;
        goto LABEL_4;
      }
      SymCryptHmacSha256Result(a1 + 208);
      SymCryptHmacSha256Init(a1 + 208, a1 + 128);
      return v7;
    case 0x2000C:
      if ( *(_DWORD *)(a1 + 12) != 48 )
      {
        v10 = 2602;
        goto LABEL_4;
      }
      SymCryptHmacSha384Result(a1 + 272);
      SymCryptHmacSha512Init(a1 + 272, a1 + 128);
      return v7;
    case 0x2000D:
      if ( *(_DWORD *)(a1 + 12) != 64 )
      {
        v10 = 2620;
        goto LABEL_4;
      }
      SymCryptHmacSha512Result(a1 + 272);
      SymCryptHmacSha512Init(a1 + 272, a1 + 128);
      return v7;
    case 0x2000E:
      if ( *(_DWORD *)(a1 + 12) != 16 )
      {
        v10 = 2638;
        goto LABEL_4;
      }
      SymCryptAesCmacResult(a1 + 672);
      *(_QWORD *)(a1 + 704) = 0;
      *(_QWORD *)(a1 + 672) = 0;
      *(_QWORD *)(a1 + 680) = 0;
      *(_QWORD *)(a1 + 712) = a1 + 128;
      return v7;
    case 0x2000F:
      if ( *(_DWORD *)(a1 + 12) != 32 )
      {
        v10 = 2656;
        goto LABEL_4;
      }
      SymCryptShake128Result(a1 + 128);
      return v7;
    case 0x20010:
      if ( *(_DWORD *)(a1 + 12) != 48 )
      {
        v10 = 2673;
        goto LABEL_4;
      }
      SymCryptSha3_384Result(a1 + 128);
      return v7;
    case 0x20011:
      if ( *(_DWORD *)(a1 + 12) != 64 )
      {
        v10 = 2690;
        goto LABEL_4;
      }
      SymCryptSha3_512Result(a1 + 128);
      return v7;
    case 0x20012:
      if ( *(_DWORD *)(a1 + 12) == 32 )
        goto LABEL_60;
      v10 = 2707;
      goto LABEL_4;
    case 0x20013:
      if ( *(_DWORD *)(a1 + 12) == 48 )
        goto LABEL_60;
      v10 = 2725;
      goto LABEL_4;
    case 0x20014:
      if ( *(_DWORD *)(a1 + 12) == 64 )
      {
LABEL_60:
        SymCryptHmacResult(a1 + 640);
        SymCryptHmacInit(a1 + 640, a1 + 128);
      }
      else
      {
        v10 = 2743;
LABEL_4:
        v7 = -1073741816;
        v11 = 3221225480LL;
LABEL_83:
        DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", v10);
      }
      return v7;
    case 0x20015:
      if ( *(_DWORD *)(a1 + 280) <= 1u )
        MSCryptHashDataInternal(a1, 0);
      goto LABEL_67;
    case 0x20016:
      if ( *(_DWORD *)(a1 + 280) <= 1u )
        MSCryptHashDataInternal(a1, 0);
LABEL_67:
      LOBYTE(a4) = v9;
      SymCryptCShake256Extract(a1 + 528, a2, v4, a4);
      *(_DWORD *)(a1 + 280) = 2 * !v9 + 1;
      return v7;
    case 0x20017:
      if ( *(_DWORD *)(a1 + 528) <= 1u )
        MSCryptHashDataInternal(a1, 0);
      v12 = a1 + 544;
      v13 = v4;
      v14 = a2;
      if ( v9 )
        goto LABEL_74;
      goto LABEL_75;
    case 0x20018:
      if ( *(_DWORD *)(a1 + 528) <= 1u )
        MSCryptHashDataInternal(a1, 0);
      v12 = a1 + 544;
      v13 = v4;
      v14 = a2;
      if ( v9 )
      {
LABEL_74:
        SymCryptKmac128ResultEx(v12, v14, v13);
      }
      else
      {
LABEL_75:
        SymCryptKmac256Extract(v12, a2, v4);
        v8 = 3;
      }
      *(_DWORD *)(a1 + 528) = v8;
      return v7;
    case 0x20019:
    case 0x2001A:
      LOBYTE(a4) = (a4 & 1) == 0;
      SymCryptShake256Extract(a1 + 128, a2, a3, a4);
      return v7;
    default:
      v7 = -1073741637;
      v10 = 2886;
      v11 = 3221225659LL;
      goto LABEL_83;
  }
}

```

## disassembly

```asm
0x18001b688  push    rbx
0x18001b68a  push    rbp
0x18001b68b  push    rsi
0x18001b68c  push    rdi
0x18001b68d  push    r14
0x18001b68f  push    r15
0x18001b691  sub     rsp, 48h
0x18001b695  mov     eax, [rcx+8]
0x18001b698  mov     r14d, r9d
0x18001b69b  add     eax, 0FFFDFFFFh; switch 26 cases
0x18001b6a0  mov     r15d, r8d
0x18001b6a3  mov     rbp, rdx
0x18001b6a6  mov     rdi, rcx
0x18001b6a9  cmp     eax, 19h
0x18001b6ac  ja      def_18001B6CE; jumptable 000000018001B6CE default case
0x18001b6b2  xor     esi, esi
0x18001b6b4  lea     rcx, cs:180000000h
0x18001b6bb  mov     eax, ds:(jpt_18001B6CE - 180000000h)[rcx+rax*4]
0x18001b6c2  not     r14b
0x18001b6c5  lea     ebx, [rsi+1]
0x18001b6c8  and     r14b, bl
0x18001b6cb  add     rax, rcx
0x18001b6ce  jmp     rax; switch jump
0x18001b6d4  cmp     dword ptr [rdi+0Ch], 10h; jumptable 000000018001B6CE case 131073
0x18001b6d8  jz      short loc_18001B6EF
0x18001b6da  mov     r9d, 95Fh
0x18001b6e0  mov     esi, 0C0000008h
0x18001b6e5  mov     ecx, 0C0000008h
0x18001b6ea  jmp     loc_18001BB6E
0x18001b6ef  lea     rcx, [rdi+80h]
0x18001b6f6  call    SymCryptMd5Result
0x18001b6fb  jmp     loc_18001BB81
0x18001b700  cmp     dword ptr [rdi+0Ch], 14h; jumptable 000000018001B6CE case 131074
0x18001b704  jz      short loc_18001B70E
0x18001b706  mov     r9d, 970h
0x18001b70c  jmp     short loc_18001B6E0
0x18001b70e  lea     rcx, [rdi+80h]
0x18001b715  call    SymCryptSha1Result
0x18001b71a  jmp     loc_18001BB81
0x18001b71f  cmp     dword ptr [rdi+0Ch], 10h; jumptable 000000018001B6CE case 131075
0x18001b723  jz      short loc_18001B72D
0x18001b725  mov     r9d, 981h
0x18001b72b  jmp     short loc_18001B6E0
0x18001b72d  lea     rcx, [rdi+80h]
0x18001b734  call    SymCryptMd2Result
0x18001b739  jmp     loc_18001BB81
0x18001b73e  cmp     dword ptr [rdi+0Ch], 10h; jumptable 000000018001B6CE case 131076
0x18001b742  jz      short loc_18001B74C
0x18001b744  mov     r9d, 992h
0x18001b74a  jmp     short loc_18001B6E0
0x18001b74c  lea     rcx, [rdi+80h]
0x18001b753  call    SymCryptMd4Result
0x18001b758  jmp     loc_18001BB81
0x18001b75d  cmp     dword ptr [rdi+0Ch], 20h ; ' '; jumptable 000000018001B6CE case 131077
0x18001b761  jz      short loc_18001B7BB
0x18001b763  mov     esi, 0C0000008h
0x18001b768  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b76f  lea     rax, WPP_GLOBAL_Control
0x18001b776  cmp     rcx, rax
0x18001b779  jz      loc_18001BB81
0x18001b77f  mov     eax, [rcx+2Ch]
0x18001b782  test    bl, al
0x18001b784  jz      loc_18001BB81
0x18001b78a  mov     rcx, [rcx+18h]
0x18001b78e  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001b795  mov     [rsp+78h+var_48], 9A3h
0x18001b79d  lea     r9, aStatus; "Status"
0x18001b7a4  mov     [rsp+78h+var_50], r8
0x18001b7a9  mov     [rsp+78h+var_58], 0C0000008h
0x18001b7b1  call    WPP_SF_sDsd
0x18001b7b6  jmp     loc_18001BB81
0x18001b7bb  lea     rcx, [rdi+80h]
0x18001b7c2  call    SymCryptSha256Result
0x18001b7c7  jmp     loc_18001BB81
0x18001b7cc  cmp     dword ptr [rdi+0Ch], 30h ; '0'; jumptable 000000018001B6CE case 131078
0x18001b7d0  jz      short loc_18001B7DD
0x18001b7d2  mov     r9d, 9B4h
0x18001b7d8  jmp     loc_18001B6E0
0x18001b7dd  lea     rcx, [rdi+80h]
0x18001b7e4  call    SymCryptSha384Result
0x18001b7e9  jmp     loc_18001BB81
0x18001b7ee  cmp     dword ptr [rdi+0Ch], 40h ; '@'; jumptable 000000018001B6CE case 131079
0x18001b7f2  jz      short loc_18001B7FF
0x18001b7f4  mov     r9d, 9C5h
0x18001b7fa  jmp     loc_18001B6E0
0x18001b7ff  lea     rcx, [rdi+80h]
0x18001b806  call    SymCryptSha512Result
0x18001b80b  jmp     loc_18001BB81
0x18001b810  cmp     [rdi+74h], esi; jumptable 000000018001B6CE case 131080
0x18001b813  jnz     short loc_18001B82A
0x18001b815  mov     esi, 0C000042Ah
0x18001b81a  mov     r9d, 9D6h
0x18001b820  mov     ecx, 0C000042Ah
0x18001b825  jmp     loc_18001BB6E
0x18001b82a  cmp     dword ptr [rdi+0Ch], 10h
0x18001b82e  jz      short loc_18001B83B
0x18001b830  mov     r9d, 9DDh
0x18001b836  jmp     loc_18001B6E0
0x18001b83b  lea     rcx, [rdi+0AB0h]
0x18001b842  mov     r8d, 10h
0x18001b848  call    SymCryptGcmEncryptFinal
0x18001b84d  mov     [rdi+74h], esi
0x18001b850  jmp     loc_18001BB81
0x18001b855  cmp     dword ptr [rdi+0Ch], 14h; jumptable 000000018001B6CE case 131081
0x18001b859  jz      short loc_18001B866
0x18001b85b  mov     r9d, 9F4h
0x18001b861  jmp     loc_18001B6E0
0x18001b866  lea     rbx, [rdi+0D0h]
0x18001b86d  mov     rcx, rbx
0x18001b870  call    SymCryptHmacSha1Result
0x18001b875  lea     rdx, [rdi+80h]
0x18001b87c  mov     rcx, rbx
0x18001b87f  call    SymCryptHmacSha1Init
0x18001b884  jmp     loc_18001BB81
0x18001b889  cmp     dword ptr [rdi+0Ch], 10h; jumptable 000000018001B6CE case 131082
0x18001b88d  jz      short loc_18001B89A
0x18001b88f  mov     r9d, 0A06h
0x18001b895  jmp     loc_18001B6E0
0x18001b89a  lea     rbx, [rdi+0B0h]
0x18001b8a1  mov     rcx, rbx
0x18001b8a4  call    SymCryptHmacMd5Result
0x18001b8a9  lea     rdx, [rdi+80h]
0x18001b8b0  mov     rcx, rbx
0x18001b8b3  call    SymCryptHmacMd5Init
0x18001b8b8  jmp     loc_18001BB81
0x18001b8bd  cmp     dword ptr [rdi+0Ch], 20h ; ' '; jumptable 000000018001B6CE case 131083
0x18001b8c1  jz      short loc_18001B8CE
0x18001b8c3  mov     r9d, 0A18h
0x18001b8c9  jmp     loc_18001B6E0
0x18001b8ce  lea     rbx, [rdi+0D0h]
0x18001b8d5  mov     rcx, rbx
0x18001b8d8  call    SymCryptHmacSha256Result
0x18001b8dd  lea     rdx, [rdi+80h]
0x18001b8e4  mov     rcx, rbx
0x18001b8e7  call    SymCryptHmacSha256Init
0x18001b8ec  jmp     loc_18001BB81
0x18001b8f1  cmp     dword ptr [rdi+0Ch], 30h ; '0'; jumptable 000000018001B6CE case 131084
0x18001b8f5  jz      short loc_18001B902
0x18001b8f7  mov     r9d, 0A2Ah
0x18001b8fd  jmp     loc_18001B6E0
0x18001b902  lea     rbx, [rdi+110h]
0x18001b909  mov     rcx, rbx
0x18001b90c  call    SymCryptHmacSha384Result
0x18001b911  lea     rdx, [rdi+80h]
0x18001b918  mov     rcx, rbx
0x18001b91b  call    SymCryptHmacSha512Init
0x18001b920  jmp     loc_18001BB81
0x18001b925  cmp     dword ptr [rdi+0Ch], 40h ; '@'; jumptable 000000018001B6CE case 131085
0x18001b929  jz      short loc_18001B936
0x18001b92b  mov     r9d, 0A3Ch
0x18001b931  jmp     loc_18001B6E0
0x18001b936  lea     rbx, [rdi+110h]
0x18001b93d  mov     rcx, rbx
0x18001b940  call    SymCryptHmacSha512Result
0x18001b945  lea     rdx, [rdi+80h]
0x18001b94c  mov     rcx, rbx
0x18001b94f  call    SymCryptHmacSha512Init
0x18001b954  jmp     loc_18001BB81
0x18001b959  cmp     dword ptr [rdi+0Ch], 10h; jumptable 000000018001B6CE case 131086
0x18001b95d  jz      short loc_18001B96A
0x18001b95f  mov     r9d, 0A4Eh
0x18001b965  jmp     loc_18001B6E0
0x18001b96a  lea     rbx, [rdi+2A0h]
0x18001b971  mov     rcx, rbx
0x18001b974  call    SymCryptAesCmacResult
0x18001b979  mov     [rbx+20h], rsi
0x18001b97d  lea     rax, [rdi+80h]
0x18001b984  mov     [rbx], rsi
0x18001b987  mov     [rbx+8], rsi
0x18001b98b  mov     [rbx+28h], rax
0x18001b98f  jmp     loc_18001BB81
0x18001b994  cmp     dword ptr [rdi+0Ch], 20h ; ' '; jumptable 000000018001B6CE case 131087
0x18001b998  jz      short loc_18001B9A5
0x18001b99a  mov     r9d, 0A60h
0x18001b9a0  jmp     loc_18001B6E0
0x18001b9a5  lea     rcx, [rdi+80h]
0x18001b9ac  call    SymCryptShake128Result
0x18001b9b1  jmp     loc_18001BB81
0x18001b9b6  cmp     dword ptr [rdi+0Ch], 30h ; '0'; jumptable 000000018001B6CE case 131088
0x18001b9ba  jz      short loc_18001B9C7
0x18001b9bc  mov     r9d, 0A71h
0x18001b9c2  jmp     loc_18001B6E0
0x18001b9c7  lea     rcx, [rdi+80h]
0x18001b9ce  call    SymCryptSha3_384Result
0x18001b9d3  jmp     loc_18001BB81
0x18001b9d8  cmp     dword ptr [rdi+0Ch], 40h ; '@'; jumptable 000000018001B6CE case 131089
0x18001b9dc  jz      short loc_18001B9E9
0x18001b9de  mov     r9d, 0A82h
0x18001b9e4  jmp     loc_18001B6E0
0x18001b9e9  lea     rcx, [rdi+80h]
0x18001b9f0  call    SymCryptSha3_512Result
0x18001b9f5  jmp     loc_18001BB81
0x18001b9fa  cmp     dword ptr [rdi+0Ch], 20h ; ' '; jumptable 000000018001B6CE case 131090
0x18001b9fe  jz      short loc_18001BA0B
0x18001ba00  mov     r9d, 0A93h
0x18001ba06  jmp     loc_18001B6E0
0x18001ba0b  lea     rbx, [rdi+280h]
0x18001ba12  mov     rcx, rbx
0x18001ba15  call    SymCryptHmacResult
0x18001ba1a  lea     rdx, [rdi+80h]
0x18001ba21  mov     rcx, rbx
0x18001ba24  call    SymCryptHmacInit
0x18001ba29  jmp     loc_18001BB81
0x18001ba2e  cmp     dword ptr [rdi+0Ch], 30h ; '0'; jumptable 000000018001B6CE case 131091
0x18001ba32  jz      short loc_18001BA0B
0x18001ba34  mov     r9d, 0AA5h
0x18001ba3a  jmp     loc_18001B6E0
0x18001ba3f  cmp     dword ptr [rdi+0Ch], 40h ; '@'; jumptable 000000018001B6CE case 131092
0x18001ba43  jz      short loc_18001BA0B
0x18001ba45  mov     r9d, 0AB7h
0x18001ba4b  jmp     loc_18001B6E0
0x18001ba50  cmp     [rdi+118h], ebx; jumptable 000000018001B6CE case 131093
0x18001ba56  ja      short loc_18001BA65
0x18001ba58  xor     r8d, r8d
0x18001ba5b  xor     edx, edx
0x18001ba5d  mov     rcx, rdi
0x18001ba60  call    MSCryptHashDataInternal
0x18001ba65  mov     r8, r15
0x18001ba68  lea     rcx, [rdi+210h]
0x18001ba6f  mov     r9b, r14b
0x18001ba72  mov     rdx, rbp
0x18001ba75  call    SymCryptCShake256Extract
0x18001ba7a  movzx   eax, r14b
0x18001ba7e  xor     eax, ebx
0x18001ba80  lea     eax, ds:1[rax*2]
0x18001ba87  mov     [rdi+118h], eax
0x18001ba8d  jmp     loc_18001BB81
0x18001ba92  cmp     [rdi+118h], ebx; jumptable 000000018001B6CE case 131094
0x18001ba98  ja      short loc_18001BAA7
0x18001ba9a  xor     r8d, r8d
0x18001ba9d  xor     edx, edx
0x18001ba9f  mov     rcx, rdi
0x18001baa2  call    MSCryptHashDataInternal
0x18001baa7  mov     r8, r15
0x18001baaa  lea     rcx, [rdi+210h]
0x18001bab1  mov     r9b, r14b
0x18001bab4  mov     rdx, rbp
0x18001bab7  call    SymCryptCShake256Extract
0x18001babc  jmp     short loc_18001BA7A
0x18001babe  cmp     [rdi+210h], ebx; jumptable 000000018001B6CE case 131095
0x18001bac4  ja      short loc_18001BAD3
0x18001bac6  xor     r8d, r8d
0x18001bac9  xor     edx, edx
0x18001bacb  mov     rcx, rdi
0x18001bace  call    MSCryptHashDataInternal
0x18001bad3  lea     rcx, [rdi+220h]
0x18001bada  mov     r8, r15
0x18001badd  mov     rdx, rbp
0x18001bae0  test    r14b, r14b
0x18001bae3  jz      short loc_18001BAEC
0x18001bae5  call    SymCryptKmac128ResultEx
0x18001baea  jmp     short loc_18001BAF6
0x18001baec  call    SymCryptKmac256Extract
0x18001baf1  mov     ebx, 3
0x18001baf6  mov     [rdi+210h], ebx
0x18001bafc  jmp     loc_18001BB81
0x18001bb01  cmp     [rdi+210h], ebx; jumptable 000000018001B6CE case 131096
0x18001bb07  ja      short loc_18001BB16
0x18001bb09  xor     r8d, r8d
0x18001bb0c  xor     edx, edx
0x18001bb0e  mov     rcx, rdi
0x18001bb11  call    MSCryptHashDataInternal
0x18001bb16  lea     rcx, [rdi+220h]
0x18001bb1d  mov     r8, r15
0x18001bb20  mov     rdx, rbp
0x18001bb23  test    r14b, r14b
0x18001bb26  jz      short loc_18001BB2F
0x18001bb28  call    SymCryptKmac128ResultEx
0x18001bb2d  jmp     short loc_18001BAF6
0x18001bb2f  call    SymCryptKmac256Extract
0x18001bb34  jmp     short loc_18001BAF1
0x18001bb36  mov     r8, r15; jumptable 000000018001B6CE case 131097
0x18001bb39  lea     rcx, [rdi+80h]
0x18001bb40  mov     r9b, r14b
0x18001bb43  call    SymCryptShake256Extract
0x18001bb48  jmp     short loc_18001BB81
0x18001bb4a  mov     r8, r15; jumptable 000000018001B6CE case 131098
0x18001bb4d  lea     rcx, [rdi+80h]
0x18001bb54  mov     r9b, r14b
0x18001bb57  call    SymCryptShake256Extract
0x18001bb5c  jmp     short loc_18001BB81
0x18001bb5e  mov     esi, 0C00000BBh; jumptable 000000018001B6CE default case
0x18001bb63  mov     r9d, 0B46h
0x18001bb69  mov     ecx, 0C00000BBh
0x18001bb6e  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001bb75  lea     rdx, aStatus; "Status"
0x18001bb7c  call    DebugTraceError
0x18001bb81  mov     eax, esi
0x18001bb83  add     rsp, 48h
0x18001bb87  pop     r15
0x18001bb89  pop     r14
0x18001bb8b  pop     rdi
0x18001bb8c  pop     rsi
0x18001bb8d  pop     rbp
0x18001bb8e  pop     rbx
0x18001bb8f  retn
```
