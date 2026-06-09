# RRasRoutingDomainConfig::UpdateTransportInfo(_MPRI_TRANSPORT_INFO_1 *)

- ea: `0x180043460`
- end: `0x180043674`
- name: `?UpdateTransportInfo@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_TRANSPORT_INFO_1@@@Z`
- size: `532`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, struct _MPRI_TRANSPORT_INFO_1 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800416fc`
- `0x180042398`

## callees

- `0x180043460`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800435a8`
- `ADVAPI32!RegSetValueExW` at `0x1800435a8`
- `ADVAPI32!RegCloseKey` at `0x180043638`
- `ADVAPI32!RegCloseKey` at `0x180043638`
- `ADVAPI32!RegCreateKeyExW` at `0x18004355c`
- `ADVAPI32!RegCreateKeyExW` at `0x18004355c`

## string_xrefs

- `0x1800435c6`: `%s: Couldn't write value %s: %d`
- `0x180043505`: `RRasRoutingDomainConfig::UpdateTransportInfo`
- `0x1800435e7`: `RRasRoutingDomainConfig::UpdateTransportInfo`
- `0x18004357a`: `%s: RegCreateKeyEx (%s) failed: %d.`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::UpdateTransportInfo(
        RRasRoutingDomainConfig *this,
        struct _MPRI_TRANSPORT_INFO_1 *a2)
{
  void (*v4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  const WCHAR *v5; // rdi
  LSTATUS v6; // eax
  const WCHAR *v7; // r9
  const wchar_t *v8; // rdx
  GUID *v9; // r9
  unsigned int v10; // ebx
  DWORD dwOptions[2]; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *samDesired; // [rsp+28h] [rbp-D8h]
  unsigned int lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  unsigned int v15; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v17; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v18; // [rsp+68h] [rbp-98h]
  __int128 v19; // [rsp+78h] [rbp-88h]
  __int64 v20; // [rsp+88h] [rbp-78h]
  int v21; // [rsp+90h] [rbp-70h]
  int v22; // [rsp+94h] [rbp-6Ch]
  GUID v23; // [rsp+98h] [rbp-68h] BYREF
  int v24; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v25; // [rsp+ACh] [rbp-54h]
  __int128 v26; // [rsp+BCh] [rbp-44h]
  int v27; // [rsp+CCh] [rbp-34h]
  int v28; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v29[2044]; // [rsp+D4h] [rbp-2Ch] BYREF

  v15 = 0;
  hKey = 0;
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v18 = 0;
  v17 = 0;
  v19 = 0;
  v20 = 0;
  v21 = -1;
  v22 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v17,
      L"RRasRoutingDomainConfig::UpdateTransportInfo",
      &v15,
      v4,
      (struct _GUID *)((char *)this + 516),
      samDesired,
      lpSecurityAttributes);
  v5 = L"Ipv4";
  if ( *(_DWORD *)a2 != 33 )
    v5 = L"Ipv6";
  v6 = RegCreateKeyExW(*((HKEY *)this + 103), v5, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  v15 = v6;
  if ( v6 )
  {
    if ( !(_QWORD)xmmword_1800710A0 )
      goto LABEL_14;
    v7 = v5;
    v8 = L"%s: RegCreateKeyEx (%s) failed: %d.";
  }
  else
  {
    v6 = RegSetValueExW(hKey, L"GlobalInfo", 0, 3u, *((const BYTE **)a2 + 1), *((_DWORD *)a2 + 1));
    v15 = v6;
    if ( !v6 || !(_QWORD)xmmword_1800710A0 )
      goto LABEL_14;
    v7 = L"GlobalInfo";
    v8 = L"%s: Couldn't write value %s: %d";
  }
  dwOptions[0] = v6;
  LOWORD(v28) = 0;
  v23 = GUID_NULL;
  LOWORD(v24) = 0;
  FormatRRASErrorString(&v28, v8, L"RRasRoutingDomainConfig::UpdateTransportInfo", v7, *(_QWORD *)dwOptions);
  v9 = &v23;
  if ( this != (RRasRoutingDomainConfig *)-516LL )
    v9 = (GUID *)((char *)this + 516);
  ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
    gCfgStoreEtwContext,
    xmmword_1800710A0,
    &v28,
    v9,
    0,
    &v24);
LABEL_14:
  if ( hKey )
    RegCloseKey(hKey);
  v10 = v15;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v17);
  return v10;
}

