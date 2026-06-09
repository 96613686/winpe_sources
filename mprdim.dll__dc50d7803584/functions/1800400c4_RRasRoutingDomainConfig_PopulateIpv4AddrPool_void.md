# RRasRoutingDomainConfig::PopulateIpv4AddrPool(void)

- ea: `0x1800400c4`
- end: `0x1800406c5`
- name: `?PopulateIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKXZ`
- size: `1537`
- prototype: `unsigned int __fastcall(RRasRoutingDomainConfig *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18003c810`
- `0x18003fde0`

## callees

- `0x1800400c4`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!_itow` at `0x1800403fa`
- `msvcrt!_itow` at `0x1800403fa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180040325`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180040325`
- `KERNEL32!GetProcessHeap` at `0x180040310`
- `KERNEL32!GetProcessHeap` at `0x180040310`
- `ADVAPI32!RegOpenKeyExW` at `0x1800401a0`
- `ADVAPI32!RegOpenKeyExW` at `0x18004041b`
- `ADVAPI32!RegOpenKeyExW` at `0x1800401a0`
- `ADVAPI32!RegOpenKeyExW` at `0x18004041b`
- `ADVAPI32!RegCloseKey` at `0x1800403db`
- `ADVAPI32!RegCloseKey` at `0x18004067e`
- `ADVAPI32!RegCloseKey` at `0x18004068d`
- `ADVAPI32!RegCloseKey` at `0x1800403db`
- `ADVAPI32!RegCloseKey` at `0x18004067e`
- `ADVAPI32!RegCloseKey` at `0x18004068d`
- `ADVAPI32!RegQueryValueExW` at `0x1800404d8`
- `ADVAPI32!RegQueryValueExW` at `0x1800405ac`
- `ADVAPI32!RegQueryValueExW` at `0x1800404d8`
- `ADVAPI32!RegQueryValueExW` at `0x1800405ac`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180040264`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180040264`

## string_xrefs

