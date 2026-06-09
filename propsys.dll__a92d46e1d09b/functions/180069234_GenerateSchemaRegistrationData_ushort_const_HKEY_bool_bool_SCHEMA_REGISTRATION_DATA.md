# GenerateSchemaRegistrationData(ushort const *,HKEY__ *,bool &,bool &,SCHEMA_REGISTRATION_DATA * *)

- ea: `0x180069234`
- end: `0x180069444`
- name: `?GenerateSchemaRegistrationData@@YAJPEBGPEAUHKEY__@@AEA_N2PEAPEAUSCHEMA_REGISTRATION_DATA@@@Z`
- size: `528`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, HKEY@<rdx>, bool *@<r8>, bool *@<r9>, struct SCHEMA_REGISTRATION_DATA **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1800926e8`

## callees

- `0x180003c70`
- `0x180025dd4`
- `0x18006114c`
- `0x180064148`
- `0x180069234`
- `0x18006958c`
- `0x18006e0b8`
- `0x18006ed20`
- `0x18008fc28`
- `0x180092bb0`
- `0x180092f8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800692c9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800692c9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180069277`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180069277`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x180069385`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x180069385`

## string_xrefs

- `0x1800692d7`: `onecoreuap\shell\propsys\schemacachehelpers.cpp`
- `0x180069393`: `onecoreuap\shell\propsys\schemacachehelpers.cpp`
- `0x1800693e6`: `onecoreuap\shell\propsys\schemacachehelpers.cpp`

## pseudocode

```c
__int64 __fastcall GenerateSchemaRegistrationData(
        const unsigned __int16 *a1,
        HKEY a2,
        bool *a3,
        bool *a4,
        struct SCHEMA_REGISTRATION_DATA **a5)
{
  const unsigned __int16 *FileNameW; // rax
  unsigned int v10; // eax
  int v11; // ebx
  unsigned int v12; // edx
  SCHEMA_REGISTRATION_DATA *v13; // rcx
  int v15; // ebx
  __int64 v16; // rax
  unsigned int v17; // eax
  __int64 v18; // rdx
  unsigned int dwOptions; // [rsp+20h] [rbp-60h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-60h]
  SCHEMA_REGISTRATION_DATA **v21; // [rsp+50h] [rbp-30h] BYREF
  struct SCHEMA_REGISTRATION_DATA *v22; // [rsp+58h] [rbp-28h] BYREF
  char v23; // [rsp+60h] [rbp-20h]
  SCHEMA_REGISTRATION_DATA *v24; // [rsp+68h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  *a5 = 0;
  *a4 = 1;
  FileNameW = PathFindFileNameW(a1);
  v24 = 0;
  if ( !*a3 )
  {
    v22 = 0;
    v21 = &v24;
    v23 = 1;
    v11 = SCHEMA_REGISTRATION_DATA::Generate(FileNameW, &v22);
    wil::details::out_param_t<wistd::unique_ptr<SCHEMA_REGISTRATION_DATA,wistd::default_delete<SCHEMA_REGISTRATION_DATA>>>::~out_param_t<wistd::unique_ptr<SCHEMA_REGISTRATION_DATA,wistd::default_delete<SCHEMA_REGISTRATION_DATA>>>(&v21);
    if ( v11 < 0 )
    {
      v18 = 501;
      goto LABEL_18;
    }
LABEL_10:
    if ( !*a4 || *a3 )
      goto LABEL_21;
    v16 = -1;
    do
      ++v16;
    while ( a1[v16] );
    v17 = SHSetValueW(a2, 0, 0, 1u, a1, 2 * v16 + 2);
    if ( v17 )
    {
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x1FC,
              (unsigned int)"onecoreuap\\shell\\propsys\\schemacachehelpers.cpp",
              (const char *)v17,
              dwOptions);
      goto LABEL_4;
    }
    v11 = SCHEMA_REGISTRATION_DATA::Write(v24, a2);
    if ( v11 >= 0 )
    {
LABEL_21:
      *a5 = v24;
      return 0;
    }
    v18 = 510;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\shell\\propsys\\schemacachehelpers.cpp",
      (const char *)(unsigned int)v11,
      dwOptions);
    goto LABEL_4;
  }
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v10 = RegCreateKeyExW(a2, &Src, 0, 0, 0, 0x20019u, 0, &phkResult, 0);
  if ( !v10 )
  {
    v21 = &v24;
    v22 = 0;
    v23 = 1;
    v15 = SCHEMA_REGISTRATION_DATA::Load(phkResult, &v22);
    wil::details::out_param_t<wistd::unique_ptr<SCHEMA_REGISTRATION_DATA,wistd::default_delete<SCHEMA_REGISTRATION_DATA>>>::~out_param_t<wistd::unique_ptr<SCHEMA_REGISTRATION_DATA,wistd::default_delete<SCHEMA_REGISTRATION_DATA>>>(&v21);
    if ( v15 < 0 )
      *a4 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    goto LABEL_10;
  }
  v11 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x1EA,
          (unsigned int)"onecoreuap\\shell\\propsys\\schemacachehelpers.cpp",
          (const char *)v10,
          dwOptionsa);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
LABEL_4:
  v13 = v24;
  v24 = 0;
  if ( v13 )
    SCHEMA_REGISTRATION_DATA::`scalar deleting destructor'(v13, v12);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180069234  mov     [rsp-38h+arg_10], rbx
