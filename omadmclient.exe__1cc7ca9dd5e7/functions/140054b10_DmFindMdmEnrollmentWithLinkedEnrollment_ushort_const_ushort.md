# DmFindMdmEnrollmentWithLinkedEnrollment(ushort const *,ushort *)

- ea: `0x140054b10`
- end: `0x140055241`
- name: `?DmFindMdmEnrollmentWithLinkedEnrollment@@YAJPEBGPEAG@Z`
- size: `1841`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140047f60`

## callees

- `0x140003450`
- `0x14000b0f4`
- `0x14000bf50`
- `0x1400194c8`
- `0x140054b10`
- `0x140069010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005511c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005511c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140054ea0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140055075`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140054ea0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140055075`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140054d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140054d23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140054d42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140054d42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400550b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140055185`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400550b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140055185`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x140054b8a`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x140054b8a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140054b6a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140054b6a`
- `OLEAUT32!__imp_SysFreeString` at `0x140054bfd`
- `OLEAUT32!__imp_SysFreeString` at `0x140054cad`
- `OLEAUT32!__imp_SysFreeString` at `0x140054d34`
- `OLEAUT32!__imp_SysFreeString` at `0x140054d92`
- `OLEAUT32!__imp_SysFreeString` at `0x140054e21`
- `OLEAUT32!__imp_SysFreeString` at `0x140054ee8`
- `OLEAUT32!__imp_SysFreeString` at `0x140054f42`
- `OLEAUT32!__imp_SysFreeString` at `0x140054ffd`
- `OLEAUT32!__imp_SysFreeString` at `0x1400550ca`
- `OLEAUT32!__imp_SysFreeString` at `0x14005519c`
- `OLEAUT32!__imp_SysFreeString` at `0x1400551f0`
- `OLEAUT32!__imp_SysFreeString` at `0x140054bfd`
- `OLEAUT32!__imp_SysFreeString` at `0x140054cad`
- `OLEAUT32!__imp_SysFreeString` at `0x140054d34`
- `OLEAUT32!__imp_SysFreeString` at `0x140054d92`
- `OLEAUT32!__imp_SysFreeString` at `0x140054e21`
- `OLEAUT32!__imp_SysFreeString` at `0x140054ee8`
- `OLEAUT32!__imp_SysFreeString` at `0x140054f42`
- `OLEAUT32!__imp_SysFreeString` at `0x140054ffd`
- `OLEAUT32!__imp_SysFreeString` at `0x1400550ca`
- `OLEAUT32!__imp_SysFreeString` at `0x14005519c`
- `OLEAUT32!__imp_SysFreeString` at `0x1400551f0`

## string_xrefs

