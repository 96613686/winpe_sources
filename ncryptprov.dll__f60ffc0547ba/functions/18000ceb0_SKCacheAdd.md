# SKCacheAdd

- ea: `0x18000ceb0`
- end: `0x18000d3c1`
- name: `SKCacheAdd`
- size: `1297`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b340`
- `0x180014160`
- `0x180014c60`
- `0x18001a050`
- `0x180033a10`
- `0x18003568c`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x18000cd9c`
- `0x18000ceb0`
- `0x18000d3d0`
- `0x18000d3f4`
- `0x18000d7e0`
- `0x18000def0`
- `0x18002464c`
- `0x1800398cc`
- `0x180062310`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000d03d`
- `ntdll!RtlAllocateHeap` at `0x18000d03d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d2be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d2be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cf03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cf03`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000d20d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000d262`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000d20d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000d262`
- `CRYPTBASE!SystemFunction040` at `0x18000d201`
- `CRYPTBASE!SystemFunction040` at `0x18000d201`

## string_xrefs

- `0x18000cf67`: `onecore\ds\security\cryptoapi\ncrypt\storage\keycache.c`
- `0x18000d0b2`: `onecore\ds\security\cryptoapi\ncrypt\storage\keycache.c`
- `0x18000d2f8`: `onecore\ds\security\cryptoapi\ncrypt\storage\keycache.c`

## pseudocode

```c
__int64 __fastcall SKCacheAdd(__int64 a1)
{
  int v1; // r14d
  _OWORD *v2; // r13
  int v3; // edi
  __int64 v4; // rbx
  int v5; // r15d
  __int64 v6; // rsi
  int KeyInfo; // eax
  const char *v8; // r8
  const void *v9; // rbx
  _OWORD *v10; // rcx
  __int64 v11; // rax
  PVOID Heap; // rax
  _OWORD *v13; // rax
  int v14; // edx
  int v15; // r8d
  __int64 v16; // rdi
  int v17; // r12d
  __int64 v18; // r15
  __int64 v19; // rsi
  __int64 v20; // rax
  DWORD TickCount; // eax
  unsigned int v22; // edx
  int v23; // esi
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 *v27; // r14
  __int64 *v28; // rcx
  __int64 v29; // [rsp+40h] [rbp-99h]
  __int128 v31; // [rsp+50h] [rbp-89h] BYREF
  _OWORD v32[2]; // [rsp+60h] [rbp-79h] BYREF
  __int128 v33; // [rsp+80h] [rbp-59h]
  void *Buf2[2]; // [rsp+90h] [rbp-49h]
  __int128 v35; // [rsp+A0h] [rbp-39h]
  __int128 v36; // [rsp+B0h] [rbp-29h]
  __int128 v37; // [rsp+C0h] [rbp-19h]
  __int64 v38; // [rsp+D0h] [rbp-9h]

  v1 = 0;
  v2 = (_OWORD *)a1;
  v3 = 0;
  v4 = 0;
  if ( (*(_BYTE *)(a1 + 428) & 0x40) != 0 )
  {
    v5 = 0;
    goto LABEL_49;
  }
  EnterCriticalSection(&CriticalSection);
  v5 = 1;
  if ( !*(_DWORD *)&Data )
    goto LABEL_49;
  v29 = 0;
  v38 = 0;
  v31 = 0;
  v6 = 0;
  memset(v32, 0, sizeof(v32));
  v33 = 0;
  *(_OWORD *)Buf2 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  KeyInfo = GetKeyInfo(v2, &v31);
  v8 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\keycache.c";
  if ( KeyInfo >= 0 )
  {
    v16 = qword_18007A628;
    v17 = v35;
    v9 = Buf2[1];
    while ( 1 )
    {
      if ( (__int64 *)v16 == &qword_18007A628 || v1 )
      {
        v2 = (_OWORD *)a1;
        v5 = 1;
        goto LABEL_8;
      }
      v18 = *(_QWORD *)v16;
      if ( (unsigned int)IsEqualKey(v16, &v31, v8) )
        break;
LABEL_36:
      v16 = v18;
    }
    v19 = *(_QWORD *)(v16 + 72);
    if ( v19 )
    {
      if ( !v9 || *(_DWORD *)(v16 + 80) != v17 || memcmp_0(*(const void **)(v16 + 72), v9, *(unsigned int *)(v16 + 80)) )
      {
        v6 = v29;
        goto LABEL_36;
      }
    }
    else if ( !v9 )
    {
      v1 = 1;
      goto LABEL_43;
    }
    v1 = 1;
    if ( v19 )
    {
LABEL_45:
      v6 = v16;
      v29 = v16;
      goto LABEL_36;
    }
LABEL_43:
    if ( v9 )
    {
      *(_DWORD *)(v16 + 80) = v17;
      v17 = 0;
      v9 = 0;
      *(void **)(v16 + 72) = Buf2[1];
      Buf2[1] = 0;
      LODWORD(v35) = 0;
    }
    goto LABEL_45;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)&WPP_GLOBAL_Control,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\keycache.c",
      (unsigned int)"Status",
      KeyInfo,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\keycache.c",
      127);
  v9 = Buf2[1];