0x180069239  push    rbp
0x18006923a  push    rsi
0x18006923b  push    rdi
0x18006923c  push    r12
0x18006923e  push    r13
0x180069240  push    r14
0x180069242  push    r15
0x180069244  mov     rbp, rsp
0x180069247  sub     rsp, 80h
0x18006924e  mov     rax, cs:__security_cookie
0x180069255  xor     rax, rsp
0x180069258  mov     [rbp+var_8], rax
0x18006925c  mov     r12, [rbp+arg_20]
0x180069260  xor     r13d, r13d
0x180069263  mov     rdi, r9
0x180069266  mov     r14, r8
0x180069269  mov     rsi, rdx
0x18006926c  mov     r15, rcx
0x18006926f  mov     [r12], r13
0x180069273  mov     byte ptr [r9], 1
0x180069277  call    cs:__imp_PathFindFileNameW
0x18006927d  mov     [rbp+var_18], r13
0x180069281  cmp     [r14], r13b
0x180069284  jz      loc_1800693AE
0x18006928a  xor     edx, edx
0x18006928c  mov     [rbp+var_10], r13
0x180069290  lea     rcx, [rbp+var_10]
0x180069294  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180069299  mov     [rsp+80h+lpdwDisposition], r13; lpdwDisposition
0x18006929e  lea     rax, [rbp+var_10]
0x1800692a2  mov     [rsp+80h+phkResult], rax; phkResult
0x1800692a7  lea     rdx, Src; lpSubKey
0x1800692ae  mov     [rsp+80h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1800692b3  xor     r9d, r9d; lpClass
0x1800692b6  mov     [rsp+80h+samDesired], 20019h; samDesired
0x1800692be  xor     r8d, r8d; Reserved
0x1800692c1  mov     rcx, rsi; hKey
0x1800692c4  mov     [rsp+80h+dwOptions], r13d; unsigned int
0x1800692c9  call    cs:__imp_RegCreateKeyExW
0x1800692cf  test    eax, eax
0x1800692d1  jz      short loc_18006930F
0x1800692d3  mov     rcx, [rbp+38h]; this
0x1800692d7  lea     r8, aOnecoreuapShel_11; "onecoreuap\\shell\\propsys\\schemacache"...
0x1800692de  mov     r9d, eax; char *
0x1800692e1  mov     edx, 1EAh; void *
0x1800692e6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800692eb  lea     rcx, [rbp+var_10]
0x1800692ef  mov     ebx, eax
0x1800692f1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800692f6  mov     rcx, [rbp+var_18]; this
0x1800692fa  mov     [rbp+var_18], r13
0x1800692fe  test    rcx, rcx
0x180069301  jz      short loc_180069308
0x180069303  call    ??_GSCHEMA_REGISTRATION_DATA@@QEAAPEAXI@Z; SCHEMA_REGISTRATION_DATA::`scalar deleting destructor'(uint)
0x180069308  mov     eax, ebx
0x18006930a  jmp     loc_18006941D
0x18006930f  mov     rcx, [rbp+var_10]; HKEY
0x180069313  lea     rax, [rbp+var_18]
0x180069317  lea     rdx, [rbp+var_28]; struct SCHEMA_REGISTRATION_DATA **
0x18006931b  mov     [rbp+var_30], rax
0x18006931f  mov     [rbp+var_28], r13
0x180069323  mov     [rbp+var_20], 1
0x180069327  call    ?Load@SCHEMA_REGISTRATION_DATA@@SAJPEAUHKEY__@@PEAPEAU1@@Z; SCHEMA_REGISTRATION_DATA::Load(HKEY__ *,SCHEMA_REGISTRATION_DATA * *)
0x18006932c  lea     rcx, [rbp+var_30]
0x180069330  mov     ebx, eax
0x180069332  call    ??1?$out_param_t@V?$unique_ptr@USCHEMA_REGISTRATION_DATA@@U?$default_delete@USCHEMA_REGISTRATION_DATA@@@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SCHEMA_REGISTRATION_DATA,wistd::default_delete<SCHEMA_REGISTRATION_DATA>>>::~out_param_t<wistd::unique_ptr<SCHEMA_REGISTRATION_DATA,wistd::default_delete<SCHEMA_REGISTRATION_DATA>>>(void)
0x180069337  test    ebx, ebx
0x180069339  jns     short loc_18006933E
0x18006933b  mov     [rdi], r13b
0x18006933e  lea     rcx, [rbp+var_10]
0x180069342  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180069347  cmp     [rdi], r13b
0x18006934a  jz      loc_180069413
0x180069350  cmp     [r14], r13b
0x180069353  jnz     loc_180069413
0x180069359  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006935d  inc     rax
0x180069360  cmp     [r15+rax*2], r13w
0x180069365  jnz     short loc_18006935D
0x180069367  lea     eax, ds:2[rax*2]
0x18006936e  mov     r9d, 1; dwType
0x180069374  mov     [rsp+80h+samDesired], eax; cbData
0x180069378  xor     r8d, r8d; pszValue
0x18006937b  xor     edx, edx; pszSubKey
0x18006937d  mov     qword ptr [rsp+80h+dwOptions], r15; unsigned int
0x180069382  mov     rcx, rsi; hkey
0x180069385  call    cs:__imp_SHSetValueW
0x18006938b  test    eax, eax
0x18006938d  jz      short loc_1800693FA
0x18006938f  mov     rcx, [rbp+38h]; this
0x180069393  lea     r8, aOnecoreuapShel_11; "onecoreuap\\shell\\propsys\\schemacache"...
0x18006939a  mov     r9d, eax; char *
0x18006939d  mov     edx, 1FCh; void *
0x1800693a2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800693a7  mov     ebx, eax
0x1800693a9  jmp     loc_1800692F6
0x1800693ae  lea     rcx, [rbp+var_18]
0x1800693b2  mov     [rbp+var_28], r13
0x1800693b6  mov     [rbp+var_30], rcx
0x1800693ba  lea     rdx, [rbp+var_28]; struct SCHEMA_REGISTRATION_DATA **
0x1800693be  mov     rcx, rax; unsigned __int16 *
0x1800693c1  mov     [rbp+var_20], 1
0x1800693c5  call    ?Generate@SCHEMA_REGISTRATION_DATA@@SAJPEBGPEAPEAU1@@Z; SCHEMA_REGISTRATION_DATA::Generate(ushort const *,SCHEMA_REGISTRATION_DATA * *)
0x1800693ca  lea     rcx, [rbp+var_30]
0x1800693ce  mov     ebx, eax
0x1800693d0  call    ??1?$out_param_t@V?$unique_ptr@USCHEMA_REGISTRATION_DATA@@U?$default_delete@USCHEMA_REGISTRATION_DATA@@@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SCHEMA_REGISTRATION_DATA,wistd::default_delete<SCHEMA_REGISTRATION_DATA>>>::~out_param_t<wistd::unique_ptr<SCHEMA_REGISTRATION_DATA,wistd::default_delete<SCHEMA_REGISTRATION_DATA>>>(void)
0x1800693d5  test    ebx, ebx
0x1800693d7  jns     loc_180069347
0x1800693dd  mov     edx, 1F5h; void *
0x1800693e2  mov     rcx, [rbp+38h]; this
0x1800693e6  lea     r8, aOnecoreuapShel_11; "onecoreuap\\shell\\propsys\\schemacache"...
0x1800693ed  mov     r9d, ebx; char *
0x1800693f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800693f5  jmp     loc_1800692F6
0x1800693fa  mov     rcx, [rbp+var_18]; this
0x1800693fe  mov     rdx, rsi; HKEY
0x180069401  call    ?Write@SCHEMA_REGISTRATION_DATA@@QEBAJPEAUHKEY__@@@Z; SCHEMA_REGISTRATION_DATA::Write(HKEY__ *)
0x180069406  mov     ebx, eax
0x180069408  test    eax, eax
0x18006940a  jns     short loc_180069413
0x18006940c  mov     edx, 1FEh
0x180069411  jmp     short loc_1800693E2
0x180069413  mov     rax, [rbp+var_18]
0x180069417  mov     [r12], rax
0x18006941b  xor     eax, eax
0x18006941d  mov     rcx, [rbp+var_8]
0x180069421  xor     rcx, rsp; StackCookie
0x180069424  call    __security_check_cookie
0x180069429  mov     rbx, [rsp+80h+arg_10]
0x180069431  add     rsp, 80h
0x180069438  pop     r15
0x18006943a  pop     r14
0x18006943c  pop     r13
0x18006943e  pop     r12
0x180069440  pop     rdi
0x180069441  pop     rsi
0x180069442  pop     rbp
0x180069443  retn
```
