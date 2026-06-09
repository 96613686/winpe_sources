# Container::Manager::Support::CreateOrOpenAppContainerProfile<2>(ushort const * const,utl::array<_SID_AND_ATTRIBUTES,2> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)

- ea: `0x180111d70`
- end: `0x180111fab`
- name: `??$CreateOrOpenAppContainerProfile@$01@Support@Manager@Container@@YAJQEBGAEBU?$array@U_SID_AND_ATTRIBUTES@@$01@utl@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `571`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180111fb4`

## callees

- `0x18000da88`
- `0x180016718`
- `0x180111d70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111e3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111ecf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111f50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111e3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111ecf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111f50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180111e59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180111eee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180111f6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180111e59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180111eee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180111f6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180111de7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180111e4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180111ee0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180111f61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180111f8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180111de7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180111e4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180111ee0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180111f61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180111f8f`
- `USERENV!DeleteAppContainerProfile` at `0x180111e05`
- `USERENV!DeleteAppContainerProfile` at `0x180111e05`
- `USERENV!CreateAppContainerProfile` at `0x180111dab`
- `USERENV!CreateAppContainerProfile` at `0x180111f1f`
- `USERENV!CreateAppContainerProfile` at `0x180111dab`
- `USERENV!CreateAppContainerProfile` at `0x180111f1f`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x180111e74`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x180111e74`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerRegisterSid` at `0x180111e9a`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerRegisterSid` at `0x180111e9a`

## pseudocode

```c
__int64 __fastcall Container::Manager::Support::CreateOrOpenAppContainerProfile<2>(__int64 a1, __int64 a2, HLOCAL *a3)
{
  int AppContainerProfile; // eax
  int v7; // ebx
  __int64 v8; // rdx
  int v10; // eax
  HLOCAL v13; // rdi
  HLOCAL v14; // rsi
  DWORD LastError; // ebx
  HLOCAL v16; // rcx
  int v17; // [rsp+20h] [rbp-28h]
  HLOCAL hMem[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]

  hMem[0] = 0;
  v17 = 2;
  AppContainerProfile = CreateAppContainerProfile(a1, a1, a1, a2);
  v7 = AppContainerProfile;
  if ( AppContainerProfile < 0 )
  {
    if ( AppContainerProfile != -2147024713 )
    {
      v8 = 126;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
        (const char *)(unsigned int)v7,
        v17);
      if ( hMem[0] )
        LocalFree(hMem[0]);
      return (unsigned int)v7;
    }
    v10 = DeleteAppContainerProfile(a1);
    if ( v10 >= 0 )
    {
      hMem[0] = 0;
      v17 = 2;
      v7 = CreateAppContainerProfile(a1, a1, a1, a2);
      if ( v7 < 0 )
      {
        v8 = 142;
        goto LABEL_4;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
        (const char *)(unsigned int)v10,
        2);
      hMem[0] = 0;
      v7 = AppContainerDeriveSidFromMoniker(a1, hMem);
      if ( v7 < 0 )
      {
        v8 = 148;
        goto LABEL_4;
      }
      v7 = AppContainerRegisterSid(hMem[0], a1, a1);
      if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147024713 )
      {
        v8 = 151;
        goto LABEL_4;
      }
    }
  }
  if ( a3 == hMem )
  {
    v16 = hMem[0];
  }
  else
  {
    v13 = *a3;
    v14 = hMem[0];
    if ( *a3 )
    {
      LastError = GetLastError();
      LocalFree(v13);
      SetLastError(LastError);
    }
    v16 = 0;
    *a3 = v14;
    hMem[0] = 0;
  }
  if ( v16 )
    LocalFree(v16);
  return 0;
}

```

## disassembly

