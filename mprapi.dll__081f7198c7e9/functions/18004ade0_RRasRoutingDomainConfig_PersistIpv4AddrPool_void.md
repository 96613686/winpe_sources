# RRasRoutingDomainConfig::PersistIpv4AddrPool(void)

- ea: `0x18004ade0`
- end: `0x18004b1fc`
- name: `?PersistIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKXZ`
- size: `1052`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18004a6c0`
- `0x18004c944`

## callees

- `0x18004ade0`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `msvcrt!_itow` at `0x18004afa9`
- `msvcrt!_itow` at `0x18004b007`
- `msvcrt!_itow` at `0x18004afa9`
- `msvcrt!_itow` at `0x18004b007`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004af73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b017`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b1a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b1c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004af73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b017`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b1a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b1c7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18004af8d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18004af8d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004b0ac`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004b101`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004b0ac`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004b101`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004afcb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004afcb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004aec9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004b052`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004aec9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004b052`

## string_xrefs

- `0x18004b125`: `%s: Couldn't write value %s: %d`
- `0x18004af12`: `%s: RegCreateKeyEx (%s) failed: %d.`
- `0x18004ae83`: `RRasRoutingDomainConfig::PersistIpv4AddrPool`
- `0x18004af0b`: `RRasRoutingDomainConfig::PersistIpv4AddrPool`
- `0x18004b146`: `RRasRoutingDomainConfig::PersistIpv4AddrPool`
- `0x18004b071`: `%s: RegCreateKeyEx (%ws) failed: %d.`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::PersistIpv4AddrPool(RRasRoutingDomainConfig *this)
{
  void (*v2)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  WCHAR *v5; // r9
  int v6; // ebx
  int i; // ecx
  unsigned int v8; // esi
  LSTATUS v9; // eax
  wchar_t *v10; // r9
  const wchar_t *v11; // rdx
  WCHAR *v12; // r9
  DWORD dwOptions[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwOptionsa[2]; // [rsp+20h] [rbp-E0h]
  unsigned int v16; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+68h] [rbp-98h] BYREF
  __int128 v20; // [rsp+70h] [rbp-90h]
  __int128 v21; // [rsp+80h] [rbp-80h]
  __int64 v22; // [rsp+90h] [rbp-70h]
  int v23; // [rsp+98h] [rbp-68h]
  int v24; // [rsp+9Ch] [rbp-64h]
  WCHAR SubKey[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v26; // [rsp+B0h] [rbp-50h]
  int v27; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v28; // [rsp+C4h] [rbp-3Ch]
  __int128 v29; // [rsp+D4h] [rbp-2Ch]
  int v30; // [rsp+E4h] [rbp-1Ch]
  wchar_t Buffer[8]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v32; // [rsp+F8h] [rbp-8h]
  int v33; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v34[2044]; // [rsp+114h] [rbp+14h] BYREF

  v16 = 0;
  phkResult = 0;
  hKey = 0;
  v33 = 0;
  memset_0(v34, 0, sizeof(v34));
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v20 = 0;
  v19 = 0;
  v21 = 0;
  v22 = 0;
  v23 = -1;
  v24 = 0;
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v19,
      L"RRasRoutingDomainConfig::PersistIpv4AddrPool",
      &v16,
      v2,
      (struct _GUID *)((char *)this + 516));
  v3 = RegCreateKeyExW(*((HKEY *)this + 103), L"Ipv4AddrPool", 0, 0, 0, 0x20006u, 0, &phkResult, 0);
  v4 = v3;
  v16 = v3;
  if ( !v3 )
  {
    v6 = 0;
    for ( i = 0; ; i = v6 )
    {
      *(_OWORD *)SubKey = 0;
      v26 = 0;
      _itow(i, SubKey, 10);
      v16 = RegOpenKeyExW(phkResult, SubKey, 0, 0x20006u, &hKey);
      if ( v16 )
        break;
      RegCloseKey(hKey);
      hKey = 0;
      RegDeleteKeyExW(phkResult, SubKey, 0, 0);
      ++v6;
    }
    v4 = 0;
    v16 = 0;
    v8 = 0;
    if ( !*((_DWORD *)this + 147) )
      goto LABEL_31;
    while ( 1 )
    {
      *(_OWORD *)Buffer = 0;
      v32 = 0;
      _itow(v8, Buffer, 10);
      if ( hKey )
      {
        RegCloseKey(hKey);
        hKey = 0;
      }
      v9 = RegCreateKeyExW(phkResult, Buffer, 0, 0, 0, 0x20006u, 0, &hKey, 0);
      v16 = v9;
      if ( v9 )
      {
        if ( (_QWORD)xmmword_180078C60 )
        {
          v10 = Buffer;
          v11 = L"%s: RegCreateKeyEx (%ws) failed: %d.";
          goto LABEL_24;
        }
      }
      else
      {
        v9 = RegSetValueExW(hKey, L"From", 0, 4u, (const BYTE *)(*((_QWORD *)this + 74) + 8LL * v8), 4u);
        v16 = v9;
        if ( v9 )
        {
          if ( (_QWORD)xmmword_180078C60 )
          {
            v10 = (wchar_t *)L"From";
            goto LABEL_23;
          }
        }
        else
        {
          v9 = RegSetValueExW(hKey, L"To", 0, 4u, (const BYTE *)(*((_QWORD *)this + 74) + 4LL + 8LL * v8), 4u);
          v4 = v9;
          v16 = v9;
          if ( !v9 )
          {
            if ( hKey )
            {
              RegCloseKey(hKey);
              hKey = 0;
              v4 = v16;
            }
            goto LABEL_30;
          }
          if ( (_QWORD)xmmword_180078C60 )
          {
            v10 = (wchar_t *)L"To";
LABEL_23:
            v11 = L"%s: Couldn't write value %s: %d";
LABEL_24:
            dwOptionsa[0] = v9;
            LOWORD(v33) = 0;
            *(GUID *)SubKey = GUID_NULL;
            LOWORD(v27) = 0;
            FormatRRASErrorString(
              &v33,
              v11,
              L"RRasRoutingDomainConfig::PersistIpv4AddrPool",
              v10,
              *(_QWORD *)dwOptionsa);
            v12 = SubKey;
            if ( this != (RRasRoutingDomainConfig *)-516LL )
              v12 = (WCHAR *)((char *)this + 516);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, WCHAR *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
              gCfgStoreEtwContext,
              xmmword_180078C60,
              &v33,
              v12,
              0,
              &v27);
          }
        }
      }
      v4 = 0;
      v16 = 0;
LABEL_30:
      if ( ++v8 >= *((_DWORD *)this + 147) )
        goto LABEL_31;
    }
  }
  if ( (_QWORD)xmmword_180078C60 )
  {
    LOWORD(v33) = 0;
    *(GUID *)SubKey = GUID_NULL;
    LOWORD(v27) = 0;
    dwOptions[0] = v3;
    FormatRRASErrorString(
      &v33,
      L"%s: RegCreateKeyEx (%s) failed: %d.",
      L"RRasRoutingDomainConfig::PersistIpv4AddrPool",
      L"Ipv4",
      *(_QWORD *)dwOptions);
    v5 = SubKey;
    if ( this != (RRasRoutingDomainConfig *)-516LL )
      v5 = (WCHAR *)((char *)this + 516);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, WCHAR *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180078C60,
      &v33,
      v5,
      0,
      &v27);
    v4 = v16;
  }
