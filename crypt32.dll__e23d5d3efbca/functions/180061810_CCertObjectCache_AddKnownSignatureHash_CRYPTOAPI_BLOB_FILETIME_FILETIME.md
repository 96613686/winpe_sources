# CCertObjectCache::AddKnownSignatureHash(_CRYPTOAPI_BLOB *,_FILETIME *,_FILETIME *)

- ea: `0x180061810`
- end: `0x180061bbf`
- name: `?AddKnownSignatureHash@CCertObjectCache@@QEAAPEAU_CHAIN_KNOWN_STORE_ENTRY@@PEAU_CRYPTOAPI_BLOB@@PEAU_FILETIME@@1@Z`
- size: `943`
- prototype: `struct _FILETIME *__fastcall(CCertObjectCache *this, struct _CRYPTOAPI_BLOB *, struct _FILETIME *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001a380`

## callees

- `0x18001071c`
- `0x180028d60`
- `0x18004d6e8`
- `0x1800615c0`
- `0x180061810`
- `0x1800819c8`
- `0x1801150c4`
- `0x1801150d0`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061922`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006192b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061936`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061b03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061b16`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061922`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006192b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061936`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061b03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061b16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061b25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061b43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061b25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061b43`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180061b34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180061b52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180061b34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180061b52`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800618b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006190f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800618b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006190f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180061a6c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180061b81`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180061a6c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180061b81`

## pseudocode

```c
struct _FILETIME *__fastcall CCertObjectCache::AddKnownSignatureHash(
        CCertObjectCache *this,
        struct _CRYPTOAPI_BLOB *a2,
        struct _FILETIME *a3,
        struct _FILETIME *a4)
{
  __int64 v4; // rdi
  unsigned int v9; // ebx
  unsigned int v10; // ebp
  __int64 v11; // r12
  HLOCAL v12; // rbx
  size_t cbData; // rbp
  struct _FILETIME *v14; // rax
  struct _FILETIME *v15; // rdi
  size_t v16; // r8
  BYTE *pbData; // rdx
  __int64 v18; // rsi
  _QWORD *v19; // rax
  int v20; // ebp
  unsigned int v21; // edx
  __int64 v22; // rsi
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rax
  int v26; // ecx
  _DWORD *v27; // rax
  unsigned int *v29; // rdx
  __int64 v30; // rax
  unsigned int v31; // r8d
  unsigned int v32; // ecx
  HLOCAL v33; // rax
  void *Src[2]; // [rsp+20h] [rbp-58h] BYREF

  v4 = *((_QWORD *)this + 6);
  v9 = (*(__int64 (__fastcall **)(struct _CRYPTOAPI_BLOB *))(v4 + 16))(a2);
  v10 = *(_DWORD *)(v4 + 32);
  v11 = *(_QWORD *)(v4 + 88);
  if ( (*(_BYTE *)v4 & 1) == 0 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 40));
  v12 = *(HLOCAL *)(v11 + 16LL * (v9 % v10) + 8);
  if ( v12 )
  {
    cbData = a2->cbData;
    while ( (_DWORD)cbData != *((_DWORD *)v12 + 4) || memcmp_0(a2->pbData, *((const void **)v12 + 3), cbData) )
    {
      v12 = (HLOCAL)*((_QWORD *)v12 + 6);
      if ( !v12 )
        goto LABEL_8;
    }
    _InterlockedIncrement((volatile signed __int32 *)v12);
  }
