# HelperV6ChangeNotification

- ea: `0x180050870`
- end: `0x18005112b`
- name: `HelperV6ChangeNotification`
- size: `2235`
- prototype: `__int64 __fastcall(void *Buf1)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task`

## callers

- `0x18001abb0`
- `0x180055114`

## callees

- `0x180002bbe`
- `0x180050870`
- `0x1800511bc`
- `0x180051368`
- `0x18005426c`
- `0x1800588f4`
- `0x180058dc4`
- `0x180058e78`
- `0x18005935c`
- `0x180059ac8`
- `0x180071cec`
- `0x180073664`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18005107d`
- `KERNEL32!LocalFree` at `0x1800510f0`
- `KERNEL32!LocalFree` at `0x18005107d`
- `KERNEL32!LocalFree` at `0x1800510f0`
- `KERNEL32!LeaveCriticalSection` at `0x180050cdb`
- `KERNEL32!LeaveCriticalSection` at `0x180050f18`
- `KERNEL32!LeaveCriticalSection` at `0x180051102`
- `KERNEL32!LeaveCriticalSection` at `0x180050cdb`
- `KERNEL32!LeaveCriticalSection` at `0x180050f18`
- `KERNEL32!LeaveCriticalSection` at `0x180051102`
- `KERNEL32!EnterCriticalSection` at `0x180050bab`
- `KERNEL32!EnterCriticalSection` at `0x180050d01`
- `KERNEL32!EnterCriticalSection` at `0x180050f3e`
- `KERNEL32!EnterCriticalSection` at `0x180050bab`
- `KERNEL32!EnterCriticalSection` at `0x180050d01`
- `KERNEL32!EnterCriticalSection` at `0x180050f3e`
- `ADVAPI32!RegCloseKey` at `0x180050b67`
- `ADVAPI32!RegCloseKey` at `0x180050b67`
- `ADVAPI32!RegOpenKeyExA` at `0x1800509f9`
- `ADVAPI32!RegOpenKeyExA` at `0x1800509f9`
- `ADVAPI32!RegQueryValueExA` at `0x180050a31`
- `ADVAPI32!RegQueryValueExA` at `0x180050a6d`
- `ADVAPI32!RegQueryValueExA` at `0x180050afa`
- `ADVAPI32!RegQueryValueExA` at `0x180050a31`
- `ADVAPI32!RegQueryValueExA` at `0x180050a6d`
- `ADVAPI32!RegQueryValueExA` at `0x180050afa`

## string_xrefs

- `0x1800509c2`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ipv6`
- `0x180050adf`: `AllowNetworkAccess`
- `0x180050b24`: `AllowNetworkAccess`

## pseudocode

