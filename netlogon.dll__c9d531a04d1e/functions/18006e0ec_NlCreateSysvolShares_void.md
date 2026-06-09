# NlCreateSysvolShares(void)

- ea: `0x18006e0ec`
- end: `0x18006e5a1`
- name: `?NlCreateSysvolShares@@YAHXZ`
- size: `1205`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180026508`
- `0x18004e118`
- `0x18006f490`

## callees

- `0x180007278`
- `0x18000edf4`
- `0x180025708`
- `0x180026180`
- `0x180034fa8`
- `0x18003f648`
- `0x18006e0ec`
- `0x180082e88`
- `0x180083250`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e3ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e3ef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006e2b8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006e3a6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006e2b8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006e3a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e56c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e57a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e56c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e57a`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18006e3e5`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18006e3e5`
- `LSASRV!LsaISafeMode` at `0x18006e136`
- `LSASRV!LsaISafeMode` at `0x18006e136`
- `ntdll!RtlLeaveCriticalSection` at `0x18006e2cd`
- `ntdll!RtlLeaveCriticalSection` at `0x18006e443`
- `ntdll!RtlLeaveCriticalSection` at `0x18006e477`
- `ntdll!RtlLeaveCriticalSection` at `0x18006e2cd`
- `ntdll!RtlLeaveCriticalSection` at `0x18006e443`
- `ntdll!RtlLeaveCriticalSection` at `0x18006e477`
- `ntdll!RtlEnterCriticalSection` at `0x18006e27b`
- `ntdll!RtlEnterCriticalSection` at `0x18006e27b`
- `ntdll!RtlGetNtProductType` at `0x18006e112`
- `ntdll!RtlGetNtProductType` at `0x18006e112`
- `netutils!NetApiBufferFree` at `0x18006e588`
- `netutils!NetApiBufferFree` at `0x18006e588`
- `srvcli!NetShareDel` at `0x18006e1ff`
- `srvcli!NetShareDel` at `0x18006e53c`
- `srvcli!NetShareDel` at `0x18006e1ff`
- `srvcli!NetShareDel` at `0x18006e53c`

## string_xrefs

- `0x18006e19b`: `NlCreateShare %lu\n`
- `0x18006e4dc`: `NlCreateShare %lu\n`
- `0x18006e25c`: `NlCreateSysvolShares: Cannot find primary domain.\n`
- `0x18006e407`: `NlCreateSysvolShares: Failed to rename junction: %ws %ws 0x%lx\n`
- `0x18006e45d`: `Renamed SysVol junction from %ws to %ws\n`

## pseudocode

