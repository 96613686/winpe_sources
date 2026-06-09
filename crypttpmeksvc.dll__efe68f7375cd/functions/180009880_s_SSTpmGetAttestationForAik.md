# s_SSTpmGetAttestationForAik

- ea: `0x180009880`
- end: `0x180009b14`
- name: `s_SSTpmGetAttestationForAik`
- size: `660`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, const WCHAR *, DWORD *, BYTE **, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003750`
- `0x180007d80`
- `0x180008f38`
- `0x180009880`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800098ce`
- `msvcrt!_wcsicmp` at `0x1800098ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800099b8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009a2a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800099b8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009a2a`
- `ncrypt!NCryptExportKey` at `0x180009999`
- `ncrypt!NCryptExportKey` at `0x180009999`
- `ncrypt!NCryptOpenStorageProvider` at `0x180009918`
- `ncrypt!NCryptOpenStorageProvider` at `0x180009918`
- `ncrypt!NCryptCreateClaim` at `0x180009a0f`
- `ncrypt!NCryptCreateClaim` at `0x180009a0f`
- `ncrypt!NCryptFreeObject` at `0x180009ae4`
- `ncrypt!NCryptFreeObject` at `0x180009af3`
- `ncrypt!NCryptFreeObject` at `0x180009ae4`
- `ncrypt!NCryptFreeObject` at `0x180009af3`

## string_xrefs

- `0x180009a6d`: `ERROR: NCryptOpenKey. Return=%x\n`
- `0x180009927`: `ERROR: NCryptOpenStorageProvider. Return=%x\n`
- `0x180009951`: `ERROR: _OpenAikKey. Return=%x\n`

## pseudocode

```c
__int64 __fastcall s_SSTpmGetAttestationForAik(
        __int64 a1,
        const wchar_t *a2,
        const WCHAR *a3,
        DWORD *a4,
        BYTE **a5,
        _DWORD *a6,
        _QWORD *a7)
{
  unsigned int Claim; // ebx
  unsigned int v11; // eax
  unsigned int v12; // eax
  BYTE *pbOutput; // rdi
  DWORD cbOutput; // r14d
  SECURITY_STATUS v15; // eax
  __int64 v16; // r9
  unsigned int v17; // ecx
  const char *v18; // r8
  HLOCAL v19; // rsi
  NCRYPT_KEY_HANDLE hKey; // [rsp+48h] [rbp-18h] BYREF
  NCRYPT_PROV_HANDLE phProvider[2]; // [rsp+50h] [rbp-10h] BYREF
  DWORD pcbResult; // [rsp+90h] [rbp+30h] BYREF

  phProvider[0] = 0;
  hKey = 0;
  if ( a1 && a2 )
  {
    if ( _wcsicmp(a2, L"Microsoft Platform Crypto Provider") )
    {
      Claim = 160;
      ekTraceFmt(0xEEA12C2u, 1u, "ERROR: Invalid KSP.Ksp=%ws Return=%d\n", a2, 160);
    }
    else
    {
      v11 = NCryptOpenStorageProvider(phProvider, L"Microsoft Platform Crypto Provider", 0x40u);
      Claim = v11;
      if ( v11 )
      {
        ekTraceFmt(0xEF412C2u, 1u, "ERROR: NCryptOpenStorageProvider. Return=%x\n", v11);
      }
      else
      {
        v12 = _OpenAikKey(phProvider[0], a3, &hKey);
        Claim = v12;
        if ( v12 )
        {
          ekTraceFmt(0xEFE12C2u, 1u, "ERROR: _OpenAikKey. Return=%x\n", v12);
        }
        else
        {
          pbOutput = 0;
          cbOutput = 0;
          while ( 1 )
          {
            pcbResult = 0;
            v15 = NCryptExportKey(hKey, 0, L"RSAPUBLICBLOB", 0, pbOutput, cbOutput, &pcbResult, 0);
            Claim = v15;
            if ( v15 )
              break;
            if ( pbOutput )
            {
              v19 = 0;
              while ( 1 )
              {
                Claim = NCryptCreateClaim(hKey, 0, 1);
                if ( Claim )
                  break;
                if ( v19 )
                {
                  Claim = 0;
                  *a7 = v19;
                  *a6 = 0;
                  *a5 = pbOutput;
                  *a4 = cbOutput;
                  goto LABEL_28;
                }
                v19 = LocalAlloc(0x40u, 0);
                if ( !v19 )
                {
                  Claim += 14;
                  ekTraceFmt(0xF3D12C2u, 1u, "ERROR: MIDL_user_allocate. Return=%d\n");
                  goto LABEL_24;
                }
              }
              ekTraceFmt(0xF3112C2u, 1u, "ERROR: NCryptOpenKey. Return=%x\n");
              goto LABEL_24;
            }
            cbOutput = pcbResult;
            pbOutput = (BYTE *)LocalAlloc(0x40u, pcbResult);
            if ( !pbOutput )
            {
              v16 = Claim + 14;
              v17 = 253563586;
              v18 = "ERROR: MIDL_user_allocate. Return=%d\n";
              goto LABEL_27;
            }
          }
          ekTraceFmt(0xF1112C2u, 1u, "ERROR: NCryptExportKey. Return=%x\n", v15);
          if ( !pbOutput )
            goto LABEL_28;
          v19 = 0;
LABEL_24:
          MIDL_user_free(pbOutput);
          if ( v19 )
            MIDL_user_free(v19);
        }
      }
    }
  }
  else
  {
    v16 = 160;
    v18 = "ERROR: Arguments. Return=%d\n";
    v17 = 249762498;
LABEL_27:
    Claim = v16;
    ekTraceFmt(v17, 1u, v18, v16);
  }
LABEL_28:
  if ( hKey )
    NCryptFreeObject(hKey);
  if ( phProvider[0] )
    NCryptFreeObject(phProvider[0]);
  return Claim;
}

```

