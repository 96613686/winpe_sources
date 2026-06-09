# VolumeCache::GetVolume(ushort const *)

- ea: `0x18001e2e0`
- end: `0x18001e7b9`
- name: `?GetVolume@VolumeCache@@QEAA?AV?$GenericStringHandle@G@@PEBG@Z`
- size: `1241`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001e234`

## callees

- `0x180006640`
- `0x18001e2e0`
- `0x180034170`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a3444`
- `0x1800ab7fc`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e3d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e614`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e3d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e614`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e353`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e353`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e795`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e795`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001e4f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001e6d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001e4f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001e6d1`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001e3cb`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001e3cb`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18001e60a`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18001e60a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall VolumeCache::GetVolume(__int64 *a1, _QWORD *a2, const WCHAR *a3)
{
  __int64 v5; // r12
  volatile signed __int32 *v6; // r15
  WCHAR *v7; // rdi
  DWORD FullPathNameW; // r14d
  signed int LastError; // ebx
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rbx
  __int64 v13; // r8
  char *v14; // rax
  signed __int64 v15; // rdi
  int v16; // ecx
  int v17; // edx
  _QWORD *v18; // rbx
  __int64 v19; // r14
  __int64 v20; // rbx
  volatile signed __int32 *v21; // rdi
  signed int v22; // ebx
  __int64 v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rcx
  __int64 v26; // rbx
  __int64 v27; // rcx
  __int64 v28; // rcx
  LPWSTR FilePart; // [rsp+20h] [rbp-69h] BYREF
  void **pExceptionObject; // [rsp+30h] [rbp-59h] BYREF
  __int128 v32; // [rsp+38h] [rbp-51h]
  int v33; // [rsp+48h] [rbp-41h]
  int v34; // [rsp+4Ch] [rbp-3Dh]
  int v35; // [rsp+50h] [rbp-39h]
  volatile signed __int32 *v36; // [rsp+98h] [rbp+Fh]
  char v37; // [rsp+A0h] [rbp+17h]
  __int64 v38; // [rsp+A8h] [rbp+1Fh]

  v5 = *a1;
  v38 = v5;
  if ( *(_BYTE *)(v5 + 40)
    && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v5);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)v5);
  v37 = 1;
  _InterlockedIncrement(&dword_180145058);
  v36 = (volatile signed __int32 *)&GenericStringHandle<unsigned short>::s_EmptyString;
  FilePart = 0;
  v6 = (volatile signed __int32 *)operator new(0x21Cu);
  *(_QWORD *)v6 = 262;
  *((_DWORD *)v6 + 2) = 1;
  v7 = (WCHAR *)(v6 + 3);
  *((_WORD *)v6 + 6) = 0;
  if ( _InterlockedExchangeAdd(&dword_180145058, 0xFFFFFFFF) == 1 )
    operator delete(&GenericStringHandle<unsigned short>::s_EmptyString, 0x10u);
  v36 = v6;
  FullPathNameW = GetFullPathNameW(a3, 0x105u, v7, &FilePart);
  if ( !FullPathNameW )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids,
        (unsigned int)LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v32 = 0;
    pExceptionObject = &ComError::`vftable';
    v33 = LastError;
    v34 = 0;
    v35 = 1;
    throw (ComError *)&pExceptionObject;
  }
  if ( FullPathNameW > 0x105 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids);
    v32 = 0;
    pExceptionObject = &ComError::`vftable';
    v33 = -2147024774;
    v34 = 119;
    v35 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v10 = -1;
  do
    ++v10;
  while ( v7[v10] );
  *(_QWORD *)v6 = v10;
  if ( FilePart )
    *FilePart = 0;
  v11 = *a1;
  if ( !**(_QWORD **)(v11 + 56) )
    goto LABEL_32;
  v12 = *(_QWORD *)(v11 + 48);
  if ( GetTickCount64() - v12 >= 0x2710 )
    goto LABEL_32;
  v13 = *a1;
  v14 = (char *)(*(_QWORD *)(*a1 + 56) + 12LL);
  v15 = (char *)v7 - v14;
  do
  {
    v16 = *(unsigned __int16 *)&v14[v15];
    v17 = *(unsigned __int16 *)v14 - v16;
    if ( v17 )
      break;
    v14 += 2;
  }
  while ( v16 );
  if ( v17 )
  {
LABEL_32:
    _InterlockedIncrement(&dword_180145058);
    v19 = FullPathNameW + 1;
    v20 = v19 + 1;
    if ( v19 + 1 < (unsigned __int64)(unsigned int)v19 )
    {
      v32 = 0;
      pExceptionObject = &ComError::`vftable';
      v33 = -2147024809;
      v34 = 1071;
      v35 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v21 = (volatile signed __int32 *)operator new(2 * v20 + 16);
    *(_QWORD *)v21 = v20;
    *((_DWORD *)v21 + 2) = 1;
    *((_WORD *)v21 + 6) = 0;
    if ( _InterlockedExchangeAdd(&dword_180145058, 0xFFFFFFFF) == 1 )
      operator delete(&GenericStringHandle<unsigned short>::s_EmptyString, 0x10u);
    if ( !GetVolumePathNameW(a3, (LPWSTR)v21 + 6, v19) )
    {
      v22 = GetLastError();
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          &WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids,
          (unsigned int)v22);
      if ( v22 > 0 )
        v22 = (unsigned __int16)v22 | 0x80070000;
      v32 = 0;
      pExceptionObject = &ComError::`vftable';
      v33 = v22;
      v34 = 0;
      v35 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v23 = -1;
    do
      ++v23;
    while ( *((_WORD *)v21 + v23 + 6) );
    *(_QWORD *)v21 = v23;
    v24 = *a1;
    _InterlockedIncrement(v21 + 2);
    v25 = *(_QWORD *)(v24 + 64);
    if ( v25 && _InterlockedExchangeAdd((volatile signed __int32 *)(v25 + 8), 0xFFFFFFFF) == 1 )
      operator delete(*(void **)(v24 + 64), 0x10u);
    *(_QWORD *)(v24 + 64) = v21;
    *(_QWORD *)(*a1 + 48) = GetTickCount64();
    v26 = *a1;
    _InterlockedIncrement(v6 + 2);
    v27 = *(_QWORD *)(v26 + 56);
    if ( v27 && _InterlockedExchangeAdd((volatile signed __int32 *)(v27 + 8), 0xFFFFFFFF) == 1 )
      operator delete(*(void **)(v26 + 56), 0x10u);
    *(_QWORD *)(v26 + 56) = v6;
    v28 = *a1;
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*a1 + 64) + 8LL));
    v18 = a2;
    *a2 = *(_QWORD *)(v28 + 64);
    if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
      operator delete((void *)v21, 0x10u);
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
      operator delete((void *)v6, 0x10u);
    if ( *(_BYTE *)(v5 + 40)
      && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v5);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)v5);
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v13 + 64) + 8LL));
    v18 = a2;
    *a2 = *(_QWORD *)(v13 + 64);
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
      operator delete((void *)v6, 0x10u);
    CCritSec2::leave((CCritSec2 *)v5);
  }
  return v18;
}