- `0x1800401bb`: `%s: RegOpenKeyEx (%s) failed: %d.`
- `0x18004015a`: `RRasRoutingDomainConfig::PopulateIpv4AddrPool`
- `0x180040450`: `RRasRoutingDomainConfig::PopulateIpv4AddrPool`
- `0x180040524`: `RRasRoutingDomainConfig::PopulateIpv4AddrPool`
- `0x1800405f8`: `RRasRoutingDomainConfig::PopulateIpv4AddrPool`
- `0x1800402b5`: `%s: No IPv4 address pool configured`
- `0x180040457`: `%s: RegOpenKeyEx (%ws) failed: %d.`
- `0x18004052b`: `%s: Couldn't read value %s in key %ws: %d`
- `0x1800405ff`: `%s: Couldn't read value %s in key %ws: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  unsigned __int16 *lpcbMaxSubKeyLen; // [rsp+28h] [rbp-D8h]
  LPDWORD lpcbMaxSubKeyLena; // [rsp+28h] [rbp-D8h]
  LPDWORD lpcbMaxSubKeyLenb; // [rsp+28h] [rbp-D8h]
  unsigned int lpcbMaxClassLen; // [rsp+30h] [rbp-D0h]
  unsigned int v27; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[4]; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD Type; // [rsp+68h] [rbp-98h] BYREF
  DWORD cSubKeys; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-90h] BYREF
  HKEY v32; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  __int64 v34; // [rsp+88h] [rbp-78h] BYREF
  __int128 v35; // [rsp+90h] [rbp-70h]
  __int128 v36; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  int v38; // [rsp+B8h] [rbp-48h]
  int v39; // [rsp+BCh] [rbp-44h]
  GUID v40; // [rsp+C0h] [rbp-40h] BYREF
  int v41; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v42; // [rsp+D4h] [rbp-2Ch]
  __int128 v43; // [rsp+E4h] [rbp-1Ch]
  int v44; // [rsp+F4h] [rbp-Ch]
  wchar_t Buffer[8]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v46; // [rsp+108h] [rbp+8h]
  int v47; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v48[2044]; // [rsp+124h] [rbp+24h] BYREF

  v27 = 0;
  hKey = 0;
  v32 = 0;
  cSubKeys = 0;
  v47 = 0;
  memset_0(v48, 0, sizeof(v48));
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v35 = 0;
  v34 = 0;
  v36 = 0;
  v37 = 0;
  v38 = -1;
  v39 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v34,
      L"RRasRoutingDomainConfig::PopulateIpv4AddrPool",
      &v27,
      v2,
      (struct _GUID *)((char *)this + 516),
      lpcbMaxSubKeyLen,
      lpcbMaxClassLen);
  v3 = RegOpenKeyExW(*((HKEY *)this + 103), L"Ipv4AddrPool", 0, 0x20019u, &hKey);
  v27 = v3;
  if ( v3 )
  {
    if ( !(_QWORD)xmmword_1800710A0 )
      goto LABEL_51;
    v4 = L"%s: RegOpenKeyEx (%s) failed: %d.";
LABEL_6:
    LODWORD(phkResult) = v3;
    LOWORD(v41) = 0;
    v40 = GUID_NULL;
    LOWORD(v47) = 0;
    FormatRRASErrorString(&v47, v4, L"RRasRoutingDomainConfig::PopulateIpv4AddrPool", L"Ipv4", phkResult);
    v5 = &v40;
    if ( this != (RRasRoutingDomainConfig *)-516LL )
      v5 = (GUID *)((char *)this + 516);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_1800710A0,
      &v47,
      v5,
      0,
      &v41);
    goto LABEL_51;
  }
  v3 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v27 = v3;
  if ( v3 )
  {
    if ( !(_QWORD)xmmword_1800710A0 )
      goto LABEL_51;
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
        v46 = 0;
        cbData = 0;
        *(_DWORD *)Data = 0;
        Type = 0;
        if ( v32 )
          RegCloseKey(v32);
        v32 = 0;
        v9[v11] = 0;
        _itow(i, Buffer, 10);
        v13 = RegOpenKeyExW(hKey, Buffer, 0, 0x20019u, &v32);
        v27 = v13;
        if ( v13 )
        {
          if ( (_QWORD)xmmword_1800710A0 )
          {
            LOWORD(v47) = 0;
            v40 = GUID_NULL;
            LOWORD(v41) = 0;
            LODWORD(phkResulta) = v13;
            FormatRRASErrorString(
              &v47,
              L"%s: RegOpenKeyEx (%ws) failed: %d.",
              L"RRasRoutingDomainConfig::PopulateIpv4AddrPool",
              Buffer,
              phkResulta);
            v14 = &v40;
            if ( this != (RRasRoutingDomainConfig *)-516LL )
              v14 = (GUID *)((char *)this + 516);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
              gCfgStoreEtwContext,
              xmmword_1800710A0,
              &v47,
              v14,
              0,
              &v41);
          }
          v27 = 0;
        }
        else
        {
          cbData = 4;
          v15 = RegQueryValueExW(v32, L"From", 0, &Type, Data, &cbData);
          v27 = v15;
          if ( v15 || Type != 4 )
          {
            if ( (_QWORD)xmmword_1800710A0 )
            {
              LOWORD(v47) = 0;
              v40 = GUID_NULL;
              LOWORD(v41) = 0;
              LODWORD(lpcbMaxSubKeyLena) = v15;
              FormatRRASErrorString(
                &v47,
                L"%s: Couldn't read value %s in key %ws: %d",
                L"RRasRoutingDomainConfig::PopulateIpv4AddrPool",
                L"From",
                Buffer,
                lpcbMaxSubKeyLena);
              v16 = &v40;
              if ( this != (RRasRoutingDomainConfig *)-516LL )
                v16 = (GUID *)((char *)this + 516);
              ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
                gCfgStoreEtwContext,
                xmmword_1800710A0,
                &v47,
                v16,
                0,
                &v41);
            }
            v27 = 0;
          }
          LODWORD(v9[v11]) = *(_DWORD *)Data;
          *(_DWORD *)Data = 0;
          v17 = RegQueryValueExW(v32, L"To", 0, &Type, Data, &cbData);
          v27 = v17;
          if ( v17 || Type != 4 )
          {
            if ( (_QWORD)xmmword_1800710A0 )
            {
              LOWORD(v47) = 0;
              v40 = GUID_NULL;
              LOWORD(v41) = 0;
              LODWORD(lpcbMaxSubKeyLenb) = v17;
              FormatRRASErrorString(
                &v47,
                L"%s: Couldn't read value %s in key %ws: %d",
                L"RRasRoutingDomainConfig::PopulateIpv4AddrPool",
                L"To",
                Buffer,
                lpcbMaxSubKeyLenb);
              v18 = &v40;
              if ( this != (RRasRoutingDomainConfig *)-516LL )
                v18 = (GUID *)((char *)this + 516);
              ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
                gCfgStoreEtwContext,
                xmmword_1800710A0,
                &v47,
                v18,
                0,
                &v41);
            }
            v27 = 0;
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
      if ( (_QWORD)xmmword_1800710A0 )
      {
        LOWORD(v47) = 0;
        v40 = GUID_NULL;
        LOWORD(v41) = 0;
        FormatRRASErrorString(&v47, L"%s: Malloc failed.", L"RRasRoutingDomainConfig::PopulateIpv4AddrPool");
        v10 = &v40;
        if ( this != (RRasRoutingDomainConfig *)-516LL )
          v10 = (GUID *)((char *)this + 516);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_1800710A0,
          &v47,
          v10,
          0,
          &v41);
      }
      v27 = 8;
    }
  }
  else
  {
    if ( (_QWORD)xmmword_1800710A0 )
    {
      LOWORD(v47) = 0;
      v40 = GUID_NULL;
      LOWORD(v41) = 0;
      FormatRRASErrorString(
        &v47,
        L"%s: No IPv4 address pool configured",
        L"RRasRoutingDomainConfig::PopulateIpv4AddrPool");
      v6 = &v40;
      if ( this != (RRasRoutingDomainConfig *)-516LL )
        v6 = (GUID *)((char *)this + 516);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_1800710A0,
        &v47,
        v6,
        0,
        &v41);
    }
    v27 = 1168;
  }
LABEL_51:
  if ( v32 )
    RegCloseKey(v32);
  if ( hKey )
    RegCloseKey(hKey);
  v19 = v27;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v34);
  return v19;
}

```

