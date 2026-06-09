# RRasRoutingDomainConfig::RemoveConfigurationFromRegistry(void)

- ea: `0x180041210`
- end: `0x18004148c`
- name: `?RemoveConfigurationFromRegistry@RRasRoutingDomainConfig@@QEAAKXZ`
- size: `636`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x18003b6d4`

## callees

- `0x180033e90`
- `0x180038eb8`
- `0x18003e984`
- `0x180041210`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `KERNEL32!RegDeleteKeyExW` at `0x1800413c8`
- `KERNEL32!RegDeleteKeyExW` at `0x1800413c8`
- `ADVAPI32!RegOpenKeyExW` at `0x18004137b`
- `ADVAPI32!RegOpenKeyExW` at `0x18004137b`
- `ADVAPI32!RegCloseKey` at `0x180041457`
- `ADVAPI32!RegCloseKey` at `0x180041457`
- `ADVAPI32!RegDeleteTreeW` at `0x18004132c`
- `ADVAPI32!RegDeleteTreeW` at `0x18004132c`

## string_xrefs

- `0x18004136d`: `System\CurrentControlSet\Services\RemoteAccess\RoutingDomains`
- `0x180041398`: `System\CurrentControlSet\Services\RemoteAccess\RoutingDomains`
- `0x18004139f`: `%s: RegOpenKeyEx (%s) failed: %d.`
- `0x1800412ac`: `RRasRoutingDomainConfig::RemoveConfigurationFromRegistry`
- `0x1800412f2`: `%s: Failed to open the routing domin key: %d.`
- `0x180041349`: `%s: RegDeleteTree failed: %d.`
- `0x1800413e5`: `%s: RegDeleteKeyEx  failed for (%ws): %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RRasRoutingDomainConfig::RemoveConfigurationFromRegistry(RRasRoutingDomainConfig *this)
{
  void (*v2)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int v3; // eax
  unsigned int v4; // ebx
  const wchar_t *v5; // rdx
  LSTATUS v6; // eax
  WCHAR *v7; // r9
  const wchar_t *v8; // rdx
  GUID *v9; // r9
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v12; // [rsp+28h] [rbp-D8h]
  unsigned int v13; // [rsp+30h] [rbp-D0h]
  unsigned int v14; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v17; // [rsp+58h] [rbp-A8h]
  __int128 v18; // [rsp+68h] [rbp-98h]
  __int64 v19; // [rsp+78h] [rbp-88h]
  int v20; // [rsp+80h] [rbp-80h]
  int v21; // [rsp+84h] [rbp-7Ch]
  GUID v22; // [rsp+88h] [rbp-78h] BYREF
  int v23; // [rsp+98h] [rbp-68h] BYREF
  __int128 v24; // [rsp+9Ch] [rbp-64h]
  __int128 v25; // [rsp+ACh] [rbp-54h]
  int v26; // [rsp+BCh] [rbp-44h]
  WCHAR SubKey[40]; // [rsp+C0h] [rbp-40h] BYREF
  int v28; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v29[2044]; // [rsp+114h] [rbp+14h] BYREF

  v14 = 0;
  memset_0(SubKey, 0, sizeof(SubKey));
  hKey = 0;
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v17 = 0;
  v16 = 0;
  v18 = 0;
  v19 = 0;
  v20 = -1;
  v21 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v16,
      L"RRasRoutingDomainConfig::RemoveConfigurationFromRegistry",
      &v14,
      v2,
      (struct _GUID *)((char *)this + 516),
      v12,
      v13);
  v3 = RRasRoutingDomainConfig::OpenConfigRegKey(this);
  v4 = v3;
  v14 = v3;
  if ( v3 )
  {
    if ( !(_QWORD)xmmword_1800710A0 )
      goto LABEL_20;
    v5 = L"%s: Failed to open the routing domin key: %d.";
LABEL_6:
    LOWORD(v23) = 0;
    v22 = GUID_NULL;
    LOWORD(v28) = 0;
    FormatRRASErrorString(&v28, v5, L"RRasRoutingDomainConfig::RemoveConfigurationFromRegistry", v3);
    goto LABEL_17;
  }
  v3 = RegDeleteTreeW(*((HKEY *)this + 103), 0);
  v4 = v3;
  v14 = v3;
  if ( v3 )
  {
    if ( !(_QWORD)xmmword_1800710A0 )
      goto LABEL_20;
    v5 = L"%s: RegDeleteTree failed: %d.";
    goto LABEL_6;
  }
  RRasRoutingDomainConfig::CloseConfigRegKey(this);
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains",
         0,
         0xF003Fu,
         &hKey);
  v4 = v6;
  v14 = v6;
  if ( v6 )
  {
    if ( !(_QWORD)xmmword_1800710A0 )
      goto LABEL_20;
    v7 = (WCHAR *)L"System\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains";
    v8 = L"%s: RegOpenKeyEx (%s) failed: %d.";
  }
  else
  {
    MprConvertGuidToString((char *)this + 516, 40, SubKey);
    v6 = RegDeleteKeyExW(hKey, SubKey, 0, 0);
    v4 = v6;
    v14 = v6;
    if ( !v6 || !(_QWORD)xmmword_1800710A0 )
      goto LABEL_20;
    v7 = SubKey;
    v8 = L"%s: RegDeleteKeyEx  failed for (%ws): %d.";
  }
  LODWORD(phkResult) = v6;
  LOWORD(v28) = 0;
  v22 = GUID_NULL;
  LOWORD(v23) = 0;
  FormatRRASErrorString(&v28, v8, L"RRasRoutingDomainConfig::RemoveConfigurationFromRegistry", v7, phkResult);
