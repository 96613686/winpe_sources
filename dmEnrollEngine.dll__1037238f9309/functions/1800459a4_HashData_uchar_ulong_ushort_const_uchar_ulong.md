# HashData(uchar *,ulong,ushort const *,uchar * *,ulong *)

- ea: `0x1800459a4`
- end: `0x180045d3c`
- name: `?HashData@@YAJPEAEKPEBGPEAPEAEPEAK@Z`
- size: `920`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, const unsigned __int16 *@<r8>, unsigned __int8 **@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18004bf7c`

## callees

- `0x18000dd20`
- `0x1800140d0`
- `0x180014148`
- `0x1800206a8`
- `0x1800459a4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180045a3c`
- `ntdll!RtlNtStatusToDosError` at `0x180045aa5`
- `ntdll!RtlNtStatusToDosError` at `0x180045b51`
- `ntdll!RtlNtStatusToDosError` at `0x180045bf8`
- `ntdll!RtlNtStatusToDosError` at `0x180045c58`
- `ntdll!RtlNtStatusToDosError` at `0x180045cb5`
- `ntdll!RtlNtStatusToDosError` at `0x180045a3c`
- `ntdll!RtlNtStatusToDosError` at `0x180045aa5`
- `ntdll!RtlNtStatusToDosError` at `0x180045b51`
- `ntdll!RtlNtStatusToDosError` at `0x180045bf8`
- `ntdll!RtlNtStatusToDosError` at `0x180045c58`
- `ntdll!RtlNtStatusToDosError` at `0x180045cb5`
- `bcrypt!BCryptHashData` at `0x180045c35`
- `bcrypt!BCryptHashData` at `0x180045c35`
- `bcrypt!BCryptCreateHash` at `0x180045bd5`
- `bcrypt!BCryptCreateHash` at `0x180045bd5`
- `bcrypt!BCryptGetProperty` at `0x180045a90`
- `bcrypt!BCryptGetProperty` at `0x180045b38`
- `bcrypt!BCryptGetProperty` at `0x180045a90`
- `bcrypt!BCryptGetProperty` at `0x180045b38`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180045a15`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180045a15`
- `bcrypt!BCryptDestroyHash` at `0x180045d07`
- `bcrypt!BCryptDestroyHash` at `0x180045d07`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180045cf8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180045cf8`
- `bcrypt!BCryptFinishHash` at `0x180045c92`
- `bcrypt!BCryptFinishHash` at `0x180045c92`

## pseudocode

