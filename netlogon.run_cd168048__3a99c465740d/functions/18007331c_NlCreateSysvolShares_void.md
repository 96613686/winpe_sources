# NlCreateSysvolShares(void)

- ea: `0x18007331c`
- end: `0x18007382c`
- name: `?NlCreateSysvolShares@@YAHXZ`
- size: `1296`
- prototype: `int(void)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180027748`
- `0x18005179c`
- `0x1800747cc`

## callees

- `0x180007518`
- `0x18000f4a4`
- `0x1800267ec`
- `0x180027350`
- `0x180036f50`
- `0x180041f80`
- `0x18007331c`
- `0x180088fe8`
- `0x180089414`
- `0x180090204`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007364f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007364f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180073500`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800735fa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180073500`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800735fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800737e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800737f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800737e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800737f8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18007363f`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18007363f`
- `LSASRV!LsaISafeMode` at `0x18007336c`
- `LSASRV!LsaISafeMode` at `0x18007336c`
- `ntdll!RtlLeaveCriticalSection` at `0x18007351b`
- `ntdll!RtlLeaveCriticalSection` at `0x1800736a9`
- `ntdll!RtlLeaveCriticalSection` at `0x1800736e3`
- `ntdll!RtlLeaveCriticalSection` at `0x18007351b`
- `ntdll!RtlLeaveCriticalSection` at `0x1800736a9`
- `ntdll!RtlLeaveCriticalSection` at `0x1800736e3`
- `ntdll!RtlEnterCriticalSection` at `0x1800734bd`
- `ntdll!RtlEnterCriticalSection` at `0x1800734bd`
- `ntdll!RtlGetNtProductType` at `0x180073342`
- `ntdll!RtlGetNtProductType` at `0x180073342`
- `netutils!NetApiBufferFree` at `0x18007380c`
- `netutils!NetApiBufferFree` at `0x18007380c`
- `srvcli!NetShareDel` at `0x18007343b`
- `srvcli!NetShareDel` at `0x1800737ae`
- `srvcli!NetShareDel` at `0x18007343b`
- `srvcli!NetShareDel` at `0x1800737ae`

## string_xrefs

- `0x1800733d7`: `NlCreateShare %lu\n`
- `0x18007374e`: `NlCreateShare %lu\n`
- `0x18007349e`: `NlCreateSysvolShares: Cannot find primary domain.\n`
- `0x18007366d`: `NlCreateSysvolShares: Failed to rename junction: %ws %ws 0x%lx\n`
- `0x1800736c9`: `Renamed SysVol junction from %ws to %ws\n`

## pseudocode

