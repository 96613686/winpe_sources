# ReadLegacyKeyFile

- ea: `0x180005290`
- end: `0x18000573a`
- name: `ReadLegacyKeyFile`
- size: `1194`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e1d4`
- `0x18000eb0c`
- `0x18002a0c0`
- `0x18002b460`
- `0x18005a688`

## callees

- `0x180005290`
- `0x180005740`
- `0x180005848`
- `0x180005ab4`
- `0x180005d64`
- `0x1800090c0`
- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x18002095c`
- `0x180038970`
- `0x180039bf0`
- `0x1800622e0`
- `0x180062310`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000535e`
- `ntdll!RtlInitUnicodeString` at `0x18000535e`
- `ntdll!RtlAllocateHeap` at `0x180005432`
- `ntdll!RtlAllocateHeap` at `0x180005432`
- `ntdll!RtlFreeAnsiString` at `0x180005478`
- `ntdll!RtlFreeAnsiString` at `0x180005478`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180005377`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180005377`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000548f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000548f`

## string_xrefs

- `0x1800054e1`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x180005599`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x18000561f`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x18000569e`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x1800056cb`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x180005701`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`

## pseudocode

```c
__int64 __fastcall ReadLegacyKeyFile(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        _WORD *a4,
        _DWORD *a5,
        _QWORD *a6,
        _DWORD *a7)
{
  void *v10; // rdi
  int v12; // eax
  int v13; // edx
  int v14; // r8d
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // ebx
  NTSTATUS v20; // eax
  int v21; // edx
  int LegacyUserDirectory; // ebx
  int v23; // r8d
  __int64 v24; // r9
  size_t v25; // rdx
  size_t *v26; // r8
  __int64 v27; // rcx
  __int64 v28; // rax
  size_t v29; // r14
  const wchar_t *Heap; // rax
  int v31; // edx
  size_t v32; // r8
  wchar_t *v34; // rcx
  __int64 v35; // rdx
  int v36; // r8d
  _QWORD *v37; // rcx
  int v38; // eax
  size_t cchToCopy; // [rsp+20h] [rbp-E0h]
  char v40; // [rsp+30h] [rbp-D0h]
  size_t cchDest; // [rsp+48h] [rbp-B8h]
  void *Src; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-A8h] BYREF
  _STRING AnsiString; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD *v45; // [rsp+70h] [rbp-90h]
  _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  wchar_t pszSrc[112]; // [rsp+90h] [rbp-70h] BYREF

  v45 = a7;
  hObject = (HANDLE)-1LL;
  v10 = 0;
  Src = 0;
  AnsiString = 0;
  DestinationString = 0;
  memset_0(pszSrc, 0, 0xDEu);
  if ( !wcscmp_0(*(const wchar_t **)(a1 + 16), L"Microsoft Software Key Storage Provider") )
  {
    *a5 = 1;
    goto LABEL_6;
  }
  v12 = LookupLegacyProviderType(*(wchar_t **)(a1 + 16));
  *a5 = v12;
  v15 = v12 - 1;
  if ( !v15 )
    goto LABEL_6;
  v16 = v15 - 1;
  if ( !v16 )
    goto LABEL_6;
  v17 = v16 - 1;
  if ( !v17 )
  {
LABEL_51:
    v19 = 0;
    goto LABEL_7;
  }
  v18 = v17 - 9;
  if ( v18 )
  {
    v38 = v18 - 1;
    if ( v38 && v38 != 5 )
    {
      LegacyUserDirectory = -2146893804;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v13,
          v14,
          (unsigned int)"Status",
          20,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c",
          180);
      goto LABEL_18;
    }
    goto LABEL_51;
  }
LABEL_6:
  v19 = 1;
LABEL_7:
  RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(a2 + 8));
  v20 = RtlUnicodeStringToAnsiString(&AnsiString, &DestinationString, 1u);
  if ( v20 < 0 )
  {
    DebugTraceError((unsigned int)v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c", 455);
    LegacyUserDirectory = -2146893810;
    goto LABEL_18;
  }
  LegacyUserDirectory = GetLegacyUserDirectory(*(_DWORD *)(a2 + 32), v19, a4, &Src);
  if ( !LegacyUserDirectory )
  {
    v10 = Src;
    LODWORD(cchDest) = 111;
    LegacyUserDirectory = OpenContainerFile(
                            AnsiString.Buffer,
                            Src,
                            *(_DWORD *)(a2 + 32),
                            v24,
                            *(_DWORD *)(a1 + 48),
                            *(_DWORD *)(a1 + 56),
                            a3,
                            &hObject,
                            pszSrc,
                            cchDest);
    if ( LegacyUserDirectory )
    {
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_18;
      v40 = -19;
    }
    else
    {
      v27 = *(_QWORD *)(a2 + 16);
      if ( v27 )
        MSCryptFree(v27);
      v28 = -1;
      do
        ++v28;
      while ( pszSrc[v28] );
      v29 = v28 + 1;
      Heap = (const wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * (v28 + 1));
      *(_QWORD *)(a2 + 16) = Heap;
      if ( !Heap )
      {
        LegacyUserDirectory = -2146893810;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v31,
            v32,
            (unsigned int)"Status",
            14,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c",
            253);
        goto LABEL_18;
      }
      LegacyUserDirectory = StringValidateDestW(Heap, v29, v32);
      if ( LegacyUserDirectory < 0 )
      {
        if ( v29 )
          *v34 = 0;
      }
      else
      {
        LegacyUserDirectory = StringCopyWorkerW_0(v34, v25, v26, pszSrc, cchToCopy);
        if ( LegacyUserDirectory >= 0 )
        {
          LegacyUserDirectory = ReadContainerInfo(hObject, a6, v45);
          if ( LegacyUserDirectory )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v35,
                v36,
                (unsigned int)"Status",
                LegacyUserDirectory,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c",
                20);
            KspCryptAuditKeyFileOperation(0, v35, a2, v10, pszSrc, 2458, LegacyUserDirectory);
          }
          else
          {
            KspCryptAuditKeyFileOperation(1, v35, a2, v10, pszSrc, 2458, 0);
          }
          goto LABEL_18;
        }
      }
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_18;
      v40 = 4;
    }
    WPP_SF_sDsd(
      v37[2],
      v25,
      (_DWORD)v26,
      (unsigned int)"Status",
      LegacyUserDirectory,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c",
      v40);
    goto LABEL_18;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v21,
      v23,
      (unsigned int)"Status",
      LegacyUserDirectory,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c",
      218);
  v10 = Src;
LABEL_18:
  if ( AnsiString.Buffer )
    RtlFreeAnsiString(&AnsiString);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v10 )
    MSCryptFree(v10);
  return (unsigned int)LegacyUserDirectory;
}

```

