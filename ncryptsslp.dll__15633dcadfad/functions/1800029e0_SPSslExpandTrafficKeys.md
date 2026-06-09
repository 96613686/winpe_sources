# SPSslExpandTrafficKeys

- ea: `0x1800029e0`
- end: `0x180003046`
- name: `SPSslExpandTrafficKeys`
- size: `1638`
- prototype: `__int64 __fastcall(_DWORD *, const wchar_t *, BCRYPT_HASH_HANDLE *, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800029e0`
- `0x1800037a0`
- `0x18000b594`
- `0x18000b654`
- `0x1800183d0`

## import_xrefs

- `bcrypt!BCryptDuplicateHash` at `0x180002b2c`
- `bcrypt!BCryptDuplicateHash` at `0x180002b2c`
- `bcrypt!BCryptFinishHash` at `0x180002b81`
- `bcrypt!BCryptFinishHash` at `0x180002b81`
- `bcrypt!BCryptDestroyHash` at `0x180002bf8`
- `bcrypt!BCryptDestroyHash` at `0x180002bf8`
- `ntdll!RtlFreeHeap` at `0x180002c2f`
- `ntdll!RtlFreeHeap` at `0x180002c62`
- `ntdll!RtlFreeHeap` at `0x180002c2f`
- `ntdll!RtlFreeHeap` at `0x180002c62`
- `ntdll!RtlAllocateHeap` at `0x180002b03`
- `ntdll!RtlAllocateHeap` at `0x180002b5c`
- `ntdll!RtlAllocateHeap` at `0x180002b03`
- `ntdll!RtlAllocateHeap` at `0x180002b5c`

## string_xrefs