```c
void __fastcall HelperV6ChangeNotification(GUID *Buf1)
{
  struct _IPv6PREFIX_POOL *v1; // rbx
  int v3; // r15d
  __int64 v4; // rdx
  int v5; // r14d
  int v6; // r13d
  int v7; // r12d
  int v8; // eax
  _QWORD *v9; // rdi
  int RoutingDomainAddressPool; // edx
  BOOL v11; // r14d
  struct _IPv6PREFIX_POOL *v12; // rcx
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  const wchar_t *v17; // rdx
  int v18; // r15d
  BOOL v19; // r14d
  struct _IPv6PREFIX_POOL *v20; // rcx
  bool v21; // zf
  unsigned int v22; // eax
  struct _GUID v23; // xmm0
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  struct _IPv6PREFIX_POOL *v27; // rcx
  struct _IPv6PREFIX_POOL *v28; // rcx
  BYTE Data[16]; // [rsp+30h] [rbp-D0h] BYREF
  struct _GUID v30; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  BYTE v32[4]; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  int v34; // [rsp+60h] [rbp-A0h] BYREF
  struct _IPv6PREFIX_POOL *v35; // [rsp+68h] [rbp-98h] BYREF
  __int64 v36; // [rsp+70h] [rbp-90h] BYREF
  GUID Buf1a; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v38[3]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v39[30]; // [rsp+C0h] [rbp-40h]
  __int16 v40; // [rsp+DEh] [rbp-22h]
  int v41; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v42[2044]; // [rsp+E4h] [rbp-1Ch] BYREF

  v1 = 0;
  v38[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  Buf1a = 0;
  v38[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v38[2] = *(_OWORD *)L"000-0000-000000000000}";
  *(_DWORD *)Data = 1;
  *(_OWORD *)v39 = *(_OWORD *)L"-000000000000}";
  *(_OWORD *)&v39[14] = *(_OWORD *)L"000000}";
  v35 = 0;
  cbData = 0;
  hKey = 0;
  *(_DWORD *)v32 = 0;
  v36 = 0;
  v40 = 0;
  v41 = 0;
  memset_0(v42, 0, sizeof(v42));
  v3 = dword_1800C8650;
  if ( !memcmp_0(Buf1, &GUID_NULL, 0x10u) )
  {
    v5 = 1;
  }
  else
  {
    v5 = 0;
    MprConvertGuidToString(Buf1, v4, v38);
  }
  if ( (_QWORD)xmmword_1800C9740 )
  {
    LOWORD(v41) = 0;
    FormatRRASErrorString(&v41, L"HelperV6ChangeNotification RDID: %ws", v38);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v41);
  }
  if ( v3 && !v5 )
  {
    v6 = 0;
    v7 = 0;
LABEL_23:
    v8 = 0;
    *(_DWORD *)Data = 0;
    goto LABEL_25;
  }
  v6 = dword_1800C9930;
  v7 = HIDWORD(qword_1800C98F0);
  *Buf1 = GUID_NULL;
  dword_1800C9938 = 1;
  Buf1a = Buf2;
  if ( !RegOpenKeyExA(
          HKEY_LOCAL_MACHINE,
          "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ipv6",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 4;
    if ( RegQueryValueExA(hKey, "UseDhcpAddressing", 0, 0, Data, &cbData) )
      *(_DWORD *)Data = 1;
    cbData = 4;
    if ( !RegQueryValueExA(hKey, "AdvertiseDefaultRoute", 0, 0, v32, &cbData) )
      dword_1800C9938 = *(_DWORD *)v32;
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v41) = 0;
      FormatRRASErrorString(&v41, L"%hs: %d", "AdvertiseDefaultRoute");
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v41);
    }
    cbData = 4;
    if ( !RegQueryValueExA(hKey, "AllowNetworkAccess", 0, 0, v32, &cbData) )
      dword_1800C9934 = *(_DWORD *)v32;
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v41) = 0;
      FormatRRASErrorString(&v41, L"%hs: %d", "AllowNetworkAccess");
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v41);
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v3 )
    goto LABEL_23;
  v8 = *(_DWORD *)Data;
LABEL_25:
  if ( !v8 )
  {
    v30 = *Buf1;
    RasStatIpv6CreatePrefixList(&v30, &v35);
    v1 = v35;
  }
  EnterCriticalSection(&RasSrvrCriticalSection);
  v34 = 0;
  LODWORD(v35) = 4;
  RasRoutingDomainGetConfigParam(Buf1, 3, &v35, &v34);
  v30 = *Buf1;
  if ( v34 )
  {
    v9 = 0;
    RasSrvrEnableIpv6Router(&v30, (unsigned int)dword_1800C9934);
    if ( v3 && !v5 )
    {
      v30 = *Buf1;
      RoutingDomainAddressPool = RasGetRoutingDomainAddressPool(&v30, 2, &v36);
      v11 = RoutingDomainAddressPool == 0;
      if ( !RoutingDomainAddressPool && v36 )
        v9 = *(_QWORD **)(v36 + 40);
      v12 = v1;
      while ( v9 )
      {
        if ( !v12 || v9[1] != *((_QWORD *)v12 + 1) || v9[3] != *((_QWORD *)v12 + 3) )
          goto LABEL_40;
        v9 = (_QWORD *)*v9;
        v12 = *(struct _IPv6PREFIX_POOL **)v12;
      }
      if ( !v12 )
        goto LABEL_52;
LABEL_40:
      if ( !RoutingDomainAddressPool )
      {
        v30 = *Buf1;
        v13 = RasReleaseRoutingDomainAddressPool(&v30);
        if ( v13 )
        {
          if ( (_QWORD)xmmword_1800C9740 )
          {
            LOWORD(v41) = 0;
            FormatRRASErrorString(
              &v41,
              L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d",
              v13);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
              gRasIpAddrMgmtEtwContext,
              xmmword_1800C9740,
              &v41);
          }
        }
        else
        {
          v11 = 0;
        }
      }
      LeaveCriticalSection(&RasSrvrCriticalSection);
      v30 = *Buf1;
      RasIpv6SrvrStop(&v30);
      EnterCriticalSection(&RasSrvrCriticalSection);
      v30 = *Buf1;
      v14 = RasStatv6AddRoutingDomainAddressPool(v1);
      if ( v14 )
      {
        if ( (_QWORD)xmmword_1800C9740 )
        {
          LOWORD(v41) = 0;
          FormatRRASErrorString(&v41, L"RasStatAddRoutingDomainv4AddressPool failed and returned %d", v14);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800C9740,
            &v41);
        }
      }
      else
      {
        v1 = 0;
      }
      v30 = *Buf1;
      v15 = RasIpv6SrvrStart(&v30);
      if ( v15 && (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v41) = 0;
        FormatRRASErrorString(&v41, L"RasSrvrStart failed and returned %d", v15);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v41);
      }
LABEL_52:
      if ( !v11 )
        goto LABEL_97;
      v30 = *Buf1;
      v16 = RasReleaseRoutingDomainAddressPool(&v30);
      if ( !v16 || !(_QWORD)xmmword_1800C9740 )
        goto LABEL_97;
      v17 = L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d";
      goto LABEL_95;
    }
    v30 = *Buf1;
    v18 = RasGetRoutingDomainAddressPool(&v30, 2, &v36);
    v19 = v18 == 0;
    if ( !v18 && v36 )
      v9 = *(_QWORD **)(v36 + 40);
    if ( v6 != *(_DWORD *)Data )
      goto LABEL_69;
    if ( *(_DWORD *)Data )
    {
      if ( v7 != HIDWORD(qword_1800C98F0) )
        goto LABEL_69;
      if ( !v7 )
      {
LABEL_84:
        if ( v19 )
        {
          v30 = *Buf1;
          v26 = RasReleaseRoutingDomainAddressPool(&v30);
          if ( v26 )
          {
            if ( (_QWORD)xmmword_1800C9740 )
            {
              LOWORD(v41) = 0;
              FormatRRASErrorString(
                &v41,
                L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d",
                v26);
              ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
                gRasIpAddrMgmtEtwContext,
                xmmword_1800C9740,
                &v41);
            }
          }
        }
        if ( *(_DWORD *)Data )
          goto LABEL_97;
        if ( !v1 )
          goto LABEL_98;
        do
        {
          v27 = v1;
          v1 = *(struct _IPv6PREFIX_POOL **)v1;
          LocalFree(v27);
        }
        while ( v1 );
        goto LABEL_91;
      }
      v21 = memcmp_0(&Buf1a, &Buf2, 0x10u) == 0;
    }
    else
    {
      v20 = v1;
      while ( v9 )
      {
        if ( !v20 || v9[1] != *((_QWORD *)v20 + 1) || v9[3] != *((_QWORD *)v20 + 3) )
          goto LABEL_69;
        v9 = (_QWORD *)*v9;
        v20 = *(struct _IPv6PREFIX_POOL **)v20;
      }
      v21 = v20 == 0;
    }
    if ( !v21 )
    {
LABEL_69:
      if ( !v18 )
      {
        v30 = *Buf1;
        v22 = RasReleaseRoutingDomainAddressPool(&v30);
        if ( v22 )
        {
          if ( (_QWORD)xmmword_1800C9740 )
          {
            LOWORD(v41) = 0;
            FormatRRASErrorString(
              &v41,
              L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d",
              v22);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
              gRasIpAddrMgmtEtwContext,
              xmmword_1800C9740,
              &v41);
          }
        }
        else
        {
          v19 = 0;
        }
      }
      LeaveCriticalSection(&RasSrvrCriticalSection);
      v30 = *Buf1;
      RasIpv6SrvrStop(&v30);
      EnterCriticalSection(&RasSrvrCriticalSection);
      v23 = *Buf1;
      dword_1800C9930 = *(_DWORD *)Data;
      v30 = v23;
      v24 = RasStatv6AddRoutingDomainAddressPool(v1);
      if ( v24 )
      {
        if ( (_QWORD)xmmword_1800C9740 )
        {
          LOWORD(v41) = 0;
          FormatRRASErrorString(&v41, L"RasStatAddRoutingDomainv4AddressPool failed and returned %d", v24);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800C9740,
            &v41);
        }
      }
      else
      {
        v1 = 0;
      }
      v30 = *Buf1;
      v25 = RasIpv6SrvrStart(&v30);
      if ( v25 && (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v41) = 0;
        FormatRRASErrorString(&v41, L"RasSrvrStart failed and returned %d", v25);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v41);
      }
      goto LABEL_84;
    }
    goto LABEL_84;
  }
  dword_1800C9930 = *(_DWORD *)Data;
  v16 = RasStatv6AddRoutingDomainAddressPool(v1);
  if ( !v16 )
  {
LABEL_91:
    v1 = 0;
    goto LABEL_97;
  }
  if ( !(_QWORD)xmmword_1800C9740 )
    goto LABEL_97;
  v17 = L"RasStatAddRoutingDomainv4AddressPool failed and returned %d";
LABEL_95:
  LOWORD(v41) = 0;
  FormatRRASErrorString(&v41, v17, v16);
  ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
    gRasIpAddrMgmtEtwContext,
    xmmword_1800C9740,
    &v41);
LABEL_97:
  while ( v1 )
  {
    v28 = v1;
    v1 = *(struct _IPv6PREFIX_POOL **)v1;
    LocalFree(v28);
  }
LABEL_98:
  LeaveCriticalSection(&RasSrvrCriticalSection);
}

```

