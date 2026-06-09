# CIssuanceLicense::GenerateRefreshConditionXML(uint *,ushort * *)

- ea: `0x18000bc94`
- end: `0x18000c082`
- name: `?GenerateRefreshConditionXML@CIssuanceLicense@@AEAAJPEAIPEAPEAG@Z`
- size: `1006`
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
- `0x18000bc94`
- `0x18000f794`
- `0x18000f970`
- `0x1800111fc`
- `0x180017358`
- `0x18001ef30`
- `0x18001ff54`
- `0x18001ffd8`
- `0x18005bd72`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c053`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c053`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bce0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bce0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIssuanceLicense::GenerateRefreshConditionXML(
        CIssuanceLicense *this,
        unsigned int *a2,
        unsigned __int16 **a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  unsigned __int16 *v6; // r13
  int OSExclusionXML; // edi
  unsigned __int16 *v8; // r14
  unsigned int v9; // r14d
  unsigned int v10; // r12d
  CDRMCBase *v11; // rcx
  CUsagePolicy *v12; // rsi
  unsigned int v13; // ecx
  unsigned int v14; // eax
  void *v15; // rax
  unsigned int i; // r14d
  CDRMCBase *v17; // rcx
  __int64 v18; // rcx
  void *v19; // r11
  __int64 v20; // rdi
  unsigned __int16 *v21; // rax
  unsigned int v23[2]; // [rsp+38h] [rbp-89h] BYREF
  unsigned __int16 *v24; // [rsp+40h] [rbp-81h] BYREF
  unsigned int v25; // [rsp+48h] [rbp-79h]
  unsigned int v26[3]; // [rsp+4Ch] [rbp-75h] BYREF
  void *Block; // [rsp+58h] [rbp-69h] BYREF
  unsigned __int16 **v28; // [rsp+60h] [rbp-61h]
  CRevocation *v29; // [rsp+68h] [rbp-59h]
  unsigned int *v30; // [rsp+70h] [rbp-51h]
  __int64 v31; // [rsp+78h] [rbp-49h]
  char *v32; // [rsp+80h] [rbp-41h]
  unsigned __int16 v33[8]; // [rsp+88h] [rbp-39h] BYREF
  __int128 v34; // [rsp+98h] [rbp-29h]
  __int128 v35; // [rsp+A8h] [rbp-19h]
  __int128 v36; // [rsp+B8h] [rbp-9h]
  __int64 v37; // [rsp+C8h] [rbp+7h]

  v31 = -2;
  v28 = a3;
  v30 = a2;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  v32 = (char *)this + 88;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v6 = 0;
  Block = 0;
  v24 = 0;
  v23[0] = 0;
  memset(v26, 0, sizeof(v26));
  *(_OWORD *)v33 = *(_OWORD *)L"<CONDITIONLIST>%s%s</CONDITIONLIST>";
  v34 = *(_OWORD *)L"ONLIST>%s%s</CONDITIONLIST>";
  v35 = *(_OWORD *)L"s%s</CONDITIONLIST>";
  v36 = *(_OWORD *)L"DITIONLIST>";
  v37 = *(_QWORD *)L"ST>";
  if ( a2 )
  {
    v9 = 0;
    v25 = 0;
    v10 = *((_DWORD *)this + 38);
    *a2 = 0;
    if ( v10 )
    {
      while ( 1 )
      {
        if ( v9 < *((_DWORD *)this + 38) )
        {
          v11 = *(CDRMCBase **)(*((_QWORD *)this + 18) + 8LL * v9);
          if ( v11 )
          {
            CDRMCBase::AddRef(v11);
            v12 = *(CUsagePolicy **)(*((_QWORD *)this + 18) + 8LL * v9);
            if ( v12 )
            {
              if ( !(unsigned int)CDRMCBase::IsDeleted(v12)
                && CUsagePolicy::GetPolicyType(v12) == DRM_USAGEPOLICY_TYPE_OSEXCLUSION )
              {
                v23[0] = 0;
                OSExclusionXML = CUsagePolicy::GetOSExclusionXML(v12, v23, 0);
                if ( OSExclusionXML < 0 )
                {
LABEL_43:
                  v8 = v24;
                  CDRMCBase::Release(v12);
                  goto LABEL_44;
                }
                v25 += v23[0];
              }
              CDRMCBase::Release(v12);
            }
          }
        }
        if ( ++v9 >= v10 )
        {
          v9 = v25;
          break;
        }
      }
    }
    v29 = (CIssuanceLicense *)((char *)this + 400);
    OSExclusionXML = CRevocation::GetXML((CIssuanceLicense *)((char *)this + 400), v26, 0);
    if ( OSExclusionXML < 0 || (v13 = v9 + v26[0]) == 0 )
    {
LABEL_20:
      v8 = v24;
      goto LABEL_44;
    }
    v14 = v13 + 35;
    v26[0] = v13 + 35;
    if ( v28 )
    {
      if ( v9 )
      {
        v15 = operator new[](saturated_mul(v9, 2u));
        *(_QWORD *)&v26[1] = v15;
        if ( !v15 )
        {
LABEL_19:
          OSExclusionXML = -2147024882;
          goto LABEL_20;
        }
        memset_0(v15, 0, 2LL * v9);
        if ( v10 )
        {
          for ( i = 0; i < v10; ++i )
          {
            if ( i < *((_DWORD *)this + 38) )
            {
              v17 = *(CDRMCBase **)(*((_QWORD *)this + 18) + 8LL * i);
              if ( v17 )
              {
                CDRMCBase::AddRef(v17);
                v12 = *(CUsagePolicy **)(*((_QWORD *)this + 18) + 8LL * i);
                if ( v12 )
                {
                  if ( !(unsigned int)CDRMCBase::IsDeleted(v12)
                    && CUsagePolicy::GetPolicyType(v12) == DRM_USAGEPOLICY_TYPE_OSEXCLUSION )
                  {
                    v23[0] = 0;
                    OSExclusionXML = CUsagePolicy::GetOSExclusionXML(v12, v23, (unsigned __int16 **)&Block);
                    if ( OSExclusionXML < 0 )
                      goto LABEL_43;
                    v18 = -1;
                    do
                      ++v18;
                    while ( *(_WORD *)(*(_QWORD *)&v26[1] + 2 * v18) );
                    OSExclusionXML = StringCchCopyW(
                                       (unsigned __int16 *)(*(_QWORD *)&v26[1] + 2LL * (unsigned int)v18),
                                       v25 - (unsigned int)v18,
                                       (unsigned __int16 *)Block);
                    if ( OSExclusionXML < 0 )
                      goto LABEL_43;
                    operator delete(v19);
                    Block = 0;
                  }
                  CDRMCBase::Release(v12);
                }
              }
            }
          }
        }
      }
      OSExclusionXML = CRevocation::GetXML(v29, v23, &v24);
      if ( OSExclusionXML < 0 )
        goto LABEL_20;
      v20 = v26[0];
      v21 = (unsigned __int16 *)operator new[](saturated_mul(v26[0], 2u));
      v6 = v21;
      if ( !v21 )
        goto LABEL_19;
      memset_0(v21, 0, 2 * v20);
      v8 = v24;
      OSExclusionXML = StringCchPrintfW(v6, (unsigned int)v20, v33);
      if ( OSExclusionXML < 0 )
        goto LABEL_44;
      *v28 = v6;
      v14 = v26[0];
    }
    else
    {
      v8 = v24;
    }
    *v30 = v14;
    v6 = 0;
    goto LABEL_44;
  }
  OSExclusionXML = -2147024809;
  v8 = 0;
LABEL_44:
  operator delete(v6);
  operator delete(Block);
  operator delete(v8);
  operator delete(*(void **)&v26[1]);
  LeaveCriticalSection(v5);
  return (unsigned int)OSExclusionXML;
}

