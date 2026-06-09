# CRight::GetConditionListXML(uint *,ushort * *)

- ea: `0x18000d1a0`
- end: `0x18000d5e3`
- name: `?GetConditionListXML@CRight@@AEAAJPEAIPEAPEAG@Z`
- size: `1091`
- prototype: `__int64 __fastcall(CRight *__hidden this, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x180011800`

## callees

- `0x180001244`
- `0x180001284`
- `0x180004654`
- `0x18000d1a0`
- `0x18000db14`
- `0x18001074c`
- `0x180011ff4`
- `0x180017358`
- `0x18001ef30`
- `0x18001ffd8`
- `0x18005bd72`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d2b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d2b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d1ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d1ef`

## string_xrefs

- `0x18000d1fd`: `<CONDITIONLIST><ACCESS>%s</ACCESS>%s%s</CONDITIONLIST>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRight::GetConditionListXML(CRight *this, unsigned int *a2, unsigned __int16 **a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  CUser *v6; // rsi
  int XML; // edi
  unsigned __int16 *v8; // r13
  unsigned __int16 *v9; // r14
  unsigned __int16 *v10; // r12
  unsigned int v12; // r13d
  int v13; // r12d
  unsigned int i; // r15d
  CDRMCBase *v15; // rcx
  __int64 v16; // r12
  unsigned __int16 *v17; // rax
  unsigned int v18; // r15d
  CDRMCBase *v19; // rcx
  __int64 v20; // rcx
  void *v21; // r11
  __int64 v22; // r15
  unsigned __int16 *v23; // rax
  const unsigned __int16 *v24; // r8
  unsigned __int16 *v25; // rcx
  unsigned int v26[2]; // [rsp+38h] [rbp-D0h] BYREF
  unsigned __int16 *v27; // [rsp+40h] [rbp-C8h]
  unsigned __int16 *v28; // [rsp+48h] [rbp-C0h] BYREF
  unsigned __int16 *v29; // [rsp+50h] [rbp-B8h]
  unsigned int v30[2]; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int16 *v31; // [rsp+60h] [rbp-A8h] BYREF
  unsigned __int16 **v32; // [rsp+68h] [rbp-A0h]
  void *Block; // [rsp+70h] [rbp-98h] BYREF
  unsigned int *v34; // [rsp+78h] [rbp-90h]
  __int64 v35; // [rsp+80h] [rbp-88h]
  char *v36; // [rsp+88h] [rbp-80h]
  unsigned __int16 v37[8]; // [rsp+98h] [rbp-70h] BYREF
  __int128 v38; // [rsp+A8h] [rbp-60h]
  __int128 v39; // [rsp+B8h] [rbp-50h]
  __int128 v40; // [rsp+C8h] [rbp-40h]
  __int128 v41; // [rsp+D8h] [rbp-30h]
  _OWORD v42[2]; // [rsp+E8h] [rbp-20h]

  v35 = -2;
  v32 = a3;
  v34 = a2;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  v36 = (char *)this + 88;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v29 = 0;
  *(_OWORD *)v37 = *(_OWORD *)L"<CONDITIONLIST><ACCESS>%s</ACCESS>%s%s</CONDITIONLIST>";
  v38 = *(_OWORD *)L"ONLIST><ACCESS>%s</ACCESS>%s%s</CONDITIONLIST>";
  v39 = *(_OWORD *)L"ACCESS>%s</ACCESS>%s%s</CONDITIONLIST>";
  v40 = *(_OWORD *)L"s</ACCESS>%s%s</CONDITIONLIST>";
  v41 = *(_OWORD *)L"S>%s%s</CONDITIONLIST>";
  v42[0] = *(_OWORD *)L"CONDITIONLIST>";
  *(_OWORD *)((char *)v42 + 14) = *(_OWORD *)L"ONLIST>";
  v27 = 0;
  v31 = 0;
  Block = 0;
  v28 = 0;
  v30[0] = 0;
  v6 = 0;
  if ( !a2 )
  {
    XML = -2147024809;
LABEL_3:
    v8 = 0;
    v9 = 0;
    goto LABEL_4;
  }
  XML = 0;
  v12 = *((_DWORD *)this + 36);
  *a2 = 0;
  if ( !v12 )
    goto LABEL_3;
  v13 = 0;
  for ( i = 0; i < v12; ++i )
  {
    if ( i < *((_DWORD *)this + 36) )
    {
      v15 = *(CDRMCBase **)(*((_QWORD *)this + 17) + 8LL * i);
      if ( v15 )
      {
        CDRMCBase::AddRef(v15);
        v6 = *(CUser **)(*((_QWORD *)this + 17) + 8LL * i);
        if ( !v6 )
          continue;
        v26[0] = 0;
        XML = CUser::GetXML(v6, v26, 0);
        if ( XML < 0 )
        {
          v9 = v29;
          v8 = v29;
          goto LABEL_4;
        }
        v13 += v26[0];
        CDRMCBase::Release(v6);
      }
    }
    v6 = 0;
  }
  v16 = (unsigned int)(v13 + 1);
  if ( !v32 )
  {
LABEL_32:
    v26[0] = 0;
    XML = CRight::GetValidityTimeXML(this, v26, 0);
    if ( XML >= 0 )
    {
      XML = CRight::GetIntervalTimeXML(this, v30, 0);
      if ( XML >= 0 )
      {
        v22 = (unsigned int)(v16 + v26[0] + v30[0] + 51);
        if ( !v32 )
        {
          v10 = v28;
          v8 = v27;
          goto LABEL_49;
        }
        XML = CRight::GetValidityTimeXML(this, v26, (unsigned __int16 **)&Block);
        if ( XML >= 0 )
        {
          XML = CRight::GetIntervalTimeXML(this, v30, &v28);
          if ( XML >= 0 )
          {
            v23 = (unsigned __int16 *)operator new(saturated_mul((unsigned int)v22, 2u));
            v9 = v23;
            if ( !v23 )
            {
              XML = -2147024882;
              goto LABEL_40;
            }
            memset_0(v23, 0, 2 * v22);
            v24 = &Src;
            v25 = (unsigned __int16 *)&Src;
            v10 = v28;
            if ( v28 )
              v25 = v28;
            if ( Block )
              v24 = (const unsigned __int16 *)Block;
            v8 = v27;
            XML = StringCchPrintfW(v9, (unsigned int)v22, v37, v27, v24, v25);
            if ( XML < 0 )
              goto LABEL_5;
            *v32 = v9;
LABEL_49:
            *v34 = v22;
            v9 = 0;
            goto LABEL_5;
          }
        }
      }
    }
    v9 = 0;
    goto LABEL_40;
  }
  v17 = (unsigned __int16 *)operator new(saturated_mul((unsigned int)v16, 2u));
  v27 = v17;
  if ( !v17 )
  {
    XML = -2147024882;
    v9 = v29;
    v8 = 0;
    goto LABEL_4;
  }
  memset_0(v17, 0, 2 * v16);
  v18 = 0;
  while ( 2 )
  {
    if ( v18 < *((_DWORD *)this + 36) && (v19 = *(CDRMCBase **)(*((_QWORD *)this + 17) + 8LL * v18)) != 0 )
    {
      CDRMCBase::AddRef(v19);
      v6 = *(CUser **)(*((_QWORD *)this + 17) + 8LL * v18);
    }
    else
    {
      v6 = 0;
    }
    v26[0] = 0;
    if ( !v6 )
    {
LABEL_31:
      if ( ++v18 >= v12 )
        goto LABEL_32;
      continue;
    }
    break;
  }
  XML = CUser::GetXML(v6, v26, &v31);
  if ( XML < 0 )
  {
    v9 = 0;
    goto LABEL_40;
  }
  v20 = -1;
  do
    ++v20;
  while ( v27[v20] );
  XML = StringCchCopyW(&v27[(unsigned int)v20], (unsigned int)(v16 - v20), v31);
  if ( XML >= 0 )
  {
    operator delete(v21);
    v31 = 0;
    CDRMCBase::Release(v6);
    v6 = 0;
    goto LABEL_31;
  }
  v9 = v29;
LABEL_40:
  v8 = v27;
LABEL_4:
  v10 = v28;
LABEL_5:
  operator delete(v9);
  operator delete(v8);
  operator delete(Block);
  operator delete(v10);
  operator delete(v31);
  if ( v6 )
    CDRMCBase::Release(v6);
  LeaveCriticalSection(v5);
  return (unsigned int)XML;
}

