# DecryptCredentialHistory(_CREDENTIAL_HISTORY *,uchar * const,uchar * const,uchar * const)

- ea: `0x1800146ac`
- end: `0x180014c74`
- name: `?DecryptCredentialHistory@@YAKPEAU_CREDENTIAL_HISTORY@@QEAE11@Z`
- size: `1480`
- prototype: `__int64 __fastcall(struct _CREDENTIAL_HISTORY *, unsigned __int8 *const, unsigned __int8 *const, unsigned __int8 *const)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004e60`

## callees

- `0x180001224`
- `0x180002480`
- `0x1800029d0`
- `0x180007f10`
- `0x180008300`
- `0x18000b638`
- `0x18001467c`
- `0x1800146ac`
- `0x18001d810`

## import_xrefs

- `bcrypt!BCryptGenerateSymmetricKey` at `0x180014843`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180014a35`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180014843`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180014a35`
- `bcrypt!BCryptDecrypt` at `0x1800148ec`
- `bcrypt!BCryptDecrypt` at `0x180014adf`
- `bcrypt!BCryptDecrypt` at `0x1800148ec`
- `bcrypt!BCryptDecrypt` at `0x180014adf`
- `bcrypt!BCryptDestroyKey` at `0x1800148ff`
- `bcrypt!BCryptDestroyKey` at `0x180014af2`
- `bcrypt!BCryptDestroyKey` at `0x1800148ff`
- `bcrypt!BCryptDestroyKey` at `0x180014af2`
- `ntdll!RtlNtStatusToDosError` at `0x180014874`
- `ntdll!RtlNtStatusToDosError` at `0x18001492c`
- `ntdll!RtlNtStatusToDosError` at `0x180014a66`
- `ntdll!RtlNtStatusToDosError` at `0x180014b1f`
- `ntdll!RtlNtStatusToDosError` at `0x180014bc7`
- `ntdll!RtlNtStatusToDosError` at `0x180014874`
- `ntdll!RtlNtStatusToDosError` at `0x18001492c`
- `ntdll!RtlNtStatusToDosError` at `0x180014a66`
- `ntdll!RtlNtStatusToDosError` at `0x180014b1f`
- `ntdll!RtlNtStatusToDosError` at `0x180014bc7`

## string_xrefs

- `0x1800147ab`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x18001485c`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x180014915`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x180014a4e`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x180014b08`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`

## pseudocode

