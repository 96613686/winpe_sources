# RRasRoutingDomainConfig::UpdateTransportInfo(_MPRI_TRANSPORT_INFO_1 *)

- ea: `0x18004e6f0`
- end: `0x18004e904`
- name: `?UpdateTransportInfo@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_TRANSPORT_INFO_1@@@Z`
- size: `532`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, struct _MPRI_TRANSPORT_INFO_1 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18004c944`
- `0x18004d60c`

## callees

- `0x18004e6f0`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e8c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e8c8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004e838`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004e838`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004e7ec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004e7ec`

## string_xrefs

- `0x18004e856`: `%s: Couldn't write value %s: %d`
- `0x18004e795`: `RRasRoutingDomainConfig::UpdateTransportInfo`
- `0x18004e877`: `RRasRoutingDomainConfig::UpdateTransportInfo`
- `0x18004e80a`: `%s: RegCreateKeyEx (%s) failed: %d.`

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
  unsigned int v13; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v15; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v16; // [rsp+68h] [rbp-98h]
  __int128 v17; // [rsp+78h] [rbp-88h]
  __int64 v18; // [rsp+88h] [rbp-78h]
  int v19; // [rsp+90h] [rbp-70h]
  int v20; // [rsp+94h] [rbp-6Ch]
  GUID v21; // [rsp+98h] [rbp-68h] BYREF
  int v22; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v23; // [rsp+ACh] [rbp-54h]
  __int128 v24; // [rsp+BCh] [rbp-44h]
  int v25; // [rsp+CCh] [rbp-34h]
  int v26; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v27[2044]; // [rsp+D4h] [rbp-2Ch] BYREF

  v13 = 0;
  hKey = 0;
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v16 = 0;
  v15 = 0;
  v17 = 0;
  v18 = 0;
  v19 = -1;
  v20 = 0;
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v15,
      L"RRasRoutingDomainConfig::UpdateTransportInfo",
      &v13,
      v4,
      (struct _GUID *)((char *)this + 516));
  v5 = L"Ipv4";
  if ( *(_DWORD *)a2 != 33 )
    v5 = L"Ipv6";
  v6 = RegCreateKeyExW(*((HKEY *)this + 103), v5, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  v13 = v6;
  if ( v6 )
  {
    if ( !(_QWORD)xmmword_180078C60 )
      goto LABEL_14;
    v7 = v5;
    v8 = L"%s: RegCreateKeyEx (%s) failed: %d.";
  }
  else
  {
    v6 = RegSetValueExW(hKey, L"GlobalInfo", 0, 3u, *((const BYTE **)a2 + 1), *((_DWORD *)a2 + 1));
    v13 = v6;
    if ( !v6 || !(_QWORD)xmmword_180078C60 )
      goto LABEL_14;
    v7 = L"GlobalInfo";
    v8 = L"%s: Couldn't write value %s: %d";
  }
  dwOptions[0] = v6;
  LOWORD(v26) = 0;
  v21 = GUID_NULL;
  LOWORD(v22) = 0;
  FormatRRASErrorString(&v26, v8, L"RRasRoutingDomainConfig::UpdateTransportInfo", v7, *(_QWORD *)dwOptions);
  v9 = &v21;
  if ( this != (RRasRoutingDomainConfig *)-516LL )
    v9 = (GUID *)((char *)this + 516);
  ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
    gCfgStoreEtwContext,
    xmmword_180078C60,
    &v26,
    v9,
    0,
    &v22);
LABEL_14:
  if ( hKey )
    RegCloseKey(hKey);
  v10 = v13;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v15);
  return v10;
}

