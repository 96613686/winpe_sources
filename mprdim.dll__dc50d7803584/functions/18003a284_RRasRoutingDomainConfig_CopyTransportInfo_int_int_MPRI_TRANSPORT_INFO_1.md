# RRasRoutingDomainConfig::CopyTransportInfo(int,int,_MPRI_TRANSPORT_INFO_1 *)

- ea: `0x18003a284`
- end: `0x18003a4cf`
- name: `?CopyTransportInfo@RRasRoutingDomainConfig@@AEAAKHHPEAU_MPRI_TRANSPORT_INFO_1@@@Z`
- size: `587`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, __int64, int, struct _MPRI_TRANSPORT_INFO_1 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180038f98`
- `0x18003c810`

## callees

- `0x180033f64`
- `0x18003a284`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18003a37b`
- `ADVAPI32!RegOpenKeyExW` at `0x18003a37b`
- `ADVAPI32!RegCloseKey` at `0x18003a48e`
- `ADVAPI32!RegCloseKey` at `0x18003a48e`

## string_xrefs

- `0x18003a39a`: `%s: RegOpenKeyEx (%s) failed: %d.`
- `0x18003a339`: `RRasRoutingDomainConfig::CopyTransportInfo`
- `0x18003a3aa`: `RRasRoutingDomainConfig::CopyTransportInfo`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RRasRoutingDomainConfig::CopyTransportInfo(
        RRasRoutingDomainConfig *this,
        __int64 a2,
        int a3,
        struct _MPRI_TRANSPORT_INFO_1 *a4)
{
  void (*v7)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  const WCHAR *v8; // rsi
  LSTATUS Binary; // eax
  const WCHAR *v10; // r9
  const wchar_t *v11; // rdx
  GUID *v12; // r9
  unsigned int v13; // ebx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v16; // [rsp+28h] [rbp-D8h]
  unsigned int v17; // [rsp+30h] [rbp-D0h]
  unsigned int v18; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v21; // [rsp+58h] [rbp-A8h]
  __int128 v22; // [rsp+68h] [rbp-98h]
  __int64 v23; // [rsp+78h] [rbp-88h]
  int v24; // [rsp+80h] [rbp-80h]
  int v25; // [rsp+84h] [rbp-7Ch]
  GUID v26; // [rsp+88h] [rbp-78h] BYREF
  int v27; // [rsp+98h] [rbp-68h] BYREF
  __int128 v28; // [rsp+9Ch] [rbp-64h]
  __int128 v29; // [rsp+ACh] [rbp-54h]
  int v30; // [rsp+BCh] [rbp-44h]
  int v31; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v32[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v18 = 0;
  hKey = 0;
  v31 = 0;
  memset_0(v32, 0, sizeof(v32));
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v21 = 0;
  v20 = 0;
  v22 = 0;
  v23 = 0;
  v24 = -1;
  v25 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v20,
      L"RRasRoutingDomainConfig::CopyTransportInfo",
      &v18,
      v7,
      (struct _GUID *)((char *)this + 516),
      v16,
      v17);
  v8 = L"Ipv4";
  if ( !a3 )
    v8 = L"Ipv6";
  Binary = RegOpenKeyExW(*((HKEY *)this + 103), v8, 0, 0x20019u, &hKey);
  v18 = Binary;
  if ( Binary )
  {
    if ( !(_QWORD)xmmword_1800710A0 )
      goto LABEL_15;
    v10 = v8;
    v11 = L"%s: RegOpenKeyEx (%s) failed: %d.";
  }
  else
  {
    Binary = RegGetBinary(hKey, L"GlobalInfo", (__int64)a4 + 4, (__int64)a4 + 8);
    v18 = Binary;
    if ( !Binary )
    {
      *(_DWORD *)a4 = a3 != 0 ? 33 : 87;
      goto LABEL_15;
    }
    if ( !(_QWORD)xmmword_1800710A0 )
      goto LABEL_15;
    v10 = L"GlobalInfo";
    v11 = L"%s: RegGetBinary (%s) failed: %d.";
  }
  LODWORD(phkResult) = Binary;
  LOWORD(v27) = 0;
  v26 = GUID_NULL;
  LOWORD(v31) = 0;
  FormatRRASErrorString(&v31, v11, L"RRasRoutingDomainConfig::CopyTransportInfo", v10, phkResult);
  v12 = &v26;
  if ( this != (RRasRoutingDomainConfig *)-516LL )
    v12 = (GUID *)((char *)this + 516);
  ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
    gCfgStoreEtwContext,
    xmmword_1800710A0,
    &v31,
    v12,
    0,
    &v27);