```

## disassembly

```asm
0x180043460  mov     [rsp-8+arg_10], rbx
0x180043465  push    rbp
0x180043466  push    rsi
0x180043467  push    rdi
0x180043468  push    r14
0x18004346a  push    r15
0x18004346c  lea     rbp, [rsp-7E0h]
0x180043474  sub     rsp, 8E0h
0x18004347b  mov     rax, cs:__security_cookie
0x180043482  xor     rax, rsp
0x180043485  mov     [rbp+800h+var_30], rax
0x18004348c  mov     rsi, rdx
0x18004348f  mov     r14, rcx
0x180043492  xor     r15d, r15d
0x180043495  mov     [rsp+900h+var_8B0], r15d
0x18004349a  mov     [rsp+900h+hKey], r15
0x18004349f  mov     [rbp+800h+var_830], r15d
0x1800434a3  xor     edx, edx; Val
0x1800434a5  mov     r8d, 7FCh; Size
0x1800434ab  lea     rcx, [rbp+800h+var_82C]; void *
0x1800434af  call    memset_0
0x1800434b4  mov     [rbp+800h+var_858], r15d
0x1800434b8  xorps   xmm0, xmm0
0x1800434bb  xor     eax, eax
0x1800434bd  movups  [rbp+800h+var_854], xmm0
0x1800434c1  movups  [rbp+800h+var_844], xmm0
0x1800434c5  mov     [rbp+800h+var_834], eax
0x1800434c8  movdqu  [rsp+900h+var_898], xmm0
0x1800434ce  mov     [rsp+900h+var_8A0], r15
0x1800434d3  xorps   xmm1, xmm1
0x1800434d6  movdqu  [rsp+900h+var_888], xmm1
0x1800434dc  mov     [rbp+800h+var_878], r15
0x1800434e0  mov     [rbp+800h+var_870], 0FFFFFFFFh
0x1800434e7  mov     [rbp+800h+var_86C], r15d
0x1800434eb  lea     rbx, [r14+204h]
0x1800434f2  cmp     qword ptr cs:xmmword_1800710A0+8, r15
0x1800434f9  jz      short loc_180043516
0x1800434fb  mov     qword ptr [rsp+900h+dwOptions], rbx; struct _GUID *
0x180043500  lea     r8, [rsp+900h+var_8B0]; unsigned int *
0x180043505  lea     rdx, aRrasroutingdom_42; "RRasRoutingDomainConfig::UpdateTranspor"...
0x18004350c  lea     rcx, [rsp+900h+var_8A0]; this
0x180043511  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180043516  lea     rax, aIpv6; "Ipv6"
0x18004351d  lea     rdi, aIpv4; "Ipv4"
0x180043524  cmp     dword ptr [rsi], 21h ; '!'
0x180043527  cmovnz  rdi, rax
0x18004352b  mov     [rsp+900h+lpdwDisposition], r15; lpdwDisposition
0x180043530  lea     rax, [rsp+900h+hKey]
0x180043535  mov     [rsp+900h+phkResult], rax; phkResult
0x18004353a  mov     [rsp+900h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18004353f  mov     [rsp+900h+samDesired], 20006h; samDesired
0x180043547  mov     [rsp+900h+dwOptions], r15d; dwOptions
0x18004354c  xor     r9d, r9d; lpClass
0x18004354f  xor     r8d, r8d; Reserved
0x180043552  mov     rdx, rdi; lpSubKey
0x180043555  mov     rcx, [r14+338h]; hKey
0x18004355c  call    cs:__imp_RegCreateKeyExW
0x180043562  mov     [rsp+900h+var_8B0], eax
0x180043566  test    eax, eax
0x180043568  jz      short loc_180043583
0x18004356a  cmp     qword ptr cs:xmmword_1800710A0, r15
0x180043571  jz      loc_18004362E
0x180043577  mov     r9, rdi
0x18004357a  lea     rdx, aSRegcreatekeye_1; "%s: RegCreateKeyEx (%s) failed: %d."
0x180043581  jmp     short loc_1800435CD
0x180043583  mov     eax, [rsi+4]
0x180043586  mov     [rsp+900h+samDesired], eax; cbData
0x18004358a  mov     rax, [rsi+8]
0x18004358e  mov     qword ptr [rsp+900h+dwOptions], rax; lpData
0x180043593  mov     r9d, 3; dwType
0x180043599  xor     r8d, r8d; Reserved
0x18004359c  lea     rdx, aGlobalinfo; "GlobalInfo"
0x1800435a3  mov     rcx, [rsp+900h+hKey]; hKey
0x1800435a8  call    cs:__imp_RegSetValueExW
0x1800435ae  mov     [rsp+900h+var_8B0], eax
0x1800435b2  test    eax, eax
0x1800435b4  jz      short loc_18004362E
0x1800435b6  cmp     qword ptr cs:xmmword_1800710A0, r15
0x1800435bd  jz      short loc_18004362E
0x1800435bf  lea     r9, aGlobalinfo; "GlobalInfo"
0x1800435c6  lea     rdx, aSCouldnTWriteV_0; "%s: Couldn't write value %s: %d"
0x1800435cd  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800435d4  mov     [rsp+900h+dwOptions], eax
0x1800435d8  mov     word ptr [rbp+800h+var_830], r15w
0x1800435dd  movdqu  [rbp+800h+var_868], xmm0
0x1800435e2  mov     word ptr [rbp+800h+var_858], r15w
0x1800435e7  lea     r8, aRrasroutingdom_42; "RRasRoutingDomainConfig::UpdateTranspor"...
0x1800435ee  lea     rcx, [rbp+800h+var_830]
0x1800435f2  call    FormatRRASErrorString
0x1800435f7  lea     rax, [rbp+800h+var_858]
0x1800435fb  mov     qword ptr [rsp+900h+samDesired], rax
0x180043600  lea     r9, [rbp+800h+var_868]
0x180043604  test    rbx, rbx
0x180043607  mov     qword ptr [rsp+900h+dwOptions], r15
0x18004360c  cmovnz  r9, rbx
0x180043610  lea     r8, [rbp+800h+var_830]
0x180043614  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18004361b  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180043622  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180043629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004362e  mov     rcx, [rsp+900h+hKey]; hKey
0x180043633  test    rcx, rcx
0x180043636  jz      short loc_18004363E
0x180043638  call    cs:__imp_RegCloseKey
0x18004363e  mov     ebx, [rsp+900h+var_8B0]
0x180043642  lea     rcx, [rsp+900h+var_8A0]; this
0x180043647  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18004364c  mov     eax, ebx
0x18004364e  mov     rcx, [rbp+800h+var_30]
0x180043655  xor     rcx, rsp; StackCookie
0x180043658  call    __security_check_cookie
0x18004365d  mov     rbx, [rsp+900h+arg_10]
0x180043665  add     rsp, 8E0h
0x18004366c  pop     r15
0x18004366e  pop     r14
0x180043670  pop     rdi
0x180043671  pop     rsi
0x180043672  pop     rbp
0x180043673  retn
```
