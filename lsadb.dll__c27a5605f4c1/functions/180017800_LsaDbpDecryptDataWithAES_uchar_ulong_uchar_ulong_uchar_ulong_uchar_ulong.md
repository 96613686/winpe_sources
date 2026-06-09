# LsaDbpDecryptDataWithAES(uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180017800`
- end: `0x180017a82`
- name: `?LsaDbpDecryptDataWithAES@@YAJPEAEK0K0KPEAPEAEPEAK@Z`
- size: `642`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, PUCHAR pbIV@<r8>, unsigned int@<r9d>, unsigned __int8 *, ULONG cbSecret, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180017018`

## callees

- `0x180001670`
- `0x18000fd18`
- `0x18000fd40`
- `0x180017800`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017998`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017998`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017a0e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017a0e`
- `bcrypt!BCryptDecrypt` at `0x180017984`
- `bcrypt!BCryptDecrypt` at `0x1800179e8`
- `bcrypt!BCryptDecrypt` at `0x180017984`
- `bcrypt!BCryptDecrypt` at `0x1800179e8`
- `bcrypt!BCryptGetProperty` at `0x1800178d8`
- `bcrypt!BCryptGetProperty` at `0x1800178d8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180017a2e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180017a2e`
- `bcrypt!BCryptDestroyKey` at `0x180017a1d`
- `bcrypt!BCryptDestroyKey` at `0x180017a1d`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180017940`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180017940`
- `bcrypt!BCryptSetProperty` at `0x18001790e`
- `bcrypt!BCryptSetProperty` at `0x18001790e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800178a6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800178a6`

## pseudocode

