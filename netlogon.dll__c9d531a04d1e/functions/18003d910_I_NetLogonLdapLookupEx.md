# I_NetLogonLdapLookupEx

- ea: `0x18003d910`
- end: `0x18003dfdb`
- name: `I_NetLogonLdapLookupEx`
- size: `1739`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007278`
- `0x18000ccf0`
- `0x18000d094`
- `0x18000e270`
- `0x18000ed34`
- `0x18003d7f8`
- `0x18003d840`
- `0x18003d8cc`
- `0x18003d910`
- `0x18003f054`
- `0x18006ef9c`
- `0x180082e88`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003d9ed`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003df8b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003d9ed`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003df8b`
- `ntdll!RtlLengthSid` at `0x18003dc2a`
- `ntdll!RtlLengthSid` at `0x18003dc2a`
- `ntdll!RtlValidSid` at `0x18003dc18`
- `ntdll!RtlValidSid` at `0x18003dc18`
- `netutils!NetApiBufferFree` at `0x18003dda1`
- `netutils!NetApiBufferFree` at `0x18003df33`
- `netutils!NetApiBufferFree` at `0x18003df4d`
- `netutils!NetApiBufferFree` at `0x18003df67`
- `netutils!NetApiBufferFree` at `0x18003df81`
- `netutils!NetApiBufferFree` at `0x18003dda1`
- `netutils!NetApiBufferFree` at `0x18003df33`
- `netutils!NetApiBufferFree` at `0x18003df4d`
- `netutils!NetApiBufferFree` at `0x18003df67`
- `netutils!NetApiBufferFree` at `0x18003df81`
- `netutils!NetApiBufferAllocate` at `0x18003dadc`
- `netutils!NetApiBufferAllocate` at `0x18003dadc`

## string_xrefs

- `0x18003de22`: `I_NetlogonLdapLookup: Bad ping from %ws: multiple UnicodeComputerName\n`
- `0x18003de03`: `I_NetlogonLdapLookup: Bad UnicodeComputerName 0x%lx\n`
- `0x18003de78`: `I_NetlogonLdapLookup: Bad UnicodeComputerName 0x%lx\n`
- `0x18003dbe5`: `DomainSid`
- `0x18003de5a`: `I_NetlogonLdapLookup: Bad DomainSid 0x%lx %ld\n`

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
  _InterlockedAdd64(&qword_1800F1D48, 1u);
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
  _InterlockedAdd64(&qword_1800F1D50, v50.QuadPart - PerformanceCount.QuadPart);
  _InterlockedIncrement64(&qword_1800F1D58);
  _InterlockedDecrement64((volatile signed __int64 *)&gDCPingGlobalPerfCounters);
  NlEndNetlogonCall();
  return v15;
}

