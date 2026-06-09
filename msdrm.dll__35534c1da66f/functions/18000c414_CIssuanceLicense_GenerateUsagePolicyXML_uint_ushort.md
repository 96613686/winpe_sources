# CIssuanceLicense::GenerateUsagePolicyXML(uint *,ushort * *)

- ea: `0x18000c414`
- end: `0x18000c980`
- name: `?GenerateUsagePolicyXML@CIssuanceLicense@@AEAAJPEAIPEAPEAG@Z`
- size: `1388`
- prototype: `__int64 __fastcall(CIssuanceLicense *__hidden this, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callers

- `0x18000cd4c`

## callees

- `0x180001284`
- `0x180001290`
- `0x180004654`
- `0x18000c414`
- `0x18000f970`
- `0x180011aa0`
- `0x180012758`
- `0x180017358`
- `0x18001ef30`
- `0x18001ff54`
- `0x18001ffd8`
- `0x18005bd72`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c951`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c951`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c468`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c468`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIssuanceLicense::GenerateUsagePolicyXML(
        CIssuanceLicense *this,
        unsigned int *a2,
        unsigned __int16 **a3)
{
  CIssuanceLicense *v4; // rsi
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  unsigned __int16 *v6; // r12
  int XML; // edi
  void *v8; // r13
  unsigned int v9; // edx
  unsigned int v10; // r14d
  unsigned int v11; // r13d
  unsigned int v12; // r15d
  CDRMCBase *v13; // rcx
  CUsagePolicy *v14; // rsi
  __int64 v15; // r15
  unsigned __int16 **v16; // rcx
  void *v17; // rax
  _WORD *v18; // rax
  __int64 v19; // rax
  unsigned int v20; // edx
  unsigned int v21; // ecx
  CIssuanceLicense *v22; // rax
  __int64 v23; // rsi
  __int64 v24; // rax
  enum _DRM_USAGEPOLICY_TYPE PolicyType; // eax
  __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  unsigned __int16 *v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r14
  unsigned __int16 *v31; // rax
  _WORD *v33; // [rsp+20h] [rbp-E0h]
  unsigned int v34; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int v35; // [rsp+2Ch] [rbp-D4h]
  CIssuanceLicense *v36; // [rsp+30h] [rbp-D0h]
  void *Block; // [rsp+38h] [rbp-C8h] BYREF
  int v38; // [rsp+40h] [rbp-C0h]
  void *v39; // [rsp+48h] [rbp-B8h]
  unsigned int v40; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 **v41; // [rsp+58h] [rbp-A8h]
  _DWORD v42[4]; // [rsp+60h] [rbp-A0h]
  __int64 v43; // [rsp+70h] [rbp-90h]
  unsigned int *v44; // [rsp+78h] [rbp-88h]
  __int64 v45; // [rsp+80h] [rbp-80h]
  char *v46; // [rsp+88h] [rbp-78h]
  unsigned __int16 v47[8]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v48; // [rsp+A0h] [rbp-60h]
  __int128 v49; // [rsp+B0h] [rbp-50h]
  __int128 v50; // [rsp+C0h] [rbp-40h]
  _OWORD v51[2]; // [rsp+D0h] [rbp-30h]
  unsigned __int16 v52[8]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v53; // [rsp+100h] [rbp+0h]
  __int128 v54; // [rsp+110h] [rbp+10h]
  __int128 v55; // [rsp+120h] [rbp+20h]
  _OWORD v56[2]; // [rsp+130h] [rbp+30h]

  v45 = -2;
  v41 = a3;
  v44 = a2;
  v4 = this;
  v36 = this;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  v46 = (char *)this + 88;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v42[0] = 0;
  v42[1] = 1;
  v42[2] = 2;
  v6 = 0;
  v39 = 0;
  v33 = 0;
  Block = 0;
  *(_OWORD *)v47 = *(_OWORD *)L"<POLICYLIST type=\"exclusion\">%s</POLICYLIST>";
  v48 = *(_OWORD *)L"IST type=\"exclusion\">%s</POLICYLIST>";
  v49 = *(_OWORD *)L"=\"exclusion\">%s</POLICYLIST>";
  v50 = *(_OWORD *)L"ion\">%s</POLICYLIST>";
  v51[0] = *(_OWORD *)L"/POLICYLIST>";
  *(_OWORD *)((char *)v51 + 10) = *(_OWORD *)L"CYLIST>";
  *(_OWORD *)v52 = *(_OWORD *)L"<POLICYLIST type=\"inclusion\">%s</POLICYLIST>";
  v53 = *(_OWORD *)L"IST type=\"inclusion\">%s</POLICYLIST>";
  v54 = *(_OWORD *)L"=\"inclusion\">%s</POLICYLIST>";
  v55 = *(_OWORD *)L"ion\">%s</POLICYLIST>";
  v56[0] = *(_OWORD *)L"/POLICYLIST>";
  *(_OWORD *)((char *)v56 + 10) = *(_OWORD *)L"CYLIST>";
  if ( a2 )
  {
    XML = 0;
    v35 = *((_DWORD *)v4 + 38);
    v9 = v35;
    *a2 = 0;
    if ( v9 )
    {
      v10 = 0;
      v11 = 0;
      v12 = 0;
      while ( 1 )
      {
        if ( v12 < *((_DWORD *)v4 + 38) )
        {
          v13 = *(CDRMCBase **)(*((_QWORD *)v36 + 18) + 8LL * v12);
          if ( v13 )
          {
            CDRMCBase::AddRef(v13);
            v14 = *(CUsagePolicy **)(*((_QWORD *)v36 + 18) + 8LL * v12);
            if ( v14 )
            {
              if ( !(unsigned int)CDRMCBase::IsDeleted(v14)
                && CUsagePolicy::GetPolicyType(v14) != DRM_USAGEPOLICY_TYPE_OSEXCLUSION )
              {
                v34 = 0;
                XML = CUsagePolicy::GetXML(v14, &v34, 0);
                if ( XML < 0 )
                {
                  v8 = 0;
LABEL_72:
                  CDRMCBase::Release(v14);
                  goto LABEL_74;
                }
                if ( (unsigned int)CUsagePolicy::IsExcluded(v14) )
                  v10 += v34;
                else
                  v11 += v34;
              }
              CDRMCBase::Release(v14);
            }
            v9 = v35;
          }
        }
        if ( ++v12 >= v9 )
          break;
        v4 = v36;
      }
      if ( v10 || v11 )
      {
        v15 = -1;
        v16 = v41;
        if ( v41 )
        {
          if ( v10 )
          {
            v17 = operator new[](saturated_mul(++v10, 2u));
            v39 = v17;
            if ( !v17 )
            {
              XML = -2147024882;
              v8 = 0;
              goto LABEL_74;
            }
            memset_0(v17, 0, 2LL * v10);
          }
          if ( v11 )
          {
            v18 = operator new[](saturated_mul(++v11, 2u));
            v33 = v18;
            if ( !v18 )
            {
              XML = -2147024882;
              v8 = 0;
              goto LABEL_74;
            }
            memset_0(v18, 0, 2LL * v11);
          }
          v19 = 0;
          v38 = 0;
          v20 = v35;
          while ( 2 )
          {
            v21 = 0;
            v34 = 0;
            v43 = v19;
            v22 = v36;
            do
            {
              if ( v21 < *((_DWORD *)v22 + 38) )
              {
                v23 = v21;
                v24 = *((_QWORD *)v22 + 18);
                if ( *(_QWORD *)(v24 + 8LL * v21) )
                {
                  CDRMCBase::AddRef(*(CDRMCBase **)(v24 + 8LL * v21));
                  v14 = *(CUsagePolicy **)(*((_QWORD *)v36 + 18) + 8 * v23);
                  if ( v14 )
                  {
                    if ( !(unsigned int)CDRMCBase::IsDeleted(v14) )
                    {
                      PolicyType = CUsagePolicy::GetPolicyType(v14);
                      if ( v42[v43] == PolicyType )
                      {
                        v40 = 0;
                        XML = CUsagePolicy::GetXML(v14, &v40, (unsigned __int16 **)&Block);
                        if ( XML < 0 )
                          goto LABEL_60;
                        if ( Block )
                        {
                          if ( (unsigned int)CUsagePolicy::IsExcluded(v14) )
                          {
                            v26 = -1;
                            do
                              ++v26;
                            while ( *((_WORD *)v39 + v26) );
                            v27 = v10 - (unsigned int)v26;
                            v28 = (unsigned __int16 *)((char *)v39 + 2 * (unsigned int)v26);
                          }
                          else
                          {
                            v29 = -1;
                            do
                              ++v29;
                            while ( v33[v29] );
                            v27 = v11 - (unsigned int)v29;
                            v28 = &v33[(unsigned int)v29];
                          }
                          XML = StringCchCopyW(v28, v27, (unsigned __int16 *)Block);
                          if ( XML < 0 )
                          {
LABEL_60:
                            v8 = v33;
                            goto LABEL_72;
                          }
                        }
                      }
                    }
                    CDRMCBase::Release(v14);
                    operator delete(Block);
                    Block = 0;
                  }
                  v20 = v35;
                  v21 = v34;
                }
                v22 = v36;
              }
              v34 = ++v21;
            }
            while ( v21 < v20 );
            v19 = (unsigned int)(v38 + 1);
            v38 = v19;
            if ( (unsigned int)v19 < 3 )
              continue;
            break;
          }
          v16 = v41;
        }
        v30 = v10 != 0 ? v10 + 42 : 0;
        if ( v11 )
          v30 = v11 + (_DWORD)v30 + 42;
        if ( !v16 )
        {
          v8 = v33;
          goto LABEL_68;
        }
        v31 = (unsigned __int16 *)operator new[](saturated_mul((unsigned int)v30, 2u));
        v6 = v31;
        if ( !v31 )
        {
          XML = -2147024882;
LABEL_58:
          v8 = v33;
          goto LABEL_74;
        }
        memset_0(v31, 0, 2 * v30);
        if ( v39 )
        {
          XML = StringCchPrintfW(v6, (unsigned int)v30, v47, v39);
          if ( XML < 0 )
            goto LABEL_58;
        }
        do
          ++v15;
        while ( v6[v15] );
        v8 = v33;
        if ( !v33 || (XML = StringCchPrintfW(&v6[(unsigned int)v15], (unsigned int)(v30 - v15), v52, v33), XML >= 0) )
        {
          *v41 = v6;
LABEL_68:
          *v44 = v30;
          v6 = 0;
        }
      }
      else
      {
        v8 = 0;
      }
    }
    else
    {
      v8 = 0;
    }
  }
  else
  {
    XML = -2147024809;
    v8 = 0;
  }
LABEL_74:
  operator delete(Block);
  operator delete(v39);
  operator delete(v8);
  operator delete(v6);
  LeaveCriticalSection(v5);
  return (unsigned int)XML;
}

```

