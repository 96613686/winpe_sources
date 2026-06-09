# MspChangePasswordSam

- ea: `0x180032500`
- end: `0x180032c85`
- name: `MspChangePasswordSam`
- size: `1925`
- prototype: `__int64 __usercall@<rax>(PLSA_UNICODE_STRING SystemName@<rcx>, int, char, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021bbc`

## callees

- `0x18002215c`
- `0x18002fb50`
- `0x180032500`
- `0x180032f70`
- `0x180034ecc`
- `0x18003536c`
- `0x180048754`
- `0x18006d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003284a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032bf1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003284a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032bf1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003263e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180032658`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003263e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180032658`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180032c47`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180032c5a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180032c47`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180032c5a`
- `ntdll!RtlReleaseResource` at `0x1800326e5`
- `ntdll!RtlReleaseResource` at `0x1800326e5`
- `ntdll!RtlAcquireResourceShared` at `0x1800326c0`
- `ntdll!RtlAcquireResourceShared` at `0x1800326c0`
- `ntdll!RtlEqualUnicodeString` at `0x1800326a8`
- `ntdll!RtlEqualUnicodeString` at `0x1800326d5`
- `ntdll!RtlEqualUnicodeString` at `0x1800326a8`
- `ntdll!RtlEqualUnicodeString` at `0x1800326d5`
- `SAMLIB!SamOpenDomain` at `0x180032a25`
- `SAMLIB!SamOpenDomain` at `0x180032a25`
- `SAMLIB!SamCloseHandle` at `0x180032c04`
- `SAMLIB!SamCloseHandle` at `0x180032c14`
- `SAMLIB!SamCloseHandle` at `0x180032c04`
- `SAMLIB!SamCloseHandle` at `0x180032c14`
- `SAMLIB!SamConnect` at `0x1800329c3`
- `SAMLIB!SamConnect` at `0x1800329c3`
- `SAMLIB!SamChangePasswordUser2` at `0x18003274a`
- `SAMLIB!SamChangePasswordUser2` at `0x18003281c`
- `SAMLIB!SamChangePasswordUser2` at `0x18003274a`
- `SAMLIB!SamChangePasswordUser2` at `0x18003281c`
- `SAMLIB!SamQueryInformationDomain` at `0x180032a62`
- `SAMLIB!SamQueryInformationDomain` at `0x180032a62`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800328b2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180032b2c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800328b2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180032b2c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18003290a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180032b79`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18003290a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180032b79`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180032c24`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180032c24`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180032c34`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180032c34`

## string_xrefs

- `0x180032637`: `samlib.dll`
- `0x180032651`: `dsparse.dll`

## pseudocode

