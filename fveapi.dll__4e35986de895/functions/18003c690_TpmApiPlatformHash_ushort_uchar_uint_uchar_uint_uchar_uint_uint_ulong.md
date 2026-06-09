# TpmApiPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)

- ea: `0x18003c690`
- end: `0x18003c8ff`
- name: `?TpmApiPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z`
- size: `623`
- prototype: `__int64 __fastcall(LPCWSTR pszAlgId, PUCHAR pbInput, ULONG cbInput, PUCHAR pbSecret, ULONG, PUCHAR, ULONG cbOutput, unsigned int *, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18003c690`
- `0x18011efce`
- `0x180129010`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003c706`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003c706`
- `bcrypt!BCryptDestroyHash` at `0x18003c867`
- `bcrypt!BCryptDestroyHash` at `0x18003c867`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18003c8bc`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18003c8bc`
- `bcrypt!BCryptGetProperty` at `0x18003c747`
- `bcrypt!BCryptGetProperty` at `0x18003c79f`
- `bcrypt!BCryptGetProperty` at `0x18003c747`
- `bcrypt!BCryptGetProperty` at `0x18003c79f`
- `bcrypt!BCryptCreateHash` at `0x18003c810`
- `bcrypt!BCryptCreateHash` at `0x18003c810`
- `bcrypt!BCryptHashData` at `0x18003c82f`
- `bcrypt!BCryptHashData` at `0x18003c82f`
- `bcrypt!BCryptFinishHash` at `0x18003c850`
- `bcrypt!BCryptFinishHash` at `0x18003c850`

## pseudocode