```c
__int64 __fastcall DecryptCredentialHistory(
        struct _CREDENTIAL_HISTORY *a1,
        unsigned __int8 *const a2,
        unsigned __int8 *const a3,
        unsigned __int8 *const a4)
{
  ULONG v7; // ebx
  unsigned int v8; // ecx
  ULONG v9; // eax
  ULONG v10; // edx
  unsigned int v11; // r12d
  UCHAR *v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  unsigned int v15; // r14d
  __int64 v16; // rdx
  void *BCryptProviderHandle; // rax
  NTSTATUS v18; // eax
  NTSTATUS v19; // r14d
  int v20; // esi
  UCHAR *v21; // rax
  void *v22; // rax
  NTSTATUS v23; // eax
  NTSTATUS v24; // r14d
  int v25; // esi
  __int64 v26; // rax
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  ULONG v31; // [rsp+54h] [rbp-154h] BYREF
  ULONG pcbResult; // [rsp+58h] [rbp-150h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+60h] [rbp-148h] BYREF
  unsigned int v34; // [rsp+68h] [rbp-140h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+70h] [rbp-138h] BYREF
  UCHAR *v36; // [rsp+78h] [rbp-130h]
  __int64 v37; // [rsp+80h] [rbp-128h]
  UCHAR *v38; // [rsp+88h] [rbp-120h]
  __int64 v39; // [rsp+90h] [rbp-118h]
  UCHAR v40[16]; // [rsp+98h] [rbp-110h] BYREF
  UCHAR pbIV[8]; // [rsp+A8h] [rbp-100h] BYREF
  UCHAR pbOutput[16]; // [rsp+B0h] [rbp-F8h] BYREF
  int v43; // [rsp+C0h] [rbp-E8h]
  __int128 v44; // [rsp+C4h] [rbp-E4h]
  int v45; // [rsp+D4h] [rbp-D4h]
  UCHAR v46[16]; // [rsp+E0h] [rbp-C8h] BYREF
  int v47; // [rsp+F0h] [rbp-B8h]
  __int128 v48; // [rsp+F4h] [rbp-B4h]
  int v49; // [rsp+104h] [rbp-A4h]
  UCHAR pbSecret[24]; // [rsp+120h] [rbp-88h] BYREF
  __int64 v51; // [rsp+138h] [rbp-70h]
  __int128 v52; // [rsp+140h] [rbp-68h]

  hKey = a2;
  v7 = 0;
  v8 = *((_DWORD *)a1 + 7);
  v9 = 64;
  v10 = 64;
  if ( v8 != 32782 )
    v10 = 40;
  pcbResult = v10;
  if ( v8 != 32782 )
    v9 = 20;
  v31 = v9;
  v11 = (v8 != 32782) + 1;
  v12 = (UCHAR *)(4LL * GetIterationCount(v8));
  if ( (unsigned __int64)v12 > 0xFFFFFFFF )
  {
    v7 = 13;
  }
  else if ( *((_DWORD *)a1 + 8) <= (unsigned int)v12 )
  {
    v15 = 0;
    while ( 1 )
    {
      v34 = v15;
      if ( v15 >= v11 )
        break;
      v16 = v15 * v31;
      if ( !PKCS5DerivePBKDF2(
              (UCHAR *)hKey,
              0x14u,
              (__int128 *)((char *)a1 + 52),
              v14,
              *((_DWORD *)a1 + 7),
              *((_DWORD *)a1 + 8),
              ++v15,
              &pbSecret[v16],
              pcbResult - (unsigned int)v16) )
      {
        v7 = 13;
        DebugTraceError(13, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", 1023);
        goto LABEL_42;
      }
    }
    LODWORD(v12) = 26115;
    if ( *((_DWORD *)a1 + 10) == 26115 )
    {
      phKey = 0;
      pcbResult = 0;
      if ( *((_DWORD *)a1 + 11) == 20 && *((_DWORD *)a1 + 12) == 20 )
      {
        BCryptProviderHandle = (void *)GetBCryptProviderHandle(0x6603u);
        if ( BCryptProviderHandle )
        {
          v18 = BCryptGenerateSymmetricKey(BCryptProviderHandle, &phKey, 0, 0, pbSecret, 0x18u, 0);
          v19 = v18;
          if ( v18 >= 0 )
          {
            *(_QWORD *)pbIV = v51;
            v20 = BCryptDecrypt(
                    phKey,
                    (PUCHAR)a1 + *((unsigned int *)a1 + 9) + 68,
                    0x28u,
                    0,
                    pbIV,
                    8u,
                    pbOutput,
                    0x28u,
                    &pcbResult,
                    0);
            BCryptDestroyKey(phKey);
            if ( v20 >= 0 )
            {
              *(_OWORD *)a3 = *(_OWORD *)pbOutput;
              *((_DWORD *)a3 + 4) = v43;
              *(_OWORD *)a4 = v44;
              *((_DWORD *)a4 + 4) = v45;
              v13 = 48;
              v37 = 48;
              v21 = pbOutput;
              v36 = pbOutput;
              while ( v13 )
              {
                *v21++ = 0;
                v36 = v21;
                v37 = --v13;
              }
            }
            else
            {
              DebugTraceError(
                (unsigned int)v20,
                "ntStatus",
                "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp",
                1096);
              v7 = RtlNtStatusToDosError(v20);
            }
          }
          else
          {
            DebugTraceError(
              (unsigned int)v18,
              "ntStatus",
              "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp",
              1072);
            v7 = RtlNtStatusToDosError(v19);
          }
        }
        else
        {
          v7 = 13;
        }
      }
      else
      {
        v7 = 87;
      }
    }
    else
    {
      LODWORD(v12) = 26128;
      if ( *((_DWORD *)a1 + 10) == 26128 )
      {
        hKey = 0;
        v31 = 0;
        if ( *((_DWORD *)a1 + 11) == 20 && *((_DWORD *)a1 + 12) == 20 )
        {
          v22 = (void *)GetBCryptProviderHandle(0x6610u);
          if ( v22 )
          {
            v23 = BCryptGenerateSymmetricKey(v22, &hKey, 0, 0, pbSecret, 0x20u, 0);
            v24 = v23;
            if ( v23 >= 0 )
            {
              *(_OWORD *)v40 = v52;
              v25 = BCryptDecrypt(
                      hKey,
                      (PUCHAR)a1 + *((unsigned int *)a1 + 9) + 68,
                      0x30u,
                      0,
                      v40,
                      0x10u,
                      v46,
                      0x30u,
                      &v31,
                      0);
              BCryptDestroyKey(hKey);
              if ( v25 >= 0 )
              {
                *(_OWORD *)a3 = *(_OWORD *)v46;
                *((_DWORD *)a3 + 4) = v47;
                *(_OWORD *)a4 = v48;
                *((_DWORD *)a4 + 4) = v49;
                v26 = 56;
                v39 = 56;
                v12 = v46;
                v38 = v46;
                while ( v26 )
                {
                  *v12++ = 0;
                  v38 = v12;
                  v39 = --v26;
                }
              }
              else
              {
                DebugTraceError(
                  (unsigned int)v25,
                  "ntStatus",
                  "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp",
                  1172);
                v7 = RtlNtStatusToDosError(v25);
              }
            }
            else
            {
              DebugTraceError(
                (unsigned int)v23,
                "ntStatus",
                "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp",
                1148);
              v7 = RtlNtStatusToDosError(v24);
            }
          }
          else
          {
            v7 = 13;
          }
        }
        else
        {
          v7 = 87;
        }
      }
      else
      {
        v7 = 13;
      }
    }
  }
  else
  {
    v7 = 13;
  }
LABEL_42:
  if ( v7 )
  {
    if ( (byte_18004CC41 & 4) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        (_DWORD)v12,
        (unsigned int)ETW_LOG_CREDHIST_DECRYPTION_FAILED,
        v13,
        1,
        (__int64)v40);
    if ( (unsigned int)dword_18004C260 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x400000000000LL) )
    {
      *(_QWORD *)pbIV = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        v27,
        (unsigned int)&dword_180044A3C,
        v28,
        v29,
        (__int64)pbIV);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800146ac  push    rbx
0x1800146ae  push    rsi
0x1800146af  push    r12
0x1800146b1  push    r13
0x1800146b3  push    r14
0x1800146b5  push    r15
0x1800146b7  sub     rsp, 178h
0x1800146be  mov     rax, cs:__security_cookie
0x1800146c5  xor     rax, rsp
0x1800146c8  mov     [rsp+1A8h+var_48], rax
0x1800146d0  mov     r13, r9
0x1800146d3  mov     r15, r8
0x1800146d6  mov     [rsp+1A8h+hKey], rdx
0x1800146db  mov     rsi, rcx
0x1800146de  xor     ebx, ebx
0x1800146e0  mov     ecx, [rcx+1Ch]; unsigned int
0x1800146e3  lea     eax, [rbx+40h]
0x1800146e6  mov     edx, eax
0x1800146e8  lea     r9d, [rbx+28h]
0x1800146ec  mov     r8d, 800Eh
0x1800146f2  cmp     ecx, r8d
0x1800146f5  cmovnz  edx, r9d
0x1800146f9  mov     [rsp+1A8h+var_150], edx
0x1800146fd  lea     edx, [rbx+14h]
0x180014700  cmovnz  eax, edx
0x180014703  mov     [rsp+1A8h+var_154], eax
0x180014707  xor     r12d, r12d
0x18001470a  cmp     ecx, r8d
0x18001470d  setnz   r12b
0x180014711  inc     r12d
0x180014714  call    ?GetIterationCount@@YAKI@Z; GetIterationCount(uint)
0x180014719  mov     ecx, eax
0x18001471b  shl     rcx, 2
0x18001471f  mov     eax, 0FFFFFFFFh
0x180014724  cmp     rcx, rax
0x180014727  ja      loc_180014BBA
0x18001472d  cmp     [rsi+20h], ecx
0x180014730  jbe     short loc_180014740
0x180014732  mov     ebx, 0Dh
0x180014737  mov     [rsp+1A8h+var_158], ebx
0x18001473b  jmp     loc_180014BD9
0x180014740  xor     r14d, r14d
0x180014743  mov     [rsp+1A8h+var_140], r14d
0x180014748  cmp     r14d, r12d
0x18001474b  jnb     short loc_1800147CA
0x18001474d  mov     eax, [rsp+1A8h+var_154]
0x180014751  imul    eax, r14d
0x180014755  mov     edx, eax
0x180014757  inc     r14d
0x18001475a  mov     ecx, [rsp+1A8h+var_150]
0x18001475e  sub     ecx, eax
0x180014760  lea     rax, [rsp+1A8h+var_88]
0x180014768  add     rax, rdx
0x18001476b  lea     r8, [rsi+34h]; int
0x18001476f  mov     dword ptr [rsp+1A8h+pcbResult], ecx; int
0x180014773  mov     qword ptr [rsp+1A8h+cbOutput], rax; PUCHAR
0x180014778  mov     [rsp+1A8h+dwFlags], r14d; char
0x18001477d  mov     eax, [rsi+20h]
0x180014780  mov     [rsp+1A8h+cbSecret], eax; int
0x180014784  mov     eax, [rsi+1Ch]
0x180014787  mov     dword ptr [rsp+1A8h+pbSecret], eax; unsigned int
0x18001478b  mov     edx, 14h; int
0x180014790  mov     rcx, [rsp+1A8h+hKey]; int
0x180014795  call    PKCS5DerivePBKDF2
0x18001479a  test    eax, eax
0x18001479c  jnz     short loc_1800147C5
0x18001479e  lea     ebx, [rax+0Dh]
0x1800147a1  mov     [rsp+1A8h+var_158], ebx
0x1800147a5  mov     r9d, 3FFh
0x1800147ab  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800147b2  lea     rdx, aDwlasterror; "dwLastError"
0x1800147b9  mov     ecx, ebx
0x1800147bb  call    DebugTraceError
0x1800147c0  jmp     loc_180014BD9
0x1800147c5  jmp     loc_180014743
0x1800147ca  mov     ecx, 6603h; unsigned int
0x1800147cf  cmp     [rsi+28h], ecx
0x1800147d2  jnz     loc_1800149BC
0x1800147d8  mov     [rsp+1A8h+phKey], 0
0x1800147e1  mov     [rsp+1A8h+var_150], 0
0x1800147e9  cmp     dword ptr [rsi+2Ch], 14h
0x1800147ed  jnz     loc_1800149AE
0x1800147f3  cmp     dword ptr [rsi+30h], 14h
0x1800147f7  jnz     loc_1800149AE
0x1800147fd  xor     r8d, r8d
0x180014800  xor     edx, edx
0x180014802  call    GetBCryptProviderHandle
0x180014807  test    rax, rax
0x18001480a  jnz     short loc_180014818
0x18001480c  lea     ebx, [rax+0Dh]
0x18001480f  mov     [rsp+1A8h+var_158], ebx
0x180014813  jmp     loc_180014BD9
0x180014818  mov     [rsp+1A8h+dwFlags], 0; dwFlags
0x180014820  mov     [rsp+1A8h+cbSecret], 18h; cbSecret
0x180014828  lea     rcx, [rsp+1A8h+var_88]
0x180014830  mov     [rsp+1A8h+pbSecret], rcx; pbSecret
0x180014835  xor     r9d, r9d; cbKeyObject
0x180014838  xor     r8d, r8d; pbKeyObject
0x18001483b  lea     rdx, [rsp+1A8h+phKey]; phKey
0x180014840  mov     rcx, rax; hAlgorithm
0x180014843  call    cs:__imp_BCryptGenerateSymmetricKey
0x18001484a  nop     dword ptr [rax+rax+00h]
0x18001484f  mov     r14d, eax
0x180014852  test    eax, eax
0x180014854  jns     short loc_18001488B
0x180014856  mov     r9d, 430h
0x18001485c  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180014863  lea     rdx, aNtstatus; "ntStatus"
0x18001486a  mov     ecx, eax
0x18001486c  call    DebugTraceError
0x180014871  mov     ecx, r14d; Status
0x180014874  call    cs:__imp_RtlNtStatusToDosError
0x18001487b  nop     dword ptr [rax+rax+00h]
0x180014880  mov     ebx, eax
0x180014882  mov     [rsp+1A8h+var_158], eax
0x180014886  jmp     loc_180014BD9
0x18001488b  mov     rax, [rsp+1A8h+var_70]
0x180014893  mov     qword ptr [rsp+1A8h+pbIV], rax
0x18001489b  mov     edx, [rsi+24h]
0x18001489e  add     rdx, 44h ; 'D'
0x1800148a2  add     rdx, rsi; pbInput
0x1800148a5  mov     [rsp+1A8h+var_160], 0; dwFlags
0x1800148ad  lea     rax, [rsp+1A8h+var_150]
0x1800148b2  mov     [rsp+1A8h+pcbResult], rax; pcbResult
0x1800148b7  mov     r8d, 28h ; '('; cbInput
0x1800148bd  mov     [rsp+1A8h+cbOutput], r8d; cbOutput
0x1800148c2  lea     rax, [rsp+1A8h+pbOutput]
0x1800148ca  mov     qword ptr [rsp+1A8h+dwFlags], rax; pbOutput
0x1800148cf  mov     [rsp+1A8h+cbSecret], 8; cbIV
0x1800148d7  lea     rax, [rsp+1A8h+pbIV]
0x1800148df  mov     [rsp+1A8h+pbSecret], rax; pbIV
0x1800148e4  xor     r9d, r9d; pPaddingInfo
0x1800148e7  mov     rcx, [rsp+1A8h+phKey]; hKey
0x1800148ec  call    cs:__imp_BCryptDecrypt
0x1800148f3  nop     dword ptr [rax+rax+00h]
0x1800148f8  mov     esi, eax
0x1800148fa  mov     rcx, [rsp+1A8h+phKey]; hKey
0x1800148ff  call    cs:__imp_BCryptDestroyKey
0x180014906  nop     dword ptr [rax+rax+00h]
0x18001490b  test    esi, esi
0x18001490d  jns     short loc_180014943
0x18001490f  mov     r9d, 448h
0x180014915  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18001491c  lea     rdx, aNtstatus; "ntStatus"
0x180014923  mov     ecx, esi
0x180014925  call    DebugTraceError
0x18001492a  mov     ecx, esi; Status
0x18001492c  call    cs:__imp_RtlNtStatusToDosError
0x180014933  nop     dword ptr [rax+rax+00h]
0x180014938  mov     ebx, eax
0x18001493a  mov     [rsp+1A8h+var_158], eax
0x18001493e  jmp     loc_180014BD9
0x180014943  movups  xmm0, xmmword ptr [rsp+1A8h+pbOutput]
0x18001494b  movups  xmmword ptr [r15], xmm0
0x18001494f  mov     eax, [rsp+1A8h+var_E8]
0x180014956  mov     [r15+10h], eax
0x18001495a  movups  xmm0, [rsp+1A8h+var_E4]
0x180014962  movups  xmmword ptr [r13+0], xmm0
0x180014967  mov     eax, [rsp+1A8h+var_D4]
0x18001496e  mov     [r13+10h], eax
0x180014972  mov     r8d, 30h ; '0'
0x180014978  mov     [rsp+1A8h+var_128], r8
0x180014980  lea     rax, [rsp+1A8h+pbOutput]
0x180014988  mov     [rsp+1A8h+var_130], rax
0x18001498d  test    r8, r8
0x180014990  jz      loc_180014BA2
0x180014996  mov     byte ptr [rax], 0
0x180014999  inc     rax
0x18001499c  mov     [rsp+1A8h+var_130], rax
0x1800149a1  dec     r8
0x1800149a4  mov     [rsp+1A8h+var_128], r8
0x1800149ac  jmp     short loc_18001498D
0x1800149ae  mov     ebx, 57h ; 'W'
0x1800149b3  mov     [rsp+1A8h+var_158], ebx
0x1800149b7  jmp     loc_180014BD9
0x1800149bc  mov     ecx, 6610h; unsigned int
0x1800149c1  cmp     [rsi+28h], ecx
0x1800149c4  jnz     loc_180014BAF
0x1800149ca  mov     [rsp+1A8h+hKey], 0
0x1800149d3  mov     [rsp+1A8h+var_154], 0
0x1800149db  cmp     dword ptr [rsi+2Ch], 14h
0x1800149df  jnz     loc_180014BA4
0x1800149e5  cmp     dword ptr [rsi+30h], 14h
0x1800149e9  jnz     loc_180014BA4
0x1800149ef  xor     r8d, r8d
0x1800149f2  xor     edx, edx
0x1800149f4  call    GetBCryptProviderHandle
0x1800149f9  test    rax, rax
0x1800149fc  jnz     short loc_180014A0A
0x1800149fe  lea     ebx, [rax+0Dh]
0x180014a01  mov     [rsp+1A8h+var_158], ebx
0x180014a05  jmp     loc_180014BD9
0x180014a0a  mov     [rsp+1A8h+dwFlags], 0; dwFlags
0x180014a12  mov     [rsp+1A8h+cbSecret], 20h ; ' '; cbSecret
0x180014a1a  lea     rcx, [rsp+1A8h+var_88]
0x180014a22  mov     [rsp+1A8h+pbSecret], rcx; pbSecret
0x180014a27  xor     r9d, r9d; cbKeyObject
0x180014a2a  xor     r8d, r8d; pbKeyObject
0x180014a2d  lea     rdx, [rsp+1A8h+hKey]; phKey
0x180014a32  mov     rcx, rax; hAlgorithm
0x180014a35  call    cs:__imp_BCryptGenerateSymmetricKey
0x180014a3c  nop     dword ptr [rax+rax+00h]
0x180014a41  mov     r14d, eax
0x180014a44  test    eax, eax
0x180014a46  jns     short loc_180014A7D
0x180014a48  mov     r9d, 47Ch
0x180014a4e  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180014a55  lea     rdx, aNtstatus; "ntStatus"
0x180014a5c  mov     ecx, eax
0x180014a5e  call    DebugTraceError
0x180014a63  mov     ecx, r14d; Status
0x180014a66  call    cs:__imp_RtlNtStatusToDosError
0x180014a6d  nop     dword ptr [rax+rax+00h]
0x180014a72  mov     ebx, eax
0x180014a74  mov     [rsp+1A8h+var_158], eax
0x180014a78  jmp     loc_180014BD9
0x180014a7d  movaps  xmm0, [rsp+1A8h+var_68]
0x180014a85  movdqu  xmmword ptr [rsp+1A8h+var_110], xmm0
0x180014a8e  mov     edx, [rsi+24h]
0x180014a91  add     rdx, 44h ; 'D'
0x180014a95  add     rdx, rsi; pbInput
0x180014a98  mov     [rsp+1A8h+var_160], 0; dwFlags
0x180014aa0  lea     rax, [rsp+1A8h+var_154]
0x180014aa5  mov     [rsp+1A8h+pcbResult], rax; pcbResult
0x180014aaa  mov     r8d, 30h ; '0'; cbInput
0x180014ab0  mov     [rsp+1A8h+cbOutput], r8d; cbOutput
0x180014ab5  lea     rax, [rsp+1A8h+var_C8]
0x180014abd  mov     qword ptr [rsp+1A8h+dwFlags], rax; pbOutput
0x180014ac2  mov     [rsp+1A8h+cbSecret], 10h; cbIV
0x180014aca  lea     rax, [rsp+1A8h+var_110]
0x180014ad2  mov     [rsp+1A8h+pbSecret], rax; pbIV
0x180014ad7  xor     r9d, r9d; pPaddingInfo
0x180014ada  mov     rcx, [rsp+1A8h+hKey]; hKey
0x180014adf  call    cs:__imp_BCryptDecrypt
0x180014ae6  nop     dword ptr [rax+rax+00h]
0x180014aeb  mov     esi, eax
0x180014aed  mov     rcx, [rsp+1A8h+hKey]; hKey
0x180014af2  call    cs:__imp_BCryptDestroyKey
0x180014af9  nop     dword ptr [rax+rax+00h]
0x180014afe  test    esi, esi
0x180014b00  jns     short loc_180014B36
0x180014b02  mov     r9d, 494h
0x180014b08  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180014b0f  lea     rdx, aNtstatus; "ntStatus"
0x180014b16  mov     ecx, esi
0x180014b18  call    DebugTraceError
0x180014b1d  mov     ecx, esi; Status
0x180014b1f  call    cs:__imp_RtlNtStatusToDosError
0x180014b26  nop     dword ptr [rax+rax+00h]
0x180014b2b  mov     ebx, eax
0x180014b2d  mov     [rsp+1A8h+var_158], eax
0x180014b31  jmp     loc_180014BD9
0x180014b36  movups  xmm0, xmmword ptr [rsp+1A8h+var_C8]
0x180014b3e  movups  xmmword ptr [r15], xmm0
0x180014b42  mov     eax, [rsp+1A8h+var_B8]
0x180014b49  mov     [r15+10h], eax
0x180014b4d  movups  xmm0, [rsp+1A8h+var_B4]
0x180014b55  movups  xmmword ptr [r13+0], xmm0
0x180014b5a  mov     eax, [rsp+1A8h+var_A4]
0x180014b61  mov     [r13+10h], eax
0x180014b65  mov     eax, 38h ; '8'
0x180014b6a  mov     [rsp+1A8h+var_118], rax
0x180014b72  lea     rcx, [rsp+1A8h+var_C8]
0x180014b7a  mov     [rsp+1A8h+var_120], rcx
0x180014b82  test    rax, rax
0x180014b85  jz      short loc_180014BA2
0x180014b87  mov     byte ptr [rcx], 0
0x180014b8a  inc     rcx
0x180014b8d  mov     [rsp+1A8h+var_120], rcx
0x180014b95  dec     rax
0x180014b98  mov     [rsp+1A8h+var_118], rax
0x180014ba0  jmp     short loc_180014B82
0x180014ba2  jmp     short loc_180014BD9
0x180014ba4  mov     ebx, 57h ; 'W'
0x180014ba9  mov     [rsp+1A8h+var_158], ebx
0x180014bad  jmp     short loc_180014BD9
0x180014baf  mov     ebx, 0Dh
0x180014bb4  mov     [rsp+1A8h+var_158], ebx
0x180014bb8  jmp     short loc_180014BD9
0x180014bba  mov     ebx, 0Dh
0x180014bbf  mov     [rsp+1A8h+var_158], ebx
0x180014bc3  jmp     short loc_180014BD9
0x180014bc5  mov     ecx, eax; Status
0x180014bc7  call    cs:__imp_RtlNtStatusToDosError
0x180014bce  nop     dword ptr [rax+rax+00h]
0x180014bd3  mov     ebx, eax
0x180014bd5  mov     [rsp+1A8h+var_158], eax
0x180014bd9  test    ebx, ebx
0x180014bdb  jz      short loc_180014C4F
0x180014bdd  test    cs:byte_18004CC41, 4
0x180014be4  jz      short loc_180014C05
0x180014be6  lea     rax, [rsp+1A8h+var_110]
0x180014bee  mov     [rsp+1A8h+pbSecret], rax
0x180014bf3  mov     r9d, 1
0x180014bf9  lea     rdx, ETW_LOG_CREDHIST_DECRYPTION_FAILED
0x180014c00  call    McGenEventWrite_EtwEventWriteTransfer
0x180014c05  mov     eax, cs:dword_18004C260
0x180014c0b  cmp     eax, 5
0x180014c0e  jbe     short loc_180014C4F
0x180014c10  mov     rdx, 400000000000h
  ... truncated ...
```
