# EnumQMSAsInternal

- ea: `0x18002efbc`
- end: `0x18002f3b2`
- name: `EnumQMSAsInternal`
- size: `1014`
- prototype: `__int64 __fastcall(__int64, __int64, IPSEC_SA_DETAILS0 **, UINT32, UINT32 numEntriesRequested, _QWORD *, UINT32 *, _DWORD *, _DWORD *, HANDLE enumHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180012410`

## callees

- `0x18000e510`
- `0x180017534`
- `0x1800175dc`
- `0x18002e0e0`
- `0x18002efbc`
- `0x180042ef8`
- `0x18004d05e`

## import_xrefs

- `fwpuclnt!FwpmEngineClose0` at `0x18002f1dc`
- `fwpuclnt!FwpmEngineClose0` at `0x18002f1dc`
- `fwpuclnt!IPsecSaEnum0` at `0x18002f18c`
- `fwpuclnt!IPsecSaEnum0` at `0x18002f2fa`
- `fwpuclnt!IPsecSaEnum0` at `0x18002f18c`
- `fwpuclnt!IPsecSaEnum0` at `0x18002f2fa`
- `fwpuclnt!FwpmFreeMemory0` at `0x18002f1ad`
- `fwpuclnt!FwpmFreeMemory0` at `0x18002f1fe`
- `fwpuclnt!FwpmFreeMemory0` at `0x18002f342`
- `fwpuclnt!FwpmFreeMemory0` at `0x18002f363`
- `fwpuclnt!FwpmFreeMemory0` at `0x18002f1ad`
- `fwpuclnt!FwpmFreeMemory0` at `0x18002f1fe`
- `fwpuclnt!FwpmFreeMemory0` at `0x18002f342`
- `fwpuclnt!FwpmFreeMemory0` at `0x18002f363`
- `fwpuclnt!FwpmEngineOpen0` at `0x18002f045`
- `fwpuclnt!FwpmEngineOpen0` at `0x18002f045`
- `fwpuclnt!IPsecSaCreateEnumHandle0` at `0x18002f0d0`
- `fwpuclnt!IPsecSaCreateEnumHandle0` at `0x18002f0d0`
- `fwpuclnt!IPsecSaDestroyEnumHandle0` at `0x18002f1d2`
- `fwpuclnt!IPsecSaDestroyEnumHandle0` at `0x18002f1d2`

## pseudocode

