# LsaIAuditReplay

- ea: `0x1800eedc0`
- end: `0x1800ef312`
- name: `LsaIAuditReplay`
- size: `1362`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009690`
- `0x18000c300`
- `0x180078d7c`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bc040`
- `0x1800eedc0`

## import_xrefs

- `LSAADT!__imp_LsapAdtWriteLog` at `0x1800ef2be`
- `LSAADT!__imp_LsapAdtWriteLog` at `0x1800ef2be`
- `LSAADT!__imp_?LsapSubsystemName@@3U_UNICODE_STRING@@A` at `0x1800eef60`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800eee8c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800eee8c`
- `ntdll!RtlLengthSid` at `0x1800eeeeb`
- `ntdll!RtlLengthSid` at `0x1800eef2d`
- `ntdll!RtlLengthSid` at `0x1800eeeeb`
- `ntdll!RtlLengthSid` at `0x1800eef2d`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledBySubCategory` at `0x1800eee72`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledBySubCategory` at `0x1800eee72`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapStringListSize` at `0x1800ef1e4`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapStringListSize` at `0x1800ef1e4`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapGetImageNameFromProcessId` at `0x1800ef24c`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapGetImageNameFromProcessId` at `0x1800ef24c`

## pseudocode

```c
__int64 __fastcall LsaIAuditReplay(
        _QWORD *a1,
        _QWORD *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        _QWORD *a5,
        _QWORD *a6,
        unsigned int *a7,
        __int64 a8)
{
  _QWORD *v8; // rbx
  void *v13; // rdx
  LPVOID Value; // rax
  void *v15; // rcx
  ULONG v16; // eax
  __int64 v17; // r8
  int v18; // r10d
  int v19; // r11d
  __int64 v20; // rcx
  unsigned int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rdx
  unsigned __int16 v24; // ax
  __int64 v25; // r9
  unsigned int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rdx
  unsigned __int16 v29; // ax
  __int64 v30; // r9
  int v31; // ecx
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rax
  unsigned __int16 *v35; // rdx
  unsigned int v36; // eax
  __int64 v37; // rcx
  __int64 v38; // rdx
  unsigned __int16 v39; // ax
  __int64 v40; // r9
  unsigned int v41; // eax
  __int64 v42; // rbx
  __int64 v43; // rax
  __int64 v44; // rcx
  int ImageNameFromProcessId; // ecx
  unsigned int v46; // eax
  struct _RTL_BALANCED_NODE *v47; // rdx
  struct _RTL_BALANCED_NODE *v49; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v50; // [rsp+28h] [rbp-D8h]
  struct _LSAP_SECURITY_PACKAGE *Package; // [rsp+30h] [rbp-D0h]
  __int128 v52; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v53; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v54; // [rsp+58h] [rbp-A8h] BYREF
  int v55; // [rsp+70h] [rbp-90h] BYREF
  __int64 v56; // [rsp+74h] [rbp-8Ch]
  int v57; // [rsp+80h] [rbp-80h]
  int v58; // [rsp+88h] [rbp-78h]
  _DWORD v59[257]; // [rsp+8Ch] [rbp-74h]
  _BYTE v60[544]; // [rsp+490h] [rbp+390h] BYREF

  v8 = a5;
  v50 = (__int64)a5;
  memset_0(v60, 0, 0x21Au);
  v49 = (struct _RTL_BALANCED_NODE *)v60;
  memset_0(&v55, 0, 0x418u);
  v52 = 0;
  v53 = 0;
  v54 = 0;
  if ( (unsigned __int8)IsLsapAdtInitializeCrashOnAuditFailPresent()
    && (unsigned __int8)LsapAdtAuditingEnabledBySubCategory(112) )
  {
    Value = TlsGetValue(dwThreadPackage);
    Package = SpmpLocatePackage((unsigned __int64)Value);
    memset_0(&v55, 0, 0x418u);
    v55 = 2;
    v57 = 1048688;
    v56 = 4649;
    v58 = 4;
    v15 = (void *)*((_QWORD *)WellKnownSids + 90);
    if ( v15 )
    {
      v16 = RtlLengthSid(v15);
      v59[8 * HIDWORD(v56)] = v16;
      *(_QWORD *)&v59[8 * HIDWORD(v56) + 5] = *((_QWORD *)WellKnownSids + 90);
    }
    else
    {
      v59[0] = RtlLengthSid(&AdtpNullSid);
      v8 = (_QWORD *)v50;
      *(_QWORD *)&v59[8 * HIDWORD(v56) + 5] = &AdtpNullSid;
    }
    v18 = 1;
    ++HIDWORD(v56);
    v19 = 16;
    v59[8 * HIDWORD(v56) - 1] = 1;
    v59[8 * HIDWORD(v56)] = LsapSubsystemName.Length + 16;
    *(_QWORD *)&v59[8 * HIDWORD(v56) + 5] = *(_QWORD *)&LsapSubsystemName.Length;
    v20 = 8LL * (unsigned int)++HIDWORD(v56);
    if ( a6 )
    {
      v59[v20 - 1] = 5;
      v59[8 * HIDWORD(v56)] = 8;
      *(_QWORD *)&v59[8 * HIDWORD(v56) + 1] = *a6;
    }
    else
    {
      v59[v20 - 1] = 6;
    }
    v21 = ++HIDWORD(v56);
    if ( a1 )
    {
      v22 = a1[1];
      v23 = WORD1(*a1);
      v52 = *(_OWORD *)a1;
      v24 = AdtpSafeWcslen(v22, v23, v17, v21);
      LOWORD(v52) = v24;
      v59[8 * v25 - 1] = v18;
      v59[8 * HIDWORD(v56)] = v19 + v24;
      *(_QWORD *)&v59[8 * HIDWORD(v56) + 5] = &v52;
      v21 = HIDWORD(v56);
    }
    v26 = v18 + v21;
    HIDWORD(v56) = v26;
    if ( a2 )
    {
      v27 = a2[1];
      v28 = WORD1(*a2);
      v53 = *(_OWORD *)a2;
      v29 = AdtpSafeWcslen(v27, v28, v17, v26);
      LOWORD(v53) = v29;
      v59[8 * v30 - 1] = v18;
      v59[8 * HIDWORD(v56)] = v19 + v29;
      *(_QWORD *)&v59[8 * HIDWORD(v56) + 5] = &v53;
      v26 = HIDWORD(v56);
    }
    v31 = *a3;
    v32 = v18 + v26;
    HIDWORD(v56) = v32;
    v59[8 * v32 - 1] = v18;
    v59[8 * HIDWORD(v56)] = v19 + v31;
    *(_QWORD *)&v59[8 * HIDWORD(v56) + 5] = a3;
    v33 = v18 + HIDWORD(v56);
    HIDWORD(v56) += v18;
    if ( a4 )
    {
      v59[8 * v33 - 1] = v18;
      v59[8 * HIDWORD(v56)] = v19 + *a4;
      *(_QWORD *)&v59[8 * HIDWORD(v56) + 5] = a4;
      v33 = HIDWORD(v56);
    }
    v34 = (unsigned int)(v18 + v33);
    HIDWORD(v56) = v34;
    v35 = (unsigned __int16 *)((char *)Package + 48);
    v59[8 * v34 - 1] = v18;
    v59[8 * HIDWORD(v56)] = v19 + *v35;
    *(_QWORD *)&v59[8 * HIDWORD(v56) + 5] = v35;
    v36 = v18 + HIDWORD(v56);
    HIDWORD(v56) += v18;
    if ( v8 )
    {
      v37 = v8[1];
      v38 = WORD1(*v8);
      v54 = *(_OWORD *)v8;
      v39 = AdtpSafeWcslen(v37, v38, v17, v36);
      LOWORD(v54) = v39;
      v59[8 * v40 - 1] = v18;
      v59[8 * HIDWORD(v56)] = v19 + v39;
      *(_QWORD *)&v59[8 * HIDWORD(v56) + 5] = &v54;
      v36 = HIDWORD(v56);
    }
    v41 = v18 + v36;
    HIDWORD(v56) = v41;
    if ( a8 )
    {
      v59[8 * v41 - 1] = v19;
      v42 = 8LL * HIDWORD(v56);
      v59[v42] = LsapStringListSize(a8);
      v18 = 1;
      *(_QWORD *)&v59[8 * HIDWORD(v56) + 5] = a8;
      v41 = HIDWORD(v56);
    }
    v43 = v18 + v41;
    HIDWORD(v56) = v43;
    v59[8 * v43 - 1] = 11;
    v59[8 * HIDWORD(v56)] = 8;
    if ( a7 )
    {
      v44 = *a7;
      *(_QWORD *)&v59[8 * HIDWORD(v56) + 1] = a7;
      ImageNameFromProcessId = LsapGetImageNameFromProcessId(v44, 538, &v49);
      v18 = 1;
    }
    else
    {
      ImageNameFromProcessId = -1073741823;
      *(_QWORD *)&v59[8 * HIDWORD(v56) + 1] = 0;
    }
    v46 = v18 + HIDWORD(v56);
    HIDWORD(v56) = v46;
    v47 = (struct _RTL_BALANCED_NODE *)v46;
    if ( ImageNameFromProcessId >= 0 )
    {
      v59[8 * v46 - 1] = v18;
      v47 = v49;
      v59[8 * HIDWORD(v56)] = LOWORD(v49->Children[0]) + 16;
      *(_QWORD *)&v59[8 * HIDWORD(v56) + 5] = v47;
      v46 = HIDWORD(v56);
    }
    HIDWORD(v56) = v18 + v46;
    LsapAdtWriteLog(&v55, v47);
  }
  if ( v49 && v49 != (struct _RTL_BALANCED_NODE *)v60 )
    LsapSubProv_FreeRoutine(v49, v13);
  return 0;
}

