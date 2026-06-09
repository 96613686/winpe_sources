# ShouldBlockMsg(ushort const *,ushort const *,OMADMINITIATIONINFO * const,STRUCTMEMBERDATA * const,ulong,bool *)

- ea: `0x18001f690`
- end: `0x18001fa32`
- name: `?ShouldBlockMsg@@YAJPEBG0QEAUOMADMINITIATIONINFO@@QEAUSTRUCTMEMBERDATA@@KPEA_N@Z`
- size: `930`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, const unsigned __int16 *@<rdx>, struct OMADMINITIATIONINFO *const@<r8>, struct STRUCTMEMBERDATA *const@<r9>, unsigned int, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180019684`

## callees

- `0x1800031b0`
- `0x180003db8`
- `0x180011b98`
- `0x18001e910`
- `0x18001eb20`
- `0x18001f690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f767`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f748`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f748`
- `bcrypt!BCryptHashData` at `0x18001f807`
- `bcrypt!BCryptHashData` at `0x18001f87e`
- `bcrypt!BCryptHashData` at `0x18001f8f1`
- `bcrypt!BCryptHashData` at `0x18001f807`
- `bcrypt!BCryptHashData` at `0x18001f87e`
- `bcrypt!BCryptHashData` at `0x18001f8f1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001fa04`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001fa04`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001f716`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001f716`
- `bcrypt!BCryptCreateHash` at `0x18001f797`
- `bcrypt!BCryptCreateHash` at `0x18001f797`
- `bcrypt!BCryptDestroyHash` at `0x18001f759`
- `bcrypt!BCryptDestroyHash` at `0x18001f9eb`
- `bcrypt!BCryptDestroyHash` at `0x18001f759`
- `bcrypt!BCryptDestroyHash` at `0x18001f9eb`
- `bcrypt!BCryptFinishHash` at `0x18001f93e`
- `bcrypt!BCryptFinishHash` at `0x18001f93e`
- `DMCmnUtils!BinaryToHexString` at `0x18001f986`
- `DMCmnUtils!BinaryToHexString` at `0x18001f986`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ShouldBlockMsg(
        PUCHAR pbInput,
        const unsigned __int16 *a2,
        struct OMADMINITIATIONINFO *const a3,
        struct STRUCTMEMBERDATA *const a4,
        unsigned int a5,
        bool *a6)
{
  bool *v8; // r15
  NTSTATUS v9; // eax
  unsigned int v10; // r8d
  __int64 v11; // rdx
  signed int v12; // ebx
  DWORD LastError; // ebx
  __int64 v14; // rcx
  PUCHAR v15; // rax
  unsigned int v16; // r14d
  unsigned __int64 v17; // rdi
  unsigned int v18; // r15d
  struct STRUCTMEMBERDATA *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdx
  UCHAR *v22; // rdx
  __int64 v23; // rcx
  UCHAR *v24; // rax
  __int64 v25; // rdx
  unsigned __int64 v26; // rdx
  int pbSecret; // [rsp+20h] [rbp-E0h]
  bool v29; // [rsp+40h] [rbp-C0h] BYREF
  BCRYPT_HASH_HANDLE hHash; // [rsp+48h] [rbp-B8h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-B0h] BYREF
  UCHAR pbInputa[4]; // [rsp+58h] [rbp-A8h] BYREF
  int v33; // [rsp+5Ch] [rbp-A4h] BYREF
  struct STRUCTMEMBERDATA *v34; // [rsp+60h] [rbp-A0h]
  bool *v35; // [rsp+68h] [rbp-98h]
  UCHAR pbOutput[16]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v37; // [rsp+80h] [rbp-80h]
  WCHAR ValueName[72]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v34 = a4;
  v8 = a6;
  v35 = a6;
  v29 = 0;
  *(_DWORD *)pbInputa = 0;
  hHash = 0;
  *(_OWORD *)pbOutput = 0;
  v37 = 0;
  memset_0(ValueName, 0, 0x82u);
  *a6 = 0;
  phAlgorithm = 0;
  v9 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( v9 < 0 )
  {
    v11 = 487;
    goto LABEL_3;
  }
  if ( hHash )
  {
    LastError = GetLastError();
    BCryptDestroyHash(hHash);
    SetLastError(LastError);
  }
  hHash = 0;
  v9 = BCryptCreateHash(phAlgorithm, &hHash, 0, 0, 0, 0, 0);
  if ( v9 < 0 )
  {
    v11 = 490;
    goto LABEL_3;
  }
  if ( !pbInput )
  {
    v12 = -2147024809;
LABEL_41:
    v25 = 495;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmapi\\src\\throttling.cpp",
      (const char *)(unsigned int)v12,
      pbSecret);
    goto LABEL_43;
  }
  v14 = 0x3FFFFFFF;
  v15 = pbInput;
  do
  {
    if ( !*(_WORD *)v15 )
      break;
    v15 += 2;
    --v14;
  }
  while ( v14 );
  v12 = v14 == 0 ? 0x80070057 : 0;
  if ( !v14 )
    goto LABEL_41;
  v9 = BCryptHashData(hHash, pbInput, v14 != 0 ? 2 * (0x3FFFFFFF - v14) : 0, 0);
  if ( v9 < 0 )
  {
    v11 = 498;
    goto LABEL_3;
  }
  v16 = 0;
  if ( !*((_DWORD *)a3 + 8) )
    goto LABEL_31;
  do
  {
    v17 = *((_QWORD *)a3 + 3) + ((unsigned __int64)v16 << 6);
    v18 = 0;
    if ( a5 )
    {
      v19 = v34;
      while ( 1 )
      {
        v20 = 32LL * v18;
        v21 = *(unsigned int *)((char *)v19 + v20 + 20);
        if ( *(_DWORD *)((char *)v19 + v20 + 16) == 4 )
          break;
        v22 = *(UCHAR **)(v21 + v17);
        if ( v22 )
        {
          v23 = 0x3FFFFFFF;
          v24 = v22;
          do
          {
            if ( !*(_WORD *)v24 )
              break;
            v24 += 2;
            --v23;
          }
          while ( v23 );
          v12 = v23 == 0 ? 0x80070057 : 0;
          if ( !v23 )
          {
            v25 = 519;
            goto LABEL_42;
          }
          v9 = BCryptHashData(hHash, v22, v23 != 0 ? 2 * (0x3FFFFFFF - v23) : 0, 0);
          v10 = 0;
          if ( v9 < 0 )
          {
            v11 = 522;
            goto LABEL_3;
          }
          goto LABEL_27;
        }
LABEL_28:
        if ( ++v18 >= a5 )
          goto LABEL_29;
      }
      *(_DWORD *)pbInputa = *(_DWORD *)(v21 + v17);
      v9 = BCryptHashData(hHash, pbInputa, 4u, 0);
      v10 = 0;
      if ( v9 < 0 )
      {
        v11 = 510;
        goto LABEL_3;
      }
LABEL_27:
      v19 = v34;
      goto LABEL_28;
    }
LABEL_29:
    ++v16;
  }
  while ( v16 < *((_DWORD *)a3 + 8) );
  v8 = v35;