```

## disassembly

```asm
0x18003d910  push    rbp
0x18003d912  push    rbx
0x18003d913  push    rsi
0x18003d914  push    rdi
0x18003d915  push    r12
0x18003d917  push    r13
0x18003d919  push    r14
0x18003d91b  push    r15
0x18003d91d  lea     rbp, [rsp-3B8h]
0x18003d925  sub     rsp, 4B8h
0x18003d92c  mov     rax, cs:__security_cookie
0x18003d933  xor     rax, rsp
0x18003d936  mov     [rbp+3F0h+var_50], rax
0x18003d93d  mov     [rbp+3F0h+var_430], r8
0x18003d941  mov     r12, rdx
0x18003d944  mov     r13, rcx
0x18003d947  mov     [rbp+3F0h+var_438], r9
0x18003d94b  xorps   xmm0, xmm0
0x18003d94e  mov     [rbp+3F0h+Buffer], 0
0x18003d956  xor     edi, edi
0x18003d958  lea     rcx, [rbp+3F0h+var_250]; void *
0x18003d95f  xor     r14d, r14d
0x18003d962  mov     [rbp+3F0h+var_450], rdi
0x18003d966  xor     edx, edx; Val
0x18003d968  mov     [rbp+3F0h+var_440], r14
0x18003d96c  mov     r8d, 200h; Size
0x18003d972  movups  [rbp+3F0h+var_3D8], xmm0
0x18003d976  call    memset_0
0x18003d97b  mov     rax, [rbp+3F0h+var_430]
0x18003d97f  lea     ebx, [rdi+2]
0x18003d982  xor     ecx, ecx
0x18003d984  mov     [rbp+3F0h+var_45C], ebx
0x18003d987  xorps   xmm1, xmm1
0x18003d98a  mov     [rbp+3F0h+var_448], rcx
0x18003d98e  xorps   xmm0, xmm0
0x18003d991  mov     [rbp+3F0h+var_460], ecx
0x18003d994  mov     [rax], rcx
0x18003d997  mov     r15d, ecx
0x18003d99a  mov     rax, [rbp+3F0h+var_438]
0x18003d99e  mov     esi, ecx
0x18003d9a0  movups  xmmword ptr [rbp+3F0h+var_3F8], xmm1
0x18003d9a4  mov     [rbp+3F0h+var_470], ecx
0x18003d9a7  movups  [rbp+3F0h+var_408], xmm0
0x18003d9ab  mov     [rax], ecx
0x18003d9ad  movups  xmmword ptr [rbp+3F0h+var_3F8+0Ch], xmm1
0x18003d9b1  mov     qword ptr [rbp+3F0h+PerformanceCount], rcx
0x18003d9b5  mov     qword ptr [rbp+3F0h+var_418], rcx
0x18003d9b9  call    ?NlStartNetlogonCall@@YAHXZ; NlStartNetlogonCall(void)
0x18003d9be  test    eax, eax
0x18003d9c0  jnz     short loc_18003D9CC
0x18003d9c2  mov     eax, 0C000000Dh
0x18003d9c7  jmp     loc_18003DFB8
0x18003d9cc  mov     [rbp+3F0h+Buf1], rsi
0x18003d9d0  mov     eax, 1
0x18003d9d5  mov     [rbp+3F0h+var_428], rsi
0x18003d9d9  lock add cs:?gDCPingGlobalPerfCounters@@3U_DOMAINCONTROLLER_GLOBAL_PING_COUNTERS@@A, rax; _DOMAINCONTROLLER_GLOBAL_PING_COUNTERS gDCPingGlobalPerfCounters
0x18003d9e1  lock add cs:qword_1800F1D48, rax
0x18003d9e9  lea     rcx, [rbp+3F0h+PerformanceCount]; lpPerformanceCount
0x18003d9ed  call    cs:__imp_QueryPerformanceCounter
0x18003d9f3  test    r12, r12
0x18003d9f6  jz      short loc_18003DA50
0x18003d9f8  cmp     [r12], bx
0x18003d9fd  jz      short loc_18003DA3C
0x18003d9ff  cmp     word ptr [r12], 17h
0x18003da05  jz      short loc_18003DA1D
0x18003da07  lea     rdx, aINetlogonldapl_8; "I_NetlogonLdapLookupEx: DS passed us a "...
0x18003da0e  mov     ecx, 100h; unsigned int
0x18003da13  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003da18  xor     r12d, r12d
0x18003da1b  jmp     short loc_18003DA50
0x18003da1d  movups  xmm0, xmmword ptr [r12]
0x18003da22  xor     eax, eax
0x18003da24  movups  xmm1, xmmword ptr [r12+0Ch]
0x18003da2a  lea     r12, [rbp+3F0h+var_3F8]
0x18003da2e  movups  xmmword ptr [rbp+3F0h+var_3F8], xmm0
0x18003da32  mov     word ptr [rbp+3F0h+var_3F8+2], ax
0x18003da36  movups  xmmword ptr [rbp+3F0h+var_3F8+0Ch], xmm1
0x18003da3a  jmp     short loc_18003DA50
0x18003da3c  movups  xmm0, xmmword ptr [r12]
0x18003da41  xor     eax, eax
0x18003da43  lea     r12, [rbp+3F0h+var_408]
0x18003da47  movdqu  [rbp+3F0h+var_408], xmm0
0x18003da4c  mov     word ptr [rbp+3F0h+var_408+2], ax
0x18003da50  test    r13, r13
0x18003da53  jz      loc_18003DEB6
0x18003da59  mov     eax, 1
0x18003da5e  cmp     [r13+0], ax
0x18003da63  jz      short loc_18003DA85
0x18003da65  lea     rdx, aINetlogonldapl_14; "I_NetlogonLdapLookup: Filter doesn't ha"...
0x18003da6c  movzx   r8d, word ptr [r13+0]
0x18003da71  mov     ecx, 100h; unsigned int
0x18003da76  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003da7b  mov     ebx, 0C000000Dh
0x18003da80  jmp     loc_18003DF2A
0x18003da85  mov     rsi, [r13+8]
0x18003da89  mov     eax, 4
0x18003da8e  test    rsi, rsi
0x18003da91  jz      loc_18003DEB0
0x18003da97  lea     rbx, [rsi+8]
0x18003da9b  cmp     [rbx], ax
0x18003da9e  jnz     loc_18003DEA4
0x18003daa4  lea     rdx, aDnsdomain; "DnsDomain"
0x18003daab  mov     rcx, rbx; struct Filter *
0x18003daae  call    ?IsFilterName@@YAEPEAUFilter@@PEAD@Z; IsFilterName(Filter *,char *)
0x18003dab3  test    al, al
0x18003dab5  jz      short loc_18003DB0B
0x18003dab7  mov     eax, [rsi+20h]
0x18003daba  test    eax, eax
0x18003dabc  jz      loc_18003DDEA
0x18003dac2  cmp     [rbp+3F0h+Buffer], 0
0x18003dac7  jnz     loc_18003DDD1
0x18003dacd  lea     ecx, [rax+1]; ByteCount
0x18003dad0  cmp     ecx, eax
0x18003dad2  jb      loc_18003DDC7
0x18003dad8  lea     rdx, [rbp+3F0h+Buffer]; Buffer
0x18003dadc  call    cs:__imp_NetApiBufferAllocate
0x18003dae2  test    eax, eax
0x18003dae4  jnz     loc_18003DDBD
0x18003daea  mov     r8d, [rsi+20h]; Size
0x18003daee  mov     rdx, [rsi+28h]; Src
0x18003daf2  mov     rcx, [rbp+3F0h+Buffer]; void *
0x18003daf6  call    memcpy_0
0x18003dafb  mov     ecx, [rbx+18h]
0x18003dafe  mov     rax, [rbp+3F0h+Buffer]
0x18003db02  mov     byte ptr [rcx+rax], 0
0x18003db06  jmp     loc_18003DDB5
0x18003db0b  lea     rdx, aHost; "Host"
0x18003db12  mov     rcx, rbx; struct Filter *
0x18003db15  call    ?IsFilterName@@YAEPEAUFilter@@PEAD@Z; IsFilterName(Filter *,char *)
0x18003db1a  test    al, al
0x18003db1c  jz      short loc_18003DB4E
0x18003db1e  test    rdi, rdi
0x18003db21  jnz     loc_18003DE22
0x18003db27  lea     r9, [rbp+3F0h+var_450]; unsigned __int16 **
0x18003db2b  mov     rcx, rbx; struct Filter *
0x18003db2e  lea     r8, [rbp+3F0h+var_370]; unsigned __int16 *
0x18003db35  lea     edx, [rdi+10h]; unsigned int
0x18003db38  call    ?FilterString@@YAKPEAUFilter@@KPEAGPEAPEAG@Z; FilterString(Filter *,ulong,ushort *,ushort * *)
0x18003db3d  test    eax, eax
0x18003db3f  jnz     loc_18003DE00
0x18003db45  mov     rdi, [rbp+3F0h+var_450]
0x18003db49  jmp     loc_18003DDB5
0x18003db4e  lea     rdx, aUser; "User"
0x18003db55  mov     rcx, rbx; struct Filter *
0x18003db58  call    ?IsFilterName@@YAEPEAUFilter@@PEAD@Z; IsFilterName(Filter *,char *)
0x18003db5d  test    al, al
0x18003db5f  jz      short loc_18003DB92
0x18003db61  test    r15, r15
0x18003db64  jnz     loc_18003DE4D
0x18003db6a  lea     r9, [rbp+3F0h+var_448]; unsigned __int16 **
0x18003db6e  mov     rcx, rbx; struct Filter *
0x18003db71  lea     r8, [rbp+3F0h+var_350]; unsigned __int16 *
0x18003db78  lea     edx, [r15+15h]; unsigned int
0x18003db7c  call    ?FilterString@@YAKPEAUFilter@@KPEAGPEAPEAG@Z; FilterString(Filter *,ulong,ushort *,ushort * *)
0x18003db81  test    eax, eax
0x18003db83  jnz     loc_18003DE2B
0x18003db89  mov     r15, [rbp+3F0h+var_448]
0x18003db8d  jmp     loc_18003DDB5
0x18003db92  lea     rdx, aAac; "AAC"
0x18003db99  mov     rcx, rbx; struct Filter *
0x18003db9c  call    ?IsFilterName@@YAEPEAUFilter@@PEAD@Z; IsFilterName(Filter *,char *)
0x18003dba1  mov     rcx, rbx; struct Filter *
0x18003dba4  test    al, al
0x18003dba6  jz      short loc_18003DBE5
0x18003dba8  lea     r9, [rbp+3F0h+var_470]; unsigned int *
0x18003dbac  mov     edx, 4; unsigned int
0x18003dbb1  lea     r8, [rbp+3F0h+var_460]; void *
0x18003dbb5  call    ?FilterBinary@@YAKPEAUFilter@@KPEAXPEAK@Z; FilterBinary(Filter *,ulong,void *,ulong *)
0x18003dbba  mov     r9d, [rbp+3F0h+var_470]
0x18003dbbe  test    eax, eax
0x18003dbc0  jnz     short loc_18003DBCC
0x18003dbc2  cmp     r9d, 4
0x18003dbc6  jz      loc_18003DDB5
0x18003dbcc  lea     rdx, aINetlogonldapl_6; "I_NetlogonLdapLookup: Bad AllowableAcco"...
0x18003dbd3  mov     r8d, eax
0x18003dbd6  mov     ecx, 100h; unsigned int
0x18003dbdb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003dbe0  jmp     loc_18003DA7B
0x18003dbe5  lea     rdx, aDomainsid; "DomainSid"
0x18003dbec  call    ?IsFilterName@@YAEPEAUFilter@@PEAD@Z; IsFilterName(Filter *,char *)
0x18003dbf1  mov     rcx, rbx; struct Filter *
0x18003dbf4  test    al, al
0x18003dbf6  jz      short loc_18003DC46
0x18003dbf8  lea     r9, [rbp+3F0h+var_470]; unsigned int *
0x18003dbfc  mov     edx, 48h ; 'H'; unsigned int
0x18003dc01  lea     r8, [rbp+3F0h+Sid]; void *
0x18003dc05  call    ?FilterBinary@@YAKPEAUFilter@@KPEAXPEAK@Z; FilterBinary(Filter *,ulong,void *,ulong *)
0x18003dc0a  mov     ebx, eax
0x18003dc0c  test    eax, eax
0x18003dc0e  jnz     loc_18003DE56
0x18003dc14  lea     rcx, [rbp+3F0h+Sid]; Sid
0x18003dc18  call    cs:__imp_RtlValidSid
0x18003dc1e  test    al, al
0x18003dc20  jz      loc_18003DE56
0x18003dc26  lea     rcx, [rbp+3F0h+Sid]; Sid
0x18003dc2a  call    cs:__imp_RtlLengthSid
0x18003dc30  cmp     eax, [rbp+3F0h+var_470]
0x18003dc33  jnz     loc_18003DE56
0x18003dc39  lea     rax, [rbp+3F0h+Sid]
0x18003dc3d  mov     [rbp+3F0h+var_428], rax
0x18003dc41  jmp     loc_18003DDB5
0x18003dc46  lea     rdx, aDomainguid; "DomainGuid"
0x18003dc4d  call    ?IsFilterName@@YAEPEAUFilter@@PEAD@Z; IsFilterName(Filter *,char *)
0x18003dc52  mov     rcx, rbx; struct Filter *
0x18003dc55  test    al, al
0x18003dc57  jz      short loc_18003DC8E
0x18003dc59  lea     r9, [rbp+3F0h+var_470]; unsigned int *
0x18003dc5d  mov     edx, 10h; unsigned int
0x18003dc62  lea     r8, [rbp+3F0h+var_3D8]; void *
0x18003dc66  call    ?FilterBinary@@YAKPEAUFilter@@KPEAXPEAK@Z; FilterBinary(Filter *,ulong,void *,ulong *)
0x18003dc6b  mov     r9d, [rbp+3F0h+var_470]
0x18003dc6f  test    eax, eax
0x18003dc71  jnz     loc_18003DE69
0x18003dc77  cmp     r9d, 10h
0x18003dc7b  jnz     loc_18003DE69
0x18003dc81  lea     rax, [rbp+3F0h+var_3D8]
0x18003dc85  mov     [rbp+3F0h+Buf1], rax
0x18003dc89  jmp     loc_18003DDB5
0x18003dc8e  lea     rdx, aNtver; "NtVer"
0x18003dc95  call    ?IsFilterName@@YAEPEAUFilter@@PEAD@Z; IsFilterName(Filter *,char *)
0x18003dc9a  mov     rcx, rbx; struct Filter *
0x18003dc9d  test    al, al
0x18003dc9f  jz      short loc_18003DCD1
0x18003dca1  lea     r9, [rbp+3F0h+var_470]; unsigned int *
0x18003dca5  mov     edx, 4; unsigned int
0x18003dcaa  lea     r8, [rbp+3F0h+var_45C]; void *
0x18003dcae  call    ?FilterBinary@@YAKPEAUFilter@@KPEAXPEAK@Z; FilterBinary(Filter *,ulong,void *,ulong *)
0x18003dcb3  mov     r9d, [rbp+3F0h+var_470]
0x18003dcb7  test    eax, eax
0x18003dcb9  jnz     short loc_18003DCC5
0x18003dcbb  cmp     r9d, 4
0x18003dcbf  jz      loc_18003DDB5
0x18003dcc5  lea     rdx, aINetlogonldapl_7; "I_NetlogonLdapLookup: Bad NtVersionFlag"...
0x18003dccc  jmp     loc_18003DBD3
0x18003dcd1  lea     rdx, aDnshostname; "DnsHostName"
0x18003dcd8  call    ?IsFilterName@@YAEPEAUFilter@@PEAD@Z; IsFilterName(Filter *,char *)
0x18003dcdd  test    al, al
0x18003dcdf  jz      short loc_18003DD17
0x18003dce1  test    r14, r14
0x18003dce4  jnz     loc_18003DE95
0x18003dcea  mov     r14d, 100h
0x18003dcf0  lea     r9, [rbp+3F0h+var_440]; unsigned __int16 **
0x18003dcf4  mov     edx, r14d; unsigned int
0x18003dcf7  lea     r8, [rbp+3F0h+var_250]; unsigned __int16 *
0x18003dcfe  mov     rcx, rbx; struct Filter *
0x18003dd01  call    ?FilterString@@YAKPEAUFilter@@KPEAGPEAPEAG@Z; FilterString(Filter *,ulong,ushort *,ushort * *)
0x18003dd06  test    eax, eax
0x18003dd08  jnz     loc_18003DE75
0x18003dd0e  mov     r14, [rbp+3F0h+var_440]
0x18003dd12  jmp     loc_18003DDB5
0x18003dd17  test    cs:?NlGlobalParameters@@3U_NETLOGON_PARAMETERS@@A, 100h; _NETLOGON_PARAMETERS NlGlobalParameters
0x18003dd21  jz      loc_18003DDB5
0x18003dd27  xor     edx, edx; Val
0x18003dd29  mov     [rbp+3F0h+var_458], 0
0x18003dd31  mov     r8d, 0C8h; Size
0x18003dd37  lea     rcx, [rbp+3F0h+var_320]; void *
0x18003dd3e  call    memset_0
0x18003dd43  mov     edx, [rbx+8]; cbMultiByte
0x18003dd46  lea     rax, [rbp+3F0h+var_458]
0x18003dd4a  mov     rcx, [rsi+18h]; lpMultiByteStr
0x18003dd4e  lea     r9, [rbp+3F0h+var_320]; unsigned __int16 *
0x18003dd55  mov     r8d, 64h ; 'd'; unsigned int
0x18003dd5b  mov     [rsp+4F0h+var_4D0], rax; unsigned __int16 **
0x18003dd60  call    ?NetpAllocWStrFromUtf8StrAsRequired@@YAKPEADKKPEAGPEAPEAG@Z; NetpAllocWStrFromUtf8StrAsRequired(char *,ulong,ulong,ushort *,ushort * *)
0x18003dd65  mov     ecx, 100h; unsigned int
0x18003dd6a  test    eax, eax
0x18003dd6c  jnz     short loc_18003DDA9
0x18003dd6e  mov     rax, [rbp+3F0h+var_458]
0x18003dd72  lea     r8, [rbp+3F0h+var_320]
0x18003dd79  test    rax, rax
0x18003dd7c  lea     rdx, aINetlogonldapl_1; "I_NetlogonLdapLookup: unrecognized filt"...
0x18003dd83  cmovnz  r8, rax
0x18003dd87  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003dd8c  mov     rcx, [rbp+3F0h+var_458]; Buffer
0x18003dd90  test    rcx, rcx
0x18003dd93  jz      short loc_18003DDB5
0x18003dd95  lea     rax, [rbp+3F0h+var_320]
0x18003dd9c  cmp     rcx, rax
0x18003dd9f  jz      short loc_18003DDB5
0x18003dda1  call    cs:__imp_NetApiBufferFree
0x18003dda7  jmp     short loc_18003DDB5
0x18003dda9  lea     rdx, aINetlogonldapl_2; "I_NetlogonLdapLookup: unrecognized filt"...
0x18003ddb0  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003ddb5  mov     rsi, [rsi]
0x18003ddb8  jmp     loc_18003DA89
0x18003ddbd  mov     ebx, 0C0000017h
0x18003ddc2  jmp     loc_18003DF2A
0x18003ddc7  mov     ebx, 0C0000095h
0x18003ddcc  jmp     loc_18003DF39
0x18003ddd1  lea     rdx, aINetlogonldapl_10; "I_NetlogonLdapLookup: Bad ping from %ws"...
0x18003ddd8  mov     r8, rdi
0x18003dddb  mov     ecx, 100h; unsigned int
0x18003dde0  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003dde5  jmp     loc_18003DA7B
0x18003ddea  lea     rdx, aINetlogonldapl_11; "I_NetlogonLdapLookup: Bad DnsDomainName"...
0x18003ddf1  mov     ecx, 100h; unsigned int
0x18003ddf6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003ddfb  jmp     loc_18003DA7B
0x18003de00  mov     r8d, eax
0x18003de03  lea     rdx, aINetlogonldapl_4; "I_NetlogonLdapLookup: Bad UnicodeComput"...
  ... truncated ...
```
