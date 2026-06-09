# CTVOAgent::StartActiveRetrieval(char const *,char const *,void *,_FILETIME *,ulong,void * *,_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *,uchar * const,uchar * const,_TVO_ACTIVE_ENTRY * *)

- ea: `0x180008a30`
- end: `0x180008f78`
- name: `?StartActiveRetrieval@CTVOAgent@@QEAAJPEBD0PEAXPEAU_FILETIME@@KPEAPEAXPEAU_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO@@QEAE5PEAPEAU_TVO_ACTIVE_ENTRY@@@Z`
- size: `1352`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, const char *, const char *, __int64 *, struct _FILETIME *, signed int, void **, struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *, unsigned __int8 *const Buf2, unsigned __int8 *const, struct _TVO_ACTIVE_ENTRY **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180007cc0`

## callees

- `0x180008a30`
- `0x180017d34`
- `0x1800183a8`
- `0x180019a54`
- `0x180026546`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008a94`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008ecb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008f19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008a94`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008ecb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008f19`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180008d5e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180008d5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008b5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008b5c`
- `CRYPT32!I_CertDiagControl` at `0x180008b9f`
- `CRYPT32!I_CertDiagControl` at `0x180008dbf`
- `CRYPT32!I_CertDiagControl` at `0x180008b9f`
- `CRYPT32!I_CertDiagControl` at `0x180008dbf`
- `CRYPT32!CertFindExtension` at `0x180008c5c`
- `CRYPT32!CertFindExtension` at `0x180008c86`
- `CRYPT32!CertFindExtension` at `0x180008c5c`
- `CRYPT32!CertFindExtension` at `0x180008c86`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008ec3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008ec3`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008d91`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008d91`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180008e97`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180008e97`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008d79`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008d79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008e62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008e62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008f41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008f41`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008a81`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008a81`

## pseudocode