```c
__int64 NlCreateSysvolShares(void)
{
  int v0; // r13d
  int v1; // r9d
  unsigned int v2; // edi
  enum _NT_PRODUCT_TYPE v3; // eax
  WCHAR *v4; // r14
  unsigned __int16 *v5; // r15
  WCHAR *v6; // r12
  unsigned int Share; // eax
  int v8; // r9d
  DWORD v9; // eax
  unsigned __int16 *v10; // rbx
  struct _DOMAIN_INFO *NetbiosDomain; // rsi
  int v12; // ecx
  __int64 v13; // r13
  __int64 v14; // rax
  size_t v15; // rbx
  WCHAR *v16; // rax
  const void *v17; // rdx
  size_t v18; // r8
  const char *v19; // rdx
  const CHAR *v20; // rcx
  SIZE_T v21; // rbx
  wchar_t *v22; // rax
  DWORD LastError; // eax
  unsigned __int16 *v24; // rdx
  int v25; // eax
  unsigned int v26; // eax
  DWORD v27; // eax
  unsigned __int16 **v29; // [rsp+20h] [rbp-48h]
  unsigned int v30; // [rsp+28h] [rbp-40h]
  unsigned __int16 *v31; // [rsp+48h] [rbp-20h] BYREF
  unsigned __int16 *v32[2]; // [rsp+50h] [rbp-18h] BYREF
  unsigned __int16 v33; // [rsp+B0h] [rbp+48h]
  DWORD v34; // [rsp+B8h] [rbp+50h] BYREF
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+C0h] [rbp+58h] BYREF
  int v36; // [rsp+C8h] [rbp+60h]

  v34 = 0;
  v0 = 0;
  ProductType = 0;
  v36 = 0;
  v2 = 1;
  if ( RtlGetNtProductType(&ProductType) )
  {
    v3 = ProductType;
  }
  else
  {
    v3 = NtProductWinNt;
    ProductType = NtProductWinNt;
  }
  if ( NlGlobalMemberWorkstation )
  {
    if ( v3 != NtProductLanManNt && !(unsigned __int8)LsaISafeMode() )
      return v2;
    v0 = 1;
    v36 = 1;
  }
  v4 = 0;
  v5 = 0;
  v6 = 0;
  if ( !dword_1800F124C || v0 )
  {
    v9 = NetShareDel(0, (LPWSTR)L"SYSVOL", 0);
    v34 = v9;
    if ( v9 && v9 != 2310 )
      NlPrintRoutine(0x100u, L"NetShareDel SYSVOL failed %lu\n", v9);
  }
  else
  {
    Share = NlCreateShare(Src, L"SYSVOL", 1u, v1, dword_1800F1270, v30);
    v34 = Share;
    if ( Share )
    {
      NlPrintRoutine(0x100u, L"NlCreateShare %lu\n", Share);
      v32[0] = Src;
      v32[1] = (unsigned __int16 *)v34;
      NlpWriteEventlog(0x164Au, 1u, 0x40000000u, v32, 2u, (unsigned __int8 *)&v34, 4u);
    }
  }
  v10 = (unsigned __int16 *)qword_1800F11E8;
  if ( qword_1800F11E8 || !Src || v0 )
  {
    v25 = 0;
LABEL_39:
    if ( !dword_1800F124C && v25 || v0 )
    {
      v27 = NetShareDel(0, (LPWSTR)L"NETLOGON", 0);
      v34 = v27;
      if ( v27 && v27 != 2310 )
        NlPrintRoutine(0x100u, L"NetShareDel NETLOGON failed %lu\n", v27);
    }
    else if ( v10 )
    {
      v26 = NlCreateShare(v10, L"NETLOGON", 0, v8, dword_1800F1274, v30);
      v34 = v26;
      if ( v26 )
      {
        *(_OWORD *)v32 = 0;
        NlPrintRoutine(0x100u, L"NlCreateShare %lu\n", v26);
        v32[1] = (unsigned __int16 *)v34;
        v32[0] = v10;
        NlpWriteEventlog(0x164Au, 1u, 0x40000000u, v32, 2u, (unsigned __int8 *)&v34, 4u);
      }
    }
    if ( !v4 )
      goto LABEL_50;
    goto LABEL_49;
  }
  NetbiosDomain = NlFindNetbiosDomain(0, 1u);
  if ( !NetbiosDomain )
  {
    NlPrintRoutine(0x100u, L"NlCreateSysvolShares: Cannot find primary domain.\n");
    return 0;
  }
  RtlEnterCriticalSection(&NlGlobalDomainCritSect);
  v12 = *((unsigned __int16 *)NetbiosDomain + 64);
  if ( !(_WORD)v12 )
  {
LABEL_35:
    RtlLeaveCriticalSection(&NlGlobalDomainCritSect);
    NlDereferenceDomain(NetbiosDomain);
    v25 = 1;
    v10 = v4;
    goto LABEL_39;
  }
  v13 = -1;
  v14 = -1;
  do
    ++v14;
  while ( Src[v14] );
  v15 = (unsigned int)(2 * v14);
  v16 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)(v15 + v12 + 20));
  v4 = v16;
  if ( !v16 )
  {
    RtlLeaveCriticalSection(&NlGlobalDomainCritSect);
    NlDereferenceDomain(NetbiosDomain);
    return 0;
  }
  memcpy_0(v16, Src, v15);
  *(WCHAR *)((char *)v4 + v15) = 92;
  v17 = (const void *)*((_QWORD *)NetbiosDomain + 17);
  v18 = *((unsigned __int16 *)NetbiosDomain + 64) - 2LL;
  v32[0] = (WCHAR *)((char *)v4 + v15 + 2);
  memcpy_0(v32[0], v17, v18);
  v33 = *((_WORD *)NetbiosDomain + 64);
  v19 = (const char *)*((_QWORD *)NetbiosDomain + 20);
  if ( !v19 || (unsigned int)NlEqualDnsNameUtf8(*((const char **)NetbiosDomain + 19), v19) )
  {
LABEL_34:
    v24 = v32[0];
    v0 = v36;
    *(_OWORD *)((char *)v32[0] + v33 - 2) = *(_OWORD *)L"\\SCRIPTS";
    *(unsigned __int16 *)((char *)v24 + v33 + 14) = aScripts_0[8];
    goto LABEL_35;
  }
  v20 = (const CHAR *)*((_QWORD *)NetbiosDomain + 20);
  v31 = 0;
  if ( !NetpAllocWStrFromUtf8StrAsRequired(v20, 0xFFFFFFFF, 0, 0, &v31) )
  {
    v5 = v31;
    if ( v31 )
    {
      do
        ++v13;
      while ( v31[v13] );
      v21 = (unsigned int)(v15 + 2 * v13 + 4);
      v22 = (wchar_t *)LocalAlloc(0x40u, v21);
      v6 = v22;
      if ( v22 )
      {
        swprintf_s(v22, v21 >> 1, L"%ws\\%ws", Src, v5);
        if ( MoveFileExW(v6, v4, 2u) )
        {
          NlPrintRoutine(1u, L"Renamed SysVol junction from %ws to %ws\n", v6, v4);
        }
        else
        {
          LastError = GetLastError();
          v34 = LastError;
          if ( LastError != 2 )
          {
            LODWORD(v29) = LastError;
            NlPrintRoutine(0x100u, L"NlCreateSysvolShares: Failed to rename junction: %ws %ws 0x%lx\n", v6, v4, v29);
          }
        }
        goto LABEL_34;
      }
    }
  }
  RtlLeaveCriticalSection(&NlGlobalDomainCritSect);
  NlDereferenceDomain(NetbiosDomain);
  v2 = 0;
LABEL_49:
  LocalFree(v4);
LABEL_50:
  if ( v6 )
    LocalFree(v6);
  if ( v5 )
    NetApiBufferFree(v5);
  return v2;
}

```

