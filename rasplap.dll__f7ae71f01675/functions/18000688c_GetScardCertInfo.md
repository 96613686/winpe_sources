# GetScardCertInfo

- ea: `0x18000688c`
- end: `0x180006c4f`
- name: `GetScardCertInfo`
- size: `963`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180001ee0`
- `0x180005068`

## callees

- `0x1800056d4`
- `0x18000627c`
- `0x18000688c`
- `0x18000b0ce`
- `0x18000b100`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180006b1e`
- `KERNEL32!LocalAlloc` at `0x180006b81`
- `KERNEL32!LocalAlloc` at `0x180006b1e`
- `KERNEL32!LocalAlloc` at `0x180006b81`
- `WinSCard!SCardReleaseContext` at `0x180006c22`
- `WinSCard!SCardReleaseContext` at `0x180006c22`
- `WinSCard!SCardEstablishContext` at `0x1800068fb`
- `WinSCard!SCardEstablishContext` at `0x1800068fb`
- `WinSCard!SCardFreeMemory` at `0x180006af4`
- `WinSCard!SCardFreeMemory` at `0x180006b58`
- `WinSCard!SCardFreeMemory` at `0x180006c0f`
- `WinSCard!SCardFreeMemory` at `0x180006af4`
- `WinSCard!SCardFreeMemory` at `0x180006b58`
- `WinSCard!SCardFreeMemory` at `0x180006c0f`
- `WinSCard!SCardListCardsW` at `0x180006a1b`
- `WinSCard!SCardListCardsW` at `0x180006a1b`
- `WinSCard!SCardGetStatusChangeW` at `0x1800069b8`
- `WinSCard!SCardGetStatusChangeW` at `0x1800069b8`
- `WinSCard!SCardListReadersW` at `0x180006932`
- `WinSCard!SCardListReadersW` at `0x180006932`
- `WinSCard!SCardGetCardTypeProviderNameW` at `0x180006a78`
- `WinSCard!SCardGetCardTypeProviderNameW` at `0x180006a78`
- `rtutils!TracePrintfExA` at `0x180006981`
- `rtutils!TracePrintfExA` at `0x1800069dd`
- `rtutils!TracePrintfExA` at `0x180006a58`
- `rtutils!TracePrintfExA` at `0x180006a99`
- `rtutils!TracePrintfExA` at `0x180006acc`
- `rtutils!TracePrintfExA` at `0x180006bc5`
- `rtutils!TracePrintfExA` at `0x180006bfc`
- `rtutils!TracePrintfExA` at `0x180006981`
- `rtutils!TracePrintfExA` at `0x1800069dd`
- `rtutils!TracePrintfExA` at `0x180006a58`
- `rtutils!TracePrintfExA` at `0x180006a99`
- `rtutils!TracePrintfExA` at `0x180006acc`
- `rtutils!TracePrintfExA` at `0x180006bc5`
- `rtutils!TracePrintfExA` at `0x180006bfc`

## string_xrefs

- `0x18000694a`: `Failed SCardListReaders: Error: %x`
- `0x180006978`: `Reader: %S`
- `0x180006bbc`: `No Smart card present in Reader: %S`

## pseudocode

