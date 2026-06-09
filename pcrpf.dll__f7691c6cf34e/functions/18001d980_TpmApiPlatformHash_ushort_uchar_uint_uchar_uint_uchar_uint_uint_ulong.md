# TpmApiPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)

- ea: `0x18001d980`
- end: `0x18001dbb8`
- name: `?TpmApiPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z`
- size: `568`
- prototype: `__int64 __fastcall(LPCWSTR pszAlgId, PUCHAR pbInput, ULONG cbInput, PUCHAR pbSecret, ULONG, PUCHAR, ULONG cbOutput, unsigned int *, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003cf0`
- `0x18001ced4`
- `0x18001d980`
- `0x180059010`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18001db0f`
- `bcrypt!BCryptCreateHash` at `0x18001db0f`
- `bcrypt!BCryptGetProperty` at `0x18001da40`
- `bcrypt!BCryptGetProperty` at `0x18001da9e`
- `bcrypt!BCryptGetProperty` at `0x18001da40`
- `bcrypt!BCryptGetProperty` at `0x18001da9e`
- `bcrypt!BCryptHashData` at `0x18001db2e`
- `bcrypt!BCryptHashData` at `0x18001db2e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001d9ff`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001d9ff`
- `bcrypt!BCryptFinishHash` at `0x18001db4f`
- `bcrypt!BCryptFinishHash` at `0x18001db4f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001db9b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001db9b`
- `bcrypt!BCryptDestroyHash` at `0x18001db6d`
- `bcrypt!BCryptDestroyHash` at `0x18001db6d`

## pseudocode

