# WinPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)

- ea: `0x1801463e0`
- end: `0x1801465c4`
- name: `?WinPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z`
- size: `484`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszAlgId@<rcx>, PUCHAR pbInput@<rdx>, ULONG cbInput@<r8d>, unsigned __int8 *@<r9>, ULONG, PUCHAR, ULONG cbOutput, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180018fe4`
- `0x180019024`
- `0x180019fc4`
- `0x1801463e0`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x18014647b`
- `bcrypt!BCryptGetProperty` at `0x1801464cf`
- `bcrypt!BCryptGetProperty` at `0x18014647b`
- `bcrypt!BCryptGetProperty` at `0x1801464cf`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180146444`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180146444`
- `bcrypt!BCryptFinishHash` at `0x180146561`
- `bcrypt!BCryptFinishHash` at `0x180146561`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801465ae`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801465ae`
- `bcrypt!BCryptDestroyHash` at `0x180146572`
- `bcrypt!BCryptDestroyHash` at `0x180146572`
- `bcrypt!BCryptHashData` at `0x180146546`
- `bcrypt!BCryptHashData` at `0x180146546`
- `bcrypt!BCryptCreateHash` at `0x18014652d`
- `bcrypt!BCryptCreateHash` at `0x18014652d`

## pseudocode

```c
__int64 __fastcall WinPlatformHash(
        LPCWSTR pszAlgId,
        PUCHAR pbInput,
        ULONG cbInput,
        unsigned __int8 *a4,
        ULONG cbSecret,
        PUCHAR a6,
        ULONG cbOutput,
        unsigned int *a8,
        ULONG dwFlags)
{
  void *v12; // rdi
  NTSTATUS Property; // ebx
  ULONG v14; // eax
  __int64 v15; // rax
  _BYTE *v16; // rcx
  UCHAR v17[4]; // [rsp+40h] [rbp-28h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-24h] BYREF
  UCHAR pbOutput[8]; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+58h] [rbp-10h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  *(_DWORD *)v17 = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  if ( cbOutput && !a6 || !a8 )
    return 2147942487LL;
  *a8 = 0;
  v12 = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, L"Microsoft Primitive Provider", dwFlags);
  if ( Property >= 0 )
  {
    pcbResult = 4;
    Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property >= 0 )
    {
      v14 = *(_DWORD *)pbOutput;
      *a8 = *(_DWORD *)pbOutput;
      if ( cbOutput )
      {
        if ( cbOutput >= v14 )
        {
          pcbResult = 4;
          Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", v17, 4u, &pcbResult, 0);
          if ( Property >= 0 )
          {
            v12 = operator new(*(unsigned int *)v17);
            memset_0(v12, 0, *(unsigned int *)v17);
            memset_0(v12, 0, *(unsigned int *)v17);
            Property = BCryptCreateHash(phAlgorithm, &phHash, (PUCHAR)v12, *(ULONG *)v17, a4, cbSecret, 0);
            if ( Property >= 0 )
            {
              Property = BCryptHashData(phHash, pbInput, cbInput, 0);
              if ( Property >= 0 )
                Property = BCryptFinishHash(phHash, a6, cbOutput, 0);
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
  if ( v12 )
  {
    v15 = *(unsigned int *)v17;
    v16 = v12;
    if ( *(_DWORD *)v17 )
    {
      do
      {
        *v16++ = 0;
        --v15;
      }
      while ( v15 );
    }
    operator delete(v12);
  }
  *(_DWORD *)v17 = 0;
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1801463e0  mov     [rsp-30h+pbSecret], r9
0x1801463e5  push    rbp
0x1801463e6  push    rbx
0x1801463e7  push    rdi
0x1801463e8  push    r12
0x1801463ea  push    r13
0x1801463ec  push    r14
0x1801463ee  mov     rbp, rsp
0x1801463f1  sub     rsp, 68h
0x1801463f5  xor     eax, eax
0x1801463f7  mov     r12d, r8d
0x1801463fa  mov     r13, rdx
0x1801463fd  mov     [rbp+phAlgorithm], rax
0x180146401  mov     [rbp+phHash], rax
0x180146405  mov     dword ptr [rbp+var_28], eax
0x180146408  mov     dword ptr [rbp+pbOutput], eax
0x18014640b  mov     [rbp+var_24], eax
0x18014640e  cmp     [rbp+cbOutput], eax
0x180146411  jz      short loc_180146419
0x180146413  cmp     [rbp+arg_28], rax
0x180146417  jz      short loc_180146422
0x180146419  mov     r14, [rbp+arg_38]
0x18014641d  test    r14, r14
0x180146420  jnz     short loc_18014642C
0x180146422  mov     eax, 80070057h
0x180146427  jmp     loc_1801465B6
0x18014642c  mov     r9d, [rbp+dwFlags]; dwFlags
0x180146430  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180146437  mov     rdx, rcx; pszAlgId
0x18014643a  mov     [r14], eax
0x18014643d  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180146441  mov     rdi, rax
0x180146444  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18014644a  mov     ebx, eax
0x18014644c  test    eax, eax
0x18014644e  js      loc_180146569
0x180146454  mov     ecx, 4
0x180146459  mov     [rsp+68h+cbSecret], edi; dwFlags
0x18014645d  mov     [rbp+var_24], ecx
0x180146460  lea     rax, [rbp+var_24]
0x180146464  mov     r9d, ecx; cbOutput
0x180146467  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18014646c  mov     rcx, [rbp+phAlgorithm]; hObject
0x180146470  lea     r8, [rbp+pbOutput]; pbOutput
0x180146474  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18014647b  call    cs:__imp_BCryptGetProperty
0x180146481  mov     ebx, eax
0x180146483  test    eax, eax
0x180146485  js      loc_180146569
0x18014648b  mov     eax, dword ptr [rbp+pbOutput]
0x18014648e  mov     [r14], eax
0x180146491  cmp     [rbp+cbOutput], edi
0x180146494  jz      loc_180146569
0x18014649a  cmp     [rbp+cbOutput], eax
0x18014649d  jnb     short loc_1801464A9
0x18014649f  mov     ebx, 0C0000023h
0x1801464a4  jmp     loc_180146569
0x1801464a9  mov     rcx, [rbp+phAlgorithm]; hObject
0x1801464ad  lea     rax, [rbp+var_24]
0x1801464b1  mov     r9d, 4; cbOutput
0x1801464b7  mov     [rsp+68h+cbSecret], edi; dwFlags
0x1801464bb  lea     r8, [rbp+var_28]; pbOutput
0x1801464bf  mov     [rbp+var_24], r9d
0x1801464c3  lea     rdx, pszProperty; "ObjectLength"
0x1801464ca  mov     [rsp+68h+pcbResult], rax; pcbResult
0x1801464cf  call    cs:__imp_BCryptGetProperty
0x1801464d5  mov     ebx, eax
0x1801464d7  test    eax, eax
0x1801464d9  js      loc_180146569
0x1801464df  mov     ecx, dword ptr [rbp+var_28]; Size
0x1801464e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801464e7  mov     r8d, dword ptr [rbp+var_28]; Size
0x1801464eb  xor     edx, edx; Val
0x1801464ed  mov     rcx, rax; void *
0x1801464f0  mov     rdi, rax
0x1801464f3  call    memset_0
0x1801464f8  mov     r8d, dword ptr [rbp+var_28]; Size
0x1801464fc  xor     edx, edx; Val
0x1801464fe  mov     rcx, rdi; void *
0x180146501  call    memset_0
0x180146506  mov     eax, [rbp+arg_20]
0x180146509  lea     rdx, [rbp+phHash]; phHash
0x18014650d  mov     r9d, dword ptr [rbp+var_28]; cbHashObject
0x180146511  mov     r8, rdi; pbHashObject
0x180146514  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180146518  mov     [rsp+68h+var_38], 0; dwFlags
0x180146520  mov     [rsp+68h+cbSecret], eax; cbSecret
0x180146524  mov     rax, [rbp+pbSecret]
0x180146528  mov     [rsp+68h+pcbResult], rax; pbSecret
0x18014652d  call    cs:__imp_BCryptCreateHash
0x180146533  mov     ebx, eax
0x180146535  test    eax, eax
0x180146537  js      short loc_180146569
0x180146539  mov     rcx, [rbp+phHash]; hHash
0x18014653d  xor     r9d, r9d; dwFlags
0x180146540  mov     r8d, r12d; cbInput
0x180146543  mov     rdx, r13; pbInput
0x180146546  call    cs:__imp_BCryptHashData
0x18014654c  mov     ebx, eax
0x18014654e  test    eax, eax
0x180146550  js      short loc_180146569
0x180146552  mov     r8d, [rbp+cbOutput]; cbOutput
0x180146556  xor     r9d, r9d; dwFlags
0x180146559  mov     rdx, [rbp+arg_28]; pbOutput
0x18014655d  mov     rcx, [rbp+phHash]; hHash
0x180146561  call    cs:__imp_BCryptFinishHash
0x180146567  mov     ebx, eax
0x180146569  mov     rcx, [rbp+phHash]; hHash
0x18014656d  test    rcx, rcx
0x180146570  jz      short loc_180146578
0x180146572  call    cs:__imp_BCryptDestroyHash
0x180146578  test    rdi, rdi
0x18014657b  jz      short loc_18014659C
0x18014657d  mov     eax, dword ptr [rbp+var_28]
0x180146580  mov     rcx, rdi
0x180146583  test    rax, rax
0x180146586  jz      short loc_180146594
0x180146588  mov     byte ptr [rcx], 0
0x18014658b  inc     rcx
0x18014658e  sub     rax, 1
0x180146592  jnz     short loc_180146588
0x180146594  mov     rcx, rdi; Block
0x180146597  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18014659c  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1801465a0  mov     dword ptr [rbp+var_28], 0
0x1801465a7  test    rcx, rcx
0x1801465aa  jz      short loc_1801465B4
0x1801465ac  xor     edx, edx; dwFlags
0x1801465ae  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1801465b4  mov     eax, ebx
0x1801465b6  add     rsp, 68h
0x1801465ba  pop     r14
0x1801465bc  pop     r13
0x1801465be  pop     r12
0x1801465c0  pop     rdi
0x1801465c1  pop     rbx
0x1801465c2  pop     rbp
0x1801465c3  retn
```
