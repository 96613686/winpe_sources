# ConvertRecoveredBlobToW2KBlob(uchar *,ulong,uchar *,ulong,void *,uchar * *,ulong *)

- ea: `0x18003048c`
- end: `0x18003085e`
- name: `?ConvertRecoveredBlobToW2KBlob@@YAHPEAEK0KPEAXPEAPEAEPEAK@Z`
- size: `978`
- prototype: `_BOOL8 __fastcall(unsigned __int8 *, unsigned int, unsigned __int8 *, ULONG, PSID pSid, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003325c`
- `0x180033b04`

## callees

- `0x180002310`
- `0x1800029d0`
- `0x180007f10`
- `0x18000c4a0`
- `0x18001d810`
- `0x18003048c`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180030525`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180030525`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18003050e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18003050e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003082a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003082a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003080a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003080a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030579`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030579`
- `bcrypt!BCryptEncrypt` at `0x1800307b2`
- `bcrypt!BCryptEncrypt` at `0x1800307b2`
- `bcrypt!BCryptGenRandom` at `0x1800305b3`
- `bcrypt!BCryptGenRandom` at `0x1800305e3`
- `bcrypt!BCryptGenRandom` at `0x1800305b3`
- `bcrypt!BCryptGenRandom` at `0x1800305e3`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18003075d`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18003075d`
- `bcrypt!BCryptDestroyKey` at `0x1800307c5`
- `bcrypt!BCryptDestroyKey` at `0x1800307c5`

## string_xrefs

- `0x180030552`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x1800307e2`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
_BOOL8 __fastcall ConvertRecoveredBlobToW2KBlob(
        unsigned __int8 *a1,
        unsigned int a2,
        unsigned __int8 *a3,
        ULONG a4,
        PSID pSid,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  DWORD v10; // edi
  __int64 v11; // r9
  ULONG cbOutput; // r13d
  unsigned int v13; // r15d
  UCHAR *v14; // rax
  UCHAR *v15; // rsi
  UCHAR *v16; // r12
  NTSTATUS v17; // ebx
  __int64 v18; // r9
  const char *v19; // rdx
  __int64 v20; // rcx
  UCHAR *v21; // rax
  size_t Size; // [rsp+60h] [rbp-91h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+68h] [rbp-89h] BYREF
  void *Src; // [rsp+70h] [rbp-81h]
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+78h] [rbp-79h]
  unsigned __int8 **v27; // [rsp+80h] [rbp-71h]
  unsigned int *v28; // [rsp+88h] [rbp-69h]
  UCHAR v29[24]; // [rsp+90h] [rbp-61h] BYREF
  UCHAR v30[24]; // [rsp+A8h] [rbp-49h] BYREF
  UCHAR pbOutput[40]; // [rsp+C0h] [rbp-31h] BYREF

  v27 = a6;
  Size = a2;
  v10 = -2146893821;
  Src = a1;
  v28 = a7;
  hAlgorithm = (BCRYPT_ALG_HANDLE)GetBCryptProviderHandle(0x6801u);
  phKey = 0;
  if ( !hAlgorithm || !IsValidSid(pSid) )
    goto LABEL_27;
  GetLengthSid(pSid);
  if ( !(unsigned int)FMyPrimitiveSHA(a3, a4, v29) )
  {
    v10 = 13;
    v11 = 3299;
LABEL_5:
    DebugTraceError(v10, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v11);
    goto LABEL_27;
  }
  cbOutput = a2 + 36;
  v13 = a2 + 56;
  v14 = (UCHAR *)LocalAlloc(0, v13);
  v15 = v14;
  if ( !v14 )
  {
    v10 = 1130;
    v11 = 3313;
    goto LABEL_5;
  }
  *(_DWORD *)v14 = 1;
  v16 = v14 + 4;
  v17 = BCryptGenRandom(0, v14 + 4, 0x10u, 2u);
  if ( v17 < 0 )
  {
    v18 = 3331;
LABEL_22:
    v19 = "ntStatus";
    goto LABEL_23;
  }
  v17 = BCryptGenRandom(0, v15 + 20, 0x10u, 2u);
  if ( v17 < 0 )
  {
    v18 = 3345;
    goto LABEL_22;
  }
  if ( (unsigned int)ReusableHMAC(0, 0, 0x8009u, v29, 0x14u, v16, 0x10u, 0, 0, pbOutput, 0x14u) )
  {
    if ( (unsigned int)ReusableHMAC(0, 0, 0x8009u, v29, 0x14u, v15 + 20, 0x10u, 0, 0, v30, 0x14u) )
    {
      memcpy_0(v15 + 56, Src, (unsigned int)Size);
      if ( (unsigned int)ReusableHMAC(0, 0, 0x8009u, v30, 0x14u, (PUCHAR)Src, Size, 0, 0, v15 + 36, 0x14u) )
      {
        v17 = BCryptGenerateSymmetricKey(hAlgorithm, &phKey, 0, 0, pbOutput, 0x14u, 0);
        if ( v17 >= 0 )
        {
          v17 = BCryptEncrypt(phKey, v15 + 20, cbOutput, 0, 0, 0, v15 + 20, cbOutput, (ULONG *)&Size + 1, 0);
          BCryptDestroyKey(phKey);
          if ( v17 >= 0 )
          {
            v10 = 0;
            *v27 = v15;
            *v28 = v13;
            goto LABEL_27;
          }
          v18 = 3448;
        }
        else
        {
          v18 = 3429;
        }
        goto LABEL_22;
      }
      v17 = -2147467259;
      v19 = "E_FAIL";
      v18 = 3412;
    }
    else
    {
      v17 = -2147467259;
      v19 = "E_FAIL";
      v18 = 3385;
    }
  }
  else
  {
    v17 = -2147467259;
    v19 = "E_FAIL";
    v18 = 3365;
  }
LABEL_23:
  DebugTraceError((unsigned int)v17, v19, "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v18);
  v20 = v13;
  v21 = v15;
  if ( v13 )
  {
    do
    {
      *v21++ = 0;
      --v20;
    }
    while ( v20 );
  }
  LocalFree(v15);
LABEL_27:
  SetLastError(v10);
  return v10 == 0;
}

```