LABEL_8:
  v10 = (_OWORD *)*((_QWORD *)&v33 + 1);
  if ( *((_QWORD *)&v33 + 1) )
  {
    v11 = LODWORD(Buf2[0]);
    if ( LODWORD(Buf2[0]) )
    {
      do
      {
        *(_BYTE *)v10 = 0;
        v10 = (_OWORD *)((char *)v10 + 1);
        --v11;
      }
      while ( v11 );
      v9 = Buf2[1];
      v10 = (_OWORD *)*((_QWORD *)&v33 + 1);
    }
    if ( v10 != v32 )
    {
      MSCryptFree(v10);
      v9 = Buf2[1];
    }
    *((_QWORD *)&v33 + 1) = 0;
    LODWORD(Buf2[0]) = 0;
    LODWORD(v33) = 0;
  }
  if ( v9 )
  {
    MSCryptFree(v9);
    Buf2[1] = 0;
    LODWORD(v35) = 0;
  }
  if ( *((_QWORD *)&v35 + 1) )
  {
    MSCryptFree(*((_QWORD *)&v35 + 1));
    *((_QWORD *)&v35 + 1) = 0;
  }
  if ( (_QWORD)v36 )
  {
    MSCryptFree(v36);
    *(_QWORD *)&v36 = 0;
  }
  if ( *((_QWORD *)&v36 + 1) )
  {
    MSCryptFree(*((_QWORD *)&v36 + 1));
    *((_QWORD *)&v36 + 1) = 0;
  }
  if ( v6 )
    RemoveCacheEntry(v6);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x88u);
  v4 = (__int64)Heap;
  if ( Heap )
  {
    v3 = GetKeyInfo(v2, Heap);
    if ( v3 >= 0 )
    {
      *(_DWORD *)(v4 + 64) = 64;
      v13 = (_OWORD *)SafeAllocaAllocateFromHeap(64);
      *(_QWORD *)(v4 + 56) = v13;
      if ( v13 )
      {
        *(_DWORD *)(v4 + 48) = 64;
        *v13 = v2[27];
        v13[1] = v2[28];
        v13[2] = v2[29];
        v13[3] = v2[30];
        SystemFunction040(*(PVOID *)(v4 + 56), *(_DWORD *)(v4 + 64), 0);
        *(_DWORD *)(v4 + 128) = GetTickCount();
        v20 = qword_18007A628;
        if ( *(__int64 **)(qword_18007A628 + 8) != &qword_18007A628 )
          __fastfail(3u);
        *(_QWORD *)v4 = qword_18007A628;
        *(_QWORD *)(v4 + 8) = &qword_18007A628;
        *(_QWORD *)(v20 + 8) = v4;
        qword_18007A628 = v4;
        if ( (unsigned int)++dword_18007A640 > *(_DWORD *)&Data )
        {
          while ( 1 )
          {
            v25 = 0;
            if ( (__int64 *)v4 == &qword_18007A628 )
              break;
            do
            {
              v26 = v4;
              v4 = *(_QWORD *)v4;
              if ( v25 )
              {
                if ( *(_DWORD *)(v26 + 128) < *(_DWORD *)(v25 + 128) )
                  v25 = v26;
              }
              else
              {
                v25 = v26;
              }
            }
            while ( (__int64 *)v4 != &qword_18007A628 );
            if ( !v25 )
              break;
            RemoveCacheEntry(v25);
            if ( (unsigned int)dword_18007A640 <= *(_DWORD *)&Data )
              break;
            v4 = qword_18007A628;
          }
        }
        v4 = 0;
        v3 = 0;
      }
      else
      {
        v3 = -2146893810;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v14,
            v15,
            (unsigned int)"Status",
            14,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\keycache.c",
            94);
      }
    }
  }
  else
  {
    v3 = -2146893810;
    DebugTraceError(2148073486LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\keycache.c", 1092);
  }
LABEL_49:
  TickCount = GetTickCount();
  v22 = *(_DWORD *)&dword_18007A644;
  v23 = TickCount;
  if ( *(_DWORD *)&dword_18007A644 <= TickCount - dword_18007A638 )
  {
    v27 = (__int64 *)qword_18007A628;
    while ( v27 != &qword_18007A628 )
    {
      v28 = v27;
      v27 = (__int64 *)*v27;
      if ( v22 < v23 - *((_DWORD *)v28 + 32) )
      {
        RemoveCacheEntry(v28);
        v22 = *(_DWORD *)&dword_18007A644;
      }
    }
    dword_18007A638 = v23;
  }
  if ( v5 )
    LeaveCriticalSection(&CriticalSection);
  if ( v4 )
    FreeKeyInfo(v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000ceb0  push    rbp
0x18000ceb2  push    rbx
0x18000ceb3  push    rsi
0x18000ceb4  push    rdi
0x18000ceb5  push    r12
0x18000ceb7  push    r13
0x18000ceb9  push    r14
0x18000cebb  push    r15
0x18000cebd  lea     rbp, [rsp-1Fh]
0x18000cec2  sub     rsp, 0F8h
0x18000cec9  mov     rax, cs:__security_cookie
0x18000ced0  xor     rax, rsp
0x18000ced3  mov     [rbp+57h+var_50], rax
0x18000ced7  xor     r14d, r14d
0x18000ceda  mov     [rsp+130h+var_E8], rcx
0x18000cedf  test    byte ptr [rcx+1ACh], 40h
0x18000cee6  lea     r12, qword_18007A628
0x18000ceed  mov     r13, rcx
0x18000cef0  mov     edi, r14d
0x18000cef3  mov     ebx, r14d
0x18000cef6  jnz     loc_18000D2D9
0x18000cefc  lea     rcx, CriticalSection; lpCriticalSection
0x18000cf03  call    cs:__imp_EnterCriticalSection
0x18000cf0a  nop     dword ptr [rax+rax+00h]
0x18000cf0f  cmp     cs:Data, ebx
0x18000cf15  mov     r15d, 1
0x18000cf1b  jz      loc_18000D262
0x18000cf21  xorps   xmm0, xmm0
0x18000cf24  mov     [rsp+130h+var_F0], r14
0x18000cf29  xor     eax, eax
0x18000cf2b  lea     rdx, [rsp+130h+var_E0]
0x18000cf30  mov     rcx, r13
0x18000cf33  mov     [rbp+57h+var_60], rax
0x18000cf37  movups  [rsp+130h+var_E0], xmm0
0x18000cf3c  mov     esi, r14d
0x18000cf3f  movups  [rbp+57h+var_D0], xmm0
0x18000cf43  movups  [rbp+57h+var_C0], xmm0
0x18000cf47  movups  [rbp+57h+var_B0], xmm0
0x18000cf4b  movups  xmmword ptr [rbp+57h+Buf2], xmm0
0x18000cf4f  movups  [rbp+57h+var_90], xmm0
0x18000cf53  movups  [rbp+57h+var_80], xmm0
0x18000cf57  movups  [rbp+57h+var_70], xmm0
0x18000cf5b  call    _GetKeyInfo
0x18000cf60  lea     rdx, WPP_GLOBAL_Control
0x18000cf67  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cf6e  test    eax, eax
0x18000cf70  jns     loc_18000D0DF
0x18000cf76  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf7d  cmp     rcx, rdx
0x18000cf80  jz      short loc_18000CF8C
0x18000cf82  test    [rcx+1Ch], r15b
0x18000cf86  jnz     loc_18000D153
0x18000cf8c  mov     rbx, [rbp+57h+Buf2+8]
0x18000cf90  mov     rcx, qword ptr [rbp+57h+var_B0+8]
0x18000cf94  test    rcx, rcx
0x18000cf97  jz      short loc_18000CFD4
0x18000cf99  mov     eax, dword ptr [rbp+57h+Buf2]
0x18000cf9c  test    rax, rax
0x18000cf9f  jz      short loc_18000CFB6
0x18000cfa1  mov     byte ptr [rcx], 0
0x18000cfa4  lea     rcx, [rcx+1]
0x18000cfa8  sub     rax, 1
0x18000cfac  jnz     short loc_18000CFA1
0x18000cfae  mov     rbx, [rbp+57h+Buf2+8]
0x18000cfb2  mov     rcx, qword ptr [rbp+57h+var_B0+8]
0x18000cfb6  lea     rax, [rbp+57h+var_D0]
0x18000cfba  cmp     rcx, rax
0x18000cfbd  jz      short loc_18000CFC8
0x18000cfbf  call    MSCryptFree
0x18000cfc4  mov     rbx, [rbp+57h+Buf2+8]
0x18000cfc8  mov     qword ptr [rbp+57h+var_B0+8], r14
0x18000cfcc  mov     dword ptr [rbp+57h+Buf2], r14d
0x18000cfd0  mov     dword ptr [rbp+57h+var_B0], r14d
0x18000cfd4  test    rbx, rbx
0x18000cfd7  jz      short loc_18000CFE9
0x18000cfd9  mov     rcx, rbx
0x18000cfdc  call    MSCryptFree
0x18000cfe1  mov     [rbp+57h+Buf2+8], r14
0x18000cfe5  mov     dword ptr [rbp+57h+var_90], r14d
0x18000cfe9  mov     rcx, qword ptr [rbp+57h+var_90+8]
0x18000cfed  test    rcx, rcx
0x18000cff0  jz      short loc_18000CFFB
0x18000cff2  call    MSCryptFree
0x18000cff7  mov     qword ptr [rbp+57h+var_90+8], r14
0x18000cffb  mov     rcx, qword ptr [rbp+57h+var_80]
0x18000cfff  test    rcx, rcx
0x18000d002  jz      short loc_18000D00D
0x18000d004  call    MSCryptFree
0x18000d009  mov     qword ptr [rbp+57h+var_80], r14
0x18000d00d  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x18000d011  test    rcx, rcx
0x18000d014  jz      short loc_18000D01F
0x18000d016  call    MSCryptFree
0x18000d01b  mov     qword ptr [rbp+57h+var_80+8], r14
0x18000d01f  test    rsi, rsi
0x18000d022  jnz     loc_18000D2CC
0x18000d028  mov     rcx, gs:60h
0x18000d031  xor     edx, edx; Flags
0x18000d033  mov     r8d, 88h; Size
0x18000d039  mov     rcx, [rcx+30h]; HeapHandle
0x18000d03d  call    cs:__imp_RtlAllocateHeap
0x18000d044  nop     dword ptr [rax+rax+00h]
0x18000d049  mov     rbx, rax
0x18000d04c  test    rax, rax
0x18000d04f  jz      loc_18000D2F2
0x18000d055  mov     rdx, rax
0x18000d058  mov     rcx, r13
0x18000d05b  call    _GetKeyInfo
0x18000d060  mov     edi, eax
0x18000d062  test    eax, eax
0x18000d064  js      loc_18000D262
0x18000d06a  mov     ecx, 40h ; '@'
0x18000d06f  mov     dword ptr [rbx+40h], 40h ; '@'
0x18000d076  call    SafeAllocaAllocateFromHeap
0x18000d07b  mov     [rbx+38h], rax
0x18000d07f  test    rax, rax
0x18000d082  jnz     loc_18000D1C1
0x18000d088  mov     edi, 8009000Eh
0x18000d08d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d094  lea     rax, WPP_GLOBAL_Control
0x18000d09b  cmp     rcx, rax
0x18000d09e  jz      loc_18000D262
0x18000d0a4  test    byte ptr [rcx+1Ch], 1
0x18000d0a8  jz      loc_18000D262
0x18000d0ae  mov     rcx, [rcx+10h]
0x18000d0b2  lea     rax, aOnecoreDsSecur_39; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d0b9  mov     [rsp+130h+var_100], 45Eh
0x18000d0c1  lea     r9, aStatus; "Status"
0x18000d0c8  mov     [rsp+130h+var_108], rax
0x18000d0cd  mov     [rsp+130h+var_110], 8009000Eh
0x18000d0d5  call    WPP_SF_sDsd
0x18000d0da  jmp     loc_18000D262
0x18000d0df  mov     rdi, cs:qword_18007A628
0x18000d0e6  lea     r13, qword_18007A628
0x18000d0ed  mov     r12d, dword ptr [rbp+57h+var_90]
0x18000d0f1  mov     rbx, [rbp+57h+Buf2+8]
0x18000d0f5  cmp     rdi, r13
0x18000d0f8  jnz     short loc_18000D114
0x18000d0fa  mov     r13, [rsp+130h+var_E8]
0x18000d0ff  lea     r12, qword_18007A628
0x18000d106  mov     r15d, 1
0x18000d10c  xor     r14d, r14d
0x18000d10f  jmp     loc_18000CF90
0x18000d114  test    r14d, r14d
0x18000d117  jnz     short loc_18000D0FA
0x18000d119  mov     r15, [rdi]
0x18000d11c  lea     rdx, [rsp+130h+var_E0]
0x18000d121  mov     rcx, rdi
0x18000d124  call    _IsEqualKey
0x18000d129  test    eax, eax
0x18000d12b  jnz     short loc_18000D132
0x18000d12d  mov     rdi, r15
0x18000d130  jmp     short loc_18000D0F5
0x18000d132  mov     rsi, [rdi+48h]
0x18000d136  test    rsi, rsi
0x18000d139  jz      loc_18000D2DE
0x18000d13f  test    rbx, rbx
0x18000d142  jz      short loc_18000D14C
0x18000d144  mov     eax, [rdi+50h]
0x18000d147  cmp     eax, r12d
0x18000d14a  jz      short loc_18000D179
0x18000d14c  mov     rsi, [rsp+130h+var_F0]
0x18000d151  jmp     short loc_18000D12D
0x18000d153  mov     rcx, [rcx+10h]
0x18000d157  lea     r9, aStatus; "Status"
0x18000d15e  mov     [rsp+130h+var_100], 27Fh
0x18000d166  mov     [rsp+130h+var_108], r8
0x18000d16b  mov     [rsp+130h+var_110], eax
0x18000d16f  call    WPP_SF_sDsd
0x18000d174  jmp     loc_18000CF8C
0x18000d179  mov     r8, rax; Size
0x18000d17c  mov     rdx, rbx; Buf2
0x18000d17f  mov     rcx, rsi; Buf1
0x18000d182  call    memcmp_0
0x18000d187  test    eax, eax
0x18000d189  jnz     short loc_18000D14C
0x18000d18b  mov     r14d, 1
0x18000d191  test    rsi, rsi
0x18000d194  jnz     short loc_18000D1B4
0x18000d196  test    rbx, rbx
0x18000d199  jz      short loc_18000D1B4
0x18000d19b  mov     [rdi+50h], r12d
0x18000d19f  xor     r12d, r12d
0x18000d1a2  mov     rax, [rbp+57h+Buf2+8]
0x18000d1a6  xor     ebx, ebx
0x18000d1a8  mov     [rdi+48h], rax
0x18000d1ac  mov     [rbp+57h+Buf2+8], rbx
0x18000d1b0  mov     dword ptr [rbp+57h+var_90], r12d
0x18000d1b4  mov     rsi, rdi
0x18000d1b7  mov     [rsp+130h+var_F0], rdi
0x18000d1bc  jmp     loc_18000D12D
0x18000d1c1  mov     dword ptr [rbx+30h], 40h ; '@'
0x18000d1c8  xor     r8d, r8d; OptionFlags
0x18000d1cb  movups  xmm0, xmmword ptr [r13+1B0h]
0x18000d1d3  movups  xmmword ptr [rax], xmm0
0x18000d1d6  movups  xmm1, xmmword ptr [r13+1C0h]
0x18000d1de  movups  xmmword ptr [rax+10h], xmm1
0x18000d1e2  movups  xmm0, xmmword ptr [r13+1D0h]
0x18000d1ea  movups  xmmword ptr [rax+20h], xmm0
0x18000d1ee  movups  xmm1, xmmword ptr [r13+1E0h]
0x18000d1f6  movups  xmmword ptr [rax+30h], xmm1
0x18000d1fa  mov     edx, [rbx+40h]; MemorySize
0x18000d1fd  mov     rcx, [rbx+38h]; Memory
0x18000d201  call    cs:__imp_SystemFunction040
0x18000d208  nop     dword ptr [rax+rax+00h]
0x18000d20d  call    cs:__imp_GetTickCount
0x18000d214  nop     dword ptr [rax+rax+00h]
0x18000d219  mov     [rbx+80h], eax
0x18000d21f  mov     rax, cs:qword_18007A628
0x18000d226  cmp     [rax+8], r12
0x18000d22a  jnz     loc_18000D31A
0x18000d230  mov     [rbx], rax
0x18000d233  mov     [rbx+8], r12
0x18000d237  mov     [rax+8], rbx
0x18000d23b  mov     eax, cs:dword_18007A640
0x18000d241  inc     eax
0x18000d243  mov     cs:qword_18007A628, rbx
0x18000d24a  cmp     eax, cs:Data
0x18000d250  mov     cs:dword_18007A640, eax
0x18000d256  ja      loc_18000D321
0x18000d25c  mov     rbx, r14
0x18000d25f  mov     edi, r14d
0x18000d262  call    cs:__imp_GetTickCount
0x18000d269  nop     dword ptr [rax+rax+00h]
0x18000d26e  mov     edx, cs:dword_18007A644
0x18000d274  mov     ecx, eax
0x18000d276  sub     ecx, cs:dword_18007A638
0x18000d27c  mov     esi, eax
0x18000d27e  cmp     edx, ecx
0x18000d280  jbe     loc_18000D37B
0x18000d286  test    r15d, r15d
0x18000d289  jnz     short loc_18000D2B7
0x18000d28b  test    rbx, rbx
0x18000d28e  jnz     loc_18000D3B4
0x18000d294  mov     eax, edi
0x18000d296  mov     rcx, [rbp+57h+var_50]
0x18000d29a  xor     rcx, rsp; StackCookie
0x18000d29d  call    __security_check_cookie
0x18000d2a2  add     rsp, 0F8h
0x18000d2a9  pop     r15
0x18000d2ab  pop     r14
0x18000d2ad  pop     r13
0x18000d2af  pop     r12
0x18000d2b1  pop     rdi
0x18000d2b2  pop     rsi
0x18000d2b3  pop     rbx
0x18000d2b4  pop     rbp
0x18000d2b5  retn
0x18000d2b7  lea     rcx, CriticalSection; lpCriticalSection
0x18000d2be  call    cs:__imp_LeaveCriticalSection
0x18000d2c5  nop     dword ptr [rax+rax+00h]
0x18000d2ca  jmp     short loc_18000D28B
0x18000d2cc  mov     rcx, rsi
0x18000d2cf  call    _RemoveCacheEntry
0x18000d2d4  jmp     loc_18000D028
0x18000d2d9  mov     r15d, r14d
0x18000d2dc  jmp     short loc_18000D262
0x18000d2de  test    rbx, rbx
0x18000d2e1  jnz     loc_18000D18B
0x18000d2e7  mov     r14d, 1
0x18000d2ed  jmp     loc_18000D196
0x18000d2f2  mov     r9d, 444h
0x18000d2f8  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d2ff  lea     rdx, aStatus; "Status"
0x18000d306  mov     ecx, 8009000Eh
0x18000d30b  mov     edi, 8009000Eh
0x18000d310  call    DebugTraceError
0x18000d315  jmp     loc_18000D262
0x18000d31a  mov     ecx, 3
0x18000d31f  int     29h; Win8: RtlFailFast(ecx)
0x18000d321  mov     rcx, r14
0x18000d324  cmp     rbx, r12
0x18000d327  jz      loc_18000D25C
0x18000d32d  mov     rdx, rbx
0x18000d330  mov     rbx, [rbx]
0x18000d333  test    rcx, rcx
0x18000d336  jnz     short loc_18000D33D
0x18000d338  mov     rcx, rdx
0x18000d33b  jmp     short loc_18000D34D
0x18000d33d  mov     eax, [rcx+80h]
0x18000d343  cmp     [rdx+80h], eax
0x18000d349  cmovb   rcx, rdx
0x18000d34d  cmp     rbx, r12
0x18000d350  jnz     short loc_18000D32D
0x18000d352  test    rcx, rcx
0x18000d355  jz      loc_18000D25C
0x18000d35b  call    _RemoveCacheEntry
0x18000d360  mov     eax, cs:Data
0x18000d366  cmp     cs:dword_18007A640, eax
0x18000d36c  jbe     loc_18000D25C
0x18000d372  mov     rbx, cs:qword_18007A628
0x18000d379  jmp     short loc_18000D321
0x18000d37b  mov     r14, cs:qword_18007A628
0x18000d382  cmp     r14, r12
0x18000d385  jz      short loc_18000D3A9
0x18000d387  mov     rcx, r14
0x18000d38a  mov     eax, esi
0x18000d38c  mov     r14, [r14]
0x18000d38f  sub     eax, [rcx+80h]
0x18000d395  cmp     edx, eax
  ... truncated ...
```
