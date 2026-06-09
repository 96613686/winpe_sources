# NlGetNdncNames(DS_NAME_RESULTW * * *,_GUID * *,ulong *)

- ea: `0x180027c6c`
- end: `0x180027f9e`
- name: `?NlGetNdncNames@@YAJPEAPEAPEAUDS_NAME_RESULTW@@PEAPEAU_GUID@@PEAK@Z`
- size: `818`
- prototype: `__int64 __fastcall(struct DS_NAME_RESULTW ***, struct _GUID **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180029858`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x1800110ac`
- `0x180027c6c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027cab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027dea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027e14`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027cab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027dea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027e14`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180027d23`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180027d23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027d6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027f6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027f7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027d6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027f6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027f7e`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180027f03`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180027f54`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180027f03`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180027f54`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x180027e78`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x180027e78`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationNamesList` at `0x180027cec`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationNamesList` at `0x180027d48`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationNamesList` at `0x180027cec`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetConfigurationNamesList` at `0x180027d48`

## string_xrefs

- `0x180027d9f`: `onecore\ds\netapi\svcdlls\logonsrv\server\domain.cxx`
- `0x180027f2b`: `NlGetNdncNames: GetConfigurationNamesList returned 0 entries\n`

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
          0x257u,
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
0x180027c6c  mov     [rsp-40h+arg_10], r8
0x180027c71  mov     [rsp-40h+arg_8], rdx
0x180027c76  mov     [rsp-40h+arg_0], rcx
0x180027c7b  push    rbp
0x180027c7c  push    rbx
0x180027c7d  push    rsi
0x180027c7e  push    rdi
0x180027c7f  push    r12
0x180027c81  push    r13
0x180027c83  push    r14
0x180027c85  push    r15
0x180027c87  mov     rbp, rsp
0x180027c8a  sub     rsp, 58h
0x180027c8e  mov     edx, 8E8h; uBytes
0x180027c93  mov     [rbp+var_18], 0
0x180027c9b  xor     ecx, ecx; uFlags
0x180027c9d  mov     dword ptr [rbp+uBytes], edx
0x180027ca0  mov     r15, r8
0x180027ca3  mov     [rbp+pResult], 0
0x180027cab  call    cs:__imp_LocalAlloc
0x180027cb2  nop     dword ptr [rax+rax+00h]
0x180027cb7  mov     rdi, rax
0x180027cba  test    rax, rax
0x180027cbd  jnz     short loc_180027CC9
0x180027cbf  mov     ebx, 0C0000017h
0x180027cc4  jmp     loc_180027F8A
0x180027cc9  xor     esi, esi
0x180027ccb  xor     r12d, r12d
0x180027cce  xor     r13d, r13d
0x180027cd1  xor     r14d, r14d
0x180027cd4  call    IsDsGetServersAndSitesForNetLogonPresent
0x180027cd9  test    al, al
0x180027cdb  jz      short loc_180027CFC
0x180027cdd  mov     r9, rdi
0x180027ce0  lea     r8, [rbp+uBytes]
0x180027ce4  mov     edx, 108h
0x180027ce9  lea     ecx, [rsi+9]
0x180027cec  call    cs:__imp_GetConfigurationNamesList
0x180027cf3  nop     dword ptr [rax+rax+00h]
0x180027cf8  mov     ebx, eax
0x180027cfa  jmp     short loc_180027D01
0x180027cfc  mov     ebx, 0C00000BBh
0x180027d01  cmp     ebx, 0C0000023h
0x180027d07  jnz     loc_180027DB9
0x180027d0d  cmp     r14d, 14h
0x180027d11  jnb     loc_180027D99
0x180027d17  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x180027d1a  mov     r8d, 2; uFlags
0x180027d20  mov     rcx, rdi; hMem
0x180027d23  call    cs:__imp_LocalReAlloc
0x180027d2a  nop     dword ptr [rax+rax+00h]
0x180027d2f  test    rax, rax
0x180027d32  jz      short loc_180027D5B
0x180027d34  mov     r9, rax
0x180027d37  lea     r8, [rbp+uBytes]
0x180027d3b  mov     edx, 108h
0x180027d40  mov     ecx, 9
0x180027d45  mov     rdi, rax
0x180027d48  call    cs:__imp_GetConfigurationNamesList
0x180027d4f  nop     dword ptr [rax+rax+00h]
0x180027d54  mov     ebx, eax
0x180027d56  inc     r14d
0x180027d59  jmp     short loc_180027D01
0x180027d5b  mov     ebx, 0C0000017h
0x180027d60  mov     r14, rsi
0x180027d63  test    rdi, rdi
0x180027d66  jz      short loc_180027D7B
0x180027d68  mov     rcx, rdi; hMem
0x180027d6b  call    cs:__imp_LocalFree
0x180027d72  nop     dword ptr [rax+rax+00h]
0x180027d77  mov     r15, [rbp+arg_10]
0x180027d7b  test    ebx, ebx
0x180027d7d  js      loc_180027F44
0x180027d83  mov     rax, [rbp+arg_0]
0x180027d87  mov     [r15], r13d
0x180027d8a  mov     [rax], rsi
0x180027d8d  mov     rax, [rbp+arg_8]
0x180027d91  mov     [rax], r12
0x180027d94  jmp     loc_180027F8A
0x180027d99  mov     r8d, 257h; unsigned int
0x180027d9f  lea     rdx, aOnecoreDsNetap_23; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180027da6  lea     rcx, aLocalrealloclo; "LocalReAllocLoopCount < 20"
0x180027dad  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180027db2  mov     ebx, 0C00000E5h
0x180027db7  jmp     short loc_180027D60
0x180027db9  test    ebx, ebx
0x180027dbb  js      short loc_180027D60
0x180027dbd  xor     eax, eax
0x180027dbf  cmp     [rdi], rax
0x180027dc2  jz      loc_180027F2B
0x180027dc8  inc     eax
0x180027dca  mov     r14d, eax
0x180027dcd  lea     rdx, ds:0[rax*8]; uBytes
0x180027dd5  cmp     [rdx+rdi], rsi
0x180027dd9  jnz     short loc_180027DC8
0x180027ddb  test    eax, eax
0x180027ddd  jz      loc_180027F2B
0x180027de3  mov     ebx, 40h ; '@'
0x180027de8  mov     ecx, ebx; uFlags
0x180027dea  call    cs:__imp_LocalAlloc
0x180027df1  nop     dword ptr [rax+rax+00h]
0x180027df6  mov     rsi, rax
0x180027df9  test    rax, rax
0x180027dfc  jnz     short loc_180027E0B
0x180027dfe  mov     ebx, 0C0000017h
0x180027e03  mov     r14, rax
0x180027e06  jmp     loc_180027D68
0x180027e0b  shl     r14, 4
0x180027e0f  mov     ecx, ebx; uFlags
0x180027e11  mov     rdx, r14; uBytes
0x180027e14  call    cs:__imp_LocalAlloc
0x180027e1b  nop     dword ptr [rax+rax+00h]
0x180027e20  mov     r12, rax
0x180027e23  mov     r14, rsi
0x180027e26  test    rax, rax
0x180027e29  jnz     short loc_180027E35
0x180027e2b  mov     ebx, 0C0000017h
0x180027e30  jmp     loc_180027D68
0x180027e35  xor     ebx, ebx
0x180027e37  cmp     [rdi], rbx
0x180027e3a  jz      loc_180027F24
0x180027e40  mov     r15d, 100h
0x180027e46  mov     rax, [rdi+rbx*8]
0x180027e4a  xor     ecx, ecx; hDS
0x180027e4c  add     rax, 38h ; '8'
0x180027e50  mov     [rbp+var_18], rax
0x180027e54  lea     rax, [rbp+pResult]
0x180027e58  mov     [rsp+58h+ppResult], rax; ppResult
0x180027e5d  lea     rax, [rbp+var_18]
0x180027e61  mov     [rsp+58h+rpNames], rax; rpNames
0x180027e66  mov     eax, 1
0x180027e6b  mov     r8d, eax; formatOffered
0x180027e6e  mov     [rsp+58h+cNames], eax; cNames
0x180027e72  mov     edx, eax; flags
0x180027e74  lea     r9d, [rax+6]; formatDesired
0x180027e78  call    cs:__imp_DsCrackNamesW
0x180027e7f  nop     dword ptr [rax+rax+00h]
0x180027e84  test    eax, eax
0x180027e86  jz      short loc_180027E94
0x180027e88  mov     r9d, eax
0x180027e8b  lea     rdx, aNlgetndncnames; "NlGetNdncNames: DsCrackNamesW failed fo"...
0x180027e92  jmp     short loc_180027EAB
0x180027e94  mov     rdx, [rbp+pResult]
0x180027e98  mov     rax, [rdx+8]
0x180027e9c  mov     r9d, [rax]
0x180027e9f  test    r9d, r9d
0x180027ea2  jz      short loc_180027EB9
0x180027ea4  lea     rdx, aNlgetndncnames_2; "NlGetNdncNames: DsCrackNamesW substatus"...
0x180027eab  mov     r8, [rbp+var_18]
0x180027eaf  mov     ecx, r15d; unsigned int
0x180027eb2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180027eb7  jmp     short loc_180027EFA
0x180027eb9  mov     r8d, [rdx]
0x180027ebc  cmp     r8d, 1
0x180027ec0  jz      short loc_180027ED7
0x180027ec2  mov     r9, [rbp+var_18]
0x180027ec6  lea     rdx, aNlgetndncnames_0; "NlGetNdncNames: DsCrackNamesW returned "...
0x180027ecd  mov     ecx, r15d; unsigned int
0x180027ed0  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180027ed5  jmp     short loc_180027EFA
0x180027ed7  mov     [rsi+r13*8], rdx
0x180027edb  mov     rax, [rdi+rbx*8]
0x180027edf  mov     ecx, r13d
0x180027ee2  add     rcx, rcx
0x180027ee5  inc     r13d
0x180027ee8  movups  xmm0, xmmword ptr [rax+8]
0x180027eec  movdqu  xmmword ptr [r12+rcx*8], xmm0
0x180027ef2  mov     [rbp+pResult], 0
0x180027efa  mov     rcx, [rbp+pResult]; pResult
0x180027efe  test    rcx, rcx
0x180027f01  jz      short loc_180027F17
0x180027f03  call    cs:__imp_DsFreeNameResultW
0x180027f0a  nop     dword ptr [rax+rax+00h]
0x180027f0f  mov     [rbp+pResult], 0
0x180027f17  inc     ebx
0x180027f19  cmp     qword ptr [rdi+rbx*8], 0
0x180027f1e  jnz     loc_180027E46
0x180027f24  xor     ebx, ebx
0x180027f26  jmp     loc_180027D68
0x180027f2b  lea     rdx, aNlgetndncnames_1; "NlGetNdncNames: GetConfigurationNamesLi"...
0x180027f32  mov     ecx, 100h; unsigned int
0x180027f37  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180027f3c  xor     r14d, r14d
0x180027f3f  jmp     loc_180027D68
0x180027f44  test    rsi, rsi
0x180027f47  jz      short loc_180027F76
0x180027f49  xor     edi, edi
0x180027f4b  test    r13d, r13d
0x180027f4e  jz      short loc_180027F67
0x180027f50  mov     rcx, [r14+rdi*8]; pResult
0x180027f54  call    cs:__imp_DsFreeNameResultW
0x180027f5b  nop     dword ptr [rax+rax+00h]
0x180027f60  inc     edi
0x180027f62  cmp     edi, r13d
0x180027f65  jb      short loc_180027F50
0x180027f67  mov     rcx, rsi; hMem
0x180027f6a  call    cs:__imp_LocalFree
0x180027f71  nop     dword ptr [rax+rax+00h]
0x180027f76  test    r12, r12
0x180027f79  jz      short loc_180027F8A
0x180027f7b  mov     rcx, r12; hMem
0x180027f7e  call    cs:__imp_LocalFree
0x180027f85  nop     dword ptr [rax+rax+00h]
0x180027f8a  mov     eax, ebx
0x180027f8c  add     rsp, 58h
0x180027f90  pop     r15
0x180027f92  pop     r14
0x180027f94  pop     r13
0x180027f96  pop     r12
0x180027f98  pop     rdi
0x180027f99  pop     rsi
0x180027f9a  pop     rbx
0x180027f9b  pop     rbp
0x180027f9c  retn
```