LABEL_31:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    v4 = v16;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v19);
  return v4;
}

```

## disassembly

```asm
0x18004ade0  push    rbp
0x18004ade2  push    rbx
0x18004ade3  push    rsi
0x18004ade4  push    rdi
0x18004ade5  push    r14
0x18004ade7  push    r15
0x18004ade9  lea     rbp, [rsp-828h]
0x18004adf1  sub     rsp, 928h
0x18004adf8  mov     rax, cs:__security_cookie
0x18004adff  xor     rax, rsp
0x18004ae02  mov     [rbp+850h+var_40], rax
0x18004ae09  mov     rdi, rcx
0x18004ae0c  xor     r15d, r15d
0x18004ae0f  mov     [rsp+950h+var_900], r15d
0x18004ae14  mov     [rsp+950h+var_8F0], r15
0x18004ae19  mov     [rsp+950h+hKey], r15
0x18004ae1e  mov     [rbp+850h+var_840], r15d
0x18004ae22  xor     edx, edx; Val
0x18004ae24  mov     r8d, 7FCh; Size
0x18004ae2a  lea     rcx, [rbp+850h+var_83C]; void *
0x18004ae2e  call    memset_0
0x18004ae33  mov     [rbp+850h+var_890], r15d
0x18004ae37  xorps   xmm0, xmm0
0x18004ae3a  xor     eax, eax
0x18004ae3c  movups  [rbp+850h+var_88C], xmm0
0x18004ae40  movups  [rbp+850h+var_87C], xmm0
0x18004ae44  mov     [rbp+850h+var_86C], eax
0x18004ae47  movdqu  [rsp+950h+var_8E0], xmm0
0x18004ae4d  mov     [rsp+950h+var_8E8], r15
0x18004ae52  xorps   xmm1, xmm1
0x18004ae55  movdqu  [rbp+850h+var_8D0], xmm1
0x18004ae5a  mov     [rbp+850h+var_8C0], r15
0x18004ae5e  mov     [rbp+850h+var_8B8], 0FFFFFFFFh
0x18004ae65  mov     [rbp+850h+var_8B4], r15d
0x18004ae69  lea     r14, [rdi+204h]
0x18004ae70  cmp     qword ptr cs:xmmword_180078C60+8, r15
0x18004ae77  jz      short loc_18004AE94
0x18004ae79  mov     qword ptr [rsp+950h+dwOptions], r14; struct _GUID *
0x18004ae7e  lea     r8, [rsp+950h+var_900]; unsigned int *
0x18004ae83  lea     rdx, aRrasroutingdom_13; "RRasRoutingDomainConfig::PersistIpv4Add"...
0x18004ae8a  lea     rcx, [rsp+950h+var_8E8]; this
0x18004ae8f  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18004ae94  mov     [rsp+950h+lpdwDisposition], r15; lpdwDisposition
0x18004ae99  lea     rax, [rsp+950h+var_8F0]
0x18004ae9e  mov     [rsp+950h+phkResult], rax; phkResult
0x18004aea3  mov     [rsp+950h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18004aea8  mov     [rsp+950h+samDesired], 20006h; samDesired
0x18004aeb0  mov     [rsp+950h+dwOptions], r15d; dwOptions
0x18004aeb5  xor     r9d, r9d; lpClass
0x18004aeb8  xor     r8d, r8d; Reserved
0x18004aebb  lea     rdx, aIpv4addrpool; "Ipv4AddrPool"
0x18004aec2  mov     rcx, [rdi+338h]; hKey
0x18004aec9  call    cs:__imp_RegCreateKeyExW
0x18004aecf  mov     ebx, eax
0x18004aed1  mov     [rsp+950h+var_900], eax
0x18004aed5  test    eax, eax
0x18004aed7  jz      loc_18004AF62
0x18004aedd  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004aee4  jz      loc_18004B1BD
0x18004aeea  mov     word ptr [rbp+850h+var_840], r15w
0x18004aeef  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004aef6  movdqu  xmmword ptr [rbp+850h+SubKey], xmm0
0x18004aefb  mov     word ptr [rbp+850h+var_890], r15w
0x18004af00  mov     [rsp+950h+dwOptions], eax
0x18004af04  lea     r9, aIpv4; "Ipv4"
0x18004af0b  lea     r8, aRrasroutingdom_13; "RRasRoutingDomainConfig::PersistIpv4Add"...
0x18004af12  lea     rdx, aSRegcreatekeye_1; "%s: RegCreateKeyEx (%s) failed: %d."
0x18004af19  lea     rcx, [rbp+850h+var_840]
0x18004af1d  call    FormatRRASErrorString
0x18004af22  lea     r9, [rbp+850h+SubKey]
0x18004af26  test    r14, r14
0x18004af29  cmovnz  r9, r14
0x18004af2d  lea     rax, [rbp+850h+var_890]
0x18004af31  mov     qword ptr [rsp+950h+samDesired], rax
0x18004af36  mov     qword ptr [rsp+950h+dwOptions], r15
0x18004af3b  lea     r8, [rbp+850h+var_840]
0x18004af3f  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004af46  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004af4d  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004af54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af59  mov     ebx, [rsp+950h+var_900]
0x18004af5d  jmp     loc_18004B1BD
0x18004af62  mov     ebx, r15d
0x18004af65  mov     esi, 0Ah
0x18004af6a  xor     ecx, ecx
0x18004af6c  jmp     short loc_18004AF97
0x18004af6e  mov     rcx, [rsp+950h+hKey]; hKey
0x18004af73  call    cs:__imp_RegCloseKey
0x18004af79  mov     [rsp+950h+hKey], r15
0x18004af7e  xor     r9d, r9d; Reserved
0x18004af81  xor     r8d, r8d; samDesired
0x18004af84  lea     rdx, [rbp+850h+SubKey]; lpSubKey
0x18004af88  mov     rcx, [rsp+950h+var_8F0]; hKey
0x18004af8d  call    cs:__imp_RegDeleteKeyExW
0x18004af93  inc     ebx
0x18004af95  mov     ecx, ebx; Value
0x18004af97  xorps   xmm0, xmm0
0x18004af9a  movups  xmmword ptr [rbp+850h+SubKey], xmm0
0x18004af9e  movups  [rbp+850h+var_8A0], xmm0
0x18004afa2  mov     r8d, esi; Radix
0x18004afa5  lea     rdx, [rbp+850h+SubKey]; Buffer
0x18004afa9  call    cs:__imp__itow
0x18004afaf  lea     rax, [rsp+950h+hKey]
0x18004afb4  mov     qword ptr [rsp+950h+dwOptions], rax; phkResult
0x18004afb9  mov     r9d, 20006h; samDesired
0x18004afbf  xor     r8d, r8d; ulOptions
0x18004afc2  lea     rdx, [rbp+850h+SubKey]; lpSubKey
0x18004afc6  mov     rcx, [rsp+950h+var_8F0]; hKey
0x18004afcb  call    cs:__imp_RegOpenKeyExW
0x18004afd1  test    eax, eax
0x18004afd3  mov     [rsp+950h+var_900], eax
0x18004afd7  jz      short loc_18004AF6E
0x18004afd9  mov     ebx, r15d
0x18004afdc  mov     [rsp+950h+var_900], ebx
0x18004afe0  mov     esi, r15d
0x18004afe3  cmp     [rdi+24Ch], r15d
0x18004afea  jbe     loc_18004B1BD
0x18004aff0  xorps   xmm0, xmm0
0x18004aff3  movups  xmmword ptr [rbp+850h+Buffer], xmm0
0x18004aff7  movups  [rbp+850h+var_858], xmm0
0x18004affb  mov     r8d, 0Ah; Radix
0x18004b001  lea     rdx, [rbp+850h+Buffer]; Buffer
0x18004b005  mov     ecx, esi; Value
0x18004b007  call    cs:__imp__itow
0x18004b00d  mov     rcx, [rsp+950h+hKey]; hKey
0x18004b012  test    rcx, rcx
0x18004b015  jz      short loc_18004B022
0x18004b017  call    cs:__imp_RegCloseKey
0x18004b01d  mov     [rsp+950h+hKey], r15
0x18004b022  mov     [rsp+950h+lpdwDisposition], r15; lpdwDisposition
0x18004b027  lea     rax, [rsp+950h+hKey]
0x18004b02c  mov     [rsp+950h+phkResult], rax; phkResult
0x18004b031  mov     [rsp+950h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18004b036  mov     [rsp+950h+samDesired], 20006h; samDesired
0x18004b03e  mov     [rsp+950h+dwOptions], r15d; dwOptions
0x18004b043  xor     r9d, r9d; lpClass
0x18004b046  xor     r8d, r8d; Reserved
0x18004b049  lea     rdx, [rbp+850h+Buffer]; lpSubKey
0x18004b04d  mov     rcx, [rsp+950h+var_8F0]; hKey
0x18004b052  call    cs:__imp_RegCreateKeyExW
0x18004b058  mov     [rsp+950h+var_900], eax
0x18004b05c  test    eax, eax
0x18004b05e  jz      short loc_18004B07D
0x18004b060  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004b067  jz      loc_18004B18D
0x18004b06d  lea     r9, [rbp+850h+Buffer]
0x18004b071  lea     rdx, aSRegcreatekeye_0; "%s: RegCreateKeyEx (%ws) failed: %d."
0x18004b078  jmp     loc_18004B12C
0x18004b07d  mov     ebx, esi
0x18004b07f  mov     rax, [rdi+250h]
0x18004b086  lea     rcx, [rax+rbx*8]
0x18004b08a  mov     [rsp+950h+samDesired], 4; cbData
0x18004b092  mov     qword ptr [rsp+950h+dwOptions], rcx; lpData
0x18004b097  mov     r9d, 4; dwType
0x18004b09d  xor     r8d, r8d; Reserved
0x18004b0a0  lea     rdx, aFrom; "From"
0x18004b0a7  mov     rcx, [rsp+950h+hKey]; hKey
0x18004b0ac  call    cs:__imp_RegSetValueExW
0x18004b0b2  mov     [rsp+950h+var_900], eax
0x18004b0b6  test    eax, eax
0x18004b0b8  jz      short loc_18004B0D0
0x18004b0ba  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004b0c1  jz      loc_18004B18D
0x18004b0c7  lea     r9, aFrom; "From"
0x18004b0ce  jmp     short loc_18004B125
0x18004b0d0  mov     rcx, [rdi+250h]
0x18004b0d7  add     rcx, 4
0x18004b0db  lea     rcx, [rcx+rbx*8]
0x18004b0df  mov     [rsp+950h+samDesired], 4; cbData
0x18004b0e7  mov     qword ptr [rsp+950h+dwOptions], rcx; lpData
0x18004b0ec  mov     r9d, 4; dwType
0x18004b0f2  xor     r8d, r8d; Reserved
0x18004b0f5  lea     rdx, aTo; "To"
0x18004b0fc  mov     rcx, [rsp+950h+hKey]; hKey
0x18004b101  call    cs:__imp_RegSetValueExW
0x18004b107  mov     ebx, eax
0x18004b109  mov     [rsp+950h+var_900], eax
0x18004b10d  test    eax, eax
0x18004b10f  jz      loc_18004B196
0x18004b115  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004b11c  jz      short loc_18004B18D
0x18004b11e  lea     r9, aTo; "To"
0x18004b125  lea     rdx, aSCouldnTWriteV_0; "%s: Couldn't write value %s: %d"
0x18004b12c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004b133  mov     [rsp+950h+dwOptions], eax
0x18004b137  mov     word ptr [rbp+850h+var_840], r15w
0x18004b13c  movdqu  xmmword ptr [rbp+850h+SubKey], xmm0
0x18004b141  mov     word ptr [rbp+850h+var_890], r15w
0x18004b146  lea     r8, aRrasroutingdom_13; "RRasRoutingDomainConfig::PersistIpv4Add"...
0x18004b14d  lea     rcx, [rbp+850h+var_840]
0x18004b151  call    FormatRRASErrorString
0x18004b156  lea     rax, [rbp+850h+var_890]
0x18004b15a  mov     qword ptr [rsp+950h+samDesired], rax
0x18004b15f  lea     r9, [rbp+850h+SubKey]
0x18004b163  test    r14, r14
0x18004b166  mov     qword ptr [rsp+950h+dwOptions], r15
0x18004b16b  cmovnz  r9, r14
0x18004b16f  lea     r8, [rbp+850h+var_840]
0x18004b173  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004b17a  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004b181  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004b188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b18d  mov     ebx, r15d
0x18004b190  mov     [rsp+950h+var_900], ebx
0x18004b194  jmp     short loc_18004B1AF
0x18004b196  mov     rcx, [rsp+950h+hKey]; hKey
0x18004b19b  test    rcx, rcx
0x18004b19e  jz      short loc_18004B1AF
0x18004b1a0  call    cs:__imp_RegCloseKey
0x18004b1a6  mov     [rsp+950h+hKey], r15
0x18004b1ab  mov     ebx, [rsp+950h+var_900]
0x18004b1af  inc     esi
0x18004b1b1  cmp     esi, [rdi+24Ch]
0x18004b1b7  jb      loc_18004AFF0
0x18004b1bd  mov     rcx, [rsp+950h+var_8F0]; hKey
0x18004b1c2  test    rcx, rcx
0x18004b1c5  jz      short loc_18004B1D1
0x18004b1c7  call    cs:__imp_RegCloseKey
0x18004b1cd  mov     ebx, [rsp+950h+var_900]
0x18004b1d1  lea     rcx, [rsp+950h+var_8E8]; this
0x18004b1d6  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18004b1db  mov     eax, ebx
0x18004b1dd  mov     rcx, [rbp+850h+var_40]
0x18004b1e4  xor     rcx, rsp; StackCookie
0x18004b1e7  call    __security_check_cookie
0x18004b1ec  add     rsp, 928h
0x18004b1f3  pop     r15
0x18004b1f5  pop     r14
0x18004b1f7  pop     rdi
0x18004b1f8  pop     rsi
0x18004b1f9  pop     rbx
0x18004b1fa  pop     rbp
0x18004b1fb  retn
```
