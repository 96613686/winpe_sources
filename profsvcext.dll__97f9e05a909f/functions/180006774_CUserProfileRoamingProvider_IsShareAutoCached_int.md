# CUserProfileRoamingProvider::_IsShareAutoCached(int *)

- ea: `0x180006774`
- end: `0x180006a79`
- name: `?_IsShareAutoCached@CUserProfileRoamingProvider@@AEAAJPEAH@Z`
- size: `773`
- prototype: `__int64 __fastcall(CUserProfileRoamingProvider *__hidden this, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180016a1c`

## callees

- `0x180006774`
- `0x180006a80`
- `0x180006a9c`
- `0x180006b18`
- `0x180008ea0`
- `0x180013a20`
- `0x1800165f0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1800068f4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18000695d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1800068f4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18000695d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x18000692e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x18000692e`
- `srvcli!NetShareGetInfo` at `0x180006871`
- `srvcli!NetShareGetInfo` at `0x1800069af`
- `srvcli!NetShareGetInfo` at `0x180006871`
- `srvcli!NetShareGetInfo` at `0x1800069af`
- `netutils!NetApiBufferFree` at `0x1800069dc`
- `netutils!NetApiBufferFree` at `0x1800069f4`
- `netutils!NetApiBufferFree` at `0x180006a15`
- `netutils!NetApiBufferFree` at `0x180006a2d`
- `netutils!NetApiBufferFree` at `0x1800069dc`
- `netutils!NetApiBufferFree` at `0x1800069f4`
- `netutils!NetApiBufferFree` at `0x180006a15`
- `netutils!NetApiBufferFree` at `0x180006a2d`

## string_xrefs

- `0x1800067bb`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180006884`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x1800068cb`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180006949`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x1800069bd`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180006a4e`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUserProfileRoamingProvider::_IsShareAutoCached(CUserProfileRoamingProvider *this, int *a2)
{
  __int64 v2; // rcx
  const unsigned __int16 *v4; // rax
  int v5; // eax
  unsigned int v6; // ebx
  WCHAR *v7; // rbx
  LPWSTR v8; // rdi
  unsigned int v9; // r14d
  WCHAR *v10; // r15
  int v11; // esi
  __int64 v12; // rdx
  unsigned int Info; // eax
  __int64 v14; // rdx
  LPBYTE v15; // rcx
  int v16; // eax
  __int64 v17; // rdx
  CUserProfileRoamingProvider *v18; // rcx
  unsigned __int16 *v19; // rdi
  __int64 v20; // rdx
  __int64 v21; // r9
  int v22; // eax
  DWORD v23; // eax
  LPBYTE v24; // rcx
  int v25; // eax
  unsigned __int64 v27[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+40h]
  LPBYTE bufptr; // [rsp+80h] [rbp+48h] BYREF
  LPWSTR servername; // [rsp+88h] [rbp+50h] BYREF
  LPBYTE v31; // [rsp+90h] [rbp+58h] BYREF
  LPWSTR v32; // [rsp+98h] [rbp+60h] BYREF

  v2 = *((_QWORD *)this + 1);
  *a2 = 0;
  servername = 0;
  v4 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 56LL))(v2);
  v5 = HeapDupStr(v4, &servername);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46F,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)(unsigned int)v5,
      v27[0]);
    return v6;
  }
  v7 = servername;
  v32 = servername;
  if ( !servername || !*servername || !servername[1] || !servername[2] )
  {
    v6 = -2147418113;
    v12 = 1143;
    goto LABEL_54;
  }
  v8 = servername + 2;
  v9 = 0;
  v10 = 0;
  v11 = 1;
  while ( *v8 )
  {
    if ( *v8 == 92 )
    {
      if ( ++v9 == 1 )
      {
        *v8 = 0;
        v10 = v8 + 1;
      }
      else if ( v9 == 2 )
      {
        *v8 = 0;
        break;
      }
    }
    ++v8;
  }
  if ( !v10 )
  {
    v6 = -2147024735;
    v12 = 1174;
LABEL_54:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)v6,
      v27[0]);
LABEL_55:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v32);
    return v6;
  }
  bufptr = 0;
  Info = NetShareGetInfo(v7, v10, 0x3EDu, &bufptr);
  if ( Info )
  {
    v14 = 1178;
LABEL_19:
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v14,
           (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
           (const char *)Info,
           v27[0]);
    goto LABEL_44;
  }
  v15 = bufptr;
  if ( (*(_DWORD *)bufptr & 2) != 0 )
  {
    if ( v9 < 2 )
    {
      v17 = 1192;
LABEL_27:
      v6 = -2147467259;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)0x80004005LL,
        v27[0]);
      goto LABEL_44;
    }
    *(v10 - 1) = 92;
    *v8 = 92;
    if ( !PathRemoveFileSpecW(v7) )
    {
      v17 = 1201;
      goto LABEL_27;
    }
    servername = 0;
    Info = CUserProfileRoamingProvider::_GetNetworkPhysicalPath(v18, v7, &servername);
    if ( Info )
    {
      v14 = 1205;
      goto LABEL_19;
    }
    v19 = servername;
    if ( PathStripToRootW(servername) )
    {
      if ( PathRemoveFileSpecW(v19) )
      {
        v27[0] = 0;
        v22 = StringCchLengthW(v19, 0x7FFFFFFFu, v27);
        v6 = v22;
        if ( v22 >= 0 )
        {
          v31 = 0;
          v23 = NetShareGetInfo(v19, &v19[v27[0] + 1], 0x3EDu, &v31);
          if ( !v23 )
          {
            v24 = v31;
            v25 = *(_DWORD *)v31 & 0x30;
            if ( v25 == 48 || !v25 )
              v11 = 0;
            *a2 = v11;
            NetApiBufferFree(v24);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&servername);
            v15 = bufptr;
            goto LABEL_50;
          }
          v6 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x4C4,
                 (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
                 (const char *)v23,
                 v27[0]);
          if ( v31 )
            NetApiBufferFree(v31);
          goto LABEL_43;
        }
        v21 = (unsigned int)v22;
        v20 = 1214;
LABEL_35:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
          (const char *)v21,
          v27[0]);
LABEL_43:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&servername);
LABEL_44:
        if ( bufptr )
          NetApiBufferFree(bufptr);
        goto LABEL_55;
      }
      v20 = 1211;
    }
    else
    {
      v20 = 1210;
    }
    v6 = -2147467259;
    v21 = 2147500037LL;
    goto LABEL_35;
  }
  v16 = *(_DWORD *)bufptr & 0x30;
  if ( v16 == 48 || !v16 )
    v11 = 0;
  *a2 = v11;
LABEL_50:
  if ( v15 )
    NetApiBufferFree(v15);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v32);
  return 0;
}

```

