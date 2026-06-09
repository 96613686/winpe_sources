# ICM_CreateHash(_CRYPT_OID_INFO const *)

- ea: `0x180048990`
- end: `0x180048bf1`
- name: `?ICM_CreateHash@@YAPEAU_ICM_HASH_INFO@@PEBU_CRYPT_OID_INFO@@@Z`
- size: `609`
- prototype: `struct _ICM_HASH_INFO *__fastcall(const struct _CRYPT_OID_INFO *)`
- caller_count: `10`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800374b0`
- `0x18003794c`
- `0x18004c484`
- `0x18004cf84`
- `0x180083e08`
- `0x1800840bc`
- `0x1800b88d0`
- `0x180103318`
- `0x180107704`
- `0x180108804`

## callees

- `0x18002aa48`
- `0x18002bbd4`
- `0x180046e10`
- `0x180048990`
- `0x18004a368`
- `0x180081758`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180048bd2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180118074`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180048bd2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180118074`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048a6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048b52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048a6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048b52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048a15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048b7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048a15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048b7d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800489d3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800489fd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180048a41`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800489d3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800489fd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180048a41`
- `bcrypt!BCryptCreateHash` at `0x180048afe`
- `bcrypt!BCryptCreateHash` at `0x180048afe`

## pseudocode

```c
struct _ICM_HASH_INFO *__fastcall ICM_CreateHash(const struct _CRYPT_OID_INFO *a1)
{
  void *v1; // rdi
  const WCHAR *v3; // r14
  WCHAR *v4; // rbp
  WCHAR *CNGAlgorithmProviderContext; // rbx
  unsigned int v6; // eax
  unsigned int v7; // ecx
  __int64 v8; // rax
  NTSTATUS Hash; // eax
  HLOCAL v11; // rax
  DWORD v12; // ecx

  v1 = 0;
  if ( a1->dwValue == -2 )
  {
    CNGAlgorithmProviderContext = 0;
    v12 = 50;
LABEL_28:
    SetLastError(v12);
    goto LABEL_22;
  }
  v3 = *(const WCHAR **)&a1[1].cbSize;
  if ( CompareStringW(0x409u, 1u, v3, -1, L"ECDSA", -1) == 2 || CompareStringW(0x409u, 1u, v3, -1, L"ECDH", -1) == 2 )
  {
    CNGAlgorithmProviderContext = (WCHAR *)CreateCNGAlgorithmProviderContext(2, v3, 0);
    goto LABEL_12;
  }
  v4 = 0;
  EnterCriticalSection(&stru_18015CDD8);
  for ( CNGAlgorithmProviderContext = (WCHAR *)qword_18015CE10;
        CNGAlgorithmProviderContext
     && (CompareStringW(0x409u, 1u, v3, -1, *((PCNZWCH *)CNGAlgorithmProviderContext + 2), -1) != 2
      || *((_DWORD *)CNGAlgorithmProviderContext + 6));
        CNGAlgorithmProviderContext = *(WCHAR **)CNGAlgorithmProviderContext )
  {
    ;
  }
  if ( CNGAlgorithmProviderContext )
    goto LABEL_9;
  LeaveCriticalSection(&stru_18015CDD8);
  v4 = (WCHAR *)CreateCNGAlgorithmProviderContext(2, v3, 0);
  if ( v4 )
  {
    EnterCriticalSection(&stru_18015CDD8);
    CNGAlgorithmProviderContext = (WCHAR *)FindCNGAlgorithmProviderContext(2, v3, 0);
    if ( !CNGAlgorithmProviderContext )
    {
      v11 = qword_18015CE10;
      CNGAlgorithmProviderContext = v4;
      v4 = 0;
      qword_18015CE10 = CNGAlgorithmProviderContext;
      *(_QWORD *)CNGAlgorithmProviderContext = v11;
    }
LABEL_9:
    _InterlockedIncrement((volatile signed __int32 *)CNGAlgorithmProviderContext + 2);
    LeaveCriticalSection(&stru_18015CDD8);
  }
  if ( v4 )
    I_CryptReleaseCNGAlgorithmProvider(v4);
LABEL_12:
  if ( !CNGAlgorithmProviderContext )
  {
LABEL_22:
    I_CryptReleaseCNGAlgorithmProvider(CNGAlgorithmProviderContext);
    return (struct _ICM_HASH_INFO *)v1;
  }
  v6 = *((_DWORD *)CNGAlgorithmProviderContext + 10);
  if ( v6 > 0xFFFF || (v7 = *((_DWORD *)CNGAlgorithmProviderContext + 11), v7 > 0xFFFF) )
  {
    v12 = 534;
    goto LABEL_28;
  }
  v8 = PkiZeroAlloc(v6 + 72 + v7);
  v1 = (void *)v8;
  if ( !v8 )
    goto LABEL_22;
  *(_QWORD *)v8 = CNGAlgorithmProviderContext;
  *(_QWORD *)(v8 + 48) = v8 + 72;
  *(_QWORD *)(v8 + 8) = a1;
  *(_DWORD *)(v8 + 24) = 1;
  *(_QWORD *)(v8 + 56) = v8 + *((unsigned int *)CNGAlgorithmProviderContext + 10) + 72LL;
  Hash = BCryptCreateHash(
           *((BCRYPT_ALG_HANDLE *)CNGAlgorithmProviderContext + 4),
           (BCRYPT_HASH_HANDLE *)(v8 + 16),
           (PUCHAR)(v8 + 72),
           *((_DWORD *)CNGAlgorithmProviderContext + 10),
           0,
           0,
           0);
  if ( Hash )
  {
    SetLastError(Hash);
    ICM_FreeHash(v1);
    return 0;
  }
  return (struct _ICM_HASH_INFO *)v1;
}