## disassembly

```asm
0x180005290  mov     [rsp-8+arg_0], rbx
0x180005295  push    rbp
0x180005296  push    rsi
0x180005297  push    rdi
0x180005298  push    r12
0x18000529a  push    r13
0x18000529c  push    r14
0x18000529e  push    r15
0x1800052a0  lea     rbp, [rsp-80h]
0x1800052a5  sub     rsp, 180h
0x1800052ac  mov     rax, cs:__security_cookie
0x1800052b3  xor     rax, rsp
0x1800052b6  mov     [rbp+0B0h+var_40], rax
0x1800052ba  mov     rax, [rbp+0B0h+arg_30]
0x1800052c1  mov     r12d, r8d
0x1800052c4  mov     rbx, [rbp+0B0h+arg_20]
0x1800052cb  mov     rsi, rdx
0x1800052ce  mov     r13, [rbp+0B0h+arg_28]
0x1800052d5  mov     r14, rcx
0x1800052d8  xorps   xmm0, xmm0
0x1800052db  mov     [rsp+1B0h+var_140], rax
0x1800052e0  xorps   xmm1, xmm1
0x1800052e3  mov     [rsp+1B0h+hObject], 0FFFFFFFFFFFFFFFFh
0x1800052ec  xor     edi, edi
0x1800052ee  lea     rcx, [rbp+0B0h+pszSrc]; void *
0x1800052f2  xor     edx, edx; Val
0x1800052f4  mov     [rsp+1B0h+Src], rdi
0x1800052f9  mov     r8d, 0DEh; Size
0x1800052ff  mov     r15, r9
0x180005302  movups  xmmword ptr [rsp+1B0h+AnsiString.Length], xmm0
0x180005307  movups  xmmword ptr [rsp+1B0h+DestinationString.Length], xmm1
0x18000530c  call    memset_0
0x180005311  mov     rcx, [r14+10h]; String1
0x180005315  lea     rdx, aMicrosoftSoftw; "Microsoft Software Key Storage Provider"
0x18000531c  call    wcscmp_0
0x180005321  test    eax, eax
0x180005323  jz      loc_1800054CE
0x180005329  mov     rcx, [r14+10h]; String1
0x18000532d  call    LookupLegacyProviderType
0x180005332  mov     [rbx], eax
0x180005334  sub     eax, 1
0x180005337  jz      short loc_180005350
0x180005339  sub     eax, 1
0x18000533c  jz      short loc_180005350
0x18000533e  sub     eax, 1
0x180005341  jz      loc_1800056F4
0x180005347  sub     eax, 9
0x18000534a  jnz     loc_1800055BB
0x180005350  mov     ebx, 1
0x180005355  mov     rdx, [rsi+8]; SourceString
0x180005359  lea     rcx, [rsp+1B0h+DestinationString]; DestinationString
0x18000535e  call    cs:__imp_RtlInitUnicodeString
0x180005365  nop     dword ptr [rax+rax+00h]
0x18000536a  mov     r8b, 1; AllocateDestinationString
0x18000536d  lea     rdx, [rsp+1B0h+DestinationString]; SourceString
0x180005372  lea     rcx, [rsp+1B0h+AnsiString]; DestinationString
0x180005377  call    cs:__imp_RtlUnicodeStringToAnsiString
0x18000537e  nop     dword ptr [rax+rax+00h]
0x180005383  mov     ecx, eax
0x180005385  test    eax, eax
0x180005387  js      loc_1800056FB
0x18000538d  mov     ecx, [rsi+20h]
0x180005390  lea     r9, [rsp+1B0h+Src]
0x180005395  mov     r8, r15
0x180005398  mov     edx, ebx
0x18000539a  call    GetLegacyUserDirectory
0x18000539f  xor     r15d, r15d
0x1800053a2  mov     ebx, eax
0x1800053a4  test    eax, eax
0x1800053a6  jnz     loc_180005649
0x1800053ac  mov     rdi, [rsp+1B0h+Src]
0x1800053b1  lea     rax, [rbp+0B0h+pszSrc]
0x1800053b5  mov     r8d, [rsi+20h]
0x1800053b9  mov     rdx, rdi; Src
0x1800053bc  mov     rcx, [rsp+1B0h+AnsiString.Buffer]; pszSrc
0x1800053c1  mov     dword ptr [rsp+1B0h+cchDest], 6Fh ; 'o'; cchDest
0x1800053c9  mov     [rsp+1B0h+pszDest], rax; pszDest
0x1800053ce  lea     rax, [rsp+1B0h+hObject]
0x1800053d3  mov     [rsp+1B0h+var_178], rax; __int64
0x1800053d8  mov     eax, [r14+38h]
0x1800053dc  mov     dword ptr [rsp+1B0h+var_180], r12d; int
0x1800053e1  mov     [rsp+1B0h+var_188], eax; int
0x1800053e5  mov     eax, [r14+30h]
0x1800053e9  mov     dword ptr [rsp+1B0h+cchToCopy], eax; int
0x1800053ed  call    OpenContainerFile
0x1800053f2  mov     ebx, eax
0x1800053f4  test    eax, eax
0x1800053f6  jnz     loc_18000566C
0x1800053fc  mov     rcx, [rsi+10h]
0x180005400  test    rcx, rcx
0x180005403  jnz     loc_18000571E
0x180005409  lea     rcx, [rbp+0B0h+pszSrc]
0x18000540d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005411  inc     rax
0x180005414  cmp     [rcx+rax*2], r15w
0x180005419  jnz     short loc_180005411
0x18000541b  mov     rcx, gs:60h
0x180005424  lea     r14, [rax+1]
0x180005428  lea     r8, [r14+r14]; Size
0x18000542c  xor     edx, edx; Flags
0x18000542e  mov     rcx, [rcx+30h]; HeapHandle
0x180005432  call    cs:__imp_RtlAllocateHeap
0x180005439  nop     dword ptr [rax+rax+00h]
0x18000543e  mov     [rsi+10h], rax
0x180005442  mov     rcx, rax; pszDest
0x180005445  test    rax, rax
0x180005448  jnz     loc_18000550A
0x18000544e  mov     ebx, 8009000Eh
0x180005453  mov     rcx, cs:WPP_GLOBAL_Control
0x18000545a  lea     rax, WPP_GLOBAL_Control
0x180005461  cmp     rcx, rax
0x180005464  jz      short loc_18000546C
0x180005466  test    byte ptr [rcx+1Ch], 1
0x18000546a  jnz     short loc_1800054D9
0x18000546c  cmp     [rsp+1B0h+AnsiString.Buffer], r15
0x180005471  jz      short loc_180005484
0x180005473  lea     rcx, [rsp+1B0h+AnsiString]; AnsiString
0x180005478  call    cs:__imp_RtlFreeAnsiString
0x18000547f  nop     dword ptr [rax+rax+00h]
0x180005484  mov     rcx, [rsp+1B0h+hObject]; hObject
0x180005489  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000548d  jz      short loc_18000549B
0x18000548f  call    cs:__imp_CloseHandle
0x180005496  nop     dword ptr [rax+rax+00h]
0x18000549b  test    rdi, rdi
0x18000549e  jnz     loc_1800055AE
0x1800054a4  mov     eax, ebx
0x1800054a6  mov     rcx, [rbp+0B0h+var_40]
0x1800054aa  xor     rcx, rsp; StackCookie
0x1800054ad  call    __security_check_cookie
0x1800054b2  mov     rbx, [rsp+1B0h+arg_0]
0x1800054ba  add     rsp, 180h
0x1800054c1  pop     r15
0x1800054c3  pop     r14
0x1800054c5  pop     r13
0x1800054c7  pop     r12
0x1800054c9  pop     rdi
0x1800054ca  pop     rsi
0x1800054cb  pop     rbp
0x1800054cc  retn
0x1800054ce  mov     dword ptr [rbx], 1
0x1800054d4  jmp     loc_180005350
0x1800054d9  mov     dword ptr [rsp+1B0h+var_180], 1FDh
0x1800054e1  lea     rax, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800054e8  mov     qword ptr [rsp+1B0h+var_188], rax
0x1800054ed  mov     dword ptr [rsp+1B0h+cchToCopy], 8009000Eh
0x1800054f5  mov     rcx, [rcx+10h]
0x1800054f9  lea     r9, aStatus; "Status"
0x180005500  call    WPP_SF_sDsd
0x180005505  jmp     loc_18000546C
0x18000550a  mov     rdx, r14; cchDest
0x18000550d  call    StringValidateDestW
0x180005512  mov     ebx, eax
0x180005514  test    eax, eax
0x180005516  js      loc_180005728
0x18000551c  lea     r9, [rbp+0B0h+pszSrc]; pszSrc
0x180005520  call    StringCopyWorkerW_0
0x180005525  mov     ebx, eax
0x180005527  test    eax, eax
0x180005529  js      short loc_180005570
0x18000552b  mov     r8, [rsp+1B0h+var_140]
0x180005530  mov     rdx, r13
0x180005533  mov     rcx, [rsp+1B0h+hObject]; hFile
0x180005538  call    ReadContainerInfo
0x18000553d  mov     ebx, eax
0x18000553f  test    eax, eax
0x180005541  jnz     loc_1800055F3
0x180005547  mov     dword ptr [rsp+1B0h+var_180], r15d
0x18000554c  lea     ecx, [rax+1]
0x18000554f  lea     rax, [rbp+0B0h+pszSrc]
0x180005553  mov     [rsp+1B0h+var_188], 99Ah
0x18000555b  mov     r8, rsi
0x18000555e  mov     [rsp+1B0h+cchToCopy], rax
0x180005563  mov     r9, rdi
0x180005566  call    KspCryptAuditKeyFileOperation
0x18000556b  jmp     loc_18000546C
0x180005570  mov     rcx, cs:WPP_GLOBAL_Control
0x180005577  lea     rax, WPP_GLOBAL_Control
0x18000557e  cmp     rcx, rax
0x180005581  jz      loc_18000546C
0x180005587  test    byte ptr [rcx+1Ch], 1
0x18000558b  jz      loc_18000546C
0x180005591  mov     dword ptr [rsp+1B0h+var_180], 204h
0x180005599  lea     rax, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800055a0  mov     qword ptr [rsp+1B0h+var_188], rax
0x1800055a5  mov     dword ptr [rsp+1B0h+cchToCopy], ebx
0x1800055a9  jmp     loc_1800054F5
0x1800055ae  mov     rcx, rdi
0x1800055b1  call    MSCryptFree
0x1800055b6  jmp     loc_1800054A4
0x1800055bb  sub     eax, 1
0x1800055be  jz      loc_1800056F4
0x1800055c4  cmp     eax, 5
0x1800055c7  jz      loc_1800056F4
0x1800055cd  mov     ebx, 80090014h
0x1800055d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055d9  lea     rax, WPP_GLOBAL_Control
0x1800055e0  cmp     rcx, rax
0x1800055e3  jz      short loc_1800055EB
0x1800055e5  test    byte ptr [rcx+1Ch], 1
0x1800055e9  jnz     short loc_18000561B
0x1800055eb  xor     r15d, r15d
0x1800055ee  jmp     loc_18000546C
0x1800055f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055fa  lea     rax, WPP_GLOBAL_Control
0x180005601  cmp     rcx, rax
0x180005604  jz      short loc_180005610
0x180005606  test    byte ptr [rcx+1Ch], 1
0x18000560a  jnz     loc_18000569A
0x180005610  mov     dword ptr [rsp+1B0h+var_180], ebx
0x180005614  xor     ecx, ecx
0x180005616  jmp     loc_18000554F
0x18000561b  mov     rcx, [rcx+10h]
0x18000561f  lea     rax, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005626  mov     dword ptr [rsp+1B0h+var_180], 1B4h
0x18000562e  lea     r9, aStatus; "Status"
0x180005635  mov     qword ptr [rsp+1B0h+var_188], rax
0x18000563a  mov     dword ptr [rsp+1B0h+cchToCopy], 80090014h
0x180005642  call    WPP_SF_sDsd
0x180005647  jmp     short loc_1800055EB
0x180005649  mov     rcx, cs:WPP_GLOBAL_Control
0x180005650  lea     rax, WPP_GLOBAL_Control
0x180005657  cmp     rcx, rax
0x18000565a  jz      short loc_180005662
0x18000565c  test    byte ptr [rcx+1Ch], 1
0x180005660  jnz     short loc_1800056C7
0x180005662  mov     rdi, [rsp+1B0h+Src]
0x180005667  jmp     loc_18000546C
0x18000566c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005673  lea     rax, WPP_GLOBAL_Control
0x18000567a  cmp     rcx, rax
0x18000567d  jz      loc_18000546C
0x180005683  test    byte ptr [rcx+1Ch], 1
0x180005687  jz      loc_18000546C
0x18000568d  mov     dword ptr [rsp+1B0h+var_180], 1EDh
0x180005695  jmp     loc_180005599
0x18000569a  mov     rcx, [rcx+10h]
0x18000569e  lea     rax, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800056a5  mov     dword ptr [rsp+1B0h+var_180], 214h
0x1800056ad  lea     r9, aStatus; "Status"
0x1800056b4  mov     qword ptr [rsp+1B0h+var_188], rax
0x1800056b9  mov     dword ptr [rsp+1B0h+cchToCopy], ebx
0x1800056bd  call    WPP_SF_sDsd
0x1800056c2  jmp     loc_180005610
0x1800056c7  mov     rcx, [rcx+10h]
0x1800056cb  lea     rax, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800056d2  mov     dword ptr [rsp+1B0h+var_180], 1DAh
0x1800056da  lea     r9, aStatus; "Status"
0x1800056e1  mov     qword ptr [rsp+1B0h+var_188], rax
0x1800056e6  mov     dword ptr [rsp+1B0h+cchToCopy], ebx
0x1800056ea  call    WPP_SF_sDsd
0x1800056ef  jmp     loc_180005662
0x1800056f4  xor     ebx, ebx
0x1800056f6  jmp     loc_180005355
0x1800056fb  mov     r9d, 1C7h
0x180005701  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005708  lea     rdx, aStatus; "Status"
0x18000570f  call    DebugTraceError
0x180005714  mov     ebx, 8009000Eh
0x180005719  jmp     loc_1800055EB
0x18000571e  call    MSCryptFree
0x180005723  jmp     loc_180005409
0x180005728  test    r14, r14
0x18000572b  jz      loc_180005570
0x180005731  mov     [rcx], r15w
0x180005735  jmp     loc_180005570
```