```c
__int64 __fastcall CTVOAgent::StartActiveRetrieval(
        struct _RTL_CRITICAL_SECTION *this,
        const char *a2,
        const char *a3,
        __int64 *a4,
        struct _FILETIME *a5,
        signed int a6,
        void **a7,
        struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *a8,
        unsigned __int8 *const Buf2,
        unsigned __int8 *const a10,
        struct _TVO_ACTIVE_ENTRY **a11)
{
  struct _TVO_ACTIVE_ENTRY **v11; // r14
  _QWORD *v15; // rax
  __int64 **v16; // rbx
  _QWORD *v18; // rax
  LPFILETIME pftCacheResync; // rax
  DWORD CurrentThreadId; // eax
  char *p_LockCount; // rdi
  char *v22; // r15
  char *i; // rcx
  struct _TVO_ACTIVE_ENTRY *v24; // rax
  char *v25; // rax
  struct _TVO_ACTIVE_ENTRY **Extension; // rax
  __int64 v27; // rcx
  PCERT_EXTENSION v28; // rax
  unsigned int v29; // edx
  int iDeltaCrlIndicator; // eax
  __int64 *v31; // rax
  __int64 *EventA; // rax
  __int64 *v33; // r15
  __int64 **v34; // rax
  __int32 v35; // ecx
  __int64 *v36; // rcx
  DWORD v37; // ebp
  HANDLE Handles[7]; // [rsp+30h] [rbp-38h] BYREF

  v11 = a11;
  *a11 = 0;
  if ( (a6 & 0x1000500) != 0 || a3 != (const char *)2 || a6 >= 0 )
  {
    ++dword_180032930;
    return 1;
  }
  v15 = LocalAlloc(0x40u, 0xC0u);
  v16 = (__int64 **)v15;
  if ( !v15 )
  {
    SetLastError(0x8007000E);
    ++dword_180032930;
    return 1;
  }
  v15[1] = v15;
  *v15 = v15;
  v18 = v15 + 2;
  v18[1] = v18;
  *v18 = v18;
  v16[6] = (__int64 *)a2;
  v16[7] = a4;
  if ( a5 )
    v16[8] = (__int64 *)*a5;
  pftCacheResync = a8->pftCacheResync;
  if ( pftCacheResync )
    v16[9] = (__int64 *)*pftCacheResync;
  *((_DWORD *)v16 + 20) = a8->iDeltaCrlIndicator;
  *((_DWORD *)v16 + 21) = a6;
  *(_OWORD *)(v16 + 11) = *(_OWORD *)Buf2;
  *(_OWORD *)(v16 + 13) = *((_OWORD *)Buf2 + 1);
  *(_OWORD *)(v16 + 15) = *(_OWORD *)a10;
  *(_OWORD *)(v16 + 17) = *((_OWORD *)a10 + 1);
  CurrentThreadId = GetCurrentThreadId();
  p_LockCount = (char *)&this[1].LockCount;
  *((_DWORD *)v16 + 38) = CurrentThreadId;
  v22 = *(char **)p_LockCount;
  for ( i = *(char **)p_LockCount; ; i = *(char **)i )
  {
    if ( i == p_LockCount )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          if ( v22 == p_LockCount )
          {
            a11 = 0;
            I_CertDiagControl(25, 0, &a11);
            v24 = (struct _TVO_ACTIVE_ENTRY *)a11;
            if ( a11 )
              v24 = a11[1];
            v16[20] = (__int64 *)v24;
            v25 = *(char **)p_LockCount;
            if ( *(char **)(*(_QWORD *)p_LockCount + 8LL) != p_LockCount )
LABEL_47:
              __fastfail(3u);
            ++dword_180032934;
            *v16 = (__int64 *)v25;
            v16[1] = (__int64 *)p_LockCount;
            *((_QWORD *)v25 + 1) = v16;
            *(_QWORD *)p_LockCount = v16;
            *v11 = (struct _TVO_ACTIVE_ENTRY *)v16;
            return 1;
          }
          if ( *((const char **)v22 + 6) != a2 || *((_DWORD *)v22 + 21) != a6 || memcmp_0(v22 + 88, Buf2, 0x20u) )
            goto LABEL_37;
          Extension = (struct _TVO_ACTIVE_ENTRY **)CertFindExtension(
                                                     "2.5.29.31",
                                                     *(_DWORD *)(a4[3] + 192),
                                                     *(CERT_EXTENSION **)(a4[3] + 200));
          v27 = *((_QWORD *)v22 + 7);
          a11 = Extension;
          v28 = CertFindExtension(
                  "2.5.29.31",
                  *(_DWORD *)(*(_QWORD *)(v27 + 24) + 192LL),
                  *(CERT_EXTENSION **)(*(_QWORD *)(v27 + 24) + 200LL));
          if ( a11 )
            break;
          if ( !v28 )
            goto LABEL_28;
LABEL_38:
          if ( (unsigned int)IsActiveRetrievalCdpMatchCheckDisabled() )
            goto LABEL_28;
          ++dword_180032940;
          v22 = *(char **)v22;
        }
        if ( !v28 )
          goto LABEL_38;
        v29 = *((_DWORD *)a11 + 4);
        if ( v29 != v28->Value.cbData || memcmp_0(a11[3], v28->Value.pbData, v29) )
          goto LABEL_38;
LABEL_28:
        if ( *((_DWORD *)v16 + 16) || *((_DWORD *)v16 + 17) )
        {
          if ( !*((_DWORD *)v22 + 16) && !*((_DWORD *)v22 + 17)
            || (unsigned int)I_CryptSubtractFileTimes(v16 + 8, v22 + 64) > 0x78 )
          {
            goto LABEL_37;
          }
          goto LABEL_31;
        }
        if ( *((_DWORD *)v22 + 16) )
          goto LABEL_37;
        if ( *((_DWORD *)v22 + 17) )
        {
          v22 = *(char **)v22;
        }
        else
        {
LABEL_31:
          if ( !*((_DWORD *)v16 + 18) && !*((_DWORD *)v16 + 19)
            || (*((_DWORD *)v22 + 18) || *((_DWORD *)v22 + 19))
            && (unsigned int)I_CryptSubtractFileTimes(v16 + 9, v22 + 72) <= 0x78 )
          {
            iDeltaCrlIndicator = a8->iDeltaCrlIndicator;
            if ( *((_DWORD *)v22 + 20) == iDeltaCrlIndicator )
            {
              if ( iDeltaCrlIndicator == 0x7FFFFFFF )
              {
                ++dword_180032958;
              }
              else
              {
                v31 = (__int64 *)OpenThread(0x100000u, 0, *((_DWORD *)v22 + 38));
                v16[5] = v31;
                if ( v31 )
                {
                  if ( WaitForSingleObjectEx(v31, 0, 0) )
                  {
                    EventA = (__int64 *)CreateEventA(0, 0, 0, 0);
                    v16[4] = EventA;
                    if ( !EventA )
                    {
                      FreeActiveEntry(v16);
                      ++dword_180032950;
                      return 1;
                    }
                    a11 = 0;
                    I_CertDiagControl(25, 0, &a11);
                    v33 = (__int64 *)(v22 + 16);
                    v16[20] = (__int64 *)a11;
                    *((_DWORD *)v16 + 42) = -2147418113;
                    v34 = (__int64 **)v33[1];
                    if ( *v34 != v33 )
                      goto LABEL_47;
                    ++dword_180032938;
                    *v16 = v33;
                    v16[1] = (__int64 *)v34;
                    *v34 = (__int64 *)v16;
                    v33[1] = (__int64)v16;
                    LeaveCriticalSection(this);
                    Handles[0] = v16[4];
                    Handles[1] = v16[5];
                    WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
                    ++dword_18003293C;
                    v35 = _InterlockedExchange((volatile __int32 *)v16 + 46, 0);
                    if ( v35 == -1 )
                    {
                      ++dword_180032948;
                      FreeActiveEntry(v16);
LABEL_59:
                      EnterCriticalSection(this);
                      SetLastError(0);
                      return 2;
                    }
                    if ( v35 != 1 )
                    {
                      ++dword_18003294C;
                      goto LABEL_59;
                    }
                    v36 = v16[22];
                    ++dword_180032944;
                    *a7 = v36;
                    v37 = *((_DWORD *)v16 + 42);
                    FreeActiveEntry(v16);
                    SetLastError(v37);
                    return (unsigned int)-(v37 != 0);
                  }
                  CloseHandle(v16[5]);
                  v16[5] = 0;
                }
                ++dword_18003295C;
              }
            }
          }
LABEL_37:
          v22 = *(char **)v22;
        }
      }
    }
    if ( *((_DWORD *)i + 38) == CurrentThreadId )
      break;
  }
  FreeActiveEntry(v16);
  ++dword_180032954;
  return 1;
}

```

