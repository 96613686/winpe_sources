# SmbAddSmbSecuritySignature

- ea: `0x14003ec3c`
- end: `0x14003edcd`
- name: `SmbAddSmbSecuritySignature`
- size: `401`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14003f0c8`
- `0x14003f41c`
- `0x14004e5b0`

## callees

- `0x14000fd40`
- `0x1400125dc`
- `0x140016560`
- `0x14003ec3c`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003ec97`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003ed21`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003ec97`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003ed21`
- `ntoskrnl!DbgPrint` at `0x14003ed8e`
- `ntoskrnl!DbgPrint` at `0x14003ed8e`
- `ksecdd!BCryptDestroyHash` at `0x14003eda3`
- `ksecdd!BCryptDestroyHash` at `0x14003eda3`
- `ksecdd!BCryptDuplicateHash` at `0x14003ece3`
- `ksecdd!BCryptDuplicateHash` at `0x14003ece3`

## pseudocode

```c
NTSTATUS __fastcall SmbAddSmbSecuritySignature(__int64 a1, __int64 *a2, _DWORD *a3, unsigned int a4)
{
  bool v4; // zf
  struct _MDL *v7; // rbx
  char *v9; // rbp
  void *v10; // rcx
  NTSTATUS result; // eax
  int v12; // edi
  PVOID MappedSystemVa; // rax
  __int64 ByteCount; // r8
  ULONG v15; // eax
  BCRYPT_HASH_HANDLE phNewHash[2]; // [rsp+30h] [rbp-58h] BYREF
  __int128 v17; // [rsp+40h] [rbp-48h]

  v4 = (*((_BYTE *)a2 + 10) & 5) == 0;
  *(_OWORD *)phNewHash = 0;
  v17 = 0;
  v7 = (struct _MDL *)a2;
  if ( v4 )
    v9 = (char *)MmMapLockedPagesSpecifyCache((PMDL)a2, 0, MmCached, 0, 0, 0x40000000u);
  else
    v9 = (char *)a2[3];
  if ( !v9 )
    return -1073741670;
  *(_DWORD *)(v9 + 14) = *(_DWORD *)(a1 + 236);
  *a3 = *(_DWORD *)(a1 + 236) + 1;
  *(_DWORD *)(v9 + 18) = 0;
  v10 = *(void **)(a1 + 200);
  phNewHash[1] = 0;
  result = BCryptDuplicateHash(v10, phNewHash, 0, 0, 0);
  if ( result >= 0 )
  {
    v12 = 0;
    while ( 1 )
    {
      if ( (v7->MdlFlags & 5) != 0 )
        MappedSystemVa = v7->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(v7, 0, MmCached, 0, 0, 0x40000000u);
      if ( !MappedSystemVa )
      {
        BCryptDestroyHash(phNewHash[0]);
        return -1073741670;
      }
      ByteCount = v7->ByteCount;
      if ( (unsigned int)ByteCount >= a4 )
        break;
      CngRsa32Compat_MD5Update(phNewHash, MappedSystemVa, ByteCount);
      v15 = v7->ByteCount;
      v12 += v15;
      v7 = v7->Next;
      if ( !v7 )
        goto LABEL_15;
      a4 -= v15;
    }
    CngRsa32Compat_MD5Update(phNewHash, MappedSystemVa, a4);
    v12 += a4;
LABEL_15:
    CngRsa32Compat_MD5Final(phNewHash);
    v4 = DumpSecuritySignature == 0;
    *(_QWORD *)(v9 + 14) = v17;
    if ( !v4 )
      DbgPrint("Add Signature: index %u length %u\n", *a3 - 1, v12);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14003ec3c  push    rbx
0x14003ec3e  push    rbp
0x14003ec3f  push    rsi
0x14003ec40  push    rdi
0x14003ec41  push    r14
0x14003ec43  sub     rsp, 60h
0x14003ec47  mov     rax, cs:__security_cookie
0x14003ec4e  xor     rax, rsp
0x14003ec51  mov     [rsp+88h+var_38], rax
0x14003ec56  test    byte ptr [rdx+0Ah], 5
0x14003ec5a  xorps   xmm0, xmm0
0x14003ec5d  movups  xmmword ptr [rsp+88h+phNewHash], xmm0
0x14003ec62  mov     esi, r9d
0x14003ec65  mov     r14, r8
0x14003ec68  movups  [rsp+88h+var_48], xmm0
0x14003ec6d  mov     rbx, rdx
0x14003ec70  mov     rdi, rcx
0x14003ec73  jz      short loc_14003EC7B
0x14003ec75  mov     rbp, [rdx+18h]
0x14003ec79  jmp     short loc_14003ECA6
0x14003ec7b  xor     r9d, r9d; RequestedAddress
0x14003ec7e  mov     [rsp+88h+Priority], 40000000h; Priority
0x14003ec86  xor     edx, edx; AccessMode
0x14003ec88  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14003ec90  mov     rcx, rbx; MemoryDescriptorList
0x14003ec93  lea     r8d, [r9+1]; CacheType
0x14003ec97  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14003ec9e  nop     dword ptr [rax+rax+00h]
0x14003eca3  mov     rbp, rax
0x14003eca6  test    rbp, rbp
0x14003eca9  jz      loc_14003EDAF
0x14003ecaf  mov     eax, [rdi+0ECh]
0x14003ecb5  lea     rdx, [rsp+88h+phNewHash]; phNewHash
0x14003ecba  mov     [rbp+0Eh], eax
0x14003ecbd  xor     r9d, r9d; cbHashObject
0x14003ecc0  mov     eax, [rdi+0ECh]
0x14003ecc6  xor     r8d, r8d; pbHashObject
0x14003ecc9  inc     eax
0x14003eccb  mov     [r14], eax
0x14003ecce  xor     eax, eax
0x14003ecd0  mov     [rbp+12h], eax
0x14003ecd3  mov     rcx, [rdi+0C8h]; hHash
0x14003ecda  mov     [rsp+88h+phNewHash+8], rax
0x14003ecdf  mov     [rsp+88h+BugCheckOnFailure], eax; dwFlags
0x14003ece3  call    cs:__imp_BCryptDuplicateHash
0x14003ecea  nop     dword ptr [rax+rax+00h]
0x14003ecef  test    eax, eax
0x14003ecf1  js      loc_14003EDB4
0x14003ecf7  xor     edi, edi
0x14003ecf9  test    byte ptr [rbx+0Ah], 5
0x14003ecfd  jz      short loc_14003ED05
0x14003ecff  mov     rax, [rbx+18h]
0x14003ed03  jmp     short loc_14003ED2D
0x14003ed05  xor     r9d, r9d; RequestedAddress
0x14003ed08  mov     [rsp+88h+Priority], 40000000h; Priority
0x14003ed10  xor     edx, edx; AccessMode
0x14003ed12  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14003ed1a  mov     rcx, rbx; MemoryDescriptorList
0x14003ed1d  lea     r8d, [r9+1]; CacheType
0x14003ed21  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14003ed28  nop     dword ptr [rax+rax+00h]
0x14003ed2d  test    rax, rax
0x14003ed30  jz      short loc_14003ED9E
0x14003ed32  mov     r8d, [rbx+28h]
0x14003ed36  lea     rcx, [rsp+88h+phNewHash]
0x14003ed3b  mov     rdx, rax
0x14003ed3e  cmp     r8d, esi
0x14003ed41  jnb     short loc_14003ED59
0x14003ed43  call    CngRsa32Compat_MD5Update
0x14003ed48  mov     eax, [rbx+28h]
0x14003ed4b  add     edi, eax
0x14003ed4d  mov     rbx, [rbx]
0x14003ed50  test    rbx, rbx
0x14003ed53  jz      short loc_14003ED63
0x14003ed55  sub     esi, eax
0x14003ed57  jmp     short loc_14003ECF9
0x14003ed59  mov     r8d, esi
0x14003ed5c  call    CngRsa32Compat_MD5Update
0x14003ed61  add     edi, esi
0x14003ed63  lea     rcx, [rsp+88h+phNewHash]
0x14003ed68  call    CngRsa32Compat_MD5Final
0x14003ed6d  cmp     cs:DumpSecuritySignature, 0
0x14003ed74  mov     rax, qword ptr [rsp+88h+var_48]
0x14003ed79  mov     [rbp+0Eh], rax
0x14003ed7d  jz      short loc_14003ED9A
0x14003ed7f  mov     edx, [r14]
0x14003ed82  lea     rcx, aAddSignatureIn; "Add Signature: index %u length %u\n"
0x14003ed89  dec     edx
0x14003ed8b  mov     r8d, edi
0x14003ed8e  call    cs:__imp_DbgPrint
0x14003ed95  nop     dword ptr [rax+rax+00h]
0x14003ed9a  xor     eax, eax
0x14003ed9c  jmp     short loc_14003EDB4
0x14003ed9e  mov     rcx, [rsp+88h+phNewHash]; hHash
0x14003eda3  call    cs:__imp_BCryptDestroyHash
0x14003edaa  nop     dword ptr [rax+rax+00h]
0x14003edaf  mov     eax, 0C000009Ah
0x14003edb4  mov     rcx, [rsp+88h+var_38]
0x14003edb9  xor     rcx, rsp; StackCookie
0x14003edbc  call    __security_check_cookie
0x14003edc1  add     rsp, 60h
0x14003edc5  pop     r14
0x14003edc7  pop     rdi
0x14003edc8  pop     rsi
0x14003edc9  pop     rbp
0x14003edca  pop     rbx
0x14003edcb  retn
```
