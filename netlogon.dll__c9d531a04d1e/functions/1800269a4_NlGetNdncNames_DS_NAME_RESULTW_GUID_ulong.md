# NlGetNdncNames(DS_NAME_RESULTW * * *,_GUID * *,ulong *)

- ea: `0x1800269a4`
- end: `0x180026c89`
- name: `?NlGetNdncNames@@YAJPEAPEAPEAUDS_NAME_RESULTW@@PEAPEAU_GUID@@PEAK@Z`
- size: `741`
- prototype: `__int64 __fastcall(struct DS_NAME_RESULTW ***, struct _GUID **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180028384`

## callees

- `0x180007278`
- `0x18000d710`
- `0x1800109fc`
- `0x1800269a4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800269e3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026b00`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026b24`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800269e3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026b00`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026b24`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180026a4b`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180026a4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026a87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026c62`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026c70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026a87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026c62`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026c70`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180026c07`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180026c52`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180026c07`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180026c52`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x180026b82`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x180026b82`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationNamesList` at `0x180026a1e`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationNamesList` at `0x180026a6a`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationNamesList` at `0x180026a1e`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationNamesList` at `0x180026a6a`

## string_xrefs

- `0x180026ab5`: `onecore\ds\netapi\svcdlls\logonsrv\server\domain.cxx`
- `0x180026c29`: `NlGetNdncNames: GetConfigurationNamesList returned 0 entries\n`

## pseudocode

```c
__int64 __fastcall NlGetNdncNames(struct DS_NAME_RESULTW ***a1, struct _GUID **a2, unsigned int *a3)
{
  _QWORD *v3; // rdi
  int ConfigurationNamesList; // ebx
  _QWORD *v5; // rsi
  struct _GUID *v6; // r12
  __int64 v7; // r13
  unsigned int v8; // r14d
  char *v9; // r9
  _QWORD *v10; // rax
  _QWORD *v11; // r14
  __int64 v12; // rax
  __int64 v13; // r14
  __int64 v14; // rbx
  DWORD v15; // eax
  __int64 status; // r9
  __int64 cItems; // r8
  __int64 v18; // rcx
  __int64 i; // rdi
  LPCWSTR rpNames; // [rsp+40h] [rbp-18h] BYREF
  PDS_NAME_RESULTW pResult; // [rsp+48h] [rbp-10h] BYREF
  SIZE_T uBytes; // [rsp+B8h] [rbp+60h] BYREF

  rpNames = 0;
  LODWORD(uBytes) = 2280;
  pResult = 0;
  v3 = LocalAlloc(0, 0x8E8u);
  if ( v3 )
  {
    v5 = 0;
    v6 = 0;
    v7 = 0;
    v8 = 0;
    if ( (unsigned __int8)IsDsGetServersAndSitesForNetLogonPresent() )
      ConfigurationNamesList = GetConfigurationNamesList(9, 264, &uBytes, v3);
    else
      ConfigurationNamesList = -1073741637;
    while ( ConfigurationNamesList == -1073741789 )
    {
      if ( v8 >= 0x14 )
      {
        NlAssertFailed(
          "LocalReAllocLoopCount < 20",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\domain.cxx",
          599,
          v9);
        ConfigurationNamesList = -1073741595;
        goto LABEL_11;
      }
      v10 = LocalReAlloc(v3, (unsigned int)uBytes, 2u);
      if ( !v10 )
      {
        ConfigurationNamesList = -1073741801;
LABEL_11:
        v11 = 0;
        goto LABEL_12;
      }
      v3 = v10;
      ConfigurationNamesList = GetConfigurationNamesList(9, 264, &uBytes, v10);
      ++v8;
    }
    if ( ConfigurationNamesList < 0 )
      goto LABEL_11;
    LODWORD(v12) = 0;
    if ( !*v3 )
      goto LABEL_36;
    do
    {
      v12 = (unsigned int)(v12 + 1);
      v13 = (unsigned int)v12;
    }
    while ( v3[v12] );
    if ( (_DWORD)v12 )
    {
      v5 = LocalAlloc(0x40u, 8 * v12);
      if ( v5 )
      {
        v6 = (struct _GUID *)LocalAlloc(0x40u, 16 * v13);
        v11 = v5;
        if ( v6 )
        {
          v14 = 0;
          if ( *v3 )
          {
            do
            {
              rpNames = (LPCWSTR)(v3[v14] + 56LL);
              v15 = DsCrackNamesW(
                      0,
                      DS_NAME_FLAG_SYNTACTICAL_ONLY,
                      DS_FQDN_1779_NAME,
                      DS_CANONICAL_NAME,
                      1u,
                      &rpNames,
                      &pResult);
              if ( v15 )
              {
                NlPrintRoutine(0x100u, L"NlGetNdncNames: DsCrackNamesW failed for %ws: 0x%lx\n", rpNames, v15);
              }
              else
              {
                status = pResult->rItems->status;
                if ( (_DWORD)status )
                {
                  NlPrintRoutine(
                    0x100u,
                    L"NlGetNdncNames: DsCrackNamesW substatus error for %ws: 0x%lx\n",
                    rpNames,
                    status);
                }
                else
                {
                  cItems = pResult->cItems;
                  if ( (_DWORD)cItems == 1 )
                  {
                    v5[v7] = pResult;
                    v18 = (unsigned int)v7;
                    v7 = (unsigned int)(v7 + 1);
                    v6[v18] = *(struct _GUID *)(v3[v14] + 8LL);
                    pResult = 0;
                  }
                  else
                  {
                    NlPrintRoutine(
                      0x100u,
                      L"NlGetNdncNames: DsCrackNamesW returned %lu names for %ws\n",
                      cItems,
                      rpNames);
                  }
                }
              }
              if ( pResult )
              {
                DsFreeNameResultW(pResult);
                pResult = 0;
              }
              v14 = (unsigned int)(v14 + 1);
            }
            while ( v3[v14] );
          }
          ConfigurationNamesList = 0;
        }
        else
        {
          ConfigurationNamesList = -1073741801;
        }
      }
      else
      {
        ConfigurationNamesList = -1073741801;
        v11 = 0;
      }
    }
    else
    {
LABEL_36:
      NlPrintRoutine(0x100u, L"NlGetNdncNames: GetConfigurationNamesList returned 0 entries\n");
      v11 = 0;
    }
LABEL_12:
    LocalFree(v3);
    if ( ConfigurationNamesList < 0 )
    {
      if ( v5 )
      {
        for ( i = 0; (unsigned int)i < (unsigned int)v7; i = (unsigned int)(i + 1) )
          DsFreeNameResultW((DS_NAME_RESULTW *)v11[i]);
        LocalFree(v5);
      }
      if ( v6 )
        LocalFree(v6);
    }
    else
    {
      *a3 = v7;
      *a1 = (struct DS_NAME_RESULTW **)v5;
      *a2 = v6;
    }
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return (unsigned int)ConfigurationNamesList;
}

```

## disassembly

```asm
0x1800269a4  mov     [rsp-40h+arg_10], r8
0x1800269a9  mov     [rsp-40h+arg_8], rdx
0x1800269ae  mov     [rsp-40h+arg_0], rcx
0x1800269b3  push    rbp
0x1800269b4  push    rbx
0x1800269b5  push    rsi
0x1800269b6  push    rdi
0x1800269b7  push    r12
0x1800269b9  push    r13
0x1800269bb  push    r14
0x1800269bd  push    r15
0x1800269bf  mov     rbp, rsp
0x1800269c2  sub     rsp, 58h
0x1800269c6  mov     edx, 8E8h; uBytes
0x1800269cb  mov     [rbp+var_18], 0
0x1800269d3  xor     ecx, ecx; uFlags
0x1800269d5  mov     dword ptr [rbp+uBytes], edx
0x1800269d8  mov     r15, r8
0x1800269db  mov     [rbp+pResult], 0
0x1800269e3  call    cs:__imp_LocalAlloc
0x1800269e9  mov     rdi, rax
0x1800269ec  test    rax, rax
0x1800269ef  jnz     short loc_1800269FB
0x1800269f1  mov     ebx, 0C0000017h
0x1800269f6  jmp     loc_180026C76
0x1800269fb  xor     esi, esi
0x1800269fd  xor     r12d, r12d
0x180026a00  xor     r13d, r13d
0x180026a03  xor     r14d, r14d
0x180026a06  call    IsDsGetServersAndSitesForNetLogonPresent
0x180026a0b  test    al, al
0x180026a0d  jz      short loc_180026A28
0x180026a0f  mov     r9, rdi
0x180026a12  lea     r8, [rbp+uBytes]
0x180026a16  mov     edx, 108h
0x180026a1b  lea     ecx, [rsi+9]
0x180026a1e  call    cs:__imp_GetConfigurationNamesList
0x180026a24  mov     ebx, eax
0x180026a26  jmp     short loc_180026A2D
0x180026a28  mov     ebx, 0C00000BBh
0x180026a2d  cmp     ebx, 0C0000023h
0x180026a33  jnz     loc_180026ACF
0x180026a39  cmp     r14d, 14h
0x180026a3d  jnb     short loc_180026AAF
0x180026a3f  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x180026a42  mov     r8d, 2; uFlags
0x180026a48  mov     rcx, rdi; hMem
0x180026a4b  call    cs:__imp_LocalReAlloc
0x180026a51  test    rax, rax
0x180026a54  jz      short loc_180026A77
0x180026a56  mov     r9, rax
0x180026a59  lea     r8, [rbp+uBytes]
0x180026a5d  mov     edx, 108h
0x180026a62  mov     ecx, 9
0x180026a67  mov     rdi, rax
0x180026a6a  call    cs:__imp_GetConfigurationNamesList
0x180026a70  mov     ebx, eax
0x180026a72  inc     r14d
0x180026a75  jmp     short loc_180026A2D
0x180026a77  mov     ebx, 0C0000017h
0x180026a7c  mov     r14, rsi
0x180026a7f  test    rdi, rdi
0x180026a82  jz      short loc_180026A91
0x180026a84  mov     rcx, rdi; hMem
0x180026a87  call    cs:__imp_LocalFree
0x180026a8d  mov     r15, [rbp+arg_10]
0x180026a91  test    ebx, ebx
0x180026a93  js      loc_180026C42
0x180026a99  mov     rax, [rbp+arg_0]
0x180026a9d  mov     [r15], r13d
0x180026aa0  mov     [rax], rsi
0x180026aa3  mov     rax, [rbp+arg_8]
0x180026aa7  mov     [rax], r12
0x180026aaa  jmp     loc_180026C76
0x180026aaf  mov     r8d, 257h; unsigned int
0x180026ab5  lea     rdx, aOnecoreDsNetap_23; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180026abc  lea     rcx, aLocalrealloclo; "LocalReAllocLoopCount < 20"
0x180026ac3  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180026ac8  mov     ebx, 0C00000E5h
0x180026acd  jmp     short loc_180026A7C
0x180026acf  test    ebx, ebx
0x180026ad1  js      short loc_180026A7C
0x180026ad3  xor     eax, eax
0x180026ad5  cmp     [rdi], rax
0x180026ad8  jz      loc_180026C29
0x180026ade  inc     eax
0x180026ae0  mov     r14d, eax
0x180026ae3  lea     rdx, ds:0[rax*8]; uBytes
0x180026aeb  cmp     [rdx+rdi], rsi
0x180026aef  jnz     short loc_180026ADE
0x180026af1  test    eax, eax
0x180026af3  jz      loc_180026C29
0x180026af9  mov     ebx, 40h ; '@'
0x180026afe  mov     ecx, ebx; uFlags
0x180026b00  call    cs:__imp_LocalAlloc
0x180026b06  mov     rsi, rax
0x180026b09  test    rax, rax
0x180026b0c  jnz     short loc_180026B1B
0x180026b0e  mov     ebx, 0C0000017h
0x180026b13  mov     r14, rax
0x180026b16  jmp     loc_180026A84
0x180026b1b  shl     r14, 4
0x180026b1f  mov     ecx, ebx; uFlags
0x180026b21  mov     rdx, r14; uBytes
0x180026b24  call    cs:__imp_LocalAlloc
0x180026b2a  mov     r12, rax
0x180026b2d  mov     r14, rsi
0x180026b30  test    rax, rax
0x180026b33  jnz     short loc_180026B3F
0x180026b35  mov     ebx, 0C0000017h
0x180026b3a  jmp     loc_180026A84
0x180026b3f  xor     ebx, ebx
0x180026b41  cmp     [rdi], rbx
0x180026b44  jz      loc_180026C22
0x180026b4a  mov     r15d, 100h
0x180026b50  mov     rax, [rdi+rbx*8]
0x180026b54  xor     ecx, ecx; hDS
0x180026b56  add     rax, 38h ; '8'
0x180026b5a  mov     [rbp+var_18], rax
0x180026b5e  lea     rax, [rbp+pResult]
0x180026b62  mov     [rsp+58h+ppResult], rax; ppResult
0x180026b67  lea     rax, [rbp+var_18]
0x180026b6b  mov     [rsp+58h+rpNames], rax; rpNames
0x180026b70  mov     eax, 1
0x180026b75  mov     r8d, eax; formatOffered
0x180026b78  mov     [rsp+58h+cNames], eax; cNames
0x180026b7c  mov     edx, eax; flags
0x180026b7e  lea     r9d, [rax+6]; formatDesired
0x180026b82  call    cs:__imp_DsCrackNamesW
0x180026b88  test    eax, eax
0x180026b8a  jz      short loc_180026B98
0x180026b8c  mov     r9d, eax
0x180026b8f  lea     rdx, aNlgetndncnames; "NlGetNdncNames: DsCrackNamesW failed fo"...
0x180026b96  jmp     short loc_180026BAF
0x180026b98  mov     rdx, [rbp+pResult]
0x180026b9c  mov     rax, [rdx+8]
0x180026ba0  mov     r9d, [rax]
0x180026ba3  test    r9d, r9d
0x180026ba6  jz      short loc_180026BBD
0x180026ba8  lea     rdx, aNlgetndncnames_2; "NlGetNdncNames: DsCrackNamesW substatus"...
0x180026baf  mov     r8, [rbp+var_18]
0x180026bb3  mov     ecx, r15d; unsigned int
0x180026bb6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180026bbb  jmp     short loc_180026BFE
0x180026bbd  mov     r8d, [rdx]
0x180026bc0  cmp     r8d, 1
0x180026bc4  jz      short loc_180026BDB
0x180026bc6  mov     r9, [rbp+var_18]
0x180026bca  lea     rdx, aNlgetndncnames_0; "NlGetNdncNames: DsCrackNamesW returned "...
0x180026bd1  mov     ecx, r15d; unsigned int
0x180026bd4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180026bd9  jmp     short loc_180026BFE
0x180026bdb  mov     [rsi+r13*8], rdx
0x180026bdf  mov     rax, [rdi+rbx*8]
0x180026be3  mov     ecx, r13d
0x180026be6  add     rcx, rcx
0x180026be9  inc     r13d
0x180026bec  movups  xmm0, xmmword ptr [rax+8]
0x180026bf0  movdqu  xmmword ptr [r12+rcx*8], xmm0
0x180026bf6  mov     [rbp+pResult], 0
0x180026bfe  mov     rcx, [rbp+pResult]; pResult
0x180026c02  test    rcx, rcx
0x180026c05  jz      short loc_180026C15
0x180026c07  call    cs:__imp_DsFreeNameResultW
0x180026c0d  mov     [rbp+pResult], 0
0x180026c15  inc     ebx
0x180026c17  cmp     qword ptr [rdi+rbx*8], 0
0x180026c1c  jnz     loc_180026B50
0x180026c22  xor     ebx, ebx
0x180026c24  jmp     loc_180026A84
0x180026c29  lea     rdx, aNlgetndncnames_1; "NlGetNdncNames: GetConfigurationNamesLi"...
0x180026c30  mov     ecx, 100h; unsigned int
0x180026c35  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180026c3a  xor     r14d, r14d
0x180026c3d  jmp     loc_180026A84
0x180026c42  test    rsi, rsi
0x180026c45  jz      short loc_180026C68
0x180026c47  xor     edi, edi
0x180026c49  test    r13d, r13d
0x180026c4c  jz      short loc_180026C5F
0x180026c4e  mov     rcx, [r14+rdi*8]; pResult
0x180026c52  call    cs:__imp_DsFreeNameResultW
0x180026c58  inc     edi
0x180026c5a  cmp     edi, r13d
0x180026c5d  jb      short loc_180026C4E
0x180026c5f  mov     rcx, rsi; hMem
0x180026c62  call    cs:__imp_LocalFree
0x180026c68  test    r12, r12
0x180026c6b  jz      short loc_180026C76
0x180026c6d  mov     rcx, r12; hMem
0x180026c70  call    cs:__imp_LocalFree
0x180026c76  mov     eax, ebx
0x180026c78  add     rsp, 58h
0x180026c7c  pop     r15
0x180026c7e  pop     r14
0x180026c80  pop     r13
0x180026c82  pop     r12
0x180026c84  pop     rdi
0x180026c85  pop     rsi
0x180026c86  pop     rbx
0x180026c87  pop     rbp
0x180026c88  retn
```
