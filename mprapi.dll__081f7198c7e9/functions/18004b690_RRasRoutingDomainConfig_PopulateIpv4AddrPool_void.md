# RRasRoutingDomainConfig::PopulateIpv4AddrPool(void)

- ea: `0x18004b690`
- end: `0x18004bc97`
- name: `?PopulateIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKXZ`
- size: `1543`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180047ff4`
- `0x18004b3ac`

## callees

- `0x18004b690`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `msvcrt!_itow` at `0x18004b9c6`
- `msvcrt!_itow` at `0x18004b9c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b8dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b8dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004b8f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004b8f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b9a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004bc50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004bc5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b9a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004bc50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004bc5f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004b830`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004b830`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b76c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b9e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b76c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b9e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004baa4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004bb78`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004baa4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004bb78`

## string_xrefs

- `0x18004b787`: `%s: RegOpenKeyEx (%s) failed: %d.`
- `0x18004b726`: `RRasRoutingDomainConfig::PopulateIpv4AddrPool`
- `0x18004ba1c`: `RRasRoutingDomainConfig::PopulateIpv4AddrPool`
- `0x18004baf0`: `RRasRoutingDomainConfig::PopulateIpv4AddrPool`
- `0x18004bbc4`: `RRasRoutingDomainConfig::PopulateIpv4AddrPool`
- `0x18004b881`: `%s: No IPv4 address pool configured`
- `0x18004ba23`: `%s: RegOpenKeyEx (%ws) failed: %d.`
- `0x18004baf7`: `%s: Couldn't read value %s in key %ws: %d`
- `0x18004bbcb`: `%s: Couldn't read value %s in key %ws: %d`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::PopulateIpv4AddrPool(RRasRoutingDomainConfig *this)
{
  void (*v2)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  LSTATUS v3; // eax
  const wchar_t *v4; // rdx
  GUID *v5; // r9
  GUID *v6; // r9
  SIZE_T v7; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v9; // rbx
  GUID *v10; // r9
  int v11; // r14d
  DWORD i; // r15d
  LSTATUS v13; // eax
  GUID *v14; // r9
  LSTATUS v15; // eax
  GUID *v16; // r9
  LSTATUS v17; // eax
  GUID *v18; // r9
  unsigned int v19; // ebx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbMaxSubKeyLen; // [rsp+28h] [rbp-D8h]
  LPDWORD lpcbMaxSubKeyLena; // [rsp+28h] [rbp-D8h]
  unsigned int v25; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[4]; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD Type; // [rsp+68h] [rbp-98h] BYREF
  DWORD cSubKeys; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-90h] BYREF
  HKEY v30; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  __int64 v32; // [rsp+88h] [rbp-78h] BYREF
  __int128 v33; // [rsp+90h] [rbp-70h]
  __int128 v34; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  int v36; // [rsp+B8h] [rbp-48h]
  int v37; // [rsp+BCh] [rbp-44h]
  GUID v38; // [rsp+C0h] [rbp-40h] BYREF
  int v39; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v40; // [rsp+D4h] [rbp-2Ch]
  __int128 v41; // [rsp+E4h] [rbp-1Ch]
  int v42; // [rsp+F4h] [rbp-Ch]
  wchar_t Buffer[8]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v44; // [rsp+108h] [rbp+8h]
  int v45; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v46[2044]; // [rsp+124h] [rbp+24h] BYREF

  v25 = 0;
  hKey = 0;
  v30 = 0;
  cSubKeys = 0;
  v45 = 0;
  memset_0(v46, 0, sizeof(v46));
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v33 = 0;
  v32 = 0;
  v34 = 0;
  v35 = 0;
  v36 = -1;
  v37 = 0;
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v32,
      L"RRasRoutingDomainConfig::PopulateIpv4AddrPool",
      &v25,
      v2,
      (struct _GUID *)((char *)this + 516));
  v3 = RegOpenKeyExW(*((HKEY *)this + 103), L"Ipv4AddrPool", 0, 0x20019u, &hKey);
  v25 = v3;
  if ( v3 )
  {
    if ( !(_QWORD)xmmword_180078C60 )
      goto LABEL_50;
    v4 = L"%s: RegOpenKeyEx (%s) failed: %d.";
LABEL_6:
    LODWORD(phkResult) = v3;
    LOWORD(v39) = 0;
    v38 = GUID_NULL;
    LOWORD(v45) = 0;
    FormatRRASErrorString(&v45, v4, L"RRasRoutingDomainConfig::PopulateIpv4AddrPool", L"Ipv4", phkResult);
    v5 = &v38;
    if ( this != (RRasRoutingDomainConfig *)-516LL )
      v5 = (GUID *)((char *)this + 516);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180078C60,
      &v45,
      v5,
      0,
      &v39);
    goto LABEL_50;
  }
  v3 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v25 = v3;
  if ( v3 )
  {
    if ( !(_QWORD)xmmword_180078C60 )
      goto LABEL_50;
    v4 = L"%s: RegQueryInfoKey (%s) failed: %d.";
    goto LABEL_6;
  }
  if ( cSubKeys )
  {
    v7 = 8LL * cSubKeys;
    ProcessHeap = GetProcessHeap();
    v9 = HeapAlloc(ProcessHeap, 8u, v7);
    if ( v9 )
    {
      v11 = 0;
      for ( i = 0; i < cSubKeys; ++i )
      {
        *(_OWORD *)Buffer = 0;
        v44 = 0;
        cbData = 0;
        *(_DWORD *)Data = 0;
        Type = 0;
        if ( v30 )
          RegCloseKey(v30);
        v30 = 0;
        v9[v11] = 0;
        _itow(i, Buffer, 10);
        v13 = RegOpenKeyExW(hKey, Buffer, 0, 0x20019u, &v30);
        v25 = v13;
        if ( v13 )
        {
          if ( (_QWORD)xmmword_180078C60 )
          {
            LOWORD(v45) = 0;
            v38 = GUID_NULL;
            LOWORD(v39) = 0;
            LODWORD(phkResulta) = v13;
            FormatRRASErrorString(
              &v45,
              L"%s: RegOpenKeyEx (%ws) failed: %d.",
              L"RRasRoutingDomainConfig::PopulateIpv4AddrPool",
              Buffer,
              phkResulta);
            v14 = &v38;
            if ( this != (RRasRoutingDomainConfig *)-516LL )
              v14 = (GUID *)((char *)this + 516);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
              gCfgStoreEtwContext,
              xmmword_180078C60,
              &v45,
              v14,
              0,
              &v39);
          }
          v25 = 0;
        }
        else
        {
          cbData = 4;
          v15 = RegQueryValueExW(v30, L"From", 0, &Type, Data, &cbData);
          v25 = v15;
          if ( v15 || Type != 4 )
          {
            if ( (_QWORD)xmmword_180078C60 )
            {
              LOWORD(v45) = 0;
              v38 = GUID_NULL;
              LOWORD(v39) = 0;
              LODWORD(lpcbMaxSubKeyLen) = v15;
              FormatRRASErrorString(
                &v45,
                L"%s: Couldn't read value %s in key %ws: %d",
                L"RRasRoutingDomainConfig::PopulateIpv4AddrPool",
                L"From",
                Buffer,
                lpcbMaxSubKeyLen);
              v16 = &v38;
              if ( this != (RRasRoutingDomainConfig *)-516LL )
                v16 = (GUID *)((char *)this + 516);
              ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
                gCfgStoreEtwContext,
                xmmword_180078C60,
                &v45,
                v16,
                0,
                &v39);
            }
            v25 = 0;
          }
          LODWORD(v9[v11]) = *(_DWORD *)Data;
          *(_DWORD *)Data = 0;
          v17 = RegQueryValueExW(v30, L"To", 0, &Type, Data, &cbData);
          v25 = v17;
          if ( v17 || Type != 4 )
          {
            if ( (_QWORD)xmmword_180078C60 )
            {
              LOWORD(v45) = 0;
              v38 = GUID_NULL;
              LOWORD(v39) = 0;
              LODWORD(lpcbMaxSubKeyLena) = v17;
              FormatRRASErrorString(
                &v45,
                L"%s: Couldn't read value %s in key %ws: %d",
                L"RRasRoutingDomainConfig::PopulateIpv4AddrPool",
                L"To",
                Buffer,
                lpcbMaxSubKeyLena);
              v18 = &v38;
              if ( this != (RRasRoutingDomainConfig *)-516LL )
                v18 = (GUID *)((char *)this + 516);
              ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
                gCfgStoreEtwContext,
                xmmword_180078C60,
                &v45,
                v18,
                0,
                &v39);
            }
            v25 = 0;
          }
          HIDWORD(v9[v11++]) = *(_DWORD *)Data;
        }
      }
      *((_DWORD *)this + 146) = 0;
      *((_DWORD *)this + 147) = v11;
      *((_QWORD *)this + 74) = v9;
    }
    else
    {
      if ( (_QWORD)xmmword_180078C60 )
      {
        LOWORD(v45) = 0;
        v38 = GUID_NULL;
        LOWORD(v39) = 0;
        FormatRRASErrorString(&v45, L"%s: Malloc failed.", L"RRasRoutingDomainConfig::PopulateIpv4AddrPool");
        v10 = &v38;
        if ( this != (RRasRoutingDomainConfig *)-516LL )
          v10 = (GUID *)((char *)this + 516);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_180078C60,
          &v45,
          v10,
          0,
          &v39);
      }
      v25 = 8;
    }
  }
  else
  {
    if ( (_QWORD)xmmword_180078C60 )
    {
      LOWORD(v45) = 0;
      v38 = GUID_NULL;
      LOWORD(v39) = 0;
      FormatRRASErrorString(
        &v45,
        L"%s: No IPv4 address pool configured",
        L"RRasRoutingDomainConfig::PopulateIpv4AddrPool");
      v6 = &v38;
      if ( this != (RRasRoutingDomainConfig *)-516LL )
        v6 = (GUID *)((char *)this + 516);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C60,
        &v45,
        v6,
        0,
        &v39);
    }
    v25 = 1168;
  }