```c
__int64 __fastcall TpmApiPlatformHash(
        LPCWSTR pszAlgId,
        PUCHAR pbInput,
        __int64 cbInput,
        PUCHAR pbSecret,
        ULONG cbSecret,
        PUCHAR a6,
        ULONG cbOutput,
        unsigned int *a8,
        ULONG dwFlags)
{
  UCHAR *v9; // r13
  ULONG v10; // r15d
  NTSTATUS Property; // ebx
  ULONG v13; // eax
  void (__fastcall *v14)(__int64, PUCHAR, __int64, PUCHAR); // rax
  PUCHAR v15; // rdx
  UCHAR v17[4]; // [rsp+40h] [rbp-38h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-34h] BYREF
  UCHAR pbOutput[8]; // [rsp+48h] [rbp-30h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-28h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+58h] [rbp-20h] BYREF
  PUCHAR pbHashObject[3]; // [rsp+60h] [rbp-18h] BYREF

  v9 = pbSecret;
  v10 = cbInput;
  phAlgorithm = 0;
  phHash = 0;
  pbHashObject[0] = 0;
  *(_DWORD *)v17 = 0;
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
          if ( cbOutput < v13 )
          {
            Property = -1073741789;
          }
          else
          {
            pcbResult = 4;
            Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", v17, 4u, &pcbResult, 0);
            if ( Property >= 0 )
            {
              if ( !qword_1801746D0 || (unsigned int)qword_1801746D0(-1, *(unsigned int *)v17, pbHashObject) )
              {
                Property = -1073741801;
              }
              else
              {
                memset_0(pbHashObject[0], 0, *(unsigned int *)v17);
                Property = BCryptCreateHash(phAlgorithm, &phHash, pbHashObject[0], *(ULONG *)v17, v9, cbSecret, 0);
                if ( Property >= 0 )
                {
                  Property = BCryptHashData(phHash, pbInput, v10, 0);
                  if ( Property >= 0 )
                    Property = BCryptFinishHash(phHash, a6, cbOutput, 0);
                }
              }
            }
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
  v14 = (void (__fastcall *)(__int64, PUCHAR, __int64, PUCHAR))qword_1801746C8;
  if ( qword_1801746C8 )
  {
    v15 = pbHashObject[0];
    if ( pbHashObject[0] )
    {
      cbInput = *(unsigned int *)v17;
      pbSecret = pbHashObject[0];
      if ( *(_DWORD *)v17 )
      {
        do
        {
          *pbSecret++ = 0;
          --cbInput;
        }
        while ( cbInput );
      }
    }
    v14(-1, v15, cbInput, pbSecret);
  }
  *(_DWORD *)v17 = 0;
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18003c690  push    rbp
0x18003c692  push    rbx
0x18003c693  push    rdi
0x18003c694  push    r12
0x18003c696  push    r13
0x18003c698  push    r15
0x18003c69a  mov     rbp, rsp
0x18003c69d  sub     rsp, 78h
0x18003c6a1  cmp     [rbp+cbOutput], 0
0x18003c6a5  mov     r13, r9
0x18003c6a8  mov     r15d, r8d
0x18003c6ab  mov     [rbp+phAlgorithm], 0
0x18003c6b3  mov     r12, rdx
0x18003c6b6  mov     [rbp+phHash], 0
0x18003c6be  mov     [rbp+pbHashObject], 0
0x18003c6c6  mov     dword ptr [rbp+var_38], 0
0x18003c6cd  mov     dword ptr [rbp+pbOutput], 0
0x18003c6d4  mov     [rbp+var_34], 0
0x18003c6db  jnz     loc_18003C8D9
0x18003c6e1  mov     rdi, [rbp+arg_38]
0x18003c6e5  test    rdi, rdi
0x18003c6e8  jz      loc_18003C8E4
0x18003c6ee  mov     r9d, [rbp+dwFlags]; dwFlags
0x18003c6f2  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18003c6f9  mov     rdx, rcx; pszAlgId
0x18003c6fc  mov     dword ptr [rdi], 0
0x18003c702  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18003c706  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18003c70d  nop     dword ptr [rax+rax+00h]
0x18003c712  mov     ebx, eax
0x18003c714  test    eax, eax
0x18003c716  js      loc_18003C85E
0x18003c71c  mov     ecx, 4
0x18003c721  mov     [rsp+78h+cbSecret], 0; dwFlags
0x18003c729  mov     [rbp+var_34], ecx
0x18003c72c  lea     rax, [rbp+var_34]
0x18003c730  mov     r9d, ecx; cbOutput
0x18003c733  mov     [rsp+78h+pcbResult], rax; pcbResult
0x18003c738  mov     rcx, [rbp+phAlgorithm]; hObject
0x18003c73c  lea     r8, [rbp+pbOutput]; pbOutput
0x18003c740  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18003c747  call    cs:__imp_BCryptGetProperty
0x18003c74e  nop     dword ptr [rax+rax+00h]
0x18003c753  mov     ebx, eax
0x18003c755  test    eax, eax
0x18003c757  js      loc_18003C85E
0x18003c75d  cmp     [rbp+cbOutput], 0
0x18003c761  mov     eax, dword ptr [rbp+pbOutput]
0x18003c764  mov     [rdi], eax
0x18003c766  jz      loc_18003C85E
0x18003c76c  cmp     [rbp+cbOutput], eax
0x18003c76f  jb      loc_18003C8F5
0x18003c775  mov     rcx, [rbp+phAlgorithm]; hObject
0x18003c779  lea     rax, [rbp+var_34]
0x18003c77d  mov     r9d, 4; cbOutput
0x18003c783  mov     [rsp+78h+cbSecret], 0; dwFlags
0x18003c78b  lea     r8, [rbp+var_38]; pbOutput
0x18003c78f  mov     [rbp+var_34], r9d
0x18003c793  lea     rdx, pszProperty; "ObjectLength"
0x18003c79a  mov     [rsp+78h+pcbResult], rax; pcbResult
0x18003c79f  call    cs:__imp_BCryptGetProperty
0x18003c7a6  nop     dword ptr [rax+rax+00h]
0x18003c7ab  mov     ebx, eax
0x18003c7ad  test    eax, eax
0x18003c7af  js      loc_18003C85E
0x18003c7b5  mov     rax, cs:qword_1801746D0
0x18003c7bc  test    rax, rax
0x18003c7bf  jz      loc_18003C8EB
0x18003c7c5  mov     edx, dword ptr [rbp+var_38]
0x18003c7c8  lea     r8, [rbp+pbHashObject]
0x18003c7cc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003c7d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c7d5  test    eax, eax
0x18003c7d7  jnz     loc_18003C8EB
0x18003c7dd  mov     r8d, dword ptr [rbp+var_38]; Size
0x18003c7e1  xor     edx, edx; Val
0x18003c7e3  mov     rcx, [rbp+pbHashObject]; void *
0x18003c7e7  call    memset_0
0x18003c7ec  mov     eax, [rbp+arg_20]
0x18003c7ef  lea     rdx, [rbp+phHash]; phHash
0x18003c7f3  mov     r9d, dword ptr [rbp+var_38]; cbHashObject
0x18003c7f7  mov     r8, [rbp+pbHashObject]; pbHashObject
0x18003c7fb  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18003c7ff  mov     [rsp+78h+var_48], 0; dwFlags
0x18003c807  mov     [rsp+78h+cbSecret], eax; cbSecret
0x18003c80b  mov     [rsp+78h+pcbResult], r13; pbSecret
0x18003c810  call    cs:__imp_BCryptCreateHash
0x18003c817  nop     dword ptr [rax+rax+00h]
0x18003c81c  mov     ebx, eax
0x18003c81e  test    eax, eax
0x18003c820  js      short loc_18003C85E
0x18003c822  mov     rcx, [rbp+phHash]; hHash
0x18003c826  xor     r9d, r9d; dwFlags
0x18003c829  mov     r8d, r15d; cbInput
0x18003c82c  mov     rdx, r12; pbInput
0x18003c82f  call    cs:__imp_BCryptHashData
0x18003c836  nop     dword ptr [rax+rax+00h]
0x18003c83b  mov     ebx, eax
0x18003c83d  test    eax, eax
0x18003c83f  js      short loc_18003C85E
0x18003c841  mov     r8d, [rbp+cbOutput]; cbOutput
0x18003c845  xor     r9d, r9d; dwFlags
0x18003c848  mov     rdx, [rbp+arg_28]; pbOutput
0x18003c84c  mov     rcx, [rbp+phHash]; hHash
0x18003c850  call    cs:__imp_BCryptFinishHash
0x18003c857  nop     dword ptr [rax+rax+00h]
0x18003c85c  mov     ebx, eax
0x18003c85e  mov     rcx, [rbp+phHash]; hHash
0x18003c862  test    rcx, rcx
0x18003c865  jz      short loc_18003C873
0x18003c867  call    cs:__imp_BCryptDestroyHash
0x18003c86e  nop     dword ptr [rax+rax+00h]
0x18003c873  mov     rax, cs:qword_1801746C8
0x18003c87a  test    rax, rax
0x18003c87d  jz      short loc_18003C8AA
0x18003c87f  mov     rdx, [rbp+pbHashObject]
0x18003c883  test    rdx, rdx
0x18003c886  jz      short loc_18003C8A1
0x18003c888  mov     r8d, dword ptr [rbp+var_38]
0x18003c88c  mov     r9, rdx
0x18003c88f  test    r8, r8
0x18003c892  jz      short loc_18003C8A1
0x18003c894  mov     byte ptr [r9], 0
0x18003c898  inc     r9
0x18003c89b  sub     r8, 1
0x18003c89f  jnz     short loc_18003C894
0x18003c8a1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003c8a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8aa  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18003c8ae  mov     dword ptr [rbp+var_38], 0
0x18003c8b5  test    rcx, rcx
0x18003c8b8  jz      short loc_18003C8C8
0x18003c8ba  xor     edx, edx; dwFlags
0x18003c8bc  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18003c8c3  nop     dword ptr [rax+rax+00h]
0x18003c8c8  mov     eax, ebx
0x18003c8ca  add     rsp, 78h
0x18003c8ce  pop     r15
0x18003c8d0  pop     r13
0x18003c8d2  pop     r12
0x18003c8d4  pop     rdi
0x18003c8d5  pop     rbx
0x18003c8d6  pop     rbp
0x18003c8d7  retn
0x18003c8d9  cmp     [rbp+arg_28], 0
0x18003c8de  jnz     loc_18003C6E1
0x18003c8e4  mov     ebx, 0C000000Dh
0x18003c8e9  jmp     short loc_18003C873
0x18003c8eb  mov     ebx, 0C0000017h
0x18003c8f0  jmp     loc_18003C85E
0x18003c8f5  mov     ebx, 0C0000023h
0x18003c8fa  jmp     loc_18003C85E
```