LABEL_8:
  if ( (*(_BYTE *)v4 & 1) == 0 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 40));
  if ( v12 )
  {
    v15 = (struct _FILETIME *)*((_QWORD *)v12 + 4);
    if ( a3
      && (a3->dwLowDateTime || a3->dwHighDateTime)
      && (!v15[2].dwLowDateTime && !v15[2].dwHighDateTime || CompareFileTime(v15 + 2, a3) > 0) )
    {
      v15[2] = *a3;
    }
    if ( a4
      && (a4->dwLowDateTime || a4->dwHighDateTime)
      && (!v15[3].dwLowDateTime && !v15[3].dwHighDateTime || CompareFileTime(v15 + 3, a4) > 0) )
    {
      v15[3] = *a4;
    }
    goto LABEL_30;
  }
  v14 = (struct _FILETIME *)LocalAlloc(0x40u, a2->cbData + 48LL);
  v15 = v14;
  if ( !v14 )
  {
    SetLastError(0x8007000E);
    return v15;
  }
  *v14 = (struct _FILETIME)&v14[6];
  v14[1].dwLowDateTime = a2->cbData;
  v16 = a2->cbData;
  pbData = a2->pbData;
  *(_OWORD *)Src = 0;
  memcpy_0(&v14[6], pbData, v16);
  Src[1] = (void *)*v15;
  LODWORD(Src[0]) = v15[1].dwLowDateTime;
  if ( a3 )
    v15[2] = *a3;
  if ( a4 )
    v15[3] = *a4;
  v18 = *((_QWORD *)this + 6);
  v19 = LocalAlloc(0x40u, 0x48u);
  v12 = v19;
  if ( v19 )
  {
    v19[5] = 0;
    *(_DWORD *)v19 = 1;
    v19[6] = 0;
    v20 = 1;
    *((_DWORD *)v19 + 16) = 0;
    v19[1] = v18;
    v19[4] = v15;
    v21 = (*(unsigned int (__fastcall **)(void **))(v18 + 16))(Src) % *(_DWORD *)(v18 + 32);
    *((_QWORD *)v12 + 7) = *(_QWORD *)(v18 + 88) + 16LL * v21;
    if ( (*(_BYTE *)v18 & 2) != 0 )
    {
      *((_OWORD *)v12 + 1) = *(_OWORD *)Src;
    }
    else
    {
      *((_DWORD *)v12 + 4) = Src[0];
      v33 = operator new(LODWORD(Src[0]));
      *((_QWORD *)v12 + 3) = v33;
      if ( v33 )
      {
        memcpy_0(v33, Src[1], LODWORD(Src[0]));
      }
      else
      {
        v20 = 0;
        SetLastError(0x8007000E);
      }
    }
    if ( !v20 )
    {
      CLruEntry::`scalar deleting destructor'(v12, v21);
      goto LABEL_18;
    }
    v22 = *((_QWORD *)v12 + 1);
    _InterlockedAdd((volatile signed __int32 *)v12, 1u);
    if ( (*(_BYTE *)v22 & 1) == 0 )
      EnterCriticalSection((LPCRITICAL_SECTION)(v22 + 40));
    v23 = *(_DWORD *)(v22 + 36);
    if ( *(_DWORD *)(v22 + 80) == v23 && v23 && !*(_DWORD *)(v22 + 100) )
      CLruCache::PurgeLeastRecentlyUsed((CLruCache *)v22, 0);
    v24 = *((_QWORD *)v12 + 7);
    *((_QWORD *)v12 + 6) = *(_QWORD *)(v24 + 8);
    v25 = *(_QWORD *)(v24 + 8);
    if ( v25 )
      *(_QWORD *)(v25 + 40) = v12;
    *(_QWORD *)(*((_QWORD *)v12 + 7) + 8LL) = v12;
    ++*(_DWORD *)(v22 + 96);
    ++*(_DWORD *)(v22 + 80);
    v26 = *(_DWORD *)(v22 + 96);
    v27 = (_DWORD *)*((_QWORD *)v12 + 7);
    *((_DWORD *)v12 + 16) = v26;
    *v27 = v26;
    if ( *(_DWORD *)(v22 + 36) )
    {
      v29 = (unsigned int *)*((_QWORD *)v12 + 7);
      v30 = *((_QWORD *)v29 + 1);
      if ( v30 )
      {
        v31 = *v29;
        do
        {
          v32 = *(_DWORD *)(v30 + 64);
          if ( v32 < v31 )
          {
            *v29 = v32;
            v31 = v32;
          }
          v30 = *(_QWORD *)(v30 + 48);
        }
        while ( v30 );
      }
    }
    if ( (*(_BYTE *)v22 & 1) == 0 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v22 + 40));
LABEL_30:
    CLruEntry::Release(v12);
    return v15;
  }
  SetLastError(0x8007000E);
  SetLastError(8u);
  SetLastError(0x8007000E);
LABEL_18:
  PkiDefaultCryptFree(v15);
  return 0;
}

```

## disassembly

```asm
0x180061810  push    rbx
0x180061812  push    rbp
0x180061813  push    rsi
0x180061814  push    rdi
0x180061815  push    r12
0x180061817  push    r13
0x180061819  push    r14
0x18006181b  push    r15
0x18006181d  sub     rsp, 38h
0x180061821  mov     rdi, [rcx+30h]
0x180061825  mov     r13, rcx
0x180061828  mov     rcx, rdx
0x18006182b  mov     rsi, r9
0x18006182e  mov     r14, r8
0x180061831  mov     r15, rdx
0x180061834  mov     rax, [rdi+10h]
0x180061838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006183d  test    byte ptr [rdi], 1
0x180061840  mov     ebx, eax
0x180061842  mov     ebp, [rdi+20h]
0x180061845  mov     r12, [rdi+58h]
0x180061849  jz      loc_180061B30
0x18006184f  xor     edx, edx
0x180061851  mov     eax, ebx
0x180061853  div     ebp
0x180061855  mov     ecx, edx
0x180061857  add     rcx, rcx
0x18006185a  mov     rbx, [r12+rcx*8+8]
0x18006185f  xor     r12d, r12d
0x180061862  test    rbx, rbx
0x180061865  jz      short loc_180061890
0x180061867  mov     ebp, [r15]
0x18006186a  cmp     ebp, [rbx+10h]
0x18006186d  jnz     short loc_180061887
0x18006186f  mov     rdx, [rbx+18h]; Buf2
0x180061873  mov     r8, rbp; Size
0x180061876  mov     rcx, [r15+8]; Buf1
0x18006187a  call    memcmp_0
0x18006187f  test    eax, eax
0x180061881  jz      loc_180061A29
0x180061887  mov     rbx, [rbx+30h]
0x18006188b  test    rbx, rbx
0x18006188e  jnz     short loc_18006186A
0x180061890  test    byte ptr [rdi], 1
0x180061893  jz      loc_180061B21
0x180061899  test    rbx, rbx
0x18006189c  jnz     loc_180061A3A
0x1800618a2  mov     edx, [r15]
0x1800618a5  mov     ebx, 40h ; '@'
0x1800618aa  add     rdx, 30h ; '0'; uBytes
0x1800618ae  mov     ecx, ebx; uFlags
0x1800618b0  call    cs:__imp_LocalAlloc
0x1800618b6  mov     rdi, rax
0x1800618b9  test    rax, rax
0x1800618bc  jz      loc_180061AFE
0x1800618c2  lea     rcx, [rax+30h]; void *
0x1800618c6  xorps   xmm0, xmm0
0x1800618c9  mov     [rax], rcx
0x1800618cc  mov     eax, [r15]
0x1800618cf  mov     [rdi+8], eax
0x1800618d2  mov     r8d, [r15]; Size
0x1800618d5  mov     rdx, [r15+8]; Src
0x1800618d9  movups  xmmword ptr [rsp+78h+Src], xmm0
0x1800618de  call    memcpy_0
0x1800618e3  mov     rax, [rdi]
0x1800618e6  mov     [rsp+78h+Src+8], rax
0x1800618eb  mov     eax, [rdi+8]
0x1800618ee  mov     dword ptr [rsp+78h+Src], eax
0x1800618f2  test    r14, r14
0x1800618f5  jnz     loc_180061B9A
0x1800618fb  test    rsi, rsi
0x1800618fe  jnz     loc_180061BA6
0x180061904  mov     rsi, [r13+30h]
0x180061908  mov     edx, 48h ; 'H'; uBytes
0x18006190d  mov     ecx, ebx; uFlags
0x18006190f  call    cs:__imp_LocalAlloc
0x180061915  mov     rbx, rax
0x180061918  test    rax, rax
0x18006191b  jnz     short loc_18006194C
0x18006191d  mov     ecx, 8007000Eh; dwErrCode
0x180061922  call    cs:__imp_SetLastError
0x180061928  lea     ecx, [rbx+8]; dwErrCode
0x18006192b  call    cs:__imp_SetLastError
0x180061931  mov     ecx, 8007000Eh; dwErrCode
0x180061936  call    cs:__imp_SetLastError
0x18006193c  mov     rcx, rdi; hMem
0x18006193f  call    PkiDefaultCryptFree
0x180061944  mov     rdi, r12
0x180061947  jmp     loc_180061A15
0x18006194c  mov     r14d, 1
0x180061952  mov     [rax+28h], r12
0x180061956  mov     [rax], r14d
0x180061959  lea     rcx, [rsp+78h+Src]
0x18006195e  mov     [rax+30h], r12
0x180061962  mov     ebp, r14d
0x180061965  mov     [rax+40h], r12d
0x180061969  mov     [rax+8], rsi
0x18006196d  mov     [rax+20h], rdi
0x180061971  mov     rax, [rsi+10h]
0x180061975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006197a  xor     edx, edx; unsigned int
0x18006197c  div     dword ptr [rsi+20h]
0x18006197f  mov     ecx, edx
0x180061981  shl     rcx, 4
0x180061985  add     rcx, [rsi+58h]
0x180061989  mov     [rbx+38h], rcx
0x18006198d  test    byte ptr [rsi], 2
0x180061990  jz      loc_180061ACE
0x180061996  movups  xmm0, xmmword ptr [rsp+78h+Src]
0x18006199b  movdqu  xmmword ptr [rbx+10h], xmm0
0x1800619a0  test    ebp, ebp
0x1800619a2  jz      loc_180061BB2
0x1800619a8  mov     rsi, [rbx+8]
0x1800619ac  lock add [rbx], r14d
0x1800619b0  test    [rsi], r14b
0x1800619b3  jz      loc_180061B4E
0x1800619b9  mov     eax, [rsi+24h]
0x1800619bc  cmp     [rsi+50h], eax
0x1800619bf  jz      loc_180061A7E
0x1800619c5  mov     rcx, [rbx+38h]
0x1800619c9  mov     rax, [rcx+8]
0x1800619cd  mov     [rbx+30h], rax
0x1800619d1  mov     rax, [rcx+8]
0x1800619d5  test    rax, rax
0x1800619d8  jz      short loc_1800619DE
0x1800619da  mov     [rax+28h], rbx
0x1800619de  mov     rax, [rbx+38h]
0x1800619e2  mov     [rax+8], rbx
0x1800619e6  add     [rsi+60h], r14d
0x1800619ea  add     [rsi+50h], r14d
0x1800619ee  mov     ecx, [rsi+60h]
0x1800619f1  mov     rax, [rbx+38h]
0x1800619f5  mov     [rbx+40h], ecx
0x1800619f8  mov     [rax], ecx
0x1800619fa  cmp     [rsi+24h], r12d
0x1800619fe  jnz     loc_180061A9F
0x180061a04  test    [rsi], r14b
0x180061a07  jz      loc_180061B3F
0x180061a0d  mov     rcx, rbx; hMem
0x180061a10  call    ?Release@CLruEntry@@QEAAXXZ; CLruEntry::Release(void)
0x180061a15  mov     rax, rdi
0x180061a18  add     rsp, 38h
0x180061a1c  pop     r15
0x180061a1e  pop     r14
0x180061a20  pop     r13
0x180061a22  pop     r12
0x180061a24  pop     rdi
0x180061a25  pop     rsi
0x180061a26  pop     rbp
0x180061a27  pop     rbx
0x180061a28  retn
0x180061a29  test    rbx, rbx
0x180061a2c  jz      loc_180061890
0x180061a32  lock inc dword ptr [rbx]
0x180061a35  jmp     loc_180061890
0x180061a3a  mov     rdi, [rbx+20h]
0x180061a3e  test    r14, r14
0x180061a41  jnz     loc_180061B5D
0x180061a47  test    rsi, rsi
0x180061a4a  jz      short loc_180061A0D
0x180061a4c  cmp     [rsi], r12d
0x180061a4f  jnz     short loc_180061A57
0x180061a51  cmp     [rsi+4], r12d
0x180061a55  jz      short loc_180061A0D
0x180061a57  lea     r14, [rdi+18h]
0x180061a5b  cmp     [r14], r12d
0x180061a5e  jnz     short loc_180061A66
0x180061a60  cmp     [r14+4], r12d
0x180061a64  jz      short loc_180061A76
0x180061a66  mov     rdx, rsi; lpFileTime2
0x180061a69  mov     rcx, r14; lpFileTime1
0x180061a6c  call    cs:__imp_CompareFileTime
0x180061a72  test    eax, eax
0x180061a74  jle     short loc_180061A0D
0x180061a76  mov     rax, [rsi]
0x180061a79  mov     [r14], rax
0x180061a7c  jmp     short loc_180061A0D
0x180061a7e  test    eax, eax
0x180061a80  jz      loc_1800619C5
0x180061a86  cmp     [rsi+64h], r12d
0x180061a8a  jnz     loc_1800619C5
0x180061a90  xor     edx, edx; void *
0x180061a92  mov     rcx, rsi; this
0x180061a95  call    ?PurgeLeastRecentlyUsed@CLruCache@@AEAAXPEAX@Z; CLruCache::PurgeLeastRecentlyUsed(void *)
0x180061a9a  jmp     loc_1800619C5
0x180061a9f  mov     rdx, [rbx+38h]
0x180061aa3  mov     rax, [rdx+8]
0x180061aa7  test    rax, rax
0x180061aaa  jz      loc_180061A04
0x180061ab0  mov     r8d, [rdx]
0x180061ab3  mov     ecx, [rax+40h]
0x180061ab6  cmp     ecx, r8d
0x180061ab9  jnb     short loc_180061AC0
0x180061abb  mov     [rdx], ecx
0x180061abd  mov     r8d, ecx
0x180061ac0  mov     rax, [rax+30h]
0x180061ac4  test    rax, rax
0x180061ac7  jnz     short loc_180061AB3
0x180061ac9  jmp     loc_180061A04
0x180061ace  mov     eax, dword ptr [rsp+78h+Src]
0x180061ad2  mov     [rbx+10h], eax
0x180061ad5  mov     ecx, dword ptr [rsp+78h+Src]; uBytes
0x180061ad9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180061ade  mov     [rbx+18h], rax
0x180061ae2  test    rax, rax
0x180061ae5  jz      short loc_180061B0E
0x180061ae7  mov     r8d, dword ptr [rsp+78h+Src]; Size
0x180061aec  mov     rcx, rax; void *
0x180061aef  mov     rdx, [rsp+78h+Src+8]; Src
0x180061af4  call    memcpy_0
0x180061af9  jmp     loc_1800619A0
0x180061afe  mov     ecx, 8007000Eh; dwErrCode
0x180061b03  call    cs:__imp_SetLastError
0x180061b09  jmp     loc_180061A15
0x180061b0e  mov     ecx, 8007000Eh; dwErrCode
0x180061b13  mov     ebp, r12d
0x180061b16  call    cs:__imp_SetLastError
0x180061b1c  jmp     loc_1800619A0
0x180061b21  lea     rcx, [rdi+28h]; lpCriticalSection
0x180061b25  call    cs:__imp_LeaveCriticalSection
0x180061b2b  jmp     loc_180061899
0x180061b30  lea     rcx, [rdi+28h]; lpCriticalSection
0x180061b34  call    cs:__imp_EnterCriticalSection
0x180061b3a  jmp     loc_18006184F
0x180061b3f  lea     rcx, [rsi+28h]; lpCriticalSection
0x180061b43  call    cs:__imp_LeaveCriticalSection
0x180061b49  jmp     loc_180061A0D
0x180061b4e  lea     rcx, [rsi+28h]; lpCriticalSection
0x180061b52  call    cs:__imp_EnterCriticalSection
0x180061b58  jmp     loc_1800619B9
0x180061b5d  cmp     [r14], r12d
0x180061b60  jnz     short loc_180061B6C
0x180061b62  cmp     [r14+4], r12d
0x180061b66  jz      loc_180061A47
0x180061b6c  lea     r15, [rdi+10h]
0x180061b70  cmp     [r15], r12d
0x180061b73  jnz     short loc_180061B7B
0x180061b75  cmp     [r15+4], r12d
0x180061b79  jz      short loc_180061B8F
0x180061b7b  mov     rdx, r14; lpFileTime2
0x180061b7e  mov     rcx, r15; lpFileTime1
0x180061b81  call    cs:__imp_CompareFileTime
0x180061b87  test    eax, eax
0x180061b89  jle     loc_180061A47
0x180061b8f  mov     rax, [r14]
0x180061b92  mov     [r15], rax
0x180061b95  jmp     loc_180061A47
0x180061b9a  mov     rax, [r14]
0x180061b9d  mov     [rdi+10h], rax
0x180061ba1  jmp     loc_1800618FB
0x180061ba6  mov     rax, [rsi]
0x180061ba9  mov     [rdi+18h], rax
0x180061bad  jmp     loc_180061904
0x180061bb2  mov     rcx, rbx; hMem
0x180061bb5  call    ??_GCLruEntry@@QEAAPEAXI@Z; CLruEntry::`scalar deleting destructor'(uint)
0x180061bba  jmp     loc_18006193C
```