```

## disassembly

```asm
0x1800eedc0  mov     [rsp-8+arg_10], rbx
0x1800eedc5  push    rbp
0x1800eedc6  push    rsi
0x1800eedc7  push    rdi
0x1800eedc8  push    r12
0x1800eedca  push    r13
0x1800eedcc  push    r14
0x1800eedce  push    r15
0x1800eedd0  lea     rbp, [rsp-5C0h]
0x1800eedd8  sub     rsp, 6C0h
0x1800eeddf  mov     rax, cs:__security_cookie
0x1800eede6  xor     rax, rsp
0x1800eede9  mov     [rbp+5F0h+var_40], rax
0x1800eedf0  mov     rbx, [rbp+5F0h+arg_20]
0x1800eedf7  mov     r12, r8
0x1800eedfa  mov     rdi, [rbp+5F0h+arg_30]
0x1800eee01  mov     r13, rdx
0x1800eee04  mov     rsi, [rbp+5F0h+arg_38]
0x1800eee0b  mov     r15, rcx
0x1800eee0e  xor     edx, edx; Val
0x1800eee10  mov     [rsp+6F0h+var_6C8], rbx
0x1800eee15  mov     r8d, 21Ah; Size
0x1800eee1b  lea     rcx, [rbp+5F0h+var_260]; void *
0x1800eee22  mov     r14, r9
0x1800eee25  call    memset_0
0x1800eee2a  lea     rax, [rbp+5F0h+var_260]
0x1800eee31  xor     edx, edx; Val
0x1800eee33  mov     r8d, 418h; Size
0x1800eee39  mov     [rsp+6F0h+var_6D0], rax
0x1800eee3e  lea     rcx, [rsp+6F0h+var_680]; void *
0x1800eee43  call    memset_0
0x1800eee48  xorps   xmm0, xmm0
0x1800eee4b  xorps   xmm1, xmm1
0x1800eee4e  movups  [rsp+6F0h+var_6B8], xmm0
0x1800eee53  movups  [rsp+6F0h+var_6A8], xmm1
0x1800eee58  movups  [rsp+6F0h+var_698], xmm0
0x1800eee5d  call    IsLsapAdtInitializeCrashOnAuditFailPresent
0x1800eee62  test    al, al
0x1800eee64  jz      loc_1800EF2CA
0x1800eee6a  mov     edx, 10h
0x1800eee6f  lea     ecx, [rdx+60h]
0x1800eee72  call    cs:__imp_LsapAdtAuditingEnabledBySubCategory
0x1800eee79  nop     dword ptr [rax+rax+00h]
0x1800eee7e  test    al, al
0x1800eee80  jz      loc_1800EF2CA
0x1800eee86  mov     ecx, cs:?dwThreadPackage@@3KA; dwTlsIndex
0x1800eee8c  call    cs:__imp_TlsGetValue
0x1800eee93  nop     dword ptr [rax+rax+00h]
0x1800eee98  mov     rcx, rax; unsigned __int64
0x1800eee9b  call    ?SpmpLocatePackage@@YAPEAU_LSAP_SECURITY_PACKAGE@@_K@Z; SpmpLocatePackage(unsigned __int64)
0x1800eeea0  xor     edx, edx; Val
0x1800eeea2  mov     [rsp+6F0h+var_6C0], rax
0x1800eeea7  mov     r8d, 418h; Size
0x1800eeead  lea     rcx, [rsp+6F0h+var_680]; void *
0x1800eeeb2  call    memset_0
0x1800eeeb7  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x1800eeebe  xor     edx, edx
0x1800eeec0  mov     [rsp+6F0h+var_680], 2
0x1800eeec8  mov     [rbp+5F0h+var_670], 100070h
0x1800eeecf  mov     [rsp+6F0h+var_67C], 1229h
0x1800eeed8  mov     [rbp+5F0h+var_668], 4
0x1800eeedf  mov     rcx, [rcx+2D0h]; Sid
0x1800eeee6  test    rcx, rcx
0x1800eeee9  jz      short loc_1800EEF20
0x1800eeeeb  call    cs:__imp_RtlLengthSid
0x1800eeef2  nop     dword ptr [rax+rax+00h]
0x1800eeef7  mov     ecx, dword ptr [rsp+6F0h+var_67C+4]
0x1800eeefb  shl     rcx, 5
0x1800eeeff  mov     [rbp+rcx+5F0h+var_664], eax
0x1800eef03  mov     edx, dword ptr [rsp+6F0h+var_67C+4]
0x1800eef07  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x1800eef0e  shl     rdx, 5
0x1800eef12  mov     rcx, [rax+2D0h]
0x1800eef19  mov     [rbp+rdx+5F0h+var_650], rcx
0x1800eef1e  jmp     short loc_1800EEF56
0x1800eef20  mov     ebx, edx
0x1800eef22  lea     rcx, AdtpNullSid; Sid
0x1800eef29  shl     rbx, 5
0x1800eef2d  call    cs:__imp_RtlLengthSid
0x1800eef34  nop     dword ptr [rax+rax+00h]
0x1800eef39  mov     [rbp+rbx+5F0h+var_664], eax
0x1800eef3d  lea     rcx, AdtpNullSid
0x1800eef44  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800eef48  mov     rbx, [rsp+6F0h+var_6C8]
0x1800eef4d  shl     rax, 5
0x1800eef51  mov     [rbp+rax+5F0h+var_650], rcx
0x1800eef56  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800eef5a  mov     r10d, 1
0x1800eef60  mov     rdx, cs:__imp_?LsapSubsystemName@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING LsapSubsystemName
0x1800eef67  add     eax, r10d
0x1800eef6a  mov     dword ptr [rsp+6F0h+var_67C+4], eax
0x1800eef6e  shl     rax, 5
0x1800eef72  lea     r11d, [r10+0Fh]
0x1800eef76  mov     [rbp+rax+5F0h+var_668], r10d
0x1800eef7b  movzx   ecx, word ptr [rdx]
0x1800eef7e  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800eef82  add     ecx, r11d
0x1800eef85  shl     rax, 5
0x1800eef89  mov     [rbp+rax+5F0h+var_664], ecx
0x1800eef8d  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800eef91  shl     rax, 5
0x1800eef95  mov     [rbp+rax+5F0h+var_650], rdx
0x1800eef9a  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800eef9e  mov     rdx, [rbp+5F0h+arg_28]
0x1800eefa5  add     eax, r10d
0x1800eefa8  mov     ecx, eax
0x1800eefaa  shl     rcx, 5
0x1800eefae  mov     dword ptr [rsp+6F0h+var_67C+4], eax
0x1800eefb2  test    rdx, rdx
0x1800eefb5  jz      short loc_1800EEFE1
0x1800eefb7  mov     [rbp+rcx+5F0h+var_668], 5
0x1800eefbf  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800eefc3  shl     rax, 5
0x1800eefc7  mov     [rbp+rax+5F0h+var_664], 8
0x1800eefcf  mov     ecx, dword ptr [rsp+6F0h+var_67C+4]
0x1800eefd3  mov     rax, [rdx]
0x1800eefd6  shl     rcx, 5
0x1800eefda  mov     [rbp+rcx+5F0h+var_660], rax
0x1800eefdf  jmp     short loc_1800EEFE9
0x1800eefe1  mov     [rbp+rcx+5F0h+var_668], 6
0x1800eefe9  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800eefed  add     eax, r10d
0x1800eeff0  mov     dword ptr [rsp+6F0h+var_67C+4], eax
0x1800eeff4  mov     r9d, eax
0x1800eeff7  test    r15, r15
0x1800eeffa  jz      short loc_1800EF050
0x1800eeffc  movups  xmm0, xmmword ptr [r15]
0x1800ef000  mov     rcx, [r15+8]
0x1800ef004  movq    rax, xmm0
0x1800ef009  shr     rax, 10h
0x1800ef00d  movzx   edx, ax
0x1800ef010  movups  [rsp+6F0h+var_6B8], xmm0
0x1800ef015  call    AdtpSafeWcslen
0x1800ef01a  movzx   ecx, ax
0x1800ef01d  mov     word ptr [rsp+6F0h+var_6B8], ax
0x1800ef022  add     ecx, r11d
0x1800ef025  shl     r9, 5
0x1800ef029  mov     [rbp+r9+5F0h+var_668], r10d
0x1800ef02e  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef032  shl     rax, 5
0x1800ef036  mov     [rbp+rax+5F0h+var_664], ecx
0x1800ef03a  lea     rcx, [rsp+6F0h+var_6B8]
0x1800ef03f  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef043  shl     rax, 5
0x1800ef047  mov     [rbp+rax+5F0h+var_650], rcx
0x1800ef04c  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef050  add     eax, r10d
0x1800ef053  mov     dword ptr [rsp+6F0h+var_67C+4], eax
0x1800ef057  mov     r9d, eax
0x1800ef05a  test    r13, r13
0x1800ef05d  jz      short loc_1800EF0B4
0x1800ef05f  movups  xmm0, xmmword ptr [r13+0]
0x1800ef064  mov     rcx, [r13+8]
0x1800ef068  movq    rax, xmm0
0x1800ef06d  shr     rax, 10h
0x1800ef071  movzx   edx, ax
0x1800ef074  movups  [rsp+6F0h+var_6A8], xmm0
0x1800ef079  call    AdtpSafeWcslen
0x1800ef07e  movzx   ecx, ax
0x1800ef081  mov     word ptr [rsp+6F0h+var_6A8], ax
0x1800ef086  add     ecx, r11d
0x1800ef089  shl     r9, 5
0x1800ef08d  mov     [rbp+r9+5F0h+var_668], r10d
0x1800ef092  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef096  shl     rax, 5
0x1800ef09a  mov     [rbp+rax+5F0h+var_664], ecx
0x1800ef09e  lea     rcx, [rsp+6F0h+var_6A8]
0x1800ef0a3  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef0a7  shl     rax, 5
0x1800ef0ab  mov     [rbp+rax+5F0h+var_650], rcx
0x1800ef0b0  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef0b4  movzx   ecx, word ptr [r12]
0x1800ef0b9  add     eax, r10d
0x1800ef0bc  mov     dword ptr [rsp+6F0h+var_67C+4], eax
0x1800ef0c0  add     ecx, r11d
0x1800ef0c3  shl     rax, 5
0x1800ef0c7  mov     [rbp+rax+5F0h+var_668], r10d
0x1800ef0cc  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef0d0  shl     rax, 5
0x1800ef0d4  mov     [rbp+rax+5F0h+var_664], ecx
0x1800ef0d8  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef0dc  shl     rax, 5
0x1800ef0e0  mov     [rbp+rax+5F0h+var_650], r12
0x1800ef0e5  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef0e9  add     eax, r10d
0x1800ef0ec  mov     dword ptr [rsp+6F0h+var_67C+4], eax
0x1800ef0f0  mov     ecx, eax
0x1800ef0f2  test    r14, r14
0x1800ef0f5  jz      short loc_1800EF124
0x1800ef0f7  shl     rcx, 5
0x1800ef0fb  mov     [rbp+rcx+5F0h+var_668], r10d
0x1800ef100  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef104  movzx   ecx, word ptr [r14]
0x1800ef108  shl     rax, 5
0x1800ef10c  add     ecx, r11d
0x1800ef10f  mov     [rbp+rax+5F0h+var_664], ecx
0x1800ef113  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef117  shl     rax, 5
0x1800ef11b  mov     [rbp+rax+5F0h+var_650], r14
0x1800ef120  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef124  mov     rdx, [rsp+6F0h+var_6C0]
0x1800ef129  add     eax, r10d
0x1800ef12c  mov     dword ptr [rsp+6F0h+var_67C+4], eax
0x1800ef130  add     rdx, 30h ; '0'
0x1800ef134  shl     rax, 5
0x1800ef138  mov     [rbp+rax+5F0h+var_668], r10d
0x1800ef13d  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef141  movzx   ecx, word ptr [rdx]
0x1800ef144  shl     rax, 5
0x1800ef148  add     ecx, r11d
0x1800ef14b  mov     [rbp+rax+5F0h+var_664], ecx
0x1800ef14f  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef153  shl     rax, 5
0x1800ef157  mov     [rbp+rax+5F0h+var_650], rdx
0x1800ef15c  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef160  add     eax, r10d
0x1800ef163  mov     dword ptr [rsp+6F0h+var_67C+4], eax
0x1800ef167  mov     r9d, eax
0x1800ef16a  test    rbx, rbx
0x1800ef16d  jz      short loc_1800EF1C2
0x1800ef16f  movups  xmm0, xmmword ptr [rbx]
0x1800ef172  mov     rcx, [rbx+8]
0x1800ef176  movq    rax, xmm0
0x1800ef17b  shr     rax, 10h
0x1800ef17f  movzx   edx, ax
0x1800ef182  movups  [rsp+6F0h+var_698], xmm0
0x1800ef187  call    AdtpSafeWcslen
0x1800ef18c  movzx   ecx, ax
0x1800ef18f  mov     word ptr [rsp+6F0h+var_698], ax
0x1800ef194  add     ecx, r11d
0x1800ef197  shl     r9, 5
0x1800ef19b  mov     [rbp+r9+5F0h+var_668], r10d
0x1800ef1a0  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef1a4  shl     rax, 5
0x1800ef1a8  mov     [rbp+rax+5F0h+var_664], ecx
0x1800ef1ac  lea     rcx, [rsp+6F0h+var_698]
0x1800ef1b1  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef1b5  shl     rax, 5
0x1800ef1b9  mov     [rbp+rax+5F0h+var_650], rcx
0x1800ef1be  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef1c2  add     eax, r10d
0x1800ef1c5  mov     dword ptr [rsp+6F0h+var_67C+4], eax
0x1800ef1c9  mov     ecx, eax
0x1800ef1cb  test    rsi, rsi
0x1800ef1ce  jz      short loc_1800EF20B
0x1800ef1d0  shl     rcx, 5
0x1800ef1d4  mov     [rbp+rcx+5F0h+var_668], r11d
0x1800ef1d9  mov     rcx, rsi
0x1800ef1dc  mov     ebx, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef1e0  shl     rbx, 5
0x1800ef1e4  call    cs:__imp_LsapStringListSize
0x1800ef1eb  nop     dword ptr [rax+rax+00h]
0x1800ef1f0  mov     [rbp+rbx+5F0h+var_664], eax
0x1800ef1f4  mov     r10d, 1
0x1800ef1fa  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef1fe  shl     rax, 5
0x1800ef202  mov     [rbp+rax+5F0h+var_650], rsi
0x1800ef207  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef20b  add     eax, r10d
0x1800ef20e  mov     dword ptr [rsp+6F0h+var_67C+4], eax
0x1800ef212  shl     rax, 5
0x1800ef216  mov     [rbp+rax+5F0h+var_668], 0Bh
0x1800ef21e  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef222  shl     rax, 5
0x1800ef226  mov     [rbp+rax+5F0h+var_664], 8
0x1800ef22e  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef232  shl     rax, 5
0x1800ef236  test    rdi, rdi
0x1800ef239  jz      short loc_1800EF262
0x1800ef23b  mov     ecx, [rdi]
0x1800ef23d  lea     r8, [rsp+6F0h+var_6D0]
0x1800ef242  mov     edx, 21Ah
0x1800ef247  mov     [rbp+rax+5F0h+var_660], rdi
0x1800ef24c  call    cs:__imp_LsapGetImageNameFromProcessId
0x1800ef253  nop     dword ptr [rax+rax+00h]
0x1800ef258  mov     ecx, eax
0x1800ef25a  mov     r10d, 1
0x1800ef260  jmp     short loc_1800EF270
0x1800ef262  mov     ecx, 0C0000001h
0x1800ef267  mov     [rbp+rax+5F0h+var_660], 0
0x1800ef270  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef274  add     eax, r10d
0x1800ef277  mov     dword ptr [rsp+6F0h+var_67C+4], eax
0x1800ef27b  mov     edx, eax
0x1800ef27d  test    ecx, ecx
0x1800ef27f  js      short loc_1800EF2B2
0x1800ef281  shl     rdx, 5
0x1800ef285  mov     [rbp+rdx+5F0h+var_668], r10d
0x1800ef28a  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef28e  mov     rdx, [rsp+6F0h+var_6D0]
0x1800ef293  shl     rax, 5
0x1800ef297  movzx   ecx, word ptr [rdx]
0x1800ef29a  add     ecx, 10h
0x1800ef29d  mov     [rbp+rax+5F0h+var_664], ecx
0x1800ef2a1  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef2a5  shl     rax, 5
0x1800ef2a9  mov     [rbp+rax+5F0h+var_650], rdx
0x1800ef2ae  mov     eax, dword ptr [rsp+6F0h+var_67C+4]
0x1800ef2b2  add     eax, r10d
0x1800ef2b5  lea     rcx, [rsp+6F0h+var_680]
  ... truncated ...
```