## disassembly

```asm
0x180050870  push    rbp
0x180050872  push    rbx
0x180050873  push    rsi
0x180050874  push    rdi
0x180050875  push    r12
0x180050877  push    r13
0x180050879  push    r14
0x18005087b  push    r15
0x18005087d  lea     rbp, [rsp-7F8h]
0x180050885  sub     rsp, 8F8h
0x18005088c  mov     rax, cs:__security_cookie
0x180050893  xor     rax, rsp
0x180050896  mov     [rbp+830h+var_50], rax
0x18005089d  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x1800508a4  xorps   xmm0, xmm0
0x1800508a7  xor     ebx, ebx
0x1800508a9  movaps  [rbp+830h+var_890], xmm1
0x1800508ad  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x1800508b4  xor     eax, eax
0x1800508b6  movups  xmmword ptr [rsp+930h+Buf1.Data1], xmm0
0x1800508bb  mov     rsi, rcx
0x1800508be  mov     edi, 1
0x1800508c3  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x1800508ca  lea     rcx, [rbp+830h+var_84C]; void *
0x1800508ce  movaps  [rbp+830h+var_8A0], xmm0
0x1800508d2  xor     edx, edx; Val
0x1800508d4  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x1800508db  mov     r8d, 7FCh; Size
0x1800508e1  movaps  [rbp+830h+var_880], xmm0
0x1800508e5  movups  xmm0, xmmword ptr cs:a00000000000000+3Eh; "000000}"
0x1800508ec  mov     dword ptr [rsp+930h+Data], edi
0x1800508f0  movaps  xmmword ptr [rbp+830h+var_870], xmm1
0x1800508f4  movups  xmmword ptr [rbp+830h+var_870+0Eh], xmm0
0x1800508f8  mov     [rsp+930h+var_8C8], rbx
0x1800508fd  mov     [rsp+930h+cbData], ebx
0x180050901  mov     [rsp+930h+hKey], rbx
0x180050906  mov     dword ptr [rsp+930h+var_8DC], ebx
0x18005090a  mov     [rsp+930h+var_8C0], rbx
0x18005090f  mov     [rbp+830h+var_852], ax
0x180050913  mov     [rbp+830h+var_850], eax
0x180050916  call    memset_0
0x18005091b  mov     r15d, cs:dword_1800C8650
0x180050922  lea     r8d, [rdi+0Fh]; Size
0x180050926  lea     rdx, GUID_NULL; Buf2
0x18005092d  mov     rcx, rsi; Buf1
0x180050930  call    memcmp_0
0x180050935  test    eax, eax
0x180050937  jnz     short loc_18005093E
0x180050939  mov     r14d, edi
0x18005093c  jmp     short loc_18005094D
0x18005093e  xor     r14d, r14d
0x180050941  lea     r8, [rbp+830h+var_8A0]
0x180050945  mov     rcx, rsi
0x180050948  call    MprConvertGuidToString
0x18005094d  cmp     qword ptr cs:xmmword_1800C9740, rbx
0x180050954  jz      short loc_18005098E
0x180050956  xor     eax, eax
0x180050958  lea     r8, [rbp+830h+var_8A0]
0x18005095c  lea     rdx, aHelperv6change; "HelperV6ChangeNotification RDID: %ws"
0x180050963  mov     word ptr [rbp+830h+var_850], ax
0x180050967  lea     rcx, [rbp+830h+var_850]
0x18005096b  call    FormatRRASErrorString
0x180050970  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180050977  lea     r8, [rbp+830h+var_850]
0x18005097b  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180050982  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180050989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005098e  mov     edi, 4
0x180050993  test    r15d, r15d
0x180050996  jz      short loc_1800509A8
0x180050998  test    r14d, r14d
0x18005099b  jnz     short loc_1800509A8
0x18005099d  xor     r13d, r13d
0x1800509a0  xor     r12d, r12d
0x1800509a3  jmp     loc_180050B77
0x1800509a8  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800509af  mov     r13d, cs:dword_1800C9930
0x1800509b6  lea     rax, [rsp+930h+hKey]
0x1800509bb  mov     r12d, dword ptr cs:qword_1800C98F0+4
0x1800509c2  lea     rdx, aSystemCurrentc_35; "System\\CurrentControlSet\\Services\\Re"...
0x1800509c9  movdqu  xmmword ptr [rsi], xmm0
0x1800509cd  mov     r9d, 20019h; samDesired
0x1800509d3  xor     r8d, r8d; ulOptions
0x1800509d6  movups  xmm0, xmmword ptr cs:Buf2.Data1
0x1800509dd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800509e4  mov     cs:dword_1800C9938, 1
0x1800509ee  mov     [rsp+930h+phkResult], rax; phkResult
0x1800509f3  movdqu  xmmword ptr [rsp+930h+Buf1.Data1], xmm0
0x1800509f9  call    cs:__imp_RegOpenKeyExA
0x1800509ff  test    eax, eax
0x180050a01  jnz     loc_180050B5D
0x180050a07  mov     rcx, [rsp+930h+hKey]; hKey
0x180050a0c  lea     rax, [rsp+930h+cbData]
0x180050a11  mov     [rsp+930h+lpcbData], rax; lpcbData
0x180050a16  lea     rdx, aUsedhcpaddress; "UseDhcpAddressing"
0x180050a1d  lea     rax, [rsp+930h+Data]
0x180050a22  mov     [rsp+930h+cbData], edi
0x180050a26  xor     r9d, r9d; lpType
0x180050a29  mov     [rsp+930h+phkResult], rax; lpData
0x180050a2e  xor     r8d, r8d; lpReserved
0x180050a31  call    cs:__imp_RegQueryValueExA
0x180050a37  test    eax, eax
0x180050a39  jz      short loc_180050A43
0x180050a3b  mov     dword ptr [rsp+930h+Data], 1
0x180050a43  mov     rcx, [rsp+930h+hKey]; hKey
0x180050a48  lea     rax, [rsp+930h+cbData]
0x180050a4d  mov     [rsp+930h+lpcbData], rax; lpcbData
0x180050a52  lea     rdx, aAdvertisedefau; "AdvertiseDefaultRoute"
0x180050a59  lea     rax, [rsp+930h+var_8DC]
0x180050a5e  mov     [rsp+930h+cbData], edi
0x180050a62  xor     r9d, r9d; lpType
0x180050a65  mov     [rsp+930h+phkResult], rax; lpData
0x180050a6a  xor     r8d, r8d; lpReserved
0x180050a6d  call    cs:__imp_RegQueryValueExA
0x180050a73  test    eax, eax
0x180050a75  jnz     short loc_180050A85
0x180050a77  mov     r9d, dword ptr [rsp+930h+var_8DC]
0x180050a7c  mov     cs:dword_1800C9938, r9d
0x180050a83  jmp     short loc_180050A8C
0x180050a85  mov     r9d, cs:dword_1800C9938
0x180050a8c  cmp     qword ptr cs:xmmword_1800C9740, rbx
0x180050a93  jz      short loc_180050AD0
0x180050a95  xor     eax, eax
0x180050a97  lea     r8, aAdvertisedefau; "AdvertiseDefaultRoute"
0x180050a9e  lea     rdx, aHsD; "%hs: %d"
0x180050aa5  mov     word ptr [rbp+830h+var_850], ax
0x180050aa9  lea     rcx, [rbp+830h+var_850]
0x180050aad  call    FormatRRASErrorString
0x180050ab2  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180050ab9  lea     r8, [rbp+830h+var_850]
0x180050abd  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180050ac4  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180050acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ad0  mov     rcx, [rsp+930h+hKey]; hKey
0x180050ad5  lea     rax, [rsp+930h+cbData]
0x180050ada  mov     [rsp+930h+lpcbData], rax; lpcbData
0x180050adf  lea     rdx, aAllownetworkac; "AllowNetworkAccess"
0x180050ae6  lea     rax, [rsp+930h+var_8DC]
0x180050aeb  mov     [rsp+930h+cbData], edi
0x180050aef  xor     r9d, r9d; lpType
0x180050af2  mov     [rsp+930h+phkResult], rax; lpData
0x180050af7  xor     r8d, r8d; lpReserved
0x180050afa  call    cs:__imp_RegQueryValueExA
0x180050b00  test    eax, eax
0x180050b02  jnz     short loc_180050B12
0x180050b04  mov     r9d, dword ptr [rsp+930h+var_8DC]
0x180050b09  mov     cs:dword_1800C9934, r9d
0x180050b10  jmp     short loc_180050B19
0x180050b12  mov     r9d, cs:dword_1800C9934
0x180050b19  cmp     qword ptr cs:xmmword_1800C9740, rbx
0x180050b20  jz      short loc_180050B5D
0x180050b22  xor     eax, eax
0x180050b24  lea     r8, aAllownetworkac; "AllowNetworkAccess"
0x180050b2b  lea     rdx, aHsD; "%hs: %d"
0x180050b32  mov     word ptr [rbp+830h+var_850], ax
0x180050b36  lea     rcx, [rbp+830h+var_850]
0x180050b3a  call    FormatRRASErrorString
0x180050b3f  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180050b46  lea     r8, [rbp+830h+var_850]
0x180050b4a  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180050b51  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180050b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b5d  mov     rcx, [rsp+930h+hKey]; hKey
0x180050b62  test    rcx, rcx
0x180050b65  jz      short loc_180050B72
0x180050b67  call    cs:__imp_RegCloseKey
0x180050b6d  mov     [rsp+930h+hKey], rbx
0x180050b72  test    r15d, r15d
0x180050b75  jz      short loc_180050B7F
0x180050b77  xor     eax, eax
0x180050b79  mov     dword ptr [rsp+930h+Data], eax
0x180050b7d  jmp     short loc_180050B83
0x180050b7f  mov     eax, dword ptr [rsp+930h+Data]
0x180050b83  test    eax, eax
0x180050b85  jnz     short loc_180050BA4
0x180050b87  movups  xmm0, xmmword ptr [rsi]
0x180050b8a  lea     rdx, [rsp+930h+var_8C8]
0x180050b8f  lea     rcx, [rsp+930h+var_8F0]; Buf1
0x180050b94  movdqu  xmmword ptr [rsp+930h+var_8F0.Data1], xmm0
0x180050b9a  call    RasStatIpv6CreatePrefixList
0x180050b9f  mov     rbx, [rsp+930h+var_8C8]
0x180050ba4  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180050bab  call    cs:__imp_EnterCriticalSection
0x180050bb1  lea     r9, [rsp+930h+var_8D0]
0x180050bb6  mov     [rsp+930h+var_8D0], 0
0x180050bbe  lea     r8, [rsp+930h+var_8C8]
0x180050bc3  mov     dword ptr [rsp+930h+var_8C8], edi
0x180050bc7  mov     edx, 3
0x180050bcc  mov     rcx, rsi
0x180050bcf  call    RasRoutingDomainGetConfigParam
0x180050bd4  cmp     [rsp+930h+var_8D0], 0
0x180050bd9  movups  xmm0, xmmword ptr [rsi]
0x180050bdc  movdqu  xmmword ptr [rsp+930h+var_8F0.Data1], xmm0
0x180050be2  jz      loc_18005108C
0x180050be8  mov     edx, cs:dword_1800C9934
0x180050bee  lea     rcx, [rsp+930h+var_8F0]
0x180050bf3  xor     edi, edi
0x180050bf5  call    RasSrvrEnableIpv6Router
0x180050bfa  test    r15d, r15d
0x180050bfd  jz      loc_180050DFD
0x180050c03  test    r14d, r14d
0x180050c06  jnz     loc_180050DFD
0x180050c0c  movups  xmm0, xmmword ptr [rsi]
0x180050c0f  lea     r8, [rsp+930h+var_8C0]
0x180050c14  lea     edx, [rdi+2]
0x180050c17  lea     rcx, [rsp+930h+var_8F0]
0x180050c1c  movdqu  xmmword ptr [rsp+930h+var_8F0.Data1], xmm0
0x180050c22  call    RasGetRoutingDomainAddressPool
0x180050c27  test    eax, eax
0x180050c29  mov     edx, eax
0x180050c2b  setz    r14b
0x180050c2f  test    eax, eax
0x180050c31  jnz     short loc_180050C41
0x180050c33  mov     rcx, [rsp+930h+var_8C0]
0x180050c38  test    rcx, rcx
0x180050c3b  jz      short loc_180050C41
0x180050c3d  mov     rdi, [rcx+28h]
0x180050c41  mov     rcx, rbx
0x180050c44  test    rdi, rdi
0x180050c47  jz      short loc_180050C6A
0x180050c49  test    rcx, rcx
0x180050c4c  jz      short loc_180050C73
0x180050c4e  mov     rax, [rdi+8]
0x180050c52  cmp     rax, [rcx+8]
0x180050c56  jnz     short loc_180050C73
0x180050c58  mov     rax, [rdi+18h]
0x180050c5c  cmp     rax, [rcx+18h]
0x180050c60  jnz     short loc_180050C73
0x180050c62  mov     rdi, [rdi]
0x180050c65  mov     rcx, [rcx]
0x180050c68  jmp     short loc_180050C44
0x180050c6a  test    rcx, rcx
0x180050c6d  jz      loc_180050DBE
0x180050c73  test    edx, edx
0x180050c75  jnz     short loc_180050CD4
0x180050c77  movups  xmm0, xmmword ptr [rsi]
0x180050c7a  lea     rcx, [rsp+930h+var_8F0]
0x180050c7f  movdqu  xmmword ptr [rsp+930h+var_8F0.Data1], xmm0
0x180050c85  call    RasReleaseRoutingDomainAddressPool
0x180050c8a  test    eax, eax
0x180050c8c  jz      short loc_180050CD1
0x180050c8e  cmp     qword ptr cs:xmmword_1800C9740, 0
0x180050c96  jz      short loc_180050CD4
0x180050c98  xor     ecx, ecx
0x180050c9a  lea     rdx, aRasreleaserout; "RasReleaseRoutingDomainAddressPool fail"...
0x180050ca1  mov     word ptr [rbp+830h+var_850], cx
0x180050ca5  mov     r8d, eax
0x180050ca8  lea     rcx, [rbp+830h+var_850]
0x180050cac  call    FormatRRASErrorString
0x180050cb1  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180050cb8  lea     r8, [rbp+830h+var_850]
0x180050cbc  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180050cc3  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180050cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ccf  jmp     short loc_180050CD4
0x180050cd1  xor     r14d, r14d
0x180050cd4  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180050cdb  call    cs:__imp_LeaveCriticalSection
0x180050ce1  movups  xmm0, xmmword ptr [rsi]
0x180050ce4  xor     edx, edx
0x180050ce6  lea     rcx, [rsp+930h+var_8F0]; struct _GUID *
0x180050ceb  movdqu  xmmword ptr [rsp+930h+var_8F0.Data1], xmm0
0x180050cf1  lea     r8d, [rdx+1]
0x180050cf5  call    RasIpv6SrvrStop
0x180050cfa  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180050d01  call    cs:__imp_EnterCriticalSection
0x180050d07  movups  xmm0, xmmword ptr [rsi]
0x180050d0a  lea     rdx, [rsp+930h+var_8F0]
0x180050d0f  mov     rcx, rbx; struct _IPv6PREFIX_POOL *
0x180050d12  movdqu  xmmword ptr [rsp+930h+var_8F0.Data1], xmm0
0x180050d18  call    RasStatv6AddRoutingDomainAddressPool
0x180050d1d  test    eax, eax
0x180050d1f  jz      short loc_180050D64
0x180050d21  cmp     qword ptr cs:xmmword_1800C9740, 0
0x180050d29  jz      short loc_180050D66
0x180050d2b  xor     ecx, ecx
0x180050d2d  lea     rdx, aRasstataddrout; "RasStatAddRoutingDomainv4AddressPool fa"...
0x180050d34  mov     word ptr [rbp+830h+var_850], cx
0x180050d38  mov     r8d, eax
0x180050d3b  lea     rcx, [rbp+830h+var_850]
0x180050d3f  call    FormatRRASErrorString
0x180050d44  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180050d4b  lea     r8, [rbp+830h+var_850]
0x180050d4f  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180050d56  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180050d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d62  jmp     short loc_180050D66
0x180050d64  xor     ebx, ebx
0x180050d66  movups  xmm0, xmmword ptr [rsi]
0x180050d69  lea     rcx, [rsp+930h+var_8F0]; struct _GUID *
0x180050d6e  movdqu  xmmword ptr [rsp+930h+var_8F0.Data1], xmm0
0x180050d74  call    RasIpv6SrvrStart
0x180050d79  test    eax, eax
0x180050d7b  jz      short loc_180050DBE
0x180050d7d  cmp     qword ptr cs:xmmword_1800C9740, 0
0x180050d85  jz      short loc_180050DBE
0x180050d87  xor     ecx, ecx
0x180050d89  lea     rdx, aRassrvrstartFa; "RasSrvrStart failed and returned %d"
0x180050d90  mov     word ptr [rbp+830h+var_850], cx
0x180050d94  mov     r8d, eax
  ... truncated ...
```
