# CMSVidWebDVDAdm::EncryptPassword(ushort *,uchar * *,ulong *,ulong *,int)

- ea: `0x1800b3580`
- end: `0x1800b37a7`
- name: `?EncryptPassword@CMSVidWebDVDAdm@@IEAAJPEAGPEAPEAEPEAK2H@Z`
- size: `551`
- prototype: `int(CMSVidWebDVDAdm *__hidden this, unsigned __int16 *, unsigned __int8 **, unsigned int *, unsigned int *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800b3110`
- `0x1800b3270`

## callees

- `0x180004740`
- `0x180004b48`
- `0x1800054bc`
- `0x1800b3580`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800b35d1`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800b35d1`
- `ADVAPI32!CryptAcquireContextW` at `0x1800b3620`
- `ADVAPI32!CryptAcquireContextW` at `0x1800b3620`
- `ADVAPI32!CryptGenRandom` at `0x1800b3641`
- `ADVAPI32!CryptGenRandom` at `0x1800b3641`
- `ADVAPI32!CryptReleaseContext` at `0x1800b36c4`
- `ADVAPI32!CryptReleaseContext` at `0x1800b3754`
- `ADVAPI32!CryptReleaseContext` at `0x1800b3784`
- `ADVAPI32!CryptReleaseContext` at `0x1800b36c4`
- `ADVAPI32!CryptReleaseContext` at `0x1800b3754`
- `ADVAPI32!CryptReleaseContext` at `0x1800b3784`
- `ADVAPI32!CryptCreateHash` at `0x1800b366f`
- `ADVAPI32!CryptCreateHash` at `0x1800b366f`
- `ADVAPI32!CryptHashData` at `0x1800b3687`
- `ADVAPI32!CryptHashData` at `0x1800b36a0`
- `ADVAPI32!CryptHashData` at `0x1800b3687`
- `ADVAPI32!CryptHashData` at `0x1800b36a0`
- `ADVAPI32!CryptDestroyHash` at `0x1800b36b3`
- `ADVAPI32!CryptDestroyHash` at `0x1800b3743`
- `ADVAPI32!CryptDestroyHash` at `0x1800b3773`
- `ADVAPI32!CryptDestroyHash` at `0x1800b36b3`
- `ADVAPI32!CryptDestroyHash` at `0x1800b3743`
- `ADVAPI32!CryptDestroyHash` at `0x1800b3773`
- `ADVAPI32!CryptGetHashParam` at `0x1800b36e9`
- `ADVAPI32!CryptGetHashParam` at `0x1800b3730`
- `ADVAPI32!CryptGetHashParam` at `0x1800b36e9`
- `ADVAPI32!CryptGetHashParam` at `0x1800b3730`

## pseudocode

```c
__int64 __fastcall CMSVidWebDVDAdm::EncryptPassword(
        CMSVidWebDVDAdm *this,
        unsigned __int16 *a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        unsigned int *a5,
        int a6)
{
  unsigned int *v9; // rbx
  unsigned int v10; // r14d
  BOOL v12; // eax
  HCRYPTHASH v13; // rcx
  BOOL v14; // eax
  unsigned __int8 *v15; // rax
  size_t v16; // r8
  BYTE *v17; // rbx
  unsigned __int64 v18; // rdx
  HCRYPTHASH phHash; // [rsp+30h] [rbp-10h] BYREF
  HCRYPTPROV phProv; // [rsp+38h] [rbp-8h] BYREF
  CMSVidWebDVDAdm *pdwDataLen; // [rsp+70h] [rbp+30h] BYREF
  unsigned int pbBuffer; // [rsp+78h] [rbp+38h] BYREF

  pdwDataLen = this;
  if ( !a2 )
    return 2147500035LL;
  if ( !a3 )
    return 2147500035LL;
  v9 = a5;
  if ( !a5 || !a4 )
    return 2147500035LL;
  v10 = wcsnlen(a2, 0x100u);
  if ( v10 >= 0x100 )
    return 2147942487LL;
  phProv = 0;
  phHash = 0;
  pbBuffer = 0;
  LODWORD(pdwDataLen) = 0;
  if ( !CryptAcquireContextW(&phProv, 0, 0, 0x18u, 0xF0000000) )
    return 2147549183LL;
  if ( a6 )
  {
    if ( !CryptGenRandom(phProv, 4u, (BYTE *)&pbBuffer) )
      goto LABEL_17;
    *v9 = pbBuffer;
  }
  else
  {
    pbBuffer = *v9;
  }
  if ( !CryptCreateHash(phProv, 0x800Cu, 0, 0, &phHash) )
  {
LABEL_17:
    if ( phProv )
      CryptReleaseContext(phProv, 0);
    return 2147549183LL;
  }
  v12 = CryptHashData(phHash, (const BYTE *)a2, 2 * v10, 0);
  v13 = phHash;
  if ( !v12 || (v14 = CryptHashData(phHash, (const BYTE *)&pbBuffer, 4u, 0), v13 = phHash, !v14) )
  {
LABEL_15:
    if ( v13 )
      CryptDestroyHash(v13);
    goto LABEL_17;
  }
  if ( !CryptGetHashParam(phHash, 2u, 0, (DWORD *)&pdwDataLen, 0) )
  {
    v13 = phHash;
    goto LABEL_15;
  }
  v15 = (unsigned __int8 *)operator new[]((unsigned int)pdwDataLen);
  v16 = (unsigned int)pdwDataLen;
  *a3 = v15;
  v17 = v15;
  memset_0(v15, 0, v16);
  *a4 = (unsigned int)pdwDataLen;
  if ( !CryptGetHashParam(phHash, 2u, v17, (DWORD *)&pdwDataLen, 0) )
  {
    if ( phHash )
      CryptDestroyHash(phHash);
    if ( phProv )
      CryptReleaseContext(phProv, 0);
    operator delete(*a3, v18);
    *a3 = 0;
    return 2147549183LL;
  }
  if ( phHash )
    CryptDestroyHash(phHash);
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  return 0;
}

```