```asm
0x180111d70  push    rbp
0x180111d72  push    rbx
0x180111d73  push    rsi
0x180111d74  push    rdi
0x180111d75  push    r14
0x180111d77  push    r15
0x180111d79  mov     rbp, rsp
0x180111d7c  sub     rsp, 48h
0x180111d80  lea     rax, [rbp+hMem]
0x180111d84  mov     [rbp+hMem], 0
0x180111d8c  mov     r14, r8
0x180111d8f  mov     [rsp+48h+var_20], rax
0x180111d94  mov     r15, rdx
0x180111d97  mov     [rsp+48h+var_28], 2; int
0x180111d9f  mov     r9, rdx
0x180111da2  mov     r8, rcx
0x180111da5  mov     rdx, rcx
0x180111da8  mov     rdi, rcx
0x180111dab  call    cs:__imp_CreateAppContainerProfile
0x180111db2  nop     dword ptr [rax+rax+00h]
0x180111db7  mov     ebx, eax
0x180111db9  mov     esi, 800700B7h
0x180111dbe  test    eax, eax
0x180111dc0  jns     short loc_180111DFA
0x180111dc2  cmp     eax, esi
0x180111dc4  jz      short loc_180111E02
0x180111dc6  mov     edx, 7Eh ; '~'; void *
0x180111dcb  mov     rcx, [rbp+30h]; this
0x180111dcf  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\pro"...
0x180111dd6  mov     r9d, ebx; char *
0x180111dd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180111dde  mov     rcx, [rbp+hMem]; hMem
0x180111de2  test    rcx, rcx
0x180111de5  jz      short loc_180111DF3
0x180111de7  call    cs:__imp_LocalFree
0x180111dee  nop     dword ptr [rax+rax+00h]
0x180111df3  mov     eax, ebx
0x180111df5  jmp     loc_180111F9D
0x180111dfa  cmp     ebx, esi
0x180111dfc  jnz     loc_180111F3B
0x180111e02  mov     rcx, rdi
0x180111e05  call    cs:__imp_DeleteAppContainerProfile
0x180111e0c  nop     dword ptr [rax+rax+00h]
0x180111e11  test    eax, eax
0x180111e13  jns     loc_180111EC6
0x180111e19  mov     rcx, [rbp+30h]; this
0x180111e1d  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\pro"...
0x180111e24  mov     r9d, eax; char *
0x180111e27  mov     edx, 85h; void *
0x180111e2c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180111e31  mov     r15, [rbp+hMem]
0x180111e35  test    r15, r15
0x180111e38  jz      short loc_180111E65
0x180111e3a  call    cs:__imp_GetLastError
0x180111e41  nop     dword ptr [rax+rax+00h]
0x180111e46  mov     rcx, r15; hMem
0x180111e49  mov     ebx, eax
0x180111e4b  call    cs:__imp_LocalFree
0x180111e52  nop     dword ptr [rax+rax+00h]
0x180111e57  mov     ecx, ebx; dwErrCode
0x180111e59  call    cs:__imp_SetLastError
0x180111e60  nop     dword ptr [rax+rax+00h]
0x180111e65  lea     rdx, [rbp+hMem]
0x180111e69  mov     [rbp+hMem], 0
0x180111e71  mov     rcx, rdi
0x180111e74  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x180111e7b  nop     dword ptr [rax+rax+00h]
0x180111e80  mov     ebx, eax
0x180111e82  test    eax, eax
0x180111e84  jns     short loc_180111E90
0x180111e86  mov     edx, 94h
0x180111e8b  jmp     loc_180111DCB
0x180111e90  mov     rcx, [rbp+hMem]
0x180111e94  mov     r8, rdi
0x180111e97  mov     rdx, rdi
0x180111e9a  call    cs:__imp_AppContainerRegisterSid
0x180111ea1  nop     dword ptr [rax+rax+00h]
0x180111ea6  mov     ebx, eax
0x180111ea8  mov     eax, 80000000h
0x180111ead  lea     ecx, [rbx+rax]
0x180111eb0  test    eax, ecx
0x180111eb2  jnz     loc_180111F3B
0x180111eb8  cmp     ebx, esi
0x180111eba  jz      short loc_180111F3B
0x180111ebc  mov     edx, 97h
0x180111ec1  jmp     loc_180111DCB
0x180111ec6  mov     rsi, [rbp+hMem]
0x180111eca  test    rsi, rsi
0x180111ecd  jz      short loc_180111EFA
0x180111ecf  call    cs:__imp_GetLastError
0x180111ed6  nop     dword ptr [rax+rax+00h]
0x180111edb  mov     rcx, rsi; hMem
0x180111ede  mov     ebx, eax
0x180111ee0  call    cs:__imp_LocalFree
0x180111ee7  nop     dword ptr [rax+rax+00h]
0x180111eec  mov     ecx, ebx; dwErrCode
0x180111eee  call    cs:__imp_SetLastError
0x180111ef5  nop     dword ptr [rax+rax+00h]
0x180111efa  lea     rax, [rbp+hMem]
0x180111efe  mov     [rbp+hMem], 0
0x180111f06  mov     [rsp+48h+var_20], rax
0x180111f0b  mov     r9, r15
0x180111f0e  mov     r8, rdi
0x180111f11  mov     [rsp+48h+var_28], 2
0x180111f19  mov     rdx, rdi
0x180111f1c  mov     rcx, rdi
0x180111f1f  call    cs:__imp_CreateAppContainerProfile
0x180111f26  nop     dword ptr [rax+rax+00h]
0x180111f2b  mov     ebx, eax
0x180111f2d  test    eax, eax
0x180111f2f  jns     short loc_180111F3B
0x180111f31  mov     edx, 8Eh
0x180111f36  jmp     loc_180111DCB
0x180111f3b  lea     rax, [rbp+hMem]
0x180111f3f  cmp     r14, rax
0x180111f42  jz      short loc_180111F86
0x180111f44  mov     rdi, [r14]
0x180111f47  mov     rsi, [rbp+hMem]
0x180111f4b  test    rdi, rdi
0x180111f4e  jz      short loc_180111F7B
0x180111f50  call    cs:__imp_GetLastError
0x180111f57  nop     dword ptr [rax+rax+00h]
0x180111f5c  mov     rcx, rdi; hMem
0x180111f5f  mov     ebx, eax
0x180111f61  call    cs:__imp_LocalFree
0x180111f68  nop     dword ptr [rax+rax+00h]
0x180111f6d  mov     ecx, ebx; dwErrCode
0x180111f6f  call    cs:__imp_SetLastError
0x180111f76  nop     dword ptr [rax+rax+00h]
0x180111f7b  xor     ecx, ecx
0x180111f7d  mov     [r14], rsi
0x180111f80  mov     [rbp+hMem], rcx
0x180111f84  jmp     short loc_180111F8A
0x180111f86  mov     rcx, [rbp+hMem]; hMem
0x180111f8a  test    rcx, rcx
0x180111f8d  jz      short loc_180111F9B
0x180111f8f  call    cs:__imp_LocalFree
0x180111f96  nop     dword ptr [rax+rax+00h]
0x180111f9b  xor     eax, eax
0x180111f9d  add     rsp, 48h
0x180111fa1  pop     r15
0x180111fa3  pop     r14
0x180111fa5  pop     rdi
0x180111fa6  pop     rsi
0x180111fa7  pop     rbx
0x180111fa8  pop     rbp
0x180111fa9  retn
```
