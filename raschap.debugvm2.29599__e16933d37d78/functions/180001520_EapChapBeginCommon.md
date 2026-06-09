# EapChapBeginCommon

- ea: `0x180001520`
- end: `0x1800019a6`
- name: `EapChapBeginCommon`
- size: `1158`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180002040`
- `0x180015d20`

## callees

- `0x180001520`
- `0x1800019b0`
- `0x180003bd0`
- `0x180006a20`
- `0x1800072f0`
- `0x180013b20`
- `0x180014610`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180001894`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180001894`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180001775`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180001775`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800016f3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800016f3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800017ac`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800017e5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180001825`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180001864`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800017ac`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800017e5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180001825`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180001864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800016fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000172d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800017b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000186e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800016fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000172d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800017b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000186e`

## pseudocode

```c
DWORD __fastcall EapChapBeginCommon(int a1, int a2, int a3, __int64 a4, _QWORD *a5, __int64 a6)
{
  __int64 v10; // r14
  void *v11; // r10
  int v12; // ecx
  char *v13; // rax
  int v14; // eax
  DWORD Message; // ebx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  const wchar_t *v18; // rcx
  wchar_t *v19; // rax
  wchar_t *v20; // rsi
  const WCHAR *v22; // r8
  bool v23; // zf
  CHAR *v24; // rax
  char v25; // [rsp+40h] [rbp-C0h] BYREF
  char v26; // [rsp+41h] [rbp-BFh] BYREF
  char v27; // [rsp+42h] [rbp-BEh] BYREF
  DWORD ReturnLength[3]; // [rsp+44h] [rbp-BCh] BYREF
  _BYTE v29[16]; // [rsp+50h] [rbp-B0h] BYREF
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+68h] [rbp-98h]
  CHAR *v32; // [rsp+70h] [rbp-90h]
  CHAR *v33; // [rsp+78h] [rbp-88h]
  CHAR *v34; // [rsp+80h] [rbp-80h]
  const unsigned __int16 *v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+90h] [rbp-70h]
  int v37; // [rsp+98h] [rbp-68h]
  int v38; // [rsp+9Ch] [rbp-64h]
  char *v39; // [rsp+A0h] [rbp-60h]
  int v40; // [rsp+A8h] [rbp-58h]
  __int64 v41; // [rsp+B0h] [rbp-50h]
  int v42; // [rsp+B8h] [rbp-48h]
  int v43; // [rsp+BCh] [rbp-44h]
  int v44; // [rsp+C0h] [rbp-40h]
  __int64 v45; // [rsp+C8h] [rbp-38h]
  void *v46; // [rsp+D0h] [rbp-30h]
  int v47; // [rsp+100h] [rbp+0h]
  __int128 v48; // [rsp+144h] [rbp+44h]
  _OWORD TokenInformation[3]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v50; // [rsp+190h] [rbp+90h]
  CHAR v51[432]; // [rsp+1A0h] [rbp+A0h] BYREF
  CHAR v52[272]; // [rsp+350h] [rbp+250h] BYREF
  CHAR MultiByteStr[272]; // [rsp+460h] [rbp+360h] BYREF
  CHAR v54[272]; // [rsp+570h] [rbp+470h] BYREF

  memset_0(v29, 0, 0x108u);
  v25 = 5;
  v26 = -127;
  v27 = -1;
  memset_0(v51, 0, 0x1A8u);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids);
  memset_0(v29, 0, 0x108u);
  v10 = 257;
  memset_0(v54, 0, 0x101u);
  memset_0(MultiByteStr, 0, 0x101u);
  memset_0(v52, 0, 0x101u);
  memset_0(v51, 0, 0x1A8u);
  v11 = *(void **)(a6 + 56);
  v12 = *(_DWORD *)(a6 + 8);
  v42 = *(_DWORD *)(a6 + 48);
  v44 = *(_DWORD *)(a6 + 52);
  v45 = *(_QWORD *)(a6 + 40);
  v47 = *(_DWORD *)(a6 + 64);
  v40 = *(unsigned __int8 *)(a6 + 32);
  v35 = &word_180028D1A;
  v30 = v12;
  v38 = 1;
  v43 = 0;
  v41 = 0;
  v46 = v11;
  v37 = 0;
  if ( a1 == 4 )
  {
    v13 = &v25;
  }
  else
  {
    v13 = &v26;
    if ( a1 != 26 )
      v13 = &v27;
  }
  v39 = v13;
  if ( !a2 || (v14 = *(_DWORD *)(a6 + 4), (v14 & 4) != 0) || (v14 & 0x20) != 0 )
  {
    v18 = *(const wchar_t **)(a6 + 16);
    if ( v18 )
    {
      v19 = wcschr(v18, 0x5Cu);
      v20 = v19;
      if ( v19 )
      {
        *v19 = 0;
        if ( !WideCharToMultiByte(0, 0, *(LPCWCH *)(a6 + 16), -1, v54, 257, 0, 0) )
          return GetLastError();
        *v20 = 92;
        if ( !WideCharToMultiByte(0, 0, v20 + 1, -1, MultiByteStr, 257, 0, 0) )
          return GetLastError();
      }
      else if ( !WideCharToMultiByte(0, 0, *(LPCWCH *)(a6 + 16), -1, MultiByteStr, 257, 0, 0) )
      {
        return GetLastError();
      }
    }
    if ( a1 == 4 )
    {
      v22 = *(const WCHAR **)(a6 + 24);
      if ( v22 && !WideCharToMultiByte(0, 0, v22, -1, v52, 257, 0, 0) )
        return GetLastError();
    }
    else
    {
      _o_strncpy_s(v52, 257, *(_QWORD *)(a4 + 24) + 269LL, 256);
    }
LABEL_29:
    v23 = (*(_BYTE *)(a6 + 4) & 0x20) == 0;
    v34 = v54;
    v32 = MultiByteStr;
    v33 = v52;
    v37 = a3;
    if ( !v23 )
      v31 |= 0x2000000u;
    v48 = *(_OWORD *)(a6 + 128);
    Message = ChapBegin(a5, v29);
    if ( !Message )
    {
      v24 = v52;
      do
      {
        *v24++ = 0;
        --v10;
      }
      while ( v10 );
      if ( v30 )
        return Message;
      Message = ChapMakeMessage(*a5, 0, 0, 0, (__int64)v51, (__int64)v29);
      if ( !Message )
        return Message;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return Message;
      v17 = 14;
      goto LABEL_40;
    }
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v17 = 13;
      goto LABEL_40;
    }
    return Message;
  }
  if ( v12 )
    goto LABEL_29;
  ReturnLength[0] = 0;
  v50 = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  if ( !GetTokenInformation(v11, TokenStatistics, TokenInformation, 0x38u, ReturnLength) )
  {
    Message = GetLastError();
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v17 = 11;
LABEL_40:
      WPP_SF_d(v16[2], v17, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids, Message);
      return Message;
    }
    return Message;
  }
  if ( ReturnLength[0] <= 0x38 )
  {
    v36 = *((_QWORD *)&TokenInformation[0] + 1);
    goto LABEL_29;
  }
  Message = GetLastError();
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v17 = 12;
    goto LABEL_40;
  }
  return Message;
}

