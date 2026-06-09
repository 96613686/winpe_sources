# TREE_HASH_TABLE::FindRecord(ushort const *,void * *)

- ea: `0x180002bb0`
- end: `0x18000314f`
- name: `?FindRecord@TREE_HASH_TABLE@@QEAAXPEBGPEAPEAX@Z`
- size: `1439`
- prototype: `void(TREE_HASH_TABLE *__hidden this, const unsigned __int16 *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180002b60`
- `0x180002bb0`
- `0x180003160`
- `0x180003550`
- `0x18002c476`
- `0x18002c48e`
- `0x18002c4c0`
- `0x18002d010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180002d80`
- `msvcrt!_wcsicmp` at `0x180002d80`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003019`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000301f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000301f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c97`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002e22`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002e22`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002f7c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002f7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f6e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f6e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180003079`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180003079`
- `bcrypt!BCryptCreateHash` at `0x1800030a4`
- `bcrypt!BCryptCreateHash` at `0x1800030a4`
- `bcrypt!BCryptFinishHash` at `0x1800030dc`
- `bcrypt!BCryptFinishHash` at `0x1800030dc`
- `bcrypt!BCryptHashData` at `0x1800030be`
- `bcrypt!BCryptHashData` at `0x1800030be`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800030f0`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800030f0`
- `bcrypt!BCryptDestroyHash` at `0x180003100`
- `bcrypt!BCryptDestroyHash` at `0x180003100`

## pseudocode