## disassembly

```asm
0x18006e0ec  push    rbp
0x18006e0ee  push    rbx
0x18006e0ef  push    rsi
0x18006e0f0  push    rdi
0x18006e0f1  push    r12
0x18006e0f3  push    r13
0x18006e0f5  push    r14
0x18006e0f7  push    r15
0x18006e0f9  mov     rbp, rsp
0x18006e0fc  sub     rsp, 68h
0x18006e100  xor     esi, esi
0x18006e102  lea     rcx, [rbp+ProductType]; ProductType
0x18006e106  mov     [rbp+arg_8], esi
0x18006e109  mov     r13d, esi
0x18006e10c  mov     [rbp+ProductType], esi
0x18006e10f  mov     [rbp+arg_18], esi
0x18006e112  call    cs:__imp_RtlGetNtProductType
0x18006e118  lea     edi, [rsi+1]
0x18006e11b  test    al, al
0x18006e11d  jnz     short loc_18006E126
0x18006e11f  mov     eax, edi
0x18006e121  mov     [rbp+ProductType], eax
0x18006e124  jmp     short loc_18006E129
0x18006e126  mov     eax, [rbp+ProductType]
0x18006e129  cmp     cs:?NlGlobalMemberWorkstation@@3HA, esi; int NlGlobalMemberWorkstation
0x18006e12f  jz      short loc_18006E14A
0x18006e131  cmp     eax, 2
0x18006e134  jz      short loc_18006E144
0x18006e136  call    cs:__imp_LsaISafeMode
0x18006e13c  test    al, al
0x18006e13e  jz      loc_18006E58E
0x18006e144  mov     r13d, edi
0x18006e147  mov     [rbp+arg_18], edi
0x18006e14a  cmp     cs:dword_1800F124C, esi
0x18006e150  mov     r14, rsi
0x18006e153  mov     r15, rsi
0x18006e156  mov     r12, rsi
0x18006e159  mov     ebx, 100h
0x18006e15e  jz      loc_18006E1F3
0x18006e164  test    r13d, r13d
0x18006e167  jnz     loc_18006E1F3
0x18006e16d  mov     eax, cs:dword_1800F1270
0x18006e173  lea     rdx, netname; "SYSVOL"
0x18006e17a  mov     rcx, cs:Src; unsigned __int16 *
0x18006e181  mov     r8b, dil; unsigned __int8
0x18006e184  mov     dword ptr [rsp+68h+var_48], eax; int
0x18006e188  call    ?NlCreateShare@@YAKPEAG0EHHK@Z; NlCreateShare(ushort *,ushort *,uchar,int,int,ulong)
0x18006e18d  mov     [rbp+arg_8], eax
0x18006e190  test    eax, eax
0x18006e192  jz      loc_18006E224
0x18006e198  xorps   xmm0, xmm0
0x18006e19b  lea     rdx, aNlcreateshareL; "NlCreateShare %lu\n"
0x18006e1a2  mov     r8d, eax
0x18006e1a5  mov     ecx, ebx; unsigned int
0x18006e1a7  movups  xmmword ptr [rbp+var_18], xmm0
0x18006e1ab  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006e1b0  mov     rax, cs:Src
0x18006e1b7  lea     r9, [rbp+var_18]; unsigned __int16 **
0x18006e1bb  mov     [rbp+var_18], rax
0x18006e1bf  mov     r8d, 40000000h; unsigned int
0x18006e1c5  mov     eax, [rbp+arg_8]
0x18006e1c8  mov     edx, edi; unsigned int
0x18006e1ca  mov     [rbp+var_18+8], rax
0x18006e1ce  mov     ecx, 164Ah; unsigned int
0x18006e1d3  lea     rax, [rbp+arg_8]
0x18006e1d7  mov     [rsp+68h+var_38], 4; unsigned int
0x18006e1df  mov     [rsp+68h+var_40], rax; unsigned __int8 *
0x18006e1e4  mov     dword ptr [rsp+68h+var_48], 2; unsigned int
0x18006e1ec  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x18006e1f1  jmp     short loc_18006E224
0x18006e1f3  xor     r8d, r8d; reserved
0x18006e1f6  lea     rdx, netname; "SYSVOL"
0x18006e1fd  xor     ecx, ecx; servername
0x18006e1ff  call    cs:__imp_NetShareDel
0x18006e205  mov     [rbp+arg_8], eax
0x18006e208  test    eax, eax
0x18006e20a  jz      short loc_18006E224
0x18006e20c  cmp     eax, 906h
0x18006e211  jz      short loc_18006E224
0x18006e213  mov     r8d, eax
0x18006e216  lea     rdx, aNetsharedelSys; "NetShareDel SYSVOL failed %lu\n"
0x18006e21d  mov     ecx, ebx; unsigned int
0x18006e21f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006e224  mov     rbx, cs:qword_1800F11E8
0x18006e22b  test    rbx, rbx
0x18006e22e  jnz     loc_18006E48E
0x18006e234  cmp     cs:Src, rsi
0x18006e23b  jz      loc_18006E48E
0x18006e241  test    r13d, r13d
0x18006e244  jnz     loc_18006E48E
0x18006e24a  mov     dl, dil; unsigned __int8
0x18006e24d  xor     ecx, ecx; SourceString
0x18006e24f  call    ?NlFindNetbiosDomain@@YAPEAU_DOMAIN_INFO@@PEBGE@Z; NlFindNetbiosDomain(ushort const *,uchar)
0x18006e254  mov     rsi, rax
0x18006e257  test    rax, rax
0x18006e25a  jnz     short loc_18006E274
0x18006e25c  lea     rdx, aNlcreatesysvol; "NlCreateSysvolShares: Cannot find prima"...
0x18006e263  mov     ecx, 100h; unsigned int
0x18006e268  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006e26d  mov     edi, ebx
0x18006e26f  jmp     loc_18006E58E
0x18006e274  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18006e27b  call    cs:__imp_RtlEnterCriticalSection
0x18006e281  movzx   ecx, word ptr [rsi+80h]
0x18006e288  test    cx, cx
0x18006e28b  jz      loc_18006E43C
0x18006e291  mov     rdx, cs:Src
0x18006e298  or      r13, 0FFFFFFFFFFFFFFFFh
0x18006e29c  mov     rax, r13
0x18006e29f  inc     rax
0x18006e2a2  cmp     [rdx+rax*2], bx
0x18006e2a6  jnz     short loc_18006E29F
0x18006e2a8  lea     ebx, [rax+rax]
0x18006e2ab  lea     edx, [rcx+14h]
0x18006e2ae  mov     [rbp+var_28], ebx
0x18006e2b1  add     edx, ebx; uBytes
0x18006e2b3  mov     ecx, 40h ; '@'; uFlags
0x18006e2b8  call    cs:__imp_LocalAlloc
0x18006e2be  mov     r14, rax
0x18006e2c1  test    rax, rax
0x18006e2c4  jnz     short loc_18006E2E2
0x18006e2c6  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18006e2cd  call    cs:__imp_RtlLeaveCriticalSection
0x18006e2d3  mov     rcx, rsi; struct _DOMAIN_INFO *
0x18006e2d6  call    ?NlDereferenceDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDereferenceDomain(_DOMAIN_INFO *)
0x18006e2db  xor     edi, edi
0x18006e2dd  jmp     loc_18006E58E
0x18006e2e2  mov     rdx, cs:Src; Src
0x18006e2e9  mov     r8, rbx; Size
0x18006e2ec  mov     rcx, r14; void *
0x18006e2ef  call    memcpy_0
0x18006e2f4  mov     word ptr [rbx+r14], 5Ch ; '\'
0x18006e2fb  lea     rax, [r14+2]
0x18006e2ff  movzx   r8d, word ptr [rsi+80h]
0x18006e307  add     rax, rbx
0x18006e30a  mov     rdx, [rsi+88h]; Src
0x18006e311  mov     rcx, rax; void *
0x18006e314  sub     r8, 2; Size
0x18006e318  mov     [rbp+var_18], rax
0x18006e31c  call    memcpy_0
0x18006e321  movzx   edx, word ptr [rsi+80h]
0x18006e328  xor     ebx, ebx
0x18006e32a  mov     [rbp+arg_0], dx
0x18006e32e  mov     rdx, [rsi+0A0h]; char *
0x18006e335  test    rdx, rdx
0x18006e338  jz      loc_18006E418
0x18006e33e  mov     rcx, [rsi+98h]; char *
0x18006e345  call    ?NlEqualDnsNameUtf8@@YAHPEBD0@Z; NlEqualDnsNameUtf8(char const *,char const *)
0x18006e34a  test    eax, eax
0x18006e34c  jnz     loc_18006E418
0x18006e352  mov     rcx, [rsi+0A0h]; lpMultiByteStr
0x18006e359  lea     rax, [rbp+var_20]
0x18006e35d  xor     r9d, r9d; unsigned __int16 *
0x18006e360  mov     [rsp+68h+var_48], rax; unsigned __int16 **
0x18006e365  xor     r8d, r8d; unsigned int
0x18006e368  mov     [rbp+var_20], rbx
0x18006e36c  or      edx, 0FFFFFFFFh; cbMultiByte
0x18006e36f  call    ?NetpAllocWStrFromUtf8StrAsRequired@@YAKPEADKKPEAGPEAPEAG@Z; NetpAllocWStrFromUtf8StrAsRequired(char *,ulong,ulong,ushort *,ushort * *)
0x18006e374  test    eax, eax
0x18006e376  jnz     loc_18006E470
0x18006e37c  mov     r15, [rbp+var_20]
0x18006e380  test    r15, r15
0x18006e383  jz      loc_18006E470
0x18006e389  inc     r13
0x18006e38c  cmp     [r15+r13*2], bx
0x18006e391  jnz     short loc_18006E389
0x18006e393  mov     eax, [rbp+var_28]
0x18006e396  mov     ecx, 40h ; '@'; uFlags
0x18006e39b  lea     eax, [rax+r13*2]
0x18006e39f  add     eax, 4
0x18006e3a2  mov     edx, eax; uBytes
0x18006e3a4  mov     ebx, eax
0x18006e3a6  call    cs:__imp_LocalAlloc
0x18006e3ac  mov     r12, rax
0x18006e3af  test    rax, rax
0x18006e3b2  jz      loc_18006E470
0x18006e3b8  mov     r9, cs:Src
0x18006e3bf  lea     r8, aWsWs_1; "%ws\\%ws"
0x18006e3c6  shr     rbx, 1
0x18006e3c9  mov     rcx, rax; Buffer
0x18006e3cc  mov     rdx, rbx; BufferCount
0x18006e3cf  mov     [rsp+68h+var_48], r15
0x18006e3d4  call    swprintf_s
0x18006e3d9  mov     r8d, 2; dwFlags
0x18006e3df  mov     rdx, r14; lpNewFileName
0x18006e3e2  mov     rcx, r12; lpExistingFileName
0x18006e3e5  call    cs:__imp_MoveFileExW
0x18006e3eb  test    eax, eax
0x18006e3ed  jnz     short loc_18006E45A
0x18006e3ef  call    cs:__imp_GetLastError
0x18006e3f5  mov     [rbp+arg_8], eax
0x18006e3f8  cmp     eax, 2
0x18006e3fb  jz      short loc_18006E418
0x18006e3fd  mov     r9, r14
0x18006e400  mov     dword ptr [rsp+68h+var_48], eax
0x18006e404  mov     r8, r12
0x18006e407  lea     rdx, aNlcreatesysvol_0; "NlCreateSysvolShares: Failed to rename "...
0x18006e40e  mov     ecx, 100h; unsigned int
0x18006e413  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006e418  movzx   ecx, [rbp+arg_0]
0x18006e41c  mov     rdx, [rbp+var_18]
0x18006e420  movups  xmm0, xmmword ptr cs:aScripts_0; "\\SCRIPTS"
0x18006e427  mov     r13d, [rbp+arg_18]
0x18006e42b  movups  xmmword ptr [rcx+rdx-2], xmm0
0x18006e430  movzx   eax, word ptr cs:aScripts_0+10h; ""
0x18006e437  mov     [rcx+rdx+0Eh], ax
0x18006e43c  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18006e443  call    cs:__imp_RtlLeaveCriticalSection
0x18006e449  mov     rcx, rsi; struct _DOMAIN_INFO *
0x18006e44c  call    ?NlDereferenceDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDereferenceDomain(_DOMAIN_INFO *)
0x18006e451  mov     eax, edi
0x18006e453  xor     esi, esi
0x18006e455  mov     rbx, r14
0x18006e458  jmp     short loc_18006E490
0x18006e45a  mov     r9, r14
0x18006e45d  lea     rdx, aRenamedSysvolJ; "Renamed SysVol junction from %ws to %ws"...
0x18006e464  mov     r8, r12
0x18006e467  mov     ecx, edi; unsigned int
0x18006e469  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006e46e  jmp     short loc_18006E418
0x18006e470  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18006e477  call    cs:__imp_RtlLeaveCriticalSection
0x18006e47d  mov     rcx, rsi; struct _DOMAIN_INFO *
0x18006e480  call    ?NlDereferenceDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDereferenceDomain(_DOMAIN_INFO *)
0x18006e485  xor     esi, esi
0x18006e487  mov     edi, esi
0x18006e489  jmp     loc_18006E569
0x18006e48e  mov     eax, esi
0x18006e490  cmp     cs:dword_1800F124C, esi
0x18006e496  jnz     short loc_18006E4A0
0x18006e498  test    eax, eax
0x18006e49a  jnz     loc_18006E530
0x18006e4a0  test    r13d, r13d
0x18006e4a3  jnz     loc_18006E530
0x18006e4a9  test    rbx, rbx
0x18006e4ac  jz      loc_18006E564
0x18006e4b2  mov     eax, cs:dword_1800F1274
0x18006e4b8  lea     rdx, aNetlogon_0; "NETLOGON"
0x18006e4bf  xor     r8d, r8d; unsigned __int8
0x18006e4c2  mov     dword ptr [rsp+68h+var_48], eax; int
0x18006e4c6  mov     rcx, rbx; unsigned __int16 *
0x18006e4c9  call    ?NlCreateShare@@YAKPEAG0EHHK@Z; NlCreateShare(ushort *,ushort *,uchar,int,int,ulong)
0x18006e4ce  mov     [rbp+arg_8], eax
0x18006e4d1  test    eax, eax
0x18006e4d3  jz      loc_18006E564
0x18006e4d9  xorps   xmm0, xmm0
0x18006e4dc  lea     rdx, aNlcreateshareL; "NlCreateShare %lu\n"
0x18006e4e3  mov     r8d, eax
0x18006e4e6  mov     ecx, 100h; unsigned int
0x18006e4eb  movups  xmmword ptr [rbp+var_18], xmm0
0x18006e4ef  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006e4f4  mov     eax, [rbp+arg_8]
0x18006e4f7  lea     r9, [rbp+var_18]; unsigned __int16 **
0x18006e4fb  mov     [rbp+var_18+8], rax
0x18006e4ff  mov     r8d, 40000000h; unsigned int
0x18006e505  lea     rax, [rbp+arg_8]
0x18006e509  mov     [rsp+68h+var_38], 4; unsigned int
0x18006e511  mov     [rsp+68h+var_40], rax; unsigned __int8 *
0x18006e516  mov     edx, edi; unsigned int
0x18006e518  mov     ecx, 164Ah; unsigned int
0x18006e51d  mov     dword ptr [rsp+68h+var_48], 2; unsigned int
0x18006e525  mov     [rbp+var_18], rbx
0x18006e529  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x18006e52e  jmp     short loc_18006E564
0x18006e530  xor     r8d, r8d; reserved
0x18006e533  lea     rdx, aNetlogon_0; "NETLOGON"
0x18006e53a  xor     ecx, ecx; servername
0x18006e53c  call    cs:__imp_NetShareDel
0x18006e542  mov     [rbp+arg_8], eax
0x18006e545  test    eax, eax
0x18006e547  jz      short loc_18006E564
0x18006e549  cmp     eax, 906h
0x18006e54e  jz      short loc_18006E564
0x18006e550  mov     r8d, eax
0x18006e553  lea     rdx, aNetsharedelNet; "NetShareDel NETLOGON failed %lu\n"
0x18006e55a  mov     ecx, 100h; unsigned int
0x18006e55f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006e564  test    r14, r14
0x18006e567  jz      short loc_18006E572
0x18006e569  mov     rcx, r14; hMem
0x18006e56c  call    cs:__imp_LocalFree
0x18006e572  test    r12, r12
0x18006e575  jz      short loc_18006E580
0x18006e577  mov     rcx, r12; hMem
0x18006e57a  call    cs:__imp_LocalFree
0x18006e580  test    r15, r15
0x18006e583  jz      short loc_18006E58E
0x18006e585  mov     rcx, r15; Buffer
0x18006e588  call    cs:__imp_NetApiBufferFree
0x18006e58e  mov     eax, edi
0x18006e590  add     rsp, 68h
0x18006e594  pop     r15
0x18006e596  pop     r14
0x18006e598  pop     r13
0x18006e59a  pop     r12
0x18006e59c  pop     rdi
0x18006e59d  pop     rsi
0x18006e59e  pop     rbx
0x18006e59f  pop     rbp
0x18006e5a0  retn
  ... truncated ...
```
