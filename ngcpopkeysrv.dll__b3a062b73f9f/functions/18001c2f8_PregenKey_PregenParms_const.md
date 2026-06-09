# PregenKey(_PregenParms const *)

- ea: `0x18001c2f8`
- end: `0x18001c501`
- name: `?PregenKey@@YAJPEBU_PregenParms@@@Z`
- size: `521`
- prototype: `__int64 __fastcall(const struct _PregenParms *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019964`

## callees

- `0x18000b0fc`
- `0x18000db5c`
- `0x18001069c`
- `0x180010730`
- `0x18001a884`
- `0x18001b0b4`
- `0x18001c2f8`
- `0x18001d2e0`
- `0x180022ef4`
- `0x18002308c`
- `0x180023264`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001c3a7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001c3a7`

## string_xrefs

- `0x18001c3cf`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001c477`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001c4b6`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PregenKey(const unsigned __int16 **a1)
{
  const unsigned __int16 *v2; // rdx
  NgcUtils *v3; // rcx
  int NgcStateSeparatedRegistryLocation; // eax
  signed int v5; // ebx
  unsigned __int64 v6; // r9
  __int64 v7; // rdx
  LSTATUS v8; // eax
  int RegistryDwordValue; // eax
  unsigned int *v10; // r9
  unsigned int unused; // esi
  int v12; // eax
  char v13; // r14
  unsigned int v14; // edi
  int KeyAndAddToPool; // eax
  int v16; // eax
  unsigned int *dwOptions; // [rsp+20h] [rbp-60h]
  HKEY phkResult; // [rsp+50h] [rbp-30h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-28h] BYREF
  _QWORD v21[2]; // [rsp+60h] [rbp-20h] BYREF
  __int16 v22; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  signed int v24; // [rsp+C8h] [rbp+48h] BYREF
  struct HKEY__ v25; // [rsp+D0h] [rbp+50h] BYREF
  unsigned int v26; // [rsp+D8h] [rbp+58h] BYREF

  v24 = 0;
  phkResult = 0;
  v21[0] = &v24;
  v21[1] = &phkResult;
  v22 = 256;
  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSubKey,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        v3,
                                        v2,
                                        a1[3],
                                        (unsigned __int16 *)&lpSubKey);
  v5 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation >= 0 )
  {
    v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
    v5 = v8;
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    v24 = v5;
    if ( v5 >= 0 )
    {
      v25.unused = 0;
      RegistryDwordValue = NgcUtils::GetRegistryDwordValue(
                             (NgcUtils *)phkResult,
                             0,
                             (const unsigned __int16 *)&stru_18002B260,
                             (const unsigned __int16 *)&v25,
                             dwOptions);
      v5 = RegistryDwordValue;
      v24 = RegistryDwordValue;
      if ( RegistryDwordValue >= 0 )
      {
        unused = v25.unused;
      }
      else
      {
        if ( RegistryDwordValue != -2147024894 )
        {
          v6 = (unsigned int)RegistryDwordValue;
          v7 = 1558;
          goto LABEL_8;
        }
        unused = *((_DWORD *)a1 + 2);
      }
      v25.unused = 0;
      v12 = NgcUtils::QueryRegistrySubKeys((NgcUtils *)phkResult, &v25, &v26, v10);
      v5 = v12;
      v24 = v12;
      if ( v12 < 0 )
      {
        v6 = (unsigned int)v12;
        v7 = 1571;
        goto LABEL_8;
      }
      v5 = 0;
      v13 = 0;
      v14 = v25.unused;
      if ( unused < v25.unused )
        v14 = unused;
      if ( v14 < unused )
      {
        do
        {
          KeyAndAddToPool = CreateKeyAndAddToPool((const struct _PregenParms *)a1);
          v24 = KeyAndAddToPool;
          if ( KeyAndAddToPool >= 0 )
          {
            if ( *(_DWORD *)a1 == 1 )
              v13 = 1;
          }
          else
          {
            if ( !v5 )
              v5 = KeyAndAddToPool;
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x631,
              (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
              (const char *)(unsigned int)KeyAndAddToPool,
              (int)dwOptions);
          }
          ++v14;
        }
        while ( v14 < unused );
        if ( v13 )
        {
          v16 = NgcTriggerTask(2);
          if ( v16 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x641,
              (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
              (const char *)(unsigned int)v16,
              (int)dwOptions);
        }
      }
      v24 = v5;
      if ( v5 >= 0 )
      {
        v5 = 0;
        goto LABEL_32;
      }
      v7 = 1605;
    }
    else
    {
      v7 = 1548;
    }
    v6 = (unsigned int)v5;
  }
  else
  {
    v6 = (unsigned int)NgcStateSeparatedRegistryLocation;
    v7 = 1536;
  }
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
    (const char *)v6,
    (int)dwOptions);
LABEL_32:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
  wil::details::ScopeExitFnGuard__lambda_160704978f391369902b6f852049b64d___::operator()(v21);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001c2f8  push    rbp
0x18001c2fa  push    rbx
0x18001c2fb  push    rsi
0x18001c2fc  push    rdi
0x18001c2fd  push    r13
0x18001c2ff  push    r14
0x18001c301  push    r15
0x18001c303  mov     rbp, rsp
0x18001c306  sub     rsp, 80h
0x18001c30d  mov     r15, rcx
0x18001c310  mov     [rbp+arg_8], 0
0x18001c317  mov     [rbp+var_30], 0
0x18001c31f  lea     rax, [rbp+arg_8]
0x18001c323  mov     [rbp+var_20], rax
0x18001c327  lea     rax, [rbp+var_30]
0x18001c32b  mov     [rbp+var_18], rax
0x18001c32f  mov     [rbp+var_10], 100h
0x18001c335  mov     r13d, 1
0x18001c33b  mov     [rbp+lpSubKey], 0
0x18001c343  xor     edx, edx
0x18001c345  lea     rcx, [rbp+lpSubKey]
0x18001c349  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001c34e  lea     r9, [rbp+lpSubKey]; unsigned __int16 *
0x18001c352  mov     r8, [r15+18h]; unsigned __int16 *
0x18001c356  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001c35b  mov     ebx, eax
0x18001c35d  test    eax, eax
0x18001c35f  jns     short loc_18001C36B
0x18001c361  mov     r9d, eax
0x18001c364  mov     edx, 600h
0x18001c369  jmp     short loc_18001C3CB
0x18001c36b  mov     [rsp+80h+lpdwDisposition], 0; lpdwDisposition
0x18001c374  lea     rax, [rbp+var_30]
0x18001c378  mov     [rsp+80h+phkResult], rax; phkResult
0x18001c37d  mov     [rsp+80h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001c386  mov     [rsp+80h+samDesired], 2001Fh; samDesired
0x18001c38e  mov     dword ptr [rsp+80h+dwOptions], 0; int
0x18001c396  xor     r9d, r9d; lpClass
0x18001c399  xor     r8d, r8d; Reserved
0x18001c39c  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18001c3a0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c3a7  call    cs:__imp_RegCreateKeyExW
0x18001c3ad  mov     ebx, eax
0x18001c3af  test    eax, eax
0x18001c3b1  jle     short loc_18001C3BC
0x18001c3b3  movzx   ebx, ax
0x18001c3b6  or      ebx, 80070000h
0x18001c3bc  mov     [rbp+arg_8], ebx
0x18001c3bf  test    ebx, ebx
0x18001c3c1  jns     short loc_18001C3E0
0x18001c3c3  mov     edx, 60Ch; void *
0x18001c3c8  mov     r9d, ebx; char *
0x18001c3cb  mov     rcx, [rbp+38h]; this
0x18001c3cf  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001c3d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c3db  jmp     loc_18001C4DA
0x18001c3e0  mov     [rbp+arg_10.unused], 0
0x18001c3e7  lea     r9, [rbp+arg_10]; unsigned __int16 *
0x18001c3eb  lea     r8, stru_18002B260; unsigned __int16 *
0x18001c3f2  xor     edx, edx; HKEY
0x18001c3f4  mov     rcx, [rbp+var_30]; this
0x18001c3f8  call    ?GetRegistryDwordValue@NgcUtils@@YAJPEAUHKEY__@@PEBG1PEAK@Z; NgcUtils::GetRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001c3fd  mov     ebx, eax
0x18001c3ff  mov     [rbp+arg_8], eax
0x18001c402  test    eax, eax
0x18001c404  jns     short loc_18001C41D
0x18001c406  cmp     eax, 80070002h
0x18001c40b  jz      short loc_18001C417
0x18001c40d  mov     r9d, eax
0x18001c410  mov     edx, 616h
0x18001c415  jmp     short loc_18001C3CB
0x18001c417  mov     esi, [r15+8]
0x18001c41b  jmp     short loc_18001C420
0x18001c41d  mov     esi, [rbp+arg_10.unused]
0x18001c420  mov     [rbp+arg_10.unused], 0
0x18001c427  lea     r8, [rbp+arg_18]; unsigned int *
0x18001c42b  lea     rdx, [rbp+arg_10]; HKEY
0x18001c42f  mov     rcx, [rbp+var_30]; this
0x18001c433  call    ?QueryRegistrySubKeys@NgcUtils@@YAJPEAUHKEY__@@PEAK1@Z; NgcUtils::QueryRegistrySubKeys(HKEY__ *,ulong *,ulong *)
0x18001c438  mov     ebx, eax
0x18001c43a  mov     [rbp+arg_8], eax
0x18001c43d  test    eax, eax
0x18001c43f  jns     short loc_18001C44B
0x18001c441  mov     r9d, eax
0x18001c444  mov     edx, 623h
0x18001c449  jmp     short loc_18001C3CB
0x18001c44b  xor     ebx, ebx
0x18001c44d  xor     r14b, r14b
0x18001c450  mov     edi, [rbp+arg_10.unused]
0x18001c453  cmp     esi, edi
0x18001c455  cmovb   edi, esi
0x18001c458  cmp     edi, esi
0x18001c45a  jnb     short loc_18001C4C7
0x18001c45c  mov     rcx, r15; struct _PregenParms *
0x18001c45f  call    ?CreateKeyAndAddToPool@@YAJPEBU_PregenParms@@@Z; CreateKeyAndAddToPool(_PregenParms const *)
0x18001c464  mov     [rbp+arg_8], eax
0x18001c467  test    eax, eax
0x18001c469  jns     short loc_18001C48A
0x18001c46b  test    ebx, ebx
0x18001c46d  cmovz   ebx, eax
0x18001c470  mov     rcx, [rbp+38h]; this
0x18001c474  mov     r9d, eax; char *
0x18001c477  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001c47e  mov     edx, 631h; void *
0x18001c483  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c488  jmp     short loc_18001C495
0x18001c48a  movzx   r14d, r14b
0x18001c48e  cmp     [r15], r13d
0x18001c491  cmovz   r14d, r13d
0x18001c495  add     edi, r13d
0x18001c498  cmp     edi, esi
0x18001c49a  jb      short loc_18001C45C
0x18001c49c  test    r14b, r14b
0x18001c49f  jz      short loc_18001C4C7
0x18001c4a1  mov     ecx, 2
0x18001c4a6  call    NgcTriggerTask
0x18001c4ab  mov     rcx, [rbp+38h]; this
0x18001c4af  test    eax, eax
0x18001c4b1  jns     short loc_18001C4C7
0x18001c4b3  mov     r9d, eax; char *
0x18001c4b6  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001c4bd  mov     edx, 641h; void *
0x18001c4c2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c4c7  mov     [rbp+arg_8], ebx
0x18001c4ca  test    ebx, ebx
0x18001c4cc  jns     short loc_18001C4D8
0x18001c4ce  mov     edx, 645h
0x18001c4d3  jmp     loc_18001C3C8
0x18001c4d8  xor     ebx, ebx
0x18001c4da  lea     rcx, [rbp+lpSubKey]
0x18001c4de  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001c4e3  nop
0x18001c4e4  lea     rcx, [rbp+var_20]
0x18001c4e8  call    wil__details__ScopeExitFnGuard__lambda_160704978f391369902b6f852049b64d_____operator__
0x18001c4ed  mov     eax, ebx
0x18001c4ef  add     rsp, 80h
0x18001c4f6  pop     r15
0x18001c4f8  pop     r14
0x18001c4fa  pop     r13
0x18001c4fc  pop     rdi
0x18001c4fd  pop     rsi
0x18001c4fe  pop     rbx
0x18001c4ff  pop     rbp
0x18001c500  retn
```
