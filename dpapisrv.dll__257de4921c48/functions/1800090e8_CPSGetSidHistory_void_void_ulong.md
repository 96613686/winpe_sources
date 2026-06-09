# CPSGetSidHistory(void *,void * * *,ulong *)

- ea: `0x1800090e8`
- end: `0x1800095c7`
- name: `?CPSGetSidHistory@@YAKPEAXPEAPEAPEAXPEAK@Z`
- size: `1247`
- prototype: `__int64 __fastcall(HANDLE *, void ***, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008498`
- `0x1800193c0`
- `0x18002e130`

## callees

- `0x180007f10`
- `0x1800090e8`
- `0x18001d810`
- `0x18001eb8c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000914b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009196`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800093df`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009518`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000914b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009196`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800093df`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009518`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800091ad`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800091d7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009292`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800092f6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800091ad`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800091d7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009292`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800092f6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800092a9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000930e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800092a9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000930e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009335`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000952c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009335`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000952c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009370`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800094ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800095ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009370`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800094ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800095ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009205`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800093ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800094b5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009205`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800093ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800094b5`

## string_xrefs

- `0x18000943b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x18000947f`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x1800094d7`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180009558`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180009571`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`

## pseudocode

```c
__int64 __fastcall CPSGetSidHistory(HANDLE *a1, void ***a2, unsigned int *a3)
{
  unsigned int v5; // edi
  DWORD v6; // esi
  PSID *v7; // r15
  HANDLE v8; // rcx
  unsigned int *v9; // r14
  unsigned int v10; // ebx
  DWORD i; // r12d
  __int64 v12; // rbx
  void **v13; // rax
  void **v15; // rdi
  DWORD LengthSid; // eax
  __int64 v17; // r13
  char *v18; // r13
  unsigned int v19; // edi
  unsigned int v20; // r15d
  void ***v21; // rsi
  __int64 v22; // rcx
  DWORD v23; // eax
  __int64 v24; // rbx
  int v25; // edx
  int v26; // edx
  DWORD v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // r9
  char v31; // [rsp+30h] [rbp-D0h]
  DWORD TokenInformationLength; // [rsp+40h] [rbp-C0h] BYREF
  DWORD LastError; // [rsp+44h] [rbp-BCh]
  DWORD ReturnLength; // [rsp+48h] [rbp-B8h] BYREF
  int v35; // [rsp+4Ch] [rbp-B4h]
  void ***v36; // [rsp+50h] [rbp-B0h]
  PSID *v37; // [rsp+58h] [rbp-A8h]
  _BYTE TokenInformation[256]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE hMem[256]; // [rsp+160h] [rbp+60h] BYREF

  v36 = a2;
  TokenInformationLength = 256;
  v5 = 1;
  if ( GetTokenInformation(a1[3], TokenUser, TokenInformation, 0x100u, &TokenInformationLength) )
  {
    v6 = 0;
    v7 = (PSID *)TokenInformation;
    LastError = 0;
    v37 = (PSID *)TokenInformation;
    goto LABEL_3;
  }
  v9 = 0;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError != 122 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        v25,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwLastError",
        LastError,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
        24);
    goto LABEL_25;
  }
  v37 = (PSID *)LocalAlloc(0, TokenInformationLength);
  v7 = v37;
  if ( v37 )
  {
    if ( !GetTokenInformation(a1[3], TokenUser, v37, TokenInformationLength, &TokenInformationLength) )
    {
      v6 = GetLastError();
      v29 = v6;
      v30 = 2611;
LABEL_44:
      DebugTraceError(v29, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", v30);
      goto LABEL_12;
    }
LABEL_3:
    v8 = a1[3];
    TokenInformationLength = 256;
    v9 = (unsigned int *)hMem;
    if ( GetTokenInformation(v8, TokenGroups, hMem, 0x100u, &TokenInformationLength) )
    {
LABEL_4:
      v10 = 0;
      for ( i = GetLengthSid(*v7); v10 < *v9; ++v10 )
      {
        if ( (v9[4 * v10 + 4] & 4) != 0 )
        {
          i += GetLengthSid(*(PSID *)&v9[4 * v10 + 2]);
          ++v5;
        }
      }
      *a3 = v5;
      v12 = v5;
      v13 = (void **)LocalAlloc(0, v12 * 8 + i);
      *v36 = v13;
      if ( v13 )
      {
        v15 = &v13[v12];
        *v13 = &v13[v12];
        LengthSid = GetLengthSid(*v7);
        v17 = LengthSid;
        CopySid(LengthSid, v15, *v7);
        v18 = (char *)v15 + v17;
        v35 = 1;
        v19 = 0;
        if ( *v9 )
        {
          v20 = v35;
          v21 = v36;
          do
          {
            if ( (v9[4 * v19 + 4] & 4) != 0 )
            {
              v22 = v20++;
              (*v21)[v22] = v18;
              v23 = GetLengthSid(*(PSID *)&v9[4 * v19 + 2]);
              v24 = v23;
              CopySid(v23, v18, *(PSID *)&v9[4 * v19 + 2]);
              v18 += v24;
            }
            ++v19;
          }
          while ( v19 < *v9 );
          v6 = LastError;
          v7 = v37;
        }
      }
      else
      {
        v6 = 8;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_sDsd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            WPP_GLOBAL_Control,
            (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
            (unsigned int)"dwLastError",
            8,
            (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
            161);
      }
    }
    else
    {
      v6 = GetLastError();
      if ( v6 == 122 )
      {
        v27 = TokenInformationLength;
        v6 = 0;
        LastError = 0;
        while ( 1 )
        {
          ReturnLength = 0;
          v9 = (unsigned int *)LocalAlloc(0, v27);
          if ( !v9 )
          {
            v29 = 8;
            v30 = 2654;
            v6 = 8;
            goto LABEL_44;
          }
          if ( GetTokenInformation(a1[3], TokenGroups, v9, TokenInformationLength, &ReturnLength) )
            goto LABEL_4;
          LastError = GetLastError();
          v6 = LastError;
          if ( LastError != 122 )
            break;
          if ( ReturnLength <= TokenInformationLength )
            goto LABEL_12;
          LocalFree(v9);
          v27 = ReturnLength;
          TokenInformationLength = ReturnLength;
        }
        v28 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v31 = 110;
          goto LABEL_34;
        }
      }
      else
      {
        v28 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v31 = 77;
LABEL_34:
          WPP_SF_sDsd(
            *(_QWORD *)(v28 + 16),
            v26,
            (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
            (unsigned int)"dwLastError",
            v6,
            (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
            v31);
        }
      }
    }
LABEL_12:
    if ( TokenInformation == (_BYTE *)v7 )
      goto LABEL_13;
    goto LABEL_40;
  }
  v6 = 8;
  DebugTraceError(8, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", 2596);
LABEL_40:
  LocalFree(v7);
LABEL_13:
  if ( hMem != (_BYTE *)v9 )
LABEL_25:
    LocalFree(v9);
  return v6;
}

```

