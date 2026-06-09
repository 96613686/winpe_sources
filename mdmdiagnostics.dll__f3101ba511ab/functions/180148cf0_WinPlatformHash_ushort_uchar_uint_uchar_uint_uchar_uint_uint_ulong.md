# WinPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)

- ea: `0x180148cf0`
- end: `0x180148f05`
- name: `?WinPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z`
- size: `533`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszAlgId@<rcx>, PUCHAR pbInput@<rdx>, ULONG cbInput@<r8d>, unsigned __int8 *@<r9>, ULONG, PUCHAR, ULONG cbOutput, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180019064`
- `0x1800190a4`
- `0x18001a054`
- `0x180148cf0`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x180148d91`
- `bcrypt!BCryptGetProperty` at `0x180148deb`
- `bcrypt!BCryptGetProperty` at `0x180148d91`
- `bcrypt!BCryptGetProperty` at `0x180148deb`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180148d54`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180148d54`
- `bcrypt!BCryptFinishHash` at `0x180148e8f`
- `bcrypt!BCryptFinishHash` at `0x180148e8f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180148ee8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180148ee8`
- `bcrypt!BCryptDestroyHash` at `0x180148ea6`
- `bcrypt!BCryptDestroyHash` at `0x180148ea6`
- `bcrypt!BCryptHashData` at `0x180148e6e`
- `bcrypt!BCryptHashData` at `0x180148e6e`
- `bcrypt!BCryptCreateHash` at `0x180148e4f`
- `bcrypt!BCryptCreateHash` at `0x180148e4f`

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
0x180148cf0  mov     [rsp-30h+pbSecret], r9
0x180148cf5  push    rbp
0x180148cf6  push    rbx
0x180148cf7  push    rdi
0x180148cf8  push    r12
0x180148cfa  push    r13
0x180148cfc  push    r14
0x180148cfe  mov     rbp, rsp
0x180148d01  sub     rsp, 68h
0x180148d05  xor     eax, eax
0x180148d07  mov     r12d, r8d
0x180148d0a  mov     r13, rdx
0x180148d0d  mov     [rbp+phAlgorithm], rax
0x180148d11  mov     [rbp+phHash], rax
0x180148d15  mov     dword ptr [rbp+var_28], eax
0x180148d18  mov     dword ptr [rbp+pbOutput], eax
0x180148d1b  mov     [rbp+var_24], eax
0x180148d1e  cmp     [rbp+cbOutput], eax
0x180148d21  jz      short loc_180148D29
0x180148d23  cmp     [rbp+arg_28], rax
0x180148d27  jz      short loc_180148D32
0x180148d29  mov     r14, [rbp+arg_38]
0x180148d2d  test    r14, r14
0x180148d30  jnz     short loc_180148D3C
0x180148d32  mov     eax, 80070057h
0x180148d37  jmp     loc_180148EF6
0x180148d3c  mov     r9d, [rbp+dwFlags]; dwFlags
0x180148d40  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180148d47  mov     rdx, rcx; pszAlgId
0x180148d4a  mov     [r14], eax
0x180148d4d  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180148d51  mov     rdi, rax
0x180148d54  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180148d5b  nop     dword ptr [rax+rax+00h]
0x180148d60  mov     ebx, eax
0x180148d62  test    eax, eax
0x180148d64  js      loc_180148E9D
0x180148d6a  mov     ecx, 4
0x180148d6f  mov     [rsp+68h+cbSecret], edi; dwFlags
0x180148d73  mov     [rbp+var_24], ecx
0x180148d76  lea     rax, [rbp+var_24]
0x180148d7a  mov     r9d, ecx; cbOutput
0x180148d7d  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180148d82  mov     rcx, [rbp+phAlgorithm]; hObject
0x180148d86  lea     r8, [rbp+pbOutput]; pbOutput
0x180148d8a  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180148d91  call    cs:__imp_BCryptGetProperty
0x180148d98  nop     dword ptr [rax+rax+00h]
0x180148d9d  mov     ebx, eax
0x180148d9f  test    eax, eax
0x180148da1  js      loc_180148E9D
0x180148da7  mov     eax, dword ptr [rbp+pbOutput]
0x180148daa  mov     [r14], eax
0x180148dad  cmp     [rbp+cbOutput], edi
0x180148db0  jz      loc_180148E9D
0x180148db6  cmp     [rbp+cbOutput], eax
0x180148db9  jnb     short loc_180148DC5
0x180148dbb  mov     ebx, 0C0000023h
0x180148dc0  jmp     loc_180148E9D
0x180148dc5  mov     rcx, [rbp+phAlgorithm]; hObject
0x180148dc9  lea     rax, [rbp+var_24]
0x180148dcd  mov     r9d, 4; cbOutput
0x180148dd3  mov     [rsp+68h+cbSecret], edi; dwFlags
0x180148dd7  lea     r8, [rbp+var_28]; pbOutput
0x180148ddb  mov     [rbp+var_24], r9d
0x180148ddf  lea     rdx, pszProperty; "ObjectLength"
0x180148de6  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180148deb  call    cs:__imp_BCryptGetProperty
0x180148df2  nop     dword ptr [rax+rax+00h]
0x180148df7  mov     ebx, eax
0x180148df9  test    eax, eax
0x180148dfb  js      loc_180148E9D
0x180148e01  mov     ecx, dword ptr [rbp+var_28]; Size
0x180148e04  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180148e09  mov     r8d, dword ptr [rbp+var_28]; Size
0x180148e0d  xor     edx, edx; Val
0x180148e0f  mov     rcx, rax; void *
0x180148e12  mov     rdi, rax
0x180148e15  call    memset_0
0x180148e1a  mov     r8d, dword ptr [rbp+var_28]; Size
0x180148e1e  xor     edx, edx; Val
0x180148e20  mov     rcx, rdi; void *
0x180148e23  call    memset_0
0x180148e28  mov     eax, [rbp+arg_20]
0x180148e2b  lea     rdx, [rbp+phHash]; phHash
0x180148e2f  mov     r9d, dword ptr [rbp+var_28]; cbHashObject
0x180148e33  mov     r8, rdi; pbHashObject
0x180148e36  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180148e3a  mov     [rsp+68h+var_38], 0; dwFlags
0x180148e42  mov     [rsp+68h+cbSecret], eax; cbSecret
0x180148e46  mov     rax, [rbp+pbSecret]
0x180148e4a  mov     [rsp+68h+pcbResult], rax; pbSecret
0x180148e4f  call    cs:__imp_BCryptCreateHash
0x180148e56  nop     dword ptr [rax+rax+00h]
0x180148e5b  mov     ebx, eax
0x180148e5d  test    eax, eax
0x180148e5f  js      short loc_180148E9D
0x180148e61  mov     rcx, [rbp+phHash]; hHash
0x180148e65  xor     r9d, r9d; dwFlags
0x180148e68  mov     r8d, r12d; cbInput
0x180148e6b  mov     rdx, r13; pbInput
0x180148e6e  call    cs:__imp_BCryptHashData
0x180148e75  nop     dword ptr [rax+rax+00h]
0x180148e7a  mov     ebx, eax
0x180148e7c  test    eax, eax
0x180148e7e  js      short loc_180148E9D
0x180148e80  mov     r8d, [rbp+cbOutput]; cbOutput
0x180148e84  xor     r9d, r9d; dwFlags
0x180148e87  mov     rdx, [rbp+arg_28]; pbOutput
0x180148e8b  mov     rcx, [rbp+phHash]; hHash
0x180148e8f  call    cs:__imp_BCryptFinishHash
0x180148e96  nop     dword ptr [rax+rax+00h]
0x180148e9b  mov     ebx, eax
0x180148e9d  mov     rcx, [rbp+phHash]; hHash
0x180148ea1  test    rcx, rcx
0x180148ea4  jz      short loc_180148EB2
0x180148ea6  call    cs:__imp_BCryptDestroyHash
0x180148ead  nop     dword ptr [rax+rax+00h]
0x180148eb2  test    rdi, rdi
0x180148eb5  jz      short loc_180148ED6
0x180148eb7  mov     eax, dword ptr [rbp+var_28]
0x180148eba  mov     rcx, rdi
0x180148ebd  test    rax, rax
0x180148ec0  jz      short loc_180148ECE
0x180148ec2  mov     byte ptr [rcx], 0
0x180148ec5  inc     rcx
0x180148ec8  sub     rax, 1
0x180148ecc  jnz     short loc_180148EC2
0x180148ece  mov     rcx, rdi; Block
0x180148ed1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180148ed6  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180148eda  mov     dword ptr [rbp+var_28], 0
0x180148ee1  test    rcx, rcx
0x180148ee4  jz      short loc_180148EF4
0x180148ee6  xor     edx, edx; dwFlags
0x180148ee8  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180148eef  nop     dword ptr [rax+rax+00h]
0x180148ef4  mov     eax, ebx
0x180148ef6  add     rsp, 68h
0x180148efa  pop     r14
0x180148efc  pop     r13
0x180148efe  pop     r12
0x180148f00  pop     rdi
0x180148f01  pop     rbx
0x180148f02  pop     rbp
0x180148f03  retn
```
