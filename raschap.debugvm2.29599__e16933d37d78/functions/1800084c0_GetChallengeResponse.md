# GetChallengeResponse

- ea: `0x1800084c0`
- end: `0x180008932`
- name: `GetChallengeResponse`
- size: `1138`
- prototype: `__int64 __usercall@<rax>(LPSTR lpMultiByteStr@<rcx>, PCSZ Source@<rdx>, int, __int64, __int64, void *, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008cf0`
- `0x18001b060`
- `0x18001b3ec`

## callees

- `0x180003bd0`
- `0x180006a20`
- `0x1800084c0`
- `0x180008938`
- `0x18000b1a0`
- `0x180013b20`

## import_xrefs

- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180008679`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180008679`
- `ntdll!RtlFreeUnicodeString` at `0x1800086df`
- `ntdll!RtlFreeUnicodeString` at `0x18000872f`
- `ntdll!RtlFreeUnicodeString` at `0x180008789`
- `ntdll!RtlFreeUnicodeString` at `0x1800086df`
- `ntdll!RtlFreeUnicodeString` at `0x18000872f`
- `ntdll!RtlFreeUnicodeString` at `0x180008789`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180008828`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180008828`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180008877`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180008877`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800088d7`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800088d7`
- `CRYPTSP!SystemFunction009` at `0x180008707`
- `CRYPTSP!SystemFunction009` at `0x180008707`
- `CRYPTSP!SystemFunction007` at `0x1800086b7`
- `CRYPTSP!SystemFunction007` at `0x1800086b7`

## pseudocode