- `0x180002aab`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180002cda`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180002d35`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180002dab`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180002ec5`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180002f34`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180002f79`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180002fa6`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180002fe7`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000300c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000302c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslExpandTrafficKeys(
        _DWORD *a1,
        const wchar_t *a2,
        BCRYPT_HASH_HANDLE *a3,
        __int64 a4,
        __int64 a5)
{
  const wchar_t *v5; // rdi
  BCRYPT_HASH_HANDLE *v7; // rsi
  UCHAR *v8; // r13
  ULONG v9; // r15d
  UCHAR *v10; // rbp
  __int64 v11; // rax
  unsigned int v12; // ebx
  ULONG v13; // esi
  const char *v14; // rbp
  const char *v15; // r14
  UCHAR *Heap; // rax
  int v17; // edx
  int v18; // r8d
  UCHAR *v19; // rax
  int v20; // edx
  int v21; // r8d
  NTSTATUS v22; // eax
  int v23; // edx
  int v24; // r8d
  __int64 v25; // rcx
  UCHAR *v26; // rax
  __int64 v27; // rcx
  UCHAR *v28; // rax
  int v30; // eax
  const wchar_t *v31; // rbp
  unsigned int i; // ebx
  __int64 *v33; // r14
  const wchar_t **v34; // rax
  unsigned int v35; // ecx
  int v36; // eax
  int v37; // eax
  BCRYPT_HASH_HANDLE phNewHash; // [rsp+40h] [rbp-48h] BYREF
  ULONG Size; // [rsp+90h] [rbp+8h]
  NTSTATUS v40; // [rsp+98h] [rbp+10h]
  UCHAR *v41; // [rsp+A0h] [rbp+18h]

  v5 = a2;
  LODWORD(a2) = 0;
  v7 = a3;
  if ( !a1 || *a1 < 0x310u || a1[1] != 1936944177 )
    a1 = 0;
  if ( !v5 || *(_DWORD *)v5 < 0x70u || *((_DWORD *)v5 + 1) != 1936944179 )
    v5 = 0;
  if ( !a3 || *(_DWORD *)a3 < 0x30u || *((_DWORD *)a3 + 1) != 1936944178 )
    v7 = 0;
  v8 = 0;
  Size = 0;
  v9 = 0;
  phNewHash = 0;
  v10 = 0;
  v41 = 0;
  if ( a1 )
  {
    if ( v5 )
    {
      v11 = *((_QWORD *)v5 + 2);
      if ( v11 )
      {
        if ( v7 )
        {
          v31 = *(const wchar_t **)(v11 + 136);
          if ( !v31 || !*v31 )
            v31 = L"SHA256";
          for ( i = 0; ; ++i )
          {
            if ( i >= g_dwHashInfoTotalCount )
              goto LABEL_64;
            v33 = &g_pHashInfo[i];
            v34 = (const wchar_t **)*v33;
            if ( *v33 )
            {
              a2 = *v34;
              if ( *v34 )
              {
                if ( !wcsnicmp(v31, a2, 0x40u) )
                  break;
              }
            }
          }
          _mm_lfence();
          if ( *v33 )
          {
            v35 = *(_DWORD *)(*v33 + 8);
            Size = v35;
            if ( v35 > 0xFF )
              goto LABEL_76;
          }
          else
          {
LABEL_64:
            v35 = 0;
          }
          if ( v35 == *((_DWORD *)v7 + 7) && (a4 || a5) )
          {
            if ( *((_DWORD *)v5 + 2) != 772 )
            {
              v12 = -2146893783;
              DebugTraceError(
                2148073513LL,
                "Status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                6140);
LABEL_74:
              v13 = Size;
              v10 = 0;
              goto LABEL_29;
            }
            v36 = *((_DWORD *)v5 + 27);
            if ( v36 == 2 )
            {
              v14 = "c hs traffic";
              v15 = "s hs traffic";
            }
            else
            {
              v37 = v36 - 1;
              if ( v37 )
              {
                if ( v37 != 2 )
                {
                  v12 = -2146893783;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_sDsd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      (_DWORD)a2,
                      (_DWORD)a3,
                      (unsigned int)"Status",
                      41,
                      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                      21);
                  }
                  goto LABEL_74;
                }
                v14 = "c ap traffic";
                v15 = "s ap traffic";
              }
              else
              {
                if ( a5 )
                {
                  v12 = -2146893785;
                  DebugTraceError(
                    2148073511LL,
                    "Status",
                    "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                    6150);
                  v13 = Size;
                  v10 = 0;
                  goto LABEL_29;
                }
                v15 = 0;
                v14 = "c e traffic";
              }
            }
            v9 = *((_DWORD *)v7 + 6);
            Heap = (UCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
            v8 = Heap;
            if ( !Heap )
            {
              v12 = -1073741801;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v17,
                  v18,
                  (unsigned int)"Status",
                  23,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                  34);
              }
              v13 = Size;
              v10 = 0;
              goto LABEL_29;
            }
            v40 = BCryptDuplicateHash(v7[2], &phNewHash, Heap, v9, 0);
            if ( v40 < 0 )
            {
              DebugTraceError(
                (unsigned int)v40,
                "Status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                6189);
              v13 = Size;
            }
            else
            {
              v13 = Size;
              v19 = (UCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, Size);
              v41 = v19;
              if ( !v19 )
              {
                v12 = -1073741801;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_sDsd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v20,
                    v21,
                    (unsigned int)"Status",
                    23,
                    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                    52);
                  v10 = 0;
                  goto LABEL_29;
                }
                goto LABEL_46;
              }
              v22 = BCryptFinishHash(phNewHash, v19, Size, 0);
              v40 = v22;
              if ( v22 < 0 )
              {
                DebugTraceError(
                  (unsigned int)v22,
                  "Status",
                  "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                  6206);
              }
              else
              {
                if ( !a4 || (v40 = TlsDeriveSecret(v5, v14, v41, (unsigned __int8)Size, 4, a4), v40 >= 0) )
                {
                  v10 = v41;
                  if ( a5 )
                  {
                    v30 = TlsDeriveSecret(v5, v15, v41, (unsigned __int8)Size, 4, a5);
                    v40 = v30;
                    if ( v30 >= 0 )
                    {
                      v12 = v30;
                      goto LABEL_29;
                    }
                    DebugTraceError(
                      (unsigned int)v30,
                      "Status",
                      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                      6240);
                  }
                  v12 = v40;
                  goto LABEL_29;
                }
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                {
                  v10 = v41;
                  v12 = v40;
                  goto LABEL_29;
                }
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v23,
                  v24,
                  (unsigned int)"Status",
                  v40,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                  81);
              }
            }
            v12 = v40;
LABEL_46:
            v10 = v41;
            goto LABEL_29;
          }
LABEL_76:
          v12 = -2146893785;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)a2,
              (_DWORD)a3,
              (unsigned int)"Status",
              39,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
              245);
          goto LABEL_74;
        }
      }
    }
  }
  v12 = -2146893786;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return v12;
  WPP_SF_sDsd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    0,
    (_DWORD)a3,
    (unsigned int)"Status",
    38,
    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
    232);
  v13 = 0;