LABEL_15:
  if ( hKey )
    RegCloseKey(hKey);
  v13 = v18;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v20);
  return v13;
}

```

## disassembly

```asm
0x18003a284  mov     [rsp-8+arg_8], rbx
0x18003a289  mov     [rsp-8+arg_10], rsi
0x18003a28e  push    rbp
0x18003a28f  push    rdi
0x18003a290  push    r12
0x18003a292  push    r14
0x18003a294  push    r15
0x18003a296  lea     rbp, [rsp-7D0h]
0x18003a29e  sub     rsp, 8D0h
0x18003a2a5  mov     rax, cs:__security_cookie
0x18003a2ac  xor     rax, rsp
0x18003a2af  mov     [rbp+7F0h+var_30], rax
0x18003a2b6  mov     r14, r9
0x18003a2b9  mov     edi, r8d
0x18003a2bc  mov     r12d, edx
0x18003a2bf  mov     r15, rcx
0x18003a2c2  mov     [rsp+8F0h+var_8B0], 0
0x18003a2ca  mov     [rsp+8F0h+hKey], 0
0x18003a2d3  xor     eax, eax
0x18003a2d5  mov     [rbp+7F0h+var_830], eax
0x18003a2d8  xor     edx, edx; Val
0x18003a2da  mov     r8d, 7FCh; Size
0x18003a2e0  lea     rcx, [rbp+7F0h+var_82C]; void *
0x18003a2e4  call    memset_0
0x18003a2e9  xor     eax, eax
0x18003a2eb  mov     [rbp+7F0h+var_858], eax
0x18003a2ee  xorps   xmm0, xmm0
0x18003a2f1  movups  [rbp+7F0h+var_854], xmm0
0x18003a2f5  movups  [rbp+7F0h+var_844], xmm0
0x18003a2f9  mov     [rbp+7F0h+var_834], eax
0x18003a2fc  movdqu  [rsp+8F0h+var_898], xmm0
0x18003a302  mov     [rsp+8F0h+var_8A0], rax
0x18003a307  xorps   xmm1, xmm1
0x18003a30a  movdqu  [rsp+8F0h+var_888], xmm1
0x18003a310  mov     [rsp+8F0h+var_878], rax
0x18003a315  mov     [rbp+7F0h+var_870], 0FFFFFFFFh
0x18003a31c  mov     [rbp+7F0h+var_86C], eax
0x18003a31f  lea     rbx, [r15+204h]
0x18003a326  cmp     qword ptr cs:xmmword_1800710A0+8, rax
0x18003a32d  jz      short loc_18003A34A
0x18003a32f  mov     [rsp+8F0h+phkResult], rbx; struct _GUID *
0x18003a334  lea     r8, [rsp+8F0h+var_8B0]; unsigned int *
0x18003a339  lea     rdx, aRrasroutingdom_7; "RRasRoutingDomainConfig::CopyTransportI"...
0x18003a340  lea     rcx, [rsp+8F0h+var_8A0]; this
0x18003a345  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18003a34a  lea     rax, aIpv6; "Ipv6"
0x18003a351  lea     rsi, aIpv4; "Ipv4"
0x18003a358  test    edi, edi
0x18003a35a  cmovz   rsi, rax
0x18003a35e  lea     rax, [rsp+8F0h+hKey]
0x18003a363  mov     [rsp+8F0h+phkResult], rax; phkResult
0x18003a368  mov     r9d, 20019h; samDesired
0x18003a36e  xor     r8d, r8d; ulOptions
0x18003a371  mov     rdx, rsi; lpSubKey
0x18003a374  mov     rcx, [r15+338h]; hKey
0x18003a37b  call    cs:__imp_RegOpenKeyExW
0x18003a381  mov     [rsp+8F0h+var_8B0], eax
0x18003a385  test    eax, eax
0x18003a387  jz      short loc_18003A408
0x18003a389  cmp     qword ptr cs:xmmword_1800710A0, 0
0x18003a391  jz      loc_18003A484
0x18003a397  mov     r9, rsi
0x18003a39a  lea     rdx, aSRegopenkeyexS_0; "%s: RegOpenKeyEx (%s) failed: %d."
0x18003a3a1  xor     ecx, ecx
0x18003a3a3  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003a3aa  lea     r8, aRrasroutingdom_7; "RRasRoutingDomainConfig::CopyTransportI"...
0x18003a3b1  mov     dword ptr [rsp+8F0h+phkResult], eax
0x18003a3b5  mov     word ptr [rbp+7F0h+var_858], cx
0x18003a3b9  movdqu  [rbp+7F0h+var_868], xmm0
0x18003a3be  mov     word ptr [rbp+7F0h+var_830], cx
0x18003a3c2  lea     rcx, [rbp+7F0h+var_830]
0x18003a3c6  call    FormatRRASErrorString
0x18003a3cb  lea     r9, [rbp+7F0h+var_868]
0x18003a3cf  test    rbx, rbx
0x18003a3d2  cmovnz  r9, rbx
0x18003a3d6  lea     rax, [rbp+7F0h+var_858]
0x18003a3da  mov     [rsp+8F0h+var_8C8], rax
0x18003a3df  mov     [rsp+8F0h+phkResult], 0
0x18003a3e8  lea     r8, [rbp+7F0h+var_830]
0x18003a3ec  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003a3f3  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003a3fa  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003a401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a406  jmp     short loc_18003A484
0x18003a408  lea     rax, [r14+8]
0x18003a40c  lea     rcx, [r14+4]
0x18003a410  lea     rdx, MprCommonFree
0x18003a417  lea     r9, ?ConfigStoreRpcFree@@YAXPEAX@Z; ConfigStoreRpcFree(void *)
0x18003a41e  test    r12d, r12d
0x18003a421  cmovz   r9, rdx
0x18003a425  lea     rdx, ?ConfigStoreAlloc@@YAPEAXK@Z; ConfigStoreAlloc(ulong)
0x18003a42c  lea     r8, ?RouterRpcAlloc@@YAPEAXK@Z; RouterRpcAlloc(ulong)
0x18003a433  cmovz   r8, rdx
0x18003a437  mov     [rsp+8F0h+var_8C8], rax; __int64
0x18003a43c  mov     [rsp+8F0h+phkResult], rcx; __int64
0x18003a441  lea     rdx, aGlobalinfo; "GlobalInfo"
0x18003a448  mov     rcx, [rsp+8F0h+hKey]; hkey
0x18003a44d  call    RegGetBinary
0x18003a452  mov     [rsp+8F0h+var_8B0], eax
0x18003a456  test    eax, eax
0x18003a458  jz      short loc_18003A477
0x18003a45a  cmp     qword ptr cs:xmmword_1800710A0, 0
0x18003a462  jz      short loc_18003A484
0x18003a464  lea     r9, aGlobalinfo; "GlobalInfo"
0x18003a46b  lea     rdx, aSReggetbinaryS; "%s: RegGetBinary (%s) failed: %d."
0x18003a472  jmp     loc_18003A3A1
0x18003a477  neg     edi
0x18003a479  sbb     eax, eax
0x18003a47b  and     eax, 0FFFFFFCAh
0x18003a47e  add     eax, 57h ; 'W'
0x18003a481  mov     [r14], eax
0x18003a484  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18003a489  test    rcx, rcx
0x18003a48c  jz      short loc_18003A494
0x18003a48e  call    cs:__imp_RegCloseKey
0x18003a494  mov     ebx, [rsp+8F0h+var_8B0]
0x18003a498  lea     rcx, [rsp+8F0h+var_8A0]; this
0x18003a49d  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003a4a2  mov     eax, ebx
0x18003a4a4  mov     rcx, [rbp+7F0h+var_30]
0x18003a4ab  xor     rcx, rsp; StackCookie
0x18003a4ae  call    __security_check_cookie
0x18003a4b3  lea     r11, [rsp+8F0h+var_20]
0x18003a4bb  mov     rbx, [r11+38h]
0x18003a4bf  mov     rsi, [r11+40h]
0x18003a4c3  mov     rsp, r11
0x18003a4c6  pop     r15
0x18003a4c8  pop     r14
0x18003a4ca  pop     r12
0x18003a4cc  pop     rdi
0x18003a4cd  pop     rbp
0x18003a4ce  retn
```
