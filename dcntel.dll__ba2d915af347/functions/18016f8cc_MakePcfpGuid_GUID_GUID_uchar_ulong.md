# MakePcfpGuid(_GUID *,_GUID *,uchar *,ulong)

- ea: `0x18016f8cc`
- end: `0x18016fb01`
- name: `?MakePcfpGuid@@YAJPEAU_GUID@@0PEAEK@Z`
- size: `565`
- prototype: `__int64 __fastcall(struct _GUID *, PUCHAR pbInput, PUCHAR, ULONG cbInput)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18016f40c`

## callees

- `0x180009efc`
- `0x18016f8cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18016f97d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18016fa51`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18016f97d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18016fa51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18016f96f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18016fa43`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18016fa99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18016fac9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18016f96f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18016fa43`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18016fa99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18016fac9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18016faa7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18016fad7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18016faa7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18016fad7`
- `bcrypt!BCryptFinishHash` at `0x18016fa71`
- `bcrypt!BCryptFinishHash` at `0x18016fa71`
- `bcrypt!BCryptHashData` at `0x18016f9de`
- `bcrypt!BCryptHashData` at `0x18016fa00`
- `bcrypt!BCryptHashData` at `0x18016f9de`
- `bcrypt!BCryptHashData` at `0x18016fa00`
- `bcrypt!BCryptCreateHash` at `0x18016f9bd`
- `bcrypt!BCryptCreateHash` at `0x18016f9bd`
- `bcrypt!BCryptGetProperty` at `0x18016f95c`
- `bcrypt!BCryptGetProperty` at `0x18016fa34`
- `bcrypt!BCryptGetProperty` at `0x18016f95c`
- `bcrypt!BCryptGetProperty` at `0x18016fa34`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18016fae8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18016fae8`
- `bcrypt!BCryptDestroyHash` at `0x18016fab6`
- `bcrypt!BCryptDestroyHash` at `0x18016fab6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18016f926`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18016f926`

## pseudocode

```c
__int64 __fastcall MakePcfpGuid(struct _GUID *a1, PUCHAR pbInput, PUCHAR a3, ULONG cbInput)
{
  UCHAR *v4; // r14
  NTSTATUS v9; // eax
  unsigned int v10; // ebx
  NTSTATUS Property; // eax
  unsigned int v12; // ebx
  HANDLE ProcessHeap; // rax
  UCHAR *v14; // rax
  NTSTATUS v15; // eax
  size_t v16; // rsi
  NTSTATUS v17; // eax
  NTSTATUS v18; // eax
  NTSTATUS v19; // eax
  unsigned int v20; // ebx
  HANDLE v21; // rax
  UCHAR *v22; // rax
  UCHAR *v23; // rdi
  NTSTATUS v24; // eax
  HANDLE v25; // rax
  HANDLE v26; // rax
  UCHAR v28[4]; // [rsp+40h] [rbp-28h] BYREF
  UCHAR pbOutput[4]; // [rsp+44h] [rbp-24h] BYREF
  ULONG pcbResult; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-18h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-10h] BYREF

  v4 = 0;
  phAlgorithm = 0;
  phHash = 0;
  *a1 = 0;
  pcbResult = 0;
  *(_DWORD *)v28 = 0;
  *(_DWORD *)pbOutput = 0;
  v9 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", L"Microsoft Primitive Provider", 0);
  v10 = v9 | 0x10000000;
  if ( v9 >= 0 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    v10 = Property | 0x10000000;
    if ( Property >= 0 )
    {
      v12 = *(_DWORD *)pbOutput;
      ProcessHeap = GetProcessHeap();
      v14 = (UCHAR *)HeapAlloc(ProcessHeap, 0, v12);
      v4 = v14;
      if ( !v14 )
      {
LABEL_4:
        v10 = -2147024882;
        goto LABEL_15;
      }
      v15 = BCryptCreateHash(phAlgorithm, &phHash, v14, *(ULONG *)pbOutput, 0, 0, 0);
      v10 = v15 | 0x10000000;
      if ( v15 >= 0 )
      {
        v16 = 16;
        v17 = BCryptHashData(phHash, pbInput, 0x10u, 0);
        v10 = v17 | 0x10000000;
        if ( v17 >= 0 )
        {
          v18 = BCryptHashData(phHash, a3, cbInput, 0);
          v10 = v18 | 0x10000000;
          if ( v18 >= 0 )
          {
            v19 = BCryptGetProperty(phAlgorithm, L"HashDigestLength", v28, 4u, &pcbResult, 0);
            v10 = v19 | 0x10000000;
            if ( v19 >= 0 )
            {
              v20 = *(_DWORD *)v28;
              v21 = GetProcessHeap();
              v22 = (UCHAR *)HeapAlloc(v21, 0, v20);
              v23 = v22;
              if ( !v22 )
                goto LABEL_4;
              v24 = BCryptFinishHash(phHash, v22, *(ULONG *)v28, 0);
              v10 = v24 | 0x10000000;
              if ( v24 >= 0 )
              {
                if ( *(_DWORD *)v28 <= 0x10u )
                  v16 = *(unsigned int *)v28;
                memcpy_0(a1, v23, v16);
                v10 = 0;
              }
              v25 = GetProcessHeap();
              HeapFree(v25, 0, v23);
            }
          }
        }
      }
    }
  }