```c
__int64 __fastcall LsaDbpDecryptDataWithAES(
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR pbIV,
        __int64 a4,
        unsigned __int8 *a5,
        ULONG cbSecret,
        unsigned __int8 **a7,
        unsigned int *a8)
{
  UCHAR *v8; // rdi
  NTSTATUS Property; // ebx
  ULONG cbOutput; // [rsp+50h] [rbp-49h] BYREF
  UCHAR pbOutput[4]; // [rsp+54h] [rbp-45h] BYREF
  ULONG v16; // [rsp+58h] [rbp-41h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp-39h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+68h] [rbp-31h] BYREF
  ULONG pcbResult; // [rsp+70h] [rbp-29h] BYREF
  PUCHAR pbSecret; // [rsp+78h] [rbp-21h]
  UCHAR pbIVa[16]; // [rsp+80h] [rbp-19h] BYREF

  v8 = 0;
  pbSecret = a5;
  phAlgorithm = 0;
  phKey = 0;
  pcbResult = 0;
  cbOutput = 0;
  *(_OWORD *)pbIVa = 0;
  v16 = 0;
  *(_DWORD *)pbOutput = 16;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids);
  *a8 = 0;
  *a7 = 0;
  *(_OWORD *)pbIVa = *(_OWORD *)pbIV;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", 0, 0);
  if ( Property >= 0 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"BlockLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property >= 0 && *(_DWORD *)pbOutput == 16 )
    {
      Property = BCryptSetProperty(phAlgorithm, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
      if ( Property >= 0 )
      {
        Property = BCryptGenerateSymmetricKey(phAlgorithm, &phKey, 0, 0, pbSecret, cbSecret, 0);
        if ( Property >= 0 )
        {
          Property = BCryptDecrypt(phKey, pbInput, cbInput, 0, pbIV, 0x10u, 0, 0, &cbOutput, 1u);
          if ( Property >= 0 )
          {
            v8 = (UCHAR *)LocalAlloc(0x40u, cbOutput);
            if ( v8 )
            {
              Property = BCryptDecrypt(phKey, pbInput, cbInput, 0, pbIVa, 0x10u, v8, cbOutput, &v16, 1u);
              if ( Property >= 0 )
              {
                if ( v16 <= cbOutput )
                {
                  *a8 = v16;
                  *a7 = v8;
                  v8 = 0;
                }
                else
                {
                  Property = -1073741811;
                }
              }
            }
            else
            {
              Property = -1073741670;
            }
          }
        }
      }
    }
  }
  LocalFree(v8);
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      63,
      &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids,
      (unsigned int)Property);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x180017800  mov     [rsp-8+arg_18], rbx
0x180017805  push    rbp
0x180017806  push    rsi
0x180017807  push    rdi
0x180017808  push    r12
0x18001780a  push    r13
0x18001780c  push    r14
0x18001780e  push    r15
0x180017810  lea     rbp, [rsp-7]
0x180017815  sub     rsp, 0A0h
0x18001781c  mov     rax, cs:__security_cookie
0x180017823  xor     rax, rsp
0x180017826  mov     [rbp+37h+var_40], rax
0x18001782a  mov     rax, [rbp+37h+arg_20]
0x18001782e  xor     ebx, ebx
0x180017830  mov     rsi, [rbp+37h+arg_30]
0x180017834  xorps   xmm0, xmm0
0x180017837  mov     r14, [rbp+37h+arg_38]
0x18001783b  mov     edi, ebx
0x18001783d  mov     [rbp+37h+pbSecret], rax
0x180017841  mov     r15, r8
0x180017844  mov     [rbp+37h+phAlgorithm], rbx
0x180017848  mov     r13d, edx
0x18001784b  mov     [rbp+37h+phKey], rbx
0x18001784f  mov     r12, rcx
0x180017852  mov     [rbp+37h+var_60], ebx
0x180017855  mov     [rbp+37h+var_80], ebx
0x180017858  movups  xmmword ptr [rbp+37h+pbIV], xmm0
0x18001785c  mov     [rbp+37h+var_78], ebx
0x18001785f  mov     dword ptr [rbp+37h+pbOutput], 10h
0x180017866  mov     rcx, cs:WPP_GLOBAL_Control
0x18001786d  test    byte ptr [rcx+1Ch], 2
0x180017871  jz      short loc_180017886
0x180017873  mov     rcx, [rcx+10h]
0x180017877  lea     edx, [rbx+3Eh]
0x18001787a  lea     r8, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x180017881  call    WPP_SF_
0x180017886  mov     [r14], ebx
0x180017889  lea     rdx, aAes; "AES"
0x180017890  mov     [rsi], rbx
0x180017893  lea     rcx, [rbp+37h+phAlgorithm]; phAlgorithm
0x180017897  movups  xmm0, xmmword ptr [r15]
0x18001789b  xor     r9d, r9d; dwFlags
0x18001789e  xor     r8d, r8d; pszImplementation
0x1800178a1  movdqu  xmmword ptr [rbp+37h+pbIV], xmm0
0x1800178a6  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800178ac  mov     ebx, eax
0x1800178ae  test    eax, eax
0x1800178b0  js      loc_180017A0B
0x1800178b6  mov     rcx, [rbp+37h+phAlgorithm]; hObject
0x1800178ba  lea     rax, [rbp+37h+var_60]
0x1800178be  mov     [rsp+0D0h+dwFlags], edi; dwFlags
0x1800178c2  lea     r8, [rbp+37h+pbOutput]; pbOutput
0x1800178c6  mov     r9d, 4; cbOutput
0x1800178cc  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x1800178d1  lea     rdx, aBlocklength; "BlockLength"
0x1800178d8  call    cs:__imp_BCryptGetProperty
0x1800178de  mov     ebx, eax
0x1800178e0  test    eax, eax
0x1800178e2  js      loc_180017A0B
0x1800178e8  cmp     dword ptr [rbp+37h+pbOutput], 10h
0x1800178ec  jnz     loc_180017A0B
0x1800178f2  mov     rcx, [rbp+37h+phAlgorithm]; hObject
0x1800178f6  lea     r8, pbInput; "ChainingModeCBC"
0x1800178fd  mov     r9d, 20h ; ' '; cbInput
0x180017903  mov     dword ptr [rsp+0D0h+pcbResult], edi; dwFlags
0x180017907  lea     rdx, aChainingmode; "ChainingMode"
0x18001790e  call    cs:__imp_BCryptSetProperty
0x180017914  mov     ebx, eax
0x180017916  test    eax, eax
0x180017918  js      loc_180017A0B
0x18001791e  mov     eax, [rbp+37h+cbSecret]
0x180017921  lea     rdx, [rbp+37h+phKey]; phKey
0x180017925  mov     rcx, [rbp+37h+phAlgorithm]; hAlgorithm
0x180017929  xor     r9d, r9d; cbKeyObject
0x18001792c  mov     [rsp+0D0h+var_A0], edi; dwFlags
0x180017930  xor     r8d, r8d; pbKeyObject
0x180017933  mov     [rsp+0D0h+dwFlags], eax; cbSecret
0x180017937  mov     rax, [rbp+37h+pbSecret]
0x18001793b  mov     [rsp+0D0h+pcbResult], rax; pbSecret
0x180017940  call    cs:__imp_BCryptGenerateSymmetricKey
0x180017946  mov     ebx, eax
0x180017948  test    eax, eax
0x18001794a  js      loc_180017A0B
0x180017950  mov     rcx, [rbp+37h+phKey]; hKey
0x180017954  lea     rax, [rbp+37h+var_80]
0x180017958  mov     [rsp+0D0h+var_88], 1; dwFlags
0x180017960  xor     r9d, r9d; pPaddingInfo
0x180017963  mov     [rsp+0D0h+var_90], rax; pcbResult
0x180017968  mov     r8d, r13d; cbInput
0x18001796b  mov     [rsp+0D0h+cbOutput], edi; cbOutput
0x18001796f  mov     rdx, r12; pbInput
0x180017972  mov     qword ptr [rsp+0D0h+var_A0], rdi; pbOutput
0x180017977  mov     [rsp+0D0h+dwFlags], 10h; cbIV
0x18001797f  mov     [rsp+0D0h+pcbResult], r15; pbIV
0x180017984  call    cs:__imp_BCryptDecrypt
0x18001798a  mov     ebx, eax
0x18001798c  test    eax, eax
0x18001798e  js      short loc_180017A0B
0x180017990  mov     edx, [rbp+37h+var_80]; uBytes
0x180017993  mov     ecx, 40h ; '@'; uFlags
0x180017998  call    cs:__imp_LocalAlloc
0x18001799e  mov     rdi, rax
0x1800179a1  test    rax, rax
0x1800179a4  jnz     short loc_1800179AD
0x1800179a6  mov     ebx, 0C000009Ah
0x1800179ab  jmp     short loc_180017A0B
0x1800179ad  mov     rcx, [rbp+37h+phKey]; hKey
0x1800179b1  lea     rax, [rbp+37h+var_78]
0x1800179b5  mov     [rsp+0D0h+var_88], 1; dwFlags
0x1800179bd  xor     r9d, r9d; pPaddingInfo
0x1800179c0  mov     [rsp+0D0h+var_90], rax; pcbResult
0x1800179c5  mov     r8d, r13d; cbInput
0x1800179c8  mov     eax, [rbp+37h+var_80]
0x1800179cb  mov     rdx, r12; pbInput
0x1800179ce  mov     [rsp+0D0h+cbOutput], eax; cbOutput
0x1800179d2  lea     rax, [rbp+37h+pbIV]
0x1800179d6  mov     qword ptr [rsp+0D0h+var_A0], rdi; pbOutput
0x1800179db  mov     [rsp+0D0h+dwFlags], 10h; cbIV
0x1800179e3  mov     [rsp+0D0h+pcbResult], rax; pbIV
0x1800179e8  call    cs:__imp_BCryptDecrypt
0x1800179ee  mov     ebx, eax
0x1800179f0  test    eax, eax
0x1800179f2  js      short loc_180017A0B
0x1800179f4  mov     eax, [rbp+37h+var_78]
0x1800179f7  cmp     eax, [rbp+37h+var_80]
0x1800179fa  jbe     short loc_180017A03
0x1800179fc  mov     ebx, 0C000000Dh
0x180017a01  jmp     short loc_180017A0B
0x180017a03  mov     [r14], eax
0x180017a06  mov     [rsi], rdi
0x180017a09  xor     edi, edi
0x180017a0b  mov     rcx, rdi; hMem
0x180017a0e  call    cs:__imp_LocalFree
0x180017a14  mov     rcx, [rbp+37h+phKey]; hKey
0x180017a18  test    rcx, rcx
0x180017a1b  jz      short loc_180017A23
0x180017a1d  call    cs:__imp_BCryptDestroyKey
0x180017a23  mov     rcx, [rbp+37h+phAlgorithm]; hAlgorithm
0x180017a27  test    rcx, rcx
0x180017a2a  jz      short loc_180017A34
0x180017a2c  xor     edx, edx; dwFlags
0x180017a2e  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180017a34  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a3b  test    byte ptr [rcx+1Ch], 2
0x180017a3f  jz      short loc_180017A59
0x180017a41  mov     rcx, [rcx+10h]
0x180017a45  lea     r8, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x180017a4c  mov     edx, 3Fh ; '?'
0x180017a51  mov     r9d, ebx
0x180017a54  call    WPP_SF_d
0x180017a59  mov     eax, ebx
0x180017a5b  mov     rcx, [rbp+37h+var_40]
0x180017a5f  xor     rcx, rsp; StackCookie
0x180017a62  call    __security_check_cookie
0x180017a67  mov     rbx, [rsp+0D0h+arg_18]
0x180017a6f  add     rsp, 0A0h
0x180017a76  pop     r15
0x180017a78  pop     r14
0x180017a7a  pop     r13
0x180017a7c  pop     r12
0x180017a7e  pop     rdi
0x180017a7f  pop     rsi
0x180017a80  pop     rbp
0x180017a81  retn
```