## disassembly

```asm
0x1800400c4  push    rbp
0x1800400c6  push    rbx
0x1800400c7  push    rsi
0x1800400c8  push    rdi
0x1800400c9  push    r12
0x1800400cb  push    r13
0x1800400cd  push    r14
0x1800400cf  push    r15
0x1800400d1  lea     rbp, [rsp-838h]
0x1800400d9  sub     rsp, 938h
0x1800400e0  mov     rax, cs:__security_cookie
0x1800400e7  xor     rax, rsp
0x1800400ea  mov     [rbp+870h+var_50], rax
0x1800400f1  mov     rsi, rcx
0x1800400f4  xor     r13d, r13d
0x1800400f7  mov     [rsp+970h+var_910], r13d
0x1800400fc  mov     [rbp+870h+hKey], r13
0x180040100  mov     [rsp+970h+var_8F8], r13
0x180040105  mov     [rsp+970h+cSubKeys], r13d
0x18004010a  mov     [rbp+870h+var_850], r13d
0x18004010e  xor     edx, edx; Val
0x180040110  mov     r8d, 7FCh; Size
0x180040116  lea     rcx, [rbp+870h+var_84C]; void *
0x18004011a  call    memset_0
0x18004011f  mov     [rbp+870h+var_8A0], r13d
0x180040123  xorps   xmm0, xmm0
0x180040126  xor     eax, eax
0x180040128  movups  [rbp+870h+var_89C], xmm0
0x18004012c  movups  [rbp+870h+var_88C], xmm0
0x180040130  mov     [rbp+870h+var_87C], eax
0x180040133  movdqu  [rbp+870h+var_8E0], xmm0
0x180040138  mov     [rbp+870h+var_8E8], r13
0x18004013c  xorps   xmm1, xmm1
0x18004013f  movdqu  [rbp+870h+var_8D0], xmm1
0x180040144  mov     [rbp+870h+var_8C0], r13
0x180040148  mov     [rbp+870h+var_8B8], 0FFFFFFFFh
0x18004014f  mov     [rbp+870h+var_8B4], r13d
0x180040153  lea     rdi, [rsi+204h]
0x18004015a  lea     r14, aRrasroutingdom_29; "RRasRoutingDomainConfig::PopulateIpv4Ad"...
0x180040161  cmp     qword ptr cs:xmmword_1800710A0+8, r13
0x180040168  jz      short loc_180040180
0x18004016a  mov     [rsp+970h+phkResult], rdi; struct _GUID *
0x18004016f  lea     r8, [rsp+970h+var_910]; unsigned int *
0x180040174  mov     rdx, r14; unsigned __int16 *
0x180040177  lea     rcx, [rbp+870h+var_8E8]; this
0x18004017b  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180040180  lea     rax, [rbp+870h+hKey]
0x180040184  mov     [rsp+970h+phkResult], rax; phkResult
0x180040189  mov     r9d, 20019h; samDesired
0x18004018f  xor     r8d, r8d; ulOptions
0x180040192  lea     rdx, aIpv4addrpool; "Ipv4AddrPool"
0x180040199  mov     rcx, [rsi+338h]; hKey
0x1800401a0  call    cs:__imp_RegOpenKeyExW
0x1800401a6  mov     [rsp+970h+var_910], eax
0x1800401aa  test    eax, eax
0x1800401ac  jz      short loc_18004022B
0x1800401ae  cmp     qword ptr cs:xmmword_1800710A0, r13
0x1800401b5  jz      loc_180040674
0x1800401bb  lea     rdx, aSRegopenkeyexS_0; "%s: RegOpenKeyEx (%s) failed: %d."
0x1800401c2  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800401c9  mov     r8, r14
0x1800401cc  lea     r9, aIpv4; "Ipv4"
0x1800401d3  mov     dword ptr [rsp+970h+phkResult], eax
0x1800401d7  mov     word ptr [rbp+870h+var_8A0], r13w
0x1800401dc  movdqu  [rbp+870h+var_8B0], xmm0
0x1800401e1  mov     word ptr [rbp+870h+var_850], r13w
0x1800401e6  lea     rcx, [rbp+870h+var_850]
0x1800401ea  call    FormatRRASErrorString
0x1800401ef  lea     r9, [rbp+870h+var_8B0]
0x1800401f3  test    rdi, rdi
0x1800401f6  cmovnz  r9, rdi
0x1800401fa  lea     rax, [rbp+870h+var_8A0]
0x1800401fe  mov     [rsp+970h+lpcbMaxSubKeyLen], rax
0x180040203  mov     [rsp+970h+phkResult], r13
0x180040208  lea     r8, [rbp+870h+var_850]
0x18004020c  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180040213  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004021a  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180040221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040226  jmp     loc_180040674
0x18004022b  mov     [rsp+970h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180040230  mov     [rsp+970h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180040235  mov     [rsp+970h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18004023a  mov     [rsp+970h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18004023f  mov     [rsp+970h+lpcValues], r13; lpcValues
0x180040244  mov     [rsp+970h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180040249  mov     [rsp+970h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x18004024e  lea     rax, [rsp+970h+cSubKeys]
0x180040253  mov     [rsp+970h+phkResult], rax; lpcSubKeys
0x180040258  xor     r9d, r9d; lpReserved
0x18004025b  xor     r8d, r8d; lpcchClass
0x18004025e  xor     edx, edx; lpClass
0x180040260  mov     rcx, [rbp+870h+hKey]; hKey
0x180040264  call    cs:__imp_RegQueryInfoKeyW
0x18004026a  mov     [rsp+970h+var_910], eax
0x18004026e  test    eax, eax
0x180040270  jz      short loc_18004028B
0x180040272  cmp     qword ptr cs:xmmword_1800710A0, r13
0x180040279  jz      loc_180040674
0x18004027f  lea     rdx, aSRegqueryinfok; "%s: RegQueryInfoKey (%s) failed: %d."
0x180040286  jmp     loc_1800401C2
0x18004028b  mov     eax, [rsp+970h+cSubKeys]
0x18004028f  test    eax, eax
0x180040291  jnz     short loc_180040309
0x180040293  cmp     qword ptr cs:xmmword_1800710A0, r13
0x18004029a  jz      short loc_1800402FC
0x18004029c  mov     word ptr [rbp+870h+var_850], r13w
0x1800402a1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800402a8  movdqu  [rbp+870h+var_8B0], xmm0
0x1800402ad  mov     word ptr [rbp+870h+var_8A0], r13w
0x1800402b2  mov     r8, r14
0x1800402b5  lea     rdx, aSNoIpv4Address; "%s: No IPv4 address pool configured"
0x1800402bc  lea     rcx, [rbp+870h+var_850]
0x1800402c0  call    FormatRRASErrorString
0x1800402c5  lea     r9, [rbp+870h+var_8B0]
0x1800402c9  test    rdi, rdi
0x1800402cc  cmovnz  r9, rdi
0x1800402d0  lea     rax, [rbp+870h+var_8A0]
0x1800402d4  mov     [rsp+970h+lpcbMaxSubKeyLen], rax
0x1800402d9  mov     [rsp+970h+phkResult], r13
0x1800402de  lea     r8, [rbp+870h+var_850]
0x1800402e2  mov     rdx, qword ptr cs:xmmword_1800710A0
0x1800402e9  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x1800402f0  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x1800402f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800402fc  mov     [rsp+970h+var_910], 490h
0x180040304  jmp     loc_180040674
0x180040309  mov     rbx, rax
0x18004030c  shl     rbx, 3
0x180040310  call    cs:__imp_GetProcessHeap
0x180040316  mov     r8, rbx; dwBytes
0x180040319  mov     r15d, 8
0x18004031f  mov     edx, r15d; dwFlags
0x180040322  mov     rcx, rax; hHeap
0x180040325  call    cs:__imp_HeapAlloc
0x18004032b  mov     rbx, rax
0x18004032e  test    rax, rax
0x180040331  jnz     short loc_1800403A6
0x180040333  cmp     qword ptr cs:xmmword_1800710A0, r13
0x18004033a  jz      short loc_18004039C
0x18004033c  mov     word ptr [rbp+870h+var_850], r13w
0x180040341  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180040348  movdqu  [rbp+870h+var_8B0], xmm0
0x18004034d  mov     word ptr [rbp+870h+var_8A0], r13w
0x180040352  mov     r8, r14
0x180040355  lea     rdx, aSMallocFailed; "%s: Malloc failed."
0x18004035c  lea     rcx, [rbp+870h+var_850]
0x180040360  call    FormatRRASErrorString
0x180040365  lea     r9, [rbp+870h+var_8B0]
0x180040369  test    rdi, rdi
0x18004036c  cmovnz  r9, rdi
0x180040370  lea     rax, [rbp+870h+var_8A0]
0x180040374  mov     [rsp+970h+lpcbMaxSubKeyLen], rax
0x180040379  mov     [rsp+970h+phkResult], r13
0x18004037e  lea     r8, [rbp+870h+var_850]
0x180040382  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180040389  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180040390  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180040397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004039c  mov     [rsp+970h+var_910], r15d
0x1800403a1  jmp     loc_180040674
0x1800403a6  mov     r14d, r13d
0x1800403a9  mov     r15d, r13d
0x1800403ac  cmp     r15d, [rsp+970h+cSubKeys]
0x1800403b1  jnb     loc_18004065F
0x1800403b7  xorps   xmm0, xmm0
0x1800403ba  movups  xmmword ptr [rbp+870h+Buffer], xmm0
0x1800403be  movups  [rbp+870h+var_868], xmm0
0x1800403c2  mov     [rsp+970h+cbData], r13d
0x1800403c7  mov     dword ptr [rsp+970h+Data], r13d
0x1800403cc  mov     [rsp+970h+Type], r13d
0x1800403d1  mov     rcx, [rsp+970h+var_8F8]; hKey
0x1800403d6  test    rcx, rcx
0x1800403d9  jz      short loc_1800403E1
0x1800403db  call    cs:__imp_RegCloseKey
0x1800403e1  mov     [rsp+970h+var_8F8], r13
0x1800403e6  mov     r12d, r14d
0x1800403e9  xor     eax, eax
0x1800403eb  mov     [rbx+r12*8], rax
0x1800403ef  lea     r8d, [rax+0Ah]; Radix
0x1800403f3  lea     rdx, [rbp+870h+Buffer]; Buffer
0x1800403f7  mov     ecx, r15d; Value
0x1800403fa  call    cs:__imp__itow
0x180040400  lea     rax, [rsp+970h+var_8F8]
0x180040405  mov     [rsp+970h+phkResult], rax; phkResult
0x18004040a  mov     r9d, 20019h; samDesired
0x180040410  xor     r8d, r8d; ulOptions
0x180040413  lea     rdx, [rbp+870h+Buffer]; lpSubKey
0x180040417  mov     rcx, [rbp+870h+hKey]; hKey
0x18004041b  call    cs:__imp_RegOpenKeyExW
0x180040421  mov     [rsp+970h+var_910], eax
0x180040425  test    eax, eax
0x180040427  jz      short loc_1800404A8
0x180040429  cmp     qword ptr cs:xmmword_1800710A0, r13
0x180040430  jz      short loc_18004049E
0x180040432  mov     word ptr [rbp+870h+var_850], r13w
0x180040437  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004043e  movdqu  [rbp+870h+var_8B0], xmm0
0x180040443  mov     word ptr [rbp+870h+var_8A0], r13w
0x180040448  mov     dword ptr [rsp+970h+phkResult], eax
0x18004044c  lea     r9, [rbp+870h+Buffer]
0x180040450  lea     r8, aRrasroutingdom_29; "RRasRoutingDomainConfig::PopulateIpv4Ad"...
0x180040457  lea     rdx, aSRegopenkeyexW; "%s: RegOpenKeyEx (%ws) failed: %d."
0x18004045e  lea     rcx, [rbp+870h+var_850]
0x180040462  call    FormatRRASErrorString
0x180040467  lea     r9, [rbp+870h+var_8B0]
0x18004046b  test    rdi, rdi
0x18004046e  cmovnz  r9, rdi
0x180040472  lea     rax, [rbp+870h+var_8A0]
0x180040476  mov     [rsp+970h+lpcbMaxSubKeyLen], rax
0x18004047b  mov     [rsp+970h+phkResult], r13
0x180040480  lea     r8, [rbp+870h+var_850]
0x180040484  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18004048b  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180040492  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180040499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004049e  mov     [rsp+970h+var_910], r13d
0x1800404a3  jmp     loc_180040657
0x1800404a8  mov     [rsp+970h+cbData], 4
0x1800404b0  lea     rax, [rsp+970h+cbData]
0x1800404b5  mov     [rsp+970h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800404ba  lea     rax, [rsp+970h+Data]
0x1800404bf  mov     [rsp+970h+phkResult], rax; lpData
0x1800404c4  lea     r9, [rsp+970h+Type]; lpType
0x1800404c9  xor     r8d, r8d; lpReserved
0x1800404cc  lea     rdx, aFrom; "From"
0x1800404d3  mov     rcx, [rsp+970h+var_8F8]; hKey
0x1800404d8  call    cs:__imp_RegQueryValueExW
0x1800404de  mov     [rsp+970h+var_910], eax
0x1800404e2  test    eax, eax
0x1800404e4  jnz     short loc_1800404F1
0x1800404e6  cmp     [rsp+970h+Type], 4
0x1800404eb  jz      loc_180040577
0x1800404f1  cmp     qword ptr cs:xmmword_1800710A0, r13
0x1800404f8  jz      short loc_180040572
0x1800404fa  mov     word ptr [rbp+870h+var_850], r13w
0x1800404ff  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180040506  movdqu  [rbp+870h+var_8B0], xmm0
0x18004050b  mov     word ptr [rbp+870h+var_8A0], r13w
0x180040510  mov     dword ptr [rsp+970h+lpcbMaxSubKeyLen], eax
0x180040514  lea     rax, [rbp+870h+Buffer]
0x180040518  mov     [rsp+970h+phkResult], rax
0x18004051d  lea     r9, aFrom; "From"
0x180040524  lea     r8, aRrasroutingdom_29; "RRasRoutingDomainConfig::PopulateIpv4Ad"...
0x18004052b  lea     rdx, aSCouldnTReadVa_0; "%s: Couldn't read value %s in key %ws: "...
0x180040532  lea     rcx, [rbp+870h+var_850]
0x180040536  call    FormatRRASErrorString
0x18004053b  lea     r9, [rbp+870h+var_8B0]
0x18004053f  test    rdi, rdi
0x180040542  cmovnz  r9, rdi
0x180040546  lea     rax, [rbp+870h+var_8A0]
0x18004054a  mov     [rsp+970h+lpcbMaxSubKeyLen], rax
0x18004054f  mov     [rsp+970h+phkResult], r13
0x180040554  lea     r8, [rbp+870h+var_850]
0x180040558  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18004055f  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180040566  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004056d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040572  mov     [rsp+970h+var_910], r13d
0x180040577  mov     eax, dword ptr [rsp+970h+Data]
0x18004057b  mov     [rbx+r12*8], eax
0x18004057f  mov     dword ptr [rsp+970h+Data], r13d
0x180040584  lea     rax, [rsp+970h+cbData]
0x180040589  mov     [rsp+970h+lpcbMaxSubKeyLen], rax; lpcbData
0x18004058e  lea     rax, [rsp+970h+Data]
0x180040593  mov     [rsp+970h+phkResult], rax; lpData
0x180040598  lea     r9, [rsp+970h+Type]; lpType
0x18004059d  xor     r8d, r8d; lpReserved
0x1800405a0  lea     rdx, aTo; "To"
0x1800405a7  mov     rcx, [rsp+970h+var_8F8]; hKey
0x1800405ac  call    cs:__imp_RegQueryValueExW
0x1800405b2  mov     [rsp+970h+var_910], eax
0x1800405b6  test    eax, eax
0x1800405b8  jnz     short loc_1800405C5
0x1800405ba  cmp     [rsp+970h+Type], 4
0x1800405bf  jz      loc_18004064B
0x1800405c5  cmp     qword ptr cs:xmmword_1800710A0, r13
0x1800405cc  jz      short loc_180040646
0x1800405ce  mov     word ptr [rbp+870h+var_850], r13w
0x1800405d3  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800405da  movdqu  [rbp+870h+var_8B0], xmm0
0x1800405df  mov     word ptr [rbp+870h+var_8A0], r13w
0x1800405e4  mov     dword ptr [rsp+970h+lpcbMaxSubKeyLen], eax
0x1800405e8  lea     rax, [rbp+870h+Buffer]
0x1800405ec  mov     [rsp+970h+phkResult], rax
0x1800405f1  lea     r9, aTo; "To"
0x1800405f8  lea     r8, aRrasroutingdom_29; "RRasRoutingDomainConfig::PopulateIpv4Ad"...
0x1800405ff  lea     rdx, aSCouldnTReadVa_0; "%s: Couldn't read value %s in key %ws: "...
0x180040606  lea     rcx, [rbp+870h+var_850]
0x18004060a  call    FormatRRASErrorString
0x18004060f  lea     r9, [rbp+870h+var_8B0]
0x180040613  test    rdi, rdi
0x180040616  cmovnz  r9, rdi
0x18004061a  lea     rax, [rbp+870h+var_8A0]
0x18004061e  mov     [rsp+970h+lpcbMaxSubKeyLen], rax
0x180040623  mov     [rsp+970h+phkResult], r13
0x180040628  lea     r8, [rbp+870h+var_850]
0x18004062c  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180040633  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004063a  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
  ... truncated ...
```
