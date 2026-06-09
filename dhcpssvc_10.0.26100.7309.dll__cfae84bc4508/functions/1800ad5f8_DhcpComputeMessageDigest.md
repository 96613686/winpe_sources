# DhcpComputeMessageDigest

- ea: `0x1800ad5f8`
- end: `0x1800ad800`
- name: `DhcpComputeMessageDigest`
- size: `520`
- prototype: `__int64 __fastcall(const void *, unsigned int, const void *, unsigned int, BCRYPT_HANDLE hObject, unsigned __int16, PUCHAR *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800ad428`
- `0x1800ad808`

## callees

- `0x1800ad5f8`
- `0x1800cc982`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800ad787`
- `ntdll!RtlNtStatusToDosError` at `0x1800ad787`
- `bcrypt!BCryptCreateHash` at `0x1800ad739`
- `bcrypt!BCryptCreateHash` at `0x1800ad739`
- `bcrypt!BCryptHashData` at `0x1800ad756`
- `bcrypt!BCryptHashData` at `0x1800ad756`
- `bcrypt!BCryptDestroyHash` at `0x1800ad7bc`
- `bcrypt!BCryptDestroyHash` at `0x1800ad7bc`
- `bcrypt!BCryptFinishHash` at `0x1800ad775`
- `bcrypt!BCryptFinishHash` at `0x1800ad775`
- `bcrypt!BCryptGetProperty` at `0x1800ad6e7`
- `bcrypt!BCryptGetProperty` at `0x1800ad6e7`
- `KERNEL32!HeapAlloc` at `0x1800ad64f`
- `KERNEL32!HeapAlloc` at `0x1800ad6a9`
- `KERNEL32!HeapAlloc` at `0x1800ad709`
- `KERNEL32!HeapAlloc` at `0x1800ad64f`
- `KERNEL32!HeapAlloc` at `0x1800ad6a9`
- `KERNEL32!HeapAlloc` at `0x1800ad709`
- `KERNEL32!HeapFree` at `0x1800ad7a1`
- `KERNEL32!HeapFree` at `0x1800ad7d9`
- `KERNEL32!HeapFree` at `0x1800ad7a1`
- `KERNEL32!HeapFree` at `0x1800ad7d9`

## pseudocode

```c
__int64 __fastcall DhcpComputeMessageDigest(
        const void *a1,
        unsigned int a2,
        const void *a3,
        unsigned int a4,
        BCRYPT_HANDLE hObject,
        unsigned __int16 a6,
        PUCHAR *a7)
{
  BCRYPT_HASH_HANDLE v7; // rcx
  size_t v8; // r15
  ULONG v9; // edi
  UCHAR *v10; // rsi
  size_t v11; // rbx
  ULONG v13; // r13d
  char *v14; // rax
  char *v15; // r14
  PUCHAR *v16; // rbx
  SIZE_T v17; // r8
  HANDLE v18; // rcx
  UCHAR *v19; // rax
  NTSTATUS Property; // eax
  UCHAR *v21; // rax
  ULONG pcbResult; // [rsp+40h] [rbp-10h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-8h] BYREF
  ULONG pbOutput; // [rsp+A8h] [rbp+58h] BYREF

  v7 = 0;
  v8 = a4;
  pbOutput = 0;
  v9 = 0;
  pcbResult = 0;
  v10 = 0;
  v11 = a2;
  phHash = 0;
  if ( a4 && a3 )
  {
    v13 = a2 + a4;
    v14 = (char *)HeapAlloc(gDhcpHeap, 8u, a2 + a4);
    v15 = v14;
    if ( !v14 )
    {
      v9 = 8;
LABEL_5:
      v7 = phHash;
      goto LABEL_16;
    }
    memcpy_0(v14, a1, v11);
    memcpy_0(&v15[v11], a3, v8);
    v16 = a7;
    v17 = a6;
    v18 = gDhcpHeap;
    *a7 = 0;
    v19 = (UCHAR *)HeapAlloc(v18, 8u, v17);
    *v16 = v19;
    if ( !v19 )
      goto LABEL_7;
    Property = BCryptGetProperty(hObject, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
    if ( !Property )
    {
      v21 = (UCHAR *)HeapAlloc(gDhcpHeap, 8u, pbOutput);
      v10 = v21;
      if ( !v21 )
      {
LABEL_7:
        v9 = 8;
LABEL_14:
        HeapFree(gDhcpHeap, 0, v15);
        goto LABEL_5;
      }
      Property = BCryptCreateHash(hObject, &phHash, v21, pbOutput, 0, 0, 0);
      if ( !Property )
      {
        Property = BCryptHashData(phHash, (PUCHAR)v15, v13, 0);
        if ( !Property )
        {
          Property = BCryptFinishHash(phHash, *v16, a6, 0);
          if ( !Property )
            goto LABEL_14;
        }
      }
    }
    v9 = RtlNtStatusToDosError(Property);
    goto LABEL_14;
  }
  v9 = 87;
LABEL_16:
  if ( v7 )
    BCryptDestroyHash(v7);
  if ( v10 )
    HeapFree(gDhcpHeap, 0, v10);
  return v9;
}

```

## disassembly

```asm
0x1800ad5f8  mov     [rsp-38h+arg_8], rbx
0x1800ad5fd  mov     [rsp-38h+Src], rcx
0x1800ad602  push    rbp
0x1800ad603  push    rsi
0x1800ad604  push    rdi
0x1800ad605  push    r12
0x1800ad607  push    r13
0x1800ad609  push    r14
0x1800ad60b  push    r15
0x1800ad60d  mov     rbp, rsp
0x1800ad610  sub     rsp, 50h
0x1800ad614  xor     ecx, ecx; hHash
0x1800ad616  mov     r15d, r9d
0x1800ad619  and     [rbp+pbOutput], ecx
0x1800ad61c  xor     edi, edi
0x1800ad61e  and     [rbp+var_10], ecx
0x1800ad621  xor     esi, esi
0x1800ad623  mov     ebx, edx
0x1800ad625  mov     r12, r8
0x1800ad628  mov     [rbp+phHash], rcx
0x1800ad62c  test    r9d, r9d
0x1800ad62f  jz      loc_1800AD7B2
0x1800ad635  test    r8, r8
0x1800ad638  jz      loc_1800AD7B2
0x1800ad63e  mov     rcx, cs:gDhcpHeap; hHeap
0x1800ad645  lea     r13d, [rbx+r15]
0x1800ad649  mov     r8d, r13d; dwBytes
0x1800ad64c  lea     edx, [rdi+8]; dwFlags
0x1800ad64f  call    cs:__imp_HeapAlloc
0x1800ad656  nop     dword ptr [rax+rax+00h]
0x1800ad65b  mov     r14, rax
0x1800ad65e  test    rax, rax
0x1800ad661  jnz     short loc_1800AD66F
0x1800ad663  lea     edi, [rsi+8]
0x1800ad666  mov     rcx, [rbp+phHash]
0x1800ad66a  jmp     loc_1800AD7B7
0x1800ad66f  mov     rdx, [rbp+Src]; Src
0x1800ad673  mov     r8, rbx; Size
0x1800ad676  mov     rcx, r14; void *
0x1800ad679  call    memcpy_0
0x1800ad67e  mov     r8, r15; Size
0x1800ad681  lea     rcx, [rbx+r14]; void *
0x1800ad685  mov     rdx, r12; Src
0x1800ad688  call    memcpy_0
0x1800ad68d  mov     rbx, [rbp+arg_30]
0x1800ad691  mov     r15d, 8
0x1800ad697  movzx   r8d, [rbp+arg_28]; dwBytes
0x1800ad69c  mov     edx, r15d; dwFlags
0x1800ad69f  mov     rcx, cs:gDhcpHeap; hHeap
0x1800ad6a6  and     [rbx], rsi
0x1800ad6a9  call    cs:__imp_HeapAlloc
0x1800ad6b0  nop     dword ptr [rax+rax+00h]
0x1800ad6b5  mov     [rbx], rax
0x1800ad6b8  test    rax, rax
0x1800ad6bb  jnz     short loc_1800AD6C5
0x1800ad6bd  mov     edi, r15d
0x1800ad6c0  jmp     loc_1800AD795
0x1800ad6c5  and     [rsp+50h+var_28], esi
0x1800ad6c9  lea     rax, [rbp+var_10]
0x1800ad6cd  mov     rcx, [rbp+hObject]; hObject
0x1800ad6d1  lea     r8, [rbp+pbOutput]; pbOutput
0x1800ad6d5  mov     r9d, 4; cbOutput
0x1800ad6db  mov     [rsp+50h+pcbResult], rax; pbSecret
0x1800ad6e0  lea     rdx, aObjectlength; "ObjectLength"
0x1800ad6e7  call    cs:__imp_BCryptGetProperty
0x1800ad6ee  nop     dword ptr [rax+rax+00h]
0x1800ad6f3  test    eax, eax
0x1800ad6f5  jnz     loc_1800AD785
0x1800ad6fb  mov     r8d, [rbp+pbOutput]; dwBytes
0x1800ad6ff  mov     edx, r15d; dwFlags
0x1800ad702  mov     rcx, cs:gDhcpHeap; hHeap
0x1800ad709  call    cs:__imp_HeapAlloc
0x1800ad710  nop     dword ptr [rax+rax+00h]
0x1800ad715  mov     rsi, rax
0x1800ad718  test    rax, rax
0x1800ad71b  jz      short loc_1800AD6BD
0x1800ad71d  and     [rsp+50h+var_20], edi
0x1800ad721  lea     rdx, [rbp+phHash]; phHash
0x1800ad725  and     [rsp+50h+var_28], edi
0x1800ad729  mov     r8, rax; pbHashObject
0x1800ad72c  mov     r9d, [rbp+pbOutput]; cbHashObject
0x1800ad730  mov     rcx, [rbp+hObject]; hAlgorithm
0x1800ad734  and     [rsp+50h+pcbResult], rdi
0x1800ad739  call    cs:__imp_BCryptCreateHash
0x1800ad740  nop     dword ptr [rax+rax+00h]
0x1800ad745  test    eax, eax
0x1800ad747  jnz     short loc_1800AD785
0x1800ad749  mov     rcx, [rbp+phHash]; hHash
0x1800ad74d  xor     r9d, r9d; dwFlags
0x1800ad750  mov     r8d, r13d; cbInput
0x1800ad753  mov     rdx, r14; pbInput
0x1800ad756  call    cs:__imp_BCryptHashData
0x1800ad75d  nop     dword ptr [rax+rax+00h]
0x1800ad762  test    eax, eax
0x1800ad764  jnz     short loc_1800AD785
0x1800ad766  movzx   r8d, [rbp+arg_28]; cbOutput
0x1800ad76b  xor     r9d, r9d; dwFlags
0x1800ad76e  mov     rdx, [rbx]; pbOutput
0x1800ad771  mov     rcx, [rbp+phHash]; hHash
0x1800ad775  call    cs:__imp_BCryptFinishHash
0x1800ad77c  nop     dword ptr [rax+rax+00h]
0x1800ad781  test    eax, eax
0x1800ad783  jz      short loc_1800AD795
0x1800ad785  mov     ecx, eax; Status
0x1800ad787  call    cs:__imp_RtlNtStatusToDosError
0x1800ad78e  nop     dword ptr [rax+rax+00h]
0x1800ad793  mov     edi, eax
0x1800ad795  mov     rcx, cs:gDhcpHeap; hHeap
0x1800ad79c  mov     r8, r14; lpMem
0x1800ad79f  xor     edx, edx; dwFlags
0x1800ad7a1  call    cs:__imp_HeapFree
0x1800ad7a8  nop     dword ptr [rax+rax+00h]
0x1800ad7ad  jmp     loc_1800AD666
0x1800ad7b2  mov     edi, 57h ; 'W'
0x1800ad7b7  test    rcx, rcx
0x1800ad7ba  jz      short loc_1800AD7C8
0x1800ad7bc  call    cs:__imp_BCryptDestroyHash
0x1800ad7c3  nop     dword ptr [rax+rax+00h]
0x1800ad7c8  test    rsi, rsi
0x1800ad7cb  jz      short loc_1800AD7E5
0x1800ad7cd  mov     rcx, cs:gDhcpHeap; hHeap
0x1800ad7d4  mov     r8, rsi; lpMem
0x1800ad7d7  xor     edx, edx; dwFlags
0x1800ad7d9  call    cs:__imp_HeapFree
0x1800ad7e0  nop     dword ptr [rax+rax+00h]
0x1800ad7e5  mov     rbx, [rsp+50h+arg_8]
0x1800ad7ed  mov     eax, edi
0x1800ad7ef  add     rsp, 50h
0x1800ad7f3  pop     r15
0x1800ad7f5  pop     r14
0x1800ad7f7  pop     r13
0x1800ad7f9  pop     r12
0x1800ad7fb  pop     rdi
0x1800ad7fc  pop     rsi
0x1800ad7fd  pop     rbp
0x1800ad7fe  retn
```