```c
__int64 __fastcall GetScardCertInfo(struct _CERT_HASH *a1, wchar_t **a2, wchar_t **a3, struct _CRYPT_KEY_PROV_INFO *a4)
{
  unsigned int SmartCardCertificate; // r15d
  unsigned int v7; // eax
  unsigned int v8; // eax
  const wchar_t *v9; // r14
  __int64 v10; // rsi
  LONG v11; // eax
  unsigned int v12; // eax
  const wchar_t *i; // rdi
  LONG CardTypeProviderNameW; // eax
  __int64 v15; // rax
  __int64 v16; // rdx
  wchar_t *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  wchar_t *v20; // rax
  __int64 v21; // rax
  SCARDCONTEXT phContext; // [rsp+30h] [rbp-79h] BYREF
  WCHAR szProvider[4]; // [rsp+38h] [rbp-71h] BYREF
  WCHAR mszCards[4]; // [rsp+40h] [rbp-69h] BYREF
  WCHAR mszReaders[4]; // [rsp+48h] [rbp-61h] BYREF
  DWORD pcchReaders; // [rsp+50h] [rbp-59h] BYREF
  DWORD pcchCards; // [rsp+54h] [rbp-55h] BYREF
  DWORD pcchProvider; // [rsp+58h] [rbp-51h] BYREF
  struct _CERT_HASH *v30; // [rsp+60h] [rbp-49h]
  wchar_t **v31; // [rsp+68h] [rbp-41h]
  $B80B7D01E79FADDB4AAC58DE22BC823F rgReaderStates; // [rsp+70h] [rbp-39h] BYREF

  v31 = a2;
  v30 = a1;
  phContext = 0;
  *(_QWORD *)mszReaders = 0;
  pcchReaders = -1;
  if ( !a2 || !a3 || !a4 )
    return 0;
  SmartCardCertificate = 0;
  v7 = SCardEstablishContext(2u, 0, 0, &phContext);
  if ( v7 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Failed SCardEstablishContext: Error: %x", v7);
  }
  else
  {
    v8 = SCardListReadersW(phContext, 0, mszReaders, &pcchReaders);
    if ( v8 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Failed SCardListReaders: Error: %x", v8);
    }
    else
    {
      v9 = *(const wchar_t **)mszReaders;
      v10 = -1;
      while ( *v9 )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "Reader: %S", v9);
        *(_QWORD *)mszCards = 0;
        pcchCards = -1;
        memset_0(&rgReaderStates, 0, sizeof(rgReaderStates));
        rgReaderStates.szReader = v9;
        rgReaderStates.dwCurrentState = 0;
        v11 = SCardGetStatusChangeW(phContext, 0, &rgReaderStates, 1u);
        if ( v11 )
        {
          if ( g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "Failed SCardGetStatusChange: Error: %x", v11);
        }
        else if ( (rgReaderStates.dwEventState & 0x20) != 0 && rgReaderStates.cbAtr )
        {
          v12 = SCardListCardsW(phContext, rgReaderStates.rgbAtr, 0, 0, mszCards, &pcchCards);
          if ( v12 )
          {
            if ( g_dwTraceId != -1 )
              TracePrintfExA(g_dwTraceId, 0xCu, "Failed SCardListCards: Error: %x", v12);
            break;
          }
          for ( i = *(const wchar_t **)mszCards; *i; i += v15 + 1 )
          {
            *(_QWORD *)szProvider = 0;
            pcchProvider = -1;
            if ( g_dwTraceId != -1 )
              TracePrintfExA(g_dwTraceId, 0xCu, "Card : %S", i);
            CardTypeProviderNameW = SCardGetCardTypeProviderNameW(phContext, i, 2u, szProvider, &pcchProvider);
            if ( CardTypeProviderNameW )
            {
              if ( g_dwTraceId != -1 )
                TracePrintfExA(
                  g_dwTraceId,
                  0xCu,
                  "Failed SCardGetCardTypeProviderName: Error: %x",
                  CardTypeProviderNameW);
            }
            else
            {
              if ( g_dwTraceId != -1 )
                TracePrintfExA(g_dwTraceId, 0xCu, "Provider Name: %S\n", *(const wchar_t **)szProvider);
              SmartCardCertificate = GetSmartCardCertificate(*(STRSAFE_LPCWSTR *)szProvider, v30, a4);
              if ( *(_QWORD *)szProvider )
              {
                SCardFreeMemory(phContext, *(LPCVOID *)szProvider);
                *(_QWORD *)szProvider = 0;
              }
              if ( SmartCardCertificate )
              {
                v16 = -1;
                do
                  ++v16;
                while ( i[v16] );
                v17 = (wchar_t *)LocalAlloc(0x40u, 2 * v16 + 2);
                *a3 = v17;
                if ( v17 )
                {
                  v18 = -1;
                  do
                    ++v18;
                  while ( i[v18] );
                  StringCchCopyW(v17, v18 + 1, i);
                }
                break;
              }
            }
            v15 = -1;
            do
              ++v15;
            while ( i[v15] );
          }
          if ( *(_QWORD *)mszCards )
          {
            SCardFreeMemory(phContext, *(LPCVOID *)mszCards);
            *(_QWORD *)mszCards = 0;
          }
          if ( SmartCardCertificate )
          {
            v19 = -1;
            do
              ++v19;
            while ( v9[v19] );
            v20 = (wchar_t *)LocalAlloc(0x40u, 2 * v19 + 2);
            *v31 = v20;
            if ( v20 )
            {
              do
                ++v10;
              while ( v9[v10] );
              StringCchCopyW(v20, v10 + 1, v9);
            }
            break;
          }
        }
        else if ( g_dwTraceId != -1 )
        {
          TracePrintfExA(g_dwTraceId, 0xCu, "No Smart card present in Reader: %S", v9);
        }
        v21 = -1;
        do
          ++v21;
        while ( v9[v21] );
        v9 += v21 + 1;
      }
    }
  }
  if ( *(_QWORD *)mszReaders )
  {
    SCardFreeMemory(phContext, *(LPCVOID *)mszReaders);
    *(_QWORD *)mszReaders = 0;
  }
  if ( phContext )
    SCardReleaseContext(phContext);
  return SmartCardCertificate;
}

```

