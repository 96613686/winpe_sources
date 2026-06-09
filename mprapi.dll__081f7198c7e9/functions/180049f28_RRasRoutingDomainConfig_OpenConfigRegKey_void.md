# RRasRoutingDomainConfig::OpenConfigRegKey(void)

- ea: `0x180049f28`
- end: `0x18004a1fb`
- name: `?OpenConfigRegKey@RRasRoutingDomainConfig@@QEAAKXZ`
- size: `723`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180047508`
- `0x180049728`
- `0x18004c448`

## callees

- `0x1800302d0`
- `0x180049f28`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a1a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a1b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a1a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a1b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a026`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a026`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004a0f7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004a0f7`

## string_xrefs

- `0x18004a018`: `System\CurrentControlSet\Services\RemoteAccess\RoutingDomains`
- `0x18004a061`: `System\CurrentControlSet\Services\RemoteAccess\RoutingDomains`
- `0x18004a06f`: `%s: RegOpenKeyEx (%s) failed: %d.`
- `0x180049fde`: `RRasRoutingDomainConfig::OpenConfigRegKey`
- `0x18004a068`: `RRasRoutingDomainConfig::OpenConfigRegKey`
- `0x18004a137`: `RRasRoutingDomainConfig::OpenConfigRegKey`
- `0x18004a13e`: `%s: RegCreateKeyEx failed for routing domain (%ws): %d.`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::OpenConfigRegKey(RRasRoutingDomainConfig *this)
{
  unsigned int v2; // edi
  void (*v3)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  GUID *v4; // rsi
  HKEY *v5; // rbx
  LSTATUS v6; // eax
  unsigned int v7; // ecx
  GUID *v8; // r9
  LSTATUS Key; // eax
  GUID *v10; // r9
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int v14; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v17; // [rsp+68h] [rbp-98h]
  __int128 v18; // [rsp+78h] [rbp-88h]
  __int64 v19; // [rsp+88h] [rbp-78h]
  int v20; // [rsp+90h] [rbp-70h]
  int v21; // [rsp+94h] [rbp-6Ch]
  GUID v22; // [rsp+98h] [rbp-68h] BYREF
  int v23; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v24; // [rsp+ACh] [rbp-54h]
  __int128 v25; // [rsp+BCh] [rbp-44h]
  int v26; // [rsp+CCh] [rbp-34h]
  WCHAR SubKey[40]; // [rsp+D0h] [rbp-30h] BYREF
  int v28; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v29[2044]; // [rsp+124h] [rbp+24h] BYREF

  v2 = 0;
  v14 = 0;
  hKey = 0;
  memset_0(SubKey, 0, sizeof(SubKey));
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
  v4 = (GUID *)((char *)this + 516);
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v16,
      L"RRasRoutingDomainConfig::OpenConfigRegKey",
      &v14,
      v3,
      (struct _GUID *)((char *)this + 516));
    v2 = v14;
  }
  v5 = (HKEY *)((char *)this + 824);
  if ( !*v5 )
  {
    v6 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains",
           0,
           0xF003Fu,
           &hKey);
    v7 = v6;
    v14 = v6;
    if ( v6 )
    {
      if ( (_QWORD)xmmword_180078C60 )
      {
        LOWORD(v28) = 0;
        v22 = GUID_NULL;
        LOWORD(v23) = 0;
        LODWORD(phkResult) = v6;
        FormatRRASErrorString(
          &v28,
          L"%s: RegOpenKeyEx (%s) failed: %d.",
          L"RRasRoutingDomainConfig::OpenConfigRegKey",
          L"System\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains",
          phkResult);
        v8 = &v22;
        if ( v4 )
          v8 = v4;
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_180078C60,
          &v28,
          v8,
          0,
          &v23);
        v7 = v14;
      }
    }
    else
    {
      MprConvertGuidToString(v4, 40, SubKey);
      Key = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0xF003Fu, 0, v5, 0);
      v7 = Key;
      v14 = Key;
      if ( Key || !*v5 )
      {
        if ( (_QWORD)xmmword_180078C60 )
        {
          LOWORD(v28) = 0;
          v22 = GUID_NULL;
          LOWORD(v23) = 0;
          LODWORD(phkResulta) = Key;
          FormatRRASErrorString(
            &v28,
            L"%s: RegCreateKeyEx failed for routing domain (%ws): %d.",
            L"RRasRoutingDomainConfig::OpenConfigRegKey",
            SubKey,
            phkResulta);
          v10 = &v22;
          if ( v4 )
            v10 = v4;
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
            gCfgStoreEtwContext,
            xmmword_180078C60,
            &v28,
            v10,
            0,
            &v23);
          v7 = v14;
        }
        if ( !v7 )
        {
          v7 = 6;
          v14 = 6;
        }
      }
    }
    if ( hKey )
    {
      RegCloseKey(hKey);
      v7 = v14;
    }
    if ( v7 && *v5 )
    {
      RegCloseKey(*v5);
      *v5 = 0;
      v7 = v14;
    }
    v2 = v7;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v16);
  return v2;
}