## disassembly

```asm
0x1800b3580  mov     [rsp-28h+arg_10], rbx
0x1800b3585  mov     [rsp-28h+pdwDataLen], rcx
0x1800b358a  push    rbp
0x1800b358b  push    rsi
0x1800b358c  push    rdi
0x1800b358d  push    r14
0x1800b358f  push    r15
0x1800b3591  mov     rbp, rsp
0x1800b3594  sub     rsp, 40h
0x1800b3598  mov     r15, r9
0x1800b359b  mov     rdi, r8
0x1800b359e  mov     rsi, rdx
0x1800b35a1  test    rdx, rdx
0x1800b35a4  jz      loc_1800B378E
0x1800b35aa  test    r8, r8
0x1800b35ad  jz      loc_1800B378E
0x1800b35b3  mov     rbx, [rbp+arg_20]
0x1800b35b7  test    rbx, rbx
0x1800b35ba  jz      loc_1800B378E
0x1800b35c0  test    r9, r9
0x1800b35c3  jz      loc_1800B378E
0x1800b35c9  mov     edx, 100h; MaxCount
0x1800b35ce  mov     rcx, rsi; Source
0x1800b35d1  call    cs:__imp_wcsnlen
0x1800b35d7  mov     r14, rax
0x1800b35da  cmp     eax, 100h
0x1800b35df  jb      short loc_1800B35EB
0x1800b35e1  mov     eax, 80070057h
0x1800b35e6  jmp     loc_1800B3793
0x1800b35eb  mov     r9d, 18h; dwProvType
0x1800b35f1  mov     [rbp+phProv], 0
0x1800b35f9  xor     r8d, r8d; szProvider
0x1800b35fc  mov     [rbp+phHash], 0
0x1800b3604  xor     edx, edx; szContainer
0x1800b3606  mov     [rbp+pbBuffer], 0
0x1800b360d  lea     rcx, [rbp+phProv]; phProv
0x1800b3611  mov     dword ptr [rbp+pdwDataLen], 0
0x1800b3618  mov     [rsp+40h+dwFlags], 0F0000000h; dwFlags
0x1800b3620  call    cs:__imp_CryptAcquireContextW
0x1800b3626  test    eax, eax
0x1800b3628  jz      loc_1800B36CA
0x1800b362e  cmp     [rbp+arg_28], 0
0x1800b3632  jz      short loc_1800B3652
0x1800b3634  mov     rcx, [rbp+phProv]; hProv
0x1800b3638  lea     r8, [rbp+pbBuffer]; pbBuffer
0x1800b363c  mov     edx, 4; dwLen
0x1800b3641  call    cs:__imp_CryptGenRandom
0x1800b3647  test    eax, eax
0x1800b3649  jz      short loc_1800B36B9
0x1800b364b  mov     eax, [rbp+pbBuffer]
0x1800b364e  mov     [rbx], eax
0x1800b3650  jmp     short loc_1800B3657
0x1800b3652  mov     eax, [rbx]
0x1800b3654  mov     [rbp+pbBuffer], eax
0x1800b3657  mov     rcx, [rbp+phProv]; hProv
0x1800b365b  lea     rax, [rbp+phHash]
0x1800b365f  xor     r9d, r9d; dwFlags
0x1800b3662  mov     qword ptr [rsp+40h+dwFlags], rax; phHash
0x1800b3667  xor     r8d, r8d; hKey
0x1800b366a  mov     edx, 800Ch; Algid
0x1800b366f  call    cs:__imp_CryptCreateHash
0x1800b3675  test    eax, eax
0x1800b3677  jz      short loc_1800B36B9
0x1800b3679  mov     rcx, [rbp+phHash]; hHash
0x1800b367d  lea     r8d, [r14+r14]; dwDataLen
0x1800b3681  xor     r9d, r9d; dwFlags
0x1800b3684  mov     rdx, rsi; pbData
0x1800b3687  call    cs:__imp_CryptHashData
0x1800b368d  mov     rcx, [rbp+phHash]; hHash
0x1800b3691  test    eax, eax
0x1800b3693  jz      short loc_1800B36AE
0x1800b3695  xor     r9d, r9d; dwFlags
0x1800b3698  lea     rdx, [rbp+pbBuffer]; pbData
0x1800b369c  lea     r8d, [r9+4]; dwDataLen
0x1800b36a0  call    cs:__imp_CryptHashData
0x1800b36a6  mov     rcx, [rbp+phHash]; hHash
0x1800b36aa  test    eax, eax
0x1800b36ac  jnz     short loc_1800B36D4
0x1800b36ae  test    rcx, rcx
0x1800b36b1  jz      short loc_1800B36B9
0x1800b36b3  call    cs:__imp_CryptDestroyHash
0x1800b36b9  mov     rcx, [rbp+phProv]; hProv
0x1800b36bd  test    rcx, rcx
0x1800b36c0  jz      short loc_1800B36CA
0x1800b36c2  xor     edx, edx; dwFlags
0x1800b36c4  call    cs:__imp_CryptReleaseContext
0x1800b36ca  mov     eax, 8000FFFFh
0x1800b36cf  jmp     loc_1800B3793
0x1800b36d4  xor     r8d, r8d; pbData
0x1800b36d7  mov     [rsp+40h+dwFlags], 0; dwFlags
0x1800b36df  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x1800b36e3  lea     esi, [r8+2]
0x1800b36e7  mov     edx, esi; dwParam
0x1800b36e9  call    cs:__imp_CryptGetHashParam
0x1800b36ef  test    eax, eax
0x1800b36f1  jnz     short loc_1800B36F9
0x1800b36f3  mov     rcx, [rbp+phHash]
0x1800b36f7  jmp     short loc_1800B36AE
0x1800b36f9  mov     ecx, dword ptr [rbp+pdwDataLen]; unsigned __int64
0x1800b36fc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800b3701  mov     r8d, dword ptr [rbp+pdwDataLen]; Size
0x1800b3705  xor     edx, edx; Val
0x1800b3707  mov     rcx, rax; void *
0x1800b370a  mov     [rdi], rax
0x1800b370d  mov     rbx, rax
0x1800b3710  call    memset_0
0x1800b3715  mov     ecx, dword ptr [rbp+pdwDataLen]
0x1800b3718  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x1800b371c  mov     [r15], ecx
0x1800b371f  mov     r8, rbx; pbData
0x1800b3722  mov     rcx, [rbp+phHash]; hHash
0x1800b3726  mov     edx, esi; dwParam
0x1800b3728  mov     [rsp+40h+dwFlags], 0; dwFlags
0x1800b3730  call    cs:__imp_CryptGetHashParam
0x1800b3736  mov     rcx, [rbp+phHash]; hHash
0x1800b373a  test    eax, eax
0x1800b373c  jnz     short loc_1800B376E
0x1800b373e  test    rcx, rcx
0x1800b3741  jz      short loc_1800B3749
0x1800b3743  call    cs:__imp_CryptDestroyHash
0x1800b3749  mov     rcx, [rbp+phProv]; hProv
0x1800b374d  test    rcx, rcx
0x1800b3750  jz      short loc_1800B375A
0x1800b3752  xor     edx, edx; dwFlags
0x1800b3754  call    cs:__imp_CryptReleaseContext
0x1800b375a  mov     rcx, [rdi]; void *
0x1800b375d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b3762  mov     qword ptr [rdi], 0
0x1800b3769  jmp     loc_1800B36CA
0x1800b376e  test    rcx, rcx
0x1800b3771  jz      short loc_1800B3779
0x1800b3773  call    cs:__imp_CryptDestroyHash
0x1800b3779  mov     rcx, [rbp+phProv]; hProv
0x1800b377d  test    rcx, rcx
0x1800b3780  jz      short loc_1800B378A
0x1800b3782  xor     edx, edx; dwFlags
0x1800b3784  call    cs:__imp_CryptReleaseContext
0x1800b378a  xor     eax, eax
0x1800b378c  jmp     short loc_1800B3793
0x1800b378e  mov     eax, 80004003h
0x1800b3793  mov     rbx, [rsp+40h+arg_10]
0x1800b379b  add     rsp, 40h
0x1800b379f  pop     r15
0x1800b37a1  pop     r14
0x1800b37a3  pop     rdi
0x1800b37a4  pop     rsi
0x1800b37a5  pop     rbp
0x1800b37a6  retn
```