```

## disassembly

```asm
0x180048990  push    rbx
0x180048992  push    rbp
0x180048993  push    rsi
0x180048994  push    rdi
0x180048995  push    r14
0x180048997  push    r15
0x180048999  sub     rsp, 48h
0x18004899d  xor     edi, edi
0x18004899f  mov     r15, rcx
0x1800489a2  cmp     dword ptr [rcx+1Ch], 0FFFFFFFEh
0x1800489a6  jz      loc_180048BC6
0x1800489ac  mov     r14, [rcx+30h]
0x1800489b0  lea     rax, aEcdsa; "ECDSA"
0x1800489b7  or      esi, 0FFFFFFFFh
0x1800489ba  lea     edx, [rdi+1]; dwCmpFlags
0x1800489bd  mov     ebx, 409h
0x1800489c2  mov     [rsp+78h+cchCount2], esi; cchCount2
0x1800489c6  mov     r9d, esi; cchCount1
0x1800489c9  mov     [rsp+78h+lpString2], rax; lpString2
0x1800489ce  mov     r8, r14; lpString1
0x1800489d1  mov     ecx, ebx; Locale
0x1800489d3  call    cs:__imp_CompareStringW
0x1800489d9  cmp     eax, 2
0x1800489dc  jz      loc_180048B2A
0x1800489e2  lea     rax, aEcdh; "ECDH"
0x1800489e9  mov     [rsp+78h+cchCount2], esi; cchCount2
0x1800489ed  mov     r9d, esi; cchCount1
0x1800489f0  mov     [rsp+78h+lpString2], rax; lpString2
0x1800489f5  mov     r8, r14; lpString1
0x1800489f8  lea     edx, [rdi+1]; dwCmpFlags
0x1800489fb  mov     ecx, ebx; Locale
0x1800489fd  call    cs:__imp_CompareStringW
0x180048a03  cmp     eax, 2
0x180048a06  jz      loc_180048B2A
0x180048a0c  xor     ebp, ebp
0x180048a0e  lea     rcx, stru_18015CDD8; lpCriticalSection
0x180048a15  call    cs:__imp_EnterCriticalSection
0x180048a1b  mov     rbx, cs:qword_18015CE10
0x180048a22  jmp     short loc_180048A53
0x180048a24  mov     rax, [rbx+10h]
0x180048a28  mov     r9d, esi; cchCount1
0x180048a2b  mov     [rsp+78h+cchCount2], esi; cchCount2
0x180048a2f  mov     r8, r14; lpString1
0x180048a32  mov     edx, 1; dwCmpFlags
0x180048a37  mov     [rsp+78h+lpString2], rax; lpString2
0x180048a3c  mov     ecx, 409h; Locale
0x180048a41  call    cs:__imp_CompareStringW
0x180048a47  cmp     eax, 2
0x180048a4a  jz      loc_180048B1C
0x180048a50  mov     rbx, [rbx]
0x180048a53  test    rbx, rbx
0x180048a56  jnz     short loc_180048A24
0x180048a58  test    rbx, rbx
0x180048a5b  jz      loc_180048B4B
0x180048a61  lock inc dword ptr [rbx+8]
0x180048a65  lea     rcx, stru_18015CDD8; lpCriticalSection
0x180048a6c  call    cs:__imp_LeaveCriticalSection
0x180048a72  test    rbp, rbp
0x180048a75  jnz     loc_180048BB9
0x180048a7b  test    rbx, rbx
0x180048a7e  jz      loc_180048B41
0x180048a84  mov     eax, [rbx+28h]
0x180048a87  mov     edx, 0FFFFh
0x180048a8c  cmp     eax, edx
0x180048a8e  ja      loc_180048BE7
0x180048a94  mov     ecx, [rbx+2Ch]
0x180048a97  cmp     ecx, edx
0x180048a99  ja      loc_180048BE7
0x180048a9f  add     eax, 48h ; 'H'
0x180048aa2  add     ecx, eax; uBytes
0x180048aa4  call    PkiZeroAlloc
0x180048aa9  mov     rdi, rax
0x180048aac  test    rax, rax
0x180048aaf  jz      loc_180048B41
0x180048ab5  mov     [rax], rbx
0x180048ab8  lea     r8, [rax+48h]; pbHashObject
0x180048abc  mov     [rax+30h], r8
0x180048ac0  lea     rdx, [rax+10h]; phHash
0x180048ac4  mov     [rax+8], r15
0x180048ac8  mov     dword ptr [rax+18h], 1
0x180048acf  mov     ecx, [rbx+28h]
0x180048ad2  add     rcx, 48h ; 'H'
0x180048ad6  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180048ade  add     rcx, rax
0x180048ae1  mov     [rsp+78h+cchCount2], 0; cbSecret
0x180048ae9  mov     [rax+38h], rcx
0x180048aed  mov     r9d, [rbx+28h]; cbHashObject
0x180048af1  mov     rcx, [rbx+20h]; hAlgorithm
0x180048af5  mov     [rsp+78h+lpString2], 0; pbSecret
0x180048afe  call    cs:__imp_BCryptCreateHash
0x180048b04  test    eax, eax
0x180048b06  jnz     loc_180048BD0
0x180048b0c  mov     rax, rdi
0x180048b0f  add     rsp, 48h
0x180048b13  pop     r15
0x180048b15  pop     r14
0x180048b17  pop     rdi
0x180048b18  pop     rsi
0x180048b19  pop     rbp
0x180048b1a  pop     rbx
0x180048b1b  retn
0x180048b1c  cmp     [rbx+18h], edi
0x180048b1f  jnz     loc_180048A50
0x180048b25  jmp     loc_180048A58
0x180048b2a  xor     r8d, r8d
0x180048b2d  mov     rdx, r14
0x180048b30  lea     ecx, [r8+2]
0x180048b34  call    CreateCNGAlgorithmProviderContext
0x180048b39  mov     rbx, rax
0x180048b3c  jmp     loc_180048A7B
0x180048b41  mov     rcx, rbx; hMem
0x180048b44  call    I_CryptReleaseCNGAlgorithmProvider
0x180048b49  jmp     short loc_180048B0C
0x180048b4b  lea     rcx, stru_18015CDD8; lpCriticalSection
0x180048b52  call    cs:__imp_LeaveCriticalSection
0x180048b58  xor     r8d, r8d
0x180048b5b  mov     rdx, r14
0x180048b5e  lea     ecx, [r8+2]
0x180048b62  call    CreateCNGAlgorithmProviderContext
0x180048b67  mov     rsi, rax
0x180048b6a  mov     rbp, rax
0x180048b6d  test    rax, rax
0x180048b70  jz      loc_180048A72
0x180048b76  lea     rcx, stru_18015CDD8; lpCriticalSection
0x180048b7d  call    cs:__imp_EnterCriticalSection
0x180048b83  xor     r8d, r8d
0x180048b86  mov     rdx, r14
0x180048b89  lea     ecx, [r8+2]
0x180048b8d  call    FindCNGAlgorithmProviderContext
0x180048b92  mov     rbx, rax
0x180048b95  test    rax, rax
0x180048b98  jnz     loc_180048A61
0x180048b9e  mov     rax, cs:qword_18015CE10
0x180048ba5  mov     rbx, rbp
0x180048ba8  xor     ebp, ebp
0x180048baa  mov     cs:qword_18015CE10, rbx
0x180048bb1  mov     [rbx], rax
0x180048bb4  jmp     loc_180048A61
0x180048bb9  mov     rcx, rbp; hMem
0x180048bbc  call    I_CryptReleaseCNGAlgorithmProvider
0x180048bc1  jmp     loc_180048A7B
0x180048bc6  xor     ebx, ebx
0x180048bc8  lea     ecx, [rbx+32h]; dwErrCode
0x180048bcb  jmp     loc_180118074
0x180048bd0  mov     ecx, eax; dwErrCode
0x180048bd2  call    cs:__imp_SetLastError
0x180048bd8  mov     rcx, rdi; hMem
0x180048bdb  call    ?ICM_FreeHash@@YAXPEAU_ICM_HASH_INFO@@@Z; ICM_FreeHash(_ICM_HASH_INFO *)
0x180048be0  xor     edi, edi
0x180048be2  jmp     loc_180048B0C
0x180048be7  mov     ecx, 216h
0x180048bec  jmp     loc_180118074
0x180118074  call    cs:__imp_SetLastError
0x18011807a  nop
0x18011807b  jmp     loc_180048B41
```