```

## disassembly

```asm
0x180049f28  mov     [rsp-8+arg_8], rbx
0x180049f2d  mov     [rsp-8+arg_10], rsi
0x180049f32  push    rbp
0x180049f33  push    rdi
0x180049f34  push    r14
0x180049f36  lea     rbp, [rsp-830h]
0x180049f3e  sub     rsp, 930h
0x180049f45  mov     rax, cs:__security_cookie
0x180049f4c  xor     rax, rsp
0x180049f4f  mov     [rbp+840h+var_20], rax
0x180049f56  mov     rbx, rcx
0x180049f59  xor     r14d, r14d
0x180049f5c  mov     edi, r14d
0x180049f5f  mov     [rsp+940h+var_8F0], r14d
0x180049f64  mov     [rsp+940h+hKey], r14
0x180049f69  xor     edx, edx; Val
0x180049f6b  lea     r8d, [r14+50h]; Size
0x180049f6f  lea     rcx, [rbp+840h+SubKey]; void *
0x180049f73  call    memset_0
0x180049f78  mov     [rbp+840h+var_820], r14d
0x180049f7c  xor     edx, edx; Val
0x180049f7e  mov     r8d, 7FCh; Size
0x180049f84  lea     rcx, [rbp+840h+var_81C]; void *
0x180049f88  call    memset_0
0x180049f8d  mov     [rbp+840h+var_898], r14d
0x180049f91  xorps   xmm0, xmm0
0x180049f94  xor     eax, eax
0x180049f96  movups  [rbp+840h+var_894], xmm0
0x180049f9a  movups  [rbp+840h+var_884], xmm0
0x180049f9e  mov     [rbp+840h+var_874], eax
0x180049fa1  movdqu  [rsp+940h+var_8D8], xmm0
0x180049fa7  mov     [rsp+940h+var_8E0], r14
0x180049fac  xorps   xmm1, xmm1
0x180049faf  movdqu  [rsp+940h+var_8C8], xmm1
0x180049fb5  mov     [rbp+840h+var_8B8], r14
0x180049fb9  mov     [rbp+840h+var_8B0], 0FFFFFFFFh
0x180049fc0  mov     [rbp+840h+var_8AC], r14d
0x180049fc4  lea     rsi, [rbx+204h]
0x180049fcb  cmp     qword ptr cs:xmmword_180078C60+8, r14
0x180049fd2  jz      short loc_180049FF3
0x180049fd4  mov     [rsp+940h+phkResult], rsi; struct _GUID *
0x180049fd9  lea     r8, [rsp+940h+var_8F0]; unsigned int *
0x180049fde  lea     rdx, aRrasroutingdom_39; "RRasRoutingDomainConfig::OpenConfigRegK"...
0x180049fe5  lea     rcx, [rsp+940h+var_8E0]; this
0x180049fea  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180049fef  mov     edi, [rsp+940h+var_8F0]
0x180049ff3  add     rbx, 338h
0x180049ffa  cmp     [rbx], r14
0x180049ffd  jnz     loc_18004A1C8
0x18004a003  lea     rax, [rsp+940h+hKey]
0x18004a008  mov     [rsp+940h+phkResult], rax; phkResult
0x18004a00d  mov     edi, 0F003Fh
0x18004a012  mov     r9d, edi; samDesired
0x18004a015  xor     r8d, r8d; ulOptions
0x18004a018  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Re"...
0x18004a01f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004a026  call    cs:__imp_RegOpenKeyExW
0x18004a02c  mov     ecx, eax
0x18004a02e  mov     [rsp+940h+var_8F0], eax
0x18004a032  test    eax, eax
0x18004a034  jz      loc_18004A0BF
0x18004a03a  cmp     qword ptr cs:xmmword_180078C60, r14
0x18004a041  jz      loc_18004A196
0x18004a047  mov     word ptr [rbp+840h+var_820], r14w
0x18004a04c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004a053  movdqu  [rbp+840h+var_8A8], xmm0
0x18004a058  mov     word ptr [rbp+840h+var_898], r14w
0x18004a05d  mov     dword ptr [rsp+940h+phkResult], eax
0x18004a061  lea     r9, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Re"...
0x18004a068  lea     r8, aRrasroutingdom_39; "RRasRoutingDomainConfig::OpenConfigRegK"...
0x18004a06f  lea     rdx, aSRegopenkeyexS_0; "%s: RegOpenKeyEx (%s) failed: %d."
0x18004a076  lea     rcx, [rbp+840h+var_820]
0x18004a07a  call    FormatRRASErrorString
0x18004a07f  lea     r9, [rbp+840h+var_8A8]
0x18004a083  test    rsi, rsi
0x18004a086  cmovnz  r9, rsi
0x18004a08a  lea     rax, [rbp+840h+var_898]
0x18004a08e  mov     qword ptr [rsp+940h+samDesired], rax
0x18004a093  mov     [rsp+940h+phkResult], r14
0x18004a098  lea     r8, [rbp+840h+var_820]
0x18004a09c  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004a0a3  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004a0aa  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004a0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a0b6  mov     ecx, [rsp+940h+var_8F0]
0x18004a0ba  jmp     loc_18004A196
0x18004a0bf  lea     r8, [rbp+840h+SubKey]
0x18004a0c3  mov     edx, 28h ; '('
0x18004a0c8  mov     rcx, rsi
0x18004a0cb  call    MprConvertGuidToString
0x18004a0d0  mov     [rsp+940h+lpdwDisposition], r14; lpdwDisposition
0x18004a0d5  mov     [rsp+940h+var_908], rbx; phkResult
0x18004a0da  mov     [rsp+940h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18004a0df  mov     [rsp+940h+samDesired], edi; samDesired
0x18004a0e3  mov     dword ptr [rsp+940h+phkResult], r14d; dwOptions
0x18004a0e8  xor     r9d, r9d; lpClass
0x18004a0eb  xor     r8d, r8d; Reserved
0x18004a0ee  lea     rdx, [rbp+840h+SubKey]; lpSubKey
0x18004a0f2  mov     rcx, [rsp+940h+hKey]; hKey
0x18004a0f7  call    cs:__imp_RegCreateKeyExW
0x18004a0fd  mov     ecx, eax
0x18004a0ff  mov     [rsp+940h+var_8F0], eax
0x18004a103  test    eax, eax
0x18004a105  jnz     short loc_18004A110
0x18004a107  cmp     [rbx], r14
0x18004a10a  jnz     loc_18004A196
0x18004a110  cmp     qword ptr cs:xmmword_180078C60, r14
0x18004a117  jz      short loc_18004A189
0x18004a119  mov     word ptr [rbp+840h+var_820], r14w
0x18004a11e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004a125  movdqu  [rbp+840h+var_8A8], xmm0
0x18004a12a  mov     word ptr [rbp+840h+var_898], r14w
0x18004a12f  mov     dword ptr [rsp+940h+phkResult], eax
0x18004a133  lea     r9, [rbp+840h+SubKey]
0x18004a137  lea     r8, aRrasroutingdom_39; "RRasRoutingDomainConfig::OpenConfigRegK"...
0x18004a13e  lea     rdx, aSRegcreatekeye_3; "%s: RegCreateKeyEx failed for routing d"...
0x18004a145  lea     rcx, [rbp+840h+var_820]
0x18004a149  call    FormatRRASErrorString
0x18004a14e  lea     r9, [rbp+840h+var_8A8]
0x18004a152  test    rsi, rsi
0x18004a155  cmovnz  r9, rsi
0x18004a159  lea     rax, [rbp+840h+var_898]
0x18004a15d  mov     qword ptr [rsp+940h+samDesired], rax
0x18004a162  mov     [rsp+940h+phkResult], r14
0x18004a167  lea     r8, [rbp+840h+var_820]
0x18004a16b  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004a172  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004a179  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004a180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a185  mov     ecx, [rsp+940h+var_8F0]
0x18004a189  test    ecx, ecx
0x18004a18b  jnz     short loc_18004A196
0x18004a18d  mov     ecx, 6
0x18004a192  mov     [rsp+940h+var_8F0], ecx
0x18004a196  mov     rax, [rsp+940h+hKey]
0x18004a19b  test    rax, rax
0x18004a19e  jz      short loc_18004A1AD
0x18004a1a0  mov     rcx, rax; hKey
0x18004a1a3  call    cs:__imp_RegCloseKey
0x18004a1a9  mov     ecx, [rsp+940h+var_8F0]
0x18004a1ad  test    ecx, ecx
0x18004a1af  jz      short loc_18004A1C6
0x18004a1b1  cmp     [rbx], r14
0x18004a1b4  jz      short loc_18004A1C6
0x18004a1b6  mov     rcx, [rbx]; hKey
0x18004a1b9  call    cs:__imp_RegCloseKey
0x18004a1bf  mov     [rbx], r14
0x18004a1c2  mov     ecx, [rsp+940h+var_8F0]
0x18004a1c6  mov     edi, ecx
0x18004a1c8  lea     rcx, [rsp+940h+var_8E0]; this
0x18004a1cd  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18004a1d2  mov     eax, edi
0x18004a1d4  mov     rcx, [rbp+840h+var_20]
0x18004a1db  xor     rcx, rsp; StackCookie
0x18004a1de  call    __security_check_cookie
0x18004a1e3  lea     r11, [rsp+940h+var_10]
0x18004a1eb  mov     rbx, [r11+28h]
0x18004a1ef  mov     rsi, [r11+30h]
0x18004a1f3  mov     rsp, r11
0x18004a1f6  pop     r14
0x18004a1f8  pop     rdi
0x18004a1f9  pop     rbp
0x18004a1fa  retn
```
