# AddAikBasedOnRegistryLocation(PregenKeyType,ushort const *,unsigned __int64 *,DelayRetryAction *,ushort * *)

- ea: `0x180015410`
- end: `0x1800155ff`
- name: `?AddAikBasedOnRegistryLocation@@YAJW4PregenKeyType@@PEBGPEA_KPEAW4DelayRetryAction@@PEAPEAG@Z`
- size: `495`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180015bf0`

## callees

- `0x18000b0dc`
- `0x18000b0fc`
- `0x18000db5c`
- `0x180010730`
- `0x180011e48`
- `0x180014588`
- `0x180015410`
- `0x18001d070`
- `0x18002336c`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800154f8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800154f8`

## string_xrefs

- `0x18001546e`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x1800154b2`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x180015506`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x18001558a`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall AddAikBasedOnRegistryLocation(int a1, const WCHAR *a2, _QWORD *a3, _DWORD *a4, NgcUtils **a5)
{
  int v9; // edx
  int PregenKey; // eax
  unsigned __int64 *v11; // r8
  unsigned int LastError; // ebx
  int v14; // eax
  const char *v15; // r9
  __int64 v16; // rcx
  NgcUtils *v17; // rcx
  int v18; // eax
  NgcUtils *v19; // rax
  __int64 v20; // rax
  unsigned __int16 *v21; // [rsp+20h] [rbp-41h]
  int v22; // [rsp+20h] [rbp-41h]
  unsigned __int8 *v23; // [rsp+30h] [rbp-31h]
  int v24; // [rsp+40h] [rbp-21h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+44h] [rbp-1Dh] BYREF
  NgcUtils *v26; // [rsp+48h] [rbp-19h] BYREF
  unsigned __int16 v27[4]; // [rsp+50h] [rbp-11h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-9h] BYREF
  struct _SECURITY_ATTRIBUTES v29[3]; // [rsp+60h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+57h]

  v26 = 0;
  v24 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v26,
    0);
  v9 = 600000;
  if ( a1 != 5 )
    v9 = 0;
  PregenKey = NgcGetPregenKey(a1, v9, &v24, &v26);
  LastError = PregenKey;
  if ( PregenKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)PregenKey,
      (int)v21);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
    return LastError;
  }
  *(_QWORD *)v27 = 0;
  v14 = NgcUtils::OpenAikNCryptHandle(v26, v27, v11);
  LastError = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)v14,
      (int)v21);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(v27);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
    return LastError;
  }
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:P(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)",
          1u,
          &SecurityDescriptor,
          &SecurityDescriptorSize) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x4A,
                  (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
                  v15);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(v27);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
    return LastError;
  }
  *(_QWORD *)&v29[0].nLength = 24;
  *(_QWORD *)&v29[0].bInheritHandle = 0;
  v29[0].lpSecurityDescriptor = SecurityDescriptor;
  v16 = -1;
  do
    ++v16;
  while ( *((_WORD *)v26 + v16) );
  v17 = (NgcUtils *)(unsigned int)(2 * v16 + 2);
  LODWORD(v23) = (_DWORD)v17;
  LODWORD(v21) = 1;
  v18 = NgcUtils::SetRegistryValue(v17, a2, v29, L"Aik", v21, (BYTE *)v26, v23);
  LastError = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)v18,
      v22);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(v27);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
    return LastError;
  }
  if ( a5 )
  {
    v19 = v26;
    v26 = 0;
    *a5 = v19;
  }
  v20 = *(_QWORD *)v27;
  *(_QWORD *)v27 = 0;
  *a3 = v20;
  *a4 = v24;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(v27);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
  return 0;
}

```

## disassembly

