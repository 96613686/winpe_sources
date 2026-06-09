# _GetAppContainerSpecificSubPath(ushort const *,ushort const *,int,ushort * *)

- ea: `0x1800017e4`
- end: `0x180001aaf`
- name: `?_GetAppContainerSpecificSubPath@@YAJPEBG0HPEAPEAG@Z`
- size: `715`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000ce3c`
- `0x180016250`

## callees

- `0x1800015a0`
- `0x1800017e4`
- `0x180001ab8`
- `0x180001ae0`
- `0x180001d3c`
- `0x1800023d8`
- `0x180002484`
- `0x180004990`
- `0x180005b60`
- `0x180005b90`
- `0x18000dc34`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001a65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001a65`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000181f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000181f`

## pseudocode

```c
__int64 __fastcall _GetAppContainerSpecificSubPath(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int a3,
        unsigned __int16 **a4)
{
  const char *v8; // r9
  unsigned int LastError; // ebx
  int IsChildAppContainerSid; // eax
  int AppContainerProperty; // eax
  __int64 v13; // rdx
  const wchar_t *v14; // rdx
  int v15; // eax
  int v16; // eax
  int v17; // [rsp+20h] [rbp-39h]
  PSID Sid; // [rsp+40h] [rbp-19h] BYREF
  unsigned __int16 *v19; // [rsp+48h] [rbp-11h] BYREF
  __int64 v20; // [rsp+50h] [rbp-9h]
  __int64 v21; // [rsp+58h] [rbp-1h]
  unsigned __int16 *v22; // [rsp+60h] [rbp+7h] BYREF
  __int64 v23; // [rsp+68h] [rbp+Fh]
  __int64 v24; // [rsp+70h] [rbp+17h]
  unsigned __int16 *v25; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 v26; // [rsp+80h] [rbp+27h]
  __int64 v27; // [rsp+88h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  int v29; // [rsp+D8h] [rbp+7Fh] BYREF

  *a4 = 0;
  Sid = 0;
  if ( !ConvertStringSidToSidW(a2, &Sid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x7F,
                  (unsigned int)"minio\\profapi\\appcontainer.cpp",
                  v8);
LABEL_9:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&Sid);
    return LastError;
  }
  v19 = 0;
  v20 = 0;
  v21 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v19);
  v20 = -1;
  v21 = -1;
  LastError = _GetAppContainerProperty(a1, a2, L"Moniker", &v19);
  if ( LastError == -2147024877 || LastError == -2147024891 || LastError == -2147024894 )
  {
LABEL_8:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v19);
    goto LABEL_9;
  }
  if ( (LastError & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x88,
      (unsigned int)"minio\\profapi\\appcontainer.cpp",
      (const char *)LastError,
      (int)"_GetAppContainerMoniker %ws %ws",
      (const char *)a1,
      a2);
    goto LABEL_8;
  }
  v29 = 0;
  IsChildAppContainerSid = _IsChildAppContainerSid(Sid, &v29);
  LastError = IsChildAppContainerSid;
  if ( IsChildAppContainerSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"minio\\profapi\\appcontainer.cpp",
      (const char *)(unsigned int)IsChildAppContainerSid,
      v17);
    goto LABEL_8;
  }
  v22 = 0;
  v23 = 0;
  v24 = 0;
  if ( v29 )
  {
    v25 = 0;
    v26 = 0;
    v27 = 0;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v25);
    v26 = -1;
    v27 = -1;
    AppContainerProperty = _GetAppContainerProperty(a1, a2, L"ParentMoniker", &v25);
    LastError = AppContainerProperty;
    if ( AppContainerProperty < 0 )
    {
      v13 = 145;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"minio\\profapi\\appcontainer.cpp",
        (const char *)(unsigned int)AppContainerProperty,
        v17);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v25);
LABEL_17:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v22);
      goto LABEL_8;
    }
    v14 = L"%s\\Children\\%s";
    if ( !a3 )
      v14 = L"%s\\AC\\#!%s";
    AppContainerProperty = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
                             &v22,
                             v14,
                             v25,
                             v19);
    LastError = AppContainerProperty;
    if ( AppContainerProperty < 0 )
    {
      v13 = 147;
      goto LABEL_16;
    }
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v25);
LABEL_23:
    *a4 = v22;
    v22 = 0;
    v24 = 0;
    v23 = 0;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v22);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v19);
    LastError = 0;
    goto LABEL_9;
  }
  v15 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Initialize(&v22, v19);
  LastError = v15;
  if ( v15 >= 0 )
  {
    if ( !a3 )
    {
      v16 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Concat(
              &v22,
              L"\\AC");
      LastError = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9A,
          (unsigned int)"minio\\profapi\\appcontainer.cpp",
          (const char *)(unsigned int)v16,
          v17);
        goto LABEL_17;
      }
    }
    goto LABEL_23;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x97,
    (unsigned int)"minio\\profapi\\appcontainer.cpp",
    (const char *)(unsigned int)v15,
    v17);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v22);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v19);
  if ( Sid )
    LocalFree(Sid);
  return LastError;
}

