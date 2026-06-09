# FveDatum2KeyCreate

- ea: `0x180106158`
- end: `0x180106532`
- name: `FveDatum2KeyCreate`
- size: `986`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800b0774`
- `0x180106870`
- `0x18010bf0c`

## callees

- `0x18005007c`
- `0x180104154`
- `0x180104740`
- `0x180106158`
- `0x180106a44`
- `0x180106db8`
- `0x18010955c`
- `0x180118be4`
- `0x180118c04`
- `0x180118da0`
- `0x180118dcc`
- `0x180118df8`
- `0x18011f010`

## string_xrefs

- `0x180106282`: `FveDatum2KeyCreate: Recognized key use role but this scenario should not require generation of a key.`
- `0x1801061b3`: `FveDatum2KeyCreate`
- `0x18010622d`: `FveDatum2KeyCreate`
- `0x18010625e`: `FveDatum2KeyCreate`
- `0x180106308`: `FveDatum2KeyCreate`
- `0x18010632f`: `FveDatum2KeyCreate`
- `0x180106369`: `FveDatum2KeyCreate`
- `0x1801063fb`: `FveDatum2KeyCreate`
- `0x1801064a1`: `FveDatum2KeyCreate`
- `0x1801064f0`: `FveDatum2KeyCreate`
- `0x180106325`: `Key material passed in to FveDatum2KeyCreate but GenerateKey is TRUE. Ignoring KeyMaterial`

## pseudocode

```c
__int64 __fastcall FveDatum2KeyCreate(char a1, __int64 a2, __int64 a3, int a4, __int64 a5, __int64 a6, _QWORD *a7)
{
  __int64 v7; // rsi
  __int64 v10; // r14
  int v11; // edx
  int v12; // ebx
  int v13; // eax
  int v14; // eax
  char v15; // cl
  int v16; // eax
  int v17; // edx
  __int64 v18; // rcx
  int v19; // eax
  int Complex; // eax
  int v21; // edx
  _QWORD *v22; // rax
  char v24; // [rsp+28h] [rbp-79h]
  char v25; // [rsp+28h] [rbp-79h]
  char v26[4]; // [rsp+30h] [rbp-71h] BYREF
  char v27; // [rsp+34h] [rbp-6Dh]
  __int64 v28; // [rsp+38h] [rbp-69h] BYREF
  __int64 v29; // [rsp+40h] [rbp-61h] BYREF
  size_t Size; // [rsp+48h] [rbp-59h]
  __int64 v31; // [rsp+50h] [rbp-51h] BYREF
  _QWORD *v32; // [rsp+58h] [rbp-49h]
  __int128 v33; // [rsp+60h] [rbp-41h] BYREF
  _BYTE v34[32]; // [rsp+70h] [rbp-31h] BYREF
  __int128 v35; // [rsp+90h] [rbp-11h] BYREF
  char v36; // [rsp+A0h] [rbp-1h]

  v7 = 0;
  v27 = a1;
  LODWORD(Size) = a4;
  v32 = a7;
  v31 = 0;
  memset(v34, 0, 28);
  v10 = 0;
  v29 = 0;
  v36 = 0;
  v28 = 0;
  *(_WORD *)v26 = 0;
  v35 = 0;
  v33 = 0;
  FveLibTraceEntryHelper("minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2key.c", 87, "FveDatum2KeyCreate");
  if ( a7 && a2 )
  {
    *a7 = 0;
    WORD2(v35) = *(_WORD *)a2;
    *(_QWORD *)((char *)&v35 + 6) = *(_QWORD *)(a2 + 2);
    LODWORD(v35) = 1;
    switch ( a6 )
    {
      case 6LL:
        LODWORD(v7) = 32;
        break;
      case 12LL:
      case 13LL:
        FveLibDbgTraceHelper("FveDatum2KeyCreate: Recognized key use role but this scenario should not require generation of a key.");
        break;
      case 21LL:
        LODWORD(v7) = 16;
        break;
      default:
        FveLibTraceHelper(
          (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2key.c",
          123,
          (int)"FveDatum2KeyCreate",
          1,
          "KeyRole unrecognized",
          v24);
        v11 = 124;
        v12 = -1073741822;
LABEL_8:
        FveLibTraceHelper(
          (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2key.c",
          v11,
          (int)"FveDatum2KeyCreate",
          1,
          "Error: 0x%x",
          v12);
        goto LABEL_37;
    }
    v13 = FveDatum2CryptoHeaderCreate((unsigned __int16 *)&v35, (__int64)v34, 0, 0, &v29);
    v12 = v13;
    if ( v13 < 0 )
    {
      FveLibTraceHelper(
        (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2key.c",
        137,
        (int)"FveDatum2KeyCreate",
        1,
        "Error: 0x%x",
        v13);
      goto LABEL_37;
    }
    *(_QWORD *)&v33 = v29;
    v14 = RtlUShortAdd(0, 1, v26);
    v12 = v14;
    if ( v14 < 0 )
    {
      FveLibTraceHelper(
        (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2key.c",
        144,
        (int)"FveDatum2KeyCreate",
        1,
        "Error: 0x%x",
        v14);
      goto LABEL_37;
    }
    if ( v27 == v15 )
    {
      v16 = FveDatum2AllPurposeArrayCreate(a3, (unsigned int)Size, 5, (__int64)&v28);
      v12 = v16;
      if ( v16 < 0 )
      {
        v17 = 177;
        goto LABEL_22;
      }
    }
    else
    {
      FveLibTraceHelper(
        (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2key.c",
        153,
        (int)"FveDatum2KeyCreate",
        0,
        "Generating key %llu in key datum creation",
        a6);
      if ( a3 )
        FveLibTraceHelper(
          (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2key.c",
          158,
          (int)"FveDatum2KeyCreate",
          0,
          "Key material passed in to FveDatum2KeyCreate but GenerateKey is TRUE. Ignoring KeyMaterial",
          v25);
      v16 = FveGenerateNewDatum2Key(a2, (unsigned int)v7, &v28);
      v12 = v16;
      if ( v16 < 0 )
      {
        v17 = 167;
LABEL_22:
        FveLibTraceHelper(
          (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2key.c",
          v17,
          (int)"FveDatum2KeyCreate",
          1,
          "Error: 0x%x",
          v16);
        v10 = v28;
        goto LABEL_37;
      }
    }
    v18 = *(unsigned __int16 *)v26;
    v10 = v28;
    *(_QWORD *)&v34[8 * *(unsigned __int16 *)v26 - 16] = v28;
    v19 = RtlUShortAdd(v18, 1, v26);
    v12 = v19;
    if ( v19 < 0 )
    {
      FveLibTraceHelper(
        (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2key.c",
        189,
        (int)"FveDatum2KeyCreate",
        1,
        "Error: 0x%x",
        v19);
      goto LABEL_37;
    }
    if ( *(_WORD *)v26 > 2u )
    {
      FveLibTraceHelper(
        (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2key.c",
        199,
        (int)"FveDatum2KeyCreate",
        1,
        "NestedDatumsCount %lu exceeds array size",
        v26[0]);
      v11 = 200;
      v12 = -1073741823;
      goto LABEL_8;
    }
    Complex = FveDatum2CreateComplex(5, a6, 0, (unsigned int)&v33, *(unsigned __int16 *)v26, (__int64)&v31);
    v7 = v31;
    v12 = Complex;
    if ( Complex >= 0 )
    {
      v12 = FveLibGenGuid(v31 + 64);
      if ( v12 >= 0 )
      {
        *(_QWORD *)(v7 + 24) |= 2uLL;
        v22 = v32;
        *(_QWORD *)(v7 + 80) = 0;
        *v22 = v7;
        goto LABEL_37;
      }
      v21 = 219;
    }
    else
    {
      v21 = 210;
    }
  }
  else
  {
    v21 = 90;
    v12 = -1073741811;
  }
  FveLibTraceHelper(
    (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2key.c",
    v21,
    (int)"FveDatum2KeyCreate",
    1,
    "Error: 0x%x",
    v12);
  if ( v7 )
    FveDatum2Free(v7);
LABEL_37:
  if ( v29 )
  {
    FveDatum2Free(v29);
    v29 = 0;
  }
  if ( v10 )
    FveDatum2Free(v10);
  FveLibTraceExitHelper("minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2key.c", 249, "FveDatum2KeyCreate");
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180106158  mov     [rsp-8+arg_0], rbx
0x18010615d  push    rbp
0x18010615e  push    rsi
0x18010615f  push    rdi
0x180106160  push    r12
0x180106162  push    r13
0x180106164  push    r14
0x180106166  push    r15
0x180106168  lea     rbp, [rsp-0Fh]
0x18010616d  sub     rsp, 0B0h
0x180106174  mov     rax, cs:__security_cookie
0x18010617b  xor     rax, rsp
0x18010617e  mov     [rbp+3Fh+var_38], rax
0x180106182  mov     rbx, [rbp+3Fh+arg_30]
0x180106186  xorps   xmm0, xmm0
0x180106189  xor     esi, esi
0x18010618b  mov     [rbp+3Fh+var_AC], cl
0x18010618e  xor     eax, eax
0x180106190  mov     dword ptr [rbp+3Fh+Size], r9d
0x180106194  mov     r13, r8
0x180106197  mov     [rbp+3Fh+var_88], rbx
0x18010619b  mov     r15, rdx
0x18010619e  mov     [rbp+3Fh+var_90], rsi
0x1801061a2  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x1801061a6  xor     r14d, r14d
0x1801061a9  mov     [rbp+3Fh+var_A0], rsi
0x1801061ad  lea     edx, [rsi+57h]
0x1801061b0  mov     [rbp+3Fh+var_40], al
0x1801061b3  lea     r8, aFvedatum2keycr; "FveDatum2KeyCreate"
0x1801061ba  mov     [rbp+3Fh+var_A8], r14
0x1801061be  lea     rcx, aMinkernelNgscb_10; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x1801061c5  mov     word ptr [rbp+3Fh+var_B0], ax
0x1801061c9  movups  [rbp+3Fh+var_50], xmm0
0x1801061cd  movups  [rbp+3Fh+var_80], xmm0
0x1801061d1  movups  xmmword ptr [rbp+3Fh+var_70+0Ch], xmm0
0x1801061d5  call    FveLibTraceEntryHelper
0x1801061da  test    rbx, rbx
0x1801061dd  jz      loc_18010648D
0x1801061e3  test    r15, r15
0x1801061e6  jz      loc_18010648D
0x1801061ec  mov     r12, [rbp+3Fh+arg_28]
0x1801061f0  lea     edi, [rsi+1]
0x1801061f3  mov     [rbx], rsi
0x1801061f6  movzx   eax, word ptr [r15]
0x1801061fa  mov     word ptr [rbp+3Fh+var_50+4], ax
0x1801061fe  mov     rax, [r15+2]
0x180106202  mov     qword ptr [rbp+3Fh+var_50+6], rax
0x180106206  mov     rax, r12
0x180106209  mov     dword ptr [rbp+3Fh+var_50], edi
0x18010620c  sub     rax, 6
0x180106210  jz      short loc_180106290
0x180106212  sub     rax, 6
0x180106216  jz      short loc_180106282
0x180106218  sub     rax, rdi
0x18010621b  jz      short loc_180106282
0x18010621d  cmp     rax, 8
0x180106221  jz      short loc_18010627B
0x180106223  lea     rax, aKeyroleUnrecog; "KeyRole unrecognized"
0x18010622a  mov     r9d, edi; int
0x18010622d  lea     r8, aFvedatum2keycr; "FveDatum2KeyCreate"
0x180106234  mov     [rsp+0E0h+Format], rax; Format
0x180106239  lea     edx, [rsi+7Bh]; int
0x18010623c  lea     rcx, aMinkernelNgscb_10; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x180106243  call    FveLibTraceHelper
0x180106248  lea     edx, [rsi+7Ch]; int
0x18010624b  mov     ebx, 0C0000002h
0x180106250  mov     dword ptr [rsp+0E0h+var_B8], ebx; char
0x180106254  lea     rax, aError0xX; "Error: 0x%x"
0x18010625b  mov     r9d, edi; int
0x18010625e  lea     r8, aFvedatum2keycr; "FveDatum2KeyCreate"
0x180106265  mov     [rsp+0E0h+Format], rax; Format
0x18010626a  lea     rcx, aMinkernelNgscb_10; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x180106271  call    FveLibTraceHelper
0x180106276  jmp     loc_1801064CD
0x18010627b  mov     esi, 10h
0x180106280  jmp     short loc_180106295
0x180106282  lea     rcx, aFvedatum2keycr_0; "FveDatum2KeyCreate: Recognized key use "...
0x180106289  call    FveLibDbgTraceHelper
0x18010628e  jmp     short loc_180106295
0x180106290  mov     esi, 20h ; ' '
0x180106295  lea     rax, [rbp+3Fh+var_A0]
0x180106299  xor     r9d, r9d
0x18010629c  xor     r8d, r8d
0x18010629f  mov     [rsp+0E0h+Format], rax
0x1801062a4  lea     rdx, [rbp+3Fh+var_70]
0x1801062a8  lea     rcx, [rbp+3Fh+var_50]
0x1801062ac  call    FveDatum2CryptoHeaderCreate
0x1801062b1  mov     ebx, eax
0x1801062b3  test    eax, eax
0x1801062b5  jns     short loc_1801062C2
0x1801062b7  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1801062bb  mov     edx, 89h
0x1801062c0  jmp     short loc_180106254
0x1801062c2  mov     rax, [rbp+3Fh+var_A0]
0x1801062c6  lea     r8, [rbp+3Fh+var_B0]
0x1801062ca  mov     edx, edi
0x1801062cc  mov     qword ptr [rbp+3Fh+var_80], rax
0x1801062d0  xor     ecx, ecx
0x1801062d2  call    RtlUShortAdd
0x1801062d7  mov     ebx, eax
0x1801062d9  test    eax, eax
0x1801062db  jns     short loc_1801062EB
0x1801062dd  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1801062e1  mov     edx, 90h
0x1801062e6  jmp     loc_180106254
0x1801062eb  cmp     [rbp+3Fh+var_AC], cl
0x1801062ee  jz      loc_180106394
0x1801062f4  lea     rax, aGeneratingKeyL; "Generating key %llu in key datum creati"...
0x1801062fb  mov     qword ptr [rsp+0E0h+var_B8], r12; char
0x180106300  xor     r9d, r9d; int
0x180106303  mov     [rsp+0E0h+Format], rax; Format
0x180106308  lea     r8, aFvedatum2keycr; "FveDatum2KeyCreate"
0x18010630f  mov     edx, 99h; int
0x180106314  lea     rcx, aMinkernelNgscb_10; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x18010631b  call    FveLibTraceHelper
0x180106320  test    r13, r13
0x180106323  jz      short loc_18010634C
0x180106325  lea     rax, aKeyMaterialPas; "Key material passed in to FveDatum2KeyC"...
0x18010632c  xor     r9d, r9d; int
0x18010632f  lea     r8, aFvedatum2keycr; "FveDatum2KeyCreate"
0x180106336  mov     [rsp+0E0h+Format], rax; Format
0x18010633b  mov     edx, 9Eh; int
0x180106340  lea     rcx, aMinkernelNgscb_10; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x180106347  call    FveLibTraceHelper
0x18010634c  lea     r8, [rbp+3Fh+var_A8]
0x180106350  mov     edx, esi
0x180106352  mov     rcx, r15
0x180106355  call    FveGenerateNewDatum2Key
0x18010635a  mov     ebx, eax
0x18010635c  test    eax, eax
0x18010635e  jns     short loc_1801063BB
0x180106360  mov     edx, 0A7h; int
0x180106365  mov     dword ptr [rsp+0E0h+var_B8], eax; char
0x180106369  lea     r8, aFvedatum2keycr; "FveDatum2KeyCreate"
0x180106370  lea     rax, aError0xX; "Error: 0x%x"
0x180106377  mov     r9d, edi; int
0x18010637a  lea     rcx, aMinkernelNgscb_10; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x180106381  mov     [rsp+0E0h+Format], rax; Format
0x180106386  call    FveLibTraceHelper
0x18010638b  mov     r14, [rbp+3Fh+var_A8]
0x18010638f  jmp     loc_1801064CD
0x180106394  mov     edx, dword ptr [rbp+3Fh+Size]; Size
0x180106397  lea     rax, [rbp+3Fh+var_A8]
0x18010639b  mov     r8d, 5; int
0x1801063a1  mov     [rsp+0E0h+Format], rax; __int64
0x1801063a6  mov     rcx, r13; int
0x1801063a9  call    FveDatum2AllPurposeArrayCreate
0x1801063ae  mov     ebx, eax
0x1801063b0  test    eax, eax
0x1801063b2  jns     short loc_1801063BB
0x1801063b4  mov     edx, 0B1h
0x1801063b9  jmp     short loc_180106365
0x1801063bb  movzx   ecx, word ptr [rbp+3Fh+var_B0]
0x1801063bf  lea     r8, [rbp+3Fh+var_B0]
0x1801063c3  mov     r14, [rbp+3Fh+var_A8]
0x1801063c7  mov     edx, edi
0x1801063c9  mov     qword ptr [rbp+rcx*8+3Fh+var_80], r14
0x1801063ce  call    RtlUShortAdd
0x1801063d3  mov     ebx, eax
0x1801063d5  test    eax, eax
0x1801063d7  jns     short loc_1801063E7
0x1801063d9  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1801063dd  mov     edx, 0BDh
0x1801063e2  jmp     loc_180106254
0x1801063e7  movzx   eax, word ptr [rbp+3Fh+var_B0]
0x1801063eb  mov     r15d, 2
0x1801063f1  cmp     ax, r15w
0x1801063f5  jbe     short loc_180106431
0x1801063f7  mov     dword ptr [rsp+0E0h+var_B8], eax; char
0x1801063fb  lea     r8, aFvedatum2keycr; "FveDatum2KeyCreate"
0x180106402  lea     rax, aNesteddatumsco; "NestedDatumsCount %lu exceeds array siz"...
0x180106409  mov     r9d, edi; int
0x18010640c  mov     edx, 0C7h; int
0x180106411  mov     [rsp+0E0h+Format], rax; Format
0x180106416  lea     rcx, aMinkernelNgscb_10; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x18010641d  call    FveLibTraceHelper
0x180106422  mov     edx, 0C8h
0x180106427  mov     ebx, 0C0000001h
0x18010642c  jmp     loc_180106250
0x180106431  xor     r8d, r8d
0x180106434  lea     rdx, [rbp+3Fh+var_90]
0x180106438  mov     qword ptr [rsp+0E0h+var_B8], rdx
0x18010643d  lea     r9, [rbp+3Fh+var_80]
0x180106441  mov     rdx, r12
0x180106444  mov     dword ptr [rsp+0E0h+Format], eax
0x180106448  lea     ecx, [r8+5]
0x18010644c  call    FveDatum2CreateComplex
0x180106451  mov     rsi, [rbp+3Fh+var_90]
0x180106455  mov     ebx, eax
0x180106457  test    eax, eax
0x180106459  jns     short loc_180106462
0x18010645b  mov     edx, 0D2h
0x180106460  jmp     short loc_18010649A
0x180106462  lea     rcx, [rsi+40h]
0x180106466  call    FveLibGenGuid
0x18010646b  mov     ebx, eax
0x18010646d  test    eax, eax
0x18010646f  jns     short loc_180106478
0x180106471  mov     edx, 0DBh
0x180106476  jmp     short loc_18010649A
0x180106478  or      [rsi+18h], r15
0x18010647c  mov     rax, [rbp+3Fh+var_88]
0x180106480  mov     qword ptr [rsi+50h], 0
0x180106488  mov     [rax], rsi
0x18010648b  jmp     short loc_1801064CD
0x18010648d  mov     edx, 5Ah ; 'Z'; int
0x180106492  mov     ebx, 0C000000Dh
0x180106497  lea     edi, [rdx-59h]
0x18010649a  lea     rcx, aMinkernelNgscb_10; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x1801064a1  lea     r8, aFvedatum2keycr; "FveDatum2KeyCreate"
0x1801064a8  lea     rax, aError0xX; "Error: 0x%x"
0x1801064af  mov     dword ptr [rsp+0E0h+var_B8], ebx; char
0x1801064b3  mov     r9d, edi; int
0x1801064b6  mov     [rsp+0E0h+Format], rax; Format
0x1801064bb  call    FveLibTraceHelper
0x1801064c0  test    rsi, rsi
0x1801064c3  jz      short loc_1801064CD
0x1801064c5  mov     rcx, rsi
0x1801064c8  call    FveDatum2Free
0x1801064cd  mov     rcx, [rbp+3Fh+var_A0]
0x1801064d1  test    rcx, rcx
0x1801064d4  jz      short loc_1801064E3
0x1801064d6  call    FveDatum2Free
0x1801064db  mov     [rbp+3Fh+var_A0], 0
0x1801064e3  test    r14, r14
0x1801064e6  jz      short loc_1801064F0
0x1801064e8  mov     rcx, r14
0x1801064eb  call    FveDatum2Free
0x1801064f0  lea     r8, aFvedatum2keycr; "FveDatum2KeyCreate"
0x1801064f7  mov     edx, 0F9h
0x1801064fc  lea     rcx, aMinkernelNgscb_10; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x180106503  call    FveLibTraceExitHelper
0x180106508  mov     eax, ebx
0x18010650a  mov     rcx, [rbp+3Fh+var_38]
0x18010650e  xor     rcx, rsp; StackCookie
0x180106511  call    __security_check_cookie
0x180106516  mov     rbx, [rsp+0E0h+arg_0]
0x18010651e  add     rsp, 0B0h
0x180106525  pop     r15
0x180106527  pop     r14
0x180106529  pop     r13
0x18010652b  pop     r12
0x18010652d  pop     rdi
0x18010652e  pop     rsi
0x18010652f  pop     rbp
0x180106530  retn
```