## disassembly

```asm
0x1800090e8  mov     [rsp-8+arg_18], rbx
0x1800090ed  push    rbp
0x1800090ee  push    rsi
0x1800090ef  push    rdi
0x1800090f0  push    r12
0x1800090f2  push    r13
0x1800090f4  push    r14
0x1800090f6  push    r15
0x1800090f8  lea     rbp, [rsp-170h]
0x180009100  sub     rsp, 270h
0x180009107  mov     rax, cs:__security_cookie
0x18000910e  xor     rax, rsp
0x180009111  mov     [rbp+1A0h+var_40], rax
0x180009118  mov     r12d, 100h
0x18000911e  mov     [rsp+2A0h+var_250], rdx
0x180009123  mov     r13, r8
0x180009126  mov     [rsp+2A0h+TokenInformationLength], r12d
0x18000912b  mov     rbx, rcx
0x18000912e  lea     rax, [rsp+2A0h+TokenInformationLength]
0x180009133  mov     rcx, [rcx+18h]; TokenHandle
0x180009137  lea     r8, [rsp+2A0h+TokenInformation]; TokenInformation
0x18000913c  mov     edi, 1
0x180009141  mov     [rsp+2A0h+ReturnLength], rax; ReturnLength
0x180009146  mov     r9d, r12d; TokenInformationLength
0x180009149  mov     edx, edi; TokenInformationClass
0x18000914b  call    cs:__imp_GetTokenInformation
0x180009152  nop     dword ptr [rax+rax+00h]
0x180009157  test    eax, eax
0x180009159  jz      loc_180009332
0x18000915f  xor     esi, esi
0x180009161  lea     r15, [rsp+2A0h+TokenInformation]
0x180009166  mov     [rsp+2A0h+var_25C], esi
0x18000916a  mov     [rsp+2A0h+var_248], r15
0x18000916f  mov     rcx, [rbx+18h]; TokenHandle
0x180009173  lea     rax, [rsp+2A0h+TokenInformationLength]
0x180009178  mov     [rsp+2A0h+TokenInformationLength], r12d
0x18000917d  lea     r8, [rbp+1A0h+hMem]; TokenInformation
0x180009181  mov     r9d, r12d; TokenInformationLength
0x180009184  mov     [rsp+2A0h+ReturnLength], rax; ReturnLength
0x180009189  mov     r12d, 2
0x18000918f  lea     r14, [rbp+1A0h+hMem]
0x180009193  mov     edx, r12d; TokenInformationClass
0x180009196  call    cs:__imp_GetTokenInformation
0x18000919d  nop     dword ptr [rax+rax+00h]
0x1800091a2  test    eax, eax
0x1800091a4  jz      loc_180009381
0x1800091aa  mov     rcx, [r15]; pSid
0x1800091ad  call    cs:__imp_GetLengthSid
0x1800091b4  nop     dword ptr [rax+rax+00h]
0x1800091b9  xor     ebx, ebx
0x1800091bb  mov     r12d, eax
0x1800091be  cmp     [r14], ebx
0x1800091c1  jbe     short loc_1800091EF
0x1800091c3  mov     edx, ebx
0x1800091c5  add     rdx, rdx
0x1800091c8  mov     ecx, [r14+rdx*8+10h]
0x1800091cd  test    cl, 4
0x1800091d0  jz      short loc_1800091E8
0x1800091d2  mov     rcx, [r14+rdx*8+8]; pSid
0x1800091d7  call    cs:__imp_GetLengthSid
0x1800091de  nop     dword ptr [rax+rax+00h]
0x1800091e3  add     r12d, eax
0x1800091e6  inc     edi
0x1800091e8  inc     ebx
0x1800091ea  cmp     ebx, [r14]
0x1800091ed  jb      short loc_1800091C3
0x1800091ef  mov     eax, edi
0x1800091f1  xor     ecx, ecx; uFlags
0x1800091f3  mov     edx, r12d
0x1800091f6  mov     [r13+0], edi
0x1800091fa  lea     rbx, ds:0[rax*8]
0x180009202  add     rdx, rbx; uBytes
0x180009205  call    cs:__imp_LocalAlloc
0x18000920c  nop     dword ptr [rax+rax+00h]
0x180009211  mov     rcx, [rsp+2A0h+var_250]
0x180009216  mov     [rcx], rax
0x180009219  test    rax, rax
0x18000921c  jnz     short loc_180009288
0x18000921e  lea     ecx, [rax+8]
0x180009221  mov     esi, ecx
0x180009223  mov     rdx, cs:WPP_GLOBAL_Control
0x18000922a  lea     rax, WPP_GLOBAL_Control
0x180009231  cmp     rdx, rax
0x180009234  jz      short loc_180009240
0x180009236  test    byte ptr [rdx+1Ch], 1
0x18000923a  jnz     loc_180009569
0x180009240  lea     rax, [rsp+2A0h+TokenInformation]
0x180009245  cmp     rax, r15
0x180009248  jnz     loc_1800094EC
0x18000924e  lea     rax, [rbp+1A0h+hMem]
0x180009252  cmp     rax, r14
0x180009255  jnz     loc_18000936D
0x18000925b  mov     eax, esi
0x18000925d  mov     rcx, [rbp+1A0h+var_40]
0x180009264  xor     rcx, rsp; StackCookie
0x180009267  call    __security_check_cookie
0x18000926c  mov     rbx, [rsp+2A0h+arg_18]
0x180009274  add     rsp, 270h
0x18000927b  pop     r15
0x18000927d  pop     r14
0x18000927f  pop     r13
0x180009281  pop     r12
0x180009283  pop     rdi
0x180009284  pop     rsi
0x180009285  pop     rbp
0x180009286  retn
0x180009288  lea     rdi, [rbx+rax]
0x18000928c  mov     [rax], rdi
0x18000928f  mov     rcx, [r15]; pSid
0x180009292  call    cs:__imp_GetLengthSid
0x180009299  nop     dword ptr [rax+rax+00h]
0x18000929e  mov     r8, [r15]; pSourceSid
0x1800092a1  mov     rdx, rdi; pDestinationSid
0x1800092a4  mov     ecx, eax; nDestinationSidLength
0x1800092a6  mov     r13d, eax
0x1800092a9  call    cs:__imp_CopySid
0x1800092b0  nop     dword ptr [rax+rax+00h]
0x1800092b5  add     r13, rdi
0x1800092b8  mov     [rsp+2A0h+var_254], 1
0x1800092c0  xor     edi, edi
0x1800092c2  cmp     [r14], edi
0x1800092c5  jbe     loc_180009240
0x1800092cb  mov     r15d, [rsp+2A0h+var_254]
0x1800092d0  mov     rsi, [rsp+2A0h+var_250]
0x1800092d5  mov     r12d, edi
0x1800092d8  add     r12, r12
0x1800092db  mov     eax, [r14+r12*8+10h]
0x1800092e0  test    al, 4
0x1800092e2  jz      short loc_18000931D
0x1800092e4  mov     rax, [rsi]
0x1800092e7  mov     ecx, r15d
0x1800092ea  inc     r15d
0x1800092ed  mov     [rax+rcx*8], r13
0x1800092f1  mov     rcx, [r14+r12*8+8]; pSid
0x1800092f6  call    cs:__imp_GetLengthSid
0x1800092fd  nop     dword ptr [rax+rax+00h]
0x180009302  mov     r8, [r14+r12*8+8]; pSourceSid
0x180009307  mov     rdx, r13; pDestinationSid
0x18000930a  mov     ecx, eax; nDestinationSidLength
0x18000930c  mov     ebx, eax
0x18000930e  call    cs:__imp_CopySid
0x180009315  nop     dword ptr [rax+rax+00h]
0x18000931a  add     r13, rbx
0x18000931d  inc     edi
0x18000931f  cmp     edi, [r14]
0x180009322  jb      short loc_1800092D5
0x180009324  mov     esi, [rsp+2A0h+var_25C]
0x180009328  mov     r15, [rsp+2A0h+var_248]
0x18000932d  jmp     loc_180009240
0x180009332  xor     r14d, r14d
0x180009335  call    cs:__imp_GetLastError
0x18000933c  nop     dword ptr [rax+rax+00h]
0x180009341  mov     [rsp+2A0h+var_25C], eax
0x180009345  mov     esi, eax
0x180009347  cmp     eax, 7Ah ; 'z'
0x18000934a  jz      loc_1800094AF
0x180009350  mov     rcx, cs:WPP_GLOBAL_Control
0x180009357  lea     rax, WPP_GLOBAL_Control
0x18000935e  cmp     rcx, rax
0x180009361  jz      short loc_18000936D
0x180009363  test    [rcx+1Ch], dil
0x180009367  jnz     loc_18000947B
0x18000936d  mov     rcx, r14; hMem
0x180009370  call    cs:__imp_LocalFree
0x180009377  nop     dword ptr [rax+rax+00h]
0x18000937c  jmp     loc_18000925B
0x180009381  call    cs:__imp_GetLastError
0x180009388  nop     dword ptr [rax+rax+00h]
0x18000938d  mov     esi, eax
0x18000938f  cmp     eax, 7Ah ; 'z'
0x180009392  jnz     loc_180009450
0x180009398  mov     eax, [rsp+2A0h+TokenInformationLength]
0x18000939c  xor     esi, esi
0x18000939e  mov     [rsp+2A0h+var_25C], esi
0x1800093a2  mov     edx, eax; uBytes
0x1800093a4  xor     ecx, ecx; uFlags
0x1800093a6  mov     [rsp+2A0h+var_258], 0
0x1800093ae  call    cs:__imp_LocalAlloc
0x1800093b5  nop     dword ptr [rax+rax+00h]
0x1800093ba  mov     r14, rax
0x1800093bd  test    rax, rax
0x1800093c0  jz      loc_180009544
0x1800093c6  mov     r9d, [rsp+2A0h+TokenInformationLength]; TokenInformationLength
0x1800093cb  lea     rax, [rsp+2A0h+var_258]
0x1800093d0  mov     rcx, [rbx+18h]; TokenHandle
0x1800093d4  mov     r8, r14; TokenInformation
0x1800093d7  mov     edx, r12d; TokenInformationClass
0x1800093da  mov     [rsp+2A0h+ReturnLength], rax; ReturnLength
0x1800093df  call    cs:__imp_GetTokenInformation
0x1800093e6  nop     dword ptr [rax+rax+00h]
0x1800093eb  test    eax, eax
0x1800093ed  jnz     loc_1800091AA
0x1800093f3  call    cs:__imp_GetLastError
0x1800093fa  nop     dword ptr [rax+rax+00h]
0x1800093ff  mov     [rsp+2A0h+var_25C], eax
0x180009403  mov     esi, eax
0x180009405  cmp     eax, 7Ah ; 'z'
0x180009408  jz      loc_18000959D
0x18000940e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009415  lea     rax, WPP_GLOBAL_Control
0x18000941c  cmp     rcx, rax
0x18000941f  jz      loc_180009240
0x180009425  test    [rcx+1Ch], dil
0x180009429  jz      loc_180009240
0x18000942f  mov     dword ptr [rsp+2A0h+var_270], 0A6Eh
0x180009437  mov     rcx, [rcx+10h]
0x18000943b  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180009442  mov     [rsp+2A0h+var_278], rax
0x180009447  mov     dword ptr [rsp+2A0h+ReturnLength], esi
0x18000944b  jmp     loc_180009585
0x180009450  mov     rcx, cs:WPP_GLOBAL_Control
0x180009457  lea     rax, WPP_GLOBAL_Control
0x18000945e  cmp     rcx, rax
0x180009461  jz      loc_180009240
0x180009467  test    [rcx+1Ch], dil
0x18000946b  jz      loc_180009240
0x180009471  mov     dword ptr [rsp+2A0h+var_270], 0A4Dh
0x180009479  jmp     short loc_180009437
0x18000947b  mov     rcx, [rcx+10h]
0x18000947f  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180009486  mov     dword ptr [rsp+2A0h+var_270], 0A18h
0x18000948e  lea     r9, aDwlasterror; "dwLastError"
0x180009495  mov     [rsp+2A0h+var_278], rax
0x18000949a  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x1800094a1  mov     dword ptr [rsp+2A0h+ReturnLength], esi
0x1800094a5  call    WPP_SF_sDsd
0x1800094aa  jmp     loc_18000936D
0x1800094af  mov     edx, [rsp+2A0h+TokenInformationLength]; uBytes
0x1800094b3  xor     ecx, ecx; uFlags
0x1800094b5  call    cs:__imp_LocalAlloc
0x1800094bc  nop     dword ptr [rax+rax+00h]
0x1800094c1  mov     [rsp+2A0h+var_248], rax
0x1800094c6  mov     r15, rax
0x1800094c9  test    rax, rax
0x1800094cc  jnz     short loc_180009500
0x1800094ce  lea     ecx, [rax+8]
0x1800094d1  mov     r9d, 0A24h
0x1800094d7  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800094de  mov     esi, ecx
0x1800094e0  lea     rdx, aDwlasterror; "dwLastError"
0x1800094e7  call    DebugTraceError
0x1800094ec  mov     rcx, r15; hMem
0x1800094ef  call    cs:__imp_LocalFree
0x1800094f6  nop     dword ptr [rax+rax+00h]
0x1800094fb  jmp     loc_18000924E
0x180009500  mov     r9d, [rsp+2A0h+TokenInformationLength]; TokenInformationLength
0x180009505  lea     rax, [rsp+2A0h+TokenInformationLength]
0x18000950a  mov     rcx, [rbx+18h]; TokenHandle
0x18000950e  mov     r8, r15; TokenInformation
0x180009511  mov     edx, edi; TokenInformationClass
0x180009513  mov     [rsp+2A0h+ReturnLength], rax; ReturnLength
0x180009518  call    cs:__imp_GetTokenInformation
0x18000951f  nop     dword ptr [rax+rax+00h]
0x180009524  test    eax, eax
0x180009526  jnz     loc_18000916F
0x18000952c  call    cs:__imp_GetLastError
0x180009533  nop     dword ptr [rax+rax+00h]
0x180009538  mov     esi, eax
0x18000953a  mov     ecx, eax
0x18000953c  mov     r9d, 0A33h
0x180009542  jmp     short loc_180009551
0x180009544  mov     ecx, 8
0x180009549  mov     r9d, 0A5Eh
0x18000954f  mov     esi, ecx
0x180009551  lea     rdx, aDwlasterror; "dwLastError"
0x180009558  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000955f  call    DebugTraceError
0x180009564  jmp     loc_180009240
0x180009569  mov     dword ptr [rsp+2A0h+var_270], 0AA1h
0x180009571  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180009578  mov     [rsp+2A0h+var_278], rax
0x18000957d  mov     dword ptr [rsp+2A0h+ReturnLength], ecx
0x180009581  mov     rcx, [rdx+10h]
0x180009585  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18000958c  lea     r9, aDwlasterror; "dwLastError"
0x180009593  call    WPP_SF_sDsd
0x180009598  jmp     loc_180009240
0x18000959d  mov     eax, [rsp+2A0h+TokenInformationLength]
0x1800095a1  cmp     [rsp+2A0h+var_258], eax
0x1800095a5  jbe     loc_180009240
0x1800095ab  mov     rcx, r14; hMem
0x1800095ae  call    cs:__imp_LocalFree
0x1800095b5  nop     dword ptr [rax+rax+00h]
0x1800095ba  mov     eax, [rsp+2A0h+var_258]
0x1800095be  mov     [rsp+2A0h+TokenInformationLength], eax
0x1800095c2  jmp     loc_1800093A2
```