## disassembly

```asm
0x18003048c  push    rbp
0x18003048e  push    rbx
0x18003048f  push    rsi
0x180030490  push    rdi
0x180030491  push    r12
0x180030493  push    r13
0x180030495  push    r14
0x180030497  push    r15
0x180030499  lea     rbp, [rsp-7]
0x18003049e  sub     rsp, 0F8h
0x1800304a5  mov     rax, cs:__security_cookie
0x1800304ac  xor     rax, rsp
0x1800304af  mov     [rbp+3Fh+var_48], rax
0x1800304b3  mov     rax, [rbp+3Fh+arg_28]
0x1800304b7  mov     rsi, r8
0x1800304ba  mov     rbx, [rbp+3Fh+pSid]
0x1800304be  mov     r15d, edx
0x1800304c1  mov     [rbp+3Fh+var_B0], rax
0x1800304c5  xor     r8d, r8d
0x1800304c8  mov     rax, [rbp+3Fh+arg_30]
0x1800304cc  mov     r14d, r9d
0x1800304cf  mov     dword ptr [rsp+130h+Size], edx
0x1800304d3  mov     edi, 80090003h
0x1800304d8  mov     [rsp+130h+Src], rcx
0x1800304dd  xor     edx, edx
0x1800304df  mov     ecx, 6801h; unsigned int
0x1800304e4  mov     [rbp+3Fh+var_A8], rax
0x1800304e8  call    GetBCryptProviderHandle
0x1800304ed  mov     [rbp+3Fh+hAlgorithm], rax
0x1800304f1  mov     [rsp+130h+phKey], 0
0x1800304fa  mov     dword ptr [rsp+130h+Size+4], 0
0x180030502  test    rax, rax
0x180030505  jz      loc_180030828
0x18003050b  mov     rcx, rbx; pSid
0x18003050e  call    cs:__imp_IsValidSid
0x180030515  nop     dword ptr [rax+rax+00h]
0x18003051a  test    eax, eax
0x18003051c  jz      loc_180030828
0x180030522  mov     rcx, rbx; pSid
0x180030525  call    cs:__imp_GetLengthSid
0x18003052c  nop     dword ptr [rax+rax+00h]
0x180030531  lea     rax, [rbp+3Fh+var_A0]
0x180030535  mov     edx, r14d; cbInput
0x180030538  mov     rcx, rsi; pbInput
0x18003053b  mov     [rsp+130h+pbSecret], rax; PUCHAR
0x180030540  call    FMyPrimitiveSHA
0x180030545  test    eax, eax
0x180030547  jnz     short loc_18003056C
0x180030549  lea     edi, [rax+0Dh]
0x18003054c  mov     r9d, 0CE3h
0x180030552  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180030559  mov     ecx, edi
0x18003055b  lea     rdx, aDwlasterror; "dwLastError"
0x180030562  call    DebugTraceError
0x180030567  jmp     loc_180030828
0x18003056c  lea     r13d, [r15+24h]
0x180030570  xor     ecx, ecx; uFlags
0x180030572  lea     r15d, [r13+14h]
0x180030576  mov     edx, r15d; uBytes
0x180030579  call    cs:__imp_LocalAlloc
0x180030580  nop     dword ptr [rax+rax+00h]
0x180030585  mov     rsi, rax
0x180030588  test    rax, rax
0x18003058b  jnz     short loc_18003059A
0x18003058d  mov     edi, 46Ah
0x180030592  mov     r9d, 0CF1h
0x180030598  jmp     short loc_180030552
0x18003059a  mov     r9d, 2; dwFlags
0x1800305a0  mov     dword ptr [rax], 1
0x1800305a6  lea     r12, [rax+4]
0x1800305aa  xor     ecx, ecx; hAlgorithm
0x1800305ac  mov     rdx, r12; pbBuffer
0x1800305af  lea     r8d, [r9+0Eh]; cbBuffer
0x1800305b3  call    cs:__imp_BCryptGenRandom
0x1800305ba  nop     dword ptr [rax+rax+00h]
0x1800305bf  mov     ebx, eax
0x1800305c1  test    eax, eax
0x1800305c3  jns     short loc_1800305D0
0x1800305c5  mov     r9d, 0D03h
0x1800305cb  jmp     loc_1800307DB
0x1800305d0  mov     r9d, 2; dwFlags
0x1800305d6  lea     r14, [rsi+14h]
0x1800305da  mov     rdx, r14; pbBuffer
0x1800305dd  xor     ecx, ecx; hAlgorithm
0x1800305df  lea     r8d, [r9+0Eh]; cbBuffer
0x1800305e3  call    cs:__imp_BCryptGenRandom
0x1800305ea  nop     dword ptr [rax+rax+00h]
0x1800305ef  mov     ebx, eax
0x1800305f1  test    eax, eax
0x1800305f3  jns     short loc_180030600
0x1800305f5  mov     r9d, 0D11h
0x1800305fb  jmp     loc_1800307DB
0x180030600  mov     ebx, 14h
0x180030605  lea     rax, [rbp+3Fh+pbOutput]
0x180030609  mov     [rsp+130h+var_E0], ebx; unsigned int
0x18003060d  lea     r9, [rbp+3Fh+var_A0]; pbSecret
0x180030611  mov     qword ptr [rsp+130h+var_E8], rax; pbOutput
0x180030616  xor     edx, edx; hHash
0x180030618  mov     dword ptr [rsp+130h+pcbResult], 0; cbHashObject
0x180030620  xor     ecx, ecx; hAlgorithm
0x180030622  mov     qword ptr [rsp+130h+cbOutput], 0; pbHashObject
0x18003062b  mov     [rsp+130h+dwFlags], 10h; cbInput
0x180030633  mov     qword ptr [rsp+130h+cbSecret], r12; pbInput
0x180030638  mov     r12d, 8009h
0x18003063e  mov     r8d, r12d; unsigned int
0x180030641  mov     dword ptr [rsp+130h+pbSecret], ebx; ULONG
0x180030645  call    ?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z; ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x18003064a  test    eax, eax
0x18003064c  jnz     short loc_180030665
0x18003064e  mov     ebx, 80004005h
0x180030653  lea     rdx, aEFail; "E_FAIL"
0x18003065a  mov     r9d, 0D25h
0x180030660  jmp     loc_1800307E2
0x180030665  mov     [rsp+130h+var_E0], ebx; unsigned int
0x180030669  lea     rax, [rbp+3Fh+var_88]
0x18003066d  mov     qword ptr [rsp+130h+var_E8], rax; pbOutput
0x180030672  lea     r9, [rbp+3Fh+var_A0]; pbSecret
0x180030676  mov     dword ptr [rsp+130h+pcbResult], 0; cbHashObject
0x18003067e  mov     r8d, r12d; unsigned int
0x180030681  mov     qword ptr [rsp+130h+cbOutput], 0; pbHashObject
0x18003068a  xor     edx, edx; hHash
0x18003068c  mov     [rsp+130h+dwFlags], 10h; cbInput
0x180030694  xor     ecx, ecx; hAlgorithm
0x180030696  mov     qword ptr [rsp+130h+cbSecret], r14; pbInput
0x18003069b  mov     dword ptr [rsp+130h+pbSecret], ebx; ULONG
0x18003069f  call    ?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z; ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x1800306a4  test    eax, eax
0x1800306a6  jnz     short loc_1800306BF
0x1800306a8  mov     ebx, 80004005h
0x1800306ad  lea     rdx, aEFail; "E_FAIL"
0x1800306b4  mov     r9d, 0D39h
0x1800306ba  jmp     loc_1800307E2
0x1800306bf  mov     ebx, dword ptr [rsp+130h+Size]
0x1800306c3  lea     rcx, [r14+24h]; void *
0x1800306c7  mov     r12, [rsp+130h+Src]
0x1800306cc  mov     r8d, ebx; Size
0x1800306cf  mov     rdx, r12; Src
0x1800306d2  call    memcpy_0
0x1800306d7  mov     ecx, 14h
0x1800306dc  lea     rax, [r14+10h]
0x1800306e0  mov     [rsp+130h+var_E0], ecx; unsigned int
0x1800306e4  lea     r9, [rbp+3Fh+var_88]; pbSecret
0x1800306e8  mov     qword ptr [rsp+130h+var_E8], rax; pbOutput
0x1800306ed  xor     edx, edx; hHash
0x1800306ef  mov     dword ptr [rsp+130h+pcbResult], 0; cbHashObject
0x1800306f7  mov     r8d, 8009h; unsigned int
0x1800306fd  mov     qword ptr [rsp+130h+cbOutput], 0; pbHashObject
0x180030706  mov     [rsp+130h+dwFlags], ebx; cbInput
0x18003070a  mov     qword ptr [rsp+130h+cbSecret], r12; pbInput
0x18003070f  mov     dword ptr [rsp+130h+pbSecret], ecx; ULONG
0x180030713  xor     ecx, ecx; hAlgorithm
0x180030715  call    ?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z; ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x18003071a  test    eax, eax
0x18003071c  jnz     short loc_180030735
0x18003071e  mov     ebx, 80004005h
0x180030723  lea     rdx, aEFail; "E_FAIL"
0x18003072a  mov     r9d, 0D54h
0x180030730  jmp     loc_1800307E2
0x180030735  mov     rcx, [rbp+3Fh+hAlgorithm]; hAlgorithm
0x180030739  lea     rax, [rbp+3Fh+pbOutput]
0x18003073d  mov     [rsp+130h+dwFlags], 0; dwFlags
0x180030745  lea     rdx, [rsp+130h+phKey]; phKey
0x18003074a  mov     [rsp+130h+cbSecret], 14h; cbSecret
0x180030752  xor     r9d, r9d; cbKeyObject
0x180030755  xor     r8d, r8d; pbKeyObject
0x180030758  mov     [rsp+130h+pbSecret], rax; pbSecret
0x18003075d  call    cs:__imp_BCryptGenerateSymmetricKey
0x180030764  nop     dword ptr [rax+rax+00h]
0x180030769  mov     ebx, eax
0x18003076b  test    eax, eax
0x18003076d  jns     short loc_180030777
0x18003076f  mov     r9d, 0D65h
0x180030775  jmp     short loc_1800307DB
0x180030777  mov     rcx, [rsp+130h+phKey]; hKey
0x18003077c  lea     rax, [rsp+130h+Size+4]
0x180030781  mov     [rsp+130h+var_E8], 0; dwFlags
0x180030789  xor     r9d, r9d; pPaddingInfo
0x18003078c  mov     [rsp+130h+pcbResult], rax; pcbResult
0x180030791  mov     r8d, r13d; cbInput
0x180030794  mov     [rsp+130h+cbOutput], r13d; cbOutput
0x180030799  mov     rdx, r14; pbInput
0x18003079c  mov     qword ptr [rsp+130h+dwFlags], r14; pbOutput
0x1800307a1  mov     [rsp+130h+cbSecret], 0; cbIV
0x1800307a9  mov     [rsp+130h+pbSecret], 0; pbIV
0x1800307b2  call    cs:__imp_BCryptEncrypt
0x1800307b9  nop     dword ptr [rax+rax+00h]
0x1800307be  mov     rcx, [rsp+130h+phKey]; hKey
0x1800307c3  mov     ebx, eax
0x1800307c5  call    cs:__imp_BCryptDestroyKey
0x1800307cc  nop     dword ptr [rax+rax+00h]
0x1800307d1  test    ebx, ebx
0x1800307d3  jns     short loc_180030818
0x1800307d5  mov     r9d, 0D78h
0x1800307db  lea     rdx, aNtstatus; "ntStatus"
0x1800307e2  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800307e9  mov     ecx, ebx
0x1800307eb  call    DebugTraceError
0x1800307f0  mov     ecx, r15d
0x1800307f3  mov     rax, rsi
0x1800307f6  test    r15d, r15d
0x1800307f9  jz      short loc_180030807
0x1800307fb  mov     byte ptr [rax], 0
0x1800307fe  inc     rax
0x180030801  sub     rcx, 1
0x180030805  jnz     short loc_1800307FB
0x180030807  mov     rcx, rsi; hMem
0x18003080a  call    cs:__imp_LocalFree
0x180030811  nop     dword ptr [rax+rax+00h]
0x180030816  jmp     short loc_180030828
0x180030818  mov     rax, [rbp+3Fh+var_B0]
0x18003081c  xor     edi, edi
0x18003081e  mov     [rax], rsi
0x180030821  mov     rax, [rbp+3Fh+var_A8]
0x180030825  mov     [rax], r15d
0x180030828  mov     ecx, edi; dwErrCode
0x18003082a  call    cs:__imp_SetLastError
0x180030831  nop     dword ptr [rax+rax+00h]
0x180030836  xor     eax, eax
0x180030838  test    edi, edi
0x18003083a  setz    al
0x18003083d  mov     rcx, [rbp+3Fh+var_48]
0x180030841  xor     rcx, rsp; StackCookie
0x180030844  call    __security_check_cookie
0x180030849  add     rsp, 0F8h
0x180030850  pop     r15
0x180030852  pop     r14
0x180030854  pop     r13
0x180030856  pop     r12
0x180030858  pop     rdi
0x180030859  pop     rsi
0x18003085a  pop     rbx
0x18003085b  pop     rbp
0x18003085c  retn
```
