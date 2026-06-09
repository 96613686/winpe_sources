# SslOpenProvider

- ea: `0x180006730`
- end: `0x180006a67`
- name: `SslOpenProvider`
- size: `823`
- prototype: `__int64 __fastcall(_QWORD *, const WCHAR *, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180006730`
- `0x180007ca0`
- `0x180007df4`
- `0x180009cd0`
- `0x18000a770`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x18001f175`
- `0x18001f1b0`
- `0x180020010`

## import_xrefs

- `bcrypt!BCryptResolveProviders` at `0x1800067c8`
- `bcrypt!BCryptResolveProviders` at `0x1800067c8`

## string_xrefs

- `0x180006789`: `Microsoft SSL Protocol Provider`
- `0x180006790`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x1800068fc`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
__int64 __fastcall SslOpenProvider(_QWORD *a1, const WCHAR *a2, int a3)
{
  char *v3; // rbx
  const WCHAR *v5; // r12
  int v6; // edx
  NTSTATUS Provider; // edi
  int v8; // r8d
  char *v9; // rax
  int v10; // edx
  int v11; // r8d
  _QWORD *v12; // rcx
  char pcbBuffer; // [rsp+30h] [rbp-D0h]
  PCRYPT_PROVIDER_REFS ppBuffer; // [rsp+40h] [rbp-C0h] BYREF
  ULONG v16; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v17[512]; // [rsp+50h] [rbp-B0h] BYREF

  v3 = 0;
  v16 = 512;
  ppBuffer = (PCRYPT_PROVIDER_REFS)v17;
  if ( !a1 || a3 )
  {
    Provider = -1073741811;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return NormalizeNteStatus((unsigned int)Provider);
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
      163);
    goto LABEL_14;
  }
  v5 = L"Microsoft SSL Protocol Provider";
  if ( a2 )
    v5 = a2;
  do
  {
    Provider = BCryptResolveProviders(0, 0x10002u, 0, v5, 1u, 0, &v16, &ppBuffer);
    if ( Provider != -1073741789 )
      break;
    if ( ppBuffer != (PCRYPT_PROVIDER_REFS)v17 )
      MSCryptFree(ppBuffer);
    ppBuffer = (PCRYPT_PROVIDER_REFS)SafeAllocaAllocateFromHeap(v16);
    if ( !ppBuffer )
    {
      Provider = -1073741801;
      DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 3028);
    }
  }
  while ( ppBuffer );
  if ( Provider < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_14;
    pcbBuffer = -37;
LABEL_13:
    WPP_SF_sDsd(
      v12[2],
      v6,
      v8,
      (unsigned int)"Status",
      Provider,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
      pcbBuffer);
    goto LABEL_14;
  }
  v9 = (char *)SafeAllocaAllocateFromHeap(432);
  v3 = v9;
  if ( !v9 )
  {
    Provider = -1073741801;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        v11,
        (unsigned int)"Status",
        23,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        240);
    goto LABEL_14;
  }
  memset_0(v9, 0, 0x1B0u);
  Provider = LoadProviderEx(*ppBuffer->rgpProviders, v3 + 32, 392, v3 + 24, v3 + 32);
  if ( Provider < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_14;
    pcbBuffer = 5;
    goto LABEL_13;
  }
  Provider = (*((__int64 (__fastcall **)(char *, const WCHAR *, _QWORD))v3 + 25))(v3 + 424, v5, 0);
  if ( Provider < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_14;
    pcbBuffer = 21;
    goto LABEL_13;
  }
  *(_DWORD *)v3 = 432;
  *(_QWORD *)(v3 + 4) = 1145324609;
  *((_DWORD *)v3 + 4) = 1;
  *((_DWORD *)v3 + 3) = 0;
  *a1 = v3;
  v3 = 0;
  Provider = 0;
LABEL_14:
  if ( ppBuffer && ppBuffer != (PCRYPT_PROVIDER_REFS)v17 )
    MSCryptFree(ppBuffer);
  if ( v3 )
  {
    if ( *((_QWORD *)v3 + 3) )
      UnloadProvider();
    MSCryptFree(v3);
  }
  return NormalizeNteStatus((unsigned int)Provider);
}