```c
__int64 __fastcall HashData(
        PUCHAR pbInput,
        ULONG cbInput,
        const unsigned __int16 *a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  UCHAR *v5; // r14
  UCHAR *v9; // rsi
  int v10; // eax
  int v11; // ebx
  int v12; // eax
  int Property; // eax
  int v14; // ebx
  int v15; // eax
  int v16; // eax
  int v17; // ebx
  int v18; // eax
  unsigned int v19; // edi
  int v20; // eax
  int v21; // ebx
  int v22; // eax
  int v23; // eax
  int v24; // ebx
  int v25; // eax
  int v26; // eax
  int v27; // ebx
  int v28; // eax
  unsigned int *v29; // rax
  unsigned int v30; // ebx
  __int64 v31; // rdx
  ULONG pcbResult; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v34; // [rsp+44h] [rbp-34h] BYREF
  UCHAR pbOutput[4]; // [rsp+48h] [rbp-30h] BYREF
  UCHAR v36[4]; // [rsp+4Ch] [rbp-2Ch] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-28h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v39[3]; // [rsp+60h] [rbp-18h] BYREF
  int v40; // [rsp+D0h] [rbp+58h] BYREF
  int v41; // [rsp+D4h] [rbp+5Ch]

  v41 = HIDWORD(a3);
  v5 = 0;
  v40 = 0;
  phAlgorithm = 0;
  v39[0] = "HashData";
  phHash = 0;
  v39[1] = &v40;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  v34 = 0;
  *(_DWORD *)v36 = 0;
  v9 = 0;
  v10 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( v10 == -1073741559 )
      goto LABEL_4;
    v12 = RtlNtStatusToDosError(v10);
    if ( !v12 || v12 == 317 )
    {
      v12 = v11 | 0x10000000;
    }
    else if ( v12 > 0 )
    {
      v12 = (unsigned __int16)v12 | 0x80070000;
    }
    v40 = v12;
    if ( v12 < 0 )
      goto LABEL_63;
  }
  else
  {
    v40 = 0;
  }
  Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  v14 = Property;
  if ( Property < 0 )
  {
    if ( Property == -1073741559 )
      goto LABEL_4;
    v15 = RtlNtStatusToDosError(Property);
    if ( !v15 || v15 == 317 )
    {
      v15 = v14 | 0x10000000;
    }
    else if ( v15 > 0 )
    {
      v15 = (unsigned __int16)v15 | 0x80070000;
    }
    v40 = v15;
    if ( v15 < 0 )
      goto LABEL_63;
  }
  if ( pcbResult != 4 )
  {
LABEL_20:
    v40 = -2147418113;
    goto LABEL_63;
  }
  v40 = ULongLongToULong(*(unsigned int *)pbOutput, &v34);
  if ( v40 < 0 )
    goto LABEL_63;
  v5 = (UCHAR *)SafeHeapAlloc(v34);
  if ( !v5 )
  {
LABEL_23:
    v40 = -2147024882;
    goto LABEL_63;
  }
  v16 = BCryptGetProperty(phAlgorithm, L"HashDigestLength", v36, 4u, &pcbResult, 0);
  v17 = v16;
  if ( v16 < 0 )
  {
    if ( v16 == -1073741559 )
      goto LABEL_4;
    v18 = RtlNtStatusToDosError(v16);
    if ( !v18 || v18 == 317 )
    {
      v18 = v17 | 0x10000000;
    }
    else if ( v18 > 0 )
    {
      v18 = (unsigned __int16)v18 | 0x80070000;
    }
    v40 = v18;
    if ( v18 < 0 )
      goto LABEL_63;
  }
  if ( pcbResult != 4 )
    goto LABEL_20;
  v40 = ULongLongToULong(*(unsigned int *)v36, &v34);
  if ( v40 < 0 )
    goto LABEL_63;
  v19 = v34;
  v9 = (UCHAR *)SafeHeapAlloc(v34);
  if ( !v9 )
    goto LABEL_23;
  v20 = BCryptCreateHash(phAlgorithm, &phHash, v5, *(ULONG *)pbOutput, 0, 0, 0);
  v21 = v20;
  if ( v20 < 0 )
  {
    if ( v20 == -1073741559 )
      goto LABEL_4;
    v22 = RtlNtStatusToDosError(v20);
    if ( !v22 || v22 == 317 )
    {
      v22 = v21 | 0x10000000;
    }
    else if ( v22 > 0 )
    {
      v22 = (unsigned __int16)v22 | 0x80070000;
    }
    v40 = v22;
    if ( v22 < 0 )
      goto LABEL_63;
  }
  else
  {
    v40 = 0;
  }
  v23 = BCryptHashData(phHash, pbInput, cbInput, 0);
  v24 = v23;
  if ( v23 < 0 )
  {
    if ( v23 == -1073741559 )
      goto LABEL_4;
    v25 = RtlNtStatusToDosError(v23);
    if ( !v25 || v25 == 317 )
    {
      v25 = v24 | 0x10000000;
    }
    else if ( v25 > 0 )
    {
      v25 = (unsigned __int16)v25 | 0x80070000;
    }
    v40 = v25;
    if ( v25 < 0 )
      goto LABEL_63;
  }
  else
  {
    v40 = 0;
  }
  v26 = BCryptFinishHash(phHash, v9, *(ULONG *)v36, 0);
  v27 = v26;
  if ( v26 >= 0 )
  {
    v40 = 0;
LABEL_62:
    v29 = a5;
    *a4 = v9;
    v9 = 0;
    *v29 = v19;
    goto LABEL_63;
  }
  if ( v26 == -1073741559 )
  {
LABEL_4:
    v40 = -2147024579;
    goto LABEL_63;
  }
  v28 = RtlNtStatusToDosError(v26);
  if ( !v28 || v28 == 317 )
  {
    v28 = v27 | 0x10000000;
  }
  else if ( v28 > 0 )
  {
    v28 = (unsigned __int16)v28 | 0x80070000;
  }
  v40 = v28;
  if ( v28 >= 0 )
    goto LABEL_62;
LABEL_63:
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( phHash )
    BCryptDestroyHash(phHash);
  SafeHeapFree(v5);
  SafeHeapFree(v9);
  v30 = v40;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v39, v31);
  return v30;
}

```

## disassembly

