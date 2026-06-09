# RRasRoutingDomainConfig::UpdateIkev2Config(_IKEV2_TUNNEL_CONFIG_PARAMS_4 *)

- ea: `0x18004dd80`
- end: `0x18004dfd8`
- name: `?UpdateIkev2Config@RRasRoutingDomainConfig@@AEAAKPEAU_IKEV2_TUNNEL_CONFIG_PARAMS_4@@@Z`
- size: `600`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x18004c944`
- `0x18004d60c`

## callees

- `0x180030648`
- `0x18004dd80`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004df9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004df9b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004dee3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004dee3`

## string_xrefs

- `0x18004df01`: `%s: Failed to open ikev2 config reg key. error %d`
- `0x18004de2c`: `RRasRoutingDomainConfig::UpdateIkev2Config`
- `0x18004df4a`: `RRasRoutingDomainConfig::UpdateIkev2Config`
- `0x18004de6f`: `RRasRoutingDomainConfig::UpdateIkev2Config`
- `0x18004df2d`: `%s: SetIkev2ConfigParams Failed. error %d`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::UpdateIkev2Config(
        RRasRoutingDomainConfig *this,
        struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *a2)
{
  void (*v4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int v5; // eax
  __int64 v6; // r9
  const wchar_t *v7; // rdx
  unsigned int v8; // eax
  GUID *v9; // r9
  unsigned int v10; // ebx
  unsigned int v12; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+54h] [rbp-ACh] BYREF
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

  hKey = 0;
  v12 = 0;
  dwDisposition = 0;
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
      L"RRasRoutingDomainConfig::UpdateIkev2Config",
      &v12,
      v4,
      (struct _GUID *)((char *)this + 516));
  if ( *((_DWORD *)a2 + 8) && *((_DWORD *)a2 + 20) || *((_DWORD *)a2 + 5) )
  {
    v12 = 87;
    if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v26) = 0;
      FormatRRASErrorString(
        &v26,
        L"%hs(Line#%d): Invalid parameter.",
        "RRasRoutingDomainConfig::UpdateIkev2Config",
        3888);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
        &v26);
    }
  }
  else
  {
    v5 = RegCreateKeyExW(*((HKEY *)this + 103), L"IKEv2", 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition);
    v6 = v5;
    v12 = v5;
    if ( v5 )
    {
      if ( !(_QWORD)xmmword_180078C60 )
        goto LABEL_17;
      v7 = L"%s: Failed to open ikev2 config reg key. error %d";
    }
    else
    {
      v8 = SetIkev2ConfigParams(hKey);
      v6 = v8;
      v12 = v8;
      if ( !v8 || !(_QWORD)xmmword_180078C60 )
        goto LABEL_17;
      v7 = L"%s: SetIkev2ConfigParams Failed. error %d";
    }
    LOWORD(v26) = 0;
    v21 = GUID_NULL;
    LOWORD(v22) = 0;
    FormatRRASErrorString(&v26, v7, L"RRasRoutingDomainConfig::UpdateIkev2Config", v6);
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
  }
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  v10 = v12;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v15);
  return v10;
}