## disassembly

```asm
0x18000688c  push    rbp
0x18000688e  push    rbx
0x18000688f  push    rsi
0x180006890  push    rdi
0x180006891  push    r12
0x180006893  push    r13
0x180006895  push    r14
0x180006897  push    r15
0x180006899  lea     rbp, [rsp-1Fh]
0x18000689e  sub     rsp, 0C8h
0x1800068a5  mov     rax, cs:__security_cookie
0x1800068ac  xor     rax, rsp
0x1800068af  mov     [rbp+57h+var_50], rax
0x1800068b3  xor     edi, edi
0x1800068b5  mov     [rbp+57h+var_98], rdx
0x1800068b9  or      ebx, 0FFFFFFFFh
0x1800068bc  mov     [rbp+57h+var_A0], rcx
0x1800068c0  mov     [rbp+57h+phContext], rdi
0x1800068c4  mov     r12, r9
0x1800068c7  mov     qword ptr [rbp+57h+mszReaders], rdi
0x1800068cb  mov     r13, r8
0x1800068ce  mov     [rbp+57h+pcchReaders], ebx
0x1800068d1  test    rdx, rdx
0x1800068d4  jz      loc_180006C2D
0x1800068da  test    r8, r8
0x1800068dd  jz      loc_180006C2D
0x1800068e3  test    r9, r9
0x1800068e6  jz      loc_180006C2D
0x1800068ec  lea     r9, [rbp+57h+phContext]; phContext
0x1800068f0  xor     r8d, r8d; pvReserved2
0x1800068f3  xor     edx, edx; pvReserved1
0x1800068f5  lea     ecx, [rdi+2]; dwScope
0x1800068f8  mov     r15d, edi
0x1800068fb  call    cs:__imp_SCardEstablishContext
0x180006901  test    eax, eax
0x180006903  jz      short loc_180006924
0x180006905  mov     ecx, cs:g_dwTraceId
0x18000690b  cmp     ecx, ebx
0x18000690d  jz      loc_180006C02
0x180006913  lea     r8, aFailedScardest; "Failed SCardEstablishContext: Error: %x"
0x18000691a  mov     edx, 0Ch
0x18000691f  jmp     loc_180006BF9
0x180006924  mov     rcx, [rbp+57h+phContext]; hContext
0x180006928  lea     r9, [rbp+57h+pcchReaders]; pcchReaders
0x18000692c  lea     r8, [rbp+57h+mszReaders]; mszReaders
0x180006930  xor     edx, edx; mszGroups
0x180006932  call    cs:__imp_SCardListReadersW
0x180006938  test    eax, eax
0x18000693a  jz      short loc_180006953
0x18000693c  mov     ecx, cs:g_dwTraceId
0x180006942  cmp     ecx, ebx
0x180006944  jz      loc_180006C02
0x18000694a  lea     r8, aFailedScardlis; "Failed SCardListReaders: Error: %x"
0x180006951  jmp     short loc_18000691A
0x180006953  mov     r14, qword ptr [rbp+57h+mszReaders]
0x180006957  mov     ebx, 0Ch
0x18000695c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180006960  cmp     di, [r14]
0x180006964  jz      loc_180006C02
0x18000696a  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180006970  cmp     ecx, 0FFFFFFFFh
0x180006973  jz      short loc_180006987
0x180006975  mov     r9, r14
0x180006978  lea     r8, aReaderS; "Reader: %S"
0x18000697f  mov     edx, ebx; dwFlags
0x180006981  call    cs:__imp_TracePrintfExA
0x180006987  xor     edx, edx; Val
0x180006989  mov     qword ptr [rbp+57h+var_C0], rdi
0x18000698d  lea     rcx, [rbp+57h+rgReaderStates]; void *
0x180006991  mov     [rbp+57h+var_AC], 0FFFFFFFFh
0x180006998  lea     r8d, [rdx+40h]; Size
0x18000699c  call    memset_0
0x1800069a1  mov     rcx, [rbp+57h+phContext]; hContext
0x1800069a5  lea     r8, [rbp+57h+rgReaderStates]; rgReaderStates
0x1800069a9  mov     r9d, 1; cReaders
0x1800069af  mov     [rbp+57h+rgReaderStates.szReader], r14
0x1800069b3  xor     edx, edx; dwTimeout
0x1800069b5  mov     [rbp+57h+rgReaderStates.dwCurrentState], edi
0x1800069b8  call    cs:__imp_SCardGetStatusChangeW
0x1800069be  test    eax, eax
0x1800069c0  jz      short loc_1800069E8
0x1800069c2  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800069c8  cmp     ecx, 0FFFFFFFFh
0x1800069cb  jz      loc_180006BCB
0x1800069d1  mov     r9d, eax
0x1800069d4  lea     r8, aFailedScardget; "Failed SCardGetStatusChange: Error: %x"
0x1800069db  mov     edx, ebx; dwFlags
0x1800069dd  call    cs:__imp_TracePrintfExA
0x1800069e3  jmp     loc_180006BCB
0x1800069e8  test    byte ptr [rbp+57h+rgReaderStates.dwEventState], 20h
0x1800069ec  jz      loc_180006BAE
0x1800069f2  cmp     [rbp+57h+rgReaderStates.cbAtr], edi
0x1800069f5  jz      loc_180006BAE
0x1800069fb  mov     rcx, [rbp+57h+phContext]; hContext
0x1800069ff  lea     rax, [rbp+57h+var_AC]
0x180006a03  mov     [rsp+100h+pcchCards], rax; pcchCards
0x180006a08  lea     rdx, [rbp+57h+rgReaderStates.rgbAtr]; pbAtr
0x180006a0c  lea     rax, [rbp+57h+var_C0]
0x180006a10  xor     r9d, r9d; cguidInterfaceCount
0x180006a13  xor     r8d, r8d; rgquidInterfaces
0x180006a16  mov     [rsp+100h+mszCards], rax; mszCards
0x180006a1b  call    cs:__imp_SCardListCardsW
0x180006a21  test    eax, eax
0x180006a23  jnz     loc_180006BE5
0x180006a29  mov     rdi, qword ptr [rbp+57h+var_C0]
0x180006a2d  xor     ecx, ecx
0x180006a2f  cmp     cx, [rdi]
0x180006a32  jz      loc_180006B49
0x180006a38  or      eax, 0FFFFFFFFh
0x180006a3b  mov     qword ptr [rbp+57h+szProvider], rcx
0x180006a3f  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180006a45  mov     [rbp+57h+pcchProvider], eax
0x180006a48  cmp     ecx, eax
0x180006a4a  jz      short loc_180006A5E
0x180006a4c  mov     r9, rdi
0x180006a4f  lea     r8, aCardS; "Card : %S"
0x180006a56  mov     edx, ebx; dwFlags
0x180006a58  call    cs:__imp_TracePrintfExA
0x180006a5e  mov     rcx, [rbp+57h+phContext]; hContext
0x180006a62  lea     rax, [rbp+57h+pcchProvider]
0x180006a66  lea     r9, [rbp+57h+szProvider]; szProvider
0x180006a6a  mov     [rsp+100h+mszCards], rax; pcchProvider
0x180006a6f  mov     r8d, 2; dwProviderId
0x180006a75  mov     rdx, rdi; szCardName
0x180006a78  call    cs:__imp_SCardGetCardTypeProviderNameW
0x180006a7e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180006a84  test    eax, eax
0x180006a86  jz      short loc_180006ABA
0x180006a88  cmp     ecx, 0FFFFFFFFh
0x180006a8b  jz      short loc_180006A9F
0x180006a8d  mov     r9d, eax
0x180006a90  lea     r8, aFailedScardget_0; "Failed SCardGetCardTypeProviderName: Er"...
0x180006a97  mov     edx, ebx; dwFlags
0x180006a99  call    cs:__imp_TracePrintfExA
0x180006a9f  xor     ecx, ecx
0x180006aa1  mov     rax, rsi
0x180006aa4  inc     rax
0x180006aa7  cmp     [rdi+rax*2], cx
0x180006aab  jnz     short loc_180006AA4
0x180006aad  lea     rdi, [rdi+rax*2]
0x180006ab1  add     rdi, 2
0x180006ab5  jmp     loc_180006A2F
0x180006aba  cmp     ecx, 0FFFFFFFFh
0x180006abd  jz      short loc_180006AD2
0x180006abf  mov     r9, qword ptr [rbp+57h+szProvider]
0x180006ac3  lea     r8, aProviderNameS; "Provider Name: %S\n"
0x180006aca  mov     edx, ebx; dwFlags
0x180006acc  call    cs:__imp_TracePrintfExA
0x180006ad2  mov     rdx, [rbp+57h+var_A0]; struct _CERT_HASH *
0x180006ad6  mov     r8, r12; struct _CRYPT_KEY_PROV_INFO *
0x180006ad9  mov     rcx, qword ptr [rbp+57h+szProvider]; pszSrc
0x180006add  call    ?GetSmartCardCertificate@@YAHPEAGPEAU_CERT_HASH@@PEAU_CRYPT_KEY_PROV_INFO@@@Z; GetSmartCardCertificate(ushort *,_CERT_HASH *,_CRYPT_KEY_PROV_INFO *)
0x180006ae2  mov     rdx, qword ptr [rbp+57h+szProvider]; pvMem
0x180006ae6  xor     ecx, ecx
0x180006ae8  mov     r15d, eax
0x180006aeb  test    rdx, rdx
0x180006aee  jz      short loc_180006B00
0x180006af0  mov     rcx, [rbp+57h+phContext]; hContext
0x180006af4  call    cs:__imp_SCardFreeMemory
0x180006afa  xor     ecx, ecx
0x180006afc  mov     qword ptr [rbp+57h+szProvider], rcx
0x180006b00  test    r15d, r15d
0x180006b03  jz      short loc_180006AA1
0x180006b05  mov     rdx, rsi
0x180006b08  inc     rdx
0x180006b0b  cmp     [rdi+rdx*2], cx
0x180006b0f  jnz     short loc_180006B08
0x180006b11  lea     rdx, ds:2[rdx*2]; uBytes
0x180006b19  mov     ecx, 40h ; '@'; uFlags
0x180006b1e  call    cs:__imp_LocalAlloc
0x180006b24  xor     ecx, ecx
0x180006b26  mov     [r13+0], rax
0x180006b2a  test    rax, rax
0x180006b2d  jz      short loc_180006B49
0x180006b2f  mov     rdx, rsi
0x180006b32  inc     rdx
0x180006b35  cmp     [rdi+rdx*2], cx
0x180006b39  jnz     short loc_180006B32
0x180006b3b  inc     rdx; cchDest
0x180006b3e  mov     r8, rdi; pszSrc
0x180006b41  mov     rcx, rax; pszDest
0x180006b44  call    StringCchCopyW
0x180006b49  mov     rdx, qword ptr [rbp+57h+var_C0]; pvMem
0x180006b4d  xor     edi, edi
0x180006b4f  test    rdx, rdx
0x180006b52  jz      short loc_180006B62
0x180006b54  mov     rcx, [rbp+57h+phContext]; hContext
0x180006b58  call    cs:__imp_SCardFreeMemory
0x180006b5e  mov     qword ptr [rbp+57h+var_C0], rdi
0x180006b62  test    r15d, r15d
0x180006b65  jz      short loc_180006BCB
0x180006b67  mov     rdx, rsi
0x180006b6a  inc     rdx
0x180006b6d  cmp     [r14+rdx*2], di
0x180006b72  jnz     short loc_180006B6A
0x180006b74  lea     rdx, ds:2[rdx*2]; uBytes
0x180006b7c  mov     ecx, 40h ; '@'; uFlags
0x180006b81  call    cs:__imp_LocalAlloc
0x180006b87  mov     rcx, [rbp+57h+var_98]
0x180006b8b  mov     [rcx], rax
0x180006b8e  test    rax, rax
0x180006b91  jz      short loc_180006C02
0x180006b93  inc     rsi
0x180006b96  cmp     [r14+rsi*2], di
0x180006b9b  jnz     short loc_180006B93
0x180006b9d  lea     rdx, [rsi+1]; cchDest
0x180006ba1  mov     r8, r14; pszSrc
0x180006ba4  mov     rcx, rax; pszDest
0x180006ba7  call    StringCchCopyW
0x180006bac  jmp     short loc_180006C02
0x180006bae  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180006bb4  cmp     ecx, 0FFFFFFFFh
0x180006bb7  jz      short loc_180006BCB
0x180006bb9  mov     r9, r14
0x180006bbc  lea     r8, aNoSmartCardPre; "No Smart card present in Reader: %S"
0x180006bc3  mov     edx, ebx; dwFlags
0x180006bc5  call    cs:__imp_TracePrintfExA
0x180006bcb  mov     rax, rsi
0x180006bce  inc     rax
0x180006bd1  cmp     [r14+rax*2], di
0x180006bd6  jnz     short loc_180006BCE
0x180006bd8  lea     r14, [r14+rax*2]
0x180006bdc  add     r14, 2
0x180006be0  jmp     loc_180006960
0x180006be5  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180006beb  cmp     ecx, 0FFFFFFFFh
0x180006bee  jz      short loc_180006C02
0x180006bf0  lea     r8, aFailedScardlis_0; "Failed SCardListCards: Error: %x"
0x180006bf7  mov     edx, ebx; dwFlags
0x180006bf9  mov     r9d, eax
0x180006bfc  call    cs:__imp_TracePrintfExA
0x180006c02  mov     rdx, qword ptr [rbp+57h+mszReaders]; pvMem
0x180006c06  test    rdx, rdx
0x180006c09  jz      short loc_180006C19
0x180006c0b  mov     rcx, [rbp+57h+phContext]; hContext
0x180006c0f  call    cs:__imp_SCardFreeMemory
0x180006c15  mov     qword ptr [rbp+57h+mszReaders], rdi
0x180006c19  mov     rcx, [rbp+57h+phContext]; hContext
0x180006c1d  test    rcx, rcx
0x180006c20  jz      short loc_180006C28
0x180006c22  call    cs:__imp_SCardReleaseContext
0x180006c28  mov     eax, r15d
0x180006c2b  jmp     short loc_180006C2F
0x180006c2d  xor     eax, eax
0x180006c2f  mov     rcx, [rbp+57h+var_50]
0x180006c33  xor     rcx, rsp; StackCookie
0x180006c36  call    __security_check_cookie
0x180006c3b  add     rsp, 0C8h
0x180006c42  pop     r15
0x180006c44  pop     r14
0x180006c46  pop     r13
0x180006c48  pop     r12
0x180006c4a  pop     rdi
0x180006c4b  pop     rsi
0x180006c4c  pop     rbx
0x180006c4d  pop     rbp
0x180006c4e  retn
```