```

## disassembly

```asm
0x1800017e4  mov     [rsp-8+arg_0], rbx
0x1800017e9  mov     [rsp-8+arg_8], rsi
0x1800017ee  push    rbp
0x1800017ef  push    rdi
0x1800017f0  push    r12
0x1800017f2  push    r14
0x1800017f4  push    r15
0x1800017f6  lea     rbp, [rsp-37h]
0x1800017fb  sub     rsp, 90h
0x180001802  mov     rdi, rdx
0x180001805  mov     r14, rcx
0x180001808  xor     r12d, r12d
0x18000180b  lea     rdx, [rbp+57h+Sid]; Sid
0x18000180f  mov     rcx, rdi; StringSid
0x180001812  mov     [r9], r12
0x180001815  mov     r15, r9
0x180001818  mov     [rbp+57h+Sid], r12
0x18000181c  mov     esi, r8d
0x18000181f  call    cs:__imp_ConvertStringSidToSidW
0x180001825  test    eax, eax
0x180001827  jnz     short loc_180001843
0x180001829  mov     rcx, [rbp+5Fh]; this
0x18000182d  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x180001834  lea     edx, [rax+7Fh]; void *
0x180001837  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000183c  mov     ebx, eax
0x18000183e  jmp     loc_1800018D9
0x180001843  lea     rcx, [rbp+57h+var_68]
0x180001847  mov     [rbp+57h+var_68], r12
0x18000184b  mov     [rbp+57h+var_60], r12
0x18000184f  mov     [rbp+57h+var_58], r12
0x180001853  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180001858  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000185c  lea     r9, [rbp+57h+var_68]; unsigned __int16 **
0x180001860  lea     r8, aMoniker; "Moniker"
0x180001867  mov     [rbp+57h+var_60], rax
0x18000186b  mov     rdx, rdi; unsigned __int16 *
0x18000186e  mov     [rbp+57h+var_58], rax
0x180001872  mov     rcx, r14; unsigned __int16 *
0x180001875  call    ?_GetAppContainerProperty@@YAJPEBG00PEAPEAG@Z; _GetAppContainerProperty(ushort const *,ushort const *,ushort const *,ushort * *)
0x18000187a  mov     ebx, eax
0x18000187c  cmp     eax, 80070013h
0x180001881  jnz     short loc_18000188E
0x180001883  lea     rcx, [rbp+57h+var_68]
0x180001887  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000188c  jmp     short loc_1800018D9
0x18000188e  cmp     ebx, 80070005h
0x180001894  jz      short loc_1800018D0
0x180001896  cmp     ebx, 80070002h
0x18000189c  jz      short loc_1800018D0
0x18000189e  test    ebx, ebx
0x1800018a0  jns     short loc_180001900
0x1800018a2  mov     rcx, [rbp+5Fh]; this
0x1800018a6  lea     rax, aGetappcontaine_0; "_GetAppContainerMoniker %ws %ws"
0x1800018ad  mov     [rsp+0B0h+var_80], rdi
0x1800018b2  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x1800018b9  mov     [rsp+0B0h+var_88], r14; char *
0x1800018be  mov     r9d, ebx; char *
0x1800018c1  mov     edx, 88h; void *
0x1800018c6  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x1800018cb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800018d0  lea     rcx, [rbp+57h+var_68]
0x1800018d4  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800018d9  lea     rcx, [rbp+57h+Sid]
0x1800018dd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1800018e2  lea     r11, [rsp+0B0h+var_20]
0x1800018ea  mov     eax, ebx
0x1800018ec  mov     rbx, [r11+30h]
0x1800018f0  mov     rsi, [r11+38h]
0x1800018f4  mov     rsp, r11
0x1800018f7  pop     r15
0x1800018f9  pop     r14
0x1800018fb  pop     r12
0x1800018fd  pop     rdi
0x1800018fe  pop     rbp
0x1800018ff  retn
0x180001900  mov     rcx, [rbp+57h+Sid]; void *
0x180001904  lea     rdx, [rbp+57h+arg_18]; int *
0x180001908  mov     [rbp+57h+arg_18], r12d
0x18000190c  call    ?_IsChildAppContainerSid@@YAJQEAXPEAH@Z; _IsChildAppContainerSid(void * const,int *)
0x180001911  mov     ebx, eax
0x180001913  test    eax, eax
0x180001915  jns     short loc_180001931
0x180001917  mov     rcx, [rbp+5Fh]; this
0x18000191b  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x180001922  mov     r9d, eax; char *
0x180001925  mov     edx, 8Bh; void *
0x18000192a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000192f  jmp     short loc_1800018D0
0x180001931  mov     [rbp+57h+var_50], r12
0x180001935  mov     [rbp+57h+var_48], r12
0x180001939  mov     [rbp+57h+var_40], r12
0x18000193d  cmp     [rbp+57h+arg_18], r12d
0x180001941  jz      loc_180001A1B
0x180001947  lea     rcx, [rbp+57h+var_38]
0x18000194b  mov     [rbp+57h+var_38], r12
0x18000194f  mov     [rbp+57h+var_30], r12
0x180001953  mov     [rbp+57h+var_28], r12
0x180001957  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000195c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001960  lea     r9, [rbp+57h+var_38]; unsigned __int16 **
0x180001964  lea     r8, aParentmoniker; "ParentMoniker"
0x18000196b  mov     [rbp+57h+var_30], rax
0x18000196f  mov     rdx, rdi; unsigned __int16 *
0x180001972  mov     [rbp+57h+var_28], rax
0x180001976  mov     rcx, r14; unsigned __int16 *
0x180001979  call    ?_GetAppContainerProperty@@YAJPEBG00PEAPEAG@Z; _GetAppContainerProperty(ushort const *,ushort const *,ushort const *,ushort * *)
0x18000197e  mov     ebx, eax
0x180001980  test    eax, eax
0x180001982  jns     short loc_1800019B3
0x180001984  mov     edx, 91h; void *
0x180001989  mov     rcx, [rbp+5Fh]; this
0x18000198d  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x180001994  mov     r9d, eax; char *
0x180001997  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000199c  lea     rcx, [rbp+57h+var_38]
0x1800019a0  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800019a5  lea     rcx, [rbp+57h+var_50]
0x1800019a9  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800019ae  jmp     loc_1800018D0
0x1800019b3  mov     r9, [rbp+57h+var_68]
0x1800019b7  lea     rax, aSAcS; "%s\\AC\\#!%s"
0x1800019be  mov     r8, [rbp+57h+var_38]
0x1800019c2  lea     rdx, aSChildrenS; "%s\\Children\\%s"
0x1800019c9  test    esi, esi
0x1800019cb  lea     rcx, [rbp+57h+var_50]
0x1800019cf  cmovz   rdx, rax
0x1800019d3  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800019d8  mov     ebx, eax
0x1800019da  test    eax, eax
0x1800019dc  jns     short loc_1800019E5
0x1800019de  mov     edx, 93h
0x1800019e3  jmp     short loc_180001989
0x1800019e5  lea     rcx, [rbp+57h+var_38]
0x1800019e9  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800019ee  mov     rax, [rbp+57h+var_50]
0x1800019f2  lea     rcx, [rbp+57h+var_50]
0x1800019f6  mov     [r15], rax
0x1800019f9  mov     [rbp+57h+var_50], r12
0x1800019fd  mov     [rbp+57h+var_40], r12
0x180001a01  mov     [rbp+57h+var_48], r12
0x180001a05  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180001a0a  lea     rcx, [rbp+57h+var_68]
0x180001a0e  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180001a13  mov     ebx, r12d
0x180001a16  jmp     loc_1800018D9
0x180001a1b  mov     rdx, [rbp+57h+var_68]
0x180001a1f  lea     rcx, [rbp+57h+var_50]
0x180001a23  call    ?_Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180001a28  mov     ebx, eax
0x180001a2a  test    eax, eax
0x180001a2c  jns     short loc_180001A70
0x180001a2e  mov     rcx, [rbp+5Fh]; this
0x180001a32  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x180001a39  mov     r9d, eax; char *
0x180001a3c  mov     edx, 97h; void *
0x180001a41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001a46  lea     rcx, [rbp+57h+var_50]
0x180001a4a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180001a4f  lea     rcx, [rbp+57h+var_68]
0x180001a53  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180001a58  mov     rcx, [rbp+57h+Sid]; hMem
0x180001a5c  test    rcx, rcx
0x180001a5f  jz      loc_1800018E2
0x180001a65  call    cs:__imp_LocalFree
0x180001a6b  jmp     loc_1800018E2
0x180001a70  test    esi, esi
0x180001a72  jnz     loc_1800019EE
0x180001a78  lea     rdx, aAc; "\\AC"
0x180001a7f  lea     rcx, [rbp+57h+var_50]
0x180001a83  call    ?Concat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Concat(ushort const *)
0x180001a88  mov     ebx, eax
0x180001a8a  test    eax, eax
0x180001a8c  jns     loc_1800019EE
0x180001a92  mov     rcx, [rbp+5Fh]; this
0x180001a96  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x180001a9d  mov     r9d, eax; char *
0x180001aa0  mov     edx, 9Ah; void *
0x180001aa5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001aaa  jmp     loc_1800019A5
```