```c
__int64 __fastcall EnumQMSAsInternal(
        __int64 a1,
        __int64 a2,
        IPSEC_SA_DETAILS0 **a3,
        UINT32 a4,
        UINT32 numEntriesRequested,
        _QWORD *a6,
        UINT32 *a7,
        _DWORD *a8,
        _DWORD *a9,
        HANDLE enumHandle)
{
  _DWORD *v10; // rsi
  _DWORD *v11; // r13
  unsigned int v12; // r12d
  UINT32 v13; // r14d
  DWORD v14; // eax
  unsigned int v15; // ebx
  _QWORD *v16; // rcx
  int v17; // r15d
  DWORD v18; // eax
  _QWORD *v19; // rcx
  unsigned int v20; // ebx
  UINT32 v21; // edi
  unsigned int v23; // eax
  unsigned int v24; // eax
  UINT32 v25; // edi
  UINT32 v26; // eax
  IPSEC_SA_DETAILS0 **v27; // rdx
  __int64 i; // rbx
  _QWORD *v29; // rax
  size_t Size; // [rsp+30h] [rbp-18h] BYREF
  void *p; // [rsp+38h] [rbp-10h] BYREF
  HANDLE engineHandle; // [rsp+90h] [rbp+48h] BYREF
  IPSEC_SA_ENUM_TEMPLATE0 enumTemplate; // [rsp+98h] [rbp+50h] BYREF
  IPSEC_SA_DETAILS0 **entries; // [rsp+A0h] [rbp+58h] BYREF
  UINT32 numEntriesReturned; // [rsp+A8h] [rbp+60h] BYREF

  numEntriesReturned = a4;
  entries = a3;
  v10 = 0;
  v11 = a9;
  engineHandle = 0;
  enumTemplate.saDirection = FWP_DIRECTION_OUTBOUND;
  enumHandle = 0;
  v12 = *a9;
  v13 = 100;
  numEntriesReturned = 0;
  a9 = 0;
  if ( numEntriesRequested - 1 <= 0x1F3 )
    v13 = numEntriesRequested;
  entries = 0;
  p = 0;
  v14 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
  v15 = v14;
  if ( !v14 )
  {
    enumTemplate.saDirection = FWP_DIRECTION_OUTBOUND;
    v17 = 0;
    v18 = IPsecSaCreateEnumHandle0(engineHandle, &enumTemplate, &enumHandle);
    v15 = v18;
    if ( v18 != 1753 )
    {
      if ( v18 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids, v18);
            v19 = WPP_GLOBAL_Control;
          }
          if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 0x10) != 0 )
            WPP_SF_d(v19[2], 37, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids, v15);
        }
LABEL_30:
        FwpmEngineClose0(engineHandle);
        if ( !v15 )
          goto LABEL_33;
        goto LABEL_31;
      }
      v20 = 0;
      v17 = 1;
      while ( v20 < v12 )
      {
        v21 = v12 - v20;
        if ( v20 + v13 <= v12 )
          v21 = v13;
        if ( IPsecSaEnum0(engineHandle, enumHandle, v21, &entries, &numEntriesReturned)
          || !numEntriesReturned
          || !entries )
        {
          entries = 0;
          goto LABEL_28;
        }
        if ( numEntriesReturned < v21 )
          goto LABEL_28;
        v20 += numEntriesReturned;
        FwpmFreeMemory0((void **)&entries);
        entries = 0;
      }
      Size = 0;
      v23 = NsuSizeTMultiply(v13, 368, &Size);
      v15 = v23;
      if ( v23 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids, v23);
        goto LABEL_29;
      }
      v24 = SPDApiBufferAllocate(Size);
      v15 = v24;
      if ( v24 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids, v24);
        v10 = a9;
        goto LABEL_29;
      }
      v10 = a9;
      v25 = 0;
      memset_0(a9, 0, Size);
      while ( v25 < v13 )
      {
        if ( IPsecSaEnum0(engineHandle, enumHandle, v13, &entries, &numEntriesReturned)
          || (v26 = numEntriesReturned) == 0
          || (v27 = entries) == 0 )
        {
          entries = 0;
          break;
        }
        for ( i = 0; (unsigned int)i < v26; i = (unsigned int)(i + 1) )
        {
          if ( (unsigned int)ConvertQMSAFromBfeToSpd((int *)v27[i], (__int64)v27, engineHandle, &v10[92 * v25]) )
            goto LABEL_59;
          if ( p )
          {
            FwpmFreeMemory0(&p);
            p = 0;
          }
          v26 = numEntriesReturned;
          ++v25;
          v27 = entries;
        }
        FwpmFreeMemory0((void **)&entries);
        entries = 0;
        if ( numEntriesReturned < v13 )
          break;
      }
LABEL_59:
      if ( v25 )
      {
        v29 = a6;
        *v11 = v25 + v12;
        v15 = 0;
        *v29 = v10;
        *a7 = v25;
        *a8 = v25 + v12;
LABEL_29:
        IPsecSaDestroyEnumHandle0(engineHandle, enumHandle);
        goto LABEL_30;
      }
    }
LABEL_28:
    v15 = 232;
    if ( !v17 )
      goto LABEL_30;
    goto LABEL_29;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids, v14);
      v16 = WPP_GLOBAL_Control;
    }
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 0x10) != 0 )
      WPP_SF_d(v16[2], 35, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids, v15);
  }
LABEL_31:
  if ( v10 )
    SPDApiBufferFree(v10);
LABEL_33:
  if ( entries )
    FwpmFreeMemory0((void **)&entries);
  return v15;
}

```

## disassembly

