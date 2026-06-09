# FveDatum2CryptoHeaderCreate

- ea: `0x18010955c`
- end: `0x180109c55`
- name: `FveDatum2CryptoHeaderCreate`
- size: `1785`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180106158`
- `0x18010a7dc`
- `0x18010c378`

## callees

- `0x18002fd50`
- `0x180030060`
- `0x18004f9dc`
- `0x180104154`
- `0x180104740`
- `0x18010955c`
- `0x18010a50c`
- `0x18010b14c`
- `0x18010bbfc`
- `0x18010d2dc`
- `0x180118be4`
- `0x180118da0`
- `0x180118dcc`
- `0x180118df8`

## string_xrefs

- `0x180109588`: `FveDatum2CryptoHeaderCreate`
- `0x1801095fb`: `FveDatum2CryptoHeaderCreate`
- `0x180109622`: `FveDatum2CryptoHeaderCreate`
- `0x18010965e`: `FveDatum2CryptoHeaderCreate`
- `0x1801096e6`: `FveDatum2CryptoHeaderCreate`
- `0x180109728`: `FveDatum2CryptoHeaderCreate`
- `0x1801097a5`: `FveDatum2CryptoHeaderCreate`
- `0x1801097f2`: `FveDatum2CryptoHeaderCreate`
- `0x180109876`: `FveDatum2CryptoHeaderCreate`
- `0x1801098b8`: `FveDatum2CryptoHeaderCreate`
- `0x18010991f`: `FveDatum2CryptoHeaderCreate`
- `0x18010997f`: `FveDatum2CryptoHeaderCreate`
- `0x180109a50`: `FveDatum2CryptoHeaderCreate`
- `0x180109aa5`: `FveDatum2CryptoHeaderCreate`
- `0x180109ad5`: `FveDatum2CryptoHeaderCreate`
- `0x180109b4f`: `FveDatum2CryptoHeaderCreate`
- `0x180109bab`: `FveDatum2CryptoHeaderCreate`
- `0x180109c26`: `FveDatum2CryptoHeaderCreate`
- `0x18010967c`: `FveDatum2CryptoHeaderCreate: Creating type %u\n`

## pseudocode

```c
__int64 __fastcall FveDatum2CryptoHeaderCreate(
        unsigned __int16 *a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        _QWORD *a5)
{
  __int64 v9; // r14
  __int64 v10; // r13
  int v11; // edx
  int v12; // eax
  int Complex; // edi
  unsigned int v14; // r14d
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // edx
  int v19; // eax
  __int64 v20; // r15
  unsigned int v21; // r8d
  int v22; // eax
  __int64 v23; // xmm1_8
  int v24; // eax
  __int64 v25; // rsi
  unsigned __int16 v26; // ax
  int v27; // eax
  int v28; // edx
  __int64 v29; // r9
  unsigned __int16 v30; // ax
  int v31; // eax
  int v32; // edx
  char v34; // [rsp+28h] [rbp-69h]
  __int64 v35; // [rsp+30h] [rbp-61h] BYREF
  __int64 v36; // [rsp+38h] [rbp-59h] BYREF
  _QWORD *v37; // [rsp+40h] [rbp-51h]
  size_t Size; // [rsp+48h] [rbp-49h] BYREF
  __int64 v39; // [rsp+50h] [rbp-41h] BYREF
  unsigned __int16 v40; // [rsp+58h] [rbp-39h]
  __int64 v41; // [rsp+60h] [rbp-31h] BYREF
  int v42; // [rsp+68h] [rbp-29h]
  char v43; // [rsp+6Ch] [rbp-25h]
  __int64 v44; // [rsp+70h] [rbp-21h] BYREF
  __int64 v45; // [rsp+78h] [rbp-19h] BYREF
  __int128 v46; // [rsp+80h] [rbp-11h] BYREF
  __int64 v47; // [rsp+90h] [rbp-1h]

  v44 = 0;
  v39 = 0;
  v45 = 0;
  v36 = 0;
  v35 = 0;
  v37 = 0;
  v9 = 0;
  LODWORD(Size) = 0;
  v10 = 0;
  FveLibTraceEntryHelper(
    "minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2cryptoheader.c",
    89,
    "FveDatum2CryptoHeaderCreate");
  if ( !a5 || !a1 || !a2 )
  {
    v25 = v36;
    v32 = 92;
    v20 = v35;
    Complex = -1073741811;
    goto LABEL_61;
  }
  *a5 = 0;
  if ( a3 )
  {
    if ( !a4 )
    {
      FveLibTraceHelper(
        (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2cryptoheader.c",
        98,
        (int)"FveDatum2CryptoHeaderCreate",
        1,
        "Nested crypto header datums passed in but count is 0",
        v34);
      v11 = 99;
LABEL_7:
      v12 = -1073741811;
LABEL_8:
      Complex = v12;
LABEL_9:
      FveLibTraceHelper(
        (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2cryptoheader.c",
        v11,
        (int)"FveDatum2CryptoHeaderCreate",
        1,
        "Error: 0x%x",
        v12);
      goto LABEL_73;
    }
  }
  else if ( a4 )
  {
    FveLibTraceHelper(
      (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2cryptoheader.c",
      103,
      (int)"FveDatum2CryptoHeaderCreate",
      1,
      "Nested crypto header datums count passed in but array is NULL",
      v34);
    v11 = 104;
    goto LABEL_7;
  }
  FveLibDbgTraceHelper("FveDatum2CryptoHeaderCreate: Creating type %u\n", *a1);
  v14 = a4 + 1;
  if ( a4 + 1 < a4 )
  {
    v12 = -1073741675;
    v11 = 114;
    goto LABEL_8;
  }
  v12 = RtlULongLongToULong(8LL * v14, &Size);
  Complex = v12;
  if ( v12 < 0 )
  {
    v11 = 121;
    goto LABEL_9;
  }
  v15 = FveLibAllocWithTagZero((unsigned int)Size);
  Complex = v15;
  if ( v15 >= 0 )
  {
    switch ( *(_DWORD *)a1 )
    {
      case 1:
        v30 = a1[6];
        v41 = *(_QWORD *)(a1 + 2);
        LOWORD(v42) = v30;
        if ( a3 || a4 )
        {
          FveLibTraceHelper(
            (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2cryptoheader.c",
            141,
            (int)"FveDatum2CryptoHeaderCreate",
            1,
            "Key creation scenario does not support nested crypto header datums",
            v34);
          LOBYTE(v15) = 13;
          Complex = -1073741811;
          v18 = 142;
          goto LABEL_17;
        }
        v31 = FveDatum2CryptoKeyCreationCreate(&v41, v16, &v39);
        Complex = v31;
        if ( v31 < 0 )
        {
          FveLibTraceHelper(
            (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2cryptoheader.c",
            153,
            (int)"FveDatum2CryptoHeaderCreate",
            1,
            "Error: 0x%x",
            v31);
          v10 = v39;
          v25 = v36;
          v20 = v35;
          goto LABEL_63;
        }
        v10 = v39;
        v21 = 1;
        *v37 = v39;
        break;
      case 2:
        v26 = a1[6];
        v39 = *(_QWORD *)(a1 + 2);
        v40 = v26;
        v27 = FveDatum2CryptoKeyWrapCreate(&v39, v16, &v45);
        Complex = v27;
        if ( v27 < 0 )
        {
          v28 = 180;
LABEL_40:
          FveLibTraceHelper(
            (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2cryptoheader.c",
            v28,
            (int)"FveDatum2CryptoHeaderCreate",
            1,
            "Error: 0x%x",
            v27);
          v25 = v36;
          v20 = v35;
LABEL_65:
          if ( v45 )
            FveDatum2Free(v45);
          goto LABEL_67;
        }
        v29 = 0;
        v21 = 1;
        *v37 = v45;
        if ( a4 )
        {
          while ( 1 )
          {
            v37[v21] = *(_QWORD *)(a3 + 8 * v29);
            if ( v21 + 1 < v21 )
              break;
            v29 = (unsigned int)(v29 + 1);
            ++v21;
            if ( (unsigned int)v29 >= a4 )
              goto LABEL_51;
          }
          LOBYTE(v27) = -107;
          Complex = -1073741675;
          v28 = 202;
          goto LABEL_40;
        }
        break;
      case 3:
        v22 = *((_DWORD *)a1 + 3);
        v23 = *(_QWORD *)(a2 + 20);
        v41 = *(_QWORD *)(a1 + 2);
        v42 = v22;
        v43 = *((_BYTE *)a1 + 16);
        v47 = v23;
        v46 = *(_OWORD *)(a2 + 4);
        if ( a3 || a4 )
        {
          FveLibTraceHelper(
            (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2cryptoheader.c",
            219,
            (int)"FveDatum2CryptoHeaderCreate",
            1,
            "KDF scenario does not support nested crypto header datums",
            v34);
          LOBYTE(v15) = 13;
          Complex = -1073741811;
          v18 = 220;
          goto LABEL_17;
        }
        if ( *(_DWORD *)a2 != 2 )
        {
          FveLibTraceHelper(
            (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2cryptoheader.c",
            228,
            (int)"FveDatum2CryptoHeaderCreate",
            1,
            "Crypto params type incorrect",
            v34);
          LOBYTE(v15) = 13;
          Complex = -1073741811;
          v18 = 229;
          goto LABEL_17;
        }
        v24 = FveDatum2CryptoKeyKdfCreate(&v41, &v46, v17, &v36);
        Complex = v24;
        if ( v24 < 0 )
        {
          FveLibTraceHelper(
            (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2cryptoheader.c",
            241,
            (int)"FveDatum2CryptoHeaderCreate",
            1,
            "Error: 0x%x",
            v24);
          v25 = v36;
          v20 = v35;
LABEL_67:
          if ( v25 )
            FveDatum2Free(v25);
          goto LABEL_69;
        }
        v25 = v36;
        v21 = 1;
        v20 = v35;
        *v37 = v36;
        goto LABEL_53;
      case 4:
        LODWORD(v39) = *((_DWORD *)a1 + 1);
        if ( a3 || a4 )
        {
          FveLibTraceHelper(
            (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2cryptoheader.c",
            263,
            (int)"FveDatum2CryptoHeaderCreate",
            1,
            "Integrity hash scenario does not support nested crypto header datums",
            v34);
          LOBYTE(v15) = 13;
          Complex = -1073741811;
          v18 = 264;
          goto LABEL_17;
        }
        v19 = FveDatum2CryptoIntegrityHashCreate(&v39, v16, &v35);
        Complex = v19;
        if ( v19 < 0 )
        {
          FveLibTraceHelper(
            (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2cryptoheader.c",
            275,
            (int)"FveDatum2CryptoHeaderCreate",
            1,
            "Error: 0x%x",
            v19);
          v20 = v35;
LABEL_69:
          if ( v20 )
            FveDatum2Free(v20);
          goto LABEL_71;
        }
        v20 = v35;
        v21 = 1;
        *v37 = v35;
LABEL_52:
        v25 = v36;
LABEL_53:
        if ( v21 > v14 )
        {
          FveLibTraceHelper(
            (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2cryptoheader.c",
            296,
            (int)"FveDatum2CryptoHeaderCreate",
            1,
            "NestedDatumsCount %lu exceeds alloc count",
            v21);
          Complex = -1073741823;
          FveLibTraceHelper(
            (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2cryptoheader.c",
            297,
            (int)"FveDatum2CryptoHeaderCreate",
            1,
            "Error: 0x%x",
            1);
          goto LABEL_63;
        }
        Complex = FveDatum2CreateComplex(3, 3, 0, (_DWORD)v37, v21, (__int64)&v44);
        if ( Complex >= 0 )
        {
          *a5 = v44;
LABEL_63:
          if ( v10 )
            FveDatum2Free(v10);
          goto LABEL_65;
        }
        v9 = v44;
        v32 = 307;
LABEL_61:
        FveLibTraceHelper(
          (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2cryptoheader.c",
          v32,
          (int)"FveDatum2CryptoHeaderCreate",
          1,
          "Error: 0x%x",
          Complex);
        if ( v9 )
          FveDatum2Free(v9);
        goto LABEL_63;
      default:
        FveLibTraceHelper(
          (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2cryptoheader.c",
          289,
          (int)"FveDatum2CryptoHeaderCreate",
          1,
          "CryptoInfo.Type %u not supported",
          *a1);
        Complex = -1073741822;
        FveLibTraceHelper(
          (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2cryptoheader.c",
          290,
          (int)"FveDatum2CryptoHeaderCreate",
          1,
          "Error: 0x%x",
          2);
        goto LABEL_71;
    }
LABEL_51:
    v20 = v35;
    goto LABEL_52;
  }
  v18 = 127;
LABEL_17:
  FveLibTraceHelper(
    (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2cryptoheader.c",
    v18,
    (int)"FveDatum2CryptoHeaderCreate",
    1,
    "Error: 0x%x",
    v15);
LABEL_71:
  if ( v37 )
    FveLibFreeWithTag(v37, (unsigned int)Size, 3);
LABEL_73:
  FveLibTraceExitHelper(
    "minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2cryptoheader.c",
    345,
    "FveDatum2CryptoHeaderCreate");
  return (unsigned int)Complex;
}

```

## disassembly

```asm
0x18010955c  push    rbp
0x18010955e  push    rbx
0x18010955f  push    rsi
0x180109560  push    rdi
0x180109561  push    r12
0x180109563  push    r13
0x180109565  push    r14
0x180109567  push    r15
0x180109569  lea     rbp, [rsp-17h]
0x18010956e  sub     rsp, 0A8h
0x180109575  xor     edi, edi
0x180109577  mov     r12, r8
0x18010957a  mov     r15, rdx
0x18010957d  mov     [rbp+4Fh+var_70], rdi
0x180109581  mov     rbx, rcx
0x180109584  mov     [rbp+4Fh+var_90], rdi
0x180109588  lea     r8, aFvedatum2crypt_1; "FveDatum2CryptoHeaderCreate"
0x18010958f  mov     [rbp+4Fh+var_68], rdi
0x180109593  lea     edx, [rdi+59h]
0x180109596  mov     [rbp+4Fh+var_A8], rdi
0x18010959a  lea     rcx, aMinkernelNgscb_18; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x1801095a1  mov     [rbp+4Fh+var_B0], rdi
0x1801095a5  mov     esi, r9d
0x1801095a8  mov     [rbp+4Fh+var_A0], rdi
0x1801095ac  mov     r14d, edi
0x1801095af  mov     dword ptr [rbp+4Fh+Size], edi
0x1801095b2  mov     r13d, edi
0x1801095b5  call    FveLibTraceEntryHelper
0x1801095ba  mov     rax, [rbp+4Fh+arg_20]
0x1801095be  test    rax, rax
0x1801095c1  jz      loc_180109B8F
0x1801095c7  test    rbx, rbx
0x1801095ca  jz      loc_180109B8F
0x1801095d0  test    r15, r15
0x1801095d3  jz      loc_180109B8F
0x1801095d9  mov     [rax], rdi
0x1801095dc  test    r12, r12
0x1801095df  jz      short loc_180109646
0x1801095e1  test    esi, esi
0x1801095e3  jnz     loc_180109679
0x1801095e9  lea     rax, aNestedCryptoHe; "Nested crypto header datums passed in b"...
0x1801095f0  lea     ebx, [rdi+1]
0x1801095f3  mov     [rsp+0E0h+Format], rax; Format
0x1801095f8  mov     r9d, ebx; int
0x1801095fb  lea     r8, aFvedatum2crypt_1; "FveDatum2CryptoHeaderCreate"
0x180109602  lea     edx, [rdi+62h]; int
0x180109605  lea     rcx, aMinkernelNgscb_18; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x18010960c  call    FveLibTraceHelper
0x180109611  lea     edx, [rdi+63h]; int
0x180109614  mov     eax, 0C000000Dh
0x180109619  mov     r9d, ebx; int
0x18010961c  mov     edi, eax
0x18010961e  mov     dword ptr [rsp+0E0h+var_B8], eax; char
0x180109622  lea     r8, aFvedatum2crypt_1; "FveDatum2CryptoHeaderCreate"
0x180109629  lea     rax, aError0xX; "Error: 0x%x"
0x180109630  lea     rcx, aMinkernelNgscb_18; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x180109637  mov     [rsp+0E0h+Format], rax; Format
0x18010963c  call    FveLibTraceHelper
0x180109641  jmp     loc_180109C26
0x180109646  test    esi, esi
0x180109648  jz      short loc_180109679
0x18010964a  mov     ebx, 1
0x18010964f  lea     rax, aNestedCryptoHe_0; "Nested crypto header datums count passe"...
0x180109656  mov     r9d, ebx; int
0x180109659  mov     [rsp+0E0h+Format], rax; Format
0x18010965e  lea     r8, aFvedatum2crypt_1; "FveDatum2CryptoHeaderCreate"
0x180109665  lea     rcx, aMinkernelNgscb_18; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x18010966c  lea     edx, [rbx+66h]; int
0x18010966f  call    FveLibTraceHelper
0x180109674  lea     edx, [rbx+67h]
0x180109677  jmp     short loc_180109614
0x180109679  movzx   edx, word ptr [rbx]
0x18010967c  lea     rcx, aFvedatum2crypt_17; "FveDatum2CryptoHeaderCreate: Creating t"...
0x180109683  call    FveLibDbgTraceHelper
0x180109688  lea     r14d, [rsi+1]
0x18010968c  cmp     r14d, esi
0x18010968f  jb      loc_180109B7B
0x180109695  mov     ecx, r14d
0x180109698  lea     rdx, [rbp+4Fh+Size]
0x18010969c  shl     rcx, 3
0x1801096a0  call    RtlULongLongToULong
0x1801096a5  mov     edi, eax
0x1801096a7  test    eax, eax
0x1801096a9  jns     short loc_1801096BA
0x1801096ab  mov     r9d, 1
0x1801096b1  lea     edx, [r9+78h]
0x1801096b5  jmp     loc_18010961E
0x1801096ba  mov     ecx, dword ptr [rbp+4Fh+Size]; Size
0x1801096bd  lea     r8, [rbp+4Fh+var_A0]
0x1801096c1  mov     edx, 3
0x1801096c6  call    FveLibAllocWithTagZero
0x1801096cb  mov     edi, eax
0x1801096cd  test    eax, eax
0x1801096cf  jns     short loc_180109703
0x1801096d1  mov     r9d, 1; int
0x1801096d7  lea     edx, [r9+7Eh]; int
0x1801096db  mov     dword ptr [rsp+0E0h+var_B8], eax; char
0x1801096df  lea     rax, aError0xX; "Error: 0x%x"
0x1801096e6  lea     r8, aFvedatum2crypt_1; "FveDatum2CryptoHeaderCreate"
0x1801096ed  mov     [rsp+0E0h+Format], rax; Format
0x1801096f2  lea     rcx, aMinkernelNgscb_18; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x1801096f9  call    FveLibTraceHelper
0x1801096fe  jmp     loc_180109C0F
0x180109703  mov     ecx, [rbx]
0x180109705  sub     ecx, 1
0x180109708  jz      loc_180109A05
0x18010970e  sub     ecx, 1
0x180109711  jz      loc_18010994B
0x180109717  sub     ecx, 1
0x18010971a  jz      loc_18010981E
0x180109720  cmp     ecx, 1
0x180109723  jz      short loc_18010976E
0x180109725  movzx   eax, word ptr [rbx]
0x180109728  lea     r8, aFvedatum2crypt_1; "FveDatum2CryptoHeaderCreate"
0x18010972f  mov     dword ptr [rsp+0E0h+var_B8], eax; char
0x180109733  lea     rcx, aMinkernelNgscb_18; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x18010973a  lea     rax, aCryptoinfoType; "CryptoInfo.Type %u not supported"
0x180109741  mov     ebx, 1
0x180109746  mov     r9d, ebx; int
0x180109749  mov     [rsp+0E0h+Format], rax; Format
0x18010974e  mov     edx, 121h; int
0x180109753  call    FveLibTraceHelper
0x180109758  mov     edi, 0C0000002h
0x18010975d  mov     r9d, ebx
0x180109760  mov     dword ptr [rsp+0E0h+var_B8], edi
0x180109764  mov     edx, 122h
0x180109769  jmp     loc_1801096DF
0x18010976e  mov     eax, [rbx+4]
0x180109771  mov     dword ptr [rbp+4Fh+var_90], eax
0x180109774  test    r12, r12
0x180109777  jnz     short loc_1801097DE
0x180109779  test    esi, esi
0x18010977b  jnz     short loc_1801097DE
0x18010977d  lea     r8, [rbp+4Fh+var_B0]
0x180109781  lea     rcx, [rbp+4Fh+var_90]
0x180109785  call    FveDatum2CryptoIntegrityHashCreate
0x18010978a  mov     edi, eax
0x18010978c  test    eax, eax
0x18010978e  jns     short loc_1801097C6
0x180109790  mov     dword ptr [rsp+0E0h+var_B8], eax; char
0x180109794  lea     r9d, [r12+1]; int
0x180109799  lea     rax, aError0xX; "Error: 0x%x"
0x1801097a0  mov     edx, 113h; int
0x1801097a5  lea     r8, aFvedatum2crypt_1; "FveDatum2CryptoHeaderCreate"
0x1801097ac  mov     [rsp+0E0h+Format], rax; Format
0x1801097b1  lea     rcx, aMinkernelNgscb_18; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x1801097b8  call    FveLibTraceHelper
0x1801097bd  mov     r15, [rbp+4Fh+var_B0]
0x1801097c1  jmp     loc_180109C02
0x1801097c6  mov     rax, [rbp+4Fh+var_A0]
0x1801097ca  mov     ebx, 1
0x1801097cf  mov     r15, [rbp+4Fh+var_B0]
0x1801097d3  mov     r8d, ebx
0x1801097d6  mov     [rax], r15
0x1801097d9  jmp     loc_180109A90
0x1801097de  lea     rax, aIntegrityHashS; "Integrity hash scenario does not suppor"...
0x1801097e5  mov     ebx, 1
0x1801097ea  mov     r9d, ebx; int
0x1801097ed  mov     [rsp+0E0h+Format], rax; Format
0x1801097f2  lea     r8, aFvedatum2crypt_1; "FveDatum2CryptoHeaderCreate"
0x1801097f9  mov     edx, 107h; int
0x1801097fe  lea     rcx, aMinkernelNgscb_18; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x180109805  call    FveLibTraceHelper
0x18010980a  mov     eax, 0C000000Dh
0x18010980f  mov     r9d, ebx
0x180109812  mov     edi, eax
0x180109814  mov     edx, 108h
0x180109819  jmp     loc_1801096DB
0x18010981e  movsd   xmm0, qword ptr [rbx+4]
0x180109823  mov     eax, [rbx+0Ch]
0x180109826  movsd   xmm1, qword ptr [r15+14h]
0x18010982c  movsd   [rbp+4Fh+var_80], xmm0
0x180109831  mov     [rbp+4Fh+var_78], eax
0x180109834  mov     al, [rbx+10h]
0x180109837  mov     [rbp+4Fh+var_74], al
0x18010983a  movsd   [rbp+4Fh+var_50], xmm1
0x18010983f  movups  xmm0, xmmword ptr [r15+4]
0x180109844  movups  [rbp+4Fh+var_60], xmm0
0x180109848  test    r12, r12
0x18010984b  jnz     loc_18010990B
0x180109851  test    esi, esi
0x180109853  jnz     loc_18010990B
0x180109859  cmp     dword ptr [r15], 2
0x18010985d  jz      short loc_18010989D
0x18010985f  lea     rax, aCryptoParamsTy; "Crypto params type incorrect"
0x180109866  mov     edx, 0E4h; int
0x18010986b  lea     ebx, [rsi+1]
0x18010986e  mov     [rsp+0E0h+Format], rax; Format
0x180109873  mov     r9d, ebx; int
0x180109876  lea     r8, aFvedatum2crypt_1; "FveDatum2CryptoHeaderCreate"
0x18010987d  lea     rcx, aMinkernelNgscb_18; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x180109884  call    FveLibTraceHelper
0x180109889  mov     eax, 0C000000Dh
0x18010988e  mov     r9d, ebx
0x180109891  mov     edi, eax
0x180109893  mov     edx, 0E5h
0x180109898  jmp     loc_1801096DB
0x18010989d  lea     r9, [rbp+4Fh+var_A8]
0x1801098a1  lea     rdx, [rbp+4Fh+var_60]
0x1801098a5  lea     rcx, [rbp+4Fh+var_80]
0x1801098a9  call    FveDatum2CryptoKeyKdfCreate
0x1801098ae  mov     edi, eax
0x1801098b0  test    eax, eax
0x1801098b2  jns     short loc_1801098EF
0x1801098b4  mov     dword ptr [rsp+0E0h+var_B8], eax; char
0x1801098b8  lea     r8, aFvedatum2crypt_1; "FveDatum2CryptoHeaderCreate"
0x1801098bf  lea     rax, aError0xX; "Error: 0x%x"
0x1801098c6  mov     r9d, 1; int
0x1801098cc  mov     edx, 0F1h; int
0x1801098d1  mov     [rsp+0E0h+Format], rax; Format
0x1801098d6  lea     rcx, aMinkernelNgscb_18; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x1801098dd  call    FveLibTraceHelper
0x1801098e2  mov     rsi, [rbp+4Fh+var_A8]
0x1801098e6  mov     r15, [rbp+4Fh+var_B0]
0x1801098ea  jmp     loc_180109BF5
0x1801098ef  mov     rax, [rbp+4Fh+var_A0]
0x1801098f3  mov     ebx, 1
0x1801098f8  mov     rsi, [rbp+4Fh+var_A8]
0x1801098fc  mov     r8d, ebx
0x1801098ff  mov     r15, [rbp+4Fh+var_B0]
0x180109903  mov     [rax], rsi
0x180109906  jmp     loc_180109A94
0x18010990b  lea     rax, aKdfScenarioDoe; "KDF scenario does not support nested cr"...
0x180109912  mov     ebx, 1
0x180109917  mov     r9d, ebx; int
0x18010991a  mov     [rsp+0E0h+Format], rax; Format
0x18010991f  lea     r8, aFvedatum2crypt_1; "FveDatum2CryptoHeaderCreate"
0x180109926  mov     edx, 0DBh; int
0x18010992b  lea     rcx, aMinkernelNgscb_18; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x180109932  call    FveLibTraceHelper
0x180109937  mov     eax, 0C000000Dh
0x18010993c  mov     r9d, ebx
0x18010993f  mov     edi, eax
0x180109941  mov     edx, 0DCh
0x180109946  jmp     loc_1801096DB
0x18010994b  movsd   xmm0, qword ptr [rbx+4]
0x180109950  lea     r8, [rbp+4Fh+var_68]
0x180109954  movzx   eax, word ptr [rbx+0Ch]
0x180109958  lea     rcx, [rbp+4Fh+var_90]
0x18010995c  movsd   [rbp+4Fh+var_90], xmm0
0x180109961  mov     [rbp+4Fh+var_88], ax
0x180109965  call    FveDatum2CryptoKeyWrapCreate
0x18010996a  mov     edi, eax
0x18010996c  test    eax, eax
0x18010996e  jns     short loc_1801099AB
0x180109970  mov     r9d, 1; int
0x180109976  mov     edx, 0B4h; int
0x18010997b  mov     dword ptr [rsp+0E0h+var_B8], eax; char
0x18010997f  lea     r8, aFvedatum2crypt_1; "FveDatum2CryptoHeaderCreate"
0x180109986  lea     rax, aError0xX; "Error: 0x%x"
0x18010998d  lea     rcx, aMinkernelNgscb_18; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x180109994  mov     [rsp+0E0h+Format], rax; Format
0x180109999  call    FveLibTraceHelper
0x18010999e  mov     rsi, [rbp+4Fh+var_A8]
0x1801099a2  mov     r15, [rbp+4Fh+var_B0]
0x1801099a6  jmp     loc_180109BE4
0x1801099ab  mov     rax, [rbp+4Fh+var_A0]
0x1801099af  xor     r9d, r9d
0x1801099b2  mov     rcx, [rbp+4Fh+var_68]
0x1801099b6  mov     ebx, 1
0x1801099bb  mov     r8d, ebx
0x1801099be  mov     [rax], rcx
0x1801099c1  test    esi, esi
0x1801099c3  jz      loc_180109A8C
0x1801099c9  mov     rax, [rbp+4Fh+var_A0]
0x1801099cd  mov     rcx, [r12+r9*8]
0x1801099d1  mov     edx, r8d
0x1801099d4  mov     [rax+rdx*8], rcx
0x1801099d8  lea     eax, [r8+1]
0x1801099dc  cmp     eax, r8d
0x1801099df  jb      short loc_1801099F1
0x1801099e1  add     r9d, ebx
0x1801099e4  mov     r8d, eax
0x1801099e7  cmp     r9d, esi
0x1801099ea  jb      short loc_1801099C9
0x1801099ec  jmp     loc_180109A8C
0x1801099f1  mov     eax, 0C0000095h
0x1801099f6  mov     r9d, ebx
0x1801099f9  mov     edi, eax
0x1801099fb  mov     edx, 0CAh
0x180109a00  jmp     loc_18010997B
0x180109a05  movsd   xmm0, qword ptr [rbx+4]
0x180109a0a  movzx   eax, word ptr [rbx+0Ch]
0x180109a0e  movsd   [rbp+4Fh+var_80], xmm0
0x180109a13  mov     word ptr [rbp+4Fh+var_78], ax
0x180109a17  test    r12, r12
0x180109a1a  jnz     loc_180109B3B
0x180109a20  test    esi, esi
0x180109a22  jnz     loc_180109B3B
0x180109a28  lea     r8, [rbp+4Fh+var_90]
0x180109a2c  lea     rcx, [rbp+4Fh+var_80]
0x180109a30  call    FveDatum2CryptoKeyCreationCreate
0x180109a35  mov     edi, eax
0x180109a37  test    eax, eax
0x180109a39  jns     short loc_180109A79
0x180109a3b  mov     dword ptr [rsp+0E0h+var_B8], eax; char
0x180109a3f  lea     r9d, [r12+1]; int
0x180109a44  lea     rax, aError0xX; "Error: 0x%x"
0x180109a4b  mov     edx, 99h; int
0x180109a50  lea     r8, aFvedatum2crypt_1; "FveDatum2CryptoHeaderCreate"
  ... truncated ...
```
