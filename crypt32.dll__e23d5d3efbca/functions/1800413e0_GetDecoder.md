# GetDecoder

- ea: `0x1800413e0`
- end: `0x18004175a`
- name: `GetDecoder`
- size: `890`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `20`
- callee_count: `6`
- tags: ``

## callers

- `0x18003be80`
- `0x18003cbb0`
- `0x18003d8d0`
- `0x18003e6f0`
- `0x18003f300`
- `0x18003f550`
- `0x18003f740`
- `0x18003f9a0`
- `0x18003fbd0`
- `0x180040f90`
- `0x180072170`
- `0x180073580`
- `0x18007b550`
- `0x18007ec10`
- `0x18007fa70`
- `0x180080330`
- `0x180080520`
- `0x180081af0`
- `0x180081d88`
- `0x180082fa4`

## callees

- `0x18000fd10`
- `0x180021994`
- `0x180028d60`
- `0x1800413e0`
- `0x180046e10`
- `0x1800bf63c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800414e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004158f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041645`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041665`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800414e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004158f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041645`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041665`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800414f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041528`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041635`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800414f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041528`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041635`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800414a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041509`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800415a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800414a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041509`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800415a4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004142c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004142c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800416a5`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800416a5`
- `MSASN1!ASN1_CreateDecoder` at `0x18004154b`
- `MSASN1!ASN1_CreateDecoder` at `0x18004154b`
- `MSASN1!ASN1_CreateModule` at `0x180041604`
- `MSASN1!ASN1_CreateModule` at `0x180041604`

## pseudocode

```c
__int64 GetDecoder()
{
  __int64 v0; // rsi
  _DWORD *Value; // rax
  _QWORD *v2; // rbx
  unsigned int v3; // ebp
  char *v4; // rdi
  __int64 *v5; // rbx
  __int64 v6; // rdi
  __int64 result; // rax
  unsigned int v8; // r14d
  __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  DWORD v11; // ecx
  __int64 v12; // rsi
  int v13; // ebx
  __int64 v14; // rsi
  int v15; // eax
  __int64 v16; // rax
  __int64 Module; // rax
  DWORD v18; // ecx
  _QWORD *v19; // rax
  _QWORD *v20; // rax
  __int64 v21; // [rsp+70h] [rbp+8h] BYREF

  if ( !dword_18015D590 )
  {
    EnterCriticalSection(&g_pkiCriticalSection);
    Module = X509_Module;
    if ( X509_Module
      || (Module = ASN1_CreateModule(
                     0x10000,
                     1024,
                     4096,
                     86,
                     off_180121B30,
                     off_180121880,
                     off_1801215D0,
                     qword_180130D70,
                     959460728),
          (X509_Module = Module) != 0) )
    {
      I_CryptSetAsn1Module(hX509Asn1Module, Module);
      dword_18015D590 = 1;
    }
    LeaveCriticalSection(&g_pkiCriticalSection);
  }
  v21 = 0;
  if ( !hX509Asn1Module )
    return 0;
  v0 = hX509Asn1Module - 1;
  Value = TlsGetValue(dwTlsIndex);
  v2 = Value;
  if ( Value )
  {
    v3 = *Value;
    if ( (unsigned int)v0 < *Value )
    {
      v4 = (char *)*((_QWORD *)Value + 1);
      goto LABEL_6;
    }
  }
  else
  {
    v3 = 0;
  }
  EnterCriticalSection(&stru_18015CD98);
  v8 = dword_18015D670;
  if ( (unsigned int)v0 >= dword_18015D670 )
  {
    v11 = -2147024809;
    goto LABEL_17;
  }
  if ( v2 )
  {
    v4 = (char *)v2[1];
    if ( (unsigned int)dword_18015D670 <= 0x10 )
      goto LABEL_43;
    v4 = (char *)PkiRealloc(v2[1], 8LL * (unsigned int)dword_18015D670);
    if ( v4 )
    {
LABEL_42:
      v8 = dword_18015D670;
LABEL_43:
      if ( v3 < v8 )
        memset_0(&v4[8 * v3], 0, 8LL * (v8 - v3));
      v2[1] = v4;
      *(_DWORD *)v2 = v8;
      goto LABEL_19;
    }
    goto LABEL_16;
  }
  v9 = 16;
  if ( (unsigned int)dword_18015D670 > 0x10 )
    v9 = (unsigned int)dword_18015D670;
  v10 = 8 * v9;
  if ( v10 > 0xFFFFFFFF || (v4 = (char *)PkiZeroAlloc((unsigned int)v10)) == 0 )
  {
LABEL_16:
    v11 = -2147024882;
LABEL_17:
    SetLastError(v11);
    goto LABEL_18;
  }
  v19 = (_QWORD *)PkiZeroAlloc(0x20u);
  v2 = v19;
  if ( !v19 )
  {
    PkiDefaultCryptFree(v4);
    goto LABEL_16;
  }
  if ( TlsSetValue(dwTlsIndex, v19) )
  {
    v20 = qword_18015CD90;
    v2[3] = 0;
    v2[2] = v20;
    if ( v20 )
      v20[3] = v2;
    qword_18015CD90 = v2;
    goto LABEL_42;
  }
  PkiDefaultCryptFree(v2);
  PkiDefaultCryptFree(v4);
LABEL_18:
  v4 = 0;
LABEL_19:
  LeaveCriticalSection(&stru_18015CD98);
LABEL_6:
  if ( !v4 )
    return 0;
  v5 = (__int64 *)&v4[8 * v0];
  v6 = *v5;
  if ( !*v5 )
  {
    v16 = PkiZeroAlloc(0x10u);
    v6 = v16;
    if ( !v16 )
    {
      SetLastError(0x8007000E);
      return 0;
    }
    *v5 = v16;
  }
  result = *(_QWORD *)(v6 + 8);
  v21 = result;
  if ( !result )
  {
    EnterCriticalSection(&stru_18015CD98);
    v12 = 2 * v0;
    v13 = *((_DWORD *)qword_18015D668 + 2 * v12);
    v14 = *((_QWORD *)qword_18015D668 + v12 + 1);
    LeaveCriticalSection(&stru_18015CD98);
    if ( v13 == 3 && v14 )
    {
      v15 = ASN1_CreateDecoder(v14, &v21, 0, 0, 0);
      if ( v15 )
      {
        v18 = -2146882280 - v15;
        if ( v15 >= 0 )
          v18 = v15 - 2146882024;
        SetLastError(v18);
        return 0;
      }
      else
      {
        *(_QWORD *)(v6 + 8) = v21;
        return v21;
      }
    }
    SetLastError(0x80070057);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800413e0  push    r15
0x1800413e2  sub     rsp, 60h
0x1800413e6  cmp     cs:dword_18015D590, 0
0x1800413ed  jz      loc_18004159D
0x1800413f3  mov     eax, cs:?hX509Asn1Module@@3KA; ulong hX509Asn1Module
0x1800413f9  xor     r15d, r15d
0x1800413fc  mov     [rsp+68h+arg_0], r15
0x180041401  test    eax, eax
0x180041403  jz      loc_1800416E6
0x180041409  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18004140f  mov     [rsp+68h+arg_8], rbx
0x180041414  mov     [rsp+68h+arg_10], rbp
0x18004141c  mov     [rsp+68h+arg_18], rsi
0x180041424  lea     esi, [rax-1]
0x180041427  mov     [rsp+68h+var_10], rdi
0x18004142c  call    cs:__imp_TlsGetValue
0x180041432  mov     rbx, rax
0x180041435  test    rax, rax
0x180041438  jz      short loc_180041491
0x18004143a  mov     ebp, [rax]
0x18004143c  cmp     esi, ebp
0x18004143e  jnb     short loc_180041494
0x180041440  mov     rdi, [rax+8]
0x180041444  mov     rbp, [rsp+68h+arg_10]
0x18004144c  test    rdi, rdi
0x18004144f  jz      loc_180041595
0x180041455  lea     rbx, [rdi+rsi*8]
0x180041459  mov     rdi, [rdi+rsi*8]
0x18004145d  test    rdi, rdi
0x180041460  jz      loc_18004156C
0x180041466  mov     rax, [rdi+8]
0x18004146a  mov     [rsp+68h+arg_0], rax
0x18004146f  test    rax, rax
0x180041472  jz      loc_180041502
0x180041478  mov     rsi, [rsp+68h+arg_18]
0x180041480  mov     rbx, [rsp+68h+arg_8]
0x180041485  mov     rdi, [rsp+68h+var_10]
0x18004148a  add     rsp, 60h
0x18004148e  pop     r15
0x180041490  retn
0x180041491  mov     ebp, r15d
0x180041494  lea     rcx, stru_18015CD98; lpCriticalSection
0x18004149b  mov     [rsp+68h+var_18], r14
0x1800414a0  call    cs:__imp_EnterCriticalSection
0x1800414a6  mov     r14d, cs:dword_18015D670
0x1800414ad  cmp     esi, r14d
0x1800414b0  jnb     loc_1800416EE
0x1800414b6  test    rbx, rbx
0x1800414b9  jnz     loc_1800416F8
0x1800414bf  mov     ecx, 10h
0x1800414c4  mov     eax, 0FFFFFFFFh
0x1800414c9  cmp     r14d, ecx
0x1800414cc  cmova   ecx, r14d
0x1800414d0  shl     rcx, 3
0x1800414d4  cmp     rcx, rax
0x1800414d7  jbe     loc_180041673
0x1800414dd  mov     ecx, 8007000Eh; dwErrCode
0x1800414e2  call    cs:__imp_SetLastError
0x1800414e8  mov     rdi, r15
0x1800414eb  lea     rcx, stru_18015CD98; lpCriticalSection
0x1800414f2  call    cs:__imp_LeaveCriticalSection
0x1800414f8  mov     r14, [rsp+68h+var_18]
0x1800414fd  jmp     loc_180041444
0x180041502  lea     rcx, stru_18015CD98; lpCriticalSection
0x180041509  call    cs:__imp_EnterCriticalSection
0x18004150f  mov     rax, cs:qword_18015D668
0x180041516  lea     rcx, stru_18015CD98; lpCriticalSection
0x18004151d  add     rsi, rsi
0x180041520  mov     ebx, [rax+rsi*8]
0x180041523  mov     rsi, [rax+rsi*8+8]
0x180041528  call    cs:__imp_LeaveCriticalSection
0x18004152e  cmp     ebx, 3
0x180041531  jnz     short loc_18004158A
0x180041533  test    rsi, rsi
0x180041536  jz      short loc_18004158A
0x180041538  xor     r9d, r9d
0x18004153b  mov     [rsp+68h+var_48], r15
0x180041540  xor     r8d, r8d
0x180041543  lea     rdx, [rsp+68h+arg_0]
0x180041548  mov     rcx, rsi
0x18004154b  call    cs:__imp_ASN1_CreateDecoder
0x180041551  test    eax, eax
0x180041553  jnz     loc_180041653
0x180041559  mov     rax, [rsp+68h+arg_0]
0x18004155e  mov     [rdi+8], rax
0x180041562  mov     rax, [rsp+68h+arg_0]
0x180041567  jmp     loc_180041478
0x18004156c  mov     ecx, 10h; uBytes
0x180041571  call    PkiZeroAlloc
0x180041576  mov     rdi, rax
0x180041579  test    rax, rax
0x18004157c  jz      loc_180041640
0x180041582  mov     [rbx], rax
0x180041585  jmp     loc_180041466
0x18004158a  mov     ecx, 80070057h; dwErrCode
0x18004158f  call    cs:__imp_SetLastError
0x180041595  mov     rax, r15
0x180041598  jmp     loc_180041478
0x18004159d  lea     rcx, g_pkiCriticalSection; lpCriticalSection
0x1800415a4  call    cs:__imp_EnterCriticalSection
0x1800415aa  mov     rax, cs:X509_Module
0x1800415b1  test    rax, rax
0x1800415b4  jnz     short loc_180041616
0x1800415b6  mov     [rsp+68h+var_28], 39303578h
0x1800415be  lea     rax, qword_180130D70
0x1800415c5  mov     [rsp+68h+var_30], rax
0x1800415ca  mov     edx, 400h
0x1800415cf  lea     rax, off_1801215D0
0x1800415d6  mov     ecx, 10000h
0x1800415db  mov     [rsp+68h+var_38], rax
0x1800415e0  mov     r9d, 56h ; 'V'
0x1800415e6  lea     rax, off_180121880
0x1800415ed  mov     r8d, 1000h
0x1800415f3  mov     [rsp+68h+var_40], rax
0x1800415f8  lea     rax, off_180121B30
0x1800415ff  mov     [rsp+68h+var_48], rax
0x180041604  call    cs:__imp_ASN1_CreateModule
0x18004160a  mov     cs:X509_Module, rax
0x180041611  test    rax, rax
0x180041614  jz      short loc_18004162E
0x180041616  mov     ecx, cs:?hX509Asn1Module@@3KA; ulong hX509Asn1Module
0x18004161c  mov     rdx, rax
0x18004161f  call    I_CryptSetAsn1Module
0x180041624  mov     cs:dword_18015D590, 1
0x18004162e  lea     rcx, g_pkiCriticalSection; lpCriticalSection
0x180041635  call    cs:__imp_LeaveCriticalSection
0x18004163b  jmp     loc_1800413F3
0x180041640  mov     ecx, 8007000Eh; dwErrCode
0x180041645  call    cs:__imp_SetLastError
0x18004164b  mov     rax, r15
0x18004164e  jmp     loc_180041478
0x180041653  mov     ecx, 80092D18h
0x180041658  lea     edx, [rax-7FF6D1E8h]
0x18004165e  sub     ecx, eax
0x180041660  test    eax, eax
0x180041662  cmovns  ecx, edx; dwErrCode
0x180041665  call    cs:__imp_SetLastError
0x18004166b  mov     rax, r15
0x18004166e  jmp     loc_180041478
0x180041673  mov     ecx, ecx; uBytes
0x180041675  call    PkiZeroAlloc
0x18004167a  mov     rdi, rax
0x18004167d  test    rax, rax
0x180041680  jz      loc_1800414DD
0x180041686  mov     ecx, 20h ; ' '; uBytes
0x18004168b  call    PkiZeroAlloc
0x180041690  mov     rbx, rax
0x180041693  test    rax, rax
0x180041696  jz      loc_18004171F
0x18004169c  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800416a2  mov     rdx, rax; lpTlsValue
0x1800416a5  call    cs:__imp_TlsSetValue
0x1800416ab  test    eax, eax
0x1800416ad  jz      short loc_18004172C
0x1800416af  mov     rax, cs:qword_18015CD90
0x1800416b6  mov     [rbx+18h], r15
0x1800416ba  mov     [rbx+10h], rax
0x1800416be  test    rax, rax
0x1800416c1  jz      short loc_1800416C7
0x1800416c3  mov     [rax+18h], rbx
0x1800416c7  mov     cs:qword_18015CD90, rbx
0x1800416ce  mov     r14d, cs:dword_18015D670
0x1800416d5  cmp     ebp, r14d
0x1800416d8  jb      short loc_180041741
0x1800416da  mov     [rbx+8], rdi
0x1800416de  mov     [rbx], r14d
0x1800416e1  jmp     loc_1800414EB
0x1800416e6  mov     rax, r15
0x1800416e9  jmp     loc_18004148A
0x1800416ee  mov     ecx, 80070057h
0x1800416f3  jmp     loc_1800414E2
0x1800416f8  mov     rdi, [rbx+8]
0x1800416fc  cmp     r14d, 10h
0x180041700  jbe     short loc_1800416D5
0x180041702  mov     rdx, r14
0x180041705  mov     rcx, rdi
0x180041708  shl     rdx, 3
0x18004170c  call    PkiRealloc
0x180041711  mov     rdi, rax
0x180041714  test    rax, rax
0x180041717  jz      loc_1800414DD
0x18004171d  jmp     short loc_1800416CE
0x18004171f  mov     rcx, rdi; hMem
0x180041722  call    PkiDefaultCryptFree
0x180041727  jmp     loc_1800414DD
0x18004172c  mov     rcx, rbx; hMem
0x18004172f  call    PkiDefaultCryptFree
0x180041734  mov     rcx, rdi; hMem
0x180041737  call    PkiDefaultCryptFree
0x18004173c  jmp     loc_1800414E8
0x180041741  mov     eax, ebp
0x180041743  mov     r8d, r14d
0x180041746  sub     r8d, ebp
0x180041749  xor     edx, edx; Val
0x18004174b  shl     r8, 3; Size
0x18004174f  lea     rcx, [rdi+rax*8]; void *
0x180041753  call    memset_0
0x180041758  jmp     short loc_1800416DA
```
