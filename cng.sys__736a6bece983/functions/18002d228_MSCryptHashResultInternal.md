# MSCryptHashResultInternal

- ea: `0x18002d228`
- end: `0x18002d708`
- name: `MSCryptHashResultInternal`
- size: `1248`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0x18002b700`
- `0x18003c470`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x1800151b0`
- `0x180015500`
- `0x18002c770`
- `0x18002d228`
- `0x18002e5a0`
- `0x18002e710`
- `0x180031f0c`
- `0x1800328d0`
- `0x1800329c0`
- `0x180035980`
- `0x18003cf80`
- `0x18003dac0`
- `0x180040f40`
- `0x1800651e0`
- `0x180065230`
- `0x1800882f0`
- `0x180093c8c`
- `0x180093dac`
- `0x180094050`
- `0x180094080`
- `0x180094980`
- `0x180094a08`
- `0x1800950a0`
- `0x1800985ec`
- `0x180098d58`
- `0x180098de0`

## string_xrefs

- `0x18002d32e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18002d6e5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptHashResultInternal(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
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

  v4 = (unsigned int)a3;
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
        goto LABEL_85;
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
      a3 = 32;
      goto LABEL_52;
    case 0x20010:
      if ( *(_DWORD *)(a1 + 12) != 48 )
      {
        v10 = 2673;
        goto LABEL_4;
      }
      a3 = 48;
      goto LABEL_52;
    case 0x20011:
      if ( *(_DWORD *)(a1 + 12) != 64 )
      {
        v10 = 2690;
        goto LABEL_4;
      }
      a3 = 64;
LABEL_52:
      LOBYTE(a4) = 1;
LABEL_53:
      SymCryptKeccakExtract(a1 + 128, a2, a3, a4);
      break;
    case 0x20012:
      if ( *(_DWORD *)(a1 + 12) == 32 )
        goto LABEL_62;
      v10 = 2707;
      goto LABEL_4;
    case 0x20013:
      if ( *(_DWORD *)(a1 + 12) == 48 )
        goto LABEL_62;
      v10 = 2725;
      goto LABEL_4;
    case 0x20014:
      if ( *(_DWORD *)(a1 + 12) == 64 )
      {
LABEL_62:
        SymCryptHmacResult(a1 + 640);
        SymCryptHmacInit(a1 + 640, a1 + 128);
      }
      else
      {
        v10 = 2743;
LABEL_4:
        v7 = -1073741816;
        v11 = 3221225480LL;
LABEL_85:
        DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", v10);
      }
      break;
    case 0x20015:
      if ( *(_DWORD *)(a1 + 280) <= 1u )
        MSCryptHashDataInternal(a1, 0);
      goto LABEL_69;
    case 0x20016:
      if ( *(_DWORD *)(a1 + 280) <= 1u )
        MSCryptHashDataInternal(a1, 0);
LABEL_69:
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
        goto LABEL_76;
      goto LABEL_77;
    case 0x20018:
      if ( *(_DWORD *)(a1 + 528) <= 1u )
        MSCryptHashDataInternal(a1, 0);
      v12 = a1 + 544;
      v13 = v4;
      v14 = a2;
      if ( v9 )
      {
LABEL_76:
        SymCryptKmac128ResultEx(v12, v14, v13);
      }
      else
      {
LABEL_77:
        SymCryptKmac256Extract(v12, a2, v4);
        v8 = 3;
      }
      *(_DWORD *)(a1 + 528) = v8;
      return v7;
    case 0x20019:
    case 0x2001A:
      a3 = (unsigned int)a3;
      LOBYTE(a4) = (a4 & 1) == 0;
      goto LABEL_53;
    default:
      v7 = -1073741637;
      v10 = 2886;
      v11 = 3221225659LL;
      goto LABEL_85;
  }
  return v7;
}

```

## disassembly