```

## disassembly

```asm
0x18000bc94  mov     rax, rsp
0x18000bc97  push    rbp
0x18000bc98  push    rsi
0x18000bc99  push    rdi
0x18000bc9a  push    r12
0x18000bc9c  push    r13
0x18000bc9e  push    r14
0x18000bca0  push    r15
0x18000bca2  lea     rbp, [rax-5Fh]
0x18000bca6  sub     rsp, 0E0h
0x18000bcad  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFEh
0x18000bcb5  mov     [rax+20h], rbx
0x18000bcb9  mov     rax, cs:__security_cookie
0x18000bcc0  xor     rax, rsp
0x18000bcc3  mov     [rbp+57h+var_40], rax
0x18000bcc7  mov     [rbp+57h+var_B8], r8
0x18000bccb  mov     rdi, rdx
0x18000bcce  mov     [rbp+57h+var_A8], rdx
0x18000bcd2  mov     r15, rcx
0x18000bcd5  lea     rbx, [rcx+58h]
0x18000bcd9  mov     [rbp+57h+var_98], rbx
0x18000bcdd  mov     rcx, rbx; lpCriticalSection
0x18000bce0  call    cs:__imp_EnterCriticalSection
0x18000bce6  nop
0x18000bce7  xor     edx, edx
0x18000bce9  mov     r13d, edx
0x18000bcec  mov     [rbp+57h+Block], rdx
0x18000bcf0  mov     [rsp+110h+var_D8], rdx
0x18000bcf5  mov     qword ptr [rbp+57h+var_CC+4], rdx
0x18000bcf9  mov     [rsp+110h+var_E0], edx
0x18000bcfd  mov     dword ptr [rbp+57h+var_CC], edx
0x18000bd00  movaps  xmm0, xmmword ptr cs:aConditionlistS; "<CONDITIONLIST>%s%s</CONDITIONLIST>"
0x18000bd07  movaps  xmmword ptr [rbp+57h+var_90], xmm0
0x18000bd0b  movaps  xmm1, xmmword ptr cs:aConditionlistS+10h; "ONLIST>%s%s</CONDITIONLIST>"
0x18000bd12  movaps  [rbp+57h+var_80], xmm1
0x18000bd16  movaps  xmm0, xmmword ptr cs:aConditionlistS+20h; "s%s</CONDITIONLIST>"
0x18000bd1d  movaps  [rbp+57h+var_70], xmm0
0x18000bd21  movaps  xmm1, xmmword ptr cs:aConditionlistS+30h; "DITIONLIST>"
0x18000bd28  movaps  [rbp+57h+var_60], xmm1
0x18000bd2c  movsd   xmm0, qword ptr cs:aConditionlistS+40h; "ST>"
0x18000bd34  movsd   [rbp+57h+var_50], xmm0
0x18000bd39  test    rdi, rdi
0x18000bd3c  jnz     short loc_18000BD4B
0x18000bd3e  mov     edi, 80070057h
0x18000bd43  mov     r14d, edx
0x18000bd46  jmp     loc_18000C02D
0x18000bd4b  mov     rsi, rdx
0x18000bd4e  mov     r14d, edx
0x18000bd51  mov     [rbp+57h+var_D0], edx
0x18000bd54  mov     r12d, [r15+98h]
0x18000bd5b  mov     [rdi], edx
0x18000bd5d  test    r12d, r12d
0x18000bd60  jz      loc_18000BDF9
0x18000bd66  cmp     r14d, [r15+98h]
0x18000bd6d  jnb     short loc_18000BDE6
0x18000bd6f  mov     esi, r14d
0x18000bd72  mov     rax, [r15+90h]
0x18000bd79  mov     rcx, [rax+rsi*8]; this
0x18000bd7d  test    rcx, rcx
0x18000bd80  jz      short loc_18000BDE6
0x18000bd82  call    ?AddRef@CDRMCBase@@QEAAKXZ; CDRMCBase::AddRef(void)
0x18000bd87  mov     rax, [r15+90h]
0x18000bd8e  mov     rsi, [rax+rsi*8]
0x18000bd92  xor     edx, edx
0x18000bd94  test    rsi, rsi
0x18000bd97  jz      short loc_18000BDE9
0x18000bd99  mov     rcx, rsi; this
0x18000bd9c  call    ?IsDeleted@CDRMCBase@@QEAAHXZ; CDRMCBase::IsDeleted(void)
0x18000bda1  xor     edi, edi
0x18000bda3  test    eax, eax
0x18000bda5  jnz     short loc_18000BDDC
0x18000bda7  mov     rcx, rsi; this
0x18000bdaa  call    ?GetPolicyType@CUsagePolicy@@QEAA?AW4_DRM_USAGEPOLICY_TYPE@@XZ; CUsagePolicy::GetPolicyType(void)
0x18000bdaf  cmp     eax, 3
0x18000bdb2  jnz     short loc_18000BDDC
0x18000bdb4  mov     [rsp+110h+var_E0], edi
0x18000bdb8  xor     r8d, r8d; unsigned __int16 **
0x18000bdbb  lea     rdx, [rsp+110h+var_E0]; unsigned int *
0x18000bdc0  mov     rcx, rsi; this
0x18000bdc3  call    ?GetOSExclusionXML@CUsagePolicy@@QEAAJPEAIPEAPEAG@Z; CUsagePolicy::GetOSExclusionXML(uint *,ushort * *)
0x18000bdc8  mov     edi, eax
0x18000bdca  test    eax, eax
0x18000bdcc  js      loc_18000C020
0x18000bdd2  mov     eax, [rbp+57h+var_D0]
0x18000bdd5  add     eax, [rsp+110h+var_E0]
0x18000bdd9  mov     [rbp+57h+var_D0], eax
0x18000bddc  mov     rcx, rsi; this
0x18000bddf  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x18000bde4  xor     edx, edx
0x18000bde6  mov     rsi, rdx
0x18000bde9  inc     r14d
0x18000bdec  cmp     r14d, r12d
0x18000bdef  jb      loc_18000BD66
0x18000bdf5  mov     r14d, [rbp+57h+var_D0]
0x18000bdf9  lea     rax, [r15+190h]
0x18000be00  mov     [rbp+57h+var_B0], rax
0x18000be04  xor     r8d, r8d; unsigned __int16 **
0x18000be07  lea     rdx, [rbp+57h+var_CC]; unsigned int *
0x18000be0b  mov     rcx, rax; this
0x18000be0e  call    ?GetXML@CRevocation@@QEAAJPEAIPEAPEAG@Z; CRevocation::GetXML(uint *,ushort * *)
0x18000be13  mov     edi, eax
0x18000be15  xor     edx, edx
0x18000be17  test    eax, eax
0x18000be19  js      short loc_18000BE66
0x18000be1b  mov     ecx, dword ptr [rbp+57h+var_CC]
0x18000be1e  add     ecx, r14d
0x18000be21  jz      short loc_18000BE66
0x18000be23  lea     eax, [rcx+23h]
0x18000be26  mov     dword ptr [rbp+57h+var_CC], eax
0x18000be29  cmp     [rbp+57h+var_B8], rdx
0x18000be2d  jz      loc_18000C00A
0x18000be33  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000be37  test    r14d, r14d
0x18000be3a  jz      loc_18000C002
0x18000be40  mov     edi, r14d
0x18000be43  lea     eax, [rdx+2]
0x18000be46  mul     rdi
0x18000be49  cmovb   rax, rcx
0x18000be4d  mov     rcx, rax; unsigned __int64
0x18000be50  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000be55  mov     r14, rax
0x18000be58  mov     qword ptr [rbp+57h+var_CC+4], rax
0x18000be5c  test    rax, rax
0x18000be5f  jnz     short loc_18000BE79
0x18000be61  mov     edi, 8007000Eh
0x18000be66  mov     r14, [rsp+110h+var_D8]
0x18000be6b  test    rsi, rsi
0x18000be6e  jz      loc_18000C02D
0x18000be74  jmp     loc_18000C025
0x18000be79  lea     r8, [rdi+rdi]; Size
0x18000be7d  xor     edx, edx; Val
0x18000be7f  mov     rcx, rax; void *
0x18000be82  call    memset_0
0x18000be87  xor     edi, edi
0x18000be89  test    r12d, r12d
0x18000be8c  jz      loc_18000BF68
0x18000be92  mov     r14d, edi
0x18000be95  cmp     r14d, [r15+98h]
0x18000be9c  jnb     loc_18000BF55
0x18000bea2  mov     esi, r14d
0x18000bea5  mov     rax, [r15+90h]
0x18000beac  mov     rcx, [rax+rsi*8]; this
0x18000beb0  test    rcx, rcx
0x18000beb3  jz      loc_18000BF55
0x18000beb9  call    ?AddRef@CDRMCBase@@QEAAKXZ; CDRMCBase::AddRef(void)
0x18000bebe  mov     rax, [r15+90h]
0x18000bec5  mov     rsi, [rax+rsi*8]
0x18000bec9  test    rsi, rsi
0x18000becc  jz      loc_18000BF58
0x18000bed2  mov     rcx, rsi; this
0x18000bed5  call    ?IsDeleted@CDRMCBase@@QEAAHXZ; CDRMCBase::IsDeleted(void)
0x18000beda  test    eax, eax
0x18000bedc  jnz     short loc_18000BF4D
0x18000bede  mov     rcx, rsi; this
0x18000bee1  call    ?GetPolicyType@CUsagePolicy@@QEAA?AW4_DRM_USAGEPOLICY_TYPE@@XZ; CUsagePolicy::GetPolicyType(void)
0x18000bee6  cmp     eax, 3
0x18000bee9  jnz     short loc_18000BF4D
0x18000beeb  mov     [rsp+110h+var_E0], edi
0x18000beef  lea     r8, [rbp+57h+Block]; unsigned __int16 **
0x18000bef3  lea     rdx, [rsp+110h+var_E0]; unsigned int *
0x18000bef8  mov     rcx, rsi; this
0x18000befb  call    ?GetOSExclusionXML@CUsagePolicy@@QEAAJPEAIPEAPEAG@Z; CUsagePolicy::GetOSExclusionXML(uint *,ushort * *)
0x18000bf00  mov     edi, eax
0x18000bf02  xor     eax, eax
0x18000bf04  test    edi, edi
0x18000bf06  js      loc_18000C020
0x18000bf0c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000bf10  mov     r8, qword ptr [rbp+57h+var_CC+4]
0x18000bf14  inc     rcx
0x18000bf17  cmp     [r8+rcx*2], ax
0x18000bf1c  jnz     short loc_18000BF14
0x18000bf1e  mov     edx, [rbp+57h+var_D0]
0x18000bf21  sub     edx, ecx; unsigned __int64
0x18000bf23  mov     eax, ecx
0x18000bf25  lea     rcx, [r8+rax*2]; unsigned __int16 *
0x18000bf29  mov     r11, [rbp+57h+Block]
0x18000bf2d  mov     r8, r11; unsigned __int16 *
0x18000bf30  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bf35  mov     edi, eax
0x18000bf37  test    eax, eax
0x18000bf39  js      loc_18000C020
0x18000bf3f  mov     rcx, r11; Block
0x18000bf42  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bf47  xor     edi, edi
0x18000bf49  mov     [rbp+57h+Block], rdi
0x18000bf4d  mov     rcx, rsi; this
0x18000bf50  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x18000bf55  mov     rsi, rdi
0x18000bf58  inc     r14d
0x18000bf5b  cmp     r14d, r12d
0x18000bf5e  jb      loc_18000BE95
0x18000bf64  mov     r14, qword ptr [rbp+57h+var_CC+4]
0x18000bf68  lea     r8, [rsp+110h+var_D8]; unsigned __int16 **
0x18000bf6d  lea     rdx, [rsp+110h+var_E0]; unsigned int *
0x18000bf72  mov     rcx, [rbp+57h+var_B0]; this
0x18000bf76  call    ?GetXML@CRevocation@@QEAAJPEAIPEAPEAG@Z; CRevocation::GetXML(uint *,ushort * *)
0x18000bf7b  mov     edi, eax
0x18000bf7d  xor     r15d, r15d
0x18000bf80  test    eax, eax
0x18000bf82  js      loc_18000BE66
0x18000bf88  mov     edi, dword ptr [rbp+57h+var_CC]
0x18000bf8b  lea     eax, [r15+2]
0x18000bf8f  mul     rdi
0x18000bf92  lea     rcx, [r15-1]
0x18000bf96  cmovb   rax, rcx
0x18000bf9a  mov     rcx, rax; unsigned __int64
0x18000bf9d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000bfa2  mov     r13, rax
0x18000bfa5  test    rax, rax
0x18000bfa8  jz      loc_18000BE61
0x18000bfae  lea     r8, [rdi+rdi]; Size
0x18000bfb2  xor     edx, edx; Val
0x18000bfb4  mov     rcx, rax; void *
0x18000bfb7  call    memset_0
0x18000bfbc  lea     r9, Src
0x18000bfc3  mov     rax, r9
0x18000bfc6  test    r14, r14
0x18000bfc9  cmovnz  rax, r14
0x18000bfcd  mov     r14, [rsp+110h+var_D8]
0x18000bfd2  test    r14, r14
0x18000bfd5  cmovnz  r9, r14
0x18000bfd9  mov     [rsp+20h], rax
0x18000bfde  lea     r8, [rbp+57h+var_90]; unsigned __int16 *
0x18000bfe2  mov     edx, edi; unsigned __int64
0x18000bfe4  mov     rcx, r13; unsigned __int16 *
0x18000bfe7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000bfec  mov     edi, eax
0x18000bfee  test    eax, eax
0x18000bff0  js      loc_18000BE6B
0x18000bff6  mov     rax, [rbp+57h+var_B8]
0x18000bffa  mov     [rax], r13
0x18000bffd  mov     eax, dword ptr [rbp+57h+var_CC]
0x18000c000  jmp     short loc_18000C012
0x18000c002  mov     r14, rdx
0x18000c005  jmp     loc_18000BF68
0x18000c00a  mov     r14, [rsp+110h+var_D8]
0x18000c00f  xor     r15d, r15d
0x18000c012  mov     rcx, [rbp+57h+var_A8]
0x18000c016  mov     [rcx], eax
0x18000c018  mov     r13, r15
0x18000c01b  jmp     loc_18000BE6B
0x18000c020  mov     r14, [rsp+110h+var_D8]
0x18000c025  mov     rcx, rsi; this
0x18000c028  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x18000c02d  mov     rcx, r13; Block
0x18000c030  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c035  mov     rcx, [rbp+57h+Block]; Block
0x18000c039  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c03e  mov     rcx, r14; Block
0x18000c041  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c046  mov     rcx, qword ptr [rbp+57h+var_CC+4]; Block
0x18000c04a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c04f  nop
0x18000c050  mov     rcx, rbx; lpCriticalSection
0x18000c053  call    cs:__imp_LeaveCriticalSection
0x18000c059  mov     eax, edi
0x18000c05b  mov     rcx, [rbp+57h+var_40]
0x18000c05f  xor     rcx, rsp; StackCookie
0x18000c062  call    __security_check_cookie
0x18000c067  mov     rbx, [rsp+110h+arg_18]
0x18000c06f  add     rsp, 0E0h
0x18000c076  pop     r15
0x18000c078  pop     r14
0x18000c07a  pop     r13
0x18000c07c  pop     r12
0x18000c07e  pop     rdi
0x18000c07f  pop     rsi
0x18000c080  pop     rbp
0x18000c081  retn
```
