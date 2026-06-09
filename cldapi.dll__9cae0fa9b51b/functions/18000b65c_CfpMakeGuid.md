# CfpMakeGuid

- ea: `0x18000b65c`
- end: `0x18000b89c`
- name: `CfpMakeGuid`
- size: `576`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800064e0`

## callees

- `0x18000b65c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000b6b8`
- `ntdll!RtlNtStatusToDosError` at `0x18000b70c`
- `ntdll!RtlNtStatusToDosError` at `0x18000b7a8`
- `ntdll!RtlNtStatusToDosError` at `0x18000b7df`
- `ntdll!RtlNtStatusToDosError` at `0x18000b817`
- `ntdll!RtlNtStatusToDosError` at `0x18000b6b8`
- `ntdll!RtlNtStatusToDosError` at `0x18000b70c`
- `ntdll!RtlNtStatusToDosError` at `0x18000b7a8`
- `ntdll!RtlNtStatusToDosError` at `0x18000b7df`
- `ntdll!RtlNtStatusToDosError` at `0x18000b817`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b72f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b849`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b72f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b849`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b746`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b746`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b85d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b85d`
- `bcrypt!BCryptHashData` at `0x18000b7d1`
- `bcrypt!BCryptHashData` at `0x18000b7d1`
- `bcrypt!BCryptDestroyHash` at `0x18000b838`
- `bcrypt!BCryptDestroyHash` at `0x18000b838`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000b874`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000b874`
- `bcrypt!BCryptFinishHash` at `0x18000b809`
- `bcrypt!BCryptFinishHash` at `0x18000b809`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000b6aa`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000b6aa`
- `bcrypt!BCryptGetProperty` at `0x18000b6fe`
- `bcrypt!BCryptGetProperty` at `0x18000b6fe`
- `bcrypt!BCryptCreateHash` at `0x18000b79a`
- `bcrypt!BCryptCreateHash` at `0x18000b79a`

## pseudocode