```c
void __fastcall TREE_HASH_TABLE::FindRecord(TREE_HASH_TABLE *this, unsigned __int16 *a2, void **a3)
{
  void **v3; // r12
  const wchar_t *v4; // r13
  TREE_HASH_TABLE *v5; // r15
  unsigned __int16 v6; // ax
  int i; // ebx
  unsigned __int16 *v8; // rcx
  signed __int32 v9; // edx
  unsigned int v10; // r14d
  DWORD v11; // edi
  DWORD CurrentThreadId; // eax
  __int64 v13; // rsi
  unsigned __int16 v14; // r8
  int v15; // ebx
  int v16; // edx
  signed __int32 v17; // r8d
  __int64 *j; // rbx
  const wchar_t *v19; // rcx
  signed __int64 v20; // r8
  int v21; // edx
  int v22; // eax
  signed __int32 v23; // edx
  __int64 v24; // rsi
  char v25; // r14
  UCHAR *v26; // rdi
  __int64 v27; // rax
  __int64 v29; // r15
  UCHAR *v30; // rbx
  __int16 v31; // cx
  unsigned int v32; // r12d
  HANDLE ProcessHeap; // rax
  UCHAR *v34; // rax
  UCHAR *v35; // rcx
  __int64 v36; // rdx
  UCHAR *v37; // rax
  __int128 v38; // xmm0
  signed int LastError; // eax
  bool v40; // sf
  ULONG v41; // esi
  unsigned __int64 v42; // rdx
  NTSTATUS v43; // ebx
  unsigned int v44; // r8d
  void *Src; // [rsp+48h] [rbp-C0h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-B8h] BYREF
  void **v47; // [rsp+58h] [rbp-B0h]
  TREE_HASH_TABLE *v48; // [rsp+60h] [rbp-A8h]
  _BYTE v49[32]; // [rsp+68h] [rbp-A0h] BYREF
  UCHAR *v50; // [rsp+88h] [rbp-80h]
  int v51; // [rsp+90h] [rbp-78h]
  __int16 v52; // [rsp+94h] [rbp-74h]
  unsigned int v53; // [rsp+98h] [rbp-70h]
  UCHAR pbOutput[16]; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v55; // [rsp+B0h] [rbp-58h]
  UCHAR pbInput[2]; // [rsp+C8h] [rbp-40h] BYREF
  char v57[526]; // [rsp+CAh] [rbp-3Eh] BYREF

  v47 = a3;
  v3 = a3;
  Src = a2;
  v4 = a2;
  v48 = this;
  v5 = this;
  *a3 = 0;
  if ( !a2 )
    return;
  if ( !*((_DWORD *)this + 6) )
  {
    v31 = *a2;
    for ( i = 0; *a2; v31 = *a2 )
    {
      ++a2;
      i = (v31 & 0xFFDF) + 101 * i;
    }
    goto LABEL_7;
  }
  if ( !*((_DWORD *)this + 7) )
  {
    v6 = *a2;
    i = 0;
    if ( *a2 )
    {
      v8 = a2;
      do
      {
        ++v8;
        i = v6 + 101 * i;
        v6 = *v8;
      }
      while ( *v8 );
    }
    goto LABEL_7;
  }
  memset_0(v57, 0, 0x206u);
  LODWORD(v24) = 0;
  v51 = 520;
  v25 = 0;
  v52 = 256;
  v53 = 0;
  v26 = pbInput;
  *(_WORD *)pbInput = 0;
  v27 = -1;
  v50 = pbInput;
  while ( v4[++v27] != 0 )
    ;
  v29 = (unsigned int)(2 * v27);
  if ( (unsigned __int64)(v29 + 2) <= 0x208 )
    goto LABEL_47;
  v32 = v29 + 128;
  if ( (unsigned __int64)(v29 + 128) > 0xFFFFFFFF )
  {
LABEL_33:
    BUFFER::~BUFFER((BUFFER *)v49);
    return;
  }
  if ( v32 > 0x208 )
  {
    ProcessHeap = GetProcessHeap();
    v34 = (UCHAR *)HeapAlloc(ProcessHeap, 0, v32);
    v30 = v34;
    if ( v34 )
    {
      v35 = v34;
      v36 = 4;
      v37 = pbInput;
      do
      {
        v35 += 128;
        v38 = *(_OWORD *)v37;
        v37 += 128;
        *((_OWORD *)v35 - 8) = v38;
        *((_OWORD *)v35 - 7) = *((_OWORD *)v37 - 7);
        *((_OWORD *)v35 - 6) = *((_OWORD *)v37 - 6);
        *((_OWORD *)v35 - 5) = *((_OWORD *)v37 - 5);
        *((_OWORD *)v35 - 4) = *((_OWORD *)v37 - 4);
        *((_OWORD *)v35 - 3) = *((_OWORD *)v37 - 3);
        *((_OWORD *)v35 - 2) = *((_OWORD *)v37 - 2);
        *((_OWORD *)v35 - 1) = *((_OWORD *)v37 - 1);
        --v36;
      }
      while ( v36 );
      v25 = 1;
      *(_QWORD *)v35 = *(_QWORD *)v37;
      v26 = v30;
      LOBYTE(v52) = 1;
      v50 = v30;
      v51 = v29 + 128;
      goto LABEL_48;
    }
    SetLastError(8u);
    LastError = GetLastError();
    v40 = LastError < 0;
    if ( LastError > 0 )
      v40 = 1;
    if ( !v40 )
    {
      v4 = (const wchar_t *)Src;
      goto LABEL_65;
    }
    goto LABEL_33;
  }
LABEL_47:
  v30 = pbInput;
LABEL_48:
  v4 = (const wchar_t *)Src;
  memcpy_0(v30, Src, (unsigned int)v29);
  v24 = (unsigned int)v29 >> 1;
  v53 = (unsigned int)v29 >> 1;
  *(_WORD *)&v30[2 * v24] = 0;
LABEL_65:
  Src = 0;
  phHash = 0;
  *(_OWORD *)pbOutput = 0;
  v55 = 0;
  if ( !v26 )
    goto LABEL_79;
  v41 = 2 * v24;
  if ( !v41 )
    goto LABEL_79;
  v43 = BCryptOpenAlgorithmProvider(&Src, L"SHA256", 0, 0);
  if ( v43 >= 0 )
  {
    v43 = BCryptCreateHash(Src, &phHash, 0, 0, 0, 0, 0);
    if ( v43 >= 0 )
    {
      v43 = BCryptHashData(phHash, v26, v41, 0);
      if ( v43 >= 0 )
        v43 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
    }
  }
  if ( Src )
    BCryptCloseAlgorithmProvider(Src, 0);
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v43 < 0 )
  {
LABEL_79:
    if ( v25 )
      BUFFER::FreeMemoryInternal((BUFFER *)v49);
    return;
  }
  i = HashBlob(pbOutput, v42, v44);
  if ( v25 )
    BUFFER::FreeMemoryInternal((BUFFER *)v49);
  v3 = v47;
  v5 = v48;
LABEL_7:
  v9 = *((_DWORD *)v5 + 8);
  v10 = (69069 * i + 1) & 0xFFFF0000 | ((unsigned int)(1103515245 * i + 12345) >> 16);
  if ( (v9 & 0xFFFF8000) != 0 || v9 != _InterlockedCompareExchange((volatile signed __int32 *)v5 + 8, v9 + 1, v9) )
  {
    v11 = 0;
    CurrentThreadId = GetCurrentThreadId();
    v13 = 0;
    v14 = CReaderWriterLock3::sm_wDefaultSpinCount;
    v15 = (int)((double)CReaderWriterLock3::sm_wDefaultSpinCount * *(double *)&qword_180030E80[CurrentThreadId % 0xD]);
LABEL_10:
    v16 = v15;
    if ( g_cProcessors < 2 || !v14 )
      v16 = 1;
    while ( 1 )
    {
      if ( --v16 < 0 )
      {
        if ( v11 || !g_pfnSwitchToThread() )
          Sleep(v11);
        if ( (unsigned int)v13 < 4 )
          v11 = dword_180030D30[v13];
        else
          v11 = 100;
        v15 = (int)((double)v15 * CReaderWriterLock3::sm_dblDfltSpinAdjFctr);
        if ( v15 > 10000 )
        {
          v14 = CReaderWriterLock3::sm_wDefaultSpinCount;
          v15 = 10000;
          v13 = (unsigned int)(v13 + 1);
        }
        else
        {
          if ( v15 <= 100 )
            v15 = 100;
          v14 = CReaderWriterLock3::sm_wDefaultSpinCount;
          v13 = (unsigned int)(v13 + 1);
        }
        goto LABEL_10;
      }
      v17 = *((_DWORD *)v5 + 8);
      if ( (v17 & 0xFFFF8000) == 0
        && v17 == _InterlockedCompareExchange((volatile signed __int32 *)v5 + 8, v17 + 1, v17) )
      {
        break;
      }
      _mm_pause();
    }
    v3 = v47;
  }
  for ( j = *(__int64 **)(*((_QWORD *)v5 + 1) + 8LL * (v10 % *((_DWORD *)v5 + 4))); j; j = (__int64 *)*j )
  {
    if ( *((_DWORD *)j + 12) == v10 )
    {
      v19 = (const wchar_t *)j[5];
      if ( *((_DWORD *)v5 + 6) )
      {
        v20 = (char *)v4 - (char *)v19;
        do
        {
          v21 = *(const wchar_t *)((char *)v19 + v20);
          v22 = *v19 - v21;
          if ( v22 )
            break;
          ++v19;
        }
        while ( v21 );
        if ( !v22 )
        {
LABEL_27:
          if ( j[4] )
          {
            (**(void (__fastcall ***)(TREE_HASH_TABLE *))v5)(v5);
            *v3 = (void *)j[4];
          }
          break;
        }
      }
      else if ( !_wcsicmp(v19, v4) )
      {
        goto LABEL_27;
      }
    }
    else if ( *((_DWORD *)j + 12) > v10 )
    {
      break;
    }
  }
  while ( 1 )
  {
    v23 = *((_DWORD *)v5 + 8);
    if ( v23 == _InterlockedCompareExchange((volatile signed __int32 *)v5 + 8, v23 - 1, v23) )
      break;
    _mm_pause();
  }
}

```