## disassembly

```asm
0x180006774  push    rbp
0x180006776  push    rbx
0x180006777  push    rsi
0x180006778  push    rdi
0x180006779  push    r12
0x18000677b  push    r13
0x18000677d  push    r14
0x18000677f  push    r15
0x180006781  mov     rbp, rsp
0x180006784  sub     rsp, 38h
0x180006788  mov     rcx, [rcx+8]
0x18000678c  xor     r13d, r13d
0x18000678f  mov     r12, rdx
0x180006792  mov     [rdx], r13d
0x180006795  mov     [rbp+servername], r13
0x180006799  mov     rax, [rcx]
0x18000679c  mov     rax, [rax+38h]
0x1800067a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067a5  mov     rcx, rax; unsigned __int16 *
0x1800067a8  lea     rdx, [rbp+servername]; unsigned __int16 **
0x1800067ac  call    ?HeapDupStr@@YAJPEBGPEAPEAG@Z; HeapDupStr(ushort const *,ushort * *)
0x1800067b1  mov     ebx, eax
0x1800067b3  test    eax, eax
0x1800067b5  jns     short loc_1800067D4
0x1800067b7  mov     rcx, [rbp+40h]; this
0x1800067bb  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x1800067c2  mov     r9d, eax; char *
0x1800067c5  mov     edx, 46Fh; void *
0x1800067ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800067cf  jmp     loc_180006A66
0x1800067d4  mov     rbx, [rbp+servername]
0x1800067d8  mov     [rbp+arg_18], rbx
0x1800067dc  test    rbx, rbx
0x1800067df  jz      loc_180006A40
0x1800067e5  cmp     [rbx], r13w
0x1800067e9  jz      loc_180006A40
0x1800067ef  cmp     [rbx+2], r13w
0x1800067f4  jz      loc_180006A40
0x1800067fa  cmp     [rbx+4], r13w
0x1800067ff  jz      loc_180006A40
0x180006805  mov     eax, 5Ch ; '\'
0x18000680a  lea     rdi, [rbx+4]
0x18000680e  mov     r14d, r13d
0x180006811  mov     r15, r13
0x180006814  lea     esi, [rax-5Bh]
0x180006817  cmp     [rdi], r13w
0x18000681b  jz      short loc_180006849
0x18000681d  cmp     [rdi], ax
0x180006820  jnz     short loc_18000683F
0x180006822  add     r14d, esi
0x180006825  cmp     r14d, esi
0x180006828  jnz     short loc_180006839
0x18000682a  mov     [rdi], r13w
0x18000682e  lea     r15, [rdi+2]
0x180006832  mov     eax, 5Ch ; '\'
0x180006837  jmp     short loc_18000683F
0x180006839  cmp     r14d, 2
0x18000683d  jz      short loc_180006845
0x18000683f  add     rdi, 2
0x180006843  jmp     short loc_180006817
0x180006845  mov     [rdi], r13w
0x180006849  test    r15, r15
0x18000684c  jnz     short loc_18000685D
0x18000684e  mov     ebx, 800700A1h
0x180006853  mov     edx, 496h
0x180006858  jmp     loc_180006A4A
0x18000685d  lea     r9, [rbp+bufptr]; bufptr
0x180006861  mov     [rbp+bufptr], r13
0x180006865  mov     r8d, 3EDh; level
0x18000686b  mov     rdx, r15; netname
0x18000686e  mov     rcx, rbx; servername
0x180006871  call    cs:__imp_NetShareGetInfo
0x180006877  test    eax, eax
0x180006879  jz      short loc_18000689A
0x18000687b  mov     edx, 49Ah; void *
0x180006880  mov     rcx, [rbp+40h]; this
0x180006884  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x18000688b  mov     r9d, eax; char *
0x18000688e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180006893  mov     ebx, eax
0x180006895  jmp     loc_1800069EB
0x18000689a  mov     rcx, [rbp+bufptr]
0x18000689e  mov     eax, [rcx]
0x1800068a0  test    al, 2
0x1800068a2  jnz     short loc_1800068BC
0x1800068a4  and     eax, 30h
0x1800068a7  cmp     eax, 30h ; '0'
0x1800068aa  jz      short loc_1800068B0
0x1800068ac  test    eax, eax
0x1800068ae  jnz     short loc_1800068B3
0x1800068b0  mov     esi, r13d
0x1800068b3  mov     [r12], esi
0x1800068b7  jmp     loc_180006A28
0x1800068bc  cmp     r14d, 2
0x1800068c0  jnb     short loc_1800068E4
0x1800068c2  mov     edx, 4A8h; void *
0x1800068c7  mov     rcx, [rbp+40h]; this
0x1800068cb  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x1800068d2  mov     ebx, 80004005h
0x1800068d7  mov     r9d, ebx; char *
0x1800068da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800068df  jmp     loc_1800069EB
0x1800068e4  mov     eax, 5Ch ; '\'
0x1800068e9  mov     rcx, rbx; pszPath
0x1800068ec  mov     [r15-2], ax
0x1800068f1  mov     [rdi], ax
0x1800068f4  call    cs:__imp_PathRemoveFileSpecW
0x1800068fa  test    eax, eax
0x1800068fc  jnz     short loc_180006905
0x1800068fe  mov     edx, 4B1h
0x180006903  jmp     short loc_1800068C7
0x180006905  lea     r8, [rbp+servername]; unsigned __int16 **
0x180006909  mov     [rbp+servername], r13
0x18000690d  mov     rdx, rbx; unsigned __int16 *
0x180006910  call    ?_GetNetworkPhysicalPath@CUserProfileRoamingProvider@@AEAAKPEBGPEAPEAG@Z; CUserProfileRoamingProvider::_GetNetworkPhysicalPath(ushort const *,ushort * *)
0x180006915  test    eax, eax
0x180006917  jz      short loc_180006923
0x180006919  mov     edx, 4B5h
0x18000691e  jmp     loc_180006880
0x180006923  mov     rdi, [rbp+servername]
0x180006927  mov     rcx, rdi; pszPath
0x18000692a  mov     [rbp+servername], rdi
0x18000692e  call    cs:__imp_PathStripToRootW
0x180006934  test    eax, eax
0x180006936  jnz     short loc_18000695A
0x180006938  mov     edx, 4BAh; void *
0x18000693d  mov     ebx, 80004005h
0x180006942  mov     r9d, ebx; char *
0x180006945  mov     rcx, [rbp+40h]; this
0x180006949  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180006950  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006955  jmp     loc_1800069E2
0x18000695a  mov     rcx, rdi; pszPath
0x18000695d  call    cs:__imp_PathRemoveFileSpecW
0x180006963  test    eax, eax
0x180006965  jnz     short loc_18000696E
0x180006967  mov     edx, 4BBh
0x18000696c  jmp     short loc_18000693D
0x18000696e  lea     r8, [rbp+var_18]; unsigned __int64 *
0x180006972  mov     [rbp+var_18], r13
0x180006976  mov     edx, 7FFFFFFFh; unsigned __int64
0x18000697b  mov     rcx, rdi; unsigned __int16 *
0x18000697e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180006983  mov     ebx, eax
0x180006985  test    eax, eax
0x180006987  jns     short loc_180006993
0x180006989  mov     r9d, eax
0x18000698c  mov     edx, 4BEh
0x180006991  jmp     short loc_180006945
0x180006993  mov     rax, [rbp+var_18]
0x180006997  lea     r9, [rbp+arg_10]; bufptr
0x18000699b  inc     rax
0x18000699e  mov     [rbp+arg_10], r13
0x1800069a2  mov     r8d, 3EDh; level
0x1800069a8  mov     rcx, rdi; servername
0x1800069ab  lea     rdx, [rdi+rax*2]; netname
0x1800069af  call    cs:__imp_NetShareGetInfo
0x1800069b5  test    eax, eax
0x1800069b7  jz      short loc_1800069FC
0x1800069b9  mov     rcx, [rbp+40h]; this
0x1800069bd  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x1800069c4  mov     r9d, eax; char *
0x1800069c7  mov     edx, 4C4h; void *
0x1800069cc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800069d1  mov     rcx, [rbp+arg_10]; Buffer
0x1800069d5  mov     ebx, eax
0x1800069d7  test    rcx, rcx
0x1800069da  jz      short loc_1800069E2
0x1800069dc  call    cs:__imp_NetApiBufferFree
0x1800069e2  lea     rcx, [rbp+servername]
0x1800069e6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800069eb  mov     rcx, [rbp+bufptr]; Buffer
0x1800069ef  test    rcx, rcx
0x1800069f2  jz      short loc_180006A5D
0x1800069f4  call    cs:__imp_NetApiBufferFree
0x1800069fa  jmp     short loc_180006A5D
0x1800069fc  mov     rcx, [rbp+arg_10]; Buffer
0x180006a00  mov     eax, [rcx]
0x180006a02  and     eax, 30h
0x180006a05  cmp     eax, 30h ; '0'
0x180006a08  jz      short loc_180006A0E
0x180006a0a  test    eax, eax
0x180006a0c  jnz     short loc_180006A11
0x180006a0e  mov     esi, r13d
0x180006a11  mov     [r12], esi
0x180006a15  call    cs:__imp_NetApiBufferFree
0x180006a1b  lea     rcx, [rbp+servername]
0x180006a1f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006a24  mov     rcx, [rbp+bufptr]; Buffer
0x180006a28  test    rcx, rcx
0x180006a2b  jz      short loc_180006A33
0x180006a2d  call    cs:__imp_NetApiBufferFree
0x180006a33  lea     rcx, [rbp+arg_18]
0x180006a37  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006a3c  xor     eax, eax
0x180006a3e  jmp     short loc_180006A68
0x180006a40  mov     ebx, 8000FFFFh
0x180006a45  mov     edx, 477h; void *
0x180006a4a  mov     rcx, [rbp+40h]; this
0x180006a4e  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180006a55  mov     r9d, ebx; char *
0x180006a58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006a5d  lea     rcx, [rbp+arg_18]
0x180006a61  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180006a66  mov     eax, ebx
0x180006a68  add     rsp, 38h
0x180006a6c  pop     r15
0x180006a6e  pop     r14
0x180006a70  pop     r13
0x180006a72  pop     r12
0x180006a74  pop     rdi
0x180006a75  pop     rsi
0x180006a76  pop     rbx
0x180006a77  pop     rbp
0x180006a78  retn
```
