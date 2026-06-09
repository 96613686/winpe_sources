# I_NetLogonLdapLookupEx

- ea: `0x18003ffd0`
- end: `0x1800406d8`
- name: `I_NetLogonLdapLookupEx`
- size: `1800`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007518`
- `0x18000d444`
- `0x18000d854`
- `0x18000e910`
- `0x18000f3e4`
- `0x18003feac`
- `0x18003fef4`
- `0x18003ff80`
- `0x18003ffd0`
- `0x180041944`
- `0x180074294`
- `0x180088fe8`
- `0x180090204`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800400ad`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180040681`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800400ad`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180040681`
- `ntdll!RtlLengthSid` at `0x1800402fc`
- `ntdll!RtlLengthSid` at `0x1800402fc`
- `ntdll!RtlValidSid` at `0x1800402e4`
- `ntdll!RtlValidSid` at `0x1800402e4`
- `netutils!NetApiBufferFree` at `0x180040479`
- `netutils!NetApiBufferFree` at `0x180040611`
- `netutils!NetApiBufferFree` at `0x180040631`
- `netutils!NetApiBufferFree` at `0x180040651`
- `netutils!NetApiBufferFree` at `0x180040671`
- `netutils!NetApiBufferFree` at `0x180040479`
- `netutils!NetApiBufferFree` at `0x180040611`
- `netutils!NetApiBufferFree` at `0x180040631`
- `netutils!NetApiBufferFree` at `0x180040651`
- `netutils!NetApiBufferFree` at `0x180040671`
- `netutils!NetApiBufferAllocate` at `0x1800401a2`
- `netutils!NetApiBufferAllocate` at `0x1800401a2`

## string_xrefs

- `0x180040500`: `I_NetlogonLdapLookup: Bad ping from %ws: multiple UnicodeComputerName\n`
- `0x1800404e1`: `I_NetlogonLdapLookup: Bad UnicodeComputerName 0x%lx\n`
- `0x180040556`: `I_NetlogonLdapLookup: Bad UnicodeComputerName 0x%lx\n`
- `0x1800402b1`: `DomainSid`
- `0x180040538`: `I_NetlogonLdapLookup: Bad DomainSid 0x%lx %ld\n`

## pseudocode

```c
__int64 __fastcall I_NetLogonLdapLookupEx(unsigned __int16 *a1, struct sockaddr *a2, void **a3, unsigned int *a4)
{
  unsigned __int16 *v6; // rdi
  unsigned __int16 *v7; // r14
  unsigned int v8; // ebx
  unsigned __int16 *v9; // r15
  unsigned int v10; // esi
  struct sockaddr v12; // xmm0
  __int128 v13; // xmm1
  struct sockaddr v14; // xmm0
  unsigned int v15; // ebx
  __int64 *i; // rsi
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned __int8 v20; // al
  struct Filter *v21; // rcx
  unsigned int v22; // eax
  __int64 v23; // r9
  unsigned __int16 *v24; // rdx
  unsigned __int8 v25; // al
  struct Filter *v26; // rcx
  unsigned int v27; // ebx
  ULONG v28; // eax
  unsigned __int8 v29; // al
  struct Filter *v30; // rcx
  unsigned __int8 v31; // al
  struct Filter *v32; // rcx
  unsigned int v33; // eax
  unsigned __int16 *v34; // r8
  unsigned __int16 *v35; // rdx
  void **v36; // r13
  unsigned int v37; // [rsp+50h] [rbp-B0h]
  unsigned int v38; // [rsp+80h] [rbp-80h] BYREF
  LPVOID Buffer; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v40; // [rsp+90h] [rbp-70h] BYREF
  int v41; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned __int16 *v42; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v43; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v44; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v45; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int *v46; // [rsp+B8h] [rbp-48h]
  void **v47; // [rsp+C0h] [rbp-40h]
  void *v48; // [rsp+C8h] [rbp-38h]
  struct _GUID *Buf1; // [rsp+D0h] [rbp-30h]
  LARGE_INTEGER v50; // [rsp+D8h] [rbp-28h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+E0h] [rbp-20h] BYREF
  struct sockaddr v52; // [rsp+E8h] [rbp-18h] BYREF
  _OWORD v53[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v54; // [rsp+118h] [rbp+18h] BYREF
  _BYTE Sid[80]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v56[16]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v57[24]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v58[104]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int16 v59[256]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v47 = a3;
  v46 = a4;
  Buffer = 0;
  v6 = 0;
  v7 = 0;
  v43 = 0;
  v45 = 0;
  v54 = 0;
  memset_0(v59, 0, sizeof(v59));
  v8 = 2;
  v41 = 2;
  v44 = 0;
  v40 = 0;
  *v47 = 0;
  v9 = 0;
  v10 = 0;
  v53[0] = 0;
  v38 = 0;
  v52 = 0;
  *v46 = 0;
  *(_OWORD *)((char *)v53 + 12) = 0;
  PerformanceCount.QuadPart = 0;
  v50.QuadPart = 0;
  if ( !(unsigned int)NlStartNetlogonCall() )
    return 3221225485LL;
  Buf1 = 0;
  v48 = 0;
  _InterlockedAdd64((volatile signed __int64 *)&gDCPingGlobalPerfCounters, 1u);
  _InterlockedAdd64(&qword_1800F8D08, 1u);
  QueryPerformanceCounter(&PerformanceCount);
  if ( a2 )
  {
    if ( a2->sa_family == 2 )
    {
      v14 = *a2;
      a2 = &v52;
      v52 = v14;
      *(_WORD *)v52.sa_data = 0;
    }
    else if ( a2->sa_family == 23 )
    {
      v12 = *a2;
      v13 = *(_OWORD *)&a2->sa_data[10];
      a2 = (struct sockaddr *)v53;
      v53[0] = v12;
      WORD1(v53[0]) = 0;
      *(_OWORD *)((char *)v53 + 12) = v13;
    }
    else
    {
      NlPrintRoutine(
        0x100u,
        L"I_NetlogonLdapLookupEx: DS passed us a SOCKADDR that wasn't AF_INET or AF_INET6 (ignoring it)\n");
      a2 = 0;
    }
  }
  if ( a1 )
  {
    if ( *a1 != 1 )
    {
      NlPrintRoutine(0x100u, L"I_NetlogonLdapLookup: Filter doesn't have AND %ld\n", *a1);
      goto LABEL_12;
    }
    for ( i = (__int64 *)*((_QWORD *)a1 + 1); i; i = (__int64 *)*i )
    {
      if ( *((_WORD *)i + 4) != 4 )
      {
        NlPrintRoutine(0x100u, L"I_NetlogonLdapLookup: Filter doesn't have EqualityMatch %ld\n", *a1);
        goto LABEL_12;
      }
      if ( IsFilterName((struct Filter *)i + 1, "DnsDomain") )
      {
        v17 = *((_DWORD *)i + 8);
        if ( !v17 )
        {
          NlPrintRoutine(0x100u, L"I_NetlogonLdapLookup: Bad DnsDomainName\n");
          goto LABEL_12;
        }
        if ( Buffer )
        {
          v35 = L"I_NetlogonLdapLookup: Bad ping from %ws: multiple DnsDomainName\n";
LABEL_65:
          NlPrintRoutine(0x100u, v35, v6);
          goto LABEL_12;
        }
        if ( v17 + 1 < v17 )
        {
          v15 = -1073741675;
          goto LABEL_82;
        }
        if ( NetApiBufferAllocate(v17 + 1, &Buffer) )
        {
          v15 = -1073741801;
          goto LABEL_80;
        }
        memcpy_0(Buffer, (const void *)i[5], *((unsigned int *)i + 8));
        *((_BYTE *)Buffer + *((unsigned int *)i + 8)) = 0;
      }
      else if ( IsFilterName((struct Filter *)i + 1, "Host") )
      {
        if ( v6 )
        {
          v35 = L"I_NetlogonLdapLookup: Bad ping from %ws: multiple UnicodeComputerName\n";
          goto LABEL_65;
        }
        v18 = FilterString((struct Filter *)i + 1, 0x10u, v56, &v43);
        if ( v18 )
        {
          NlPrintRoutine(0x100u, L"I_NetlogonLdapLookup: Bad UnicodeComputerName 0x%lx\n", v18);
          v6 = v43;
          v15 = -1073741811;
          goto LABEL_80;
        }
        v6 = v43;
      }
      else if ( IsFilterName((struct Filter *)i + 1, "User") )
      {
        if ( v9 )
        {
          v35 = L"I_NetlogonLdapLookup: Bad ping from %ws: multiple UnicodeUserName\n";
          goto LABEL_65;
        }
        v19 = FilterString((struct Filter *)i + 1, 0x15u, v57, &v44);
        if ( v19 )
        {
          NlPrintRoutine(0x100u, L"I_NetlogonLdapLookup: Bad UnicodeUserName 0x%lx\n", v19);
          v9 = v44;
          v15 = -1073741811;
          goto LABEL_80;
        }
        v9 = v44;
      }
      else
      {
        v20 = IsFilterName((struct Filter *)i + 1, "AAC");
        v21 = (struct Filter *)(i + 1);
        if ( v20 )
        {
          v22 = FilterBinary(v21, 4u, &v40, &v38);
          v23 = v38;
          if ( v22 || v38 != 4 )
          {
            v24 = L"I_NetlogonLdapLookup: Bad AllowableAccountControl 0x%lx %lu\n";
LABEL_34:
            NlPrintRoutine(0x100u, v24, v22, v23);
            goto LABEL_12;
          }
        }
        else
        {
          v25 = IsFilterName(v21, "DomainSid");
          v26 = (struct Filter *)(i + 1);
          if ( v25 )
          {
            v27 = FilterBinary(v26, 0x48u, Sid, &v38);
            if ( v27 || !RtlValidSid(Sid) || (v28 = RtlLengthSid(Sid), v28 != v38) )
            {
              NlPrintRoutine(0x100u, L"I_NetlogonLdapLookup: Bad DomainSid 0x%lx %ld\n", v27, v38);
LABEL_12:
              v15 = -1073741811;
              goto LABEL_80;
            }
            v48 = Sid;
          }
          else
          {
            v29 = IsFilterName(v26, "DomainGuid");
            v30 = (struct Filter *)(i + 1);
            if ( v29 )
            {
              v22 = FilterBinary(v30, 0x10u, &v54, &v38);
              v23 = v38;
              if ( v22 || v38 != 16 )
              {
                v24 = L"I_NetlogonLdapLookup: Bad DomainGuid 0x%lx %ld\n";
                goto LABEL_34;
              }
              Buf1 = (struct _GUID *)&v54;
            }
            else
            {
              v31 = IsFilterName(v30, "NtVer");
              v32 = (struct Filter *)(i + 1);
              if ( v31 )
              {
                v22 = FilterBinary(v32, 4u, &v41, &v38);
                v23 = v38;
                if ( v22 || v38 != 4 )
                {
                  v24 = L"I_NetlogonLdapLookup: Bad NtVersionFlags 0x%lx %ld\n";
                  goto LABEL_34;
                }
              }
              else if ( IsFilterName(v32, "DnsHostName") )
              {
                if ( v7 )
                {
                  NlPrintRoutine(0x100u, L"I_NetlogonLdapLookup: Bad ping from %ws: multiple UnicodeDnsHostName\n", v7);
                  goto LABEL_12;
                }
                v33 = FilterString((struct Filter *)i + 1, 0x100u, v59, &v45);
                if ( v33 )
                {
                  NlPrintRoutine(0x100u, L"I_NetlogonLdapLookup: Bad UnicodeComputerName 0x%lx\n", v33);
                  v7 = v45;
                  v15 = -1073741811;
                  goto LABEL_80;
                }
                v7 = v45;
              }
              else if ( (NlGlobalParameters & 0x100) != 0 )
              {
                v42 = 0;
                memset_0(v58, 0, 0xC8u);
                if ( NetpAllocWStrFromUtf8StrAsRequired((LPCCH)i[3], *((_DWORD *)i + 4), 0x64u, v58, &v42) )
                {
                  NlPrintRoutine(0x100u, L"I_NetlogonLdapLookup: unrecognized filter parameter <unknown>.\n");
                }
                else
                {
                  v34 = v58;
                  if ( v42 )
                    v34 = v42;
                  NlPrintRoutine(0x100u, L"I_NetlogonLdapLookup: unrecognized filter parameter %ws\n", v34);
                  if ( v42 && v42 != v58 )
                    NetApiBufferFree(v42);
                }
              }
            }
          }
        }
      }
    }
    v10 = v40;
    v8 = v41;
  }
  v36 = v47;
  if ( NlGetLocalPingResponse(
         L"UDP LDAP",
         0,
         (const char *)Buffer,
         Buf1,
         v48,
         0,
         v6,
         v7,
         v9,
         v10,
         v37,
         v8,
         a2,
         v47,
         v46) )
  {
    goto LABEL_12;
  }
  NlpDumpBuffer(0x2000000u, *v36, *v46);
  v15 = 0;
LABEL_80:
  if ( Buffer )
    NetApiBufferFree(Buffer);
LABEL_82:
  if ( v6 && v6 != v56 )
    NetApiBufferFree(v6);
  if ( v7 && v7 != v59 )
    NetApiBufferFree(v7);
  if ( v9 )
  {
    if ( v9 != v57 )
      NetApiBufferFree(v9);
  }
  QueryPerformanceCounter(&v50);
  _InterlockedAdd64(&qword_1800F8D10, v50.QuadPart - PerformanceCount.QuadPart);
  _InterlockedIncrement64(&qword_1800F8D18);
  _InterlockedDecrement64((volatile signed __int64 *)&gDCPingGlobalPerfCounters);
  NlEndNetlogonCall();
  return v15;
}

```

## disassembly

```asm
0x18003ffd0  push    rbp
0x18003ffd2  push    rbx
0x18003ffd3  push    rsi
0x18003ffd4  push    rdi
0x18003ffd5  push    r12
0x18003ffd7  push    r13
0x18003ffd9  push    r14
0x18003ffdb  push    r15
0x18003ffdd  lea     rbp, [rsp-3B8h]
0x18003ffe5  sub     rsp, 4B8h
0x18003ffec  mov     rax, cs:__security_cookie
0x18003fff3  xor     rax, rsp
0x18003fff6  mov     [rbp+3F0h+var_50], rax
0x18003fffd  mov     [rbp+3F0h+var_430], r8
0x180040001  mov     r12, rdx
0x180040004  mov     r13, rcx
0x180040007  mov     [rbp+3F0h+var_438], r9
0x18004000b  xorps   xmm0, xmm0
0x18004000e  mov     [rbp+3F0h+Buffer], 0
0x180040016  xor     edi, edi
0x180040018  lea     rcx, [rbp+3F0h+var_250]; void *
0x18004001f  xor     r14d, r14d
0x180040022  mov     [rbp+3F0h+var_450], rdi
0x180040026  xor     edx, edx; Val
0x180040028  mov     [rbp+3F0h+var_440], r14
0x18004002c  mov     r8d, 200h; Size
0x180040032  movups  [rbp+3F0h+var_3D8], xmm0
0x180040036  call    memset_0
0x18004003b  mov     rax, [rbp+3F0h+var_430]
0x18004003f  lea     ebx, [rdi+2]
0x180040042  xor     ecx, ecx
0x180040044  mov     [rbp+3F0h+var_45C], ebx
0x180040047  xorps   xmm1, xmm1
0x18004004a  mov     [rbp+3F0h+var_448], rcx
0x18004004e  xorps   xmm0, xmm0
0x180040051  mov     [rbp+3F0h+var_460], ecx
0x180040054  mov     [rax], rcx
0x180040057  mov     r15d, ecx
0x18004005a  mov     rax, [rbp+3F0h+var_438]
0x18004005e  mov     esi, ecx
0x180040060  movups  xmmword ptr [rbp+3F0h+var_3F8], xmm1
0x180040064  mov     [rbp+3F0h+var_470], ecx
0x180040067  movups  [rbp+3F0h+var_408], xmm0
0x18004006b  mov     [rax], ecx
0x18004006d  movups  xmmword ptr [rbp+3F0h+var_3F8+0Ch], xmm1
0x180040071  mov     qword ptr [rbp+3F0h+PerformanceCount], rcx
0x180040075  mov     qword ptr [rbp+3F0h+var_418], rcx
0x180040079  call    ?NlStartNetlogonCall@@YAHXZ; NlStartNetlogonCall(void)
0x18004007e  test    eax, eax
0x180040080  jnz     short loc_18004008C
0x180040082  mov     eax, 0C000000Dh
0x180040087  jmp     loc_1800406B4
0x18004008c  mov     [rbp+3F0h+Buf1], rsi
0x180040090  mov     eax, 1
0x180040095  mov     [rbp+3F0h+var_428], rsi
0x180040099  lock add cs:?gDCPingGlobalPerfCounters@@3U_DOMAINCONTROLLER_GLOBAL_PING_COUNTERS@@A, rax; _DOMAINCONTROLLER_GLOBAL_PING_COUNTERS gDCPingGlobalPerfCounters
0x1800400a1  lock add cs:qword_1800F8D08, rax
0x1800400a9  lea     rcx, [rbp+3F0h+PerformanceCount]; lpPerformanceCount
0x1800400ad  call    cs:__imp_QueryPerformanceCounter
0x1800400b4  nop     dword ptr [rax+rax+00h]
0x1800400b9  test    r12, r12
0x1800400bc  jz      short loc_180040116
0x1800400be  cmp     [r12], bx
0x1800400c3  jz      short loc_180040102
0x1800400c5  cmp     word ptr [r12], 17h
0x1800400cb  jz      short loc_1800400E3
0x1800400cd  lea     rdx, aINetlogonldapl_8; "I_NetlogonLdapLookupEx: DS passed us a "...
0x1800400d4  mov     ecx, 100h; unsigned int
0x1800400d9  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800400de  xor     r12d, r12d
0x1800400e1  jmp     short loc_180040116
0x1800400e3  movups  xmm0, xmmword ptr [r12]
0x1800400e8  xor     eax, eax
0x1800400ea  movups  xmm1, xmmword ptr [r12+0Ch]
0x1800400f0  lea     r12, [rbp+3F0h+var_3F8]
0x1800400f4  movups  xmmword ptr [rbp+3F0h+var_3F8], xmm0
0x1800400f8  mov     word ptr [rbp+3F0h+var_3F8+2], ax
0x1800400fc  movups  xmmword ptr [rbp+3F0h+var_3F8+0Ch], xmm1
0x180040100  jmp     short loc_180040116
0x180040102  movups  xmm0, xmmword ptr [r12]
0x180040107  xor     eax, eax
0x180040109  lea     r12, [rbp+3F0h+var_408]
0x18004010d  movdqu  [rbp+3F0h+var_408], xmm0
0x180040112  mov     word ptr [rbp+3F0h+var_408+2], ax
0x180040116  test    r13, r13
0x180040119  jz      loc_180040594
0x18004011f  mov     eax, 1
0x180040124  cmp     [r13+0], ax
0x180040129  jz      short loc_18004014B
0x18004012b  lea     rdx, aINetlogonldapl_14; "I_NetlogonLdapLookup: Filter doesn't ha"...
0x180040132  movzx   r8d, word ptr [r13+0]
0x180040137  mov     ecx, 100h; unsigned int
0x18004013c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180040141  mov     ebx, 0C000000Dh
0x180040146  jmp     loc_180040608
0x18004014b  mov     rsi, [r13+8]
0x18004014f  mov     eax, 4
0x180040154  test    rsi, rsi
0x180040157  jz      loc_18004058E
0x18004015d  lea     rbx, [rsi+8]
0x180040161  cmp     [rbx], ax
0x180040164  jnz     loc_180040582
0x18004016a  lea     rdx, aDnsdomain; "DnsDomain"
0x180040171  mov     rcx, rbx; struct Filter *
0x180040174  call    ?IsFilterName@@YAEPEAUFilter@@PEAD@Z; IsFilterName(Filter *,char *)
0x180040179  test    al, al
0x18004017b  jz      short loc_1800401D7
0x18004017d  mov     eax, [rsi+20h]
0x180040180  test    eax, eax
0x180040182  jz      loc_1800404C8
0x180040188  cmp     [rbp+3F0h+Buffer], 0
0x18004018d  jnz     loc_1800404AF
0x180040193  lea     ecx, [rax+1]; ByteCount
0x180040196  cmp     ecx, eax
0x180040198  jb      loc_1800404A5
0x18004019e  lea     rdx, [rbp+3F0h+Buffer]; Buffer
0x1800401a2  call    cs:__imp_NetApiBufferAllocate
0x1800401a9  nop     dword ptr [rax+rax+00h]
0x1800401ae  test    eax, eax
0x1800401b0  jnz     loc_18004049B
0x1800401b6  mov     r8d, [rsi+20h]; Size
0x1800401ba  mov     rdx, [rsi+28h]; Src
0x1800401be  mov     rcx, [rbp+3F0h+Buffer]; void *
0x1800401c2  call    memcpy_0
0x1800401c7  mov     ecx, [rbx+18h]
0x1800401ca  mov     rax, [rbp+3F0h+Buffer]
0x1800401ce  mov     byte ptr [rcx+rax], 0
0x1800401d2  jmp     loc_180040493
0x1800401d7  lea     rdx, aHost; "Host"
0x1800401de  mov     rcx, rbx; struct Filter *
0x1800401e1  call    ?IsFilterName@@YAEPEAUFilter@@PEAD@Z; IsFilterName(Filter *,char *)
0x1800401e6  test    al, al
0x1800401e8  jz      short loc_18004021A
0x1800401ea  test    rdi, rdi
0x1800401ed  jnz     loc_180040500
0x1800401f3  lea     r9, [rbp+3F0h+var_450]; unsigned __int16 **
0x1800401f7  mov     rcx, rbx; struct Filter *
0x1800401fa  lea     r8, [rbp+3F0h+var_370]; unsigned __int16 *
0x180040201  lea     edx, [rdi+10h]; unsigned int
0x180040204  call    ?FilterString@@YAKPEAUFilter@@KPEAGPEAPEAG@Z; FilterString(Filter *,ulong,ushort *,ushort * *)
0x180040209  test    eax, eax
0x18004020b  jnz     loc_1800404DE
0x180040211  mov     rdi, [rbp+3F0h+var_450]
0x180040215  jmp     loc_180040493
0x18004021a  lea     rdx, aUser; "User"
0x180040221  mov     rcx, rbx; struct Filter *
0x180040224  call    ?IsFilterName@@YAEPEAUFilter@@PEAD@Z; IsFilterName(Filter *,char *)
0x180040229  test    al, al
0x18004022b  jz      short loc_18004025E
0x18004022d  test    r15, r15
0x180040230  jnz     loc_18004052B
0x180040236  lea     r9, [rbp+3F0h+var_448]; unsigned __int16 **
0x18004023a  mov     rcx, rbx; struct Filter *
0x18004023d  lea     r8, [rbp+3F0h+var_350]; unsigned __int16 *
0x180040244  lea     edx, [r15+15h]; unsigned int
0x180040248  call    ?FilterString@@YAKPEAUFilter@@KPEAGPEAPEAG@Z; FilterString(Filter *,ulong,ushort *,ushort * *)
0x18004024d  test    eax, eax
0x18004024f  jnz     loc_180040509
0x180040255  mov     r15, [rbp+3F0h+var_448]
0x180040259  jmp     loc_180040493
0x18004025e  lea     rdx, aAac; "AAC"
0x180040265  mov     rcx, rbx; struct Filter *
0x180040268  call    ?IsFilterName@@YAEPEAUFilter@@PEAD@Z; IsFilterName(Filter *,char *)
0x18004026d  mov     rcx, rbx; struct Filter *
0x180040270  test    al, al
0x180040272  jz      short loc_1800402B1
0x180040274  lea     r9, [rbp+3F0h+var_470]; unsigned int *
0x180040278  mov     edx, 4; unsigned int
0x18004027d  lea     r8, [rbp+3F0h+var_460]; void *
0x180040281  call    ?FilterBinary@@YAKPEAUFilter@@KPEAXPEAK@Z; FilterBinary(Filter *,ulong,void *,ulong *)
0x180040286  mov     r9d, [rbp+3F0h+var_470]
0x18004028a  test    eax, eax
0x18004028c  jnz     short loc_180040298
0x18004028e  cmp     r9d, 4
0x180040292  jz      loc_180040493
0x180040298  lea     rdx, aINetlogonldapl_6; "I_NetlogonLdapLookup: Bad AllowableAcco"...
0x18004029f  mov     r8d, eax
0x1800402a2  mov     ecx, 100h; unsigned int
0x1800402a7  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800402ac  jmp     loc_180040141
0x1800402b1  lea     rdx, aDomainsid; "DomainSid"
0x1800402b8  call    ?IsFilterName@@YAEPEAUFilter@@PEAD@Z; IsFilterName(Filter *,char *)
0x1800402bd  mov     rcx, rbx; struct Filter *
0x1800402c0  test    al, al
0x1800402c2  jz      short loc_18004031E
0x1800402c4  lea     r9, [rbp+3F0h+var_470]; unsigned int *
0x1800402c8  mov     edx, 48h ; 'H'; unsigned int
0x1800402cd  lea     r8, [rbp+3F0h+Sid]; void *
0x1800402d1  call    ?FilterBinary@@YAKPEAUFilter@@KPEAXPEAK@Z; FilterBinary(Filter *,ulong,void *,ulong *)
0x1800402d6  mov     ebx, eax
0x1800402d8  test    eax, eax
0x1800402da  jnz     loc_180040534
0x1800402e0  lea     rcx, [rbp+3F0h+Sid]; Sid
0x1800402e4  call    cs:__imp_RtlValidSid
0x1800402eb  nop     dword ptr [rax+rax+00h]
0x1800402f0  test    al, al
0x1800402f2  jz      loc_180040534
0x1800402f8  lea     rcx, [rbp+3F0h+Sid]; Sid
0x1800402fc  call    cs:__imp_RtlLengthSid
0x180040303  nop     dword ptr [rax+rax+00h]
0x180040308  cmp     eax, [rbp+3F0h+var_470]
0x18004030b  jnz     loc_180040534
0x180040311  lea     rax, [rbp+3F0h+Sid]
0x180040315  mov     [rbp+3F0h+var_428], rax
0x180040319  jmp     loc_180040493
0x18004031e  lea     rdx, aDomainguid; "DomainGuid"
0x180040325  call    ?IsFilterName@@YAEPEAUFilter@@PEAD@Z; IsFilterName(Filter *,char *)
0x18004032a  mov     rcx, rbx; struct Filter *
0x18004032d  test    al, al
0x18004032f  jz      short loc_180040366
0x180040331  lea     r9, [rbp+3F0h+var_470]; unsigned int *
0x180040335  mov     edx, 10h; unsigned int
0x18004033a  lea     r8, [rbp+3F0h+var_3D8]; void *
0x18004033e  call    ?FilterBinary@@YAKPEAUFilter@@KPEAXPEAK@Z; FilterBinary(Filter *,ulong,void *,ulong *)
0x180040343  mov     r9d, [rbp+3F0h+var_470]
0x180040347  test    eax, eax
0x180040349  jnz     loc_180040547
0x18004034f  cmp     r9d, 10h
0x180040353  jnz     loc_180040547
0x180040359  lea     rax, [rbp+3F0h+var_3D8]
0x18004035d  mov     [rbp+3F0h+Buf1], rax
0x180040361  jmp     loc_180040493
0x180040366  lea     rdx, aNtver; "NtVer"
0x18004036d  call    ?IsFilterName@@YAEPEAUFilter@@PEAD@Z; IsFilterName(Filter *,char *)
0x180040372  mov     rcx, rbx; struct Filter *
0x180040375  test    al, al
0x180040377  jz      short loc_1800403A9
0x180040379  lea     r9, [rbp+3F0h+var_470]; unsigned int *
0x18004037d  mov     edx, 4; unsigned int
0x180040382  lea     r8, [rbp+3F0h+var_45C]; void *
0x180040386  call    ?FilterBinary@@YAKPEAUFilter@@KPEAXPEAK@Z; FilterBinary(Filter *,ulong,void *,ulong *)
0x18004038b  mov     r9d, [rbp+3F0h+var_470]
0x18004038f  test    eax, eax
0x180040391  jnz     short loc_18004039D
0x180040393  cmp     r9d, 4
0x180040397  jz      loc_180040493
0x18004039d  lea     rdx, aINetlogonldapl_7; "I_NetlogonLdapLookup: Bad NtVersionFlag"...
0x1800403a4  jmp     loc_18004029F
0x1800403a9  lea     rdx, aDnshostname; "DnsHostName"
0x1800403b0  call    ?IsFilterName@@YAEPEAUFilter@@PEAD@Z; IsFilterName(Filter *,char *)
0x1800403b5  test    al, al
0x1800403b7  jz      short loc_1800403EF
0x1800403b9  test    r14, r14
0x1800403bc  jnz     loc_180040573
0x1800403c2  mov     r14d, 100h
0x1800403c8  lea     r9, [rbp+3F0h+var_440]; unsigned __int16 **
0x1800403cc  mov     edx, r14d; unsigned int
0x1800403cf  lea     r8, [rbp+3F0h+var_250]; unsigned __int16 *
0x1800403d6  mov     rcx, rbx; struct Filter *
0x1800403d9  call    ?FilterString@@YAKPEAUFilter@@KPEAGPEAPEAG@Z; FilterString(Filter *,ulong,ushort *,ushort * *)
0x1800403de  test    eax, eax
0x1800403e0  jnz     loc_180040553
0x1800403e6  mov     r14, [rbp+3F0h+var_440]
0x1800403ea  jmp     loc_180040493
0x1800403ef  test    cs:?NlGlobalParameters@@3U_NETLOGON_PARAMETERS@@A, 100h; _NETLOGON_PARAMETERS NlGlobalParameters
0x1800403f9  jz      loc_180040493
0x1800403ff  xor     edx, edx; Val
0x180040401  mov     [rbp+3F0h+var_458], 0
0x180040409  mov     r8d, 0C8h; Size
0x18004040f  lea     rcx, [rbp+3F0h+var_320]; void *
0x180040416  call    memset_0
0x18004041b  mov     edx, [rbx+8]; cbMultiByte
0x18004041e  lea     rax, [rbp+3F0h+var_458]
0x180040422  mov     rcx, [rsi+18h]; lpMultiByteStr
0x180040426  lea     r9, [rbp+3F0h+var_320]; unsigned __int16 *
0x18004042d  mov     r8d, 64h ; 'd'; unsigned int
0x180040433  mov     [rsp+4F0h+var_4D0], rax; unsigned __int16 **
0x180040438  call    ?NetpAllocWStrFromUtf8StrAsRequired@@YAKPEADKKPEAGPEAPEAG@Z; NetpAllocWStrFromUtf8StrAsRequired(char *,ulong,ulong,ushort *,ushort * *)
0x18004043d  mov     ecx, 100h; unsigned int
0x180040442  test    eax, eax
0x180040444  jnz     short loc_180040487
0x180040446  mov     rax, [rbp+3F0h+var_458]
0x18004044a  lea     r8, [rbp+3F0h+var_320]
0x180040451  test    rax, rax
0x180040454  lea     rdx, aINetlogonldapl_1; "I_NetlogonLdapLookup: unrecognized filt"...
0x18004045b  cmovnz  r8, rax
0x18004045f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180040464  mov     rcx, [rbp+3F0h+var_458]; Buffer
0x180040468  test    rcx, rcx
0x18004046b  jz      short loc_180040493
0x18004046d  lea     rax, [rbp+3F0h+var_320]
0x180040474  cmp     rcx, rax
0x180040477  jz      short loc_180040493
0x180040479  call    cs:__imp_NetApiBufferFree
0x180040480  nop     dword ptr [rax+rax+00h]
0x180040485  jmp     short loc_180040493
0x180040487  lea     rdx, aINetlogonldapl_2; "I_NetlogonLdapLookup: unrecognized filt"...
0x18004048e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180040493  mov     rsi, [rsi]
0x180040496  jmp     loc_18004014F
0x18004049b  mov     ebx, 0C0000017h
0x1800404a0  jmp     loc_180040608
0x1800404a5  mov     ebx, 0C0000095h
0x1800404aa  jmp     loc_18004061D
0x1800404af  lea     rdx, aINetlogonldapl_10; "I_NetlogonLdapLookup: Bad ping from %ws"...
0x1800404b6  mov     r8, rdi
0x1800404b9  mov     ecx, 100h; unsigned int
0x1800404be  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800404c3  jmp     loc_180040141
0x1800404c8  lea     rdx, aINetlogonldapl_11; "I_NetlogonLdapLookup: Bad DnsDomainName"...
  ... truncated ...
```