## disassembly

```asm
0x180009880  mov     [rsp-28h+arg_8], rbx
0x180009885  mov     [rsp-28h+arg_10], rsi
0x18000988a  push    rbp
0x18000988b  push    rdi
0x18000988c  push    r12
0x18000988e  push    r14
0x180009890  push    r15
0x180009892  mov     rbp, rsp
0x180009895  sub     rsp, 60h
0x180009899  mov     [rbp+phProvider], 0
0x1800098a1  mov     r12, r9
0x1800098a4  mov     [rbp+hKey], 0
0x1800098ac  mov     rsi, r8
0x1800098af  mov     rdi, rdx
0x1800098b2  test    rcx, rcx
0x1800098b5  jz      loc_180009ABC
0x1800098bb  test    rdx, rdx
0x1800098be  jz      loc_180009ABC
0x1800098c4  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x1800098cb  mov     rcx, rdi; String1
0x1800098ce  call    cs:__imp__wcsicmp
0x1800098d4  test    eax, eax
0x1800098d6  jz      short loc_180009904
0x1800098d8  mov     r9d, 0A0h
0x1800098de  lea     r8, aErrorInvalidKs; "ERROR: Invalid KSP.Ksp=%ws Return=%d\n"
0x1800098e5  mov     ebx, r9d
0x1800098e8  mov     dword ptr [rsp+60h+pbOutput], r9d
0x1800098ed  mov     r9, rdi
0x1800098f0  mov     edx, 1; unsigned int
0x1800098f5  mov     ecx, 0EEA12C2h; unsigned int
0x1800098fa  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800098ff  jmp     loc_180009ADB
0x180009904  mov     r15d, 40h ; '@'
0x18000990a  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x180009911  mov     r8d, r15d; dwFlags
0x180009914  lea     rcx, [rbp+phProvider]; phProvider
0x180009918  call    cs:__imp_NCryptOpenStorageProvider
0x18000991e  mov     ebx, eax
0x180009920  test    eax, eax
0x180009922  jz      short loc_180009938
0x180009924  mov     r9d, eax
0x180009927  lea     r8, aErrorNcryptope_1; "ERROR: NCryptOpenStorageProvider. Retur"...
0x18000992e  mov     ecx, 0EF412C2h
0x180009933  jmp     loc_180009AD1
0x180009938  mov     rcx, [rbp+phProvider]; hProvider
0x18000993c  lea     r8, [rbp+hKey]; phKey
0x180009940  mov     rdx, rsi; pszKeyName
0x180009943  call    ?_OpenAikKey@@YAK_KPEBGPEA_K@Z; _OpenAikKey(unsigned __int64,ushort const *,unsigned __int64 *)
0x180009948  mov     ebx, eax
0x18000994a  test    eax, eax
0x18000994c  jz      short loc_180009962
0x18000994e  mov     r9d, eax
0x180009951  lea     r8, aErrorOpenaikke_0; "ERROR: _OpenAikKey. Return=%x\n"
0x180009958  mov     ecx, 0EFE12C2h
0x18000995d  jmp     loc_180009AD1
0x180009962  xor     edi, edi
0x180009964  xor     r14d, r14d
0x180009967  mov     rcx, [rbp+hKey]; hKey
0x18000996b  lea     rax, [rbp+arg_0]
0x18000996f  mov     [rsp+60h+dwFlags], 0; dwFlags
0x180009977  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x18000997e  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180009983  xor     r9d, r9d; pParameterList
0x180009986  mov     [rsp+60h+cbOutput], r14d; cbOutput
0x18000998b  xor     edx, edx; hExportKey
0x18000998d  mov     [rsp+60h+pbOutput], rdi; pbOutput
0x180009992  mov     [rbp+arg_0], 0
0x180009999  call    cs:__imp_NCryptExportKey
0x18000999f  mov     ebx, eax
0x1800099a1  test    eax, eax
0x1800099a3  jnz     loc_180009A85
0x1800099a9  test    rdi, rdi
0x1800099ac  jnz     short loc_1800099DB
0x1800099ae  mov     r14d, [rbp+arg_0]
0x1800099b2  mov     ecx, r15d; uFlags
0x1800099b5  mov     edx, r14d; uBytes
0x1800099b8  call    cs:__imp_LocalAlloc
0x1800099be  mov     rdi, rax
0x1800099c1  test    rax, rax
0x1800099c4  jnz     short loc_180009967
0x1800099c6  lea     r9d, [rbx+0Eh]
0x1800099ca  mov     ecx, 0F1D12C2h
0x1800099cf  lea     r8, aErrorMidlUserA_0; "ERROR: MIDL_user_allocate. Return=%d\n"
0x1800099d6  jmp     loc_180009ACE
0x1800099db  xor     esi, esi
0x1800099dd  xor     r15d, r15d
0x1800099e0  mov     rcx, [rbp+hKey]
0x1800099e4  lea     rax, [rbp+uBytes]
0x1800099e8  mov     [rsp+60h+dwFlags], 0
0x1800099f0  xor     r9d, r9d
0x1800099f3  mov     [rsp+60h+pcbResult], rax
0x1800099f8  xor     edx, edx
0x1800099fa  mov     [rsp+60h+cbOutput], r15d
0x1800099ff  mov     dword ptr [rbp+uBytes], 0
0x180009a06  lea     r8d, [r9+1]
0x180009a0a  mov     [rsp+60h+pbOutput], rsi
0x180009a0f  call    cs:__imp_NCryptCreateClaim
0x180009a15  mov     ebx, eax
0x180009a17  test    eax, eax
0x180009a19  jnz     short loc_180009A6A
0x180009a1b  test    rsi, rsi
0x180009a1e  jnz     short loc_180009A4D
0x180009a20  mov     r15d, dword ptr [rbp+uBytes]
0x180009a24  lea     ecx, [rsi+40h]; uFlags
0x180009a27  mov     edx, r15d; uBytes
0x180009a2a  call    cs:__imp_LocalAlloc
0x180009a30  mov     rsi, rax
0x180009a33  test    rax, rax
0x180009a36  jnz     short loc_1800099E0
0x180009a38  lea     r9d, [rbx+0Eh]
0x180009a3c  mov     ecx, 0F3D12C2h
0x180009a41  mov     ebx, r9d
0x180009a44  lea     r8, aErrorMidlUserA_0; "ERROR: MIDL_user_allocate. Return=%d\n"
0x180009a4b  jmp     short loc_180009A79
0x180009a4d  mov     rax, [rbp+arg_30]
0x180009a51  xor     ebx, ebx
0x180009a53  mov     [rax], rsi
0x180009a56  mov     rax, [rbp+arg_28]
0x180009a5a  mov     [rax], r15d
0x180009a5d  mov     rax, [rbp+arg_20]
0x180009a61  mov     [rax], rdi
0x180009a64  mov     [r12], r14d
0x180009a68  jmp     short loc_180009ADB
0x180009a6a  mov     r9d, eax
0x180009a6d  lea     r8, aErrorNcryptope_0; "ERROR: NCryptOpenKey. Return=%x\n"
0x180009a74  mov     ecx, 0F3112C2h; unsigned int
0x180009a79  mov     edx, 1; unsigned int
0x180009a7e  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180009a83  jmp     short loc_180009AA5
0x180009a85  mov     r9d, eax
0x180009a88  lea     r8, aErrorNcryptexp; "ERROR: NCryptExportKey. Return=%x\n"
0x180009a8f  mov     edx, 1; unsigned int
0x180009a94  mov     ecx, 0F1112C2h; unsigned int
0x180009a99  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180009a9e  test    rdi, rdi
0x180009aa1  jz      short loc_180009ADB
0x180009aa3  xor     esi, esi
0x180009aa5  mov     rcx, rdi; void *
0x180009aa8  call    MIDL_user_free
0x180009aad  test    rsi, rsi
0x180009ab0  jz      short loc_180009ADB
0x180009ab2  mov     rcx, rsi; void *
0x180009ab5  call    MIDL_user_free
0x180009aba  jmp     short loc_180009ADB
0x180009abc  mov     r9d, 0A0h
0x180009ac2  lea     r8, aErrorArguments; "ERROR: Arguments. Return=%d\n"
0x180009ac9  mov     ecx, 0EE312C2h; unsigned int
0x180009ace  mov     ebx, r9d
0x180009ad1  mov     edx, 1; unsigned int
0x180009ad6  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180009adb  mov     rcx, [rbp+hKey]; hObject
0x180009adf  test    rcx, rcx
0x180009ae2  jz      short loc_180009AEA
0x180009ae4  call    cs:__imp_NCryptFreeObject
0x180009aea  mov     rcx, [rbp+phProvider]; hObject
0x180009aee  test    rcx, rcx
0x180009af1  jz      short loc_180009AF9
0x180009af3  call    cs:__imp_NCryptFreeObject
0x180009af9  lea     r11, [rsp+60h+var_s0]
0x180009afe  mov     eax, ebx
0x180009b00  mov     rbx, [r11+38h]
0x180009b04  mov     rsi, [r11+40h]
0x180009b08  mov     rsp, r11
0x180009b0b  pop     r15
0x180009b0d  pop     r14
0x180009b0f  pop     r12
0x180009b11  pop     rdi
0x180009b12  pop     rbp
0x180009b13  retn
```