## disassembly

```asm
0x180002bb0  mov     r11, rsp
0x180002bb3  push    rbp
0x180002bb4  push    r12
0x180002bb6  push    r13
0x180002bb8  push    r15
0x180002bba  lea     rbp, [r11-218h]
0x180002bc1  sub     rsp, 2F8h
0x180002bc8  mov     rax, cs:__security_cookie
0x180002bcf  xor     rax, rsp
0x180002bd2  mov     [rbp+210h+var_40], rax
0x180002bd9  mov     [rsp+310h+var_2C0], r8
0x180002bde  mov     r12, r8
0x180002be1  mov     [rsp+310h+Src], rdx
0x180002be6  mov     r13, rdx
0x180002be9  mov     [rsp+310h+var_2B8], rcx
0x180002bee  mov     r15, rcx
0x180002bf1  mov     qword ptr [r8], 0
0x180002bf8  test    rdx, rdx
0x180002bfb  jz      loc_180002DEE
0x180002c01  cmp     dword ptr [rcx+18h], 0
0x180002c05  mov     [r11+20h], rbx
0x180002c09  mov     [r11-28h], rsi
0x180002c0d  mov     [r11-30h], rdi
0x180002c11  mov     [r11-38h], r14
0x180002c15  jz      loc_180002F1D
0x180002c1b  cmp     dword ptr [rcx+1Ch], 0
0x180002c1f  jnz     loc_180002E6F
0x180002c25  movzx   eax, word ptr [rdx]
0x180002c28  xor     ebx, ebx
0x180002c2a  test    ax, ax
0x180002c2d  jz      short loc_180002C54
0x180002c2f  mov     rcx, rdx
0x180002c32  nop     dword ptr [rax+00h]
0x180002c36  nop     word ptr [rax+rax+00000000h]
0x180002c40  imul    ebx, 65h ; 'e'
0x180002c43  lea     rcx, [rcx+2]
0x180002c47  movzx   eax, ax
0x180002c4a  add     ebx, eax
0x180002c4c  movzx   eax, word ptr [rcx]
0x180002c4f  test    ax, ax
0x180002c52  jnz     short loc_180002C40
0x180002c54  mov     edx, [r15+20h]
0x180002c58  imul    r14d, ebx, 41C64E6Dh
0x180002c5f  imul    eax, ebx, 10DCDh
0x180002c65  add     r14d, 3039h
0x180002c6c  inc     eax
0x180002c6e  shr     r14d, 10h
0x180002c72  and     eax, 0FFFF0000h
0x180002c77  or      r14d, eax
0x180002c7a  test    edx, 0FFFF8000h
0x180002c80  jnz     short loc_180002C95
0x180002c82  lea     ecx, [rdx+1]
0x180002c85  mov     eax, edx
0x180002c87  lock cmpxchg [r15+20h], ecx
0x180002c8d  cmp     edx, eax
0x180002c8f  jz      loc_180002D2C
0x180002c95  xor     edi, edi
0x180002c97  call    cs:__imp_GetCurrentThreadId
0x180002c9d  mov     r8d, eax
0x180002ca0  lea     r12, __ImageBase
0x180002ca7  mov     eax, 4EC4EC4Fh
0x180002cac  mul     r8d
0x180002caf  shr     edx, 2
0x180002cb2  imul    ecx, edx, 0Dh
0x180002cb5  lea     rdx, __ImageBase
0x180002cbc  sub     r8d, ecx
0x180002cbf  mov     ecx, r8d
0x180002cc2  xor     esi, esi
0x180002cc4  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x180002ccc  movd    xmm0, r8d
0x180002cd1  cvtdq2pd xmm0, xmm0
0x180002cd5  mulsd   xmm0, ds:rva qword_180030E80[rdx+rcx*8]
0x180002cde  cvttsd2si ebx, xmm0
0x180002ce2  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x180002ce9  mov     edx, ebx
0x180002ceb  jb      loc_18000300A
0x180002cf1  test    r8w, r8w
0x180002cf5  jz      loc_18000300A
0x180002cfb  sub     edx, 1
0x180002cfe  js      loc_180002E0C
0x180002d04  mov     r8d, [r15+20h]
0x180002d08  test    r8d, 0FFFF8000h
0x180002d0f  jnz     short loc_180002D23
0x180002d11  lea     ecx, [r8+1]
0x180002d15  mov     eax, r8d
0x180002d18  lock cmpxchg [r15+20h], ecx
0x180002d1e  cmp     r8d, eax
0x180002d21  jz      short loc_180002D27
0x180002d23  pause
0x180002d25  jmp     short loc_180002CFB
0x180002d27  mov     r12, [rsp+310h+var_2C0]
0x180002d2c  xor     edx, edx
0x180002d2e  mov     eax, r14d
0x180002d31  div     dword ptr [r15+10h]
0x180002d35  mov     rax, [r15+8]
0x180002d39  mov     rbx, [rax+rdx*8]
0x180002d3d  nop     dword ptr [rax]
0x180002d40  test    rbx, rbx
0x180002d43  jz      short loc_180002DA9
0x180002d45  cmp     [rbx+30h], r14d
0x180002d49  jnz     short loc_180002DC0
0x180002d4b  cmp     dword ptr [r15+18h], 0
0x180002d50  mov     rcx, [rbx+28h]; String1
0x180002d54  jz      short loc_180002D7D
0x180002d56  mov     r8, r13
0x180002d59  sub     r8, rcx
0x180002d5c  nop     dword ptr [rax+00h]
0x180002d60  movzx   eax, word ptr [rcx]
0x180002d63  movzx   edx, word ptr [rcx+r8]
0x180002d68  sub     eax, edx
0x180002d6a  jnz     short loc_180002D74
0x180002d6c  add     rcx, 2
0x180002d70  test    edx, edx
0x180002d72  jnz     short loc_180002D60
0x180002d74  test    eax, eax
0x180002d76  jz      short loc_180002D8A
0x180002d78  mov     rbx, [rbx]
0x180002d7b  jmp     short loc_180002D40
0x180002d7d  mov     rdx, r13; String2
0x180002d80  call    cs:__imp__wcsicmp
0x180002d86  test    eax, eax
0x180002d88  jnz     short loc_180002D78
0x180002d8a  mov     rdx, [rbx+20h]
0x180002d8e  test    rdx, rdx
0x180002d91  jz      short loc_180002DA9
0x180002d93  mov     rax, [r15]
0x180002d96  mov     rcx, r15
0x180002d99  mov     rax, [rax]
0x180002d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002da1  mov     rax, [rbx+20h]
0x180002da5  mov     [r12], rax
0x180002da9  mov     edx, [r15+20h]
0x180002dad  mov     eax, edx
0x180002daf  lea     ecx, [rdx-1]
0x180002db2  lock cmpxchg [r15+20h], ecx
0x180002db8  cmp     edx, eax
0x180002dba  jz      short loc_180002DCE
0x180002dbc  pause
0x180002dbe  jmp     short loc_180002DA9
0x180002dc0  jbe     short loc_180002D78
0x180002dc2  jmp     short loc_180002DA9
0x180002dc4  lea     rcx, [rsp+310h+var_2B0]; this
0x180002dc9  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180002dce  mov     rdi, [rsp+310h+var_28]
0x180002dd6  mov     rsi, [rsp+2F0h]
0x180002dde  mov     rbx, [rsp+310h+arg_18]
0x180002de6  mov     r14, [rsp+310h+var_30]
0x180002dee  mov     rcx, [rbp+210h+var_40]
0x180002df5  xor     rcx, rsp; StackCookie
0x180002df8  call    __security_check_cookie
0x180002dfd  add     rsp, 2F8h
0x180002e04  pop     r15
0x180002e06  pop     r13
0x180002e08  pop     r12
0x180002e0a  pop     rbp
0x180002e0b  retn
0x180002e0c  test    edi, edi
0x180002e0e  jnz     short loc_180002E20
0x180002e10  mov     rax, cs:?g_pfnSwitchToThread@@3P6AHXZEA; int (*g_pfnSwitchToThread)(void)
0x180002e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e1c  test    eax, eax
0x180002e1e  jnz     short loc_180002E28
0x180002e20  mov     ecx, edi; dwMilliseconds
0x180002e22  call    cs:__imp_Sleep
0x180002e28  cmp     esi, 4
0x180002e2b  jb      loc_180002F10
0x180002e31  mov     edi, 64h ; 'd'
0x180002e36  movd    xmm0, ebx
0x180002e3a  cvtdq2pd xmm0, xmm0
0x180002e3e  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock3@@1NA; double CReaderWriterLock3::sm_dblDfltSpinAdjFctr
0x180002e46  cvttsd2si ebx, xmm0
0x180002e4a  cmp     ebx, 2710h
0x180002e50  jg      loc_180002EFC
0x180002e56  cmp     ebx, 64h ; 'd'
0x180002e59  jg      short loc_180002E60
0x180002e5b  mov     ebx, 64h ; 'd'
0x180002e60  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x180002e68  inc     esi
0x180002e6a  jmp     loc_180002CE2
0x180002e6f  xor     edx, edx; Val
0x180002e71  lea     rcx, [rbp+210h+var_24E]; void *
0x180002e75  mov     r8d, 206h; Size
0x180002e7b  call    memset_0
0x180002e80  xor     esi, esi
0x180002e82  mov     [rbp+210h+var_288], 208h
0x180002e89  xor     r14b, r14b
0x180002e8c  mov     [rbp+210h+var_284], 100h
0x180002e92  xor     eax, eax
0x180002e94  mov     [rbp+210h+var_280], esi
0x180002e97  lea     rdi, [rbp+210h+pbInput]
0x180002e9b  mov     word ptr [rbp+210h+pbInput], ax
0x180002e9f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180002ea6  mov     [rbp+210h+var_290], rdi
0x180002eaa  nop     word ptr [rax+rax+00h]
0x180002eb0  cmp     [r13+rax*2+2], si
0x180002eb6  lea     rax, [rax+1]
0x180002eba  jnz     short loc_180002EB0
0x180002ebc  lea     r15d, [rax+rax]
0x180002ec0  lea     rax, [r15+2]
0x180002ec4  mov     r13d, r15d
0x180002ec7  cmp     rax, 208h
0x180002ecd  ja      short loc_180002F4C
0x180002ecf  lea     rbx, [rbp+210h+pbInput]
0x180002ed3  mov     r8, r13; Size
0x180002ed6  mov     rcx, rbx; void *
0x180002ed9  mov     r13, [rsp+310h+Src]
0x180002ede  mov     rdx, r13; Src
0x180002ee1  call    memcpy_0
0x180002ee6  shr     r15d, 1
0x180002ee9  mov     esi, r15d
0x180002eec  xor     r15d, r15d
0x180002eef  mov     [rbp+210h+var_280], esi
0x180002ef2  mov     [rbx+rsi*2], r15w
0x180002ef7  jmp     loc_180003041
0x180002efc  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x180002f04  mov     ebx, 2710h
0x180002f09  inc     esi
0x180002f0b  jmp     loc_180002CE2
0x180002f10  mov     edi, ds:rva dword_180030D30[r12+rsi*4]
0x180002f18  jmp     loc_180002E36
0x180002f1d  movzx   ecx, word ptr [rdx]
0x180002f20  xor     ebx, ebx
0x180002f22  test    cx, cx
0x180002f25  jz      loc_180002C54
0x180002f2b  nop     dword ptr [rax+rax+00h]
0x180002f30  and     ecx, 0FFDFh
0x180002f36  imul    ebx, 65h ; 'e'
0x180002f39  lea     rdx, [rdx+2]
0x180002f3d  add     ebx, ecx
0x180002f3f  movzx   ecx, word ptr [rdx]
0x180002f42  test    cx, cx
0x180002f45  jnz     short loc_180002F30
0x180002f47  jmp     loc_180002C54
0x180002f4c  lea     r12, [r15+80h]
0x180002f53  mov     eax, 0FFFFFFFFh
0x180002f58  cmp     r12, rax
0x180002f5b  ja      loc_180002DC4
0x180002f61  cmp     r12d, 208h
0x180002f68  jbe     loc_180002ECF
0x180002f6e  call    cs:__imp_GetProcessHeap
0x180002f74  mov     r8d, r12d; dwBytes
0x180002f77  xor     edx, edx; dwFlags
0x180002f79  mov     rcx, rax; hHeap
0x180002f7c  call    cs:__imp_HeapAlloc
0x180002f82  mov     rbx, rax
0x180002f85  test    rax, rax
0x180002f88  jz      loc_180003014
0x180002f8e  mov     rcx, rax
0x180002f91  mov     edx, 4
0x180002f96  lea     rax, [rbp+210h+pbInput]
0x180002f9a  lea     rcx, [rcx+80h]
0x180002fa1  movups  xmm0, xmmword ptr [rax]
0x180002fa4  lea     rax, [rax+80h]
0x180002fab  movups  xmmword ptr [rcx-80h], xmm0
0x180002faf  movups  xmm1, xmmword ptr [rax-70h]
0x180002fb3  movups  xmmword ptr [rcx-70h], xmm1
0x180002fb7  movups  xmm0, xmmword ptr [rax-60h]
0x180002fbb  movups  xmmword ptr [rcx-60h], xmm0
0x180002fbf  movups  xmm1, xmmword ptr [rax-50h]
0x180002fc3  movups  xmmword ptr [rcx-50h], xmm1
0x180002fc7  movups  xmm0, xmmword ptr [rax-40h]
0x180002fcb  movups  xmmword ptr [rcx-40h], xmm0
0x180002fcf  movups  xmm1, xmmword ptr [rax-30h]
0x180002fd3  movups  xmmword ptr [rcx-30h], xmm1
0x180002fd7  movups  xmm0, xmmword ptr [rax-20h]
0x180002fdb  movups  xmmword ptr [rcx-20h], xmm0
0x180002fdf  movups  xmm1, xmmword ptr [rax-10h]
0x180002fe3  movups  xmmword ptr [rcx-10h], xmm1
0x180002fe7  sub     rdx, 1
0x180002feb  jnz     short loc_180002F9A
0x180002fed  mov     rax, [rax]
0x180002ff0  mov     r14b, 1
0x180002ff3  mov     [rcx], rax
0x180002ff6  mov     rdi, rbx
0x180002ff9  mov     byte ptr [rbp+210h+var_284], r14b
0x180002ffd  mov     [rbp+210h+var_290], rbx
0x180003001  mov     [rbp+210h+var_288], r12d
0x180003005  jmp     loc_180002ED3
0x18000300a  mov     edx, 1
0x18000300f  jmp     loc_180002CFB
0x180003014  mov     ecx, 8; dwErrCode
0x180003019  call    cs:__imp_SetLastError
0x18000301f  call    cs:__imp_GetLastError
0x180003025  test    eax, eax
0x180003027  jle     short loc_180003033
0x180003029  movzx   eax, ax
0x18000302c  or      eax, 80070000h
0x180003031  test    eax, eax
0x180003033  js      loc_180002DC4
0x180003039  mov     r13, [rsp+310h+Src]
0x18000303e  xor     r15d, r15d
0x180003041  mov     [rsp+310h+Src], r15
0x180003046  xorps   xmm0, xmm0
0x180003049  mov     [rsp+310h+phHash], r15
0x18000304e  movups  xmmword ptr [rbp+210h+pbOutput], xmm0
0x180003052  movups  [rbp+210h+var_268], xmm0
0x180003056  test    rdi, rdi
0x180003059  jz      loc_180003137
0x18000305f  add     esi, esi
0x180003061  jz      loc_180003137
  ... truncated ...
```
