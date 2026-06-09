# SaBlob_Query

- ea: `0x180016120`
- end: `0x1800164f6`
- name: `SaBlob_Query`
- size: `982`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015970`
- `0x18001ea64`
- `0x18002aa78`

## callees

- `0x180004410`
- `0x180015310`
- `0x180016120`
- `0x1800205d8`
- `0x1800222f0`
- `0x180029a14`
- `0x18002a98c`
- `0x180038a20`
- `0x180039ea8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016367`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016367`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800164aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800164c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800164aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800164c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800162e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800162e3`
- `DNSAPI!DnsQueryConfigAllocEx` at `0x1800163cb`
- `DNSAPI!DnsQueryConfigAllocEx` at `0x1800163cb`
- `DNSAPI!DnsFree` at `0x18001644e`
- `DNSAPI!DnsFree` at `0x18001644e`
- `DNSAPI!DnsApiFree` at `0x180016423`
- `DNSAPI!DnsApiFree` at `0x180016435`
- `DNSAPI!DnsApiFree` at `0x180016423`
- `DNSAPI!DnsApiFree` at `0x180016435`
- `DNSAPI!DnsNameCompare_W` at `0x180016393`
- `DNSAPI!DnsNameCompare_W` at `0x1800163ad`
- `DNSAPI!DnsNameCompare_W` at `0x180016393`
- `DNSAPI!DnsNameCompare_W` at `0x1800163ad`
- `DNSAPI!DnsStringCopyAllocateEx` at `0x18001640c`
- `DNSAPI!DnsStringCopyAllocateEx` at `0x18001640c`
- `DNSAPI!Dns_FreeMsgBuf` at `0x180016307`
- `DNSAPI!Dns_FreeMsgBuf` at `0x180016307`
- `DNSAPI!DnsFreeCustomServers` at `0x180016476`
- `DNSAPI!DnsFreeCustomServers` at `0x180016476`
- `DNSAPI!DnsQueryEx` at `0x1800162aa`
- `DNSAPI!DnsQueryEx` at `0x1800162aa`

## pseudocode

```c
PCWSTR *__fastcall SaBlob_Query(
        const WCHAR *a1,
        unsigned __int16 a2,
        ULONG64 *a3,
        PVOID *a4,
        int a5,
        ULONG a6,
        HANDLE *a7,
        _DWORD *a8,
        _DWORD *a9,
        _QWORD *a10,
        unsigned int a11,
        __int64 a12,
        int a13)
{
  int v14; // eax
  __int64 v15; // rdx
  PCWSTR *v18; // rdi
  DWORD LastError; // ebx
  ULONG64 QueryOptions; // rax
  int v21; // edx
  char v22; // al
  PDNS_RECORD pQueryRecords; // r15
  PCWSTR *v24; // rax
  void *ConfigAlloc; // rsi
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v27; // rax
  const WCHAR *v28; // r14
  unsigned __int16 v30; // [rsp+30h] [rbp-D0h]
  _DNS_QUERY_REQUEST pQueryRequest; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v32; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v33[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct _DNS_QUERY_RESULT pQueryResults; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE hObject[2]; // [rsp+D0h] [rbp-30h]
  __int128 v36; // [rsp+E0h] [rbp-20h]
  __int128 v37; // [rsp+F0h] [rbp-10h]
  __int128 v38; // [rsp+100h] [rbp+0h]
  __int128 v39; // [rsp+110h] [rbp+10h]

  v14 = a2;
  v15 = a12;
  v30 = v14;
  v33[0] = 0;
  memset(&pQueryRequest, 0, sizeof(pQueryRequest));
  v32 = 0;
  memset(&pQueryResults, 0, sizeof(pQueryResults));
  *(_OWORD *)hObject = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  if ( a10 )
    *a10 = 0;
  if ( a8 )
  {
    *a9 = 0;
    *a8 = 0;
  }
  if ( a3 && a10 )
  {
    v18 = 0;
    if ( (xmmword_180063D60 & 2) != 0 )
    {
      WPP_SF_Sdi(v14, a12, 0, (_DWORD)a1, v14, *a3);
      LOWORD(v14) = v30;
      v15 = a12;
    }
    if ( a4 )
      *a3 |= 0x200uLL;
    pQueryRequest.QueryType = v14;
    pQueryRequest.QueryOptions = *a3;
    pQueryRequest.InterfaceIndex = a6;
    pQueryRequest.Version = 3;
    pQueryRequest.QueryName = a1;
    LastError = ConvertCustomServers(a11, v15, (char *)&v32 + 8, v33);
    if ( !LastError )
    {
      QueryOptions = pQueryRequest.QueryOptions;
      if ( !a13 )
        QueryOptions = pQueryRequest.QueryOptions | 0x200000000000000LL;
      pQueryResults.Version = -1;
      pQueryRequest.QueryOptions = QueryOptions | 0x800000000000000LL;
      LastError = DnsQueryEx(&pQueryRequest, &pQueryResults, 0);
      *a3 = pQueryResults.QueryOptions;
      if ( a4 )
        *a4 = pQueryResults.Reserved;
      if ( a7 )
      {
        *a7 = hObject[0];
      }
      else if ( hObject[0] )
      {
        CloseHandle(hObject[0]);
      }
      hObject[0] = 0;
      if ( LastError )
      {
        if ( a4 && *a4 )
        {
          Dns_FreeMsgBuf();
          *a4 = 0;
        }
        if ( LastError == 1722 )
          LastError = 11002;
      }
      else
      {
        v22 = BYTE8(v36);
        if ( (BYTE8(v36) & 1) != 0 )
          *a10 |= 1uLL;
        if ( (v22 & 2) != 0 )
          *a10 |= 2uLL;
        pQueryRecords = pQueryResults.pQueryRecords;
        v24 = (PCWSTR *)SaBlob_CreateFromRecords(pQueryResults.pQueryRecords, v21, v30, (_DWORD)a8, (__int64)a9);
        v18 = v24;
        if ( v24 )
        {
          if ( *v24 )
          {
            if ( DnsNameCompare_W(*v24, L"localhost") || DnsNameCompare_W(*v18, L"loopback") )
            {
              ConfigAlloc = (void *)DnsQueryConfigAllocEx(15, 0, 0);
              if ( ConfigAlloc )
              {
                if ( (Feature_5977_1413__private_featureState & 0x10) != 0 )
                  IsEnabledDeviceUsageNoInline = Feature_5977_1413__private_featureState & 1;
                else
                  IsEnabledDeviceUsageNoInline = Feature_5977_1413__private_IsEnabledDeviceUsageNoInline();
                if ( IsEnabledDeviceUsageNoInline )
                  v27 = SaBlob_StringCopyAllocW(ConfigAlloc);
                else
                  v27 = DnsStringCopyAllocateEx(ConfigAlloc, 0, 1);
                v28 = (const WCHAR *)v27;
                if ( v27 )
                {
                  DnsApiFree(*v18);
                  *v18 = v28;
                }
                DnsApiFree(ConfigAlloc);
              }
            }
          }
          else
          {
            LastError = 9501;
          }
        }
        else
        {
          LastError = GetLastError();
        }
        if ( pQueryRecords )
          DnsFree(pQueryRecords, DnsFreeRecordList);
        if ( LastError && v18 )
        {
          SaBlob_Free(v18);
          v18 = 0;
        }
      }
    }
    DnsFreeCustomServers((char *)&v32 + 8, v33);
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_qD(1025, 23, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids, v18, LastError);
    SetLastError(LastError);
    return v18;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x180016120  push    rbp
0x180016122  push    rbx
0x180016123  push    rsi
0x180016124  push    r12
0x180016126  push    r13
0x180016128  push    r14
0x18001612a  push    r15
0x18001612c  lea     rbp, [rsp-40h]
0x180016131  sub     rsp, 140h
0x180016138  mov     rax, cs:__security_cookie
0x18001613f  xor     rax, rsp
0x180016142  mov     [rbp+70h+var_50], rax
0x180016146  mov     rsi, [rbp+70h+arg_48]
0x18001614d  xorps   xmm1, xmm1
0x180016150  mov     r13, [rbp+70h+arg_30]
0x180016157  xorps   xmm0, xmm0
0x18001615a  mov     r12, [rbp+70h+arg_38]
0x180016161  mov     r15, r8
0x180016164  xor     r8d, r8d
0x180016167  movzx   eax, dx
0x18001616a  mov     rdx, [rbp+70h+arg_58]
0x180016171  mov     rbx, rcx
0x180016174  mov     rcx, [rbp+70h+arg_40]
0x18001617b  mov     r14, r9
0x18001617e  mov     [rsp+170h+var_140], ax
0x180016183  mov     [rsp+170h+var_130], rcx
0x180016188  mov     [rsp+170h+var_138], rdx
0x18001618d  mov     [rbp+70h+var_D0], r8
0x180016191  movups  xmmword ptr [rsp+170h+pQueryRequest.Version], xmm0
0x180016196  movups  xmmword ptr [rsp+170h+pQueryRequest.QueryType], xmm0
0x18001619b  movups  xmmword ptr [rsp+170h+pQueryRequest.pDnsServerList], xmm0
0x1800161a0  movups  xmmword ptr [rbp+70h+pQueryRequest.pQueryCompletionCallback], xmm0
0x1800161a4  movups  [rbp+70h+var_E0], xmm0
0x1800161a8  movups  xmmword ptr [rbp+70h+pQueryResults.Version], xmm1
0x1800161ac  movups  xmmword ptr [rbp+70h+pQueryResults.pQueryRecords], xmm1
0x1800161b0  movups  xmmword ptr [rbp+70h+hObject], xmm1
0x1800161b4  movups  [rbp+70h+var_90], xmm1
0x1800161b8  movups  [rbp+70h+var_80], xmm1
0x1800161bc  movups  [rbp+70h+var_70], xmm1
0x1800161c0  movups  [rbp+70h+var_60], xmm1
0x1800161c4  test    rsi, rsi
0x1800161c7  jz      short loc_1800161CC
0x1800161c9  mov     [rsi], r8
0x1800161cc  test    r12, r12
0x1800161cf  jz      short loc_1800161D8
0x1800161d1  mov     [rcx], r8d
0x1800161d4  mov     [r12], r8d
0x1800161d8  test    r15, r15
0x1800161db  jz      loc_1800164C3
0x1800161e1  test    rsi, rsi
0x1800161e4  jz      loc_1800164C3
0x1800161ea  mov     [rsp+170h+var_38], rdi
0x1800161f2  test    byte ptr cs:xmmword_180063D60, 2
0x1800161f9  mov     rdi, r8
0x1800161fc  jz      short loc_18001621E
0x1800161fe  mov     ecx, eax
0x180016200  mov     r9, rbx
0x180016203  mov     rax, [r15]
0x180016206  mov     [rsp+170h+var_148], rax
0x18001620b  mov     dword ptr [rsp+170h+var_150], ecx
0x18001620f  call    WPP_SF_Sdi
0x180016214  movzx   eax, [rsp+170h+var_140]
0x180016219  mov     rdx, [rsp+170h+var_138]
0x18001621e  test    r14, r14
0x180016221  jz      short loc_18001622A
0x180016223  or      qword ptr [r15], 200h
0x18001622a  mov     ecx, [rbp+70h+arg_50]
0x180016230  lea     r9, [rbp+70h+var_D0]
0x180016234  mov     [rsp+170h+pQueryRequest.QueryType], ax
0x180016239  lea     r8, [rbp+70h+var_E0+8]
0x18001623d  mov     rax, [r15]
0x180016240  mov     [rsp+170h+pQueryRequest.QueryOptions], rax
0x180016245  mov     eax, [rbp+70h+arg_28]
0x18001624b  mov     [rsp+170h+pQueryRequest.InterfaceIndex], eax
0x18001624f  mov     [rsp+170h+pQueryRequest.Version], 3
0x180016257  mov     [rsp+170h+pQueryRequest.QueryName], rbx
0x18001625c  call    ConvertCustomServers
0x180016261  mov     ebx, eax
0x180016263  test    eax, eax
0x180016265  jnz     loc_18001646E
0x18001626b  mov     rax, [rsp+170h+pQueryRequest.QueryOptions]
0x180016270  cmp     [rbp+70h+arg_60], edi
0x180016276  jnz     short loc_180016285
0x180016278  mov     rcx, 200000000000000h
0x180016282  or      rax, rcx
0x180016285  mov     rcx, 800000000000000h
0x18001628f  mov     [rbp+70h+pQueryResults.Version], 0FFFFFFFFh
0x180016296  or      rax, rcx
0x180016299  lea     rdx, [rbp+70h+pQueryResults]; pQueryResults
0x18001629d  lea     rcx, [rsp+170h+pQueryRequest]; pQueryRequest
0x1800162a2  mov     [rsp+170h+pQueryRequest.QueryOptions], rax
0x1800162a7  xor     r8d, r8d; pCancelHandle
0x1800162aa  call    cs:__imp_DnsQueryEx
0x1800162b1  nop     dword ptr [rax+rax+00h]
0x1800162b6  mov     ebx, eax
0x1800162b8  mov     rax, [rbp+70h+pQueryResults.QueryOptions]
0x1800162bc  mov     [r15], rax
0x1800162bf  test    r14, r14
0x1800162c2  jz      short loc_1800162CB
0x1800162c4  mov     rax, [rbp+70h+pQueryResults.Reserved]
0x1800162c8  mov     [r14], rax
0x1800162cb  test    r13, r13
0x1800162ce  jz      short loc_1800162DA
0x1800162d0  mov     rax, [rbp+70h+hObject]
0x1800162d4  mov     [r13+0], rax
0x1800162d8  jmp     short loc_1800162EF
0x1800162da  mov     rcx, [rbp+70h+hObject]; hObject
0x1800162de  test    rcx, rcx
0x1800162e1  jz      short loc_1800162EF
0x1800162e3  call    cs:__imp_CloseHandle
0x1800162ea  nop     dword ptr [rax+rax+00h]
0x1800162ef  xor     r13d, r13d
0x1800162f2  mov     [rbp+70h+hObject], r13
0x1800162f6  test    ebx, ebx
0x1800162f8  jz      short loc_18001632C
0x1800162fa  test    r14, r14
0x1800162fd  jz      short loc_180016316
0x1800162ff  mov     rcx, [r14]
0x180016302  test    rcx, rcx
0x180016305  jz      short loc_180016316
0x180016307  call    cs:__imp_Dns_FreeMsgBuf
0x18001630e  nop     dword ptr [rax+rax+00h]
0x180016313  mov     [r14], r13
0x180016316  cmp     ebx, 6BAh
0x18001631c  jnz     loc_18001646E
0x180016322  mov     ebx, 2AFAh
0x180016327  jmp     loc_18001646E
0x18001632c  movzx   eax, byte ptr [rbp+70h+var_90+8]
0x180016330  test    al, 1
0x180016332  jz      short loc_180016338
0x180016334  or      qword ptr [rsi], 1
0x180016338  test    al, 2
0x18001633a  jz      short loc_180016340
0x18001633c  or      qword ptr [rsi], 2
0x180016340  mov     r15, [rbp+70h+pQueryResults.pQueryRecords]
0x180016344  mov     r9, r12
0x180016347  mov     rax, [rsp+170h+var_130]
0x18001634c  mov     rcx, r15
0x18001634f  movzx   r8d, [rsp+170h+var_140]
0x180016355  mov     [rsp+170h+var_150], rax
0x18001635a  call    SaBlob_CreateFromRecords
0x18001635f  mov     rdi, rax
0x180016362  test    rax, rax
0x180016365  jnz     short loc_18001637A
0x180016367  call    cs:__imp_GetLastError
0x18001636e  nop     dword ptr [rax+rax+00h]
0x180016373  mov     ebx, eax
0x180016375  jmp     loc_180016441
0x18001637a  mov     rcx, [rax]; pName1
0x18001637d  test    rcx, rcx
0x180016380  jnz     short loc_18001638C
0x180016382  mov     ebx, 251Dh
0x180016387  jmp     loc_180016441
0x18001638c  lea     rdx, String2; "localhost"
0x180016393  call    cs:__imp_DnsNameCompare_W
0x18001639a  nop     dword ptr [rax+rax+00h]
0x18001639f  test    eax, eax
0x1800163a1  jnz     short loc_1800163C1
0x1800163a3  mov     rcx, [rdi]; pName1
0x1800163a6  lea     rdx, aLoopback; "loopback"
0x1800163ad  call    cs:__imp_DnsNameCompare_W
0x1800163b4  nop     dword ptr [rax+rax+00h]
0x1800163b9  test    eax, eax
0x1800163bb  jz      loc_180016441
0x1800163c1  xor     r8d, r8d
0x1800163c4  xor     edx, edx
0x1800163c6  mov     ecx, 0Fh
0x1800163cb  call    cs:__imp_DnsQueryConfigAllocEx
0x1800163d2  nop     dword ptr [rax+rax+00h]
0x1800163d7  mov     rsi, rax
0x1800163da  test    rax, rax
0x1800163dd  jz      short loc_180016441
0x1800163df  mov     eax, cs:Feature_5977_1413__private_featureState
0x1800163e5  test    al, 10h
0x1800163e7  jz      short loc_1800163EE
0x1800163e9  and     eax, 1
0x1800163ec  jmp     short loc_1800163F3
0x1800163ee  call    Feature_5977_1413__private_IsEnabledDeviceUsageNoInline
0x1800163f3  mov     rcx, rsi; Src
0x1800163f6  test    eax, eax
0x1800163f8  jz      short loc_180016401
0x1800163fa  call    SaBlob_StringCopyAllocW
0x1800163ff  jmp     short loc_180016418
0x180016401  mov     r9d, 1
0x180016407  xor     edx, edx
0x180016409  mov     r8d, r9d
0x18001640c  call    cs:__imp_DnsStringCopyAllocateEx
0x180016413  nop     dword ptr [rax+rax+00h]
0x180016418  mov     r14, rax
0x18001641b  test    rax, rax
0x18001641e  jz      short loc_180016432
0x180016420  mov     rcx, [rdi]
0x180016423  call    cs:__imp_DnsApiFree
0x18001642a  nop     dword ptr [rax+rax+00h]
0x18001642f  mov     [rdi], r14
0x180016432  mov     rcx, rsi
0x180016435  call    cs:__imp_DnsApiFree
0x18001643c  nop     dword ptr [rax+rax+00h]
0x180016441  test    r15, r15
0x180016444  jz      short loc_18001645A
0x180016446  mov     edx, 1; FreeType
0x18001644b  mov     rcx, r15; pData
0x18001644e  call    cs:__imp_DnsFree
0x180016455  nop     dword ptr [rax+rax+00h]
0x18001645a  test    ebx, ebx
0x18001645c  jz      short loc_18001646E
0x18001645e  test    rdi, rdi
0x180016461  jz      short loc_18001646E
0x180016463  mov     rcx, rdi
0x180016466  call    SaBlob_Free
0x18001646b  mov     rdi, r13
0x18001646e  lea     rdx, [rbp+70h+var_D0]
0x180016472  lea     rcx, [rbp+70h+var_E0+8]
0x180016476  call    cs:__imp_DnsFreeCustomServers
0x18001647d  nop     dword ptr [rax+rax+00h]
0x180016482  test    byte ptr cs:xmmword_180063D60, 2
0x180016489  jz      short loc_1800164A8
0x18001648b  mov     edx, 17h
0x180016490  mov     dword ptr [rsp+170h+var_150], ebx
0x180016494  mov     ecx, 401h
0x180016499  lea     r8, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids
0x1800164a0  mov     r9, rdi
0x1800164a3  call    WPP_SF_qD
0x1800164a8  mov     ecx, ebx; dwErrCode
0x1800164aa  call    cs:__imp_SetLastError
0x1800164b1  nop     dword ptr [rax+rax+00h]
0x1800164b6  mov     rax, rdi
0x1800164b9  mov     rdi, [rsp+170h+var_38]
0x1800164c1  jmp     short loc_1800164D6
0x1800164c3  mov     ecx, 57h ; 'W'; dwErrCode
0x1800164c8  call    cs:__imp_SetLastError
0x1800164cf  nop     dword ptr [rax+rax+00h]
0x1800164d4  xor     eax, eax
0x1800164d6  mov     rcx, [rbp+70h+var_50]
0x1800164da  xor     rcx, rsp; StackCookie
0x1800164dd  call    __security_check_cookie
0x1800164e2  add     rsp, 140h
0x1800164e9  pop     r15
0x1800164eb  pop     r14
0x1800164ed  pop     r13
0x1800164ef  pop     r12
0x1800164f1  pop     rsi
0x1800164f2  pop     rbx
0x1800164f3  pop     rbp
0x1800164f4  retn
```
