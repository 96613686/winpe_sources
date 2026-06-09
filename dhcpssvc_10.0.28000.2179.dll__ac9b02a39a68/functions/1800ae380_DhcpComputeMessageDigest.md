# DhcpComputeMessageDigest

- ea: `0x1800ae380`
- end: `0x1800ae588`
- name: `DhcpComputeMessageDigest`
- size: `520`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800ae180`
- `0x1800ae590`

## callees

- `0x1800ae380`
- `0x1800cda62`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800ae50f`
- `ntdll!RtlNtStatusToDosError` at `0x1800ae50f`
- `bcrypt!BCryptCreateHash` at `0x1800ae4c1`
- `bcrypt!BCryptCreateHash` at `0x1800ae4c1`
- `bcrypt!BCryptHashData` at `0x1800ae4de`
- `bcrypt!BCryptHashData` at `0x1800ae4de`
- `bcrypt!BCryptDestroyHash` at `0x1800ae544`
- `bcrypt!BCryptDestroyHash` at `0x1800ae544`
- `bcrypt!BCryptFinishHash` at `0x1800ae4fd`
- `bcrypt!BCryptFinishHash` at `0x1800ae4fd`
- `bcrypt!BCryptGetProperty` at `0x1800ae46f`
- `bcrypt!BCryptGetProperty` at `0x1800ae46f`
- `KERNEL32!HeapAlloc` at `0x1800ae3d7`
- `KERNEL32!HeapAlloc` at `0x1800ae431`
- `KERNEL32!HeapAlloc` at `0x1800ae491`
- `KERNEL32!HeapAlloc` at `0x1800ae3d7`
- `KERNEL32!HeapAlloc` at `0x1800ae431`
- `KERNEL32!HeapAlloc` at `0x1800ae491`
- `KERNEL32!HeapFree` at `0x1800ae529`
- `KERNEL32!HeapFree` at `0x1800ae561`
- `KERNEL32!HeapFree` at `0x1800ae529`
- `KERNEL32!HeapFree` at `0x1800ae561`

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
  size_t v10; // rbx
  UCHAR *v11; // rsi
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
  v9 = 0;
  v10 = a2;
  v11 = 0;
  phHash = 0;
  pbOutput = 0;
  pcbResult = 0;
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
    memcpy_0(v14, a1, v10);
    memcpy_0(&v15[v10], a3, v8);
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
      v11 = v21;
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
  if ( v11 )
    HeapFree(gDhcpHeap, 0, v11);
  return v9;
}