```asm
0x18002d228  push    rbx
0x18002d22a  push    rbp
0x18002d22b  push    rsi
0x18002d22c  push    rdi
0x18002d22d  push    r14
0x18002d22f  push    r15
0x18002d231  sub     rsp, 48h
0x18002d235  mov     eax, [rcx+8]
0x18002d238  mov     r14d, r9d
0x18002d23b  add     eax, 0FFFDFFFFh; switch 26 cases
0x18002d240  mov     r15d, r8d
0x18002d243  mov     rbp, rdx
0x18002d246  mov     rdi, rcx
0x18002d249  cmp     eax, 19h
0x18002d24c  ja      def_18002D26E; jumptable 000000018002D26E default case
0x18002d252  xor     esi, esi
0x18002d254  lea     rcx, cs:180000000h
0x18002d25b  mov     eax, ds:(jpt_18002D26E - 180000000h)[rcx+rax*4]
0x18002d262  not     r14b
0x18002d265  lea     ebx, [rsi+1]
0x18002d268  and     r14b, bl
0x18002d26b  add     rax, rcx
0x18002d26e  jmp     rax; switch jump
0x18002d274  cmp     dword ptr [rdi+0Ch], 10h; jumptable 000000018002D26E case 131073
0x18002d278  jz      short loc_18002D28F
0x18002d27a  mov     r9d, 95Fh
0x18002d280  mov     esi, 0C0000008h
0x18002d285  mov     ecx, 0C0000008h
0x18002d28a  jmp     loc_18002D6E5
0x18002d28f  lea     rcx, [rdi+80h]
0x18002d296  call    SymCryptMd5Result
0x18002d29b  jmp     loc_18002D6F8
0x18002d2a0  cmp     dword ptr [rdi+0Ch], 14h; jumptable 000000018002D26E case 131074
0x18002d2a4  jz      short loc_18002D2AE
0x18002d2a6  mov     r9d, 970h
0x18002d2ac  jmp     short loc_18002D280
0x18002d2ae  lea     rcx, [rdi+80h]
0x18002d2b5  call    SymCryptSha1Result
0x18002d2ba  jmp     loc_18002D6F8
0x18002d2bf  cmp     dword ptr [rdi+0Ch], 10h; jumptable 000000018002D26E case 131075
0x18002d2c3  jz      short loc_18002D2CD
0x18002d2c5  mov     r9d, 981h
0x18002d2cb  jmp     short loc_18002D280
0x18002d2cd  lea     rcx, [rdi+80h]
0x18002d2d4  call    SymCryptMd2Result
0x18002d2d9  jmp     loc_18002D6F8
0x18002d2de  cmp     dword ptr [rdi+0Ch], 10h; jumptable 000000018002D26E case 131076
0x18002d2e2  jz      short loc_18002D2EC
0x18002d2e4  mov     r9d, 992h
0x18002d2ea  jmp     short loc_18002D280
0x18002d2ec  lea     rcx, [rdi+80h]
0x18002d2f3  call    SymCryptMd4Result
0x18002d2f8  jmp     loc_18002D6F8
0x18002d2fd  cmp     dword ptr [rdi+0Ch], 20h ; ' '; jumptable 000000018002D26E case 131077
0x18002d301  jz      short loc_18002D35B
0x18002d303  mov     esi, 0C0000008h
0x18002d308  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d30f  lea     rax, WPP_GLOBAL_Control
0x18002d316  cmp     rcx, rax
0x18002d319  jz      loc_18002D6F8
0x18002d31f  mov     eax, [rcx+2Ch]
0x18002d322  test    bl, al
0x18002d324  jz      loc_18002D6F8
0x18002d32a  mov     rcx, [rcx+18h]
0x18002d32e  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002d335  mov     [rsp+78h+var_48], 9A3h
0x18002d33d  lea     r9, aStatus; "Status"
0x18002d344  mov     [rsp+78h+var_50], r8
0x18002d349  mov     [rsp+78h+var_58], 0C0000008h
0x18002d351  call    WPP_SF_sDsd
0x18002d356  jmp     loc_18002D6F8
0x18002d35b  lea     rcx, [rdi+80h]
0x18002d362  call    SymCryptSha256Result
0x18002d367  jmp     loc_18002D6F8
0x18002d36c  cmp     dword ptr [rdi+0Ch], 30h ; '0'; jumptable 000000018002D26E case 131078
0x18002d370  jz      short loc_18002D37D
0x18002d372  mov     r9d, 9B4h
0x18002d378  jmp     loc_18002D280
0x18002d37d  lea     rcx, [rdi+80h]
0x18002d384  call    SymCryptSha384Result
0x18002d389  jmp     loc_18002D6F8
0x18002d38e  cmp     dword ptr [rdi+0Ch], 40h ; '@'; jumptable 000000018002D26E case 131079
0x18002d392  jz      short loc_18002D39F
0x18002d394  mov     r9d, 9C5h
0x18002d39a  jmp     loc_18002D280
0x18002d39f  lea     rcx, [rdi+80h]
0x18002d3a6  call    SymCryptSha512Result
0x18002d3ab  jmp     loc_18002D6F8
0x18002d3b0  cmp     [rdi+74h], esi; jumptable 000000018002D26E case 131080
0x18002d3b3  jnz     short loc_18002D3CA
0x18002d3b5  mov     esi, 0C000042Ah
0x18002d3ba  mov     r9d, 9D6h
0x18002d3c0  mov     ecx, 0C000042Ah
0x18002d3c5  jmp     loc_18002D6E5
0x18002d3ca  cmp     dword ptr [rdi+0Ch], 10h
0x18002d3ce  jz      short loc_18002D3DB
0x18002d3d0  mov     r9d, 9DDh
0x18002d3d6  jmp     loc_18002D280
0x18002d3db  lea     rcx, [rdi+0AB0h]
0x18002d3e2  mov     r8d, 10h
0x18002d3e8  call    SymCryptGcmEncryptFinal
0x18002d3ed  mov     [rdi+74h], esi
0x18002d3f0  jmp     loc_18002D6F8
0x18002d3f5  cmp     dword ptr [rdi+0Ch], 14h; jumptable 000000018002D26E case 131081
0x18002d3f9  jz      short loc_18002D406
0x18002d3fb  mov     r9d, 9F4h
0x18002d401  jmp     loc_18002D280
0x18002d406  lea     rbx, [rdi+0D0h]
0x18002d40d  mov     rcx, rbx
0x18002d410  call    SymCryptHmacSha1Result
0x18002d415  lea     rdx, [rdi+80h]
0x18002d41c  mov     rcx, rbx
0x18002d41f  call    SymCryptHmacSha1Init
0x18002d424  jmp     loc_18002D6F8
0x18002d429  cmp     dword ptr [rdi+0Ch], 10h; jumptable 000000018002D26E case 131082
0x18002d42d  jz      short loc_18002D43A
0x18002d42f  mov     r9d, 0A06h
0x18002d435  jmp     loc_18002D280
0x18002d43a  lea     rbx, [rdi+0B0h]
0x18002d441  mov     rcx, rbx
0x18002d444  call    SymCryptHmacMd5Result
0x18002d449  lea     rdx, [rdi+80h]
0x18002d450  mov     rcx, rbx
0x18002d453  call    SymCryptHmacMd5Init
0x18002d458  jmp     loc_18002D6F8
0x18002d45d  cmp     dword ptr [rdi+0Ch], 20h ; ' '; jumptable 000000018002D26E case 131083
0x18002d461  jz      short loc_18002D46E
0x18002d463  mov     r9d, 0A18h
0x18002d469  jmp     loc_18002D280
0x18002d46e  lea     rbx, [rdi+0D0h]
0x18002d475  mov     rcx, rbx
0x18002d478  call    SymCryptHmacSha256Result
0x18002d47d  lea     rdx, [rdi+80h]
0x18002d484  mov     rcx, rbx
0x18002d487  call    SymCryptHmacSha256Init
0x18002d48c  jmp     loc_18002D6F8
0x18002d491  cmp     dword ptr [rdi+0Ch], 30h ; '0'; jumptable 000000018002D26E case 131084
0x18002d495  jz      short loc_18002D4A2
0x18002d497  mov     r9d, 0A2Ah
0x18002d49d  jmp     loc_18002D280
0x18002d4a2  lea     rbx, [rdi+110h]
0x18002d4a9  mov     rcx, rbx
0x18002d4ac  call    SymCryptHmacSha384Result
0x18002d4b1  lea     rdx, [rdi+80h]
0x18002d4b8  mov     rcx, rbx
0x18002d4bb  call    SymCryptHmacSha512Init
0x18002d4c0  jmp     loc_18002D6F8
0x18002d4c5  cmp     dword ptr [rdi+0Ch], 40h ; '@'; jumptable 000000018002D26E case 131085
0x18002d4c9  jz      short loc_18002D4D6
0x18002d4cb  mov     r9d, 0A3Ch
0x18002d4d1  jmp     loc_18002D280
0x18002d4d6  lea     rbx, [rdi+110h]
0x18002d4dd  mov     rcx, rbx
0x18002d4e0  call    SymCryptHmacSha512Result
0x18002d4e5  lea     rdx, [rdi+80h]
0x18002d4ec  mov     rcx, rbx
0x18002d4ef  call    SymCryptHmacSha512Init
0x18002d4f4  jmp     loc_18002D6F8
0x18002d4f9  cmp     dword ptr [rdi+0Ch], 10h; jumptable 000000018002D26E case 131086
0x18002d4fd  jz      short loc_18002D50A
0x18002d4ff  mov     r9d, 0A4Eh
0x18002d505  jmp     loc_18002D280
0x18002d50a  lea     rbx, [rdi+2A0h]
0x18002d511  mov     rcx, rbx
0x18002d514  call    SymCryptAesCmacResult
0x18002d519  mov     [rbx+20h], rsi
0x18002d51d  lea     rax, [rdi+80h]
0x18002d524  mov     [rbx], rsi
0x18002d527  mov     [rbx+8], rsi
0x18002d52b  mov     [rbx+28h], rax
0x18002d52f  jmp     loc_18002D6F8
0x18002d534  cmp     dword ptr [rdi+0Ch], 20h ; ' '; jumptable 000000018002D26E case 131087
0x18002d538  jz      short loc_18002D545
0x18002d53a  mov     r9d, 0A60h
0x18002d540  jmp     loc_18002D280
0x18002d545  mov     r8d, 20h ; ' '
0x18002d54b  mov     r9b, bl
0x18002d54e  lea     rcx, [rdi+80h]
0x18002d555  call    SymCryptKeccakExtract
0x18002d55a  jmp     loc_18002D6F8
0x18002d55f  cmp     dword ptr [rdi+0Ch], 30h ; '0'; jumptable 000000018002D26E case 131088
0x18002d563  jz      short loc_18002D570
0x18002d565  mov     r9d, 0A71h
0x18002d56b  jmp     loc_18002D280
0x18002d570  mov     r8d, 30h ; '0'
0x18002d576  jmp     short loc_18002D54B
0x18002d578  cmp     dword ptr [rdi+0Ch], 40h ; '@'; jumptable 000000018002D26E case 131089
0x18002d57c  jz      short loc_18002D589
0x18002d57e  mov     r9d, 0A82h
0x18002d584  jmp     loc_18002D280
0x18002d589  mov     r8d, 40h ; '@'
0x18002d58f  jmp     short loc_18002D54B
0x18002d591  cmp     dword ptr [rdi+0Ch], 20h ; ' '; jumptable 000000018002D26E case 131090
0x18002d595  jz      short loc_18002D5A2
0x18002d597  mov     r9d, 0A93h
0x18002d59d  jmp     loc_18002D280
0x18002d5a2  lea     rbx, [rdi+280h]
0x18002d5a9  mov     rcx, rbx
0x18002d5ac  call    SymCryptHmacResult
0x18002d5b1  lea     rdx, [rdi+80h]
0x18002d5b8  mov     rcx, rbx
0x18002d5bb  call    SymCryptHmacInit
0x18002d5c0  jmp     loc_18002D6F8
0x18002d5c5  cmp     dword ptr [rdi+0Ch], 30h ; '0'; jumptable 000000018002D26E case 131091
0x18002d5c9  jz      short loc_18002D5A2
0x18002d5cb  mov     r9d, 0AA5h
0x18002d5d1  jmp     loc_18002D280
0x18002d5d6  cmp     dword ptr [rdi+0Ch], 40h ; '@'; jumptable 000000018002D26E case 131092
0x18002d5da  jz      short loc_18002D5A2
0x18002d5dc  mov     r9d, 0AB7h
0x18002d5e2  jmp     loc_18002D280
0x18002d5e7  cmp     [rdi+118h], ebx; jumptable 000000018002D26E case 131093
0x18002d5ed  ja      short loc_18002D5FC
0x18002d5ef  xor     r8d, r8d
0x18002d5f2  xor     edx, edx
0x18002d5f4  mov     rcx, rdi
0x18002d5f7  call    MSCryptHashDataInternal
0x18002d5fc  mov     r8, r15
0x18002d5ff  lea     rcx, [rdi+210h]
0x18002d606  mov     r9b, r14b
0x18002d609  mov     rdx, rbp
0x18002d60c  call    SymCryptCShake256Extract
0x18002d611  movzx   eax, r14b
0x18002d615  xor     eax, ebx
0x18002d617  lea     eax, ds:1[rax*2]
0x18002d61e  mov     [rdi+118h], eax
0x18002d624  jmp     loc_18002D6F8
0x18002d629  cmp     [rdi+118h], ebx; jumptable 000000018002D26E case 131094
0x18002d62f  ja      short loc_18002D63E
0x18002d631  xor     r8d, r8d
0x18002d634  xor     edx, edx
0x18002d636  mov     rcx, rdi
0x18002d639  call    MSCryptHashDataInternal
0x18002d63e  mov     r8, r15
0x18002d641  lea     rcx, [rdi+210h]
0x18002d648  mov     r9b, r14b
0x18002d64b  mov     rdx, rbp
0x18002d64e  call    SymCryptCShake256Extract
0x18002d653  jmp     short loc_18002D611
0x18002d655  cmp     [rdi+210h], ebx; jumptable 000000018002D26E case 131095
0x18002d65b  ja      short loc_18002D66A
0x18002d65d  xor     r8d, r8d
0x18002d660  xor     edx, edx
0x18002d662  mov     rcx, rdi
0x18002d665  call    MSCryptHashDataInternal
0x18002d66a  lea     rcx, [rdi+220h]
0x18002d671  mov     r8, r15
0x18002d674  mov     rdx, rbp
0x18002d677  test    r14b, r14b
0x18002d67a  jz      short loc_18002D683
0x18002d67c  call    SymCryptKmac128ResultEx
0x18002d681  jmp     short loc_18002D68D
0x18002d683  call    SymCryptKmac256Extract
0x18002d688  mov     ebx, 3
0x18002d68d  mov     [rdi+210h], ebx
0x18002d693  jmp     short loc_18002D6F8
0x18002d695  cmp     [rdi+210h], ebx; jumptable 000000018002D26E case 131096
0x18002d69b  ja      short loc_18002D6AA
0x18002d69d  xor     r8d, r8d
0x18002d6a0  xor     edx, edx
0x18002d6a2  mov     rcx, rdi
0x18002d6a5  call    MSCryptHashDataInternal
0x18002d6aa  lea     rcx, [rdi+220h]
0x18002d6b1  mov     r8, r15
0x18002d6b4  mov     rdx, rbp
0x18002d6b7  test    r14b, r14b
0x18002d6ba  jz      short loc_18002D6C3
0x18002d6bc  call    SymCryptKmac128ResultEx
0x18002d6c1  jmp     short loc_18002D68D
0x18002d6c3  call    SymCryptKmac256Extract
0x18002d6c8  jmp     short loc_18002D688
0x18002d6ca  mov     r8, r15; jumptable 000000018002D26E cases 131097,131098
0x18002d6cd  mov     r9b, r14b
0x18002d6d0  jmp     loc_18002D54E
0x18002d6d5  mov     esi, 0C00000BBh; jumptable 000000018002D26E default case
0x18002d6da  mov     r9d, 0B46h
0x18002d6e0  mov     ecx, 0C00000BBh
0x18002d6e5  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002d6ec  lea     rdx, aStatus; "Status"
0x18002d6f3  call    DebugTraceError
0x18002d6f8  mov     eax, esi
0x18002d6fa  add     rsp, 48h
0x18002d6fe  pop     r15
0x18002d700  pop     r14
0x18002d702  pop     rdi
0x18002d703  pop     rsi
0x18002d704  pop     rbp
0x18002d705  pop     rbx
0x18002d706  retn
```