```c
__int64 __fastcall GetChallengeResponse(
        LPSTR lpMultiByteStr,
        PCSZ Source,
        __int64 a3,
        __int64 a4,
        int a5,
        void *a6,
        __int64 a7,
        void *a8,
        _BYTE *a9,
        __int64 a10,
        __int64 a11)
{
  _QWORD *v14; // rcx
  unsigned int Credentials; // eax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  unsigned __int64 v19; // rbx
  __int64 v20; // rax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  unsigned int v23; // ebx
  __int64 v24; // rax
  HANDLE *v25; // rcx
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  HANDLE *v28; // rcx
  __int64 v29; // rax
  unsigned int v30; // edi
  _UNICODE_STRING Destination; // [rsp+40h] [rbp-488h] BYREF
  HANDLE hToken[2]; // [rsp+50h] [rbp-478h] BYREF
  WCHAR WideCharStr[520]; // [rsp+60h] [rbp-468h] BYREF

  hToken[0] = a6;
  *(_QWORD *)&Destination.Length = a7;
  *a9 = 1;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_dc9258d3638b33007e445a4426f6dbaa_Traceguids);
    v14 = WPP_GLOBAL_Control;
  }
  if ( a5 )
  {
    if ( v14 != &WPP_GLOBAL_Control )
      WPP_SF_(v14[2], 24, WPP_dc9258d3638b33007e445a4426f6dbaa_Traceguids);
    Credentials = GetCredentials(0, a8, a10, a11);
    if ( Credentials )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v17 = 25;
        v18 = Credentials;
LABEL_43:
        WPP_SF_d(v16[2], v17, WPP_dc9258d3638b33007e445a4426f6dbaa_Traceguids, v18);
        return 645;
      }
      return 645;
    }
    goto LABEL_53;
  }
  v19 = -1;
  v20 = -1;
  do
    ++v20;
  while ( lpMultiByteStr[v20] );
  if ( !v20 )
  {
    if ( NtCurrentTeb()->IsImpersonating )
    {
      if ( !RevertToSelf() )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return 645;
        v22 = 28;
        goto LABEL_51;
      }
      v30 = GetCredentials(WideCharStr, a8, a10, a11);
      if ( !ImpersonateLoggedOnUser(hToken[0]) )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return 645;
        v22 = 29;
        goto LABEL_51;
      }
    }
    else
    {
      v30 = GetCredentials(WideCharStr, a8, a10, a11);
    }
    if ( v30 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v17 = 30;
        v18 = v30;
        goto LABEL_43;
      }
      return 645;
    }
    WideCharToMultiByte(0, 0, WideCharStr, -1, lpMultiByteStr, 257, 0, 0);
    lpMultiByteStr[256] = 0;
    goto LABEL_53;
  }
  do
    ++v19;
  while ( Source[v19] );
  if ( v19 <= 0x80 )
  {
    if ( !(unsigned int)GetDESChallengeResponse(Source, a4, *(_QWORD *)&Destination.Length) )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return 645;
      v22 = 26;
LABEL_51:
      WPP_SF_(v21[2], v22, WPP_dc9258d3638b33007e445a4426f6dbaa_Traceguids);
      return 645;
    }
    v14 = WPP_GLOBAL_Control;
  }
  Destination = 0;
  *(_OWORD *)hToken = 0;
  if ( v14 != &WPP_GLOBAL_Control )
    WPP_SF_(v14[2], 43, WPP_dc9258d3638b33007e445a4426f6dbaa_Traceguids);
  if ( !RtlCreateUnicodeStringFromAsciiz(&Destination, Source) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return 645;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_dc9258d3638b33007e445a4426f6dbaa_Traceguids);
    goto LABEL_33;
  }
  v23 = SystemFunction007(&Destination, hToken);
  if ( v23 )
  {
    v24 = 16;
    v25 = hToken;
    do
    {
      *(_BYTE *)v25 = 0;
      v25 = (HANDLE *)((char *)v25 + 1);
      --v24;
    }
    while ( v24 );
    RtlFreeUnicodeString(&Destination);
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return 645;
    v27 = 45;
    goto LABEL_32;
  }
  v23 = SystemFunction009(a4, hToken, a8);
  v28 = hToken;
  v29 = 16;
  if ( v23 )
  {
    do
    {
      *(_BYTE *)v28 = 0;
      v28 = (HANDLE *)((char *)v28 + 1);
      --v29;
    }
    while ( v29 );
    RtlFreeUnicodeString(&Destination);
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return 645;
    v27 = 46;
LABEL_32:
    WPP_SF_d(v26[2], v27, WPP_dc9258d3638b33007e445a4426f6dbaa_Traceguids, v23);
LABEL_33:
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return 645;
    v22 = 27;
    goto LABEL_51;
  }
  do
  {
    *(_BYTE *)v28 = 0;
    v28 = (HANDLE *)((char *)v28 + 1);
    --v29;
  }
  while ( v29 );
  RtlFreeUnicodeString(&Destination);
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return 0;
  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_dc9258d3638b33007e445a4426f6dbaa_Traceguids);
LABEL_53:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_dc9258d3638b33007e445a4426f6dbaa_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x1800084c0  push    rbx
0x1800084c2  push    rbp
0x1800084c3  push    rsi
0x1800084c4  push    rdi
0x1800084c5  push    r12
0x1800084c7  push    r13
0x1800084c9  push    r14
0x1800084cb  push    r15
0x1800084cd  sub     rsp, 488h
0x1800084d4  mov     rax, cs:__security_cookie
0x1800084db  xor     rax, rsp
0x1800084de  mov     [rsp+4C8h+var_58], rax
0x1800084e6  mov     rax, [rsp+4C8h+arg_28]
0x1800084ee  mov     r12, r9
0x1800084f1  mov     rbx, [rsp+4C8h+arg_30]
0x1800084f9  mov     rbp, r8
0x1800084fc  mov     r13, [rsp+4C8h+arg_38]
0x180008504  mov     rdi, rdx
0x180008507  mov     r14, [rsp+4C8h+arg_48]
0x18000850f  mov     rsi, rcx
0x180008512  mov     r15, [rsp+4C8h+arg_50]
0x18000851a  mov     [rsp+4C8h+hToken], rax
0x18000851f  mov     rax, [rsp+4C8h+arg_40]
0x180008527  mov     qword ptr [rsp+4C8h+Destination.Length], rbx
0x18000852c  mov     byte ptr [rax], 1
0x18000852f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008536  lea     rax, WPP_GLOBAL_Control
0x18000853d  cmp     rcx, rax
0x180008540  jz      short loc_180008565
0x180008542  mov     rcx, [rcx+10h]
0x180008546  lea     r8, WPP_dc9258d3638b33007e445a4426f6dbaa_Traceguids
0x18000854d  mov     edx, 17h
0x180008552  call    WPP_SF_
0x180008557  mov     rcx, cs:WPP_GLOBAL_Control
0x18000855e  lea     rax, WPP_GLOBAL_Control
0x180008565  cmp     [rsp+4C8h+arg_20], 0
0x18000856d  jz      short loc_1800085D4
0x18000856f  cmp     rcx, rax
0x180008572  jz      short loc_180008589
0x180008574  mov     rcx, [rcx+10h]
0x180008578  lea     r8, WPP_dc9258d3638b33007e445a4426f6dbaa_Traceguids
0x18000857f  mov     edx, 18h
0x180008584  call    WPP_SF_
0x180008589  mov     [rsp+4C8h+lpDefaultChar], r15; __int64
0x18000858e  mov     r9, rbx
0x180008591  mov     qword ptr [rsp+4C8h+cbMultiByte], r14; __int64
0x180008596  mov     r8, r12
0x180008599  mov     rdx, rbp
0x18000859c  mov     [rsp+4C8h+lpMultiByteStr], r13; void *
0x1800085a1  xor     ecx, ecx; void *
0x1800085a3  call    GetCredentials
0x1800085a8  test    eax, eax
0x1800085aa  jz      loc_1800088E4
0x1800085b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800085b7  lea     rsi, WPP_GLOBAL_Control
0x1800085be  cmp     rcx, rsi
0x1800085c1  jz      loc_18000881E
0x1800085c7  mov     edx, 19h
0x1800085cc  mov     r9d, eax
0x1800085cf  jmp     loc_18000880E
0x1800085d4  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800085db  mov     rax, rbx
0x1800085de  xchg    ax, ax
0x1800085e0  inc     rax
0x1800085e3  cmp     byte ptr [rsi+rax], 0
0x1800085e7  jnz     short loc_1800085E0
0x1800085e9  test    rax, rax
0x1800085ec  jz      loc_1800087B9
0x1800085f2  inc     rbx
0x1800085f5  cmp     byte ptr [rdi+rbx], 0
0x1800085f9  jnz     short loc_1800085F2
0x1800085fb  cmp     rbx, 80h
0x180008602  ja      short loc_180008640
0x180008604  mov     r8, qword ptr [rsp+4C8h+Destination.Length]
0x180008609  mov     rdx, r12
0x18000860c  mov     rcx, rdi
0x18000860f  call    GetDESChallengeResponse
0x180008614  test    eax, eax
0x180008616  jnz     short loc_180008639
0x180008618  mov     rcx, cs:WPP_GLOBAL_Control
0x18000861f  lea     rsi, WPP_GLOBAL_Control
0x180008626  cmp     rcx, rsi
0x180008629  jz      loc_18000881E
0x18000862f  mov     edx, 1Ah
0x180008634  jmp     loc_18000889D
0x180008639  mov     rcx, cs:WPP_GLOBAL_Control
0x180008640  xorps   xmm0, xmm0
0x180008643  xorps   xmm1, xmm1
0x180008646  movups  xmmword ptr [rsp+4C8h+Destination.Length], xmm0
0x18000864b  movups  xmmword ptr [rsp+4C8h+hToken], xmm1
0x180008650  lea     rsi, WPP_GLOBAL_Control
0x180008657  cmp     rcx, rsi
0x18000865a  jz      short loc_180008671
0x18000865c  mov     rcx, [rcx+10h]
0x180008660  lea     r8, WPP_dc9258d3638b33007e445a4426f6dbaa_Traceguids
0x180008667  mov     edx, 2Bh ; '+'
0x18000866c  call    WPP_SF_
0x180008671  mov     rdx, rdi; Source
0x180008674  lea     rcx, [rsp+4C8h+Destination]; Destination
0x180008679  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18000867f  test    al, al
0x180008681  jnz     short loc_1800086AD
0x180008683  mov     rcx, cs:WPP_GLOBAL_Control
0x18000868a  cmp     rcx, rsi
0x18000868d  jz      loc_18000881E
0x180008693  mov     rcx, [rcx+10h]
0x180008697  lea     r8, WPP_dc9258d3638b33007e445a4426f6dbaa_Traceguids
0x18000869e  mov     edx, 2Ch ; ','
0x1800086a3  call    WPP_SF_
0x1800086a8  jmp     loc_18000875D
0x1800086ad  lea     rdx, [rsp+4C8h+hToken]
0x1800086b2  lea     rcx, [rsp+4C8h+Destination]
0x1800086b7  call    cs:__imp_SystemFunction007
0x1800086bd  mov     ebx, eax
0x1800086bf  test    eax, eax
0x1800086c1  jz      short loc_1800086FC
0x1800086c3  mov     eax, 10h
0x1800086c8  lea     rcx, [rsp+4C8h+hToken]
0x1800086cd  mov     byte ptr [rcx], 0
0x1800086d0  lea     rcx, [rcx+1]
0x1800086d4  sub     rax, 1
0x1800086d8  jnz     short loc_1800086CD
0x1800086da  lea     rcx, [rsp+4C8h+Destination]; UnicodeString
0x1800086df  call    cs:__imp_RtlFreeUnicodeString
0x1800086e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086ec  cmp     rcx, rsi
0x1800086ef  jz      loc_18000881E
0x1800086f5  mov     edx, 2Dh ; '-'
0x1800086fa  jmp     short loc_18000874A
0x1800086fc  mov     r8, r13
0x1800086ff  lea     rdx, [rsp+4C8h+hToken]
0x180008704  mov     rcx, r12
0x180008707  call    cs:__imp_SystemFunction009
0x18000870d  mov     ebx, eax
0x18000870f  lea     rcx, [rsp+4C8h+hToken]
0x180008714  test    eax, eax
0x180008716  mov     eax, 10h
0x18000871b  jz      short loc_180008777
0x18000871d  mov     byte ptr [rcx], 0
0x180008720  lea     rcx, [rcx+1]
0x180008724  sub     rax, 1
0x180008728  jnz     short loc_18000871D
0x18000872a  lea     rcx, [rsp+4C8h+Destination]; UnicodeString
0x18000872f  call    cs:__imp_RtlFreeUnicodeString
0x180008735  mov     rcx, cs:WPP_GLOBAL_Control
0x18000873c  cmp     rcx, rsi
0x18000873f  jz      loc_18000881E
0x180008745  mov     edx, 2Eh ; '.'
0x18000874a  mov     rcx, [rcx+10h]
0x18000874e  lea     r8, WPP_dc9258d3638b33007e445a4426f6dbaa_Traceguids
0x180008755  mov     r9d, ebx
0x180008758  call    WPP_SF_d
0x18000875d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008764  cmp     rcx, rsi
0x180008767  jz      loc_18000881E
0x18000876d  mov     edx, 1Bh
0x180008772  jmp     loc_18000889D
0x180008777  mov     byte ptr [rcx], 0
0x18000877a  lea     rcx, [rcx+1]
0x18000877e  sub     rax, 1
0x180008782  jnz     short loc_180008777
0x180008784  lea     rcx, [rsp+4C8h+Destination]; UnicodeString
0x180008789  call    cs:__imp_RtlFreeUnicodeString
0x18000878f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008796  cmp     rcx, rsi
0x180008799  jz      loc_18000890C
0x18000879f  mov     rcx, [rcx+10h]
0x1800087a3  lea     r8, WPP_dc9258d3638b33007e445a4426f6dbaa_Traceguids
0x1800087aa  mov     edx, 33h ; '3'
0x1800087af  call    WPP_SF_
0x1800087b4  jmp     loc_1800088EB
0x1800087b9  mov     eax, gs:179Ch
0x1800087c1  test    eax, eax
0x1800087c3  jnz     short loc_180008828
0x1800087c5  mov     r9, qword ptr [rsp+4C8h+Destination.Length]
0x1800087ca  lea     rcx, [rsp+4C8h+WideCharStr]; void *
0x1800087cf  mov     [rsp+4C8h+lpDefaultChar], r15; __int64
0x1800087d4  mov     r8, r12
0x1800087d7  mov     qword ptr [rsp+4C8h+cbMultiByte], r14; __int64
0x1800087dc  mov     rdx, rbp
0x1800087df  mov     [rsp+4C8h+lpMultiByteStr], r13; void *
0x1800087e4  call    GetCredentials
0x1800087e9  mov     edi, eax
0x1800087eb  test    edi, edi
0x1800087ed  jz      loc_1800088B2
0x1800087f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087fa  lea     rsi, WPP_GLOBAL_Control
0x180008801  cmp     rcx, rsi
0x180008804  jz      short loc_18000881E
0x180008806  mov     edx, 1Eh
0x18000880b  mov     r9d, edi
0x18000880e  mov     rcx, [rcx+10h]
0x180008812  lea     r8, WPP_dc9258d3638b33007e445a4426f6dbaa_Traceguids
0x180008819  call    WPP_SF_d
0x18000881e  mov     eax, 285h
0x180008823  jmp     loc_18000890E
0x180008828  call    cs:__imp_RevertToSelf
0x18000882e  test    eax, eax
0x180008830  jnz     short loc_18000884C
0x180008832  mov     rcx, cs:WPP_GLOBAL_Control
0x180008839  lea     rsi, WPP_GLOBAL_Control
0x180008840  cmp     rcx, rsi
0x180008843  jz      short loc_18000881E
0x180008845  mov     edx, 1Ch
0x18000884a  jmp     short loc_18000889D
0x18000884c  mov     r9, qword ptr [rsp+4C8h+Destination.Length]
0x180008851  lea     rcx, [rsp+4C8h+WideCharStr]; void *
0x180008856  mov     [rsp+4C8h+lpDefaultChar], r15; __int64
0x18000885b  mov     r8, r12
0x18000885e  mov     qword ptr [rsp+4C8h+cbMultiByte], r14; __int64
0x180008863  mov     rdx, rbp
0x180008866  mov     [rsp+4C8h+lpMultiByteStr], r13; void *
0x18000886b  call    GetCredentials
0x180008870  mov     rcx, [rsp+4C8h+hToken]; hToken
0x180008875  mov     edi, eax
0x180008877  call    cs:__imp_ImpersonateLoggedOnUser
0x18000887d  test    eax, eax
0x18000887f  jnz     loc_1800087EB
0x180008885  mov     rcx, cs:WPP_GLOBAL_Control
0x18000888c  lea     rsi, WPP_GLOBAL_Control
0x180008893  cmp     rcx, rsi
0x180008896  jz      short loc_18000881E
0x180008898  mov     edx, 1Dh
0x18000889d  mov     rcx, [rcx+10h]
0x1800088a1  lea     r8, WPP_dc9258d3638b33007e445a4426f6dbaa_Traceguids
0x1800088a8  call    WPP_SF_
0x1800088ad  jmp     loc_18000881E
0x1800088b2  xor     eax, eax
0x1800088b4  lea     r8, [rsp+4C8h+WideCharStr]; lpWideCharStr
0x1800088b9  mov     [rsp+4C8h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x1800088be  mov     r9d, ebx; cchWideChar
0x1800088c1  mov     [rsp+4C8h+lpDefaultChar], rax; lpDefaultChar
0x1800088c6  xor     edx, edx; dwFlags
0x1800088c8  mov     [rsp+4C8h+cbMultiByte], 101h; cbMultiByte
0x1800088d0  xor     ecx, ecx; CodePage
0x1800088d2  mov     [rsp+4C8h+lpMultiByteStr], rsi; lpMultiByteStr
0x1800088d7  call    cs:__imp_WideCharToMultiByte
0x1800088dd  mov     byte ptr [rsi+100h], 0
0x1800088e4  lea     rsi, WPP_GLOBAL_Control
0x1800088eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088f2  cmp     rcx, rsi
0x1800088f5  jz      short loc_18000890C
0x1800088f7  mov     rcx, [rcx+10h]
0x1800088fb  lea     r8, WPP_dc9258d3638b33007e445a4426f6dbaa_Traceguids
0x180008902  mov     edx, 1Fh
0x180008907  call    WPP_SF_
0x18000890c  xor     eax, eax
0x18000890e  mov     rcx, [rsp+4C8h+var_58]
0x180008916  xor     rcx, rsp; StackCookie
0x180008919  call    __security_check_cookie
0x18000891e  add     rsp, 488h
0x180008925  pop     r15
0x180008927  pop     r14
0x180008929  pop     r13
0x18000892b  pop     r12
0x18000892d  pop     rdi
0x18000892e  pop     rsi
0x18000892f  pop     rbp
0x180008930  pop     rbx
0x180008931  retn
```