LABEL_17:
  v9 = &v22;
  if ( this != (RRasRoutingDomainConfig *)-516LL )
    v9 = (GUID *)((char *)this + 516);
  ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
    gCfgStoreEtwContext,
    xmmword_1800710A0,
    &v28,
    v9,
    0,
    &v23);
  v4 = v14;
LABEL_20:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v4 = v14;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v16);
  return v4;
}

```

## disassembly

```asm
0x180041210  push    rbp
0x180041212  push    rbx
0x180041213  push    rsi
0x180041214  push    rdi
0x180041215  push    r14
0x180041217  push    r15
0x180041219  lea     rbp, [rsp-828h]
0x180041221  sub     rsp, 928h
0x180041228  mov     rax, cs:__security_cookie
0x18004122f  xor     rax, rsp
0x180041232  mov     [rbp+850h+var_40], rax
0x180041239  mov     rsi, rcx
0x18004123c  xor     r14d, r14d
0x18004123f  mov     [rsp+950h+var_910], r14d
0x180041244  xor     edx, edx; Val
0x180041246  lea     r8d, [r14+50h]; Size
0x18004124a  lea     rcx, [rbp+850h+SubKey]; void *
0x18004124e  call    memset_0
0x180041253  mov     [rsp+950h+hKey], r14
0x180041258  mov     [rbp+850h+var_840], r14d
0x18004125c  xor     edx, edx; Val
0x18004125e  mov     r8d, 7FCh; Size
0x180041264  lea     rcx, [rbp+850h+var_83C]; void *
0x180041268  call    memset_0
0x18004126d  mov     [rbp+850h+var_8B8], r14d
0x180041271  xorps   xmm0, xmm0
0x180041274  xor     eax, eax
0x180041276  movups  [rbp+850h+var_8B4], xmm0
0x18004127a  movups  [rbp+850h+var_8A4], xmm0
0x18004127e  mov     [rbp+850h+var_894], eax
0x180041281  movdqu  [rsp+950h+var_8F8], xmm0
0x180041287  mov     [rsp+950h+var_900], r14
0x18004128c  xorps   xmm1, xmm1
0x18004128f  movdqu  [rsp+950h+var_8E8], xmm1
0x180041295  mov     [rsp+950h+var_8D8], r14
0x18004129a  mov     [rbp+850h+var_8D0], 0FFFFFFFFh
0x1800412a1  mov     [rbp+850h+var_8CC], r14d
0x1800412a5  lea     rdi, [rsi+204h]
0x1800412ac  lea     r15, aRrasroutingdom_50; "RRasRoutingDomainConfig::RemoveConfigur"...
0x1800412b3  cmp     qword ptr cs:xmmword_1800710A0+8, r14
0x1800412ba  jz      short loc_1800412D3
0x1800412bc  mov     [rsp+950h+phkResult], rdi; struct _GUID *
0x1800412c1  lea     r8, [rsp+950h+var_910]; unsigned int *
0x1800412c6  mov     rdx, r15; unsigned __int16 *
0x1800412c9  lea     rcx, [rsp+950h+var_900]; this
0x1800412ce  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x1800412d3  mov     rcx, rsi; this
0x1800412d6  call    ?OpenConfigRegKey@RRasRoutingDomainConfig@@QEAAKXZ; RRasRoutingDomainConfig::OpenConfigRegKey(void)
0x1800412db  mov     ebx, eax
0x1800412dd  mov     [rsp+950h+var_910], eax
0x1800412e1  test    eax, eax
0x1800412e3  jz      short loc_180041323
0x1800412e5  cmp     qword ptr cs:xmmword_1800710A0, r14
0x1800412ec  jz      loc_18004144D
0x1800412f2  lea     rdx, aSFailedToOpenT; "%s: Failed to open the routing domin ke"...
0x1800412f9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180041300  mov     r8, r15
0x180041303  mov     r9d, eax
0x180041306  mov     word ptr [rbp+850h+var_8B8], r14w
0x18004130b  movdqu  [rbp+850h+var_8C8], xmm0
0x180041310  mov     word ptr [rbp+850h+var_840], r14w
0x180041315  lea     rcx, [rbp+850h+var_840]
0x180041319  call    FormatRRASErrorString
0x18004131e  jmp     loc_180041412
0x180041323  xor     edx, edx; lpSubKey
0x180041325  mov     rcx, [rsi+338h]; hKey
0x18004132c  call    cs:__imp_RegDeleteTreeW
0x180041332  mov     ebx, eax
0x180041334  mov     [rsp+950h+var_910], eax
0x180041338  test    eax, eax
0x18004133a  jz      short loc_180041352
0x18004133c  cmp     qword ptr cs:xmmword_1800710A0, r14
0x180041343  jz      loc_18004144D
0x180041349  lea     rdx, aSRegdeletetree; "%s: RegDeleteTree failed: %d."
0x180041350  jmp     short loc_1800412F9
0x180041352  mov     rcx, rsi; this
0x180041355  call    ?CloseConfigRegKey@RRasRoutingDomainConfig@@AEAAXXZ; RRasRoutingDomainConfig::CloseConfigRegKey(void)
0x18004135a  lea     rax, [rsp+950h+hKey]
0x18004135f  mov     [rsp+950h+phkResult], rax; phkResult
0x180041364  mov     r9d, 0F003Fh; samDesired
0x18004136a  xor     r8d, r8d; ulOptions
0x18004136d  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Re"...
0x180041374  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004137b  call    cs:__imp_RegOpenKeyExW
0x180041381  mov     ebx, eax
0x180041383  mov     [rsp+950h+var_910], eax
0x180041387  test    eax, eax
0x180041389  jz      short loc_1800413A8
0x18004138b  cmp     qword ptr cs:xmmword_1800710A0, r14
0x180041392  jz      loc_18004144D
0x180041398  lea     r9, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Re"...
0x18004139f  lea     rdx, aSRegopenkeyexS_0; "%s: RegOpenKeyEx (%s) failed: %d."
0x1800413a6  jmp     short loc_1800413EC
0x1800413a8  lea     r8, [rbp+850h+SubKey]
0x1800413ac  mov     edx, 28h ; '('
0x1800413b1  mov     rcx, rdi
0x1800413b4  call    MprConvertGuidToString
0x1800413b9  xor     r9d, r9d; Reserved
0x1800413bc  xor     r8d, r8d; samDesired
0x1800413bf  lea     rdx, [rbp+850h+SubKey]; lpSubKey
0x1800413c3  mov     rcx, [rsp+950h+hKey]; hKey
0x1800413c8  call    cs:__imp_RegDeleteKeyExW
0x1800413ce  mov     ebx, eax
0x1800413d0  mov     [rsp+950h+var_910], eax
0x1800413d4  test    eax, eax
0x1800413d6  jz      short loc_18004144D
0x1800413d8  cmp     qword ptr cs:xmmword_1800710A0, r14
0x1800413df  jz      short loc_18004144D
0x1800413e1  lea     r9, [rbp+850h+SubKey]
0x1800413e5  lea     rdx, aSRegdeletekeye; "%s: RegDeleteKeyEx  failed for (%ws): %"...
0x1800413ec  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800413f3  mov     dword ptr [rsp+950h+phkResult], eax
0x1800413f7  mov     word ptr [rbp+850h+var_840], r14w
0x1800413fc  movdqu  [rbp+850h+var_8C8], xmm0
0x180041401  mov     word ptr [rbp+850h+var_8B8], r14w
0x180041406  mov     r8, r15
0x180041409  lea     rcx, [rbp+850h+var_840]
0x18004140d  call    FormatRRASErrorString
0x180041412  lea     rax, [rbp+850h+var_8B8]
0x180041416  mov     [rsp+950h+var_928], rax
0x18004141b  lea     r9, [rbp+850h+var_8C8]
0x18004141f  test    rdi, rdi
0x180041422  mov     [rsp+950h+phkResult], r14
0x180041427  cmovnz  r9, rdi
0x18004142b  lea     r8, [rbp+850h+var_840]
0x18004142f  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180041436  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004143d  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180041444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041449  mov     ebx, [rsp+950h+var_910]
0x18004144d  mov     rcx, [rsp+950h+hKey]; hKey
0x180041452  test    rcx, rcx
0x180041455  jz      short loc_180041461
0x180041457  call    cs:__imp_RegCloseKey
0x18004145d  mov     ebx, [rsp+950h+var_910]
0x180041461  lea     rcx, [rsp+950h+var_900]; this
0x180041466  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18004146b  mov     eax, ebx
0x18004146d  mov     rcx, [rbp+850h+var_40]
0x180041474  xor     rcx, rsp; StackCookie
0x180041477  call    __security_check_cookie
0x18004147c  add     rsp, 928h
0x180041483  pop     r15
0x180041485  pop     r14
0x180041487  pop     rdi
0x180041488  pop     rsi
0x180041489  pop     rbx
0x18004148a  pop     rbp
0x18004148b  retn
```