```

## disassembly

```asm
0x180001520  mov     [rsp-8+arg_0], rbx
0x180001525  push    rbp
0x180001526  push    rsi
0x180001527  push    rdi
0x180001528  push    r12
0x18000152a  push    r13
0x18000152c  push    r14
0x18000152e  push    r15
0x180001530  lea     rbp, [rsp-590h]
0x180001538  sub     rsp, 690h
0x18000153f  mov     rax, cs:__security_cookie
0x180001546  xor     rax, rsp
0x180001549  mov     [rbp+5C0h+var_40], rax
0x180001550  mov     r12, [rbp+5C0h+arg_20]
0x180001557  mov     r15d, r8d
0x18000155a  mov     rbx, [rbp+5C0h+arg_28]
0x180001561  mov     esi, edx
0x180001563  mov     edi, ecx
0x180001565  xor     edx, edx; Val
0x180001567  mov     r8d, 108h; Size
0x18000156d  lea     rcx, [rsp+6C0h+var_670]; void *
0x180001572  mov     r13, r9
0x180001575  call    memset_0
0x18000157a  xor     edx, edx; Val
0x18000157c  mov     [rsp+6C0h+var_680], 5
0x180001581  mov     r8d, 1A8h; Size
0x180001587  mov     [rsp+6C0h+var_67F], 81h
0x18000158c  lea     rcx, [rbp+5C0h+var_520]; void *
0x180001593  mov     [rsp+6C0h+var_67E], 0FFh
0x180001598  call    memset_0
0x18000159d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800015a4  lea     rax, WPP_GLOBAL_Control
0x1800015ab  cmp     rcx, rax
0x1800015ae  jz      short loc_1800015C5
0x1800015b0  mov     rcx, [rcx+10h]
0x1800015b4  lea     r8, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x1800015bb  mov     edx, 0Ah
0x1800015c0  call    WPP_SF_
0x1800015c5  xor     edx, edx; Val
0x1800015c7  lea     rcx, [rsp+6C0h+var_670]; void *
0x1800015cc  mov     r8d, 108h; Size
0x1800015d2  call    memset_0
0x1800015d7  mov     r14d, 101h
0x1800015dd  lea     rcx, [rbp+5C0h+var_150]; void *
0x1800015e4  mov     r8d, r14d; Size
0x1800015e7  xor     edx, edx; Val
0x1800015e9  call    memset_0
0x1800015ee  mov     r8d, r14d; Size
0x1800015f1  lea     rcx, [rbp+5C0h+MultiByteStr]; void *
0x1800015f8  xor     edx, edx; Val
0x1800015fa  call    memset_0
0x1800015ff  mov     r8d, r14d; Size
0x180001602  lea     rcx, [rbp+5C0h+var_370]; void *
0x180001609  xor     edx, edx; Val
0x18000160b  call    memset_0
0x180001610  xor     edx, edx; Val
0x180001612  lea     rcx, [rbp+5C0h+var_520]; void *
0x180001619  mov     r8d, 1A8h; Size
0x18000161f  call    memset_0
0x180001624  mov     eax, [rbx+30h]
0x180001627  xor     edx, edx
0x180001629  mov     r10, [rbx+38h]
0x18000162d  mov     ecx, [rbx+8]
0x180001630  mov     [rbp+5C0h+var_608], eax
0x180001633  mov     eax, [rbx+34h]
0x180001636  mov     [rbp+5C0h+var_600], eax
0x180001639  mov     rax, [rbx+28h]
0x18000163d  mov     [rbp+5C0h+var_5F8], rax
0x180001641  mov     eax, [rbx+40h]
0x180001644  mov     [rbp+5C0h+var_5C0], eax
0x180001647  movzx   eax, byte ptr [rbx+20h]
0x18000164b  mov     [rbp+5C0h+var_618], eax
0x18000164e  lea     rax, word_180028D1A
0x180001655  mov     [rbp+5C0h+var_638], rax
0x180001659  mov     [rsp+6C0h+var_660], ecx
0x18000165d  mov     [rbp+5C0h+var_624], 1
0x180001664  mov     [rbp+5C0h+var_604], edx
0x180001667  mov     [rbp+5C0h+var_610], rdx
0x18000166b  mov     [rbp+5C0h+var_5F0], r10
0x18000166f  mov     [rbp+5C0h+var_628], edx
0x180001672  cmp     edi, 4
0x180001675  jnz     short loc_18000167E
0x180001677  lea     rax, [rsp+6C0h+var_680]
0x18000167c  jmp     short loc_180001691
0x18000167e  cmp     edi, 1Ah
0x180001681  lea     rdx, [rsp+6C0h+var_67E]
0x180001686  lea     rax, [rsp+6C0h+var_67F]
0x18000168b  cmovnz  rax, rdx
0x18000168f  xor     edx, edx
0x180001691  mov     [rbp+5C0h+var_620], rax
0x180001695  test    esi, esi
0x180001697  jz      loc_180001763
0x18000169d  mov     eax, [rbx+4]
0x1800016a0  test    al, 4
0x1800016a2  jnz     loc_180001763
0x1800016a8  test    al, 20h
0x1800016aa  jnz     loc_180001763
0x1800016b0  test    ecx, ecx
0x1800016b2  jnz     loc_18000189A
0x1800016b8  xorps   xmm0, xmm0
0x1800016bb  mov     [rsp+6C0h+var_67C], edx
0x1800016bf  xor     eax, eax
0x1800016c1  lea     r8, [rbp+5C0h+TokenInformation]; TokenInformation
0x1800016c5  mov     [rbp+5C0h+var_530], rax
0x1800016cc  mov     r9d, 38h ; '8'; TokenInformationLength
0x1800016d2  lea     rax, [rsp+6C0h+var_67C]
0x1800016d7  mov     edx, 0Ah; TokenInformationClass
0x1800016dc  mov     rcx, r10; TokenHandle
0x1800016df  mov     [rsp+6C0h+ReturnLength], rax; ReturnLength
0x1800016e4  movups  [rbp+5C0h+TokenInformation], xmm0
0x1800016e8  movups  [rbp+5C0h+var_550], xmm0
0x1800016ec  movups  [rbp+5C0h+var_540], xmm0
0x1800016f3  call    cs:__imp_GetTokenInformation
0x1800016f9  test    eax, eax
0x1800016fb  jnz     short loc_180001726
0x1800016fd  call    cs:__imp_GetLastError
0x180001703  mov     ebx, eax
0x180001705  mov     rcx, cs:WPP_GLOBAL_Control
0x18000170c  lea     rax, WPP_GLOBAL_Control
0x180001713  cmp     rcx, rax
0x180001716  jz      loc_18000197A
0x18000171c  mov     edx, 0Bh
0x180001721  jmp     loc_180001967
0x180001726  cmp     [rsp+6C0h+var_67C], 38h ; '8'
0x18000172b  jbe     short loc_180001756
0x18000172d  call    cs:__imp_GetLastError
0x180001733  mov     ebx, eax
0x180001735  mov     rcx, cs:WPP_GLOBAL_Control
0x18000173c  lea     rax, WPP_GLOBAL_Control
0x180001743  cmp     rcx, rax
0x180001746  jz      loc_18000197A
0x18000174c  mov     edx, 0Ch
0x180001751  jmp     loc_180001967
0x180001756  mov     rax, qword ptr [rbp+5C0h+TokenInformation+8]
0x18000175a  mov     [rbp+5C0h+var_630], rax
0x18000175e  jmp     loc_18000189A
0x180001763  mov     rcx, [rbx+10h]; Str
0x180001767  test    rcx, rcx
0x18000176a  jz      loc_180001831
0x180001770  mov     edx, 5Ch ; '\'; Ch
0x180001775  call    cs:__imp_wcschr
0x18000177b  xor     edx, edx; dwFlags
0x18000177d  xor     ecx, ecx; CodePage
0x18000177f  mov     rsi, rax
0x180001782  mov     r9d, 0FFFFFFFFh; cchWideChar
0x180001788  test    rax, rax
0x18000178b  jnz     short loc_1800017C1
0x18000178d  mov     r8, [rbx+10h]; lpWideCharStr
0x180001791  lea     rax, [rbp+5C0h+MultiByteStr]
0x180001798  mov     [rsp+6C0h+lpUsedDefaultChar], rcx; lpUsedDefaultChar
0x18000179d  mov     [rsp+6C0h+lpDefaultChar], rcx; lpDefaultChar
0x1800017a2  mov     [rsp+6C0h+cbMultiByte], r14d; cbMultiByte
0x1800017a7  mov     [rsp+6C0h+ReturnLength], rax; lpMultiByteStr
0x1800017ac  call    cs:__imp_WideCharToMultiByte
0x1800017b2  test    eax, eax
0x1800017b4  jnz     short loc_18000182F
0x1800017b6  call    cs:__imp_GetLastError
0x1800017bc  jmp     loc_18000197C
0x1800017c1  xor     eax, eax
0x1800017c3  mov     [rsp+6C0h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x1800017c8  mov     [rsp+6C0h+lpDefaultChar], rax; lpDefaultChar
0x1800017cd  mov     [rsi], ax
0x1800017d0  lea     rax, [rbp+5C0h+var_150]
0x1800017d7  mov     r8, [rbx+10h]; lpWideCharStr
0x1800017db  mov     [rsp+6C0h+cbMultiByte], r14d; cbMultiByte
0x1800017e0  mov     [rsp+6C0h+ReturnLength], rax; lpMultiByteStr
0x1800017e5  call    cs:__imp_WideCharToMultiByte
0x1800017eb  test    eax, eax
0x1800017ed  jz      short loc_1800017B6
0x1800017ef  mov     [rsp+6C0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800017f8  lea     rax, [rbp+5C0h+MultiByteStr]
0x1800017ff  mov     [rsp+6C0h+lpDefaultChar], 0; lpDefaultChar
0x180001808  lea     r8, [rsi+2]; lpWideCharStr
0x18000180c  mov     [rsp+6C0h+cbMultiByte], r14d; cbMultiByte
0x180001811  xor     edx, edx; dwFlags
0x180001813  xor     ecx, ecx; CodePage
0x180001815  mov     [rsp+6C0h+ReturnLength], rax; lpMultiByteStr
0x18000181a  mov     r9d, 0FFFFFFFFh; cchWideChar
0x180001820  mov     word ptr [rsi], 5Ch ; '\'
0x180001825  call    cs:__imp_WideCharToMultiByte
0x18000182b  test    eax, eax
0x18000182d  jz      short loc_18000186E
0x18000182f  xor     edx, edx
0x180001831  cmp     edi, 4
0x180001834  jnz     short loc_180001879
0x180001836  mov     r8, [rbx+18h]; lpWideCharStr
0x18000183a  test    r8, r8
0x18000183d  jz      short loc_18000189A
0x18000183f  mov     [rsp+6C0h+lpUsedDefaultChar], rdx; lpUsedDefaultChar
0x180001844  lea     rax, [rbp+5C0h+var_370]
0x18000184b  mov     [rsp+6C0h+lpDefaultChar], rdx; lpDefaultChar
0x180001850  xor     ecx, ecx; CodePage
0x180001852  mov     [rsp+6C0h+cbMultiByte], r14d; cbMultiByte
0x180001857  xor     edx, edx; dwFlags
0x180001859  mov     r9d, 0FFFFFFFFh; cchWideChar
0x18000185f  mov     [rsp+6C0h+ReturnLength], rax; lpMultiByteStr
0x180001864  call    cs:__imp_WideCharToMultiByte
0x18000186a  test    eax, eax
0x18000186c  jnz     short loc_18000189A
0x18000186e  call    cs:__imp_GetLastError
0x180001874  jmp     loc_18000197C
0x180001879  mov     r8, [r13+18h]
0x18000187d  lea     rcx, [rbp+5C0h+var_370]
0x180001884  add     r8, 10Dh
0x18000188b  mov     r9d, 100h
0x180001891  mov     rdx, r14
0x180001894  call    cs:__imp__o_strncpy_s
0x18000189a  test    byte ptr [rbx+4], 20h
0x18000189e  lea     rax, [rbp+5C0h+var_150]
0x1800018a5  mov     [rbp+5C0h+var_640], rax
0x1800018a9  lea     rax, [rbp+5C0h+MultiByteStr]
0x1800018b0  mov     [rsp+6C0h+var_650], rax
0x1800018b5  lea     rax, [rbp+5C0h+var_370]
0x1800018bc  mov     [rsp+6C0h+var_648], rax
0x1800018c1  mov     [rbp+5C0h+var_628], r15d
0x1800018c5  jz      short loc_1800018CF
0x1800018c7  or      [rsp+6C0h+var_658], 2000000h
0x1800018cf  movups  xmm0, xmmword ptr [rbx+80h]
0x1800018d6  lea     rdx, [rsp+6C0h+var_670]
0x1800018db  mov     rcx, r12
0x1800018de  movups  [rbp+5C0h+var_57C], xmm0
0x1800018e2  call    ChapBegin
0x1800018e7  mov     ebx, eax
0x1800018e9  test    eax, eax
0x1800018eb  jz      short loc_180001907
0x1800018ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800018f4  lea     rax, WPP_GLOBAL_Control
0x1800018fb  cmp     rcx, rax
0x1800018fe  jz      short loc_18000197A
0x180001900  mov     edx, 0Dh
0x180001905  jmp     short loc_180001967
0x180001907  lea     rax, [rbp+5C0h+var_370]
0x18000190e  mov     byte ptr [rax], 0
0x180001911  lea     rax, [rax+1]
0x180001915  sub     r14, 1
0x180001919  jnz     short loc_18000190E
0x18000191b  cmp     [rsp+6C0h+var_660], r14d
0x180001920  jnz     short loc_18000197A
0x180001922  mov     rcx, [r12]
0x180001926  lea     rax, [rsp+6C0h+var_670]
0x18000192b  mov     qword ptr [rsp+6C0h+cbMultiByte], rax
0x180001930  xor     r9d, r9d
0x180001933  lea     rax, [rbp+5C0h+var_520]
0x18000193a  xor     r8d, r8d
0x18000193d  xor     edx, edx
0x18000193f  mov     [rsp+6C0h+ReturnLength], rax
0x180001944  call    ChapMakeMessage
0x180001949  mov     ebx, eax
0x18000194b  test    eax, eax
0x18000194d  jz      short loc_18000197A
0x18000194f  mov     rcx, cs:WPP_GLOBAL_Control
0x180001956  lea     rax, WPP_GLOBAL_Control
0x18000195d  cmp     rcx, rax
0x180001960  jz      short loc_18000197A
0x180001962  mov     edx, 0Eh
0x180001967  mov     rcx, [rcx+10h]
0x18000196b  lea     r8, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x180001972  mov     r9d, ebx
0x180001975  call    WPP_SF_d
0x18000197a  mov     eax, ebx
0x18000197c  mov     rcx, [rbp+5C0h+var_40]
0x180001983  xor     rcx, rsp; StackCookie
0x180001986  call    __security_check_cookie
0x18000198b  mov     rbx, [rsp+6C0h+arg_0]
0x180001993  add     rsp, 690h
0x18000199a  pop     r15
0x18000199c  pop     r14
0x18000199e  pop     r13
0x1800019a0  pop     r12
0x1800019a2  pop     rdi
0x1800019a3  pop     rsi
0x1800019a4  pop     rbp
0x1800019a5  retn
```