## disassembly

```asm
0x18000c414  mov     rax, rsp
0x18000c417  push    rbp
0x18000c418  push    rsi
0x18000c419  push    rdi
0x18000c41a  push    r12
0x18000c41c  push    r13
0x18000c41e  push    r14
0x18000c420  push    r15
0x18000c422  lea     rbp, [rsp-60h]
0x18000c427  sub     rsp, 160h
0x18000c42e  mov     [rbp+90h+var_110], 0FFFFFFFFFFFFFFFEh
0x18000c436  mov     [rax+20h], rbx
0x18000c43a  mov     rax, cs:__security_cookie
0x18000c441  xor     rax, rsp
0x18000c444  mov     [rbp+90h+var_40], rax
0x18000c448  mov     [rsp+190h+var_138], r8
0x18000c44d  mov     r14, rdx
0x18000c450  mov     [rsp+190h+var_118], rdx
0x18000c455  mov     rsi, rcx
0x18000c458  mov     [rsp+190h+var_160], rcx
0x18000c45d  lea     rbx, [rcx+58h]
0x18000c461  mov     [rbp+90h+var_108], rbx
0x18000c465  mov     rcx, rbx; lpCriticalSection
0x18000c468  call    cs:__imp_EnterCriticalSection
0x18000c46e  nop
0x18000c46f  xor     r8d, r8d
0x18000c472  mov     [rsp+190h+var_130], r8d
0x18000c477  mov     [rsp+190h+var_12C], 1
0x18000c47f  mov     [rsp+190h+var_128], 2
0x18000c487  mov     r12d, r8d
0x18000c48a  mov     [rsp+190h+var_148], r8
0x18000c48f  mov     [rsp+190h+var_170], r8
0x18000c494  mov     [rsp+190h+Block], r8
0x18000c499  movaps  xmm0, xmmword ptr cs:aPolicylistType; "<POLICYLIST type=\"exclusion\">%s</POLI"...
0x18000c4a0  movaps  xmmword ptr [rbp+90h+var_100], xmm0
0x18000c4a4  movaps  xmm1, xmmword ptr cs:aPolicylistType+10h; "IST type=\"exclusion\">%s</POLICYLIST>"
0x18000c4ab  movaps  [rbp+90h+var_F0], xmm1
0x18000c4af  movaps  xmm0, xmmword ptr cs:aPolicylistType+20h; "=\"exclusion\">%s</POLICYLIST>"
0x18000c4b6  movaps  [rbp+90h+var_E0], xmm0
0x18000c4ba  movaps  xmm1, xmmword ptr cs:aPolicylistType+30h; "ion\">%s</POLICYLIST>"
0x18000c4c1  movaps  [rbp+90h+var_D0], xmm1
0x18000c4c5  movaps  xmm0, xmmword ptr cs:aPolicylistType+40h; "/POLICYLIST>"
0x18000c4cc  movaps  xmmword ptr [rbp+90h+var_C0], xmm0
0x18000c4d0  movups  xmm1, xmmword ptr cs:aPolicylistType+4Ah; "CYLIST>"
0x18000c4d7  movups  xmmword ptr [rbp+90h+var_C0+0Ah], xmm1
0x18000c4db  movaps  xmm0, xmmword ptr cs:aPolicylistType_0; "<POLICYLIST type=\"inclusion\">%s</POLI"...
0x18000c4e2  movaps  xmmword ptr [rbp+90h+var_A0], xmm0
0x18000c4e6  movaps  xmm1, xmmword ptr cs:aPolicylistType_0+10h; "IST type=\"inclusion\">%s</POLICYLIST>"
0x18000c4ed  movaps  [rbp+90h+var_90], xmm1
0x18000c4f1  movaps  xmm0, xmmword ptr cs:aPolicylistType_0+20h; "=\"inclusion\">%s</POLICYLIST>"
0x18000c4f8  movaps  [rbp+90h+var_80], xmm0
0x18000c4fc  movaps  xmm1, xmmword ptr cs:aPolicylistType_0+30h; "ion\">%s</POLICYLIST>"
0x18000c503  movaps  [rbp+90h+var_70], xmm1
0x18000c507  movaps  xmm0, xmmword ptr cs:aPolicylistType_0+40h; "/POLICYLIST>"
0x18000c50e  movaps  xmmword ptr [rbp+90h+var_60], xmm0
0x18000c512  movups  xmm1, xmmword ptr cs:aPolicylistType_0+4Ah; "CYLIST>"
0x18000c519  movups  xmmword ptr [rbp+90h+var_60+0Ah], xmm1
0x18000c51d  test    r14, r14
0x18000c520  jnz     short loc_18000C52F
0x18000c522  mov     edi, 80070057h
0x18000c527  mov     r13d, r8d
0x18000c52a  jmp     loc_18000C929
0x18000c52f  mov     edi, r8d
0x18000c532  mov     edx, [rsi+98h]
0x18000c538  mov     [rsp+190h+var_164], edx
0x18000c53c  mov     [r14], r8d
0x18000c53f  test    edx, edx
0x18000c541  jz      loc_18000C926
0x18000c547  mov     r14d, r8d
0x18000c54a  mov     r13d, r8d
0x18000c54d  mov     r15d, r8d
0x18000c550  jmp     short loc_18000C557
0x18000c552  mov     rsi, [rsp+190h+var_160]
0x18000c557  cmp     r15d, [rsi+98h]
0x18000c55e  jb      short loc_18000C568
0x18000c560  mov     rsi, r8
0x18000c563  jmp     loc_18000C5FF
0x18000c568  mov     esi, r15d
0x18000c56b  mov     rax, [rsp+190h+var_160]
0x18000c570  mov     rax, [rax+90h]
0x18000c577  mov     rcx, [rax+rsi*8]; this
0x18000c57b  test    rcx, rcx
0x18000c57e  jz      short loc_18000C560
0x18000c580  call    ?AddRef@CDRMCBase@@QEAAKXZ; CDRMCBase::AddRef(void)
0x18000c585  mov     rcx, [rsp+190h+var_160]
0x18000c58a  mov     rax, [rcx+90h]
0x18000c591  mov     rsi, [rax+rsi*8]
0x18000c595  xor     r8d, r8d
0x18000c598  test    rsi, rsi
0x18000c59b  jz      short loc_18000C5FB
0x18000c59d  mov     rcx, rsi; this
0x18000c5a0  call    ?IsDeleted@CDRMCBase@@QEAAHXZ; CDRMCBase::IsDeleted(void)
0x18000c5a5  test    eax, eax
0x18000c5a7  jnz     short loc_18000C5ED
0x18000c5a9  mov     rcx, rsi; this
0x18000c5ac  call    ?GetPolicyType@CUsagePolicy@@QEAA?AW4_DRM_USAGEPOLICY_TYPE@@XZ; CUsagePolicy::GetPolicyType(void)
0x18000c5b1  cmp     eax, 3
0x18000c5b4  jz      short loc_18000C5ED
0x18000c5b6  mov     [rsp+190h+var_168], r12d
0x18000c5bb  xor     r8d, r8d; unsigned __int16 **
0x18000c5be  lea     rdx, [rsp+190h+var_168]; unsigned int *
0x18000c5c3  mov     rcx, rsi; this
0x18000c5c6  call    ?GetXML@CUsagePolicy@@QEAAJPEAIPEAPEAG@Z; CUsagePolicy::GetXML(uint *,ushort * *)
0x18000c5cb  mov     edi, eax
0x18000c5cd  test    eax, eax
0x18000c5cf  js      loc_18000C919
0x18000c5d5  mov     rcx, rsi; this
0x18000c5d8  call    ?IsExcluded@CUsagePolicy@@QEAAHXZ; CUsagePolicy::IsExcluded(void)
0x18000c5dd  test    eax, eax
0x18000c5df  jz      short loc_18000C5E8
0x18000c5e1  add     r14d, [rsp+190h+var_168]
0x18000c5e6  jmp     short loc_18000C5ED
0x18000c5e8  add     r13d, [rsp+190h+var_168]
0x18000c5ed  mov     rcx, rsi; this
0x18000c5f0  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x18000c5f5  xor     r8d, r8d
0x18000c5f8  mov     esi, r8d
0x18000c5fb  mov     edx, [rsp+190h+var_164]
0x18000c5ff  inc     r15d
0x18000c602  cmp     r15d, edx
0x18000c605  jb      loc_18000C552
0x18000c60b  test    r14d, r14d
0x18000c60e  jnz     short loc_18000C619
0x18000c610  test    r13d, r13d
0x18000c613  jz      loc_18000C90F
0x18000c619  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000c61d  mov     rcx, [rsp+190h+var_138]
0x18000c622  test    rcx, rcx
0x18000c625  jz      loc_18000C824
0x18000c62b  test    r14d, r14d
0x18000c62e  jz      short loc_18000C676
0x18000c630  inc     r14d
0x18000c633  mov     ecx, r14d
0x18000c636  lea     eax, [r15+3]
0x18000c63a  mul     rcx
0x18000c63d  cmovb   rax, r15
0x18000c641  mov     rcx, rax; unsigned __int64
0x18000c644  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000c649  mov     [rsp+190h+var_148], rax
0x18000c64e  xor     r8d, r8d
0x18000c651  test    rax, rax
0x18000c654  jnz     short loc_18000C663
0x18000c656  mov     edi, 8007000Eh
0x18000c65b  mov     r13d, r8d
0x18000c65e  jmp     loc_18000C912
0x18000c663  mov     r8d, r14d
0x18000c666  add     r8, r8; Size
0x18000c669  xor     edx, edx; Val
0x18000c66b  mov     rcx, rax; void *
0x18000c66e  call    memset_0
0x18000c673  xor     r8d, r8d
0x18000c676  test    r13d, r13d
0x18000c679  jz      short loc_18000C6BF
0x18000c67b  inc     r13d
0x18000c67e  mov     ecx, r13d
0x18000c681  mov     eax, 2
0x18000c686  mul     rcx
0x18000c689  cmovb   rax, r15
0x18000c68d  mov     rcx, rax; unsigned __int64
0x18000c690  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000c695  mov     [rsp+190h+var_170], rax
0x18000c69a  test    rax, rax
0x18000c69d  jnz     short loc_18000C6AC
0x18000c69f  mov     edi, 8007000Eh
0x18000c6a4  mov     r13, rax
0x18000c6a7  jmp     loc_18000C912
0x18000c6ac  mov     r8d, r13d
0x18000c6af  add     r8, r8; Size
0x18000c6b2  xor     edx, edx; Val
0x18000c6b4  mov     rcx, rax; void *
0x18000c6b7  call    memset_0
0x18000c6bc  xor     r8d, r8d
0x18000c6bf  mov     eax, r8d
0x18000c6c2  mov     [rsp+190h+var_150], eax
0x18000c6c6  mov     edx, [rsp+190h+var_164]
0x18000c6ca  mov     ecx, r8d
0x18000c6cd  mov     [rsp+190h+var_168], ecx
0x18000c6d1  mov     [rsp+190h+var_120], rax
0x18000c6d6  mov     rax, [rsp+190h+var_160]
0x18000c6db  cmp     ecx, [rax+98h]
0x18000c6e1  jb      short loc_18000C6EB
0x18000c6e3  mov     rsi, r8
0x18000c6e6  jmp     loc_18000C7FE
0x18000c6eb  mov     esi, ecx
0x18000c6ed  mov     rax, [rax+90h]
0x18000c6f4  cmp     [rax+rsi*8], r8
0x18000c6f8  jz      loc_18000C874
0x18000c6fe  mov     rcx, [rax+rsi*8]; this
0x18000c702  call    ?AddRef@CDRMCBase@@QEAAKXZ; CDRMCBase::AddRef(void)
0x18000c707  mov     rcx, [rsp+190h+var_160]
0x18000c70c  mov     rax, [rcx+90h]
0x18000c713  mov     rsi, [rax+rsi*8]
0x18000c717  xor     r8d, r8d
0x18000c71a  test    rsi, rsi
0x18000c71d  jz      loc_18000C7F1
0x18000c723  mov     rcx, rsi; this
0x18000c726  call    ?IsDeleted@CDRMCBase@@QEAAHXZ; CDRMCBase::IsDeleted(void)
0x18000c72b  test    eax, eax
0x18000c72d  jnz     loc_18000C7D5
0x18000c733  mov     rcx, rsi; this
0x18000c736  call    ?GetPolicyType@CUsagePolicy@@QEAA?AW4_DRM_USAGEPOLICY_TYPE@@XZ; CUsagePolicy::GetPolicyType(void)
0x18000c73b  mov     rcx, [rsp+190h+var_120]
0x18000c740  cmp     [rsp+rcx*4+190h+var_130], eax
0x18000c744  jnz     loc_18000C7D5
0x18000c74a  mov     [rsp+190h+var_140], r12d
0x18000c74f  lea     r8, [rsp+190h+Block]; unsigned __int16 **
0x18000c754  lea     rdx, [rsp+190h+var_140]; unsigned int *
0x18000c759  mov     rcx, rsi; this
0x18000c75c  call    ?GetXML@CUsagePolicy@@QEAAJPEAIPEAPEAG@Z; CUsagePolicy::GetXML(uint *,ushort * *)
0x18000c761  mov     edi, eax
0x18000c763  xor     eax, eax
0x18000c765  test    edi, edi
0x18000c767  js      loc_18000C879
0x18000c76d  cmp     [rsp+190h+Block], rax
0x18000c772  jz      short loc_18000C7D5
0x18000c774  mov     rcx, rsi; this
0x18000c777  call    ?IsExcluded@CUsagePolicy@@QEAAHXZ; CUsagePolicy::IsExcluded(void)
0x18000c77c  xor     r11d, r11d
0x18000c77f  test    eax, eax
0x18000c781  jz      short loc_18000C7A2
0x18000c783  mov     rcx, r15
0x18000c786  mov     r8, [rsp+190h+var_148]
0x18000c78b  inc     rcx
0x18000c78e  cmp     [r8+rcx*2], r11w
0x18000c793  jnz     short loc_18000C78B
0x18000c795  mov     edx, r14d
0x18000c798  sub     edx, ecx
0x18000c79a  mov     eax, ecx
0x18000c79c  lea     rcx, [r8+rax*2]
0x18000c7a0  jmp     short loc_18000C7C1
0x18000c7a2  mov     r8, r15
0x18000c7a5  mov     rcx, [rsp+190h+var_170]
0x18000c7aa  inc     r8
0x18000c7ad  cmp     [rcx+r8*2], r11w
0x18000c7b2  jnz     short loc_18000C7AA
0x18000c7b4  mov     edx, r13d
0x18000c7b7  sub     edx, r8d; unsigned __int64
0x18000c7ba  mov     eax, r8d
0x18000c7bd  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x18000c7c1  mov     r8, [rsp+190h+Block]; unsigned __int16 *
0x18000c7c6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c7cb  test    eax, eax
0x18000c7cd  mov     edi, eax
0x18000c7cf  js      loc_18000C879
0x18000c7d5  mov     rcx, rsi; this
0x18000c7d8  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x18000c7dd  xor     esi, esi
0x18000c7df  mov     rcx, [rsp+190h+Block]; Block
0x18000c7e4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c7e9  xor     r8d, r8d
0x18000c7ec  mov     [rsp+190h+Block], r8
0x18000c7f1  mov     edx, [rsp+190h+var_164]
0x18000c7f5  mov     ecx, [rsp+190h+var_168]
0x18000c7f9  mov     rax, [rsp+190h+var_160]
0x18000c7fe  inc     ecx
0x18000c800  mov     [rsp+190h+var_168], ecx
0x18000c804  cmp     ecx, edx
0x18000c806  jb      loc_18000C6DB
0x18000c80c  mov     eax, [rsp+190h+var_150]
0x18000c810  inc     eax
0x18000c812  mov     [rsp+190h+var_150], eax
0x18000c816  cmp     eax, 3
0x18000c819  jb      loc_18000C6CA
0x18000c81f  mov     rcx, [rsp+190h+var_138]
0x18000c824  lea     eax, [r14+2Ah]
0x18000c828  neg     r14d
0x18000c82b  sbb     r14d, r14d
0x18000c82e  and     r14d, eax
0x18000c831  test    r13d, r13d
0x18000c834  jz      short loc_18000C83D
0x18000c836  add     r14d, 2Ah ; '*'
0x18000c83a  add     r14d, r13d
0x18000c83d  test    rcx, rcx
0x18000c840  jz      loc_18000C8FD
0x18000c846  mov     r13d, r14d
0x18000c849  mov     eax, 2
0x18000c84e  mul     r13
0x18000c851  cmovb   rax, r15
0x18000c855  mov     rcx, rax; unsigned __int64
0x18000c858  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000c85d  mov     r12, rax
0x18000c860  test    rax, rax
0x18000c863  jnz     short loc_18000C883
0x18000c865  mov     edi, 8007000Eh
0x18000c86a  mov     r13, [rsp+190h+var_170]
0x18000c86f  jmp     loc_18000C912
0x18000c874  mov     rsi, r8
0x18000c877  jmp     short loc_18000C7F9
0x18000c879  mov     r13, [rsp+190h+var_170]
0x18000c87e  jmp     loc_18000C91C
0x18000c883  lea     r8, ds:0[r14*2]; Size
0x18000c88b  xor     edx, edx; Val
0x18000c88d  mov     rcx, r12; void *
0x18000c890  call    memset_0
0x18000c895  mov     rax, [rsp+190h+var_148]
0x18000c89a  xor     r8d, r8d
0x18000c89d  test    rax, rax
0x18000c8a0  jz      short loc_18000C8BD
0x18000c8a2  mov     r9, rax
0x18000c8a5  lea     r8, [rbp+90h+var_100]; unsigned __int16 *
  ... truncated ...
```