- `0x140054b7d`: `OSData\Software\Microsoft\Enrollments\%s\LinkedEnrollment`
- `0x140054b76`: `Software\Microsoft\Enrollments\%s\LinkedEnrollment`
- `0x140054e8a`: `LinkedEnrollmentId`
- `0x140055066`: `LinkedEnrollmentId`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DmFindMdmEnrollmentWithLinkedEnrollment(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  unsigned __int16 *v2; // rsi
  const unsigned __int16 *v4; // r15
  __int64 DatabaseManagerInstance; // rbx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, BSTR *); // r12
  OLECHAR *v15; // r14
  DWORD LastError; // ebx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rcx
  LSTATUS ValueW; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  PVOID v28; // rbx
  __int64 v29; // rcx
  __int64 v30; // rcx
  LSTATUS v31; // eax
  unsigned int v32; // edi
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rax
  BSTR v36; // rcx
  __int64 v37; // rdx
  OLECHAR v38; // r8
  unsigned __int16 *v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  int pdwTypeb; // [rsp+20h] [rbp-E0h]
  __int64 v46; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v47; // [rsp+48h] [rbp-B8h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v50; // [rsp+5Ch] [rbp-A4h] BYREF
  PVOID hMem[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v2 = a2;
  if ( !a1 || !a2 )
    return 2147942487LL;
  v47 = 0;
  v46 = 0;
  bstrString = 0;
  v4 = L"OSData\\Software\\Microsoft\\Enrollments\\%s\\LinkedEnrollment";
  if ( !(unsigned __int8)RtlIsStateSeparationEnabled(a1) )
    v4 = L"Software\\Microsoft\\Enrollments\\%s\\LinkedEnrollment";
  DatabaseManagerInstance = GetDatabaseManagerInstance();
  v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)DatabaseManagerInstance + 32LL))(
         DatabaseManagerInstance,
         8289,
         &v47);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x191,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\enrollmentutils\\enrollmentutils.cpp",
      (const char *)(unsigned int)v6,
      pdwType);
    if ( bstrString )
      SysFreeString(bstrString);
    v8 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return v7;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v47 + 24LL))(v47, &v46);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x192,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\enrollmentutils\\enrollmentutils.cpp",
      (const char *)(unsigned int)v10,
      pdwType);
    if ( bstrString )
      SysFreeString(bstrString);
    v11 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    v12 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return v7;
  }
  v13 = v46;
  if ( v46 )
  {
    v50 = 1;
    pcbData = 0;
    v14 = *(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v46 + 32LL);
    v15 = bstrString;
    if ( bstrString )
    {
      LastError = GetLastError();
      SysFreeString(v15);
      SetLastError(LastError);
    }
    bstrString = 0;
    v17 = v14(v13, &bstrString);
    v7 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x199,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\enrollmentutils\\enrollmentutils.cpp",
        (const char *)(unsigned int)v17,
        pdwType);
      if ( bstrString )
        SysFreeString(bstrString);
      v18 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      v19 = v47;
      if ( v47 )
      {
        v47 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      return v7;
    }
    v20 = StringCchPrintfW(SubKey, 0x104u, v4, bstrString);
    v7 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19C,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\enrollmentutils\\enrollmentutils.cpp",
        (const char *)(unsigned int)v20,
        pdwType);
      if ( bstrString )
        SysFreeString(bstrString);
      v21 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      v22 = v47;
      if ( v47 )
      {
        v47 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      return v7;
    }
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"LinkedEnrollmentId", 2u, &v50, 0, &pcbData);
    v7 = ValueW;
    if ( ValueW > 0 )
      v7 = (unsigned __int16)ValueW | 0x80070000;
    if ( (v7 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AA,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\enrollmentutils\\enrollmentutils.cpp",
        (const char *)v7,
        pdwTypea);
      if ( bstrString )
        SysFreeString(bstrString);
      v24 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      v25 = v47;
      if ( v47 )
      {
        v47 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      }
      return v7;
    }
    if ( pcbData > 0x104 )
    {
      if ( bstrString )
        SysFreeString(bstrString);
      v26 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      v27 = v47;
      if ( v47 )
      {
        v47 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      }
      return 2147942487LL;
    }
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      hMem,
      0,
      pcbData);
    v28 = hMem[0];
    if ( !hMem[0] )
    {
      v7 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B3,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\enrollmentutils\\enrollmentutils.cpp",
        (const char *)0x8007000ELL,
        pdwTypea);
      if ( bstrString )
        SysFreeString(bstrString);
      v29 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      v30 = v47;
      if ( v47 )
      {
        v47 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
      return v7;
    }
    v31 = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"LinkedEnrollmentId", 2u, &v50, hMem[0], &pcbData);
    v32 = v31;
    if ( v31 > 0 )
      v32 = (unsigned __int16)v31 | 0x80070000;
    if ( (v32 & 0x80000000) == 0 )
    {
      if ( (unsigned int)_o__wcsicmp(v28, a1) )
      {
        v32 = -2147024894;
      }
      else
      {
        v35 = 2147483646;
        v36 = bstrString;
        v37 = 39;
        do
        {
          if ( !v35 )
            break;
          v38 = *v36;
          if ( !*v36 )
            break;
          ++v36;
          *v2++ = v38;
          --v35;
          --v37;
        }
        while ( v37 );
        v39 = v2 - 1;
        if ( v37 )
          v39 = v2;
        *v39 = 0;
        v32 = v37 == 0 ? 0x8007007A : 0;
      }
      LocalFree(v28);
      if ( bstrString )
        SysFreeString(bstrString);
      v40 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      }
      v41 = v47;
      if ( v47 )
      {
        v47 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BE,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\enrollmentutils\\enrollmentutils.cpp",
        (const char *)v32,
        pdwTypeb);
      LocalFree(v28);
      if ( bstrString )
        SysFreeString(bstrString);
      v33 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      }
      v34 = v47;
      if ( v47 )
      {
        v47 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      }
    }
    return v32;
  }
  else
  {
    if ( bstrString )
    {
      SysFreeString(bstrString);
      v13 = v46;
    }
    if ( v13 )
    {
      v46 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v42 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x140054b10  mov     [rsp-8+arg_10], rbx
0x140054b15  push    rbp
0x140054b16  push    rsi
0x140054b17  push    rdi
0x140054b18  push    r12
0x140054b1a  push    r13
0x140054b1c  push    r14
0x140054b1e  push    r15
0x140054b20  lea     rbp, [rsp-190h]
0x140054b28  sub     rsp, 290h
0x140054b2f  mov     rax, cs:__security_cookie
0x140054b36  xor     rax, rsp
0x140054b39  mov     [rbp+1C0h+var_40], rax
0x140054b40  mov     rsi, rdx
0x140054b43  mov     r13, rcx
0x140054b46  xor     r14d, r14d
0x140054b49  test    rcx, rcx
0x140054b4c  jz      loc_140054F87
0x140054b52  test    rdx, rdx
0x140054b55  jz      loc_140054F87
0x140054b5b  mov     [rsp+2C0h+var_278], r14
0x140054b60  mov     [rsp+2C0h+var_280], r14
0x140054b65  mov     [rsp+2C0h+bstrString], r14
0x140054b6a  call    cs:__imp_RtlIsStateSeparationEnabled
0x140054b71  nop     dword ptr [rax+rax+00h]
0x140054b76  lea     rcx, aSoftwareMicros_1; "Software\\Microsoft\\Enrollments\\%s\\L"...
0x140054b7d  lea     r15, aOsdataSoftware_6; "OSData\\Software\\Microsoft\\Enrollment"...
0x140054b84  test    al, al
0x140054b86  cmovz   r15, rcx
0x140054b8a  call    cs:__imp_GetDatabaseManagerInstance
0x140054b91  nop     dword ptr [rax+rax+00h]
0x140054b96  mov     rbx, rax
0x140054b99  mov     rcx, [rax]
0x140054b9c  mov     rdi, [rcx+20h]
0x140054ba0  mov     rcx, [rsp+2C0h+var_278]
0x140054ba5  test    rcx, rcx
0x140054ba8  jz      short loc_140054BBC
0x140054baa  mov     [rsp+2C0h+var_278], r14
0x140054baf  mov     rdx, [rcx]
0x140054bb2  mov     rax, [rdx+10h]
0x140054bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054bbb  nop
0x140054bbc  lea     r8, [rsp+2C0h+var_278]
0x140054bc1  mov     edx, 2061h
0x140054bc6  mov     rcx, rbx
0x140054bc9  mov     rax, rdi
0x140054bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054bd1  mov     ebx, eax
0x140054bd3  test    eax, eax
0x140054bd5  jns     short loc_140054C49
0x140054bd7  mov     rcx, [rbp+1C8h]; this
0x140054bde  mov     r9d, eax; char *
0x140054be1  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\dm\\dmcmnutils\\enro"...
0x140054be8  mov     edx, 191h; void *
0x140054bed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140054bf2  nop
0x140054bf3  mov     rcx, [rsp+2C0h+bstrString]; bstrString
0x140054bf8  test    rcx, rcx
0x140054bfb  jz      short loc_140054C0A
0x140054bfd  call    cs:__imp_SysFreeString
0x140054c04  nop     dword ptr [rax+rax+00h]
0x140054c09  nop
0x140054c0a  mov     rcx, [rsp+2C0h+var_280]
0x140054c0f  test    rcx, rcx
0x140054c12  jz      short loc_140054C26
0x140054c14  mov     [rsp+2C0h+var_280], r14
0x140054c19  mov     rax, [rcx]
0x140054c1c  mov     rax, [rax+10h]
0x140054c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054c25  nop
0x140054c26  mov     rcx, [rsp+2C0h+var_278]
0x140054c2b  test    rcx, rcx
0x140054c2e  jz      short loc_140054C42
0x140054c30  mov     [rsp+2C0h+var_278], r14
0x140054c35  mov     rax, [rcx]
0x140054c38  mov     rax, [rax+10h]
0x140054c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054c41  nop
0x140054c42  mov     eax, ebx
0x140054c44  jmp     loc_140054F8C
0x140054c49  mov     rbx, [rsp+2C0h+var_278]
0x140054c4e  mov     rax, [rbx]
0x140054c51  mov     rdi, [rax+18h]
0x140054c55  mov     rcx, [rsp+2C0h+var_280]
0x140054c5a  test    rcx, rcx
0x140054c5d  jz      short loc_140054C71
0x140054c5f  mov     [rsp+2C0h+var_280], r14
0x140054c64  mov     rdx, [rcx]
0x140054c67  mov     rax, [rdx+10h]
0x140054c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054c70  nop
0x140054c71  lea     rdx, [rsp+2C0h+var_280]
0x140054c76  mov     rcx, rbx
0x140054c79  mov     rax, rdi
0x140054c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054c81  mov     ebx, eax
0x140054c83  test    eax, eax
0x140054c85  jns     short loc_140054CF7
0x140054c87  mov     rcx, [rbp+1C8h]; this
0x140054c8e  mov     r9d, eax; char *
0x140054c91  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\dm\\dmcmnutils\\enro"...
0x140054c98  mov     edx, 192h; void *
0x140054c9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140054ca2  nop
0x140054ca3  mov     rcx, [rsp+2C0h+bstrString]; bstrString
0x140054ca8  test    rcx, rcx
0x140054cab  jz      short loc_140054CBA
0x140054cad  call    cs:__imp_SysFreeString
0x140054cb4  nop     dword ptr [rax+rax+00h]
0x140054cb9  nop
0x140054cba  mov     rcx, [rsp+2C0h+var_280]
0x140054cbf  test    rcx, rcx
0x140054cc2  jz      short loc_140054CD6
0x140054cc4  mov     [rsp+2C0h+var_280], r14
0x140054cc9  mov     rax, [rcx]
0x140054ccc  mov     rax, [rax+10h]
0x140054cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054cd5  nop
0x140054cd6  mov     rcx, [rsp+2C0h+var_278]
0x140054cdb  test    rcx, rcx
0x140054cde  jz      short loc_140054CF2
0x140054ce0  mov     [rsp+2C0h+var_278], r14
0x140054ce5  mov     rax, [rcx]
0x140054ce8  mov     rax, [rax+10h]
0x140054cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054cf1  nop
0x140054cf2  jmp     loc_140054C42
0x140054cf7  mov     rdi, [rsp+2C0h+var_280]
0x140054cfc  test    rdi, rdi
0x140054cff  jz      loc_1400551E6
0x140054d05  mov     [rsp+2C0h+var_264], 1
0x140054d0d  mov     [rsp+2C0h+var_268], r14d
0x140054d12  mov     rax, [rdi]
0x140054d15  mov     r12, [rax+20h]
0x140054d19  mov     r14, [rsp+2C0h+bstrString]
0x140054d1e  test    r14, r14
0x140054d21  jz      short loc_140054D4E
0x140054d23  call    cs:__imp_GetLastError
0x140054d2a  nop     dword ptr [rax+rax+00h]
0x140054d2f  mov     ebx, eax
0x140054d31  mov     rcx, r14; bstrString
0x140054d34  call    cs:__imp_SysFreeString
0x140054d3b  nop     dword ptr [rax+rax+00h]
0x140054d40  mov     ecx, ebx; dwErrCode
0x140054d42  call    cs:__imp_SetLastError
0x140054d49  nop     dword ptr [rax+rax+00h]
0x140054d4e  xor     r14d, r14d
0x140054d51  mov     [rsp+2C0h+bstrString], r14
0x140054d56  lea     rdx, [rsp+2C0h+bstrString]
0x140054d5b  mov     rcx, rdi
0x140054d5e  mov     rax, r12
0x140054d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054d66  mov     ebx, eax
0x140054d68  test    eax, eax
0x140054d6a  jns     short loc_140054DDC
0x140054d6c  mov     rcx, [rbp+1C8h]; this
0x140054d73  mov     r9d, eax; char *
0x140054d76  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\dm\\dmcmnutils\\enro"...
0x140054d7d  mov     edx, 199h; void *
0x140054d82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140054d87  nop
0x140054d88  mov     rcx, [rsp+2C0h+bstrString]; bstrString
0x140054d8d  test    rcx, rcx
0x140054d90  jz      short loc_140054D9F
0x140054d92  call    cs:__imp_SysFreeString
0x140054d99  nop     dword ptr [rax+rax+00h]
0x140054d9e  nop
0x140054d9f  mov     rcx, [rsp+2C0h+var_280]
0x140054da4  test    rcx, rcx
0x140054da7  jz      short loc_140054DBB
0x140054da9  mov     [rsp+2C0h+var_280], r14
0x140054dae  mov     rax, [rcx]
0x140054db1  mov     rax, [rax+10h]
0x140054db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054dba  nop
0x140054dbb  mov     rcx, [rsp+2C0h+var_278]
0x140054dc0  test    rcx, rcx
0x140054dc3  jz      short loc_140054DD7
0x140054dc5  mov     [rsp+2C0h+var_278], r14
0x140054dca  mov     rax, [rcx]
0x140054dcd  mov     rax, [rax+10h]
0x140054dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054dd6  nop
0x140054dd7  jmp     loc_140054C42
0x140054ddc  mov     r9, [rsp+2C0h+bstrString]
0x140054de1  mov     r8, r15; unsigned __int16 *
0x140054de4  mov     edi, 104h
0x140054de9  mov     edx, edi; unsigned __int64
0x140054deb  lea     rcx, [rsp+2C0h+SubKey]; unsigned __int16 *
0x140054df0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140054df5  mov     ebx, eax
0x140054df7  test    eax, eax
0x140054df9  jns     short loc_140054E6B
0x140054dfb  mov     rcx, [rbp+1C8h]; this
0x140054e02  mov     r9d, eax; char *
0x140054e05  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\dm\\dmcmnutils\\enro"...
0x140054e0c  mov     edx, 19Ch; void *
0x140054e11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140054e16  nop
0x140054e17  mov     rcx, [rsp+2C0h+bstrString]; bstrString
0x140054e1c  test    rcx, rcx
0x140054e1f  jz      short loc_140054E2E
0x140054e21  call    cs:__imp_SysFreeString
0x140054e28  nop     dword ptr [rax+rax+00h]
0x140054e2d  nop
0x140054e2e  mov     rcx, [rsp+2C0h+var_280]
0x140054e33  test    rcx, rcx
0x140054e36  jz      short loc_140054E4A
0x140054e38  mov     [rsp+2C0h+var_280], r14
0x140054e3d  mov     rax, [rcx]
0x140054e40  mov     rax, [rax+10h]
0x140054e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054e49  nop
0x140054e4a  mov     rcx, [rsp+2C0h+var_278]
0x140054e4f  test    rcx, rcx
0x140054e52  jz      short loc_140054E66
0x140054e54  mov     [rsp+2C0h+var_278], r14
0x140054e59  mov     rax, [rcx]
0x140054e5c  mov     rax, [rax+10h]
0x140054e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054e65  nop
0x140054e66  jmp     loc_140054C42
0x140054e6b  lea     rax, [rsp+2C0h+var_268]
0x140054e70  mov     [rsp+2C0h+pcbData], rax; pcbData
0x140054e75  mov     [rsp+2C0h+pvData], r14; pvData
0x140054e7a  lea     rax, [rsp+2C0h+var_264]
0x140054e7f  mov     [rsp+2C0h+pdwType], rax; int
0x140054e84  mov     r9d, 2; dwFlags
0x140054e8a  lea     r8, aLinkedenrollme; "LinkedEnrollmentId"
0x140054e91  lea     rdx, [rsp+2C0h+SubKey]; lpSubKey
0x140054e96  mov     r12, 0FFFFFFFF80000002h
0x140054e9d  mov     rcx, r12; hkey
0x140054ea0  call    cs:__imp_RegGetValueW
0x140054ea7  nop     dword ptr [rax+rax+00h]
0x140054eac  mov     ebx, eax
0x140054eae  mov     r15d, 80070000h
0x140054eb4  test    eax, eax
0x140054eb6  jle     short loc_140054EBE
0x140054eb8  movzx   ebx, ax
0x140054ebb  or      ebx, r15d
0x140054ebe  test    ebx, ebx
0x140054ec0  jns     short loc_140054F32
0x140054ec2  mov     rcx, [rbp+1C8h]; this
0x140054ec9  mov     r9d, ebx; char *
0x140054ecc  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\dm\\dmcmnutils\\enro"...
0x140054ed3  mov     edx, 1AAh; void *
0x140054ed8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140054edd  nop
0x140054ede  mov     rcx, [rsp+2C0h+bstrString]; bstrString
0x140054ee3  test    rcx, rcx
0x140054ee6  jz      short loc_140054EF5
0x140054ee8  call    cs:__imp_SysFreeString
0x140054eef  nop     dword ptr [rax+rax+00h]
0x140054ef4  nop
0x140054ef5  mov     rcx, [rsp+2C0h+var_280]
0x140054efa  test    rcx, rcx
0x140054efd  jz      short loc_140054F11
0x140054eff  mov     [rsp+2C0h+var_280], r14
0x140054f04  mov     rax, [rcx]
0x140054f07  mov     rax, [rax+10h]
0x140054f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054f10  nop
0x140054f11  mov     rcx, [rsp+2C0h+var_278]
0x140054f16  test    rcx, rcx
0x140054f19  jz      short loc_140054F2D
0x140054f1b  mov     [rsp+2C0h+var_278], r14
0x140054f20  mov     rdx, [rcx]
0x140054f23  mov     rax, [rdx+10h]
0x140054f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054f2c  nop
0x140054f2d  jmp     loc_140054C42
0x140054f32  cmp     [rsp+2C0h+var_268], edi
0x140054f36  jbe     short loc_140054FB7
0x140054f38  mov     rcx, [rsp+2C0h+bstrString]; bstrString
0x140054f3d  test    rcx, rcx
0x140054f40  jz      short loc_140054F4F
0x140054f42  call    cs:__imp_SysFreeString
0x140054f49  nop     dword ptr [rax+rax+00h]
0x140054f4e  nop
0x140054f4f  mov     rcx, [rsp+2C0h+var_280]
0x140054f54  test    rcx, rcx
0x140054f57  jz      short loc_140054F6B
0x140054f59  mov     [rsp+2C0h+var_280], r14
0x140054f5e  mov     rax, [rcx]
0x140054f61  mov     rax, [rax+10h]
0x140054f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054f6a  nop
0x140054f6b  mov     rcx, [rsp+2C0h+var_278]
0x140054f70  test    rcx, rcx
0x140054f73  jz      short loc_140054F87
0x140054f75  mov     [rsp+2C0h+var_278], r14
0x140054f7a  mov     rax, [rcx]
0x140054f7d  mov     rax, [rax+10h]
0x140054f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054f86  nop
0x140054f87  mov     eax, 80070057h
0x140054f8c  mov     rcx, [rbp+1C0h+var_40]
0x140054f93  xor     rcx, rsp; StackCookie
0x140054f96  call    __security_check_cookie
0x140054f9b  mov     rbx, [rsp+2C0h+arg_10]
  ... truncated ...
```