```

## disassembly

```asm
0x18000d1a0  mov     rax, rsp
0x18000d1a3  push    rbp
0x18000d1a4  push    rsi
0x18000d1a5  push    rdi
0x18000d1a6  push    r12
0x18000d1a8  push    r13
0x18000d1aa  push    r14
0x18000d1ac  push    r15
0x18000d1ae  lea     rbp, [rax-48h]
0x18000d1b2  sub     rsp, 110h
0x18000d1b9  mov     [rsp+140h+var_C8], 0FFFFFFFFFFFFFFFEh
0x18000d1c2  mov     [rax+20h], rbx
0x18000d1c6  mov     rax, cs:__security_cookie
0x18000d1cd  xor     rax, rsp
0x18000d1d0  mov     [rbp+40h+var_40], rax
0x18000d1d4  mov     [rsp+140h+var_E0], r8
0x18000d1d9  mov     r15, rdx
0x18000d1dc  mov     [rsp+140h+var_D0], rdx
0x18000d1e1  mov     r14, rcx
0x18000d1e4  lea     rbx, [rcx+58h]
0x18000d1e8  mov     [rbp+40h+var_C0], rbx
0x18000d1ec  mov     rcx, rbx; lpCriticalSection
0x18000d1ef  call    cs:__imp_EnterCriticalSection
0x18000d1f5  nop
0x18000d1f6  xor     edx, edx
0x18000d1f8  mov     [rsp+140h+var_F8], rdx
0x18000d1fd  movaps  xmm0, xmmword ptr cs:aConditionlistA; "<CONDITIONLIST><ACCESS>%s</ACCESS>%s%s<"...
0x18000d204  movaps  xmmword ptr [rbp+40h+var_B0], xmm0
0x18000d208  movaps  xmm1, xmmword ptr cs:aConditionlistA+10h; "ONLIST><ACCESS>%s</ACCESS>%s%s</CONDITI"...
0x18000d20f  movaps  [rbp+40h+var_A0], xmm1
0x18000d213  movaps  xmm0, xmmword ptr cs:aConditionlistA+20h; "ACCESS>%s</ACCESS>%s%s</CONDITIONLIST>"
0x18000d21a  movaps  [rbp+40h+var_90], xmm0
0x18000d21e  movaps  xmm1, xmmword ptr cs:aConditionlistA+30h; "s</ACCESS>%s%s</CONDITIONLIST>"
0x18000d225  movaps  [rbp+40h+var_80], xmm1
0x18000d229  movaps  xmm0, xmmword ptr cs:aConditionlistA+40h; "S>%s%s</CONDITIONLIST>"
0x18000d230  movaps  [rbp+40h+var_70], xmm0
0x18000d234  movaps  xmm1, xmmword ptr cs:aConditionlistA+50h; "CONDITIONLIST>"
0x18000d23b  movaps  xmmword ptr [rbp+40h+var_60], xmm1
0x18000d23f  movups  xmm0, xmmword ptr cs:aConditionlistA+5Eh; "ONLIST>"
0x18000d246  movups  xmmword ptr [rbp+40h+var_60+0Eh], xmm0
0x18000d24a  mov     [rsp+140h+var_108], rdx
0x18000d24f  mov     [rsp+140h+var_E8], rdx
0x18000d254  mov     [rsp+140h+Block], rdx
0x18000d259  mov     [rsp+140h+var_100], rdx
0x18000d25e  mov     [rsp+140h+var_F0], edx
0x18000d262  mov     esi, edx
0x18000d264  test    r15, r15
0x18000d267  jnz     short loc_18000D2E5
0x18000d269  mov     edi, 80070057h
0x18000d26e  mov     r13, rdx
0x18000d271  mov     r14, rdx
0x18000d274  mov     r12, [rsp+140h+var_100]
0x18000d279  mov     rcx, r14; Block
0x18000d27c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d281  mov     rcx, r13; Block
0x18000d284  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d289  mov     rcx, [rsp+140h+Block]; Block
0x18000d28e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d293  mov     rcx, r12; Block
0x18000d296  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d29b  mov     rcx, [rsp+140h+var_E8]; Block
0x18000d2a0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d2a5  test    rsi, rsi
0x18000d2a8  jz      short loc_18000D2B3
0x18000d2aa  mov     rcx, rsi; this
0x18000d2ad  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x18000d2b2  nop
0x18000d2b3  mov     rcx, rbx; lpCriticalSection
0x18000d2b6  call    cs:__imp_LeaveCriticalSection
0x18000d2bc  mov     eax, edi
0x18000d2be  mov     rcx, [rbp+40h+var_40]
0x18000d2c2  xor     rcx, rsp; StackCookie
0x18000d2c5  call    __security_check_cookie
0x18000d2ca  mov     rbx, [rsp+140h+arg_18]
0x18000d2d2  add     rsp, 110h
0x18000d2d9  pop     r15
0x18000d2db  pop     r14
0x18000d2dd  pop     r13
0x18000d2df  pop     r12
0x18000d2e1  pop     rdi
0x18000d2e2  pop     rsi
0x18000d2e3  pop     rbp
0x18000d2e4  retn
0x18000d2e5  mov     edi, edx
0x18000d2e7  mov     r13d, [r14+90h]
0x18000d2ee  mov     [r15], edx
0x18000d2f1  test    r13d, r13d
0x18000d2f4  jz      loc_18000D26E
0x18000d2fa  mov     r12d, edx
0x18000d2fd  mov     r15d, edx
0x18000d300  cmp     r15d, [r14+90h]
0x18000d307  jnb     short loc_18000D360
0x18000d309  mov     esi, r15d
0x18000d30c  mov     rax, [r14+88h]
0x18000d313  mov     rcx, [rax+rsi*8]; this
0x18000d317  test    rcx, rcx
0x18000d31a  jz      short loc_18000D360
0x18000d31c  call    ?AddRef@CDRMCBase@@QEAAKXZ; CDRMCBase::AddRef(void)
0x18000d321  mov     rax, [r14+88h]
0x18000d328  mov     rsi, [rax+rsi*8]
0x18000d32c  xor     edx, edx
0x18000d32e  test    rsi, rsi
0x18000d331  jz      short loc_18000D363
0x18000d333  mov     [rsp+140h+var_110], edx
0x18000d337  xor     r8d, r8d; unsigned __int16 **
0x18000d33a  lea     rdx, [rsp+140h+var_110]; unsigned int *
0x18000d33f  mov     rcx, rsi; this
0x18000d342  call    ?GetXML@CUser@@QEAAJPEAIPEAPEAG@Z; CUser::GetXML(uint *,ushort * *)
0x18000d347  mov     edi, eax
0x18000d349  test    eax, eax
0x18000d34b  js      loc_18000D5D5
0x18000d351  add     r12d, [rsp+140h+var_110]
0x18000d356  mov     rcx, rsi; this
0x18000d359  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x18000d35e  xor     edx, edx
0x18000d360  mov     rsi, rdx
0x18000d363  inc     r15d
0x18000d366  cmp     r15d, r13d
0x18000d369  jb      short loc_18000D300
0x18000d36b  inc     r12d
0x18000d36e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000d372  cmp     [rsp+140h+var_E0], rdx
0x18000d377  jz      loc_18000D482
0x18000d37d  mov     edi, r12d
0x18000d380  lea     eax, [rcx+3]
0x18000d383  mul     rdi
0x18000d386  cmovb   rax, rcx
0x18000d38a  mov     rcx, rax; Size
0x18000d38d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d392  mov     [rsp+140h+var_108], rax
0x18000d397  test    rax, rax
0x18000d39a  jnz     short loc_18000D3AE
0x18000d39c  mov     edi, 8007000Eh
0x18000d3a1  mov     r14, [rsp+140h+var_F8]
0x18000d3a6  mov     r13, rax
0x18000d3a9  jmp     loc_18000D274
0x18000d3ae  lea     r8, [r12+r12]; Size
0x18000d3b2  xor     edx, edx; Val
0x18000d3b4  mov     rcx, rax; void *
0x18000d3b7  call    memset_0
0x18000d3bc  xor     edx, edx
0x18000d3be  mov     r15d, edx
0x18000d3c1  test    r13d, r13d
0x18000d3c4  jz      loc_18000D482
0x18000d3ca  cmp     r15d, [r14+90h]
0x18000d3d1  jnb     short loc_18000D3FA
0x18000d3d3  mov     esi, r15d
0x18000d3d6  mov     rax, [r14+88h]
0x18000d3dd  mov     rcx, [rax+rsi*8]; this
0x18000d3e1  test    rcx, rcx
0x18000d3e4  jz      short loc_18000D3FA
0x18000d3e6  call    ?AddRef@CDRMCBase@@QEAAKXZ; CDRMCBase::AddRef(void)
0x18000d3eb  mov     rax, [r14+88h]
0x18000d3f2  mov     rsi, [rax+rsi*8]
0x18000d3f6  xor     edx, edx
0x18000d3f8  jmp     short loc_18000D3FD
0x18000d3fa  mov     rsi, rdx
0x18000d3fd  mov     [rsp+140h+var_110], edx
0x18000d401  test    rsi, rsi
0x18000d404  jz      short loc_18000D476
0x18000d406  lea     r8, [rsp+140h+var_E8]; unsigned __int16 **
0x18000d40b  lea     rdx, [rsp+140h+var_110]; unsigned int *
0x18000d410  mov     rcx, rsi; this
0x18000d413  call    ?GetXML@CUser@@QEAAJPEAIPEAPEAG@Z; CUser::GetXML(uint *,ushort * *)
0x18000d418  mov     edi, eax
0x18000d41a  xor     eax, eax
0x18000d41c  test    edi, edi
0x18000d41e  js      loc_18000D53A
0x18000d424  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000d428  mov     r8, [rsp+140h+var_108]
0x18000d42d  inc     rcx
0x18000d430  cmp     [r8+rcx*2], ax
0x18000d435  jnz     short loc_18000D42D
0x18000d437  mov     edx, r12d
0x18000d43a  sub     edx, ecx; unsigned __int64
0x18000d43c  mov     eax, ecx
0x18000d43e  lea     rcx, [r8+rax*2]; unsigned __int16 *
0x18000d442  mov     r11, [rsp+140h+var_E8]
0x18000d447  mov     r8, r11; unsigned __int16 *
0x18000d44a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d44f  mov     edi, eax
0x18000d451  test    eax, eax
0x18000d453  js      loc_18000D5CB
0x18000d459  mov     rcx, r11; Block
0x18000d45c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d461  mov     [rsp+140h+var_E8], 0
0x18000d46a  mov     rcx, rsi; this
0x18000d46d  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x18000d472  xor     edx, edx
0x18000d474  mov     esi, edx
0x18000d476  inc     r15d
0x18000d479  cmp     r15d, r13d
0x18000d47c  jb      loc_18000D3CA
0x18000d482  mov     [rsp+140h+var_110], edx
0x18000d486  xor     r8d, r8d; unsigned __int16 **
0x18000d489  lea     rdx, [rsp+140h+var_110]; unsigned int *
0x18000d48e  mov     rcx, r14; this
0x18000d491  call    ?GetValidityTimeXML@CRight@@AEAAJPEAIPEAPEAG@Z; CRight::GetValidityTimeXML(uint *,ushort * *)
0x18000d496  mov     edi, eax
0x18000d498  xor     r13d, r13d
0x18000d49b  test    eax, eax
0x18000d49d  js      loc_18000D5AC
0x18000d4a3  xor     r8d, r8d; unsigned __int16 **
0x18000d4a6  lea     rdx, [rsp+140h+var_F0]; unsigned int *
0x18000d4ab  mov     rcx, r14; this
0x18000d4ae  call    ?GetIntervalTimeXML@CRight@@AEAAJPEAIPEAPEAG@Z; CRight::GetIntervalTimeXML(uint *,ushort * *)
0x18000d4b3  mov     edi, eax
0x18000d4b5  test    eax, eax
0x18000d4b7  js      loc_18000D5AC
0x18000d4bd  mov     r15d, [rsp+140h+var_F0]
0x18000d4c2  add     r15d, 33h ; '3'
0x18000d4c6  add     r15d, [rsp+140h+var_110]
0x18000d4cb  add     r15d, r12d
0x18000d4ce  cmp     [rsp+140h+var_E0], r13
0x18000d4d3  jz      loc_18000D5B1
0x18000d4d9  lea     r8, [rsp+140h+Block]; unsigned __int16 **
0x18000d4de  lea     rdx, [rsp+140h+var_110]; unsigned int *
0x18000d4e3  mov     rcx, r14; this
0x18000d4e6  call    ?GetValidityTimeXML@CRight@@AEAAJPEAIPEAPEAG@Z; CRight::GetValidityTimeXML(uint *,ushort * *)
0x18000d4eb  mov     edi, eax
0x18000d4ed  test    eax, eax
0x18000d4ef  js      loc_18000D5AC
0x18000d4f5  lea     r8, [rsp+140h+var_100]; unsigned __int16 **
0x18000d4fa  lea     rdx, [rsp+140h+var_F0]; unsigned int *
0x18000d4ff  mov     rcx, r14; this
0x18000d502  call    ?GetIntervalTimeXML@CRight@@AEAAJPEAIPEAPEAG@Z; CRight::GetIntervalTimeXML(uint *,ushort * *)
0x18000d507  mov     edi, eax
0x18000d509  test    eax, eax
0x18000d50b  js      loc_18000D5AC
0x18000d511  mov     edi, r15d
0x18000d514  lea     eax, [r13+2]
0x18000d518  mul     rdi
0x18000d51b  lea     rcx, [r13-1]
0x18000d51f  cmovb   rax, rcx
0x18000d523  mov     rcx, rax; Size
0x18000d526  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d52b  mov     r14, rax
0x18000d52e  test    rax, rax
0x18000d531  jnz     short loc_18000D547
0x18000d533  mov     edi, 8007000Eh
0x18000d538  jmp     short loc_18000D53D
0x18000d53a  mov     r14, rax
0x18000d53d  mov     r13, [rsp+140h+var_108]
0x18000d542  jmp     loc_18000D274
0x18000d547  lea     r8, [r15+r15]; Size
0x18000d54b  xor     edx, edx; Val
0x18000d54d  mov     rcx, r14; void *
0x18000d550  call    memset_0
0x18000d555  lea     r8, Src
0x18000d55c  mov     rcx, r8
0x18000d55f  mov     r12, [rsp+140h+var_100]
0x18000d564  test    r12, r12
0x18000d567  cmovnz  rcx, r12
0x18000d56b  mov     rax, [rsp+140h+Block]
0x18000d570  test    rax, rax
0x18000d573  cmovnz  r8, rax
0x18000d577  mov     qword ptr [rsp+140h+var_118], rcx
0x18000d57c  mov     [rsp+140h+var_120], r8
0x18000d581  mov     r13, [rsp+140h+var_108]
0x18000d586  mov     r9, r13
0x18000d589  lea     r8, [rbp+40h+var_B0]; unsigned __int16 *
0x18000d58d  mov     rdx, rdi; unsigned __int64
0x18000d590  mov     rcx, r14; unsigned __int16 *
0x18000d593  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d598  mov     edi, eax
0x18000d59a  test    eax, eax
0x18000d59c  js      loc_18000D279
0x18000d5a2  mov     rax, [rsp+140h+var_E0]
0x18000d5a7  mov     [rax], r14
0x18000d5aa  jmp     short loc_18000D5BB
0x18000d5ac  mov     r14, r13
0x18000d5af  jmp     short loc_18000D53D
0x18000d5b1  mov     r12, [rsp+140h+var_100]
0x18000d5b6  mov     r13, [rsp+140h+var_108]
0x18000d5bb  mov     rax, [rsp+140h+var_D0]
0x18000d5c0  mov     [rax], r15d
0x18000d5c3  xor     r14d, r14d
0x18000d5c6  jmp     loc_18000D279
0x18000d5cb  mov     r14, [rsp+140h+var_F8]
0x18000d5d0  jmp     loc_18000D53D
0x18000d5d5  mov     r14, [rsp+140h+var_F8]
0x18000d5da  mov     r13, r14
0x18000d5dd  jmp     loc_18000D274
```