```

## disassembly

```asm
0x18001e2e0  mov     [rsp-8+arg_10], rbx
0x18001e2e5  mov     [rsp-8+arg_8], rdx
0x18001e2ea  mov     [rsp-8+arg_0], rcx
0x18001e2ef  push    rbp
0x18001e2f0  push    rsi
0x18001e2f1  push    rdi
0x18001e2f2  push    r12
0x18001e2f4  push    r13
0x18001e2f6  push    r14
0x18001e2f8  push    r15
0x18001e2fa  lea     rbp, [rsp-27h]
0x18001e2ff  sub     rsp, 0B0h
0x18001e306  mov     r13, r8
0x18001e309  mov     rbx, rcx
0x18001e30c  xor     esi, esi
0x18001e30e  mov     r12, [rcx]
0x18001e311  mov     [rbp+57h+var_38], r12
0x18001e315  lea     rax, WPP_GLOBAL_Control
0x18001e31c  cmp     [r12+28h], sil
0x18001e321  jz      short loc_18001E350
0x18001e323  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e32a  cmp     rcx, rax
0x18001e32d  jz      short loc_18001E350
0x18001e32f  test    dword ptr [rcx+1Ch], 100h
0x18001e336  jz      short loc_18001E350
0x18001e338  mov     edx, 0Fh
0x18001e33d  mov     r9, r12
0x18001e340  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x18001e347  mov     rcx, [rcx+10h]
0x18001e34b  call    WPP_SF_q
0x18001e350  mov     rcx, r12; lpCriticalSection
0x18001e353  call    cs:__imp_EnterCriticalSection
0x18001e359  mov     [rbp+57h+var_40], 1
0x18001e35d  lock inc cs:dword_180145058
0x18001e364  lea     r14, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x18001e36b  mov     [rbp+57h+var_48], r14
0x18001e36f  mov     [rbp+57h+FilePart], rsi
0x18001e373  mov     ecx, 21Ch; dwBytes
0x18001e378  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e37d  mov     r15, rax
0x18001e380  mov     qword ptr [rax], 106h
0x18001e387  mov     dword ptr [rax+8], 1
0x18001e38e  lea     rdi, [rax+0Ch]
0x18001e392  mov     [rdi], si
0x18001e395  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18001e39c  mov     ecx, esi
0x18001e39e  lock xadd cs:dword_180145058, ecx
0x18001e3a6  cmp     ecx, 1
0x18001e3a9  jnz     short loc_18001E3B8
0x18001e3ab  mov     edx, 10h; unsigned __int64
0x18001e3b0  mov     rcx, r14; void *
0x18001e3b3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e3b8  mov     [rbp+57h+var_48], r15
0x18001e3bc  lea     r9, [rbp+57h+FilePart]; lpFilePart
0x18001e3c0  mov     r8, rdi; lpBuffer
0x18001e3c3  mov     edx, 105h; nBufferLength
0x18001e3c8  mov     rcx, r13; lpFileName
0x18001e3cb  call    cs:__imp_GetFullPathNameW
0x18001e3d1  mov     r14d, eax
0x18001e3d4  test    eax, eax
0x18001e3d6  jnz     short loc_18001E452
0x18001e3d8  call    cs:__imp_GetLastError
0x18001e3de  mov     ebx, eax
0x18001e3e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e3e7  lea     rax, WPP_GLOBAL_Control
0x18001e3ee  cmp     rcx, rax
0x18001e3f1  jz      short loc_18001E411
0x18001e3f3  test    byte ptr [rcx+1Ch], 4
0x18001e3f7  jz      short loc_18001E411
0x18001e3f9  mov     edx, 0Ah
0x18001e3fe  mov     r9d, ebx
0x18001e401  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x18001e408  mov     rcx, [rcx+10h]
0x18001e40c  call    WPP_SF_d
0x18001e411  test    ebx, ebx
0x18001e413  jle     short loc_18001E41E
0x18001e415  movzx   ebx, bx
0x18001e418  or      ebx, 80070000h
0x18001e41e  xorps   xmm0, xmm0
0x18001e421  movups  [rbp+57h+var_A8], xmm0
0x18001e425  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18001e42c  mov     [rbp+57h+pExceptionObject], rax
0x18001e430  mov     [rbp+57h+var_98], ebx
0x18001e433  mov     [rbp+57h+var_94], 0
0x18001e43a  mov     [rbp+57h+var_90], 1
0x18001e441  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001e448  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001e44c  call    _CxxThrowException_0
0x18001e452  cmp     r14d, 105h
0x18001e459  jbe     short loc_18001E4C1
0x18001e45b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e462  lea     rax, WPP_GLOBAL_Control
0x18001e469  cmp     rcx, rax
0x18001e46c  jz      short loc_18001E489
0x18001e46e  test    byte ptr [rcx+1Ch], 4
0x18001e472  jz      short loc_18001E489
0x18001e474  mov     edx, 0Bh
0x18001e479  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x18001e480  mov     rcx, [rcx+10h]
0x18001e484  call    WPP_SF_
0x18001e489  xorps   xmm0, xmm0
0x18001e48c  movups  [rbp+57h+var_A8], xmm0
0x18001e490  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18001e497  mov     [rbp+57h+pExceptionObject], rax
0x18001e49b  mov     [rbp+57h+var_98], 8007007Ah
0x18001e4a2  mov     [rbp+57h+var_94], 77h ; 'w'
0x18001e4a9  mov     [rbp+57h+var_90], 1
0x18001e4b0  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001e4b7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001e4bb  call    _CxxThrowException_0
0x18001e4c1  mov     rax, rsi
0x18001e4c4  inc     rax
0x18001e4c7  cmp     word ptr [rdi+rax*2], 0
0x18001e4cc  jnz     short loc_18001E4C4
0x18001e4ce  mov     [r15], rax
0x18001e4d1  mov     rcx, [rbp+57h+FilePart]
0x18001e4d5  test    rcx, rcx
0x18001e4d8  jz      short loc_18001E4DF
0x18001e4da  xor     eax, eax
0x18001e4dc  mov     [rcx], ax
0x18001e4df  mov     rbx, [rbx]
0x18001e4e2  mov     rax, [rbx+38h]
0x18001e4e6  cmp     qword ptr [rax], 0
0x18001e4ea  jbe     short loc_18001E563
0x18001e4ec  mov     rbx, [rbx+30h]
0x18001e4f0  call    cs:__imp_GetTickCount64
0x18001e4f6  sub     rax, rbx
0x18001e4f9  cmp     rax, 2710h
0x18001e4ff  jnb     short loc_18001E563
0x18001e501  mov     r8, [rbp+57h+arg_0]
0x18001e505  mov     r8, [r8]
0x18001e508  mov     rax, [r8+38h]
0x18001e50c  add     rax, 0Ch
0x18001e510  sub     rdi, rax
0x18001e513  movzx   edx, word ptr [rax]
0x18001e516  movzx   ecx, word ptr [rax+rdi]
0x18001e51a  sub     edx, ecx
0x18001e51c  jnz     short loc_18001E526
0x18001e51e  add     rax, 2
0x18001e522  test    ecx, ecx
0x18001e524  jnz     short loc_18001E513
0x18001e526  test    edx, edx
0x18001e528  jnz     short loc_18001E563
0x18001e52a  mov     rax, [r8+40h]
0x18001e52e  lock inc dword ptr [rax+8]
0x18001e532  mov     rax, [r8+40h]
0x18001e536  mov     rbx, [rbp+57h+arg_8]
0x18001e53a  mov     [rbx], rax
0x18001e53d  lock xadd [r15+8], esi
0x18001e543  cmp     esi, 1
0x18001e546  jnz     short loc_18001E556
0x18001e548  mov     edx, 10h; unsigned __int64
0x18001e54d  mov     rcx, r15; void *
0x18001e550  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e555  nop
0x18001e556  mov     rcx, r12; this
0x18001e559  call    ?leave@CCritSec2@@QEAAXXZ; CCritSec2::leave(void)
0x18001e55e  jmp     loc_18001E79B
0x18001e563  lock inc cs:dword_180145058
0x18001e56a  lea     rax, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x18001e571  mov     [rbp+57h+arg_18], rax
0x18001e575  inc     r14d
0x18001e578  mov     eax, r14d
0x18001e57b  lea     rbx, [r14+1]
0x18001e57f  cmp     rbx, rax
0x18001e582  jnb     short loc_18001E5BC
0x18001e584  xorps   xmm0, xmm0
0x18001e587  movups  [rbp+57h+var_A8], xmm0
0x18001e58b  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18001e592  mov     [rbp+57h+pExceptionObject], rax
0x18001e596  mov     [rbp+57h+var_98], 80070057h
0x18001e59d  mov     [rbp+57h+var_94], 42Fh
0x18001e5a4  mov     [rbp+57h+var_90], 1
0x18001e5ab  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001e5b2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001e5b6  call    _CxxThrowException_0
0x18001e5bc  lea     rcx, ds:10h[rbx*2]; dwBytes
0x18001e5c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e5c9  mov     rdi, rax
0x18001e5cc  mov     [rax], rbx
0x18001e5cf  mov     dword ptr [rax+8], 1
0x18001e5d6  xor     edx, edx
0x18001e5d8  mov     [rax+0Ch], dx
0x18001e5dc  mov     edx, esi
0x18001e5de  lock xadd cs:dword_180145058, edx
0x18001e5e6  cmp     edx, 1
0x18001e5e9  jnz     short loc_18001E5FC
0x18001e5eb  mov     edx, 10h; unsigned __int64
0x18001e5f0  lea     rcx, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; void *
0x18001e5f7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e5fc  mov     [rbp+57h+arg_18], rdi
0x18001e600  mov     r8d, r14d; cchBufferLength
0x18001e603  lea     rdx, [rdi+0Ch]; lpszVolumePathName
0x18001e607  mov     rcx, r13; lpszFileName
0x18001e60a  call    cs:__imp_GetVolumePathNameW
0x18001e610  test    eax, eax
0x18001e612  jnz     short loc_18001E68E
0x18001e614  call    cs:__imp_GetLastError
0x18001e61a  mov     ebx, eax
0x18001e61c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e623  lea     rax, WPP_GLOBAL_Control
0x18001e62a  cmp     rcx, rax
0x18001e62d  jz      short loc_18001E64D
0x18001e62f  test    byte ptr [rcx+1Ch], 4
0x18001e633  jz      short loc_18001E64D
0x18001e635  mov     edx, 0Ch
0x18001e63a  mov     r9d, ebx
0x18001e63d  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x18001e644  mov     rcx, [rcx+10h]
0x18001e648  call    WPP_SF_d
0x18001e64d  test    ebx, ebx
0x18001e64f  jle     short loc_18001E65A
0x18001e651  movzx   ebx, bx
0x18001e654  or      ebx, 80070000h
0x18001e65a  xorps   xmm0, xmm0
0x18001e65d  movups  [rbp+57h+var_A8], xmm0
0x18001e661  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18001e668  mov     [rbp+57h+pExceptionObject], rax
0x18001e66c  mov     [rbp+57h+var_98], ebx
0x18001e66f  mov     [rbp+57h+var_94], 0
0x18001e676  mov     [rbp+57h+var_90], 1
0x18001e67d  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001e684  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001e688  call    _CxxThrowException_0
0x18001e68e  mov     rax, rsi
0x18001e691  inc     rax
0x18001e694  cmp     word ptr [rdi+rax*2+0Ch], 0
0x18001e69a  jnz     short loc_18001E691
0x18001e69c  mov     [rdi], rax
0x18001e69f  mov     r14, [rbp+57h+arg_0]
0x18001e6a3  mov     rbx, [r14]
0x18001e6a6  lock inc dword ptr [rdi+8]
0x18001e6aa  mov     rcx, [rbx+40h]
0x18001e6ae  test    rcx, rcx
0x18001e6b1  jz      short loc_18001E6CD
0x18001e6b3  mov     eax, esi
0x18001e6b5  lock xadd [rcx+8], eax
0x18001e6ba  cmp     eax, 1
0x18001e6bd  jnz     short loc_18001E6CD
0x18001e6bf  mov     edx, 10h; unsigned __int64
0x18001e6c4  mov     rcx, [rbx+40h]; void *
0x18001e6c8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e6cd  mov     [rbx+40h], rdi
0x18001e6d1  call    cs:__imp_GetTickCount64
0x18001e6d7  mov     rcx, [r14]
0x18001e6da  mov     [rcx+30h], rax
0x18001e6de  mov     rbx, [r14]
0x18001e6e1  lock inc dword ptr [r15+8]
0x18001e6e6  mov     rcx, [rbx+38h]
0x18001e6ea  test    rcx, rcx
0x18001e6ed  jz      short loc_18001E709
0x18001e6ef  mov     eax, esi
0x18001e6f1  lock xadd [rcx+8], eax
0x18001e6f6  cmp     eax, 1
0x18001e6f9  jnz     short loc_18001E709
0x18001e6fb  mov     edx, 10h; unsigned __int64
0x18001e700  mov     rcx, [rbx+38h]; void *
0x18001e704  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e709  mov     [rbx+38h], r15
0x18001e70d  mov     rcx, [r14]
0x18001e710  mov     rax, [rcx+40h]
0x18001e714  lock inc dword ptr [rax+8]
0x18001e718  mov     rax, [rcx+40h]
0x18001e71c  mov     rbx, [rbp+57h+arg_8]
0x18001e720  mov     [rbx], rax
0x18001e723  mov     eax, esi
0x18001e725  lock xadd [rdi+8], eax
0x18001e72a  cmp     eax, 1
0x18001e72d  jnz     short loc_18001E73D
0x18001e72f  mov     edx, 10h; unsigned __int64
0x18001e734  mov     rcx, rdi; void *
0x18001e737  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e73c  nop
0x18001e73d  lock xadd [r15+8], esi
0x18001e743  cmp     esi, 1
0x18001e746  jnz     short loc_18001E756
0x18001e748  mov     edx, 10h; unsigned __int64
0x18001e74d  mov     rcx, r15; void *
0x18001e750  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e755  nop
0x18001e756  cmp     byte ptr [r12+28h], 0
0x18001e75c  jz      short loc_18001E792
0x18001e75e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e765  lea     rax, WPP_GLOBAL_Control
0x18001e76c  cmp     rcx, rax
0x18001e76f  jz      short loc_18001E792
0x18001e771  test    dword ptr [rcx+1Ch], 100h
0x18001e778  jz      short loc_18001E792
0x18001e77a  mov     edx, 10h
0x18001e77f  mov     r9, r12
0x18001e782  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x18001e789  mov     rcx, [rcx+10h]
0x18001e78d  call    WPP_SF_q
0x18001e792  mov     rcx, r12; lpCriticalSection
0x18001e795  call    cs:__imp_LeaveCriticalSection
0x18001e79b  mov     rax, rbx
0x18001e79e  mov     rbx, [rsp+0E0h+arg_10]
0x18001e7a6  add     rsp, 0B0h
0x18001e7ad  pop     r15
0x18001e7af  pop     r14
  ... truncated ...
```