```

## disassembly

```asm
0x18004e6f0  mov     [rsp-8+arg_10], rbx
0x18004e6f5  push    rbp
0x18004e6f6  push    rsi
0x18004e6f7  push    rdi
0x18004e6f8  push    r14
0x18004e6fa  push    r15
0x18004e6fc  lea     rbp, [rsp-7E0h]
0x18004e704  sub     rsp, 8E0h
0x18004e70b  mov     rax, cs:__security_cookie
0x18004e712  xor     rax, rsp
0x18004e715  mov     [rbp+800h+var_30], rax
0x18004e71c  mov     rsi, rdx
0x18004e71f  mov     r14, rcx
0x18004e722  xor     r15d, r15d
0x18004e725  mov     [rsp+900h+var_8B0], r15d
0x18004e72a  mov     [rsp+900h+hKey], r15
0x18004e72f  mov     [rbp+800h+var_830], r15d
0x18004e733  xor     edx, edx; Val
0x18004e735  mov     r8d, 7FCh; Size
0x18004e73b  lea     rcx, [rbp+800h+var_82C]; void *
0x18004e73f  call    memset_0
0x18004e744  mov     [rbp+800h+var_858], r15d
0x18004e748  xorps   xmm0, xmm0
0x18004e74b  xor     eax, eax
0x18004e74d  movups  [rbp+800h+var_854], xmm0
0x18004e751  movups  [rbp+800h+var_844], xmm0
0x18004e755  mov     [rbp+800h+var_834], eax
0x18004e758  movdqu  [rsp+900h+var_898], xmm0
0x18004e75e  mov     [rsp+900h+var_8A0], r15
0x18004e763  xorps   xmm1, xmm1
0x18004e766  movdqu  [rsp+900h+var_888], xmm1
0x18004e76c  mov     [rbp+800h+var_878], r15
0x18004e770  mov     [rbp+800h+var_870], 0FFFFFFFFh
0x18004e777  mov     [rbp+800h+var_86C], r15d
0x18004e77b  lea     rbx, [r14+204h]
0x18004e782  cmp     qword ptr cs:xmmword_180078C60+8, r15
0x18004e789  jz      short loc_18004E7A6
0x18004e78b  mov     qword ptr [rsp+900h+dwOptions], rbx; struct _GUID *
0x18004e790  lea     r8, [rsp+900h+var_8B0]; unsigned int *
0x18004e795  lea     rdx, aRrasroutingdom_41; "RRasRoutingDomainConfig::UpdateTranspor"...
0x18004e79c  lea     rcx, [rsp+900h+var_8A0]; this
0x18004e7a1  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18004e7a6  lea     rax, aIpv6; "Ipv6"
0x18004e7ad  lea     rdi, aIpv4; "Ipv4"
0x18004e7b4  cmp     dword ptr [rsi], 21h ; '!'
0x18004e7b7  cmovnz  rdi, rax
0x18004e7bb  mov     [rsp+900h+lpdwDisposition], r15; lpdwDisposition
0x18004e7c0  lea     rax, [rsp+900h+hKey]
0x18004e7c5  mov     [rsp+900h+phkResult], rax; phkResult
0x18004e7ca  mov     [rsp+900h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18004e7cf  mov     [rsp+900h+samDesired], 20006h; samDesired
0x18004e7d7  mov     [rsp+900h+dwOptions], r15d; dwOptions
0x18004e7dc  xor     r9d, r9d; lpClass
0x18004e7df  xor     r8d, r8d; Reserved
0x18004e7e2  mov     rdx, rdi; lpSubKey
0x18004e7e5  mov     rcx, [r14+338h]; hKey
0x18004e7ec  call    cs:__imp_RegCreateKeyExW
0x18004e7f2  mov     [rsp+900h+var_8B0], eax
0x18004e7f6  test    eax, eax
0x18004e7f8  jz      short loc_18004E813
0x18004e7fa  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004e801  jz      loc_18004E8BE
0x18004e807  mov     r9, rdi
0x18004e80a  lea     rdx, aSRegcreatekeye_1; "%s: RegCreateKeyEx (%s) failed: %d."
0x18004e811  jmp     short loc_18004E85D
0x18004e813  mov     eax, [rsi+4]
0x18004e816  mov     [rsp+900h+samDesired], eax; cbData
0x18004e81a  mov     rax, [rsi+8]
0x18004e81e  mov     qword ptr [rsp+900h+dwOptions], rax; lpData
0x18004e823  mov     r9d, 3; dwType
0x18004e829  xor     r8d, r8d; Reserved
0x18004e82c  lea     rdx, aGlobalinfo; "GlobalInfo"
0x18004e833  mov     rcx, [rsp+900h+hKey]; hKey
0x18004e838  call    cs:__imp_RegSetValueExW
0x18004e83e  mov     [rsp+900h+var_8B0], eax
0x18004e842  test    eax, eax
0x18004e844  jz      short loc_18004E8BE
0x18004e846  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004e84d  jz      short loc_18004E8BE
0x18004e84f  lea     r9, aGlobalinfo; "GlobalInfo"
0x18004e856  lea     rdx, aSCouldnTWriteV_0; "%s: Couldn't write value %s: %d"
0x18004e85d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004e864  mov     [rsp+900h+dwOptions], eax
0x18004e868  mov     word ptr [rbp+800h+var_830], r15w
0x18004e86d  movdqu  [rbp+800h+var_868], xmm0
0x18004e872  mov     word ptr [rbp+800h+var_858], r15w
0x18004e877  lea     r8, aRrasroutingdom_41; "RRasRoutingDomainConfig::UpdateTranspor"...
0x18004e87e  lea     rcx, [rbp+800h+var_830]
0x18004e882  call    FormatRRASErrorString
0x18004e887  lea     rax, [rbp+800h+var_858]
0x18004e88b  mov     qword ptr [rsp+900h+samDesired], rax
0x18004e890  lea     r9, [rbp+800h+var_868]
0x18004e894  test    rbx, rbx
0x18004e897  mov     qword ptr [rsp+900h+dwOptions], r15
0x18004e89c  cmovnz  r9, rbx
0x18004e8a0  lea     r8, [rbp+800h+var_830]
0x18004e8a4  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004e8ab  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004e8b2  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004e8b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e8be  mov     rcx, [rsp+900h+hKey]; hKey
0x18004e8c3  test    rcx, rcx
0x18004e8c6  jz      short loc_18004E8CE
0x18004e8c8  call    cs:__imp_RegCloseKey
0x18004e8ce  mov     ebx, [rsp+900h+var_8B0]
0x18004e8d2  lea     rcx, [rsp+900h+var_8A0]; this
0x18004e8d7  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18004e8dc  mov     eax, ebx
0x18004e8de  mov     rcx, [rbp+800h+var_30]
0x18004e8e5  xor     rcx, rsp; StackCookie
0x18004e8e8  call    __security_check_cookie
0x18004e8ed  mov     rbx, [rsp+900h+arg_10]
0x18004e8f5  add     rsp, 8E0h
0x18004e8fc  pop     r15
0x18004e8fe  pop     r14
0x18004e900  pop     rdi
0x18004e901  pop     rsi
0x18004e902  pop     rbp
0x18004e903  retn
```