```

## disassembly

```asm
0x1800ae380  mov     [rsp-38h+arg_8], rbx
0x1800ae385  mov     [rsp-38h+Src], rcx
0x1800ae38a  push    rbp
0x1800ae38b  push    rsi
0x1800ae38c  push    rdi
0x1800ae38d  push    r12
0x1800ae38f  push    r13
0x1800ae391  push    r14
0x1800ae393  push    r15
0x1800ae395  mov     rbp, rsp
0x1800ae398  sub     rsp, 50h
0x1800ae39c  xor     ecx, ecx; hHash
0x1800ae39e  mov     r15d, r9d
0x1800ae3a1  xor     edi, edi
0x1800ae3a3  mov     ebx, edx
0x1800ae3a5  xor     esi, esi
0x1800ae3a7  mov     [rbp+phHash], rcx
0x1800ae3ab  mov     [rbp+pbOutput], ecx
0x1800ae3ae  mov     r12, r8
0x1800ae3b1  mov     [rbp+var_10], ecx
0x1800ae3b4  test    r9d, r9d
0x1800ae3b7  jz      loc_1800AE53A
0x1800ae3bd  test    r8, r8
0x1800ae3c0  jz      loc_1800AE53A
0x1800ae3c6  mov     rcx, cs:gDhcpHeap; hHeap
0x1800ae3cd  lea     r13d, [rbx+r15]
0x1800ae3d1  mov     r8d, r13d; dwBytes
0x1800ae3d4  lea     edx, [rdi+8]; dwFlags
0x1800ae3d7  call    cs:__imp_HeapAlloc
0x1800ae3de  nop     dword ptr [rax+rax+00h]
0x1800ae3e3  mov     r14, rax
0x1800ae3e6  test    rax, rax
0x1800ae3e9  jnz     short loc_1800AE3F7
0x1800ae3eb  lea     edi, [rsi+8]
0x1800ae3ee  mov     rcx, [rbp+phHash]
0x1800ae3f2  jmp     loc_1800AE53F
0x1800ae3f7  mov     rdx, [rbp+Src]; Src
0x1800ae3fb  mov     r8, rbx; Size
0x1800ae3fe  mov     rcx, r14; void *
0x1800ae401  call    memcpy_0
0x1800ae406  mov     r8, r15; Size
0x1800ae409  lea     rcx, [rbx+r14]; void *
0x1800ae40d  mov     rdx, r12; Src
0x1800ae410  call    memcpy_0
0x1800ae415  mov     rbx, [rbp+arg_30]
0x1800ae419  mov     r15d, 8
0x1800ae41f  movzx   r8d, [rbp+arg_28]; dwBytes
0x1800ae424  mov     edx, r15d; dwFlags
0x1800ae427  mov     rcx, cs:gDhcpHeap; hHeap
0x1800ae42e  mov     [rbx], rsi
0x1800ae431  call    cs:__imp_HeapAlloc
0x1800ae438  nop     dword ptr [rax+rax+00h]
0x1800ae43d  mov     [rbx], rax
0x1800ae440  test    rax, rax
0x1800ae443  jnz     short loc_1800AE44D
0x1800ae445  mov     edi, r15d
0x1800ae448  jmp     loc_1800AE51D
0x1800ae44d  mov     rcx, [rbp+hObject]; hObject
0x1800ae451  lea     rax, [rbp+var_10]
0x1800ae455  mov     [rsp+50h+dwFlags], esi; dwFlags
0x1800ae459  lea     r8, [rbp+pbOutput]; pbOutput
0x1800ae45d  mov     r9d, 4; cbOutput
0x1800ae463  mov     [rsp+50h+pcbResult], rax; pcbResult
0x1800ae468  lea     rdx, aObjectlength; "ObjectLength"
0x1800ae46f  call    cs:__imp_BCryptGetProperty
0x1800ae476  nop     dword ptr [rax+rax+00h]
0x1800ae47b  test    eax, eax
0x1800ae47d  jnz     loc_1800AE50D
0x1800ae483  mov     r8d, [rbp+pbOutput]; dwBytes
0x1800ae487  mov     edx, r15d; dwFlags
0x1800ae48a  mov     rcx, cs:gDhcpHeap; hHeap
0x1800ae491  call    cs:__imp_HeapAlloc
0x1800ae498  nop     dword ptr [rax+rax+00h]
0x1800ae49d  mov     rsi, rax
0x1800ae4a0  test    rax, rax
0x1800ae4a3  jz      short loc_1800AE445
0x1800ae4a5  mov     r9d, [rbp+pbOutput]; cbHashObject
0x1800ae4a9  lea     rdx, [rbp+phHash]; phHash
0x1800ae4ad  mov     rcx, [rbp+hObject]; hAlgorithm
0x1800ae4b1  mov     r8, rax; pbHashObject
0x1800ae4b4  mov     [rsp+50h+var_20], edi; dwFlags
0x1800ae4b8  mov     [rsp+50h+dwFlags], edi; cbSecret
0x1800ae4bc  mov     [rsp+50h+pcbResult], rdi; pbSecret
0x1800ae4c1  call    cs:__imp_BCryptCreateHash
0x1800ae4c8  nop     dword ptr [rax+rax+00h]
0x1800ae4cd  test    eax, eax
0x1800ae4cf  jnz     short loc_1800AE50D
0x1800ae4d1  mov     rcx, [rbp+phHash]; hHash
0x1800ae4d5  xor     r9d, r9d; dwFlags
0x1800ae4d8  mov     r8d, r13d; cbInput
0x1800ae4db  mov     rdx, r14; pbInput
0x1800ae4de  call    cs:__imp_BCryptHashData
0x1800ae4e5  nop     dword ptr [rax+rax+00h]
0x1800ae4ea  test    eax, eax
0x1800ae4ec  jnz     short loc_1800AE50D
0x1800ae4ee  movzx   r8d, [rbp+arg_28]; cbOutput
0x1800ae4f3  xor     r9d, r9d; dwFlags
0x1800ae4f6  mov     rdx, [rbx]; pbOutput
0x1800ae4f9  mov     rcx, [rbp+phHash]; hHash
0x1800ae4fd  call    cs:__imp_BCryptFinishHash
0x1800ae504  nop     dword ptr [rax+rax+00h]
0x1800ae509  test    eax, eax
0x1800ae50b  jz      short loc_1800AE51D
0x1800ae50d  mov     ecx, eax; Status
0x1800ae50f  call    cs:__imp_RtlNtStatusToDosError
0x1800ae516  nop     dword ptr [rax+rax+00h]
0x1800ae51b  mov     edi, eax
0x1800ae51d  mov     rcx, cs:gDhcpHeap; hHeap
0x1800ae524  mov     r8, r14; lpMem
0x1800ae527  xor     edx, edx; dwFlags
0x1800ae529  call    cs:__imp_HeapFree
0x1800ae530  nop     dword ptr [rax+rax+00h]
0x1800ae535  jmp     loc_1800AE3EE
0x1800ae53a  mov     edi, 57h ; 'W'
0x1800ae53f  test    rcx, rcx
0x1800ae542  jz      short loc_1800AE550
0x1800ae544  call    cs:__imp_BCryptDestroyHash
0x1800ae54b  nop     dword ptr [rax+rax+00h]
0x1800ae550  test    rsi, rsi
0x1800ae553  jz      short loc_1800AE56D
0x1800ae555  mov     rcx, cs:gDhcpHeap; hHeap
0x1800ae55c  mov     r8, rsi; lpMem
0x1800ae55f  xor     edx, edx; dwFlags
0x1800ae561  call    cs:__imp_HeapFree
0x1800ae568  nop     dword ptr [rax+rax+00h]
0x1800ae56d  mov     rbx, [rsp+50h+arg_8]
0x1800ae575  mov     eax, edi
0x1800ae577  add     rsp, 50h
0x1800ae57b  pop     r15
0x1800ae57d  pop     r14
0x1800ae57f  pop     r13
0x1800ae581  pop     r12
0x1800ae583  pop     rdi
0x1800ae584  pop     rsi
0x1800ae585  pop     rbp
0x1800ae586  retn
```