LABEL_29:
  if ( phNewHash )
    BCryptDestroyHash(phNewHash);
  if ( v8 )
  {
    v25 = v9;
    v26 = v8;
    if ( v9 )
    {
      do
      {
        *v26++ = 0;
        --v25;
      }
      while ( v25 );
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  }
  if ( v10 )
  {
    v27 = v13;
    v28 = v10;
    if ( v13 )
    {
      do
      {
        *v28++ = 0;
        --v27;
      }
      while ( v27 );
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  }
  return v12;
}

```

## disassembly

```asm
0x1800029e0  push    rbp
0x1800029e2  push    rsi
0x1800029e3  push    rdi
0x1800029e4  push    r12
0x1800029e6  push    r13
0x1800029e8  push    r15
0x1800029ea  sub     rsp, 58h
0x1800029ee  mov     rdi, rdx
0x1800029f1  mov     r12, r9
0x1800029f4  xor     edx, edx
0x1800029f6  mov     rsi, r8
0x1800029f9  test    rcx, rcx
0x1800029fc  jz      short loc_180002A0F
0x1800029fe  cmp     dword ptr [rcx], 310h
0x180002a04  jb      short loc_180002A0F
0x180002a06  cmp     dword ptr [rcx+4], 73736C31h
0x180002a0d  jz      short loc_180002A12
0x180002a0f  mov     rcx, rdx
0x180002a12  test    rdi, rdi
0x180002a15  jz      short loc_180002A25
0x180002a17  cmp     dword ptr [rdi], 70h ; 'p'
0x180002a1a  jb      short loc_180002A25
0x180002a1c  cmp     dword ptr [rdi+4], 73736C33h
0x180002a23  jz      short loc_180002A28
0x180002a25  mov     rdi, rdx
0x180002a28  test    r8, r8
0x180002a2b  jz      short loc_180002A3D
0x180002a2d  cmp     dword ptr [r8], 30h ; '0'
0x180002a31  jb      short loc_180002A3D
0x180002a33  cmp     dword ptr [r8+4], 73736C32h
0x180002a3b  jz      short loc_180002A40
0x180002a3d  mov     rsi, rdx
0x180002a40  mov     [rsp+88h+arg_18], rbx
0x180002a48  mov     r13, rdx
0x180002a4b  mov     dword ptr [rsp+88h+Size], edx
0x180002a52  mov     r15d, edx
0x180002a55  mov     [rsp+88h+phNewHash], rdx
0x180002a5a  mov     rbp, rdx
0x180002a5d  mov     [rsp+88h+arg_10], rdx
0x180002a65  test    rcx, rcx
0x180002a68  jz      short loc_180002A81
0x180002a6a  test    rdi, rdi
0x180002a6d  jz      short loc_180002A81
0x180002a6f  mov     rax, [rdi+10h]
0x180002a73  test    rax, rax
0x180002a76  jz      short loc_180002A81
0x180002a78  test    rsi, rsi
0x180002a7b  jnz     loc_180002DE0
0x180002a81  mov     ebx, 80090026h
0x180002a86  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a8d  lea     rax, WPP_GLOBAL_Control
0x180002a94  cmp     rcx, rax
0x180002a97  jz      loc_180002C68
0x180002a9d  test    byte ptr [rcx+1Ch], 1
0x180002aa1  jz      loc_180002C68
0x180002aa7  mov     rcx, [rcx+10h]
0x180002aab  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002ab2  mov     [rsp+88h+var_58], 17E8h
0x180002aba  lea     r9, aStatus; "Status"
0x180002ac1  mov     [rsp+88h+var_60], rax
0x180002ac6  mov     [rsp+88h+dwFlags], 80090026h
0x180002ace  call    WPP_SF_sDsd
0x180002ad3  mov     esi, dword ptr [rsp+88h+Size]
0x180002ada  jmp     loc_180002BEE
0x180002adf  lea     rbp, aCHsTraffic; "c hs traffic"
0x180002ae6  lea     r14, aSHsTraffic; "s hs traffic"
0x180002aed  mov     rcx, gs:60h
0x180002af6  xor     edx, edx; Flags
0x180002af8  mov     r15d, [rsi+18h]
0x180002afc  mov     r8d, r15d; Size
0x180002aff  mov     rcx, [rcx+30h]; HeapHandle
0x180002b03  call    cs:__imp_RtlAllocateHeap
0x180002b09  mov     r13, rax
0x180002b0c  test    rax, rax
0x180002b0f  jz      loc_180002D13
0x180002b15  mov     rcx, [rsi+10h]; hHash
0x180002b19  lea     rdx, [rsp+88h+phNewHash]; phNewHash
0x180002b1e  mov     r9d, r15d; cbHashObject
0x180002b21  mov     [rsp+88h+dwFlags], 0; dwFlags
0x180002b29  mov     r8, rax; pbHashObject
0x180002b2c  call    cs:__imp_BCryptDuplicateHash
0x180002b32  mov     [rsp+88h+arg_8], eax
0x180002b39  mov     ecx, eax
0x180002b3b  test    eax, eax
0x180002b3d  js      loc_180002FE1
0x180002b43  mov     rcx, gs:60h
0x180002b4c  xor     edx, edx; Flags
0x180002b4e  mov     esi, dword ptr [rsp+88h+Size]
0x180002b55  mov     r8d, esi; Size
0x180002b58  mov     rcx, [rcx+30h]; HeapHandle
0x180002b5c  call    cs:__imp_RtlAllocateHeap
0x180002b62  mov     [rsp+88h+arg_10], rax
0x180002b6a  test    rax, rax
0x180002b6d  jz      loc_180002D81
0x180002b73  mov     rcx, [rsp+88h+phNewHash]; hHash
0x180002b78  xor     r9d, r9d; dwFlags
0x180002b7b  mov     r8d, esi; cbOutput
0x180002b7e  mov     rdx, rax; pbOutput
0x180002b81  call    cs:__imp_BCryptFinishHash
0x180002b87  mov     [rsp+88h+arg_8], eax
0x180002b8e  test    eax, eax
0x180002b90  js      loc_180003006
0x180002b96  test    r12, r12
0x180002b99  jz      short loc_180002BD1
0x180002b9b  mov     r8, [rsp+88h+arg_10]
0x180002ba3  movzx   r9d, sil
0x180002ba7  mov     [rsp+88h+var_60], r12
0x180002bac  mov     rdx, rbp
0x180002baf  mov     rcx, rdi
0x180002bb2  mov     [rsp+88h+dwFlags], 4
0x180002bba  call    TlsDeriveSecret
0x180002bbf  mov     [rsp+88h+arg_8], eax
0x180002bc6  mov     r10d, eax
0x180002bc9  test    eax, eax
0x180002bcb  js      loc_180002CB5
0x180002bd1  mov     rbp, [rsp+88h+arg_10]
0x180002bd9  test    rbx, rbx
0x180002bdc  jnz     loc_180002C80
0x180002be2  mov     ebx, [rsp+88h+arg_8]
0x180002be9  mov     r14, [rsp+88h+var_38]
0x180002bee  mov     rcx, [rsp+88h+phNewHash]; hHash
0x180002bf3  test    rcx, rcx
0x180002bf6  jz      short loc_180002BFE
0x180002bf8  call    cs:__imp_BCryptDestroyHash
0x180002bfe  test    r13, r13
0x180002c01  jz      short loc_180002C35
0x180002c03  mov     ecx, r15d
0x180002c06  mov     rax, r13
0x180002c09  test    r15d, r15d
0x180002c0c  jz      short loc_180002C1D
0x180002c0e  xchg    ax, ax
0x180002c10  mov     byte ptr [rax], 0
0x180002c13  lea     rax, [rax+1]
0x180002c17  sub     rcx, 1
0x180002c1b  jnz     short loc_180002C10
0x180002c1d  mov     rcx, gs:60h
0x180002c26  mov     r8, r13; P
0x180002c29  xor     edx, edx; Flags
0x180002c2b  mov     rcx, [rcx+30h]; HeapHandle
0x180002c2f  call    cs:__imp_RtlFreeHeap
0x180002c35  test    rbp, rbp
0x180002c38  jz      short loc_180002C68
0x180002c3a  mov     ecx, esi
0x180002c3c  mov     rax, rbp
0x180002c3f  test    esi, esi
0x180002c41  jz      short loc_180002C50
0x180002c43  mov     byte ptr [rax], 0
0x180002c46  lea     rax, [rax+1]
0x180002c4a  sub     rcx, 1
0x180002c4e  jnz     short loc_180002C43
0x180002c50  mov     rcx, gs:60h
0x180002c59  mov     r8, rbp; P
0x180002c5c  xor     edx, edx; Flags
0x180002c5e  mov     rcx, [rcx+30h]; HeapHandle
0x180002c62  call    cs:__imp_RtlFreeHeap
0x180002c68  mov     eax, ebx
0x180002c6a  mov     rbx, [rsp+88h+arg_18]
0x180002c72  add     rsp, 58h
0x180002c76  pop     r15
0x180002c78  pop     r13
0x180002c7a  pop     r12
0x180002c7c  pop     rdi
0x180002c7d  pop     rsi
0x180002c7e  pop     rbp
0x180002c7f  retn
0x180002c80  movzx   r9d, sil
0x180002c84  mov     [rsp+88h+var_60], rbx
0x180002c89  mov     r8, rbp
0x180002c8c  mov     [rsp+88h+dwFlags], 4
0x180002c94  mov     rdx, r14
0x180002c97  mov     rcx, rdi
0x180002c9a  call    TlsDeriveSecret
0x180002c9f  mov     [rsp+88h+arg_8], eax
0x180002ca6  test    eax, eax
0x180002ca8  js      loc_180003026
0x180002cae  mov     ebx, eax
0x180002cb0  jmp     loc_180002BE9
0x180002cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cbc  lea     rax, WPP_GLOBAL_Control
0x180002cc3  cmp     rcx, rax
0x180002cc6  jz      loc_180002D71
0x180002ccc  test    byte ptr [rcx+1Ch], 1
0x180002cd0  jz      loc_180002D71
0x180002cd6  mov     rcx, [rcx+10h]
0x180002cda  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002ce1  mov     [rsp+88h+var_58], 1851h
0x180002ce9  lea     r9, aStatus; "Status"
0x180002cf0  mov     [rsp+88h+var_60], rax
0x180002cf5  mov     [rsp+88h+dwFlags], r10d
0x180002cfa  call    WPP_SF_sDsd
0x180002cff  mov     ebx, [rsp+88h+arg_8]
0x180002d06  mov     rbp, [rsp+88h+arg_10]
0x180002d0e  jmp     loc_180002BE9
0x180002d13  mov     ebx, 0C0000017h
0x180002d18  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d1f  lea     rax, WPP_GLOBAL_Control
0x180002d26  cmp     rcx, rax
0x180002d29  jz      short loc_180002D5D
0x180002d2b  test    byte ptr [rcx+1Ch], 1
0x180002d2f  jz      short loc_180002D5D
0x180002d31  mov     rcx, [rcx+10h]
0x180002d35  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002d3c  mov     [rsp+88h+var_58], 1822h
0x180002d44  lea     r9, aStatus; "Status"
0x180002d4b  mov     [rsp+88h+var_60], rax
0x180002d50  mov     [rsp+88h+dwFlags], 0C0000017h
0x180002d58  call    WPP_SF_sDsd
0x180002d5d  mov     esi, dword ptr [rsp+88h+Size]
0x180002d64  mov     rbp, [rsp+88h+arg_10]
0x180002d6c  jmp     loc_180002BE9
0x180002d71  mov     rbp, [rsp+88h+arg_10]
0x180002d79  mov     ebx, r10d
0x180002d7c  jmp     loc_180002BE9
0x180002d81  mov     ebx, 0C0000017h
0x180002d86  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d8d  lea     rax, WPP_GLOBAL_Control
0x180002d94  cmp     rcx, rax
0x180002d97  jz      loc_180002D06
0x180002d9d  test    byte ptr [rcx+1Ch], 1
0x180002da1  jz      loc_180002D06
0x180002da7  mov     rcx, [rcx+10h]
0x180002dab  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002db2  mov     [rsp+88h+var_58], 1834h
0x180002dba  lea     r9, aStatus; "Status"
0x180002dc1  mov     [rsp+88h+var_60], rax
0x180002dc6  mov     [rsp+88h+dwFlags], 0C0000017h
0x180002dce  call    WPP_SF_sDsd
0x180002dd3  mov     rbp, [rsp+88h+arg_10]
0x180002ddb  jmp     loc_180002BE9
0x180002de0  mov     rbp, [rax+88h]
0x180002de7  test    rbp, rbp
0x180002dea  jz      loc_180002F5D
0x180002df0  cmp     [rbp+0], dx
0x180002df4  jz      loc_180002F5D
0x180002dfa  mov     ebx, edx
0x180002dfc  mov     [rsp+88h+var_38], r14
0x180002e01  lea     rcx, g_pHashInfo
0x180002e08  cmp     ebx, cs:g_dwHashInfoTotalCount
0x180002e0e  jnb     short loc_180002E53
0x180002e10  mov     eax, ebx
0x180002e12  lea     r14, [rcx+rax*8]
0x180002e16  mov     rax, [rcx+rax*8]
0x180002e1a  test    rax, rax
0x180002e1d  jz      short loc_180002E40
0x180002e1f  mov     rdx, [rax]; String2
0x180002e22  test    rdx, rdx
0x180002e25  jz      short loc_180002E40
0x180002e27  mov     r8d, 40h ; '@'; MaxCount
0x180002e2d  mov     rcx, rbp; String1
0x180002e30  call    _wcsnicmp
0x180002e35  test    eax, eax
0x180002e37  jz      short loc_180002E44
0x180002e39  lea     rcx, g_pHashInfo
0x180002e40  inc     ebx
0x180002e42  jmp     short loc_180002E08
0x180002e44  lfence
0x180002e47  mov     rax, [r14]
0x180002e4a  test    rax, rax
0x180002e4d  jnz     loc_180002EF8
0x180002e53  mov     ecx, dword ptr [rsp+88h+Size]
0x180002e5a  cmp     ecx, [rsi+1Ch]
0x180002e5d  jnz     loc_180002F0E
0x180002e63  mov     rbx, [rsp+88h+arg_20]
0x180002e6b  test    r12, r12
0x180002e6e  jz      loc_180002F69
0x180002e74  cmp     dword ptr [rdi+8], 304h
0x180002e7b  jnz     loc_180002F73
0x180002e81  mov     eax, [rdi+6Ch]
0x180002e84  cmp     eax, 2
0x180002e87  jz      loc_180002ADF
0x180002e8d  sub     eax, 1
0x180002e90  jz      loc_180002F9B
0x180002e96  cmp     eax, 2
0x180002e99  jz      loc_180002F4A
0x180002e9f  mov     ebx, 80090029h
0x180002ea4  mov     rcx, cs:WPP_GLOBAL_Control
0x180002eab  lea     rax, WPP_GLOBAL_Control
0x180002eb2  cmp     rcx, rax
0x180002eb5  jz      short loc_180002EE9
0x180002eb7  test    byte ptr [rcx+1Ch], 1
0x180002ebb  jz      short loc_180002EE9
0x180002ebd  mov     [rsp+88h+var_58], 1815h
0x180002ec5  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002ecc  mov     [rsp+88h+var_60], rax
0x180002ed1  mov     [rsp+88h+dwFlags], 80090029h
0x180002ed9  mov     rcx, [rcx+10h]
0x180002edd  lea     r9, aStatus; "Status"
0x180002ee4  call    WPP_SF_sDsd
0x180002ee9  mov     esi, dword ptr [rsp+88h+Size]
0x180002ef0  mov     rbp, r13
0x180002ef3  jmp     loc_180002BE9
0x180002ef8  mov     ecx, [rax+8]
0x180002efb  mov     dword ptr [rsp+88h+Size], ecx
0x180002f02  cmp     ecx, 0FFh
0x180002f08  jbe     loc_180002E5A
0x180002f0e  mov     ebx, 80090027h
0x180002f13  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f1a  lea     rax, WPP_GLOBAL_Control
0x180002f21  cmp     rcx, rax
0x180002f24  jz      short loc_180002EE9
  ... truncated ...
```