```asm
0x180015410  push    rbp
0x180015412  push    rbx
0x180015413  push    rsi
0x180015414  push    rdi
0x180015415  push    r14
0x180015417  push    r15
0x180015419  lea     rbp, [rsp-27h]
0x18001541e  sub     rsp, 88h
0x180015425  mov     rdi, r9
0x180015428  mov     rsi, r8
0x18001542b  mov     r14, rdx
0x18001542e  mov     ebx, ecx
0x180015430  xor     r15d, r15d
0x180015433  mov     [rbp+4Fh+var_68], r15
0x180015437  mov     [rbp+4Fh+var_70], r15d
0x18001543b  xor     edx, edx
0x18001543d  lea     rcx, [rbp+4Fh+var_68]
0x180015441  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180015446  mov     edx, 927C0h
0x18001544b  cmp     ebx, 5
0x18001544e  cmovnz  edx, r15d
0x180015452  lea     r9, [rbp+4Fh+var_68]
0x180015456  lea     r8, [rbp+4Fh+var_70]
0x18001545a  mov     ecx, ebx
0x18001545c  call    NgcGetPregenKey
0x180015461  mov     ebx, eax
0x180015463  test    eax, eax
0x180015465  jns     short loc_180015490
0x180015467  mov     rcx, [rbp+57h]; this
0x18001546b  mov     r9d, eax; char *
0x18001546e  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180015475  lea     edx, [r15+3Bh]; void *
0x180015479  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001547e  nop
0x18001547f  lea     rcx, [rbp+4Fh+var_68]
0x180015483  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180015488  nop
0x180015489  mov     eax, ebx
0x18001548b  jmp     loc_1800155EF
0x180015490  mov     qword ptr [rbp+4Fh+var_60], r15
0x180015494  mov     qword ptr [rbp+4Fh+var_60], r15
0x180015498  lea     rdx, [rbp+4Fh+var_60]; unsigned __int16 *
0x18001549c  mov     rcx, [rbp+4Fh+var_68]; this
0x1800154a0  call    ?OpenAikNCryptHandle@NgcUtils@@YAJPEBGPEA_K@Z; NgcUtils::OpenAikNCryptHandle(ushort const *,unsigned __int64 *)
0x1800154a5  mov     ebx, eax
0x1800154a7  test    eax, eax
0x1800154a9  jns     short loc_1800154DA
0x1800154ab  mov     rcx, [rbp+57h]; this
0x1800154af  mov     r9d, eax; char *
0x1800154b2  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800154b9  mov     edx, 40h ; '@'; void *
0x1800154be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800154c3  nop
0x1800154c4  lea     rcx, [rbp+4Fh+var_60]
0x1800154c8  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800154cd  nop
0x1800154ce  lea     rcx, [rbp+4Fh+var_68]
0x1800154d2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800154d7  nop
0x1800154d8  jmp     short loc_180015489
0x1800154da  mov     [rbp+4Fh+SecurityDescriptor], r15
0x1800154de  mov     [rbp+4Fh+SecurityDescriptorSize], r15d
0x1800154e2  lea     r9, [rbp+4Fh+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800154e6  lea     r8, [rbp+4Fh+SecurityDescriptor]; SecurityDescriptor
0x1800154ea  mov     ebx, 1
0x1800154ef  mov     edx, ebx; StringSDRevision
0x1800154f1  lea     rcx, StringSecurityDescriptor; "D:P(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)"
0x1800154f8  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800154fe  test    eax, eax
0x180015500  jnz     short loc_180015530
0x180015502  mov     rcx, [rbp+57h]; this
0x180015506  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001550d  lea     edx, [rbx+49h]; void *
0x180015510  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015515  mov     ebx, eax
0x180015517  lea     rcx, [rbp+4Fh+var_60]
0x18001551b  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180015520  nop
0x180015521  lea     rcx, [rbp+4Fh+var_68]
0x180015525  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001552a  nop
0x18001552b  jmp     loc_180015489
0x180015530  mov     qword ptr [rbp+4Fh+var_50], 18h
0x180015538  mov     [rbp+4Fh+var_40], r15
0x18001553c  mov     rax, [rbp+4Fh+SecurityDescriptor]
0x180015540  mov     [rbp+4Fh+var_48], rax
0x180015544  mov     rax, [rbp+4Fh+var_68]
0x180015548  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001554c  inc     rcx
0x18001554f  cmp     [rax+rcx*2], r15w
0x180015554  jnz     short loc_18001554C
0x180015556  lea     ecx, ds:2[rcx*2]; this
0x18001555d  mov     dword ptr [rsp+0B0h+var_80], ecx; unsigned __int8 *
0x180015561  mov     qword ptr [rsp+0B0h+var_88], rax; unsigned int
0x180015566  mov     dword ptr [rsp+0B0h+var_90], ebx; int
0x18001556a  lea     r9, ValueName; "Aik"
0x180015571  lea     r8, [rbp+4Fh+var_50]; unsigned __int16 *
0x180015575  mov     rdx, r14; HKEY
0x180015578  call    ?SetRegistryValue@NgcUtils@@YAJPEAUHKEY__@@PEBGPEAU_SECURITY_ATTRIBUTES@@1KPEAEK@Z; NgcUtils::SetRegistryValue(HKEY__ *,ushort const *,_SECURITY_ATTRIBUTES *,ushort const *,ulong,uchar *,ulong)
0x18001557d  mov     ebx, eax
0x18001557f  test    eax, eax
0x180015581  jns     short loc_1800155B5
0x180015583  mov     rcx, [rbp+57h]; this
0x180015587  mov     r9d, eax; char *
0x18001558a  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180015591  mov     edx, 56h ; 'V'; void *
0x180015596  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001559b  nop
0x18001559c  lea     rcx, [rbp+4Fh+var_60]
0x1800155a0  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800155a5  nop
0x1800155a6  lea     rcx, [rbp+4Fh+var_68]
0x1800155aa  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800155af  nop
0x1800155b0  jmp     loc_180015489
0x1800155b5  mov     rcx, [rbp+4Fh+arg_20]
0x1800155b9  test    rcx, rcx
0x1800155bc  jz      short loc_1800155C9
0x1800155be  mov     rax, [rbp+4Fh+var_68]
0x1800155c2  mov     [rbp+4Fh+var_68], r15
0x1800155c6  mov     [rcx], rax
0x1800155c9  mov     rax, qword ptr [rbp+4Fh+var_60]
0x1800155cd  mov     qword ptr [rbp+4Fh+var_60], r15
0x1800155d1  mov     [rsi], rax
0x1800155d4  mov     eax, [rbp+4Fh+var_70]
0x1800155d7  mov     [rdi], eax
0x1800155d9  lea     rcx, [rbp+4Fh+var_60]
0x1800155dd  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800155e2  nop
0x1800155e3  lea     rcx, [rbp+4Fh+var_68]
0x1800155e7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800155ec  nop
0x1800155ed  xor     eax, eax
0x1800155ef  add     rsp, 88h
0x1800155f6  pop     r15
0x1800155f8  pop     r14
0x1800155fa  pop     rdi
0x1800155fb  pop     rsi
0x1800155fc  pop     rbx
0x1800155fd  pop     rbp
0x1800155fe  retn
```
