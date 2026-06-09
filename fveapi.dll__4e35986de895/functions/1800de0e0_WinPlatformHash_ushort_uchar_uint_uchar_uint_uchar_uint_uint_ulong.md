# WinPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)

- ea: `0x1800de0e0`
- end: `0x1800de30b`
- name: `?WinPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z`
- size: `555`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszAlgId@<rcx>, PUCHAR pbInput@<rdx>, ULONG cbInput@<r8d>, unsigned __int8 *@<r9>, ULONG, PUCHAR, ULONG cbOutput, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18005f760`
- `0x1800de0e0`
- `0x18011efce`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800de2d0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800de2d0`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800de144`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800de144`
- `bcrypt!BCryptDestroyHash` at `0x1800de2a5`
- `bcrypt!BCryptDestroyHash` at `0x1800de2a5`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800de2ee`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800de2ee`
- `bcrypt!BCryptGetProperty` at `0x1800de181`
- `bcrypt!BCryptGetProperty` at `0x1800de1db`
- `bcrypt!BCryptGetProperty` at `0x1800de181`
- `bcrypt!BCryptGetProperty` at `0x1800de1db`
- `bcrypt!BCryptCreateHash` at `0x1800de24e`
- `bcrypt!BCryptCreateHash` at `0x1800de24e`
- `bcrypt!BCryptHashData` at `0x1800de26d`
- `bcrypt!BCryptHashData` at `0x1800de26d`
- `bcrypt!BCryptFinishHash` at `0x1800de28e`
- `bcrypt!BCryptFinishHash` at `0x1800de28e`

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
  void *v15; // rax
  __int64 v16; // rax
  _BYTE *v17; // rcx
  UCHAR v18[4]; // [rsp+40h] [rbp-28h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-24h] BYREF
  UCHAR pbOutput[8]; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+58h] [rbp-10h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  *(_DWORD *)v18 = 0;
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
          Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", v18, 4u, &pcbResult, 0);
          if ( Property >= 0 )
          {
            v15 = operator new(*(unsigned int *)v18);
            v12 = v15;
            if ( v15 )
            {
              memset_0(v15, 0, *(unsigned int *)v18);
              memset_0(v12, 0, *(unsigned int *)v18);
              Property = BCryptCreateHash(phAlgorithm, &phHash, (PUCHAR)v12, *(ULONG *)v18, a4, cbSecret, 0);
              if ( Property >= 0 )
              {
                Property = BCryptHashData(phHash, pbInput, cbInput, 0);
                if ( Property >= 0 )
                  Property = BCryptFinishHash(phHash, a6, cbOutput, 0);
              }
            }
            else
            {
              Property = -1073741801;
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
    v16 = *(unsigned int *)v18;
    v17 = v12;
    if ( *(_DWORD *)v18 )
    {
      do
      {
        *v17++ = 0;
        --v16;
      }
      while ( v16 );
    }
    operator delete(v12);
  }
  *(_DWORD *)v18 = 0;
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1800de0e0  mov     [rsp-30h+pbSecret], r9
0x1800de0e5  push    rbp
0x1800de0e6  push    rbx
0x1800de0e7  push    rdi
0x1800de0e8  push    r12
0x1800de0ea  push    r13
0x1800de0ec  push    r14
0x1800de0ee  mov     rbp, rsp
0x1800de0f1  sub     rsp, 68h
0x1800de0f5  xor     eax, eax
0x1800de0f7  mov     r12d, r8d
0x1800de0fa  mov     r13, rdx
0x1800de0fd  mov     [rbp+phAlgorithm], rax
0x1800de101  mov     [rbp+phHash], rax
0x1800de105  mov     dword ptr [rbp+var_28], eax
0x1800de108  mov     dword ptr [rbp+pbOutput], eax
0x1800de10b  mov     [rbp+var_24], eax
0x1800de10e  cmp     [rbp+cbOutput], eax
0x1800de111  jz      short loc_1800DE119
0x1800de113  cmp     [rbp+arg_28], rax
0x1800de117  jz      short loc_1800DE122
0x1800de119  mov     r14, [rbp+arg_38]
0x1800de11d  test    r14, r14
0x1800de120  jnz     short loc_1800DE12C
0x1800de122  mov     eax, 80070057h
0x1800de127  jmp     loc_1800DE2FC
0x1800de12c  mov     r9d, [rbp+dwFlags]; dwFlags
0x1800de130  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1800de137  mov     rdx, rcx; pszAlgId
0x1800de13a  mov     [r14], eax
0x1800de13d  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800de141  mov     rdi, rax
0x1800de144  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800de14b  nop     dword ptr [rax+rax+00h]
0x1800de150  mov     ebx, eax
0x1800de152  test    eax, eax
0x1800de154  js      loc_1800DE29C
0x1800de15a  mov     ecx, 4
0x1800de15f  mov     [rsp+68h+cbSecret], edi; dwFlags
0x1800de163  mov     [rbp+var_24], ecx
0x1800de166  lea     rax, [rbp+var_24]
0x1800de16a  mov     r9d, ecx; cbOutput
0x1800de16d  mov     [rsp+68h+pcbResult], rax; pcbResult
0x1800de172  mov     rcx, [rbp+phAlgorithm]; hObject
0x1800de176  lea     r8, [rbp+pbOutput]; pbOutput
0x1800de17a  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800de181  call    cs:__imp_BCryptGetProperty
0x1800de188  nop     dword ptr [rax+rax+00h]
0x1800de18d  mov     ebx, eax
0x1800de18f  test    eax, eax
0x1800de191  js      loc_1800DE29C
0x1800de197  mov     eax, dword ptr [rbp+pbOutput]
0x1800de19a  mov     [r14], eax
0x1800de19d  cmp     [rbp+cbOutput], edi
0x1800de1a0  jz      loc_1800DE29C
0x1800de1a6  cmp     [rbp+cbOutput], eax
0x1800de1a9  jnb     short loc_1800DE1B5
0x1800de1ab  mov     ebx, 0C0000023h
0x1800de1b0  jmp     loc_1800DE29C
0x1800de1b5  mov     rcx, [rbp+phAlgorithm]; hObject
0x1800de1b9  lea     rax, [rbp+var_24]
0x1800de1bd  mov     r9d, 4; cbOutput
0x1800de1c3  mov     [rsp+68h+cbSecret], edi; dwFlags
0x1800de1c7  lea     r8, [rbp+var_28]; pbOutput
0x1800de1cb  mov     [rbp+var_24], r9d
0x1800de1cf  lea     rdx, pszProperty; "ObjectLength"
0x1800de1d6  mov     [rsp+68h+pcbResult], rax; pcbResult
0x1800de1db  call    cs:__imp_BCryptGetProperty
0x1800de1e2  nop     dword ptr [rax+rax+00h]
0x1800de1e7  mov     ebx, eax
0x1800de1e9  test    eax, eax
0x1800de1eb  js      loc_1800DE29C
0x1800de1f1  mov     ecx, dword ptr [rbp+var_28]; Size
0x1800de1f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800de1f9  mov     rdi, rax
0x1800de1fc  test    rax, rax
0x1800de1ff  jnz     short loc_1800DE20B
0x1800de201  mov     ebx, 0C0000017h
0x1800de206  jmp     loc_1800DE29C
0x1800de20b  mov     r8d, dword ptr [rbp+var_28]; Size
0x1800de20f  xor     edx, edx; Val
0x1800de211  mov     rcx, rdi; void *
0x1800de214  call    memset_0
0x1800de219  mov     r8d, dword ptr [rbp+var_28]; Size
0x1800de21d  xor     edx, edx; Val
0x1800de21f  mov     rcx, rdi; void *
0x1800de222  call    memset_0
0x1800de227  mov     eax, [rbp+arg_20]
0x1800de22a  lea     rdx, [rbp+phHash]; phHash
0x1800de22e  mov     r9d, dword ptr [rbp+var_28]; cbHashObject
0x1800de232  mov     r8, rdi; pbHashObject
0x1800de235  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800de239  mov     [rsp+68h+var_38], 0; dwFlags
0x1800de241  mov     [rsp+68h+cbSecret], eax; cbSecret
0x1800de245  mov     rax, [rbp+pbSecret]
0x1800de249  mov     [rsp+68h+pcbResult], rax; pbSecret
0x1800de24e  call    cs:__imp_BCryptCreateHash
0x1800de255  nop     dword ptr [rax+rax+00h]
0x1800de25a  mov     ebx, eax
0x1800de25c  test    eax, eax
0x1800de25e  js      short loc_1800DE29C
0x1800de260  mov     rcx, [rbp+phHash]; hHash
0x1800de264  xor     r9d, r9d; dwFlags
0x1800de267  mov     r8d, r12d; cbInput
0x1800de26a  mov     rdx, r13; pbInput
0x1800de26d  call    cs:__imp_BCryptHashData
0x1800de274  nop     dword ptr [rax+rax+00h]
0x1800de279  mov     ebx, eax
0x1800de27b  test    eax, eax
0x1800de27d  js      short loc_1800DE29C
0x1800de27f  mov     r8d, [rbp+cbOutput]; cbOutput
0x1800de283  xor     r9d, r9d; dwFlags
0x1800de286  mov     rdx, [rbp+arg_28]; pbOutput
0x1800de28a  mov     rcx, [rbp+phHash]; hHash
0x1800de28e  call    cs:__imp_BCryptFinishHash
0x1800de295  nop     dword ptr [rax+rax+00h]
0x1800de29a  mov     ebx, eax
0x1800de29c  mov     rcx, [rbp+phHash]; hHash
0x1800de2a0  test    rcx, rcx
0x1800de2a3  jz      short loc_1800DE2B1
0x1800de2a5  call    cs:__imp_BCryptDestroyHash
0x1800de2ac  nop     dword ptr [rax+rax+00h]
0x1800de2b1  test    rdi, rdi
0x1800de2b4  jz      short loc_1800DE2DC
0x1800de2b6  mov     eax, dword ptr [rbp+var_28]
0x1800de2b9  mov     rcx, rdi
0x1800de2bc  test    rax, rax
0x1800de2bf  jz      short loc_1800DE2CD
0x1800de2c1  mov     byte ptr [rcx], 0
0x1800de2c4  inc     rcx
0x1800de2c7  sub     rax, 1
0x1800de2cb  jnz     short loc_1800DE2C1
0x1800de2cd  mov     rcx, rdi
0x1800de2d0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800de2d7  nop     dword ptr [rax+rax+00h]
0x1800de2dc  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800de2e0  mov     dword ptr [rbp+var_28], 0
0x1800de2e7  test    rcx, rcx
0x1800de2ea  jz      short loc_1800DE2FA
0x1800de2ec  xor     edx, edx; dwFlags
0x1800de2ee  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800de2f5  nop     dword ptr [rax+rax+00h]
0x1800de2fa  mov     eax, ebx
0x1800de2fc  add     rsp, 68h
0x1800de300  pop     r14
0x1800de302  pop     r13
0x1800de304  pop     r12
0x1800de306  pop     rdi
0x1800de307  pop     rbx
0x1800de308  pop     rbp
0x1800de309  retn
```