```asm
0x1800459a4  mov     [rsp-40h+arg_10], r8
0x1800459a9  push    rbp
0x1800459aa  push    rbx
0x1800459ab  push    rsi
0x1800459ac  push    rdi
0x1800459ad  push    r12
0x1800459af  push    r13
0x1800459b1  push    r14
0x1800459b3  push    r15
0x1800459b5  mov     rbp, rsp
0x1800459b8  sub     rsp, 78h
0x1800459bc  xor     r14d, r14d
0x1800459bf  mov     dword ptr [rbp+arg_10], 0
0x1800459c6  lea     rax, aHashdata; "HashData"
0x1800459cd  mov     [rbp+phAlgorithm], 0
0x1800459d5  mov     [rbp+var_18], rax
0x1800459d9  mov     r13, r9
0x1800459dc  lea     rax, [rbp+arg_10]
0x1800459e0  mov     [rbp+phHash], 0
0x1800459e8  mov     r15d, edx
0x1800459eb  mov     [rbp+var_10], rax
0x1800459ef  mov     r12, rcx
0x1800459f2  mov     dword ptr [rbp+pbOutput], r14d
0x1800459f6  xor     r9d, r9d; dwFlags
0x1800459f9  mov     [rbp+var_38], r14d
0x1800459fd  xor     r8d, r8d; pszImplementation
0x180045a00  mov     [rbp+var_34], r14d
0x180045a04  lea     rdx, aSha256; "SHA256"
0x180045a0b  mov     dword ptr [rbp+var_2C], r14d
0x180045a0f  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180045a13  xor     esi, esi
0x180045a15  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180045a1b  mov     ebx, eax
0x180045a1d  test    eax, eax
0x180045a1f  js      short loc_180045A26
0x180045a21  mov     dword ptr [rbp+arg_10], esi
0x180045a24  jmp     short loc_180045A6C
0x180045a26  cmp     ebx, 0C0000109h
0x180045a2c  jnz     short loc_180045A3A
0x180045a2e  mov     dword ptr [rbp+arg_10], 8007013Dh
0x180045a35  jmp     loc_180045CED
0x180045a3a  mov     ecx, ebx; Status
0x180045a3c  call    cs:__imp_RtlNtStatusToDosError
0x180045a42  test    eax, eax
0x180045a44  jz      short loc_180045A5B
0x180045a46  cmp     eax, 13Dh
0x180045a4b  jz      short loc_180045A5B
0x180045a4d  test    eax, eax
0x180045a4f  jle     short loc_180045A61
0x180045a51  movzx   eax, ax
0x180045a54  or      eax, 80070000h
0x180045a59  jmp     short loc_180045A61
0x180045a5b  mov     eax, ebx
0x180045a5d  bts     eax, 1Ch
0x180045a61  mov     dword ptr [rbp+arg_10], eax
0x180045a64  test    eax, eax
0x180045a66  js      loc_180045CED
0x180045a6c  mov     rcx, [rbp+phAlgorithm]; hObject
0x180045a70  lea     rax, [rbp+var_38]
0x180045a74  mov     edi, 4
0x180045a79  mov     [rsp+78h+dwFlags], esi; dwFlags
0x180045a7d  mov     r9d, edi; cbOutput
0x180045a80  mov     [rsp+78h+pcbResult], rax; pcbResult
0x180045a85  lea     r8, [rbp+pbOutput]; pbOutput
0x180045a89  lea     rdx, aObjectlength; "ObjectLength"
0x180045a90  call    cs:__imp_BCryptGetProperty
0x180045a96  mov     ebx, eax
0x180045a98  test    eax, eax
0x180045a9a  jns     short loc_180045AD5
0x180045a9c  cmp     eax, 0C0000109h
0x180045aa1  jz      short loc_180045A2E
0x180045aa3  mov     ecx, eax; Status
0x180045aa5  call    cs:__imp_RtlNtStatusToDosError
0x180045aab  test    eax, eax
0x180045aad  jz      short loc_180045AC4
0x180045aaf  cmp     eax, 13Dh
0x180045ab4  jz      short loc_180045AC4
0x180045ab6  test    eax, eax
0x180045ab8  jle     short loc_180045ACA
0x180045aba  movzx   eax, ax
0x180045abd  or      eax, 80070000h
0x180045ac2  jmp     short loc_180045ACA
0x180045ac4  mov     eax, ebx
0x180045ac6  bts     eax, 1Ch
0x180045aca  mov     dword ptr [rbp+arg_10], eax
0x180045acd  test    eax, eax
0x180045acf  js      loc_180045CED
0x180045ad5  cmp     [rbp+var_38], edi
0x180045ad8  jz      short loc_180045AE6
0x180045ada  mov     dword ptr [rbp+arg_10], 8000FFFFh
0x180045ae1  jmp     loc_180045CED
0x180045ae6  mov     ecx, dword ptr [rbp+pbOutput]; unsigned __int64
0x180045ae9  lea     rdx, [rbp+var_34]; unsigned int *
0x180045aed  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180045af2  mov     dword ptr [rbp+arg_10], eax
0x180045af5  test    eax, eax
0x180045af7  js      loc_180045CED
0x180045afd  mov     ecx, [rbp+var_34]; unsigned __int64
0x180045b00  call    ?SafeHeapAlloc@@YAPEAX_K@Z; SafeHeapAlloc(unsigned __int64)
0x180045b05  mov     r14, rax
0x180045b08  test    rax, rax
0x180045b0b  jnz     short loc_180045B19
0x180045b0d  mov     dword ptr [rbp+arg_10], 8007000Eh
0x180045b14  jmp     loc_180045CED
0x180045b19  mov     rcx, [rbp+phAlgorithm]; hObject
0x180045b1d  lea     rax, [rbp+var_38]
0x180045b21  mov     [rsp+78h+dwFlags], esi; dwFlags
0x180045b25  lea     r8, [rbp+var_2C]; pbOutput
0x180045b29  mov     r9d, edi; cbOutput
0x180045b2c  mov     [rsp+78h+pcbResult], rax; pcbResult
0x180045b31  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180045b38  call    cs:__imp_BCryptGetProperty
0x180045b3e  mov     ebx, eax
0x180045b40  test    eax, eax
0x180045b42  jns     short loc_180045B81
0x180045b44  cmp     eax, 0C0000109h
0x180045b49  jz      loc_180045A2E
0x180045b4f  mov     ecx, eax; Status
0x180045b51  call    cs:__imp_RtlNtStatusToDosError
0x180045b57  test    eax, eax
0x180045b59  jz      short loc_180045B70
0x180045b5b  cmp     eax, 13Dh
0x180045b60  jz      short loc_180045B70
0x180045b62  test    eax, eax
0x180045b64  jle     short loc_180045B76
0x180045b66  movzx   eax, ax
0x180045b69  or      eax, 80070000h
0x180045b6e  jmp     short loc_180045B76
0x180045b70  mov     eax, ebx
0x180045b72  bts     eax, 1Ch
0x180045b76  mov     dword ptr [rbp+arg_10], eax
0x180045b79  test    eax, eax
0x180045b7b  js      loc_180045CED
0x180045b81  cmp     [rbp+var_38], edi
0x180045b84  jnz     loc_180045ADA
0x180045b8a  mov     ecx, dword ptr [rbp+var_2C]; unsigned __int64
0x180045b8d  lea     rdx, [rbp+var_34]; unsigned int *
0x180045b91  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180045b96  mov     dword ptr [rbp+arg_10], eax
0x180045b99  test    eax, eax
0x180045b9b  js      loc_180045CED
0x180045ba1  mov     edi, [rbp+var_34]
0x180045ba4  mov     ecx, edi; unsigned __int64
0x180045ba6  call    ?SafeHeapAlloc@@YAPEAX_K@Z; SafeHeapAlloc(unsigned __int64)
0x180045bab  mov     rsi, rax
0x180045bae  xor     eax, eax
0x180045bb0  test    rsi, rsi
0x180045bb3  jz      loc_180045B0D
0x180045bb9  mov     r9d, dword ptr [rbp+pbOutput]; cbHashObject
0x180045bbd  lea     rdx, [rbp+phHash]; phHash
0x180045bc1  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180045bc5  mov     r8, r14; pbHashObject
0x180045bc8  mov     [rsp+78h+var_48], eax; dwFlags
0x180045bcc  mov     [rsp+78h+dwFlags], eax; cbSecret
0x180045bd0  mov     [rsp+78h+pcbResult], rax; pbSecret
0x180045bd5  call    cs:__imp_BCryptCreateHash
0x180045bdb  mov     ebx, eax
0x180045bdd  test    eax, eax
0x180045bdf  js      short loc_180045BEA
0x180045be1  mov     dword ptr [rbp+arg_10], 0
0x180045be8  jmp     short loc_180045C28
0x180045bea  cmp     ebx, 0C0000109h
0x180045bf0  jz      loc_180045A2E
0x180045bf6  mov     ecx, ebx; Status
0x180045bf8  call    cs:__imp_RtlNtStatusToDosError
0x180045bfe  test    eax, eax
0x180045c00  jz      short loc_180045C17
0x180045c02  cmp     eax, 13Dh
0x180045c07  jz      short loc_180045C17
0x180045c09  test    eax, eax
0x180045c0b  jle     short loc_180045C1D
0x180045c0d  movzx   eax, ax
0x180045c10  or      eax, 80070000h
0x180045c15  jmp     short loc_180045C1D
0x180045c17  mov     eax, ebx
0x180045c19  bts     eax, 1Ch
0x180045c1d  mov     dword ptr [rbp+arg_10], eax
0x180045c20  test    eax, eax
0x180045c22  js      loc_180045CED
0x180045c28  mov     rcx, [rbp+phHash]; hHash
0x180045c2c  xor     r9d, r9d; dwFlags
0x180045c2f  mov     r8d, r15d; cbInput
0x180045c32  mov     rdx, r12; pbInput
0x180045c35  call    cs:__imp_BCryptHashData
0x180045c3b  mov     ebx, eax
0x180045c3d  test    eax, eax
0x180045c3f  js      short loc_180045C4A
0x180045c41  mov     dword ptr [rbp+arg_10], 0
0x180045c48  jmp     short loc_180045C84
0x180045c4a  cmp     ebx, 0C0000109h
0x180045c50  jz      loc_180045A2E
0x180045c56  mov     ecx, ebx; Status
0x180045c58  call    cs:__imp_RtlNtStatusToDosError
0x180045c5e  test    eax, eax
0x180045c60  jz      short loc_180045C77
0x180045c62  cmp     eax, 13Dh
0x180045c67  jz      short loc_180045C77
0x180045c69  test    eax, eax
0x180045c6b  jle     short loc_180045C7D
0x180045c6d  movzx   eax, ax
0x180045c70  or      eax, 80070000h
0x180045c75  jmp     short loc_180045C7D
0x180045c77  mov     eax, ebx
0x180045c79  bts     eax, 1Ch
0x180045c7d  mov     dword ptr [rbp+arg_10], eax
0x180045c80  test    eax, eax
0x180045c82  js      short loc_180045CED
0x180045c84  mov     r8d, dword ptr [rbp+var_2C]; cbOutput
0x180045c88  xor     r9d, r9d; dwFlags
0x180045c8b  mov     rcx, [rbp+phHash]; hHash
0x180045c8f  mov     rdx, rsi; pbOutput
0x180045c92  call    cs:__imp_BCryptFinishHash
0x180045c98  mov     ebx, eax
0x180045c9a  test    eax, eax
0x180045c9c  js      short loc_180045CA7
0x180045c9e  mov     dword ptr [rbp+arg_10], 0
0x180045ca5  jmp     short loc_180045CE1
0x180045ca7  cmp     ebx, 0C0000109h
0x180045cad  jz      loc_180045A2E
0x180045cb3  mov     ecx, ebx; Status
0x180045cb5  call    cs:__imp_RtlNtStatusToDosError
0x180045cbb  test    eax, eax
0x180045cbd  jz      short loc_180045CD4
0x180045cbf  cmp     eax, 13Dh
0x180045cc4  jz      short loc_180045CD4
0x180045cc6  test    eax, eax
0x180045cc8  jle     short loc_180045CDA
0x180045cca  movzx   eax, ax
0x180045ccd  or      eax, 80070000h
0x180045cd2  jmp     short loc_180045CDA
0x180045cd4  mov     eax, ebx
0x180045cd6  bts     eax, 1Ch
0x180045cda  mov     dword ptr [rbp+arg_10], eax
0x180045cdd  test    eax, eax
0x180045cdf  js      short loc_180045CED
0x180045ce1  mov     rax, [rbp+arg_20]
0x180045ce5  mov     [r13+0], rsi
0x180045ce9  xor     esi, esi
0x180045ceb  mov     [rax], edi
0x180045ced  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180045cf1  test    rcx, rcx
0x180045cf4  jz      short loc_180045CFE
0x180045cf6  xor     edx, edx; dwFlags
0x180045cf8  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180045cfe  mov     rcx, [rbp+phHash]; hHash
0x180045d02  test    rcx, rcx
0x180045d05  jz      short loc_180045D0D
0x180045d07  call    cs:__imp_BCryptDestroyHash
0x180045d0d  mov     rcx, r14; void *
0x180045d10  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x180045d15  mov     rcx, rsi; void *
0x180045d18  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x180045d1d  mov     ebx, dword ptr [rbp+arg_10]
0x180045d20  lea     rcx, [rbp+var_18]; this
0x180045d24  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180045d29  mov     eax, ebx
0x180045d2b  add     rsp, 78h
0x180045d2f  pop     r15
0x180045d31  pop     r14
0x180045d33  pop     r13
0x180045d35  pop     r12
0x180045d37  pop     rdi
0x180045d38  pop     rsi
0x180045d39  pop     rbx
0x180045d3a  pop     rbp
0x180045d3b  retn
```
