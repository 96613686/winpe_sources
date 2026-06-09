# RRasRoutingDomainConfig::CopyTransportInfo(int,int,_MPRI_TRANSPORT_INFO_1 *)

- ea: `0x180045c14`
- end: `0x180045e5f`
- name: `?CopyTransportInfo@RRasRoutingDomainConfig@@AEAAKHHPEAU_MPRI_TRANSPORT_INFO_1@@@Z`
- size: `587`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, __int64, int, struct _MPRI_TRANSPORT_INFO_1 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180044888`
- `0x180047ff4`

## callees

- `0x180030368`
- `0x180045c14`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045e1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045e1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045d0b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045d0b`

## string_xrefs

- `0x180045d2a`: `%s: RegOpenKeyEx (%s) failed: %d.`
- `0x180045cc9`: `RRasRoutingDomainConfig::CopyTransportInfo`
- `0x180045d3a`: `RRasRoutingDomainConfig::CopyTransportInfo`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
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
    if ( !(_QWORD)xmmword_180078C60 )
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
    if ( !(_QWORD)xmmword_180078C60 )
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
    xmmword_180078C60,
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
0x180045c14  mov     [rsp-8+arg_8], rbx
0x180045c19  mov     [rsp-8+arg_10], rsi
0x180045c1e  push    rbp
0x180045c1f  push    rdi
0x180045c20  push    r12
0x180045c22  push    r14
0x180045c24  push    r15
0x180045c26  lea     rbp, [rsp-7D0h]
0x180045c2e  sub     rsp, 8D0h
0x180045c35  mov     rax, cs:__security_cookie
0x180045c3c  xor     rax, rsp
0x180045c3f  mov     [rbp+7F0h+var_30], rax
0x180045c46  mov     r14, r9
0x180045c49  mov     edi, r8d
0x180045c4c  mov     r12d, edx
0x180045c4f  mov     r15, rcx
0x180045c52  mov     [rsp+8F0h+var_8B0], 0
0x180045c5a  mov     [rsp+8F0h+hKey], 0
0x180045c63  xor     eax, eax
0x180045c65  mov     [rbp+7F0h+var_830], eax
0x180045c68  xor     edx, edx; Val
0x180045c6a  mov     r8d, 7FCh; Size
0x180045c70  lea     rcx, [rbp+7F0h+var_82C]; void *
0x180045c74  call    memset_0
0x180045c79  xor     eax, eax
0x180045c7b  mov     [rbp+7F0h+var_858], eax
0x180045c7e  xorps   xmm0, xmm0
0x180045c81  movups  [rbp+7F0h+var_854], xmm0
0x180045c85  movups  [rbp+7F0h+var_844], xmm0
0x180045c89  mov     [rbp+7F0h+var_834], eax
0x180045c8c  movdqu  [rsp+8F0h+var_898], xmm0
0x180045c92  mov     [rsp+8F0h+var_8A0], rax
0x180045c97  xorps   xmm1, xmm1
0x180045c9a  movdqu  [rsp+8F0h+var_888], xmm1
0x180045ca0  mov     [rsp+8F0h+var_878], rax
0x180045ca5  mov     [rbp+7F0h+var_870], 0FFFFFFFFh
0x180045cac  mov     [rbp+7F0h+var_86C], eax
0x180045caf  lea     rbx, [r15+204h]
0x180045cb6  cmp     qword ptr cs:xmmword_180078C60+8, rax
0x180045cbd  jz      short loc_180045CDA
0x180045cbf  mov     [rsp+8F0h+phkResult], rbx; struct _GUID *
0x180045cc4  lea     r8, [rsp+8F0h+var_8B0]; unsigned int *
0x180045cc9  lea     rdx, aRrasroutingdom_7; "RRasRoutingDomainConfig::CopyTransportI"...
0x180045cd0  lea     rcx, [rsp+8F0h+var_8A0]; this
0x180045cd5  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180045cda  lea     rax, aIpv6; "Ipv6"
0x180045ce1  lea     rsi, aIpv4; "Ipv4"
0x180045ce8  test    edi, edi
0x180045cea  cmovz   rsi, rax
0x180045cee  lea     rax, [rsp+8F0h+hKey]
0x180045cf3  mov     [rsp+8F0h+phkResult], rax; phkResult
0x180045cf8  mov     r9d, 20019h; samDesired
0x180045cfe  xor     r8d, r8d; ulOptions
0x180045d01  mov     rdx, rsi; lpSubKey
0x180045d04  mov     rcx, [r15+338h]; hKey
0x180045d0b  call    cs:__imp_RegOpenKeyExW
0x180045d11  mov     [rsp+8F0h+var_8B0], eax
0x180045d15  test    eax, eax
0x180045d17  jz      short loc_180045D98
0x180045d19  cmp     qword ptr cs:xmmword_180078C60, 0
0x180045d21  jz      loc_180045E14
0x180045d27  mov     r9, rsi
0x180045d2a  lea     rdx, aSRegopenkeyexS_0; "%s: RegOpenKeyEx (%s) failed: %d."
0x180045d31  xor     ecx, ecx
0x180045d33  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180045d3a  lea     r8, aRrasroutingdom_7; "RRasRoutingDomainConfig::CopyTransportI"...
0x180045d41  mov     dword ptr [rsp+8F0h+phkResult], eax
0x180045d45  mov     word ptr [rbp+7F0h+var_858], cx
0x180045d49  movdqu  [rbp+7F0h+var_868], xmm0
0x180045d4e  mov     word ptr [rbp+7F0h+var_830], cx
0x180045d52  lea     rcx, [rbp+7F0h+var_830]
0x180045d56  call    FormatRRASErrorString
0x180045d5b  lea     r9, [rbp+7F0h+var_868]
0x180045d5f  test    rbx, rbx
0x180045d62  cmovnz  r9, rbx
0x180045d66  lea     rax, [rbp+7F0h+var_858]
0x180045d6a  mov     [rsp+8F0h+var_8C8], rax
0x180045d6f  mov     [rsp+8F0h+phkResult], 0
0x180045d78  lea     r8, [rbp+7F0h+var_830]
0x180045d7c  mov     rdx, qword ptr cs:xmmword_180078C60
0x180045d83  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180045d8a  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180045d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d96  jmp     short loc_180045E14
0x180045d98  lea     rax, [r14+8]
0x180045d9c  lea     rcx, [r14+4]
0x180045da0  lea     rdx, MprCommonFree
0x180045da7  lea     r9, ?ConfigStoreRpcFree@@YAXPEAX@Z; ConfigStoreRpcFree(void *)
0x180045dae  test    r12d, r12d
0x180045db1  cmovz   r9, rdx
0x180045db5  lea     rdx, ?ConfigStoreAlloc@@YAPEAXK@Z; ConfigStoreAlloc(ulong)
0x180045dbc  lea     r8, ?ConfigStoreRpcAlloc@@YAPEAXK@Z; ConfigStoreRpcAlloc(ulong)
0x180045dc3  cmovz   r8, rdx
0x180045dc7  mov     [rsp+8F0h+var_8C8], rax; __int64
0x180045dcc  mov     [rsp+8F0h+phkResult], rcx; __int64
0x180045dd1  lea     rdx, aGlobalinfo; "GlobalInfo"
0x180045dd8  mov     rcx, [rsp+8F0h+hKey]; hkey
0x180045ddd  call    RegGetBinary
0x180045de2  mov     [rsp+8F0h+var_8B0], eax
0x180045de6  test    eax, eax
0x180045de8  jz      short loc_180045E07
0x180045dea  cmp     qword ptr cs:xmmword_180078C60, 0
0x180045df2  jz      short loc_180045E14
0x180045df4  lea     r9, aGlobalinfo; "GlobalInfo"
0x180045dfb  lea     rdx, aSReggetbinaryS; "%s: RegGetBinary (%s) failed: %d."
0x180045e02  jmp     loc_180045D31
0x180045e07  neg     edi
0x180045e09  sbb     eax, eax
0x180045e0b  and     eax, 0FFFFFFCAh
0x180045e0e  add     eax, 57h ; 'W'
0x180045e11  mov     [r14], eax
0x180045e14  mov     rcx, [rsp+8F0h+hKey]; hKey
0x180045e19  test    rcx, rcx
0x180045e1c  jz      short loc_180045E24
0x180045e1e  call    cs:__imp_RegCloseKey
0x180045e24  mov     ebx, [rsp+8F0h+var_8B0]
0x180045e28  lea     rcx, [rsp+8F0h+var_8A0]; this
0x180045e2d  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180045e32  mov     eax, ebx
0x180045e34  mov     rcx, [rbp+7F0h+var_30]
0x180045e3b  xor     rcx, rsp; StackCookie
0x180045e3e  call    __security_check_cookie
0x180045e43  lea     r11, [rsp+8F0h+var_20]
0x180045e4b  mov     rbx, [r11+38h]
0x180045e4f  mov     rsi, [r11+40h]
0x180045e53  mov     rsp, r11
0x180045e56  pop     r15
0x180045e58  pop     r14
0x180045e5a  pop     r12
0x180045e5c  pop     rdi
0x180045e5d  pop     rbp
0x180045e5e  retn
```