LABEL_50:
  if ( v30 )
    RegCloseKey(v30);
  if ( hKey )
    RegCloseKey(hKey);
  v19 = v25;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v32);
  return v19;
}

```

## disassembly

```asm
0x18004b690  push    rbp
0x18004b692  push    rbx
0x18004b693  push    rsi
0x18004b694  push    rdi
0x18004b695  push    r12
0x18004b697  push    r13
0x18004b699  push    r14
0x18004b69b  push    r15
0x18004b69d  lea     rbp, [rsp-838h]
0x18004b6a5  sub     rsp, 938h
0x18004b6ac  mov     rax, cs:__security_cookie
0x18004b6b3  xor     rax, rsp
0x18004b6b6  mov     [rbp+870h+var_50], rax
0x18004b6bd  mov     rsi, rcx
0x18004b6c0  xor     r13d, r13d
0x18004b6c3  mov     [rsp+970h+var_910], r13d
0x18004b6c8  mov     [rbp+870h+hKey], r13
0x18004b6cc  mov     [rsp+970h+var_8F8], r13
0x18004b6d1  mov     [rsp+970h+cSubKeys], r13d
0x18004b6d6  mov     [rbp+870h+var_850], r13d
0x18004b6da  xor     edx, edx; Val
0x18004b6dc  mov     r8d, 7FCh; Size
0x18004b6e2  lea     rcx, [rbp+870h+var_84C]; void *
0x18004b6e6  call    memset_0
0x18004b6eb  mov     [rbp+870h+var_8A0], r13d
0x18004b6ef  xorps   xmm0, xmm0
0x18004b6f2  xor     eax, eax
0x18004b6f4  movups  [rbp+870h+var_89C], xmm0
0x18004b6f8  movups  [rbp+870h+var_88C], xmm0
0x18004b6fc  mov     [rbp+870h+var_87C], eax
0x18004b6ff  movdqu  [rbp+870h+var_8E0], xmm0
0x18004b704  mov     [rbp+870h+var_8E8], r13
0x18004b708  xorps   xmm1, xmm1
0x18004b70b  movdqu  [rbp+870h+var_8D0], xmm1
0x18004b710  mov     [rbp+870h+var_8C0], r13
0x18004b714  mov     [rbp+870h+var_8B8], 0FFFFFFFFh
0x18004b71b  mov     [rbp+870h+var_8B4], r13d
0x18004b71f  lea     rdi, [rsi+204h]
0x18004b726  lea     r14, aRrasroutingdom_28; "RRasRoutingDomainConfig::PopulateIpv4Ad"...
0x18004b72d  cmp     qword ptr cs:xmmword_180078C60+8, r13
0x18004b734  jz      short loc_18004B74C
0x18004b736  mov     [rsp+970h+phkResult], rdi; struct _GUID *
0x18004b73b  lea     r8, [rsp+970h+var_910]; unsigned int *
0x18004b740  mov     rdx, r14; unsigned __int16 *
0x18004b743  lea     rcx, [rbp+870h+var_8E8]; this
0x18004b747  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18004b74c  lea     rax, [rbp+870h+hKey]
0x18004b750  mov     [rsp+970h+phkResult], rax; phkResult
0x18004b755  mov     r9d, 20019h; samDesired
0x18004b75b  xor     r8d, r8d; ulOptions
0x18004b75e  lea     rdx, aIpv4addrpool; "Ipv4AddrPool"
0x18004b765  mov     rcx, [rsi+338h]; hKey
0x18004b76c  call    cs:__imp_RegOpenKeyExW
0x18004b772  mov     [rsp+970h+var_910], eax
0x18004b776  test    eax, eax
0x18004b778  jz      short loc_18004B7F7
0x18004b77a  cmp     qword ptr cs:xmmword_180078C60, r13
0x18004b781  jz      loc_18004BC46
0x18004b787  lea     rdx, aSRegopenkeyexS_0; "%s: RegOpenKeyEx (%s) failed: %d."
0x18004b78e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004b795  mov     r8, r14
0x18004b798  lea     r9, aIpv4; "Ipv4"
0x18004b79f  mov     dword ptr [rsp+970h+phkResult], eax
0x18004b7a3  mov     word ptr [rbp+870h+var_8A0], r13w
0x18004b7a8  movdqu  [rbp+870h+var_8B0], xmm0
0x18004b7ad  mov     word ptr [rbp+870h+var_850], r13w
0x18004b7b2  lea     rcx, [rbp+870h+var_850]
0x18004b7b6  call    FormatRRASErrorString
0x18004b7bb  lea     r9, [rbp+870h+var_8B0]
0x18004b7bf  test    rdi, rdi
0x18004b7c2  cmovnz  r9, rdi
0x18004b7c6  lea     rax, [rbp+870h+var_8A0]
0x18004b7ca  mov     [rsp+970h+lpcbMaxSubKeyLen], rax
0x18004b7cf  mov     [rsp+970h+phkResult], r13
0x18004b7d4  lea     r8, [rbp+870h+var_850]
0x18004b7d8  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004b7df  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004b7e6  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004b7ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b7f2  jmp     loc_18004BC46
0x18004b7f7  mov     [rsp+970h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18004b7fc  mov     [rsp+970h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18004b801  mov     [rsp+970h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18004b806  mov     [rsp+970h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18004b80b  mov     [rsp+970h+lpcValues], r13; lpcValues
0x18004b810  mov     [rsp+970h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18004b815  mov     [rsp+970h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x18004b81a  lea     rax, [rsp+970h+cSubKeys]
0x18004b81f  mov     [rsp+970h+phkResult], rax; lpcSubKeys
0x18004b824  xor     r9d, r9d; lpReserved
0x18004b827  xor     r8d, r8d; lpcchClass
0x18004b82a  xor     edx, edx; lpClass
0x18004b82c  mov     rcx, [rbp+870h+hKey]; hKey
0x18004b830  call    cs:__imp_RegQueryInfoKeyW
0x18004b836  mov     [rsp+970h+var_910], eax
0x18004b83a  test    eax, eax
0x18004b83c  jz      short loc_18004B857
0x18004b83e  cmp     qword ptr cs:xmmword_180078C60, r13
0x18004b845  jz      loc_18004BC46
0x18004b84b  lea     rdx, aSRegqueryinfok; "%s: RegQueryInfoKey (%s) failed: %d."
0x18004b852  jmp     loc_18004B78E
0x18004b857  mov     eax, [rsp+970h+cSubKeys]
0x18004b85b  test    eax, eax
0x18004b85d  jnz     short loc_18004B8D5
0x18004b85f  cmp     qword ptr cs:xmmword_180078C60, r13
0x18004b866  jz      short loc_18004B8C8
0x18004b868  mov     word ptr [rbp+870h+var_850], r13w
0x18004b86d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004b874  movdqu  [rbp+870h+var_8B0], xmm0
0x18004b879  mov     word ptr [rbp+870h+var_8A0], r13w
0x18004b87e  mov     r8, r14
0x18004b881  lea     rdx, aSNoIpv4Address; "%s: No IPv4 address pool configured"
0x18004b888  lea     rcx, [rbp+870h+var_850]
0x18004b88c  call    FormatRRASErrorString
0x18004b891  lea     r9, [rbp+870h+var_8B0]
0x18004b895  test    rdi, rdi
0x18004b898  cmovnz  r9, rdi
0x18004b89c  lea     rax, [rbp+870h+var_8A0]
0x18004b8a0  mov     [rsp+970h+lpcbMaxSubKeyLen], rax
0x18004b8a5  mov     [rsp+970h+phkResult], r13
0x18004b8aa  lea     r8, [rbp+870h+var_850]
0x18004b8ae  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004b8b5  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004b8bc  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004b8c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b8c8  mov     [rsp+970h+var_910], 490h
0x18004b8d0  jmp     loc_18004BC46
0x18004b8d5  mov     rbx, rax
0x18004b8d8  shl     rbx, 3
0x18004b8dc  call    cs:__imp_GetProcessHeap
0x18004b8e2  mov     r8, rbx; dwBytes
0x18004b8e5  mov     r15d, 8
0x18004b8eb  mov     edx, r15d; dwFlags
0x18004b8ee  mov     rcx, rax; hHeap
0x18004b8f1  call    cs:__imp_HeapAlloc
0x18004b8f7  mov     rbx, rax
0x18004b8fa  test    rax, rax
0x18004b8fd  jnz     short loc_18004B972
0x18004b8ff  cmp     qword ptr cs:xmmword_180078C60, r13
0x18004b906  jz      short loc_18004B968
0x18004b908  mov     word ptr [rbp+870h+var_850], r13w
0x18004b90d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004b914  movdqu  [rbp+870h+var_8B0], xmm0
0x18004b919  mov     word ptr [rbp+870h+var_8A0], r13w
0x18004b91e  mov     r8, r14
0x18004b921  lea     rdx, aSMallocFailed; "%s: Malloc failed."
0x18004b928  lea     rcx, [rbp+870h+var_850]
0x18004b92c  call    FormatRRASErrorString
0x18004b931  lea     r9, [rbp+870h+var_8B0]
0x18004b935  test    rdi, rdi
0x18004b938  cmovnz  r9, rdi
0x18004b93c  lea     rax, [rbp+870h+var_8A0]
0x18004b940  mov     [rsp+970h+lpcbMaxSubKeyLen], rax
0x18004b945  mov     [rsp+970h+phkResult], r13
0x18004b94a  lea     r8, [rbp+870h+var_850]
0x18004b94e  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004b955  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004b95c  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004b963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b968  mov     [rsp+970h+var_910], r15d
0x18004b96d  jmp     loc_18004BC46
0x18004b972  mov     r14d, r13d
0x18004b975  mov     r15d, r13d
0x18004b978  cmp     [rsp+970h+cSubKeys], r13d
0x18004b97d  jbe     loc_18004BC31
0x18004b983  xorps   xmm0, xmm0
0x18004b986  movups  xmmword ptr [rbp+870h+Buffer], xmm0
0x18004b98a  movups  [rbp+870h+var_868], xmm0
0x18004b98e  mov     [rsp+970h+cbData], r13d
0x18004b993  mov     dword ptr [rsp+970h+Data], r13d
0x18004b998  mov     [rsp+970h+Type], r13d
0x18004b99d  mov     rcx, [rsp+970h+var_8F8]; hKey
0x18004b9a2  test    rcx, rcx
0x18004b9a5  jz      short loc_18004B9AD
0x18004b9a7  call    cs:__imp_RegCloseKey
0x18004b9ad  mov     [rsp+970h+var_8F8], r13
0x18004b9b2  mov     r12d, r14d
0x18004b9b5  xor     eax, eax
0x18004b9b7  mov     [rbx+r12*8], rax
0x18004b9bb  lea     r8d, [rax+0Ah]; Radix
0x18004b9bf  lea     rdx, [rbp+870h+Buffer]; Buffer
0x18004b9c3  mov     ecx, r15d; Value
0x18004b9c6  call    cs:__imp__itow
0x18004b9cc  lea     rax, [rsp+970h+var_8F8]
0x18004b9d1  mov     [rsp+970h+phkResult], rax; phkResult
0x18004b9d6  mov     r9d, 20019h; samDesired
0x18004b9dc  xor     r8d, r8d; ulOptions
0x18004b9df  lea     rdx, [rbp+870h+Buffer]; lpSubKey
0x18004b9e3  mov     rcx, [rbp+870h+hKey]; hKey
0x18004b9e7  call    cs:__imp_RegOpenKeyExW
0x18004b9ed  mov     [rsp+970h+var_910], eax
0x18004b9f1  test    eax, eax
0x18004b9f3  jz      short loc_18004BA74
0x18004b9f5  cmp     qword ptr cs:xmmword_180078C60, r13
0x18004b9fc  jz      short loc_18004BA6A
0x18004b9fe  mov     word ptr [rbp+870h+var_850], r13w
0x18004ba03  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004ba0a  movdqu  [rbp+870h+var_8B0], xmm0
0x18004ba0f  mov     word ptr [rbp+870h+var_8A0], r13w
0x18004ba14  mov     dword ptr [rsp+970h+phkResult], eax
0x18004ba18  lea     r9, [rbp+870h+Buffer]
0x18004ba1c  lea     r8, aRrasroutingdom_28; "RRasRoutingDomainConfig::PopulateIpv4Ad"...
0x18004ba23  lea     rdx, aSRegopenkeyexW; "%s: RegOpenKeyEx (%ws) failed: %d."
0x18004ba2a  lea     rcx, [rbp+870h+var_850]
0x18004ba2e  call    FormatRRASErrorString
0x18004ba33  lea     r9, [rbp+870h+var_8B0]
0x18004ba37  test    rdi, rdi
0x18004ba3a  cmovnz  r9, rdi
0x18004ba3e  lea     rax, [rbp+870h+var_8A0]
0x18004ba42  mov     [rsp+970h+lpcbMaxSubKeyLen], rax
0x18004ba47  mov     [rsp+970h+phkResult], r13
0x18004ba4c  lea     r8, [rbp+870h+var_850]
0x18004ba50  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004ba57  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004ba5e  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004ba65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ba6a  mov     [rsp+970h+var_910], r13d
0x18004ba6f  jmp     loc_18004BC23
0x18004ba74  mov     [rsp+970h+cbData], 4
0x18004ba7c  lea     rax, [rsp+970h+cbData]
0x18004ba81  mov     [rsp+970h+lpcbMaxSubKeyLen], rax; lpcbData
0x18004ba86  lea     rax, [rsp+970h+Data]
0x18004ba8b  mov     [rsp+970h+phkResult], rax; lpData
0x18004ba90  lea     r9, [rsp+970h+Type]; lpType
0x18004ba95  xor     r8d, r8d; lpReserved
0x18004ba98  lea     rdx, aFrom; "From"
0x18004ba9f  mov     rcx, [rsp+970h+var_8F8]; hKey
0x18004baa4  call    cs:__imp_RegQueryValueExW
0x18004baaa  mov     [rsp+970h+var_910], eax
0x18004baae  test    eax, eax
0x18004bab0  jnz     short loc_18004BABD
0x18004bab2  cmp     [rsp+970h+Type], 4
0x18004bab7  jz      loc_18004BB43
0x18004babd  cmp     qword ptr cs:xmmword_180078C60, r13
0x18004bac4  jz      short loc_18004BB3E
0x18004bac6  mov     word ptr [rbp+870h+var_850], r13w
0x18004bacb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004bad2  movdqu  [rbp+870h+var_8B0], xmm0
0x18004bad7  mov     word ptr [rbp+870h+var_8A0], r13w
0x18004badc  mov     dword ptr [rsp+970h+lpcbMaxSubKeyLen], eax
0x18004bae0  lea     rax, [rbp+870h+Buffer]
0x18004bae4  mov     [rsp+970h+phkResult], rax
0x18004bae9  lea     r9, aFrom; "From"
0x18004baf0  lea     r8, aRrasroutingdom_28; "RRasRoutingDomainConfig::PopulateIpv4Ad"...
0x18004baf7  lea     rdx, aSCouldnTReadVa_0; "%s: Couldn't read value %s in key %ws: "...
0x18004bafe  lea     rcx, [rbp+870h+var_850]
0x18004bb02  call    FormatRRASErrorString
0x18004bb07  lea     r9, [rbp+870h+var_8B0]
0x18004bb0b  test    rdi, rdi
0x18004bb0e  cmovnz  r9, rdi
0x18004bb12  lea     rax, [rbp+870h+var_8A0]
0x18004bb16  mov     [rsp+970h+lpcbMaxSubKeyLen], rax
0x18004bb1b  mov     [rsp+970h+phkResult], r13
0x18004bb20  lea     r8, [rbp+870h+var_850]
0x18004bb24  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004bb2b  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004bb32  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004bb39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bb3e  mov     [rsp+970h+var_910], r13d
0x18004bb43  mov     eax, dword ptr [rsp+970h+Data]
0x18004bb47  mov     [rbx+r12*8], eax
0x18004bb4b  mov     dword ptr [rsp+970h+Data], r13d
0x18004bb50  lea     rax, [rsp+970h+cbData]
0x18004bb55  mov     [rsp+970h+lpcbMaxSubKeyLen], rax; lpcbData
0x18004bb5a  lea     rax, [rsp+970h+Data]
0x18004bb5f  mov     [rsp+970h+phkResult], rax; lpData
0x18004bb64  lea     r9, [rsp+970h+Type]; lpType
0x18004bb69  xor     r8d, r8d; lpReserved
0x18004bb6c  lea     rdx, aTo; "To"
0x18004bb73  mov     rcx, [rsp+970h+var_8F8]; hKey
0x18004bb78  call    cs:__imp_RegQueryValueExW
0x18004bb7e  mov     [rsp+970h+var_910], eax
0x18004bb82  test    eax, eax
0x18004bb84  jnz     short loc_18004BB91
0x18004bb86  cmp     [rsp+970h+Type], 4
0x18004bb8b  jz      loc_18004BC17
0x18004bb91  cmp     qword ptr cs:xmmword_180078C60, r13
0x18004bb98  jz      short loc_18004BC12
0x18004bb9a  mov     word ptr [rbp+870h+var_850], r13w
0x18004bb9f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004bba6  movdqu  [rbp+870h+var_8B0], xmm0
0x18004bbab  mov     word ptr [rbp+870h+var_8A0], r13w
0x18004bbb0  mov     dword ptr [rsp+970h+lpcbMaxSubKeyLen], eax
0x18004bbb4  lea     rax, [rbp+870h+Buffer]
0x18004bbb8  mov     [rsp+970h+phkResult], rax
0x18004bbbd  lea     r9, aTo; "To"
0x18004bbc4  lea     r8, aRrasroutingdom_28; "RRasRoutingDomainConfig::PopulateIpv4Ad"...
0x18004bbcb  lea     rdx, aSCouldnTReadVa_0; "%s: Couldn't read value %s in key %ws: "...
0x18004bbd2  lea     rcx, [rbp+870h+var_850]
0x18004bbd6  call    FormatRRASErrorString
0x18004bbdb  lea     r9, [rbp+870h+var_8B0]
0x18004bbdf  test    rdi, rdi
0x18004bbe2  cmovnz  r9, rdi
0x18004bbe6  lea     rax, [rbp+870h+var_8A0]
0x18004bbea  mov     [rsp+970h+lpcbMaxSubKeyLen], rax
0x18004bbef  mov     [rsp+970h+phkResult], r13
0x18004bbf4  lea     r8, [rbp+870h+var_850]
0x18004bbf8  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004bbff  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004bc06  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
  ... truncated ...
```