```

## disassembly

```asm
0x18004dd80  mov     [rsp-8+arg_10], rbx
0x18004dd85  mov     [rsp-8+arg_18], rsi
0x18004dd8a  push    rbp
0x18004dd8b  push    rdi
0x18004dd8c  push    r14
0x18004dd8e  lea     rbp, [rsp-7E0h]
0x18004dd96  sub     rsp, 8E0h
0x18004dd9d  mov     rax, cs:__security_cookie
0x18004dda4  xor     rax, rsp
0x18004dda7  mov     [rbp+7F0h+var_20], rax
0x18004ddae  mov     rbx, rdx
0x18004ddb1  mov     rsi, rcx
0x18004ddb4  xor     r14d, r14d
0x18004ddb7  mov     [rsp+8F0h+hKey], r14
0x18004ddbc  mov     [rsp+8F0h+var_8A0], r14d
0x18004ddc1  mov     [rsp+8F0h+dwDisposition], r14d
0x18004ddc6  mov     [rbp+7F0h+var_820], r14d
0x18004ddca  xor     edx, edx; Val
0x18004ddcc  mov     r8d, 7FCh; Size
0x18004ddd2  lea     rcx, [rbp+7F0h+var_81C]; void *
0x18004ddd6  call    memset_0
0x18004dddb  mov     [rbp+7F0h+var_848], r14d
0x18004dddf  xorps   xmm0, xmm0
0x18004dde2  xor     eax, eax
0x18004dde4  movups  [rbp+7F0h+var_844], xmm0
0x18004dde8  movups  [rbp+7F0h+var_834], xmm0
0x18004ddec  mov     [rbp+7F0h+var_824], eax
0x18004ddef  movdqu  [rsp+8F0h+var_888], xmm0
0x18004ddf5  mov     [rsp+8F0h+var_890], r14
0x18004ddfa  xorps   xmm1, xmm1
0x18004ddfd  movdqu  [rsp+8F0h+var_878], xmm1
0x18004de03  mov     [rbp+7F0h+var_868], r14
0x18004de07  mov     [rbp+7F0h+var_860], 0FFFFFFFFh
0x18004de0e  mov     [rbp+7F0h+var_85C], r14d
0x18004de12  lea     rdi, [rsi+204h]
0x18004de19  cmp     qword ptr cs:xmmword_180078C60+8, r14
0x18004de20  jz      short loc_18004DE3D
0x18004de22  mov     qword ptr [rsp+8F0h+dwOptions], rdi; struct _GUID *
0x18004de27  lea     r8, [rsp+8F0h+var_8A0]; unsigned int *
0x18004de2c  lea     rdx, aRrasroutingdom_6; "RRasRoutingDomainConfig::UpdateIkev2Con"...
0x18004de33  lea     rcx, [rsp+8F0h+var_890]; this
0x18004de38  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18004de3d  cmp     [rbx+20h], r14d
0x18004de41  jz      short loc_18004DE49
0x18004de43  cmp     [rbx+50h], r14d
0x18004de47  jnz     short loc_18004DE4F
0x18004de49  cmp     [rbx+14h], r14d
0x18004de4d  jz      short loc_18004DEA9
0x18004de4f  mov     [rsp+8F0h+var_8A0], 57h ; 'W'
0x18004de57  cmp     qword ptr cs:xmmword_180078C50, r14
0x18004de5e  jz      loc_18004DF91
0x18004de64  mov     word ptr [rbp+7F0h+var_820], r14w
0x18004de69  mov     r9d, 0F30h
0x18004de6f  lea     r8, aRrasroutingdom_0; "RRasRoutingDomainConfig::UpdateIkev2Con"...
0x18004de76  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18004de7d  lea     rcx, [rbp+7F0h+var_820]
0x18004de81  call    FormatRRASErrorString
0x18004de86  lea     r8, [rbp+7F0h+var_820]
0x18004de8a  mov     rdx, qword ptr cs:xmmword_180078C50
0x18004de91  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004de98  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004de9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dea4  jmp     loc_18004DF91
0x18004dea9  lea     rax, [rsp+8F0h+dwDisposition]
0x18004deae  mov     [rsp+8F0h+lpdwDisposition], rax; lpdwDisposition
0x18004deb3  lea     rax, [rsp+8F0h+hKey]
0x18004deb8  mov     [rsp+8F0h+phkResult], rax; phkResult
0x18004debd  mov     [rsp+8F0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18004dec2  mov     [rsp+8F0h+samDesired], 20006h; samDesired
0x18004deca  mov     [rsp+8F0h+dwOptions], r14d; dwOptions
0x18004decf  xor     r9d, r9d; lpClass
0x18004ded2  xor     r8d, r8d; Reserved
0x18004ded5  lea     rdx, aIkev2; "IKEv2"
0x18004dedc  mov     rcx, [rsi+338h]; hKey
0x18004dee3  call    cs:__imp_RegCreateKeyExW
0x18004dee9  mov     r9d, eax
0x18004deec  mov     [rsp+8F0h+var_8A0], eax
0x18004def0  test    eax, eax
0x18004def2  jz      short loc_18004DF0A
0x18004def4  cmp     qword ptr cs:xmmword_180078C60, r14
0x18004defb  jz      loc_18004DF91
0x18004df01  lea     rdx, aSFailedToOpenI; "%s: Failed to open ikev2 config reg key"...
0x18004df08  jmp     short loc_18004DF34
0x18004df0a  mov     r8, rbx
0x18004df0d  mov     dl, 5
0x18004df0f  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18004df14  call    SetIkev2ConfigParams
0x18004df19  mov     r9d, eax
0x18004df1c  mov     [rsp+8F0h+var_8A0], eax
0x18004df20  test    eax, eax
0x18004df22  jz      short loc_18004DF91
0x18004df24  cmp     qword ptr cs:xmmword_180078C60, r14
0x18004df2b  jz      short loc_18004DF91
0x18004df2d  lea     rdx, aSSetikev2confi; "%s: SetIkev2ConfigParams Failed. error "...
0x18004df34  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004df3b  mov     word ptr [rbp+7F0h+var_820], r14w
0x18004df40  movdqu  [rbp+7F0h+var_858], xmm0
0x18004df45  mov     word ptr [rbp+7F0h+var_848], r14w
0x18004df4a  lea     r8, aRrasroutingdom_6; "RRasRoutingDomainConfig::UpdateIkev2Con"...
0x18004df51  lea     rcx, [rbp+7F0h+var_820]
0x18004df55  call    FormatRRASErrorString
0x18004df5a  lea     rax, [rbp+7F0h+var_848]
0x18004df5e  mov     qword ptr [rsp+8F0h+samDesired], rax
0x18004df63  lea     r9, [rbp+7F0h+var_858]
0x18004df67  test    rdi, rdi
0x18004df6a  mov     qword ptr [rsp+8F0h+dwOptions], r14
0x18004df6f  cmovnz  r9, rdi
0x18004df73  lea     r8, [rbp+7F0h+var_820]
0x18004df77  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004df7e  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004df85  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004df8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df91  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18004df96  test    rcx, rcx
0x18004df99  jz      short loc_18004DFA1
0x18004df9b  call    cs:__imp_RegCloseKey
0x18004dfa1  mov     ebx, [rsp+8F0h+var_8A0]
0x18004dfa5  lea     rcx, [rsp+8F0h+var_890]; this
0x18004dfaa  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18004dfaf  mov     eax, ebx
0x18004dfb1  mov     rcx, [rbp+7F0h+var_20]
0x18004dfb8  xor     rcx, rsp; StackCookie
0x18004dfbb  call    __security_check_cookie
0x18004dfc0  lea     r11, [rsp+8F0h+var_10]
0x18004dfc8  mov     rbx, [r11+30h]
0x18004dfcc  mov     rsi, [r11+38h]
0x18004dfd0  mov     rsp, r11
0x18004dfd3  pop     r14
0x18004dfd5  pop     rdi
0x18004dfd6  pop     rbp
0x18004dfd7  retn
```