```asm
0x18002efbc  mov     rax, rsp
0x18002efbf  mov     [rax+20h], r9d
0x18002efc3  mov     [rax+18h], r8
0x18002efc7  mov     [rax+10h], edx
0x18002efca  mov     [rax+8], rcx
0x18002efce  push    rbp
0x18002efcf  push    rbx
0x18002efd0  push    rsi
0x18002efd1  push    rdi
0x18002efd2  push    r12
0x18002efd4  push    r13
0x18002efd6  push    r14
0x18002efd8  push    r15
0x18002efda  mov     rbp, rsp
0x18002efdd  sub     rsp, 48h
0x18002efe1  mov     ecx, [rbp+numEntriesRequested]
0x18002efe4  xor     esi, esi
0x18002efe6  mov     r13, [rbp+arg_40]
0x18002efed  mov     [rbp+arg_0], 0
0x18002eff5  mov     [rbp+enumTemplate.saDirection], 0
0x18002effc  lea     eax, [rcx-1]
0x18002efff  mov     [rbp+enumHandle], 0
0x18002f00a  mov     r12d, [r13+0]
0x18002f00e  lea     r14d, [rsi+64h]
0x18002f012  cmp     eax, 1F3h
0x18002f017  mov     [rbp+numEntriesReturned], 0
0x18002f01e  lea     rax, [rbp+arg_0]
0x18002f022  mov     [rbp+arg_40], rsi
0x18002f029  cmovbe  r14d, ecx
0x18002f02d  mov     [rbp+entries], rsi
0x18002f031  xor     r9d, r9d; session
0x18002f034  mov     [rbp+p], rsi
0x18002f038  xor     r8d, r8d; authIdentity
0x18002f03b  mov     [rsp+48h+engineHandle], rax; engineHandle
0x18002f040  xor     ecx, ecx; serverName
0x18002f042  lea     edx, [rsi+0Ah]; authnService
0x18002f045  call    cs:__imp_FwpmEngineOpen0
0x18002f04b  mov     ebx, eax
0x18002f04d  test    eax, eax
0x18002f04f  jz      short loc_18002F0BB
0x18002f051  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f058  lea     rdi, WPP_GLOBAL_Control
0x18002f05f  cmp     rcx, rdi
0x18002f062  jz      loc_18002F1E6
0x18002f068  test    byte ptr [rcx+1Ch], 10h
0x18002f06c  jz      short loc_18002F08B
0x18002f06e  mov     rcx, [rcx+10h]
0x18002f072  lea     edx, [rsi+22h]
0x18002f075  mov     r9d, eax
0x18002f078  lea     r8, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids
0x18002f07f  call    WPP_SF_d
0x18002f084  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f08b  cmp     rcx, rdi
0x18002f08e  jz      loc_18002F1E6
0x18002f094  test    byte ptr [rcx+1Ch], 10h
0x18002f098  jz      loc_18002F1E6
0x18002f09e  mov     rcx, [rcx+10h]
0x18002f0a2  lea     r8, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids
0x18002f0a9  mov     edx, 23h ; '#'
0x18002f0ae  mov     r9d, ebx
0x18002f0b1  call    WPP_SF_d
0x18002f0b6  jmp     loc_18002F1E6
0x18002f0bb  mov     rcx, [rbp+arg_0]; engineHandle
0x18002f0bf  lea     r8, [rbp+enumHandle]; enumHandle
0x18002f0c6  lea     rdx, [rbp+enumTemplate]; enumTemplate
0x18002f0ca  mov     [rbp+enumTemplate.saDirection], esi
0x18002f0cd  xor     r15d, r15d
0x18002f0d0  call    cs:__imp_IPsecSaCreateEnumHandle0
0x18002f0d6  mov     ebx, eax
0x18002f0d8  cmp     eax, 6D9h
0x18002f0dd  jz      loc_18002F1BD
0x18002f0e3  test    eax, eax
0x18002f0e5  jz      short loc_18002F152
0x18002f0e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f0ee  lea     rdi, WPP_GLOBAL_Control
0x18002f0f5  cmp     rcx, rdi
0x18002f0f8  jz      loc_18002F1D8
0x18002f0fe  test    byte ptr [rcx+1Ch], 10h
0x18002f102  jz      short loc_18002F122
0x18002f104  mov     rcx, [rcx+10h]
0x18002f108  lea     edx, [r15+24h]
0x18002f10c  mov     r9d, eax
0x18002f10f  lea     r8, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids
0x18002f116  call    WPP_SF_d
0x18002f11b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f122  cmp     rcx, rdi
0x18002f125  jz      loc_18002F1D8
0x18002f12b  test    byte ptr [rcx+1Ch], 10h
0x18002f12f  jz      loc_18002F1D8
0x18002f135  mov     rcx, [rcx+10h]
0x18002f139  lea     r8, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids
0x18002f140  mov     edx, 25h ; '%'
0x18002f145  mov     r9d, ebx
0x18002f148  call    WPP_SF_d
0x18002f14d  jmp     loc_18002F1D8
0x18002f152  xor     ebx, ebx
0x18002f154  lea     r15d, [rbx+1]
0x18002f158  cmp     ebx, r12d
0x18002f15b  jnb     loc_18002F217
0x18002f161  mov     rdx, [rbp+enumHandle]; enumHandle
0x18002f168  lea     eax, [rbx+r14]
0x18002f16c  mov     rcx, [rbp+arg_0]; engineHandle
0x18002f170  lea     r9, [rbp+entries]; entries
0x18002f174  mov     edi, r12d
0x18002f177  sub     edi, ebx
0x18002f179  cmp     eax, r12d
0x18002f17c  lea     rax, [rbp+numEntriesReturned]
0x18002f180  mov     [rsp+48h+engineHandle], rax; numEntriesReturned
0x18002f185  cmovbe  edi, r14d
0x18002f189  mov     r8d, edi; numEntriesRequested
0x18002f18c  call    cs:__imp_IPsecSaEnum0
0x18002f192  test    eax, eax
0x18002f194  jnz     short loc_18002F1B9
0x18002f196  mov     eax, [rbp+numEntriesReturned]
0x18002f199  test    eax, eax
0x18002f19b  jz      short loc_18002F1B9
0x18002f19d  cmp     [rbp+entries], rsi
0x18002f1a1  jz      short loc_18002F1B9
0x18002f1a3  cmp     eax, edi
0x18002f1a5  jb      short loc_18002F1BD
0x18002f1a7  add     ebx, eax
0x18002f1a9  lea     rcx, [rbp+entries]; p
0x18002f1ad  call    cs:__imp_FwpmFreeMemory0
0x18002f1b3  mov     [rbp+entries], rsi
0x18002f1b7  jmp     short loc_18002F158
0x18002f1b9  mov     [rbp+entries], rsi
0x18002f1bd  mov     ebx, 0E8h
0x18002f1c2  test    r15d, r15d
0x18002f1c5  jz      short loc_18002F1D8
0x18002f1c7  mov     rdx, [rbp+enumHandle]; enumHandle
0x18002f1ce  mov     rcx, [rbp+arg_0]; engineHandle
0x18002f1d2  call    cs:__imp_IPsecSaDestroyEnumHandle0
0x18002f1d8  mov     rcx, [rbp+arg_0]; engineHandle
0x18002f1dc  call    cs:__imp_FwpmEngineClose0
0x18002f1e2  test    ebx, ebx
0x18002f1e4  jz      short loc_18002F1F3
0x18002f1e6  test    rsi, rsi
0x18002f1e9  jz      short loc_18002F1F3
0x18002f1eb  mov     rcx, rsi
0x18002f1ee  call    SPDApiBufferFree
0x18002f1f3  cmp     [rbp+entries], 0
0x18002f1f8  jz      short loc_18002F204
0x18002f1fa  lea     rcx, [rbp+entries]; p
0x18002f1fe  call    cs:__imp_FwpmFreeMemory0
0x18002f204  mov     eax, ebx
0x18002f206  add     rsp, 48h
0x18002f20a  pop     r15
0x18002f20c  pop     r14
0x18002f20e  pop     r13
0x18002f210  pop     r12
0x18002f212  pop     rdi
0x18002f213  pop     rsi
0x18002f214  pop     rbx
0x18002f215  pop     rbp
0x18002f216  retn
0x18002f217  mov     ecx, r14d
0x18002f21a  lea     r8, [rbp+Size]
0x18002f21e  mov     edx, 170h
0x18002f223  mov     [rbp+Size], rsi
0x18002f227  call    NsuSizeTMultiply
0x18002f22c  mov     ebx, eax
0x18002f22e  test    eax, eax
0x18002f230  jz      short loc_18002F26C
0x18002f232  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f239  lea     rdi, WPP_GLOBAL_Control
0x18002f240  cmp     rcx, rdi
0x18002f243  jz      short loc_18002F1C7
0x18002f245  test    byte ptr [rcx+1Ch], 10h
0x18002f249  jz      loc_18002F1C7
0x18002f24f  mov     rcx, [rcx+10h]
0x18002f253  lea     r8, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids
0x18002f25a  mov     edx, 26h ; '&'
0x18002f25f  mov     r9d, eax
0x18002f262  call    WPP_SF_d
0x18002f267  jmp     loc_18002F1C7
0x18002f26c  mov     rcx, [rbp+Size]; Size
0x18002f270  lea     rdx, [rbp+arg_40]
0x18002f277  call    SPDApiBufferAllocate
0x18002f27c  mov     ebx, eax
0x18002f27e  test    eax, eax
0x18002f280  jz      short loc_18002F2BF
0x18002f282  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f289  lea     rdi, WPP_GLOBAL_Control
0x18002f290  cmp     rcx, rdi
0x18002f293  jz      short loc_18002F2B3
0x18002f295  test    byte ptr [rcx+1Ch], 10h
0x18002f299  jz      short loc_18002F2B3
0x18002f29b  mov     rcx, [rcx+10h]
0x18002f29f  lea     r8, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids
0x18002f2a6  mov     edx, 27h ; '''
0x18002f2ab  mov     r9d, eax
0x18002f2ae  call    WPP_SF_d
0x18002f2b3  mov     rsi, [rbp+arg_40]
0x18002f2ba  jmp     loc_18002F1C7
0x18002f2bf  mov     rsi, [rbp+arg_40]
0x18002f2c6  xor     edi, edi
0x18002f2c8  mov     r8, [rbp+Size]; Size
0x18002f2cc  mov     rcx, rsi; void *
0x18002f2cf  xor     edx, edx; Val
0x18002f2d1  call    memset_0
0x18002f2d6  cmp     edi, r14d
0x18002f2d9  jnb     loc_18002F385
0x18002f2df  mov     rdx, [rbp+enumHandle]; enumHandle
0x18002f2e6  lea     rax, [rbp+numEntriesReturned]
0x18002f2ea  mov     rcx, [rbp+arg_0]; engineHandle
0x18002f2ee  lea     r9, [rbp+entries]; entries
0x18002f2f2  mov     r8d, r14d; numEntriesRequested
0x18002f2f5  mov     [rsp+48h+engineHandle], rax; numEntriesReturned
0x18002f2fa  call    cs:__imp_IPsecSaEnum0
0x18002f300  test    eax, eax
0x18002f302  jnz     short loc_18002F37D
0x18002f304  mov     eax, [rbp+numEntriesReturned]
0x18002f307  test    eax, eax
0x18002f309  jz      short loc_18002F37D
0x18002f30b  mov     rdx, [rbp+entries]
0x18002f30f  test    rdx, rdx
0x18002f312  jz      short loc_18002F37D
0x18002f314  xor     ebx, ebx
0x18002f316  cmp     ebx, eax
0x18002f318  jnb     short loc_18002F35F
0x18002f31a  mov     r8, [rbp+arg_0]
0x18002f31e  mov     rcx, [rdx+rbx*8]
0x18002f322  mov     eax, edi
0x18002f324  imul    r9, rax, 170h
0x18002f32b  add     r9, rsi
0x18002f32e  call    ConvertQMSAFromBfeToSpd
0x18002f333  test    eax, eax
0x18002f335  jnz     short loc_18002F385
0x18002f337  cmp     [rbp+p], 0
0x18002f33c  jz      short loc_18002F350
0x18002f33e  lea     rcx, [rbp+p]; p
0x18002f342  call    cs:__imp_FwpmFreeMemory0
0x18002f348  mov     [rbp+p], 0
0x18002f350  mov     eax, [rbp+numEntriesReturned]
0x18002f353  add     edi, r15d
0x18002f356  mov     rdx, [rbp+entries]
0x18002f35a  add     ebx, r15d
0x18002f35d  jmp     short loc_18002F316
0x18002f35f  lea     rcx, [rbp+entries]; p
0x18002f363  call    cs:__imp_FwpmFreeMemory0
0x18002f369  mov     [rbp+entries], 0
0x18002f371  cmp     [rbp+numEntriesReturned], r14d
0x18002f375  jnb     loc_18002F2D6
0x18002f37b  jmp     short loc_18002F385
0x18002f37d  mov     [rbp+entries], 0
0x18002f385  test    edi, edi
0x18002f387  jz      loc_18002F1BD
0x18002f38d  mov     rax, [rbp+arg_28]
0x18002f391  lea     ecx, [rdi+r12]
0x18002f395  mov     [r13+0], ecx
0x18002f399  xor     ebx, ebx
0x18002f39b  mov     [rax], rsi
0x18002f39e  mov     rax, [rbp+arg_30]
0x18002f3a2  mov     [rax], edi
0x18002f3a4  mov     rax, [rbp+arg_38]
0x18002f3ab  mov     [rax], ecx
0x18002f3ad  jmp     loc_18002F1C7
```