LABEL_15:
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( v4 )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v4);
  }
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return v10;
}

```

## disassembly

```asm
0x18016f8cc  push    rbp
0x18016f8ce  push    rbx
0x18016f8cf  push    rsi
0x18016f8d0  push    rdi
0x18016f8d1  push    r12
0x18016f8d3  push    r13
0x18016f8d5  push    r14
0x18016f8d7  push    r15
0x18016f8d9  mov     rbp, rsp
0x18016f8dc  sub     rsp, 68h
0x18016f8e0  xor     r14d, r14d
0x18016f8e3  mov     [rbp+phAlgorithm], 0
0x18016f8eb  xorps   xmm0, xmm0
0x18016f8ee  mov     [rbp+phHash], 0
0x18016f8f6  movups  xmmword ptr [rcx], xmm0
0x18016f8f9  mov     r12d, r9d
0x18016f8fc  mov     [rbp+var_20], r14d
0x18016f900  mov     r13, r8
0x18016f903  mov     dword ptr [rbp+var_28], r14d
0x18016f907  mov     rdi, rdx
0x18016f90a  mov     dword ptr [rbp+pbOutput], r14d
0x18016f90e  mov     r15, rcx
0x18016f911  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18016f918  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18016f91c  xor     r9d, r9d; dwFlags
0x18016f91f  lea     rdx, aSha1; "SHA1"
0x18016f926  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18016f92c  mov     ebx, eax
0x18016f92e  mov     esi, 10000000h
0x18016f933  or      ebx, esi
0x18016f935  jl      loc_18016FAAD
0x18016f93b  mov     rcx, [rbp+phAlgorithm]; hObject
0x18016f93f  lea     rax, [rbp+var_20]
0x18016f943  mov     [rsp+68h+dwFlags], r14d; dwFlags
0x18016f948  lea     r9d, [r14+4]; cbOutput
0x18016f94c  lea     r8, [rbp+pbOutput]; pbOutput
0x18016f950  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18016f955  lea     rdx, aObjectlength; "ObjectLength"
0x18016f95c  call    cs:__imp_BCryptGetProperty
0x18016f962  mov     ebx, eax
0x18016f964  or      ebx, esi
0x18016f966  jl      loc_18016FAAD
0x18016f96c  mov     ebx, dword ptr [rbp+pbOutput]
0x18016f96f  call    cs:__imp_GetProcessHeap
0x18016f975  mov     r8d, ebx; dwBytes
0x18016f978  xor     edx, edx; dwFlags
0x18016f97a  mov     rcx, rax; hHeap
0x18016f97d  call    cs:__imp_HeapAlloc
0x18016f983  mov     r14, rax
0x18016f986  test    rax, rax
0x18016f989  jnz     short loc_18016F995
0x18016f98b  mov     ebx, 8007000Eh
0x18016f990  jmp     loc_18016FAAD
0x18016f995  mov     r9d, dword ptr [rbp+pbOutput]; cbHashObject
0x18016f999  lea     rdx, [rbp+phHash]; phHash
0x18016f99d  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18016f9a1  mov     r8, rax; pbHashObject
0x18016f9a4  mov     [rsp+68h+var_38], 0; dwFlags
0x18016f9ac  mov     [rsp+68h+dwFlags], 0; cbSecret
0x18016f9b4  mov     [rsp+68h+pcbResult], 0; pbSecret
0x18016f9bd  call    cs:__imp_BCryptCreateHash
0x18016f9c3  mov     ebx, eax
0x18016f9c5  or      ebx, esi
0x18016f9c7  jl      loc_18016FAAD
0x18016f9cd  mov     rcx, [rbp+phHash]; hHash
0x18016f9d1  xor     r9d, r9d; dwFlags
0x18016f9d4  mov     rdx, rdi; pbInput
0x18016f9d7  lea     esi, [r9+10h]
0x18016f9db  mov     r8d, esi; cbInput
0x18016f9de  call    cs:__imp_BCryptHashData
0x18016f9e4  mov     ebx, eax
0x18016f9e6  mov     edi, 10000000h
0x18016f9eb  or      ebx, edi
0x18016f9ed  jl      loc_18016FAAD
0x18016f9f3  mov     rcx, [rbp+phHash]; hHash
0x18016f9f7  xor     r9d, r9d; dwFlags
0x18016f9fa  mov     r8d, r12d; cbInput
0x18016f9fd  mov     rdx, r13; pbInput
0x18016fa00  call    cs:__imp_BCryptHashData
0x18016fa06  mov     ebx, eax
0x18016fa08  or      ebx, edi
0x18016fa0a  jl      loc_18016FAAD
0x18016fa10  mov     rcx, [rbp+phAlgorithm]; hObject
0x18016fa14  lea     rax, [rbp+var_20]
0x18016fa18  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18016fa20  lea     r9d, [rsi-0Ch]; cbOutput
0x18016fa24  lea     r8, [rbp+var_28]; pbOutput
0x18016fa28  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18016fa2d  lea     rdx, pszProperty; "HashDigestLength"
0x18016fa34  call    cs:__imp_BCryptGetProperty
0x18016fa3a  mov     ebx, eax
0x18016fa3c  or      ebx, edi
0x18016fa3e  jl      short loc_18016FAAD
0x18016fa40  mov     ebx, dword ptr [rbp+var_28]
0x18016fa43  call    cs:__imp_GetProcessHeap
0x18016fa49  mov     r8d, ebx; dwBytes
0x18016fa4c  xor     edx, edx; dwFlags
0x18016fa4e  mov     rcx, rax; hHeap
0x18016fa51  call    cs:__imp_HeapAlloc
0x18016fa57  mov     rdi, rax
0x18016fa5a  test    rax, rax
0x18016fa5d  jz      loc_18016F98B
0x18016fa63  mov     r8d, dword ptr [rbp+var_28]; cbOutput
0x18016fa67  xor     r9d, r9d; dwFlags
0x18016fa6a  mov     rcx, [rbp+phHash]; hHash
0x18016fa6e  mov     rdx, rax; pbOutput
0x18016fa71  call    cs:__imp_BCryptFinishHash
0x18016fa77  mov     ebx, eax
0x18016fa79  or      ebx, 10000000h
0x18016fa7f  jl      short loc_18016FA99
0x18016fa81  cmp     dword ptr [rbp+var_28], esi
0x18016fa84  ja      short loc_18016FA89
0x18016fa86  mov     esi, dword ptr [rbp+var_28]
0x18016fa89  mov     r8, rsi; Size
0x18016fa8c  mov     rdx, rdi; Src
0x18016fa8f  mov     rcx, r15; void *
0x18016fa92  call    memcpy_0
0x18016fa97  xor     ebx, ebx
0x18016fa99  call    cs:__imp_GetProcessHeap
0x18016fa9f  mov     r8, rdi; lpMem
0x18016faa2  xor     edx, edx; dwFlags
0x18016faa4  mov     rcx, rax; hHeap
0x18016faa7  call    cs:__imp_HeapFree
0x18016faad  mov     rcx, [rbp+phHash]; hHash
0x18016fab1  test    rcx, rcx
0x18016fab4  jz      short loc_18016FAC4
0x18016fab6  call    cs:__imp_BCryptDestroyHash
0x18016fabc  mov     [rbp+phHash], 0
0x18016fac4  test    r14, r14
0x18016fac7  jz      short loc_18016FADD
0x18016fac9  call    cs:__imp_GetProcessHeap
0x18016facf  mov     r8, r14; lpMem
0x18016fad2  xor     edx, edx; dwFlags
0x18016fad4  mov     rcx, rax; hHeap
0x18016fad7  call    cs:__imp_HeapFree
0x18016fadd  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18016fae1  test    rcx, rcx
0x18016fae4  jz      short loc_18016FAEE
0x18016fae6  xor     edx, edx; dwFlags
0x18016fae8  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18016faee  mov     eax, ebx
0x18016faf0  add     rsp, 68h
0x18016faf4  pop     r15
0x18016faf6  pop     r14
0x18016faf8  pop     r13
0x18016fafa  pop     r12
0x18016fafc  pop     rdi
0x18016fafd  pop     rsi
0x18016fafe  pop     rbx
0x18016faff  pop     rbp
0x18016fb00  retn
```