```c
__int64 __fastcall TpmApiPlatformHash(
        LPCWSTR pszAlgId,
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR pbSecret,
        ULONG cbSecret,
        PUCHAR a6,
        ULONG cbOutput,
        unsigned int *a8,
        ULONG dwFlags)
{
  NTSTATUS Property; // ebx
  ULONG v13; // eax
  UCHAR v15[4]; // [rsp+40h] [rbp-38h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-34h] BYREF
  UCHAR pbOutput[8]; // [rsp+48h] [rbp-30h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-28h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+58h] [rbp-20h] BYREF
  PUCHAR pbHashObject[3]; // [rsp+60h] [rbp-18h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  pbHashObject[0] = 0;
  *(_DWORD *)v15 = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  if ( (!cbOutput || a6) && a8 )
  {
    *a8 = 0;
    Property = BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, L"Microsoft Primitive Provider", dwFlags);
    if ( Property >= 0 )
    {
      pcbResult = 4;
      Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
      if ( Property >= 0 )
      {
        v13 = *(_DWORD *)pbOutput;
        *a8 = *(_DWORD *)pbOutput;
        if ( cbOutput )
        {
          if ( cbOutput >= v13 )
          {
            pcbResult = 4;
            Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", v15, 4u, &pcbResult, 0);
            if ( Property >= 0 )
            {
              if ( !qword_180072B30 || (unsigned int)qword_180072B30(-1, *(unsigned int *)v15, pbHashObject) )
              {
                Property = -1073741801;
              }
              else
              {
                memset_0(pbHashObject[0], 0, *(unsigned int *)v15);
                Property = BCryptCreateHash(phAlgorithm, &phHash, pbHashObject[0], *(ULONG *)v15, pbSecret, cbSecret, 0);
                if ( Property >= 0 )
                {
                  Property = BCryptHashData(phHash, pbInput, cbInput, 0);
                  if ( Property >= 0 )
                    Property = BCryptFinishHash(phHash, a6, cbOutput, 0);
                }
              }
            }
          }
          else
          {
            Property = -1073741789;
          }
        }
      }
    }
    if ( phHash )
      BCryptDestroyHash(phHash);
  }
  else
  {
    Property = -1073741811;
  }
  TpmApiCallbackFree(-1, *(unsigned int *)v15);
  *(_DWORD *)v15 = 0;
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18001d980  push    rbp
0x18001d982  push    rbx
0x18001d983  push    rdi
0x18001d984  push    r12
0x18001d986  push    r13
0x18001d988  push    r15
0x18001d98a  mov     rbp, rsp
0x18001d98d  sub     rsp, 78h
0x18001d991  cmp     [rbp+cbOutput], 0
0x18001d995  mov     r13, r9
0x18001d998  mov     r15d, r8d
0x18001d99b  mov     [rbp+phAlgorithm], 0
0x18001d9a3  mov     r12, rdx
0x18001d9a6  mov     [rbp+phHash], 0
0x18001d9ae  mov     [rbp+pbHashObject], 0
0x18001d9b6  mov     dword ptr [rbp+var_38], 0
0x18001d9bd  mov     dword ptr [rbp+pbOutput], 0
0x18001d9c4  mov     [rbp+var_34], 0
0x18001d9cb  jz      short loc_18001D9D4
0x18001d9cd  cmp     [rbp+arg_28], 0
0x18001d9d2  jz      short loc_18001D9DD
0x18001d9d4  mov     rdi, [rbp+arg_38]
0x18001d9d8  test    rdi, rdi
0x18001d9db  jnz     short loc_18001D9E7
0x18001d9dd  mov     ebx, 0C000000Dh
0x18001d9e2  jmp     loc_18001DB79
0x18001d9e7  mov     r9d, [rbp+dwFlags]; dwFlags
0x18001d9eb  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18001d9f2  mov     rdx, rcx; pszAlgId
0x18001d9f5  mov     dword ptr [rdi], 0
0x18001d9fb  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18001d9ff  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001da06  nop     dword ptr [rax+rax+00h]
0x18001da0b  mov     ebx, eax
0x18001da0d  test    eax, eax
0x18001da0f  js      loc_18001DB64
0x18001da15  mov     ecx, 4
0x18001da1a  mov     [rsp+78h+cbSecret], 0; dwFlags
0x18001da22  mov     [rbp+var_34], ecx
0x18001da25  lea     rax, [rbp+var_34]
0x18001da29  mov     r9d, ecx; cbOutput
0x18001da2c  mov     [rsp+78h+pcbResult], rax; pcbResult
0x18001da31  mov     rcx, [rbp+phAlgorithm]; hObject
0x18001da35  lea     r8, [rbp+pbOutput]; pbOutput
0x18001da39  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18001da40  call    cs:__imp_BCryptGetProperty
0x18001da47  nop     dword ptr [rax+rax+00h]
0x18001da4c  mov     ebx, eax
0x18001da4e  test    eax, eax
0x18001da50  js      loc_18001DB64
0x18001da56  cmp     [rbp+cbOutput], 0
0x18001da5a  mov     eax, dword ptr [rbp+pbOutput]
0x18001da5d  mov     [rdi], eax
0x18001da5f  jz      loc_18001DB64
0x18001da65  cmp     [rbp+cbOutput], eax
0x18001da68  jnb     short loc_18001DA74
0x18001da6a  mov     ebx, 0C0000023h
0x18001da6f  jmp     loc_18001DB64
0x18001da74  mov     rcx, [rbp+phAlgorithm]; hObject
0x18001da78  lea     rax, [rbp+var_34]
0x18001da7c  mov     r9d, 4; cbOutput
0x18001da82  mov     [rsp+78h+cbSecret], 0; dwFlags
0x18001da8a  lea     r8, [rbp+var_38]; pbOutput
0x18001da8e  mov     [rbp+var_34], r9d
0x18001da92  lea     rdx, aObjectlength; "ObjectLength"
0x18001da99  mov     [rsp+78h+pcbResult], rax; pcbResult
0x18001da9e  call    cs:__imp_BCryptGetProperty
0x18001daa5  nop     dword ptr [rax+rax+00h]
0x18001daaa  mov     ebx, eax
0x18001daac  test    eax, eax
0x18001daae  js      loc_18001DB64
0x18001dab4  mov     rax, cs:qword_180072B30
0x18001dabb  test    rax, rax
0x18001dabe  jz      loc_18001DB5F
0x18001dac4  mov     edx, dword ptr [rbp+var_38]
0x18001dac7  lea     r8, [rbp+pbHashObject]
0x18001dacb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001dacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dad4  test    eax, eax
0x18001dad6  jnz     loc_18001DB5F
0x18001dadc  mov     r8d, dword ptr [rbp+var_38]; Size
0x18001dae0  xor     edx, edx; Val
0x18001dae2  mov     rcx, [rbp+pbHashObject]; void *
0x18001dae6  call    memset_0
0x18001daeb  mov     eax, [rbp+arg_20]
0x18001daee  lea     rdx, [rbp+phHash]; phHash
0x18001daf2  mov     r9d, dword ptr [rbp+var_38]; cbHashObject
0x18001daf6  mov     r8, [rbp+pbHashObject]; pbHashObject
0x18001dafa  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18001dafe  mov     [rsp+78h+var_48], 0; dwFlags
0x18001db06  mov     [rsp+78h+cbSecret], eax; cbSecret
0x18001db0a  mov     [rsp+78h+pcbResult], r13; pbSecret
0x18001db0f  call    cs:__imp_BCryptCreateHash
0x18001db16  nop     dword ptr [rax+rax+00h]
0x18001db1b  mov     ebx, eax
0x18001db1d  test    eax, eax
0x18001db1f  js      short loc_18001DB64
0x18001db21  mov     rcx, [rbp+phHash]; hHash
0x18001db25  xor     r9d, r9d; dwFlags
0x18001db28  mov     r8d, r15d; cbInput
0x18001db2b  mov     rdx, r12; pbInput
0x18001db2e  call    cs:__imp_BCryptHashData
0x18001db35  nop     dword ptr [rax+rax+00h]
0x18001db3a  mov     ebx, eax
0x18001db3c  test    eax, eax
0x18001db3e  js      short loc_18001DB64
0x18001db40  mov     r8d, [rbp+cbOutput]; cbOutput
0x18001db44  xor     r9d, r9d; dwFlags
0x18001db47  mov     rdx, [rbp+arg_28]; pbOutput
0x18001db4b  mov     rcx, [rbp+phHash]; hHash
0x18001db4f  call    cs:__imp_BCryptFinishHash
0x18001db56  nop     dword ptr [rax+rax+00h]
0x18001db5b  mov     ebx, eax
0x18001db5d  jmp     short loc_18001DB64
0x18001db5f  mov     ebx, 0C0000017h
0x18001db64  mov     rcx, [rbp+phHash]; hHash
0x18001db68  test    rcx, rcx
0x18001db6b  jz      short loc_18001DB79
0x18001db6d  call    cs:__imp_BCryptDestroyHash
0x18001db74  nop     dword ptr [rax+rax+00h]
0x18001db79  mov     r8, [rbp+pbHashObject]
0x18001db7d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001db81  mov     edx, dword ptr [rbp+var_38]
0x18001db84  call    TpmApiCallbackFree
0x18001db89  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18001db8d  mov     dword ptr [rbp+var_38], 0
0x18001db94  test    rcx, rcx
0x18001db97  jz      short loc_18001DBA7
0x18001db99  xor     edx, edx; dwFlags
0x18001db9b  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18001dba2  nop     dword ptr [rax+rax+00h]
0x18001dba7  mov     eax, ebx
0x18001dba9  add     rsp, 78h
0x18001dbad  pop     r15
0x18001dbaf  pop     r13
0x18001dbb1  pop     r12
0x18001dbb3  pop     rdi
0x18001dbb4  pop     rbx
0x18001dbb5  pop     rbp
0x18001dbb6  retn
```