```c
__int64 NlCreateSysvolShares(void)
{
  int v0; // r13d
  __int64 v1; // r9
  unsigned int v2; // edi
  enum _NT_PRODUCT_TYPE v3; // eax
  WCHAR *v4; // r14
  unsigned __int16 *v5; // r15
  WCHAR *v6; // r12
  DWORD Share; // eax
  __int64 v8; // r9
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
  DWORD v26; // eax
  DWORD v27; // eax
  unsigned __int16 **v29; // [rsp+20h] [rbp-48h]
  unsigned __int16 *v30; // [rsp+48h] [rbp-20h] BYREF
  unsigned __int16 *v31[2]; // [rsp+50h] [rbp-18h] BYREF
  unsigned __int16 v32; // [rsp+B0h] [rbp+48h]
  DWORD v33; // [rsp+B8h] [rbp+50h] BYREF
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+C0h] [rbp+58h] BYREF
  int v35; // [rsp+C8h] [rbp+60h]

  v33 = 0;
  v0 = 0;
  ProductType = 0;
  v35 = 0;
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
    v35 = 1;
  }
  v4 = 0;
  v5 = 0;
  v6 = 0;
  if ( !dword_1800F824C || v0 )
  {
    v9 = NetShareDel(0, (LPWSTR)L"SYSVOL", 0);
    v33 = v9;
    if ( v9 && v9 != 2310 )
      NlPrintRoutine(0x100u, L"NetShareDel SYSVOL failed %lu\n", v9);
  }
  else
  {
    Share = NlCreateShare(Src, L"SYSVOL", 1, v1, dword_1800F8270);
    v33 = Share;
    if ( Share )
    {
      NlPrintRoutine(0x100u, L"NlCreateShare %lu\n", Share);
      v31[0] = Src;
      v31[1] = (unsigned __int16 *)v33;
      NlpWriteEventlog(0x164Au, 1u, 0x40000000u, v31, 2u, (unsigned __int8 *)&v33, 4u);
    }
  }
  v10 = (unsigned __int16 *)qword_1800F81E8;
  if ( qword_1800F81E8 || !Src || v0 )
  {
    v25 = 0;
LABEL_39:
    if ( !dword_1800F824C && v25 || v0 )
    {
      v27 = NetShareDel(0, (LPWSTR)L"NETLOGON", 0);
      v33 = v27;
      if ( v27 && v27 != 2310 )
        NlPrintRoutine(0x100u, L"NetShareDel NETLOGON failed %lu\n", v27);
    }
    else if ( v10 )
    {
      v26 = NlCreateShare(v10, L"NETLOGON", 0, v8, dword_1800F8274);
      v33 = v26;
      if ( v26 )
      {
        *(_OWORD *)v31 = 0;
        NlPrintRoutine(0x100u, L"NlCreateShare %lu\n", v26);
        v31[1] = (unsigned __int16 *)v33;
        v31[0] = v10;
        NlpWriteEventlog(0x164Au, 1u, 0x40000000u, v31, 2u, (unsigned __int8 *)&v33, 4u);
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
  v31[0] = (WCHAR *)((char *)v4 + v15 + 2);
  memcpy_0(v31[0], v17, v18);
  v32 = *((_WORD *)NetbiosDomain + 64);
  v19 = (const char *)*((_QWORD *)NetbiosDomain + 20);
  if ( !v19 || (unsigned int)NlEqualDnsNameUtf8(*((const char **)NetbiosDomain + 19), v19) )
  {
LABEL_34:
    v24 = v31[0];
    v0 = v35;
    *(_OWORD *)((char *)v31[0] + v32 - 2) = *(_OWORD *)L"\\SCRIPTS";
    *(unsigned __int16 *)((char *)v24 + v32 + 14) = aScripts_0[8];
    goto LABEL_35;
  }
  v20 = (const CHAR *)*((_QWORD *)NetbiosDomain + 20);
  v30 = 0;
  if ( !NetpAllocWStrFromUtf8StrAsRequired(v20, 0xFFFFFFFF, 0, 0, &v30) )
  {
    v5 = v30;
    if ( v30 )
    {
      do
        ++v13;
      while ( v30[v13] );
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
          v33 = LastError;
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
0x18007331c  push    rbp
0x18007331e  push    rbx
0x18007331f  push    rsi
0x180073320  push    rdi
0x180073321  push    r12
0x180073323  push    r13
0x180073325  push    r14
0x180073327  push    r15
0x180073329  mov     rbp, rsp
0x18007332c  sub     rsp, 68h
0x180073330  xor     esi, esi
0x180073332  lea     rcx, [rbp+ProductType]; ProductType
0x180073336  mov     [rbp+arg_8], esi
0x180073339  mov     r13d, esi
0x18007333c  mov     [rbp+ProductType], esi
0x18007333f  mov     [rbp+arg_18], esi
0x180073342  call    cs:__imp_RtlGetNtProductType
0x180073349  nop     dword ptr [rax+rax+00h]
0x18007334e  lea     edi, [rsi+1]
0x180073351  test    al, al
0x180073353  jnz     short loc_18007335C
0x180073355  mov     eax, edi
0x180073357  mov     [rbp+ProductType], eax
0x18007335a  jmp     short loc_18007335F
0x18007335c  mov     eax, [rbp+ProductType]
0x18007335f  cmp     cs:?NlGlobalMemberWorkstation@@3HA, esi; int NlGlobalMemberWorkstation
0x180073365  jz      short loc_180073386
0x180073367  cmp     eax, 2
0x18007336a  jz      short loc_180073380
0x18007336c  call    cs:__imp_LsaISafeMode
0x180073373  nop     dword ptr [rax+rax+00h]
0x180073378  test    al, al
0x18007337a  jz      loc_180073818
0x180073380  mov     r13d, edi
0x180073383  mov     [rbp+arg_18], edi
0x180073386  cmp     cs:dword_1800F824C, esi
0x18007338c  mov     r14, rsi
0x18007338f  mov     r15, rsi
0x180073392  mov     r12, rsi
0x180073395  mov     ebx, 100h
0x18007339a  jz      loc_18007342F
0x1800733a0  test    r13d, r13d
0x1800733a3  jnz     loc_18007342F
0x1800733a9  mov     eax, cs:dword_1800F8270
0x1800733af  lea     rdx, netname; "SYSVOL"
0x1800733b6  mov     rcx, cs:Src; unsigned __int16 *
0x1800733bd  mov     r8b, dil; unsigned __int8
0x1800733c0  mov     dword ptr [rsp+68h+var_48], eax; int
0x1800733c4  call    ?NlCreateShare@@YAKPEAG0EHHK@Z; NlCreateShare(ushort *,ushort *,uchar,int,int,ulong)
0x1800733c9  mov     [rbp+arg_8], eax
0x1800733cc  test    eax, eax
0x1800733ce  jz      loc_180073466
0x1800733d4  xorps   xmm0, xmm0
0x1800733d7  lea     rdx, aNlcreateshareL; "NlCreateShare %lu\n"
0x1800733de  mov     r8d, eax
0x1800733e1  mov     ecx, ebx; unsigned int
0x1800733e3  movups  xmmword ptr [rbp+var_18], xmm0
0x1800733e7  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800733ec  mov     rax, cs:Src
0x1800733f3  lea     r9, [rbp+var_18]; unsigned __int16 **
0x1800733f7  mov     [rbp+var_18], rax
0x1800733fb  mov     r8d, 40000000h; unsigned int
0x180073401  mov     eax, [rbp+arg_8]
0x180073404  mov     edx, edi; unsigned int
0x180073406  mov     [rbp+var_18+8], rax
0x18007340a  mov     ecx, 164Ah; unsigned int
0x18007340f  lea     rax, [rbp+arg_8]
0x180073413  mov     [rsp+68h+var_38], 4; unsigned int
0x18007341b  mov     [rsp+68h+var_40], rax; unsigned __int8 *
0x180073420  mov     dword ptr [rsp+68h+var_48], 2; unsigned int
0x180073428  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x18007342d  jmp     short loc_180073466
0x18007342f  xor     r8d, r8d; reserved
0x180073432  lea     rdx, netname; "SYSVOL"
0x180073439  xor     ecx, ecx; servername
0x18007343b  call    cs:__imp_NetShareDel
0x180073442  nop     dword ptr [rax+rax+00h]
0x180073447  mov     [rbp+arg_8], eax
0x18007344a  test    eax, eax
0x18007344c  jz      short loc_180073466
0x18007344e  cmp     eax, 906h
0x180073453  jz      short loc_180073466
0x180073455  mov     r8d, eax
0x180073458  lea     rdx, aNetsharedelSys; "NetShareDel SYSVOL failed %lu\n"
0x18007345f  mov     ecx, ebx; unsigned int
0x180073461  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180073466  mov     rbx, cs:qword_1800F81E8
0x18007346d  test    rbx, rbx
0x180073470  jnz     loc_180073700
0x180073476  cmp     cs:Src, rsi
0x18007347d  jz      loc_180073700
0x180073483  test    r13d, r13d
0x180073486  jnz     loc_180073700
0x18007348c  mov     dl, dil; unsigned __int8
0x18007348f  xor     ecx, ecx; SourceString
0x180073491  call    ?NlFindNetbiosDomain@@YAPEAU_DOMAIN_INFO@@PEBGE@Z; NlFindNetbiosDomain(ushort const *,uchar)
0x180073496  mov     rsi, rax
0x180073499  test    rax, rax
0x18007349c  jnz     short loc_1800734B6
0x18007349e  lea     rdx, aNlcreatesysvol; "NlCreateSysvolShares: Cannot find prima"...
0x1800734a5  mov     ecx, 100h; unsigned int
0x1800734aa  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800734af  mov     edi, ebx
0x1800734b1  jmp     loc_180073818
0x1800734b6  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800734bd  call    cs:__imp_RtlEnterCriticalSection
0x1800734c4  nop     dword ptr [rax+rax+00h]
0x1800734c9  movzx   ecx, word ptr [rsi+80h]
0x1800734d0  test    cx, cx
0x1800734d3  jz      loc_1800736A2
0x1800734d9  mov     rdx, cs:Src
0x1800734e0  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800734e4  mov     rax, r13
0x1800734e7  inc     rax
0x1800734ea  cmp     [rdx+rax*2], bx
0x1800734ee  jnz     short loc_1800734E7
0x1800734f0  lea     ebx, [rax+rax]
0x1800734f3  lea     edx, [rcx+14h]
0x1800734f6  mov     [rbp+var_28], ebx
0x1800734f9  add     edx, ebx; uBytes
0x1800734fb  mov     ecx, 40h ; '@'; uFlags
0x180073500  call    cs:__imp_LocalAlloc
0x180073507  nop     dword ptr [rax+rax+00h]
0x18007350c  mov     r14, rax
0x18007350f  test    rax, rax
0x180073512  jnz     short loc_180073536
0x180073514  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18007351b  call    cs:__imp_RtlLeaveCriticalSection
0x180073522  nop     dword ptr [rax+rax+00h]
0x180073527  mov     rcx, rsi; struct _DOMAIN_INFO *
0x18007352a  call    ?NlDereferenceDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDereferenceDomain(_DOMAIN_INFO *)
0x18007352f  xor     edi, edi
0x180073531  jmp     loc_180073818
0x180073536  mov     rdx, cs:Src; Src
0x18007353d  mov     r8, rbx; Size
0x180073540  mov     rcx, r14; void *
0x180073543  call    memcpy_0
0x180073548  mov     word ptr [rbx+r14], 5Ch ; '\'
0x18007354f  lea     rax, [r14+2]
0x180073553  movzx   r8d, word ptr [rsi+80h]
0x18007355b  add     rax, rbx
0x18007355e  mov     rdx, [rsi+88h]; Src
0x180073565  mov     rcx, rax; void *
0x180073568  sub     r8, 2; Size
0x18007356c  mov     [rbp+var_18], rax
0x180073570  call    memcpy_0
0x180073575  movzx   edx, word ptr [rsi+80h]
0x18007357c  xor     ebx, ebx
0x18007357e  mov     [rbp+arg_0], dx
0x180073582  mov     rdx, [rsi+0A0h]; char *
0x180073589  test    rdx, rdx
0x18007358c  jz      loc_18007367E
0x180073592  mov     rcx, [rsi+98h]; char *
0x180073599  call    ?NlEqualDnsNameUtf8@@YAHPEBD0@Z; NlEqualDnsNameUtf8(char const *,char const *)
0x18007359e  test    eax, eax
0x1800735a0  jnz     loc_18007367E
0x1800735a6  mov     rcx, [rsi+0A0h]; lpMultiByteStr
0x1800735ad  lea     rax, [rbp+var_20]
0x1800735b1  xor     r9d, r9d; unsigned __int16 *
0x1800735b4  mov     [rsp+68h+var_48], rax; unsigned __int16 **
0x1800735b9  xor     r8d, r8d; unsigned int
0x1800735bc  mov     [rbp+var_20], rbx
0x1800735c0  or      edx, 0FFFFFFFFh; cbMultiByte
0x1800735c3  call    ?NetpAllocWStrFromUtf8StrAsRequired@@YAKPEADKKPEAGPEAPEAG@Z; NetpAllocWStrFromUtf8StrAsRequired(char *,ulong,ulong,ushort *,ushort * *)
0x1800735c8  test    eax, eax
0x1800735ca  jnz     loc_1800736DC
0x1800735d0  mov     r15, [rbp+var_20]
0x1800735d4  test    r15, r15
0x1800735d7  jz      loc_1800736DC
0x1800735dd  inc     r13
0x1800735e0  cmp     [r15+r13*2], bx
0x1800735e5  jnz     short loc_1800735DD
0x1800735e7  mov     eax, [rbp+var_28]
0x1800735ea  mov     ecx, 40h ; '@'; uFlags
0x1800735ef  lea     eax, [rax+r13*2]
0x1800735f3  add     eax, 4
0x1800735f6  mov     edx, eax; uBytes
0x1800735f8  mov     ebx, eax
0x1800735fa  call    cs:__imp_LocalAlloc
0x180073601  nop     dword ptr [rax+rax+00h]
0x180073606  mov     r12, rax
0x180073609  test    rax, rax
0x18007360c  jz      loc_1800736DC
0x180073612  mov     r9, cs:Src
0x180073619  lea     r8, aWsWs_1; "%ws\\%ws"
0x180073620  shr     rbx, 1
0x180073623  mov     rcx, rax; Buffer
0x180073626  mov     rdx, rbx; BufferCount
0x180073629  mov     [rsp+68h+var_48], r15
0x18007362e  call    swprintf_s
0x180073633  mov     r8d, 2; dwFlags
0x180073639  mov     rdx, r14; lpNewFileName
0x18007363c  mov     rcx, r12; lpExistingFileName
0x18007363f  call    cs:__imp_MoveFileExW
0x180073646  nop     dword ptr [rax+rax+00h]
0x18007364b  test    eax, eax
0x18007364d  jnz     short loc_1800736C6
0x18007364f  call    cs:__imp_GetLastError
0x180073656  nop     dword ptr [rax+rax+00h]
0x18007365b  mov     [rbp+arg_8], eax
0x18007365e  cmp     eax, 2
0x180073661  jz      short loc_18007367E
0x180073663  mov     r9, r14
0x180073666  mov     dword ptr [rsp+68h+var_48], eax
0x18007366a  mov     r8, r12
0x18007366d  lea     rdx, aNlcreatesysvol_0; "NlCreateSysvolShares: Failed to rename "...
0x180073674  mov     ecx, 100h; unsigned int
0x180073679  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007367e  movzx   ecx, [rbp+arg_0]
0x180073682  mov     rdx, [rbp+var_18]
0x180073686  movups  xmm0, xmmword ptr cs:aScripts_0; "\\SCRIPTS"
0x18007368d  mov     r13d, [rbp+arg_18]
0x180073691  movups  xmmword ptr [rcx+rdx-2], xmm0
0x180073696  movzx   eax, word ptr cs:aScripts_0+10h; ""
0x18007369d  mov     [rcx+rdx+0Eh], ax
0x1800736a2  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800736a9  call    cs:__imp_RtlLeaveCriticalSection
0x1800736b0  nop     dword ptr [rax+rax+00h]
0x1800736b5  mov     rcx, rsi; struct _DOMAIN_INFO *
0x1800736b8  call    ?NlDereferenceDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDereferenceDomain(_DOMAIN_INFO *)
0x1800736bd  mov     eax, edi
0x1800736bf  xor     esi, esi
0x1800736c1  mov     rbx, r14
0x1800736c4  jmp     short loc_180073702
0x1800736c6  mov     r9, r14
0x1800736c9  lea     rdx, aRenamedSysvolJ; "Renamed SysVol junction from %ws to %ws"...
0x1800736d0  mov     r8, r12
0x1800736d3  mov     ecx, edi; unsigned int
0x1800736d5  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800736da  jmp     short loc_18007367E
0x1800736dc  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800736e3  call    cs:__imp_RtlLeaveCriticalSection
0x1800736ea  nop     dword ptr [rax+rax+00h]
0x1800736ef  mov     rcx, rsi; struct _DOMAIN_INFO *
0x1800736f2  call    ?NlDereferenceDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDereferenceDomain(_DOMAIN_INFO *)
0x1800736f7  xor     esi, esi
0x1800736f9  mov     edi, esi
0x1800736fb  jmp     loc_1800737E1
0x180073700  mov     eax, esi
0x180073702  cmp     cs:dword_1800F824C, esi
0x180073708  jnz     short loc_180073712
0x18007370a  test    eax, eax
0x18007370c  jnz     loc_1800737A2
0x180073712  test    r13d, r13d
0x180073715  jnz     loc_1800737A2
0x18007371b  test    rbx, rbx
0x18007371e  jz      loc_1800737DC
0x180073724  mov     eax, cs:dword_1800F8274
0x18007372a  lea     rdx, aNetlogon_0; "NETLOGON"
0x180073731  xor     r8d, r8d; unsigned __int8
0x180073734  mov     dword ptr [rsp+68h+var_48], eax; int
0x180073738  mov     rcx, rbx; unsigned __int16 *
0x18007373b  call    ?NlCreateShare@@YAKPEAG0EHHK@Z; NlCreateShare(ushort *,ushort *,uchar,int,int,ulong)
0x180073740  mov     [rbp+arg_8], eax
0x180073743  test    eax, eax
0x180073745  jz      loc_1800737DC
0x18007374b  xorps   xmm0, xmm0
0x18007374e  lea     rdx, aNlcreateshareL; "NlCreateShare %lu\n"
0x180073755  mov     r8d, eax
0x180073758  mov     ecx, 100h; unsigned int
0x18007375d  movups  xmmword ptr [rbp+var_18], xmm0
0x180073761  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180073766  mov     eax, [rbp+arg_8]
0x180073769  lea     r9, [rbp+var_18]; unsigned __int16 **
0x18007376d  mov     [rbp+var_18+8], rax
0x180073771  mov     r8d, 40000000h; unsigned int
0x180073777  lea     rax, [rbp+arg_8]
0x18007377b  mov     [rsp+68h+var_38], 4; unsigned int
0x180073783  mov     [rsp+68h+var_40], rax; unsigned __int8 *
0x180073788  mov     edx, edi; unsigned int
0x18007378a  mov     ecx, 164Ah; unsigned int
0x18007378f  mov     dword ptr [rsp+68h+var_48], 2; unsigned int
0x180073797  mov     [rbp+var_18], rbx
0x18007379b  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x1800737a0  jmp     short loc_1800737DC
0x1800737a2  xor     r8d, r8d; reserved
0x1800737a5  lea     rdx, aNetlogon_0; "NETLOGON"
0x1800737ac  xor     ecx, ecx; servername
0x1800737ae  call    cs:__imp_NetShareDel
0x1800737b5  nop     dword ptr [rax+rax+00h]
0x1800737ba  mov     [rbp+arg_8], eax
0x1800737bd  test    eax, eax
0x1800737bf  jz      short loc_1800737DC
0x1800737c1  cmp     eax, 906h
0x1800737c6  jz      short loc_1800737DC
0x1800737c8  mov     r8d, eax
0x1800737cb  lea     rdx, aNetsharedelNet; "NetShareDel NETLOGON failed %lu\n"
0x1800737d2  mov     ecx, 100h; unsigned int
0x1800737d7  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800737dc  test    r14, r14
0x1800737df  jz      short loc_1800737F0
0x1800737e1  mov     rcx, r14; hMem
0x1800737e4  call    cs:__imp_LocalFree
0x1800737eb  nop     dword ptr [rax+rax+00h]
0x1800737f0  test    r12, r12
0x1800737f3  jz      short loc_180073804
0x1800737f5  mov     rcx, r12; hMem
0x1800737f8  call    cs:__imp_LocalFree
0x1800737ff  nop     dword ptr [rax+rax+00h]
0x180073804  test    r15, r15
  ... truncated ...
```