```c
__int64 __fastcall MspChangePasswordSam(
        PLSA_UNICODE_STRING SystemName,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        char a6,
        __int64 a7,
        PVOID *a8,
        _BYTE *a9)
{
  char v10; // r15
  UNICODE_STRING v11; // xmm0
  unsigned __int16 v12; // cx
  _WORD *v13; // xmm0_8
  __int64 v14; // rcx
  char v15; // si
  __int64 v16; // rdi
  BOOLEAN v17; // di
  int v18; // eax
  int v19; // r15d
  NTSTATUS v20; // eax
  NTSTATUS v21; // eax
  int v22; // eax
  _QWORD *v23; // rcx
  int v24; // edx
  _QWORD *v25; // r13
  int InformationDomain; // eax
  PVOID *v27; // r13
  NTSTATUS v28; // eax
  NTSTATUS InformationPolicy; // eax
  int v30; // ecx
  PVOID PolicyHandle; // [rsp+38h] [rbp-150h] BYREF
  __int64 v33; // [rsp+40h] [rbp-148h] BYREF
  UNICODE_STRING String1; // [rsp+48h] [rbp-140h] BYREF
  __int64 v35; // [rsp+58h] [rbp-130h]
  PVOID Buffer; // [rsp+60h] [rbp-128h] BYREF
  int v37; // [rsp+68h] [rbp-120h]
  __int64 v38; // [rsp+70h] [rbp-118h]
  __int64 v39; // [rsp+78h] [rbp-110h]
  __int64 v40; // [rsp+80h] [rbp-108h] BYREF
  __int64 v41; // [rsp+88h] [rbp-100h]
  PVOID *v42; // [rsp+90h] [rbp-F8h]
  _BYTE *v43; // [rsp+98h] [rbp-F0h]
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-E8h] BYREF
  PLSA_UNICODE_STRING v45; // [rsp+D0h] [rbp-B8h]
  __int64 v46; // [rsp+D8h] [rbp-B0h]
  __int64 v47; // [rsp+E0h] [rbp-A8h]
  __int64 v48; // [rsp+E8h] [rbp-A0h]
  HMODULE hLibModule; // [rsp+F0h] [rbp-98h]
  HMODULE Library; // [rsp+F8h] [rbp-90h]
  _BYTE v51[48]; // [rsp+100h] [rbp-88h] BYREF
  __int64 v52; // [rsp+130h] [rbp-58h] BYREF
  int v53; // [rsp+138h] [rbp-50h]

  v38 = a4;
  v39 = a3;
  v35 = a2;
  v45 = SystemName;
  v46 = a2;
  v47 = a3;
  v48 = a4;
  v41 = a7;
  v42 = a8;
  v43 = a9;
  memset(v51, 0, 44);
  v52 = 0;
  v53 = 0;
  v40 = 0;
  v33 = 0;
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  Buffer = 0;
  v10 = 0;
  *a9 = 1;
  v11 = (UNICODE_STRING)*SystemName;
  String1 = v11;
  v12 = _mm_cvtsi128_si32((__m128i)v11);
  if ( v12 > 4u )
  {
    v13 = (_WORD *)_mm_srli_si128((__m128i)v11, 8).m128i_u64[0];
    if ( *v13 == 92 && v13[1] == 92 )
    {
      String1.Buffer = v13 + 2;
      String1.Length = v12 - 4;
      String1.MaximumLength -= 4;
    }
  }
  Library = LoadLibraryExW(L"samlib.dll", 0, 0x800u);
  hLibModule = LoadLibraryExW(L"dsparse.dll", 0, 0x800u);
  if ( a6 )
  {
    v15 = 0;
    LODWORD(v16) = ((__int64 (*)(void))qword_180088268)();
  }
  else
  {
    v17 = 0;
    if ( NlpSamDomainName.Buffer )
      v17 = RtlEqualUnicodeString(&String1, &NlpSamDomainName, 1u);
    if ( !v17 )
    {
      RtlAcquireResourceShared(&NtLmGlobalCritSect, 1u);
      v17 = RtlEqualUnicodeString(&String1, &NtLmGlobalUnicodeComputerNameString, 1u);
      RtlReleaseResource(&NtLmGlobalCritSect);
    }
    if ( ((unsigned __int8)-((NtLmCheckProcessOption(v14) & 1) != 0) & v17) != 0 )
    {
      LODWORD(v16) = 0;
      v15 = 0;
      v10 = 1;
    }
    else
    {
      if ( v17 )
      {
        v18 = MspImpersonateAnonymous();
      }
      else
      {
        v18 = MspDisableAdminsAlias();
        v10 = 1;
      }
      LODWORD(v16) = v18;
      v15 = 1;
    }
  }
  if ( (int)v16 >= 0 )
  {
    LODWORD(v16) = SamChangePasswordUser2(&String1, v35, v39, v38);
    v37 = v16;
    MsvPaswdLogPrintRoutine(
      "SamChangePasswordUser2 on machine %wZ for user %wZ returned 0x%x\n",
      &String1,
      v35,
      (unsigned int)v16);
    if ( (int)v16 < 0 && (a6 || v10) )
    {
      v19 = 21;
      if ( (_DWORD)v16 != -1073741602
        && ((unsigned int)(v16 + 1073741718) > 4 || !_bittest(&v19, v16 + 1073741718))
        && (_DWORD)v16 != -1073610729 )
      {
        LODWORD(v16) = MspImpersonateAnonymous();
        if ( (int)v16 < 0 )
          goto LABEL_59;
        v15 = 1;
        v16 = (unsigned int)SamChangePasswordUser2(&String1, v35, v39, v38);
        MsvPaswdLogPrintRoutine(
          "SamChangePasswordUser2 retry on machine %wZ for user %wZ returned 0x%x\n",
          &String1,
          v35,
          v16);
      }
    }
    if ( v15 )
      RevertToSelf();
    if ( (int)v16 < 0 )
    {
      if ( (_DWORD)v16 == -1073610729 )
      {
        LODWORD(v16) = -1073741606;
        goto LABEL_59;
      }
      if ( (_DWORD)v16 != -1073741716 )
        goto LABEL_59;
      ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.RootDirectory, 0, 20);
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v20 = LsaOpenPolicy(SystemName, &ObjectAttributes, 1u, &PolicyHandle);
      if ( v20 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Zd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            (unsigned int)WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids,
            (_DWORD)SystemName,
            v20);
        PolicyHandle = 0;
        goto LABEL_59;
      }
      v21 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
      if ( v21 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Zd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            (unsigned int)WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids,
            (_DWORD)SystemName,
            v21);
        Buffer = 0;
        goto LABEL_59;
      }
      *(_DWORD *)v51 = 48;
      memset(&v51[8], 0, 20);
      *(_QWORD *)&v51[32] = 0;
      *(_QWORD *)&v51[40] = &v52;
      v52 = 0x10000000CLL;
      LOWORD(v53) = 0;
      v22 = SamConnect(SystemName, &v40, 32, v51);
      if ( v22 < 0 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_47;
        v24 = 18;
LABEL_46:
        WPP_SF_Zd(v23[2], v24, (unsigned int)WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids, (_DWORD)SystemName, v22);
LABEL_47:
        v33 = 0;
        goto LABEL_59;
      }
      v22 = SamOpenDomain(v40, 1, *((_QWORD *)Buffer + 2), &v33);
      if ( v22 < 0 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_47;
        v24 = 19;
        goto LABEL_46;
      }
      v25 = (_QWORD *)v41;
      InformationDomain = SamQueryInformationDomain(v33, 1, v41);
      if ( InformationDomain >= 0 )
      {
        LODWORD(v16) = -1073741716;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Zd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            (unsigned int)WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids,
            (_DWORD)SystemName,
            InformationDomain);
        *v25 = 0;
      }
    }
  }
LABEL_59:
  if ( (_DWORD)v16 != -1073741433 && (_DWORD)v16 != -1073741602 )
    goto LABEL_79;
  v27 = v42;
  if ( v42 )
  {
    if ( !PolicyHandle )
    {
      ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.RootDirectory, 0, 20);
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v28 = LsaOpenPolicy(SystemName, &ObjectAttributes, 1u, &PolicyHandle);
      if ( v28 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_Zd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            (unsigned int)WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids,
            (_DWORD)SystemName,
            v28);
        PolicyHandle = 0;
      }
    }
    if ( PolicyHandle )
    {
      InformationPolicy = LsaQueryInformationPolicy(PolicyHandle, PolicyPrimaryDomainInformation, v27);
      if ( InformationPolicy < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_Zd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            (unsigned int)WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids,
            (_DWORD)SystemName,
            InformationPolicy);
        *v27 = 0;
      }
    }
    LODWORD(v16) = -1073741433;
  }
  if ( (_DWORD)v16 != -1073741602 )
  {
LABEL_79:
    if ( (unsigned int)(v16 + 1073741724) > 0xA || (v30 = 1345, !_bittest(&v30, v16 + 1073741724)) )
    {
      if ( (_DWORD)v16 != -1073741790 && (_DWORD)v16 != -1073741260 )
        *v43 = 0;
    }
  }
  RevertToSelf();
  if ( v40 )
    SamCloseHandle();
  if ( v33 )
    SamCloseHandle();
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  if ( Buffer )
    LsaFreeMemory(Buffer);
  if ( hLibModule )
    FreeLibrary(hLibModule);
  if ( Library )
    FreeLibrary(Library);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180032500  mov     r11, rsp
0x180032503  push    rbx
0x180032504  push    rsi
0x180032505  push    rdi
0x180032506  push    r12
0x180032508  push    r13
0x18003250a  push    r14
0x18003250c  push    r15
0x18003250e  sub     rsp, 150h
0x180032515  mov     rax, cs:__security_cookie
0x18003251c  xor     rax, rsp
0x18003251f  mov     [rsp+188h+var_48], rax
0x180032527  mov     [rsp+188h+var_118], r9
0x18003252c  mov     [rsp+188h+var_110], r8
0x180032531  mov     [rsp+188h+var_130], rdx
0x180032536  mov     r12, rcx
0x180032539  mov     [rsp+188h+var_B8], rcx
0x180032541  mov     [rsp+188h+var_B0], rdx
0x180032549  mov     [rsp+188h+var_A8], r8
0x180032551  mov     [rsp+188h+var_A0], r9
0x180032559  mov     rax, [rsp+188h+arg_30]
0x180032561  mov     [rsp+188h+var_100], rax
0x180032569  mov     rax, [rsp+188h+arg_38]
0x180032571  mov     [rsp+188h+var_F8], rax
0x180032579  mov     rax, [rsp+188h+arg_40]
0x180032581  mov     [rsp+188h+var_F0], rax
0x180032589  xor     ecx, ecx
0x18003258b  xorps   xmm0, xmm0
0x18003258e  movups  [rsp+188h+var_88], xmm0
0x180032596  movups  xmmword ptr [r11-78h], xmm0
0x18003259b  movups  xmmword ptr [r11-6Ch], xmm0
0x1800325a0  mov     [r11-58h], rcx
0x1800325a4  mov     [r11-50h], ecx
0x1800325a8  xor     ebx, ebx
0x1800325aa  mov     [r11-108h], rbx
0x1800325b1  mov     [rsp+188h+var_148], rbx
0x1800325b6  mov     [rsp+188h+PolicyHandle], rbx
0x1800325bb  movups  xmmword ptr [rsp+188h+ObjectAttributes.Length], xmm0
0x1800325c3  movups  xmmword ptr [rsp+188h+ObjectAttributes.ObjectName], xmm0
0x1800325cb  movups  xmmword ptr [rsp+188h+ObjectAttributes+1Ch], xmm0
0x1800325d3  mov     [rsp+188h+Buffer], rbx
0x1800325d8  mov     r15b, bl
0x1800325db  mov     [rsp+188h+var_157], bl
0x1800325df  lea     r14d, [rcx+1]
0x1800325e3  mov     [rax], r14b
0x1800325e6  movups  xmm0, xmmword ptr [r12]
0x1800325eb  movups  xmmword ptr [rsp+188h+String1.Length], xmm0
0x1800325f0  movd    ecx, xmm0
0x1800325f4  lea     edx, [rbx+4]
0x1800325f7  cmp     cx, dx
0x1800325fa  jbe     short loc_18003262D
0x1800325fc  psrldq  xmm0, 8
0x180032601  movq    rax, xmm0
0x180032606  cmp     word ptr [rax], 5Ch ; '\'
0x18003260a  jnz     short loc_18003262D
0x18003260c  cmp     word ptr [rax+2], 5Ch ; '\'
0x180032611  jnz     short loc_18003262D
0x180032613  add     rax, rdx
0x180032616  mov     [rsp+188h+String1.Buffer], rax
0x18003261b  mov     eax, 0FFFCh
0x180032620  add     cx, ax
0x180032623  mov     [rsp+188h+String1.Length], cx
0x180032628  add     [rsp+188h+String1.MaximumLength], ax
0x18003262d  mov     edi, 800h
0x180032632  mov     r8d, edi; dwFlags
0x180032635  xor     edx, edx; hFile
0x180032637  lea     rcx, LibFileName; "samlib.dll"
0x18003263e  call    cs:__imp_LoadLibraryExW
0x180032644  mov     [rsp+188h+var_90], rax
0x18003264c  mov     r8d, edi; dwFlags
0x18003264f  xor     edx, edx; hFile
0x180032651  lea     rcx, aDsparseDll_0; "dsparse.dll"
0x180032658  call    cs:__imp_LoadLibraryExW
0x18003265e  mov     [rsp+188h+hLibModule], rax
0x180032666  mov     r13b, [rsp+188h+arg_28]
0x18003266e  test    r13b, r13b
0x180032671  jz      short loc_18003268D
0x180032673  mov     sil, bl
0x180032676  mov     [rsp+188h+var_158], bl
0x18003267a  mov     rax, cs:qword_180088268
0x180032681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032686  mov     edi, eax
0x180032688  jmp     loc_18003272E
0x18003268d  mov     dil, bl
0x180032690  cmp     cs:NlpSamDomainName.Buffer, rbx
0x180032697  jz      short loc_1800326B1
0x180032699  mov     r8b, r14b; CaseInsensitive
0x18003269c  lea     rdx, NlpSamDomainName; String2
0x1800326a3  lea     rcx, [rsp+188h+String1]; String1
0x1800326a8  call    cs:__imp_RtlEqualUnicodeString
0x1800326ae  mov     dil, al
0x1800326b1  test    dil, dil
0x1800326b4  jnz     short loc_1800326EB
0x1800326b6  mov     dl, r14b; Wait
0x1800326b9  lea     rcx, NtLmGlobalCritSect; Resource
0x1800326c0  call    cs:__imp_RtlAcquireResourceShared
0x1800326c6  mov     r8b, r14b; CaseInsensitive
0x1800326c9  lea     rdx, NtLmGlobalUnicodeComputerNameString; String2
0x1800326d0  lea     rcx, [rsp+188h+String1]; String1
0x1800326d5  call    cs:__imp_RtlEqualUnicodeString
0x1800326db  mov     dil, al
0x1800326de  lea     rcx, NtLmGlobalCritSect; Resource
0x1800326e5  call    cs:__imp_RtlReleaseResource
0x1800326eb  call    NtLmCheckProcessOption
0x1800326f0  and     al, r14b
0x1800326f3  neg     al
0x1800326f5  sbb     al, al
0x1800326f7  test    dil, al
0x1800326fa  jz      short loc_18003270B
0x1800326fc  mov     edi, ebx
0x1800326fe  mov     sil, bl
0x180032701  mov     r15b, r14b
0x180032704  mov     [rsp+188h+var_157], r14b
0x180032709  jmp     short loc_180032729
0x18003270b  test    dil, dil
0x18003270e  jnz     short loc_18003271F
0x180032710  call    MspDisableAdminsAlias
0x180032715  mov     r15b, r14b
0x180032718  mov     [rsp+188h+var_157], r14b
0x18003271d  jmp     short loc_180032724
0x18003271f  call    MspImpersonateAnonymous
0x180032724  mov     edi, eax
0x180032726  mov     sil, r14b
0x180032729  mov     [rsp+188h+var_158], sil
0x18003272e  test    edi, edi
0x180032730  js      loc_180032AB2
0x180032736  mov     r9, [rsp+188h+var_118]
0x18003273b  mov     r8, [rsp+188h+var_110]
0x180032740  mov     rdx, [rsp+188h+var_130]
0x180032745  lea     rcx, [rsp+188h+String1]
0x18003274a  call    cs:__imp_SamChangePasswordUser2
0x180032750  mov     edi, eax
0x180032752  mov     [rsp+188h+var_120], eax
0x180032756  mov     rax, [rsp+188h+var_130]
0x18003275b  jmp     short loc_1800327AA
0x18003275d  mov     edi, eax
0x18003275f  mov     [rsp+188h+var_120], eax
0x180032763  xor     ebx, ebx
0x180032765  lea     r14d, [rbx+1]
0x180032769  mov     r13b, [rsp+188h+arg_28]
0x180032771  mov     sil, [rsp+188h+var_158]
0x180032776  mov     r15b, [rsp+188h+var_157]
0x18003277b  mov     r12, [rsp+188h+var_B8]
0x180032783  mov     rax, [rsp+188h+var_B0]
0x18003278b  mov     [rsp+188h+var_130], rax
0x180032790  mov     rcx, [rsp+188h+var_A8]
0x180032798  mov     [rsp+188h+var_110], rcx
0x18003279d  mov     rcx, [rsp+188h+var_A0]
0x1800327a5  mov     [rsp+188h+var_118], rcx
0x1800327aa  mov     r9d, edi
0x1800327ad  mov     r8, rax
0x1800327b0  lea     rdx, [rsp+188h+String1]
0x1800327b5  lea     rcx, aSamchangepassw_1; "SamChangePasswordUser2 on machine %wZ f"...
0x1800327bc  call    MsvPaswdLogPrintRoutine
0x1800327c1  test    edi, edi
0x1800327c3  jns     short loc_18003283F
0x1800327c5  test    r13b, r13b
0x1800327c8  jnz     short loc_1800327CF
0x1800327ca  test    r15b, r15b
0x1800327cd  jz      short loc_18003283F
0x1800327cf  mov     r15d, 15h
0x1800327d5  cmp     edi, 0C00000DEh
0x1800327db  jz      short loc_180032845
0x1800327dd  lea     eax, [rdi+3FFFFF96h]
0x1800327e3  cmp     eax, 4
0x1800327e6  ja      short loc_1800327EE
0x1800327e8  bt      r15d, eax
0x1800327ec  jb      short loc_180032845
0x1800327ee  cmp     edi, 0C0020017h
0x1800327f4  jz      short loc_180032845
0x1800327f6  call    MspImpersonateAnonymous
0x1800327fb  mov     edi, eax
0x1800327fd  test    eax, eax
0x1800327ff  js      loc_180032AB8
0x180032805  mov     sil, r14b
0x180032808  mov     r9, [rsp+188h+var_118]
0x18003280d  mov     r8, [rsp+188h+var_110]
0x180032812  mov     rdx, [rsp+188h+var_130]
0x180032817  lea     rcx, [rsp+188h+String1]
0x18003281c  call    cs:__imp_SamChangePasswordUser2
0x180032822  mov     edi, eax
0x180032824  mov     r9d, eax
0x180032827  mov     r8, [rsp+188h+var_130]
0x18003282c  lea     rdx, [rsp+188h+String1]
0x180032831  lea     rcx, aSamchangepassw_0; "SamChangePasswordUser2 retry on machine"...
0x180032838  call    MsvPaswdLogPrintRoutine
0x18003283d  jmp     short loc_180032845
0x18003283f  mov     r15d, 15h
0x180032845  test    sil, sil
0x180032848  jz      short loc_180032850
0x18003284a  call    cs:__imp_RevertToSelf
0x180032850  test    edi, edi
0x180032852  jns     loc_180032AB8
0x180032858  cmp     edi, 0C0020017h
0x18003285e  jz      loc_180032AAB
0x180032864  mov     esi, 0C000006Ch
0x180032869  cmp     edi, esi
0x18003286b  jnz     loc_180032AB8
0x180032871  mov     [rsp+188h+ObjectAttributes.Length], 30h ; '0'
0x18003287c  mov     [rsp+188h+ObjectAttributes.RootDirectory], rbx
0x180032884  mov     [rsp+188h+ObjectAttributes.Attributes], ebx
0x18003288b  mov     [rsp+188h+ObjectAttributes.ObjectName], rbx
0x180032893  xorps   xmm0, xmm0
0x180032896  movdqu  xmmword ptr [rsp+188h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003289f  lea     r9, [rsp+188h+PolicyHandle]; PolicyHandle
0x1800328a4  mov     r8d, r14d; DesiredAccess
0x1800328a7  lea     rdx, [rsp+188h+ObjectAttributes]; ObjectAttributes
0x1800328af  mov     rcx, r12; SystemName
0x1800328b2  call    cs:__imp_LsaOpenPolicy
0x1800328b8  test    eax, eax
0x1800328ba  jns     short loc_1800328FB
0x1800328bc  lea     rsi, WPP_GLOBAL_Control
0x1800328c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800328ca  cmp     rcx, rsi
0x1800328cd  jz      short loc_1800328F1
0x1800328cf  test    [rcx+1Ch], r14b
0x1800328d3  jz      short loc_1800328F1
0x1800328d5  mov     edx, 10h
0x1800328da  mov     [rsp+188h+var_168], eax
0x1800328de  mov     r9, r12
0x1800328e1  lea     r8, WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids
0x1800328e8  mov     rcx, [rcx+10h]
0x1800328ec  call    WPP_SF_Zd
0x1800328f1  mov     [rsp+188h+PolicyHandle], rbx
0x1800328f6  jmp     loc_180032ABF
0x1800328fb  lea     r8, [rsp+188h+Buffer]; Buffer
0x180032900  mov     edx, 5; InformationClass
0x180032905  mov     rcx, [rsp+188h+PolicyHandle]; PolicyHandle
0x18003290a  call    cs:__imp_LsaQueryInformationPolicy
0x180032910  test    eax, eax
0x180032912  jns     short loc_180032953
0x180032914  lea     rsi, WPP_GLOBAL_Control
0x18003291b  mov     rcx, cs:WPP_GLOBAL_Control
0x180032922  cmp     rcx, rsi
0x180032925  jz      short loc_180032949
0x180032927  test    [rcx+1Ch], r14b
0x18003292b  jz      short loc_180032949
0x18003292d  mov     edx, 11h
0x180032932  mov     [rsp+188h+var_168], eax
0x180032936  mov     r9, r12
0x180032939  lea     r8, WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids
0x180032940  mov     rcx, [rcx+10h]
0x180032944  call    WPP_SF_Zd
0x180032949  mov     [rsp+188h+Buffer], rbx
0x18003294e  jmp     loc_180032ABF
0x180032953  mov     dword ptr [rsp+188h+var_88], 30h ; '0'
0x18003295e  mov     qword ptr [rsp+188h+var_88+8], rbx
0x180032966  mov     [rsp+188h+var_70], ebx
0x18003296d  mov     [rsp+188h+var_78], rbx
0x180032975  mov     [rsp+188h+var_68], rbx
0x18003297d  lea     rax, [rsp+188h+var_58]
0x180032985  mov     [rsp+188h+var_60], rax
0x18003298d  mov     [rsp+188h+var_58], 0Ch
0x180032998  mov     [rsp+188h+var_54], r14d
0x1800329a0  mov     word ptr [rsp+188h+var_50], 0
0x1800329aa  lea     r9, [rsp+188h+var_88]
0x1800329b2  mov     r8d, 20h ; ' '
0x1800329b8  lea     rdx, [rsp+188h+var_108]
0x1800329c0  mov     rcx, r12
0x1800329c3  call    cs:__imp_SamConnect
0x1800329c9  test    eax, eax
0x1800329cb  jns     short loc_180032A0C
0x1800329cd  lea     rsi, WPP_GLOBAL_Control
0x1800329d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800329db  cmp     rcx, rsi
0x1800329de  jz      short loc_180032A02
0x1800329e0  test    [rcx+1Ch], r14b
0x1800329e4  jz      short loc_180032A02
0x1800329e6  mov     edx, 12h
0x1800329eb  mov     [rsp+188h+var_168], eax
0x1800329ef  mov     r9, r12
0x1800329f2  lea     r8, WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids
0x1800329f9  mov     rcx, [rcx+10h]
0x1800329fd  call    WPP_SF_Zd
0x180032a02  mov     [rsp+188h+var_148], rbx
0x180032a07  jmp     loc_180032ABF
0x180032a0c  lea     r9, [rsp+188h+var_148]
0x180032a11  mov     r8, [rsp+188h+Buffer]
0x180032a16  mov     r8, [r8+10h]
0x180032a1a  mov     edx, r14d
0x180032a1d  mov     rcx, [rsp+188h+var_108]
0x180032a25  call    cs:__imp_SamOpenDomain
0x180032a2b  test    eax, eax
0x180032a2d  jns     short loc_180032A4F
0x180032a2f  lea     rsi, WPP_GLOBAL_Control
0x180032a36  mov     rcx, cs:WPP_GLOBAL_Control
0x180032a3d  cmp     rcx, rsi
0x180032a40  jz      short loc_180032A02
0x180032a42  test    [rcx+1Ch], r14b
0x180032a46  jz      short loc_180032A02
0x180032a48  mov     edx, 13h
0x180032a4d  jmp     short loc_1800329EB
0x180032a4f  mov     r13, [rsp+188h+var_100]
0x180032a57  mov     r8, r13
0x180032a5a  mov     edx, r14d
0x180032a5d  mov     rcx, [rsp+188h+var_148]
0x180032a62  call    cs:__imp_SamQueryInformationDomain
0x180032a68  test    eax, eax
0x180032a6a  jns     short loc_180032AA7
0x180032a6c  lea     rsi, WPP_GLOBAL_Control
  ... truncated ...
```