```

## disassembly

```asm
0x180006730  mov     [rsp-8+arg_18], rbx
0x180006735  push    rbp
0x180006736  push    rdi
0x180006737  push    r12
0x180006739  push    r13
0x18000673b  push    r15
0x18000673d  lea     rbp, [rsp-160h]
0x180006745  sub     rsp, 260h
0x18000674c  mov     rax, cs:__security_cookie
0x180006753  xor     rax, rsp
0x180006756  mov     [rbp+180h+var_30], rax
0x18000675d  xor     ebx, ebx
0x18000675f  mov     [rsp+280h+var_238], 200h
0x180006767  lea     rax, [rsp+280h+var_230]
0x18000676c  mov     r13, rcx
0x18000676f  mov     [rsp+280h+var_240], rax
0x180006774  test    rcx, rcx
0x180006777  jz      loc_1800068D6
0x18000677d  test    r8d, r8d
0x180006780  jnz     loc_1800068D6
0x180006786  test    rdx, rdx
0x180006789  lea     r12, aMicrosoftSslPr; "Microsoft SSL Protocol Provider"
0x180006790  lea     r15, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006797  cmovnz  r12, rdx
0x18000679b  lea     rax, [rsp+280h+var_240]
0x1800067a0  mov     r9, r12; pszProvider
0x1800067a3  mov     [rsp+280h+ppBuffer], rax; ppBuffer
0x1800067a8  xor     r8d, r8d; pszFunction
0x1800067ab  lea     rax, [rsp+280h+var_238]
0x1800067b0  mov     edx, 10002h; dwInterface
0x1800067b5  mov     [rsp+280h+pcbBuffer], rax; pcbBuffer
0x1800067ba  xor     ecx, ecx; pszContext
0x1800067bc  mov     [rsp+280h+dwFlags], ebx; dwFlags
0x1800067c0  mov     [rsp+280h+dwMode], 1; dwMode
0x1800067c8  call    cs:__imp_BCryptResolveProviders
0x1800067ce  mov     edi, eax
0x1800067d0  cmp     eax, 0C0000023h
0x1800067d5  jz      loc_1800069C4
0x1800067db  test    edi, edi
0x1800067dd  js      loc_1800069F6
0x1800067e3  mov     edi, 1B0h
0x1800067e8  mov     ecx, edi
0x1800067ea  call    SafeAllocaAllocateFromHeap
0x1800067ef  mov     rbx, rax
0x1800067f2  test    rax, rax
0x1800067f5  jz      loc_180006956
0x1800067fb  mov     r8d, edi; Size
0x1800067fe  xor     edx, edx; Val
0x180006800  mov     rcx, rax; void *
0x180006803  call    memset_0
0x180006808  mov     rax, [rsp+280h+var_240]
0x18000680d  lea     rdx, [rbx+20h]
0x180006811  lea     r9, [rbx+18h]
0x180006815  mov     qword ptr [rsp+280h+dwMode], rdx
0x18000681a  lea     r8d, [rdi-28h]
0x18000681e  mov     rcx, [rax+8]
0x180006822  mov     rcx, [rcx]
0x180006825  call    LoadProviderEx
0x18000682a  mov     edi, eax
0x18000682c  test    eax, eax
0x18000682e  js      loc_180006996
0x180006834  mov     rax, [rbx+0C8h]
0x18000683b  lea     rcx, [rbx+1A8h]
0x180006842  xor     r8d, r8d
0x180006845  mov     rdx, r12
0x180006848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000684d  mov     edi, eax
0x18000684f  test    eax, eax
0x180006851  jns     loc_180006915
0x180006857  mov     rcx, cs:WPP_GLOBAL_Control
0x18000685e  lea     rax, WPP_GLOBAL_Control
0x180006865  cmp     rcx, rax
0x180006868  jz      short loc_180006891
0x18000686a  test    byte ptr [rcx+1Ch], 1
0x18000686e  jz      short loc_180006891
0x180006870  mov     dword ptr [rsp+280h+pcbBuffer], 0C15h
0x180006878  mov     qword ptr [rsp+280h+dwFlags], r15
0x18000687d  mov     [rsp+280h+dwMode], edi
0x180006881  mov     rcx, [rcx+10h]
0x180006885  lea     r9, aStatus; "Status"
0x18000688c  call    WPP_SF_sDsd
0x180006891  mov     rcx, [rsp+280h+var_240]
0x180006896  test    rcx, rcx
0x180006899  jnz     loc_18000693E
0x18000689f  test    rbx, rbx
0x1800068a2  jnz     loc_180006A4C
0x1800068a8  mov     ecx, edi
0x1800068aa  call    NormalizeNteStatus
0x1800068af  mov     rcx, [rbp+180h+var_30]
0x1800068b6  xor     rcx, rsp; StackCookie
0x1800068b9  call    __security_check_cookie
0x1800068be  mov     rbx, [rsp+280h+arg_18]
0x1800068c6  add     rsp, 260h
0x1800068cd  pop     r15
0x1800068cf  pop     r13
0x1800068d1  pop     r12
0x1800068d3  pop     rdi
0x1800068d4  pop     rbp
0x1800068d5  retn
0x1800068d6  mov     edi, 0C000000Dh
0x1800068db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068e2  lea     rax, WPP_GLOBAL_Control
0x1800068e9  cmp     rcx, rax
0x1800068ec  jz      short loc_1800068A8
0x1800068ee  test    byte ptr [rcx+1Ch], 1
0x1800068f2  jz      short loc_1800068A8
0x1800068f4  mov     dword ptr [rsp+280h+pcbBuffer], 0BA3h
0x1800068fc  lea     r15, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006903  mov     qword ptr [rsp+280h+dwFlags], r15
0x180006908  mov     [rsp+280h+dwMode], 0C000000Dh
0x180006910  jmp     loc_180006881
0x180006915  mov     dword ptr [rbx], 1B0h
0x18000691b  mov     qword ptr [rbx+4], 44444441h
0x180006923  mov     dword ptr [rbx+10h], 1
0x18000692a  mov     dword ptr [rbx+0Ch], 0
0x180006931  mov     [r13+0], rbx
0x180006935  xor     ebx, ebx
0x180006937  xor     edi, edi
0x180006939  jmp     loc_180006891
0x18000693e  lea     rax, [rsp+280h+var_230]
0x180006943  cmp     rcx, rax
0x180006946  jz      loc_18000689F
0x18000694c  call    MSCryptFree
0x180006951  jmp     loc_18000689F
0x180006956  mov     edi, 0C0000017h
0x18000695b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006962  lea     rax, WPP_GLOBAL_Control
0x180006969  cmp     rcx, rax
0x18000696c  jz      loc_180006891
0x180006972  test    byte ptr [rcx+1Ch], 1
0x180006976  jz      loc_180006891
0x18000697c  mov     dword ptr [rsp+280h+pcbBuffer], 0BF0h
0x180006984  mov     qword ptr [rsp+280h+dwFlags], r15
0x180006989  mov     [rsp+280h+dwMode], 0C0000017h
0x180006991  jmp     loc_180006881
0x180006996  mov     rcx, cs:WPP_GLOBAL_Control
0x18000699d  lea     rax, WPP_GLOBAL_Control
0x1800069a4  cmp     rcx, rax
0x1800069a7  jz      loc_180006891
0x1800069ad  test    byte ptr [rcx+1Ch], 1
0x1800069b1  jz      loc_180006891
0x1800069b7  mov     dword ptr [rsp+280h+pcbBuffer], 0C05h
0x1800069bf  jmp     loc_180006878
0x1800069c4  mov     rcx, [rsp+280h+var_240]
0x1800069c9  lea     rax, [rsp+280h+var_230]
0x1800069ce  cmp     rcx, rax
0x1800069d1  jnz     short loc_180006A24
0x1800069d3  mov     ecx, [rsp+280h+var_238]
0x1800069d7  call    SafeAllocaAllocateFromHeap
0x1800069dc  mov     [rsp+280h+var_240], rax
0x1800069e1  test    rax, rax
0x1800069e4  jz      short loc_180006A2B
0x1800069e6  cmp     [rsp+280h+var_240], rbx
0x1800069eb  jz      loc_1800067DB
0x1800069f1  jmp     loc_18000679B
0x1800069f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069fd  lea     rax, WPP_GLOBAL_Control
0x180006a04  cmp     rcx, rax
0x180006a07  jz      loc_180006891
0x180006a0d  test    byte ptr [rcx+1Ch], 1
0x180006a11  jz      loc_180006891
0x180006a17  mov     dword ptr [rsp+280h+pcbBuffer], 0BDBh
0x180006a1f  jmp     loc_180006878
0x180006a24  call    MSCryptFree
0x180006a29  jmp     short loc_1800069D3
0x180006a2b  mov     r9d, 0BD4h
0x180006a31  lea     rdx, aStatus; "Status"
0x180006a38  mov     r8, r15
0x180006a3b  mov     ecx, 0C0000017h
0x180006a40  mov     edi, 0C0000017h
0x180006a45  call    DebugTraceError
0x180006a4a  jmp     short loc_1800069E6
0x180006a4c  mov     rcx, [rbx+18h]
0x180006a50  test    rcx, rcx
0x180006a53  jz      short loc_180006A5A
0x180006a55  call    UnloadProvider
0x180006a5a  mov     rcx, rbx
0x180006a5d  call    MSCryptFree
0x180006a62  jmp     loc_1800068A8
```