```c
__int64 __fastcall CfpMakeGuid(PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput)
{
  UCHAR *v6; // rdi
  NTSTATUS v7; // eax
  signed int v8; // eax
  signed int v9; // ebx
  NTSTATUS Property; // eax
  signed int v11; // eax
  ULONG v12; // ebx
  HANDLE ProcessHeap; // rax
  NTSTATUS v14; // eax
  signed int v15; // eax
  NTSTATUS v16; // eax
  signed int v17; // eax
  NTSTATUS v18; // eax
  signed int v19; // eax
  HANDLE v20; // rax
  ULONG cbOutput; // [rsp+40h] [rbp-20h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-18h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-10h] BYREF
  ULONG pbOutputa; // [rsp+A8h] [rbp+48h] BYREF

  phAlgorithm = 0;
  cbOutput = 4;
  v6 = 0;
  pbOutputa = 0;
  phHash = 0;
  v7 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"MD5", L"Microsoft Primitive Provider", 0);
  v8 = RtlNtStatusToDosError(v7);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 >= 0 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)&pbOutputa, cbOutput, &cbOutput, 0);
    v11 = RtlNtStatusToDosError(Property);
    v9 = v11;
    if ( v11 > 0 )
      v9 = (unsigned __int16)v11 | 0x80070000;
    if ( v9 >= 0 )
    {
      v12 = pbOutputa;
      ProcessHeap = GetProcessHeap();
      v6 = (UCHAR *)HeapAlloc(ProcessHeap, 8u, v12);
      v9 = v6 == 0 ? 8 : 0;
      if ( !v6 )
        v9 |= 0x80070000;
      if ( v9 >= 0 )
      {
        v14 = BCryptCreateHash(phAlgorithm, &phHash, v6, pbOutputa, 0, 0, 0);
        v15 = RtlNtStatusToDosError(v14);
        v9 = v15;
        if ( v15 > 0 )
          v9 = (unsigned __int16)v15 | 0x80070000;
        if ( v9 >= 0 )
        {
          v16 = BCryptHashData(phHash, pbInput, cbInput, 0);
          v17 = RtlNtStatusToDosError(v16);
          v9 = v17;
          if ( v17 > 0 )
            v9 = (unsigned __int16)v17 | 0x80070000;
          if ( v9 >= 0 )
          {
            v18 = BCryptFinishHash(phHash, pbOutput, 0x10u, 0);
            v19 = RtlNtStatusToDosError(v18);
            v9 = v19;
            if ( v19 > 0 )
              v9 = (unsigned __int16)v19 | 0x80070000;
          }
        }
      }
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v6 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v6);
  }
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000b65c  mov     [rsp-28h+arg_0], rbx
0x18000b661  mov     [rsp-28h+arg_8], rsi
0x18000b666  push    rbp
0x18000b667  push    rdi
0x18000b668  push    r13
0x18000b66a  push    r14
0x18000b66c  push    r15
0x18000b66e  mov     rbp, rsp
0x18000b671  sub     rsp, 60h
0x18000b675  mov     r15, r8
0x18000b678  mov     [rbp+phAlgorithm], 0
0x18000b680  mov     esi, edx
0x18000b682  mov     [rbp+cbOutput], 4
0x18000b689  mov     r14, rcx
0x18000b68c  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18000b693  xor     edi, edi
0x18000b695  lea     rdx, pszAlgId; "MD5"
0x18000b69c  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18000b6a0  mov     [rbp+pbOutput], edi
0x18000b6a3  xor     r9d, r9d; dwFlags
0x18000b6a6  mov     [rbp+phHash], rdi
0x18000b6aa  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000b6b1  nop     dword ptr [rax+rax+00h]
0x18000b6b6  mov     ecx, eax; Status
0x18000b6b8  call    cs:__imp_RtlNtStatusToDosError
0x18000b6bf  nop     dword ptr [rax+rax+00h]
0x18000b6c4  mov     ebx, eax
0x18000b6c6  mov     r13d, 80070000h
0x18000b6cc  test    eax, eax
0x18000b6ce  jle     short loc_18000B6D6
0x18000b6d0  movzx   ebx, ax
0x18000b6d3  or      ebx, r13d
0x18000b6d6  test    ebx, ebx
0x18000b6d8  js      loc_18000B82F
0x18000b6de  mov     r9d, [rbp+cbOutput]; cbOutput
0x18000b6e2  lea     rax, [rbp+cbOutput]
0x18000b6e6  mov     rcx, [rbp+phAlgorithm]; hObject
0x18000b6ea  lea     r8, [rbp+pbOutput]; pbOutput
0x18000b6ee  mov     [rsp+60h+dwFlags], edi; dwFlags
0x18000b6f2  lea     rdx, pszProperty; "ObjectLength"
0x18000b6f9  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18000b6fe  call    cs:__imp_BCryptGetProperty
0x18000b705  nop     dword ptr [rax+rax+00h]
0x18000b70a  mov     ecx, eax; Status
0x18000b70c  call    cs:__imp_RtlNtStatusToDosError
0x18000b713  nop     dword ptr [rax+rax+00h]
0x18000b718  mov     ebx, eax
0x18000b71a  test    eax, eax
0x18000b71c  jle     short loc_18000B724
0x18000b71e  movzx   ebx, ax
0x18000b721  or      ebx, r13d
0x18000b724  test    ebx, ebx
0x18000b726  js      loc_18000B82F
0x18000b72c  mov     ebx, [rbp+pbOutput]
0x18000b72f  call    cs:__imp_GetProcessHeap
0x18000b736  nop     dword ptr [rax+rax+00h]
0x18000b73b  mov     r8d, ebx; dwBytes
0x18000b73e  mov     edx, 8; dwFlags
0x18000b743  mov     rcx, rax; hHeap
0x18000b746  call    cs:__imp_HeapAlloc
0x18000b74d  nop     dword ptr [rax+rax+00h]
0x18000b752  mov     rdi, rax
0x18000b755  neg     rax
0x18000b758  sbb     ebx, ebx
0x18000b75a  not     ebx
0x18000b75c  and     ebx, 8
0x18000b75f  mov     eax, ebx
0x18000b761  or      eax, r13d
0x18000b764  test    rdi, rdi
0x18000b767  cmovz   ebx, eax
0x18000b76a  test    ebx, ebx
0x18000b76c  js      loc_18000B82F
0x18000b772  mov     r9d, [rbp+pbOutput]; cbHashObject
0x18000b776  lea     rdx, [rbp+phHash]; phHash
0x18000b77a  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18000b77e  mov     r8, rdi; pbHashObject
0x18000b781  mov     [rsp+60h+var_30], 0; dwFlags
0x18000b789  mov     [rsp+60h+dwFlags], 0; cbSecret
0x18000b791  mov     [rsp+60h+pcbResult], 0; pbSecret
0x18000b79a  call    cs:__imp_BCryptCreateHash
0x18000b7a1  nop     dword ptr [rax+rax+00h]
0x18000b7a6  mov     ecx, eax; Status
0x18000b7a8  call    cs:__imp_RtlNtStatusToDosError
0x18000b7af  nop     dword ptr [rax+rax+00h]
0x18000b7b4  mov     ebx, eax
0x18000b7b6  test    eax, eax
0x18000b7b8  jle     short loc_18000B7C0
0x18000b7ba  movzx   ebx, ax
0x18000b7bd  or      ebx, r13d
0x18000b7c0  test    ebx, ebx
0x18000b7c2  js      short loc_18000B82F
0x18000b7c4  mov     rcx, [rbp+phHash]; hHash
0x18000b7c8  xor     r9d, r9d; dwFlags
0x18000b7cb  mov     r8d, esi; cbInput
0x18000b7ce  mov     rdx, r14; pbInput
0x18000b7d1  call    cs:__imp_BCryptHashData
0x18000b7d8  nop     dword ptr [rax+rax+00h]
0x18000b7dd  mov     ecx, eax; Status
0x18000b7df  call    cs:__imp_RtlNtStatusToDosError
0x18000b7e6  nop     dword ptr [rax+rax+00h]
0x18000b7eb  mov     ebx, eax
0x18000b7ed  test    eax, eax
0x18000b7ef  jle     short loc_18000B7F7
0x18000b7f1  movzx   ebx, ax
0x18000b7f4  or      ebx, r13d
0x18000b7f7  test    ebx, ebx
0x18000b7f9  js      short loc_18000B82F
0x18000b7fb  mov     rcx, [rbp+phHash]; hHash
0x18000b7ff  xor     r9d, r9d; dwFlags
0x18000b802  mov     rdx, r15; pbOutput
0x18000b805  lea     r8d, [r9+10h]; cbOutput
0x18000b809  call    cs:__imp_BCryptFinishHash
0x18000b810  nop     dword ptr [rax+rax+00h]
0x18000b815  mov     ecx, eax; Status
0x18000b817  call    cs:__imp_RtlNtStatusToDosError
0x18000b81e  nop     dword ptr [rax+rax+00h]
0x18000b823  mov     ebx, eax
0x18000b825  test    eax, eax
0x18000b827  jle     short loc_18000B82F
0x18000b829  movzx   ebx, ax
0x18000b82c  or      ebx, r13d
0x18000b82f  mov     rcx, [rbp+phHash]; hHash
0x18000b833  test    rcx, rcx
0x18000b836  jz      short loc_18000B844
0x18000b838  call    cs:__imp_BCryptDestroyHash
0x18000b83f  nop     dword ptr [rax+rax+00h]
0x18000b844  test    rdi, rdi
0x18000b847  jz      short loc_18000B869
0x18000b849  call    cs:__imp_GetProcessHeap
0x18000b850  nop     dword ptr [rax+rax+00h]
0x18000b855  mov     r8, rdi; lpMem
0x18000b858  xor     edx, edx; dwFlags
0x18000b85a  mov     rcx, rax; hHeap
0x18000b85d  call    cs:__imp_HeapFree
0x18000b864  nop     dword ptr [rax+rax+00h]
0x18000b869  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18000b86d  test    rcx, rcx
0x18000b870  jz      short loc_18000B880
0x18000b872  xor     edx, edx; dwFlags
0x18000b874  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000b87b  nop     dword ptr [rax+rax+00h]
0x18000b880  lea     r11, [rsp+60h+var_s0]
0x18000b885  mov     eax, ebx
0x18000b887  mov     rbx, [r11+30h]
0x18000b88b  mov     rsi, [r11+38h]
0x18000b88f  mov     rsp, r11
0x18000b892  pop     r15
0x18000b894  pop     r14
0x18000b896  pop     r13
0x18000b898  pop     rdi
0x18000b899  pop     rbp
0x18000b89a  retn
```