## disassembly

```asm
0x180008a30  mov     [rsp+lpCriticalSection], rcx
0x180008a35  push    rsi
0x180008a36  push    rdi
0x180008a37  push    r12
0x180008a39  push    r13
0x180008a3b  push    r14
0x180008a3d  sub     rsp, 40h
0x180008a41  mov     r14, [rsp+68h+arg_50]
0x180008a49  mov     r13, r9
0x180008a4c  mov     esi, [rsp+68h+arg_28]
0x180008a53  mov     r12, rdx
0x180008a56  mov     rdi, rcx
0x180008a59  mov     qword ptr [r14], 0
0x180008a60  test    esi, 1000500h
0x180008a66  jnz     short loc_180008AB7
0x180008a68  cmp     r8, 2
0x180008a6c  jnz     short loc_180008AB7
0x180008a6e  test    esi, esi
0x180008a70  jns     short loc_180008AB7
0x180008a72  mov     edx, 0C0h; uBytes
0x180008a77  mov     [rsp+68h+arg_8], rbx
0x180008a7c  mov     ecx, 40h ; '@'; uFlags
0x180008a81  call    cs:__imp_LocalAlloc
0x180008a87  mov     rbx, rax
0x180008a8a  test    rax, rax
0x180008a8d  jnz     short loc_180008ACF
0x180008a8f  mov     ecx, 8007000Eh; dwErrCode
0x180008a94  call    cs:__imp_SetLastError
0x180008a9a  inc     cs:dword_180032930
0x180008aa0  mov     eax, 1
0x180008aa5  mov     rbx, [rsp+68h+arg_8]
0x180008aaa  add     rsp, 40h
0x180008aae  pop     r14
0x180008ab0  pop     r13
0x180008ab2  pop     r12
0x180008ab4  pop     rdi
0x180008ab5  pop     rsi
0x180008ab6  retn
0x180008ab7  inc     cs:dword_180032930
0x180008abd  mov     eax, 1
0x180008ac2  add     rsp, 40h
0x180008ac6  pop     r14
0x180008ac8  pop     r13
0x180008aca  pop     r12
0x180008acc  pop     rdi
0x180008acd  pop     rsi
0x180008ace  retn
0x180008acf  mov     [rax+8], rbx
0x180008ad3  mov     [rax], rbx
0x180008ad6  add     rax, 10h
0x180008ada  mov     [rsp+68h+arg_10], rbp
0x180008ae2  mov     [rsp+68h+arg_18], r15
0x180008aea  mov     [rax+8], rax
0x180008aee  mov     [rax], rax
0x180008af1  mov     rax, [rsp+68h+arg_20]
0x180008af9  mov     [rbx+30h], r12
0x180008afd  mov     [rbx+38h], r13
0x180008b01  test    rax, rax
0x180008b04  jz      short loc_180008B0D
0x180008b06  mov     rax, [rax]
0x180008b09  mov     [rbx+40h], rax
0x180008b0d  mov     rbp, [rsp+68h+arg_38]
0x180008b15  mov     rax, [rbp+8]
0x180008b19  test    rax, rax
0x180008b1c  jnz     loc_180008F26
0x180008b22  mov     eax, [rbp+4]
0x180008b25  mov     [rbx+50h], eax
0x180008b28  mov     rax, [rsp+68h+Buf2]
0x180008b30  mov     [rbx+54h], esi
0x180008b33  movups  xmm0, xmmword ptr [rax]
0x180008b36  movups  xmmword ptr [rbx+58h], xmm0
0x180008b3a  movups  xmm1, xmmword ptr [rax+10h]
0x180008b3e  mov     rax, [rsp+68h+arg_48]
0x180008b46  movups  xmmword ptr [rbx+68h], xmm1
0x180008b4a  movups  xmm0, xmmword ptr [rax]
0x180008b4d  movups  xmmword ptr [rbx+78h], xmm0
0x180008b51  movups  xmm1, xmmword ptr [rax+10h]
0x180008b55  movups  xmmword ptr [rbx+88h], xmm1
0x180008b5c  call    cs:__imp_GetCurrentThreadId
0x180008b62  add     rdi, 30h ; '0'
0x180008b66  mov     [rbx+98h], eax
0x180008b6c  mov     r15, [rdi]
0x180008b6f  mov     rcx, r15
0x180008b72  cmp     rcx, rdi
0x180008b75  jnz     loc_180008BFD
0x180008b7b  cmp     r15, rdi
0x180008b7e  jnz     loc_180008C11
0x180008b84  lea     r8, [rsp+68h+arg_50]
0x180008b8c  mov     [rsp+68h+arg_50], 0
0x180008b98  xor     edx, edx
0x180008b9a  mov     ecx, 19h
0x180008b9f  call    cs:__imp_I_CertDiagControl
0x180008ba5  mov     rax, [rsp+68h+arg_50]
0x180008bad  test    rax, rax
0x180008bb0  jnz     short loc_180008BF7
0x180008bb2  mov     [rbx+0A0h], rax
0x180008bb9  mov     rax, [rdi]
0x180008bbc  cmp     [rax+8], rdi
0x180008bc0  jnz     loc_180008DEB
0x180008bc6  inc     cs:dword_180032934
0x180008bcc  mov     [rbx], rax
0x180008bcf  mov     [rbx+8], rdi
0x180008bd3  mov     [rax+8], rbx
0x180008bd7  mov     [rdi], rbx
0x180008bda  mov     [r14], rbx
0x180008bdd  mov     eax, 1
0x180008be2  mov     rbp, [rsp+68h+arg_10]
0x180008bea  mov     r15, [rsp+68h+arg_18]
0x180008bf2  jmp     loc_180008AA5
0x180008bf7  mov     rax, [rax+8]
0x180008bfb  jmp     short loc_180008BB2
0x180008bfd  cmp     [rcx+98h], eax
0x180008c03  jz      loc_180008E02
0x180008c09  mov     rcx, [rcx]
0x180008c0c  jmp     loc_180008B72
0x180008c11  cmp     [r15+30h], r12
0x180008c15  jnz     loc_180008D17
0x180008c1b  cmp     [r15+54h], esi
0x180008c1f  jnz     loc_180008D17
0x180008c25  mov     rdx, [rsp+68h+Buf2]; Buf2
0x180008c2d  lea     rcx, [r15+58h]; Buf1
0x180008c31  mov     r8d, 20h ; ' '; Size
0x180008c37  call    memcmp_0
0x180008c3c  test    eax, eax
0x180008c3e  jnz     loc_180008D17
0x180008c44  mov     rdx, [r13+18h]
0x180008c48  lea     rcx, pszObjId; "2.5.29.31"
0x180008c4f  mov     r8, [rdx+0C8h]; rgExtensions
0x180008c56  mov     edx, [rdx+0C0h]; cExtensions
0x180008c5c  call    cs:__imp_CertFindExtension
0x180008c62  mov     rcx, [r15+38h]
0x180008c66  mov     [rsp+68h+arg_50], rax
0x180008c6e  mov     rdx, [rcx+18h]
0x180008c72  lea     rcx, pszObjId; "2.5.29.31"
0x180008c79  mov     r8, [rdx+0C8h]; rgExtensions
0x180008c80  mov     edx, [rdx+0C0h]; cExtensions
0x180008c86  call    cs:__imp_CertFindExtension
0x180008c8c  mov     rcx, [rsp+68h+arg_50]
0x180008c94  test    rcx, rcx
0x180008c97  jz      loc_180008E28
0x180008c9d  test    rax, rax
0x180008ca0  jz      short loc_180008D1F
0x180008ca2  mov     edx, [rcx+10h]
0x180008ca5  cmp     edx, [rax+10h]
0x180008ca8  jnz     short loc_180008D1F
0x180008caa  mov     rcx, [rcx+18h]; Buf1
0x180008cae  mov     r8d, edx; Size
0x180008cb1  mov     rdx, [rax+18h]; Buf2
0x180008cb5  call    memcmp_0
0x180008cba  test    eax, eax
0x180008cbc  jnz     short loc_180008D1F
0x180008cbe  cmp     dword ptr [rbx+40h], 0
0x180008cc2  lea     rcx, [rbx+40h]
0x180008cc6  jz      short loc_180008D06
0x180008cc8  cmp     dword ptr [r15+40h], 0
0x180008ccd  lea     rdx, [r15+40h]
0x180008cd1  jz      loc_180008DF2
0x180008cd7  call    I_CryptSubtractFileTimes
0x180008cdc  cmp     eax, 78h ; 'x'
0x180008cdf  ja      short loc_180008D17
0x180008ce1  cmp     dword ptr [rbx+48h], 0
0x180008ce5  lea     rcx, [rbx+48h]
0x180008ce9  jz      short loc_180008D36
0x180008ceb  cmp     dword ptr [r15+48h], 0
0x180008cf0  lea     rdx, [r15+48h]
0x180008cf4  jz      loc_180008E36
0x180008cfa  call    I_CryptSubtractFileTimes
0x180008cff  cmp     eax, 78h ; 'x'
0x180008d02  ja      short loc_180008D17
0x180008d04  jmp     short loc_180008D3C
0x180008d06  cmp     dword ptr [rcx+4], 0
0x180008d0a  jnz     short loc_180008CC8
0x180008d0c  cmp     dword ptr [r15+40h], 0
0x180008d11  jz      loc_180008E15
0x180008d17  mov     r15, [r15]
0x180008d1a  jmp     loc_180008B7B
0x180008d1f  call    _IsActiveRetrievalCdpMatchCheckDisabled
0x180008d24  test    eax, eax
0x180008d26  jnz     short loc_180008CBE
0x180008d28  inc     cs:dword_180032940
0x180008d2e  mov     r15, [r15]
0x180008d31  jmp     loc_180008B7B
0x180008d36  cmp     dword ptr [rcx+4], 0
0x180008d3a  jnz     short loc_180008CEB
0x180008d3c  mov     eax, [rbp+4]
0x180008d3f  cmp     [r15+50h], eax
0x180008d43  jnz     short loc_180008D17
0x180008d45  cmp     eax, 7FFFFFFFh
0x180008d4a  jz      loc_180008F32
0x180008d50  mov     r8d, [r15+98h]; dwThreadId
0x180008d57  xor     edx, edx; bInheritHandle
0x180008d59  mov     ecx, 100000h; dwDesiredAccess
0x180008d5e  call    cs:__imp_OpenThread
0x180008d64  mov     [rbx+28h], rax
0x180008d68  test    rax, rax
0x180008d6b  jz      loc_180008F4F
0x180008d71  xor     r8d, r8d; bAlertable
0x180008d74  xor     edx, edx; dwMilliseconds
0x180008d76  mov     rcx, rax; hHandle
0x180008d79  call    cs:__imp_WaitForSingleObjectEx
0x180008d7f  test    eax, eax
0x180008d81  jz      loc_180008F3D
0x180008d87  xor     r9d, r9d; lpName
0x180008d8a  xor     r8d, r8d; bInitialState
0x180008d8d  xor     edx, edx; bManualReset
0x180008d8f  xor     ecx, ecx; lpEventAttributes
0x180008d91  call    cs:__imp_CreateEventA
0x180008d97  mov     [rbx+20h], rax
0x180008d9b  test    rax, rax
0x180008d9e  jz      loc_180008F5A
0x180008da4  lea     r8, [rsp+68h+arg_50]
0x180008dac  mov     [rsp+68h+arg_50], 0
0x180008db8  xor     edx, edx
0x180008dba  mov     ecx, 19h
0x180008dbf  call    cs:__imp_I_CertDiagControl
0x180008dc5  mov     rax, [rsp+68h+arg_50]
0x180008dcd  add     r15, 10h
0x180008dd1  mov     [rbx+0A0h], rax
0x180008dd8  mov     dword ptr [rbx+0A8h], 8000FFFFh
0x180008de2  mov     rax, [r15+8]
0x180008de6  cmp     [rax], r15
0x180008de9  jz      short loc_180008E46
0x180008deb  mov     ecx, 3
0x180008df0  int     29h; Win8: RtlFailFast(ecx)
0x180008df2  cmp     dword ptr [r15+44h], 0
0x180008df7  jnz     loc_180008CD7
0x180008dfd  jmp     loc_180008D17
0x180008e02  mov     rcx, rbx; hMem
0x180008e05  call    _FreeActiveEntry
0x180008e0a  inc     cs:dword_180032954
0x180008e10  jmp     loc_180008BDD
0x180008e15  cmp     dword ptr [r15+44h], 0
0x180008e1a  jz      loc_180008CE1
0x180008e20  mov     r15, [r15]
0x180008e23  jmp     loc_180008B7B
0x180008e28  test    rax, rax
0x180008e2b  jz      loc_180008CBE
0x180008e31  jmp     loc_180008D1F
0x180008e36  cmp     dword ptr [r15+4Ch], 0
0x180008e3b  jz      loc_180008D17
0x180008e41  jmp     loc_180008CFA
0x180008e46  mov     rdi, [rsp+68h+lpCriticalSection]
0x180008e4b  inc     cs:dword_180032938
0x180008e51  mov     rcx, rdi; lpCriticalSection
0x180008e54  mov     [rbx], r15
0x180008e57  mov     [rbx+8], rax
0x180008e5b  mov     [rax], rbx
0x180008e5e  mov     [r15+8], rbx
0x180008e62  call    cs:__imp_LeaveCriticalSection
0x180008e68  mov     rax, [rbx+20h]
0x180008e6c  lea     rdx, [rsp+68h+Handles]; lpHandles
0x180008e71  mov     [rsp+68h+Handles], rax
0x180008e76  mov     esi, 2
0x180008e7b  mov     rax, [rbx+28h]
0x180008e7f  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x180008e85  xor     r8d, r8d; bWaitAll
0x180008e88  mov     [rsp+68h+var_30], rax
0x180008e8d  mov     ecx, esi; nCount
0x180008e8f  mov     [rsp+68h+bAlertable], 0; bAlertable
0x180008e97  call    cs:__imp_WaitForMultipleObjectsEx
0x180008e9d  inc     cs:dword_18003293C
0x180008ea3  xor     ecx, ecx
0x180008ea5  xchg    ecx, [rbx+0B8h]
0x180008eab  xor     ebp, ebp
0x180008ead  cmp     ecx, 0FFFFFFFFh
0x180008eb0  jnz     short loc_180008ED8
0x180008eb2  inc     cs:dword_180032948
0x180008eb8  mov     rcx, rbx; hMem
0x180008ebb  call    _FreeActiveEntry
0x180008ec0  mov     rcx, rdi; lpCriticalSection
0x180008ec3  call    cs:__imp_EnterCriticalSection
0x180008ec9  mov     ecx, ebp; dwErrCode
0x180008ecb  call    cs:__imp_SetLastError
0x180008ed1  mov     eax, esi
0x180008ed3  jmp     loc_180008BE2
0x180008ed8  test    ecx, ecx
0x180008eda  jz      loc_180008F6D
0x180008ee0  cmp     ecx, 1
0x180008ee3  jnz     loc_180008F6D
0x180008ee9  mov     rcx, [rbx+0B0h]
0x180008ef0  mov     rax, [rsp+68h+arg_30]
0x180008ef8  inc     cs:dword_180032944
0x180008efe  mov     [rax], rcx
0x180008f01  mov     rcx, rbx; hMem
0x180008f04  mov     ebp, [rbx+0A8h]
0x180008f0a  call    _FreeActiveEntry
0x180008f0f  xor     eax, eax
0x180008f11  mov     ecx, ebp; dwErrCode
0x180008f13  sub     eax, ebp
0x180008f15  neg     eax
0x180008f17  sbb     esi, esi
0x180008f19  call    cs:__imp_SetLastError
0x180008f1f  mov     eax, esi
0x180008f21  jmp     loc_180008BE2
0x180008f26  mov     rax, [rax]
0x180008f29  mov     [rbx+48h], rax
0x180008f2d  jmp     loc_180008B22
0x180008f32  inc     cs:dword_180032958
0x180008f38  jmp     loc_180008D17
0x180008f3d  mov     rcx, [rbx+28h]; hObject
  ... truncated ...
```