LABEL_31:
  v9 = BCryptFinishHash(hHash, pbOutput, 0x20u, 0);
  if ( v9 >= 0 )
  {
    v33 = 65;
    pbSecret = 0;
    v12 = BinaryToHexString(pbOutput, 32, ValueName, &v33);
    if ( v12 >= 0 )
    {
      v12 = IsRepeatingMsg(ValueName, v26, &v29);
      if ( v12 >= 0 )
      {
        *v8 = v29;
        goto LABEL_43;
      }
      v25 = 537;
    }
    else
    {
      v25 = 533;
    }
    goto LABEL_42;
  }
  v11 = 529;
LABEL_3:
  v12 = wil::details::in1diag3::Return_NtStatus(retaddr, (void *)v11, v10, (const char *)(unsigned int)v9, pbSecret);
LABEL_43:
  if ( hHash )
    BCryptDestroyHash(hHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001f690  push    rbp
0x18001f692  push    rbx
0x18001f693  push    rdi
0x18001f694  push    r12
0x18001f696  push    r13
0x18001f698  push    r14
0x18001f69a  push    r15
0x18001f69c  lea     rbp, [rsp-30h]
0x18001f6a1  sub     rsp, 130h
0x18001f6a8  mov     rax, cs:__security_cookie
0x18001f6af  xor     rax, rsp
0x18001f6b2  mov     [rbp+60h+var_40], rax
0x18001f6b6  mov     [rsp+160h+var_100], r9
0x18001f6bb  mov     r13, r8
0x18001f6be  mov     r14, rcx
0x18001f6c1  mov     r15, [rbp+60h+arg_28]
0x18001f6c8  mov     [rsp+160h+var_F8], r15
0x18001f6cd  xor     r12d, r12d
0x18001f6d0  mov     [rsp+160h+var_120], r12b
0x18001f6d5  mov     dword ptr [rsp+160h+pbInput], r12d
0x18001f6da  mov     [rsp+160h+hHash], r12
0x18001f6df  xorps   xmm0, xmm0
0x18001f6e2  movups  xmmword ptr [rsp+160h+pbOutput], xmm0
0x18001f6e7  movups  [rbp+60h+var_E0], xmm0
0x18001f6eb  xor     edx, edx; Val
0x18001f6ed  mov     r8d, 82h; Size
0x18001f6f3  lea     rcx, [rbp+60h+ValueName]; void *
0x18001f6f7  call    memset_0
0x18001f6fc  mov     [r15], r12b
0x18001f6ff  mov     [rsp+160h+phAlgorithm], r12
0x18001f704  xor     r9d, r9d; dwFlags
0x18001f707  xor     r8d, r8d; pszImplementation
0x18001f70a  lea     rdx, pszAlgId; "SHA256"
0x18001f711  lea     rcx, [rsp+160h+phAlgorithm]; phAlgorithm
0x18001f716  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001f71d  nop     dword ptr [rax+rax+00h]
0x18001f722  test    eax, eax
0x18001f724  jns     short loc_18001F73E
0x18001f726  mov     edx, 1E7h; void *
0x18001f72b  mov     r9d, eax; char *
0x18001f72e  mov     rcx, [rbp+68h]; this
0x18001f732  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001f737  mov     ebx, eax
0x18001f739  jmp     loc_18001F9E1
0x18001f73e  mov     rdi, [rsp+160h+hHash]
0x18001f743  test    rdi, rdi
0x18001f746  jz      short loc_18001F773
0x18001f748  call    cs:__imp_GetLastError
0x18001f74f  nop     dword ptr [rax+rax+00h]
0x18001f754  mov     ebx, eax
0x18001f756  mov     rcx, rdi; hHash
0x18001f759  call    cs:__imp_BCryptDestroyHash
0x18001f760  nop     dword ptr [rax+rax+00h]
0x18001f765  mov     ecx, ebx; dwErrCode
0x18001f767  call    cs:__imp_SetLastError
0x18001f76e  nop     dword ptr [rax+rax+00h]
0x18001f773  mov     [rsp+160h+hHash], r12
0x18001f778  mov     [rsp+160h+dwFlags], r12d; dwFlags
0x18001f77d  mov     [rsp+160h+cbSecret], r12d; cbSecret
0x18001f782  mov     [rsp+160h+pbSecret], r12; int
0x18001f787  xor     r9d, r9d; cbHashObject
0x18001f78a  xor     r8d, r8d; pbHashObject
0x18001f78d  lea     rdx, [rsp+160h+hHash]; phHash
0x18001f792  mov     rcx, [rsp+160h+phAlgorithm]; hAlgorithm
0x18001f797  call    cs:__imp_BCryptCreateHash
0x18001f79e  nop     dword ptr [rax+rax+00h]
0x18001f7a3  test    eax, eax
0x18001f7a5  jns     short loc_18001F7B1
0x18001f7a7  mov     edx, 1EAh
0x18001f7ac  jmp     loc_18001F72B
0x18001f7b1  test    r14, r14
0x18001f7b4  jz      loc_18001F9C3
0x18001f7ba  mov     edx, 3FFFFFFFh
0x18001f7bf  mov     ecx, edx
0x18001f7c1  mov     rax, r14
0x18001f7c4  cmp     [rax], r12w
0x18001f7c8  jz      short loc_18001F7D4
0x18001f7ca  add     rax, 2
0x18001f7ce  sub     rcx, 1
0x18001f7d2  jnz     short loc_18001F7C4
0x18001f7d4  mov     rax, rcx
0x18001f7d7  neg     rax
0x18001f7da  sbb     ebx, ebx
0x18001f7dc  not     ebx
0x18001f7de  and     ebx, 80070057h
0x18001f7e4  test    rcx, rcx
0x18001f7e7  jz      loc_18001F9C8
0x18001f7ed  mov     eax, edx
0x18001f7ef  sub     eax, ecx
0x18001f7f1  add     eax, eax
0x18001f7f3  neg     rcx
0x18001f7f6  sbb     r8d, r8d
0x18001f7f9  and     r8d, eax; cbInput
0x18001f7fc  xor     r9d, r9d; dwFlags
0x18001f7ff  mov     rdx, r14; pbInput
0x18001f802  mov     rcx, [rsp+160h+hHash]; hHash
0x18001f807  call    cs:__imp_BCryptHashData
0x18001f80e  nop     dword ptr [rax+rax+00h]
0x18001f813  test    eax, eax
0x18001f815  jns     short loc_18001F821
0x18001f817  mov     edx, 1F2h
0x18001f81c  jmp     loc_18001F72B
0x18001f821  mov     r14d, r12d
0x18001f824  cmp     [r13+20h], r12d
0x18001f828  jbe     loc_18001F92A
0x18001f82e  mov     r12d, [rbp+60h+arg_20]
0x18001f835  xor     r8d, r8d
0x18001f838  mov     edi, r14d
0x18001f83b  shl     rdi, 6
0x18001f83f  add     rdi, [r13+18h]
0x18001f843  mov     r15d, r8d
0x18001f846  test    r12d, r12d
0x18001f849  jz      loc_18001F915
0x18001f84f  mov     rcx, [rsp+160h+var_100]
0x18001f854  mov     eax, r15d
0x18001f857  shl     rax, 5
0x18001f85b  mov     edx, [rcx+rax+14h]
0x18001f85f  cmp     dword ptr [rcx+rax+10h], 4
0x18001f864  jnz     short loc_18001F89B
0x18001f866  mov     eax, [rdx+rdi]
0x18001f869  mov     dword ptr [rsp+160h+pbInput], eax
0x18001f86d  xor     r9d, r9d; dwFlags
0x18001f870  lea     r8d, [r9+4]; cbInput
0x18001f874  lea     rdx, [rsp+160h+pbInput]; pbInput
0x18001f879  mov     rcx, [rsp+160h+hHash]; hHash
0x18001f87e  call    cs:__imp_BCryptHashData
0x18001f885  nop     dword ptr [rax+rax+00h]
0x18001f88a  xor     r8d, r8d
0x18001f88d  test    eax, eax
0x18001f88f  jns     short loc_18001F904
0x18001f891  mov     edx, 1FEh
0x18001f896  jmp     loc_18001F72B
0x18001f89b  mov     rdx, [rdx+rdi]; pbInput
0x18001f89f  test    rdx, rdx
0x18001f8a2  jz      short loc_18001F909
0x18001f8a4  mov     r9d, 3FFFFFFFh
0x18001f8aa  mov     ecx, r9d
0x18001f8ad  mov     rax, rdx
0x18001f8b0  cmp     [rax], r8w
0x18001f8b4  jz      short loc_18001F8C0
0x18001f8b6  add     rax, 2
0x18001f8ba  sub     rcx, 1
0x18001f8be  jnz     short loc_18001F8B0
0x18001f8c0  mov     rax, rcx
0x18001f8c3  neg     rax
0x18001f8c6  sbb     ebx, ebx
0x18001f8c8  not     ebx
0x18001f8ca  and     ebx, 80070057h
0x18001f8d0  test    rcx, rcx
0x18001f8d3  jz      loc_18001F962
0x18001f8d9  mov     eax, r9d
0x18001f8dc  sub     eax, ecx
0x18001f8de  add     eax, eax
0x18001f8e0  neg     rcx
0x18001f8e3  sbb     r8d, r8d
0x18001f8e6  and     r8d, eax; cbInput
0x18001f8e9  xor     r9d, r9d; dwFlags
0x18001f8ec  mov     rcx, [rsp+160h+hHash]; hHash
0x18001f8f1  call    cs:__imp_BCryptHashData
0x18001f8f8  nop     dword ptr [rax+rax+00h]
0x18001f8fd  xor     r8d, r8d
0x18001f900  test    eax, eax
0x18001f902  js      short loc_18001F958
0x18001f904  mov     rcx, [rsp+160h+var_100]
0x18001f909  inc     r15d
0x18001f90c  cmp     r15d, r12d
0x18001f90f  jb      loc_18001F854
0x18001f915  inc     r14d
0x18001f918  cmp     r14d, [r13+20h]
0x18001f91c  jb      loc_18001F838
0x18001f922  mov     r15, [rsp+160h+var_F8]
0x18001f927  xor     r12d, r12d
0x18001f92a  xor     r9d, r9d; dwFlags
0x18001f92d  lea     ebx, [r9+20h]
0x18001f931  mov     r8d, ebx; cbOutput
0x18001f934  lea     rdx, [rsp+160h+pbOutput]; pbOutput
0x18001f939  mov     rcx, [rsp+160h+hHash]; hHash
0x18001f93e  call    cs:__imp_BCryptFinishHash
0x18001f945  nop     dword ptr [rax+rax+00h]
0x18001f94a  test    eax, eax
0x18001f94c  jns     short loc_18001F969
0x18001f94e  mov     edx, 211h
0x18001f953  jmp     loc_18001F72B
0x18001f958  mov     edx, 20Ah
0x18001f95d  jmp     loc_18001F72B
0x18001f962  mov     edx, 207h
0x18001f967  jmp     short loc_18001F9CD
0x18001f969  mov     [rsp+160h+var_104], 41h ; 'A'
0x18001f971  mov     dword ptr [rsp+160h+pbSecret], r12d
0x18001f976  lea     r9, [rsp+160h+var_104]
0x18001f97b  lea     r8, [rbp+60h+ValueName]
0x18001f97f  mov     edx, ebx
0x18001f981  lea     rcx, [rsp+160h+pbOutput]
0x18001f986  call    cs:__imp_BinaryToHexString
0x18001f98d  nop     dword ptr [rax+rax+00h]
0x18001f992  mov     ebx, eax
0x18001f994  test    eax, eax
0x18001f996  jns     short loc_18001F99F
0x18001f998  mov     edx, 215h
0x18001f99d  jmp     short loc_18001F9CD
0x18001f99f  lea     r8, [rsp+160h+var_120]; bool *
0x18001f9a4  lea     rcx, [rbp+60h+ValueName]; lpValueName
0x18001f9a8  call    ?IsRepeatingMsg@@YAJPEAG_KPEA_N@Z; IsRepeatingMsg(ushort *,unsigned __int64,bool *)
0x18001f9ad  mov     ebx, eax
0x18001f9af  test    eax, eax
0x18001f9b1  jns     short loc_18001F9BA
0x18001f9b3  mov     edx, 219h
0x18001f9b8  jmp     short loc_18001F9CD
0x18001f9ba  mov     al, [rsp+160h+var_120]
0x18001f9be  mov     [r15], al
0x18001f9c1  jmp     short loc_18001F9E1
0x18001f9c3  mov     ebx, 80070057h
0x18001f9c8  mov     edx, 1EFh; void *
0x18001f9cd  mov     r9d, ebx; char *
0x18001f9d0  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\dm\\omadm\\omadmapi"...
0x18001f9d7  mov     rcx, [rbp+68h]; this
0x18001f9db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f9e0  nop
0x18001f9e1  mov     rcx, [rsp+160h+hHash]; hHash
0x18001f9e6  test    rcx, rcx
0x18001f9e9  jz      short loc_18001F9F8
0x18001f9eb  call    cs:__imp_BCryptDestroyHash
0x18001f9f2  nop     dword ptr [rax+rax+00h]
0x18001f9f7  nop
0x18001f9f8  mov     rcx, [rsp+160h+phAlgorithm]; hAlgorithm
0x18001f9fd  test    rcx, rcx
0x18001fa00  jz      short loc_18001FA10
0x18001fa02  xor     edx, edx; dwFlags
0x18001fa04  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18001fa0b  nop     dword ptr [rax+rax+00h]
0x18001fa10  mov     eax, ebx
0x18001fa12  mov     rcx, [rbp+60h+var_40]
0x18001fa16  xor     rcx, rsp; StackCookie
0x18001fa19  call    __security_check_cookie
0x18001fa1e  add     rsp, 130h
0x18001fa25  pop     r15
0x18001fa27  pop     r14
0x18001fa29  pop     r13
0x18001fa2b  pop     r12
0x18001fa2d  pop     rdi
0x18001fa2e  pop     rbx
0x18001fa2f  pop     rbp
0x18001fa30  retn
```
