# RRasRoutingDomainConfig::UpdateIkev2Config(_IKEV2_TUNNEL_CONFIG_PARAMS_4 *)

- ea: `0x180042b00`
- end: `0x180042d56`
- name: `?UpdateIkev2Config@RRasRoutingDomainConfig@@AEAAKPEAU_IKEV2_TUNNEL_CONFIG_PARAMS_4@@@Z`
- size: `598`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800416fc`
- `0x180042398`

## callees

- `0x180034244`
- `0x180042b00`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180042d19`
- `ADVAPI32!RegCloseKey` at `0x180042d19`
- `ADVAPI32!RegCreateKeyExW` at `0x180042c63`
- `ADVAPI32!RegCreateKeyExW` at `0x180042c63`

## string_xrefs

- `0x180042c81`: `%s: Failed to open ikev2 config reg key. error %d`
- `0x180042bac`: `RRasRoutingDomainConfig::UpdateIkev2Config`
- `0x180042cc8`: `RRasRoutingDomainConfig::UpdateIkev2Config`
- `0x180042bef`: `RRasRoutingDomainConfig::UpdateIkev2Config`
- `0x180042cab`: `%s: SetIkev2ConfigParams Failed. error %d`

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
  unsigned __int16 *samDesired; // [rsp+28h] [rbp-D8h]
  unsigned int lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  unsigned int v14; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+54h] [rbp-ACh] BYREF
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

  hKey = 0;
  v14 = 0;
  dwDisposition = 0;
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
      L"RRasRoutingDomainConfig::UpdateIkev2Config",
      &v14,
      v4,
      (struct _GUID *)((char *)this + 516),
      samDesired,
      lpSecurityAttributes);
  if ( *((_DWORD *)a2 + 8) && *((_DWORD *)a2 + 20) || *((_DWORD *)a2 + 5) )
  {
    v14 = 87;
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v28) = 0;
      FormatRRASErrorString(
        &v28,
        L"%hs(Line#%d): Invalid parameter.",
        "RRasRoutingDomainConfig::UpdateIkev2Config",
        3888);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v28);
    }
  }
  else
  {
    v5 = RegCreateKeyExW(*((HKEY *)this + 103), L"IKEv2", 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition);
    v6 = v5;
    v14 = v5;
    if ( v5 )
    {
      if ( !(_QWORD)xmmword_1800710A0 )
        goto LABEL_17;
      v7 = L"%s: Failed to open ikev2 config reg key. error %d";
    }
    else
    {
      v8 = SetIkev2ConfigParams(hKey);
      v6 = v8;
      v14 = v8;
      if ( !v8 || !(_QWORD)xmmword_1800710A0 )
        goto LABEL_17;
      v7 = L"%s: SetIkev2ConfigParams Failed. error %d";
    }
    LOWORD(v28) = 0;
    v23 = GUID_NULL;
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v28, v7, L"RRasRoutingDomainConfig::UpdateIkev2Config", v6);
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
  }
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  v10 = v14;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v17);
  return v10;
}

```

## disassembly

```asm
0x180042b00  mov     [rsp-8+arg_10], rbx
0x180042b05  mov     [rsp-8+arg_18], rsi
0x180042b0a  push    rbp
0x180042b0b  push    rdi
0x180042b0c  push    r14
0x180042b0e  lea     rbp, [rsp-7E0h]
0x180042b16  sub     rsp, 8E0h
0x180042b1d  mov     rax, cs:__security_cookie
0x180042b24  xor     rax, rsp
0x180042b27  mov     [rbp+7F0h+var_20], rax
0x180042b2e  mov     rbx, rdx
0x180042b31  mov     rsi, rcx
0x180042b34  xor     r14d, r14d
0x180042b37  mov     [rsp+8F0h+hKey], r14
0x180042b3c  mov     [rsp+8F0h+var_8A0], r14d
0x180042b41  mov     [rsp+8F0h+dwDisposition], r14d
0x180042b46  mov     [rbp+7F0h+var_820], r14d
0x180042b4a  xor     edx, edx; Val
0x180042b4c  mov     r8d, 7FCh; Size
0x180042b52  lea     rcx, [rbp+7F0h+var_81C]; void *
0x180042b56  call    memset_0
0x180042b5b  mov     [rbp+7F0h+var_848], r14d
0x180042b5f  xorps   xmm0, xmm0
0x180042b62  xor     eax, eax
0x180042b64  movups  [rbp+7F0h+var_844], xmm0
0x180042b68  movups  [rbp+7F0h+var_834], xmm0
0x180042b6c  mov     [rbp+7F0h+var_824], eax
0x180042b6f  movdqu  [rsp+8F0h+var_888], xmm0
0x180042b75  mov     [rsp+8F0h+var_890], r14
0x180042b7a  xorps   xmm1, xmm1
0x180042b7d  movdqu  [rsp+8F0h+var_878], xmm1
0x180042b83  mov     [rbp+7F0h+var_868], r14
0x180042b87  mov     [rbp+7F0h+var_860], 0FFFFFFFFh
0x180042b8e  mov     [rbp+7F0h+var_85C], r14d
0x180042b92  lea     rdi, [rsi+204h]
0x180042b99  cmp     qword ptr cs:xmmword_1800710A0+8, r14
0x180042ba0  jz      short loc_180042BBD
0x180042ba2  mov     qword ptr [rsp+8F0h+dwOptions], rdi; struct _GUID *
0x180042ba7  lea     r8, [rsp+8F0h+var_8A0]; unsigned int *
0x180042bac  lea     rdx, aRrasroutingdom_6; "RRasRoutingDomainConfig::UpdateIkev2Con"...
0x180042bb3  lea     rcx, [rsp+8F0h+var_890]; this
0x180042bb8  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180042bbd  cmp     [rbx+20h], r14d
0x180042bc1  jz      short loc_180042BC9
0x180042bc3  cmp     [rbx+50h], r14d
0x180042bc7  jnz     short loc_180042BCF
0x180042bc9  cmp     [rbx+14h], r14d
0x180042bcd  jz      short loc_180042C29
0x180042bcf  mov     [rsp+8F0h+var_8A0], 57h ; 'W'
0x180042bd7  cmp     qword ptr cs:xmmword_180071090, r14
0x180042bde  jz      loc_180042D0F
0x180042be4  mov     word ptr [rbp+7F0h+var_820], r14w
0x180042be9  mov     r9d, 0F30h
0x180042bef  lea     r8, aRrasroutingdom_0; "RRasRoutingDomainConfig::UpdateIkev2Con"...
0x180042bf6  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x180042bfd  lea     rcx, [rbp+7F0h+var_820]
0x180042c01  call    FormatRRASErrorString
0x180042c06  lea     r8, [rbp+7F0h+var_820]
0x180042c0a  mov     rdx, qword ptr cs:xmmword_180071090
0x180042c11  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180042c18  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180042c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c24  jmp     loc_180042D0F
0x180042c29  lea     rax, [rsp+8F0h+dwDisposition]
0x180042c2e  mov     [rsp+8F0h+lpdwDisposition], rax; lpdwDisposition
0x180042c33  lea     rax, [rsp+8F0h+hKey]
0x180042c38  mov     [rsp+8F0h+phkResult], rax; phkResult
0x180042c3d  mov     [rsp+8F0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180042c42  mov     [rsp+8F0h+samDesired], 20006h; samDesired
0x180042c4a  mov     [rsp+8F0h+dwOptions], r14d; dwOptions
0x180042c4f  xor     r9d, r9d; lpClass
0x180042c52  xor     r8d, r8d; Reserved
0x180042c55  lea     rdx, aIkev2; "IKEv2"
0x180042c5c  mov     rcx, [rsi+338h]; hKey
0x180042c63  call    cs:__imp_RegCreateKeyExW
0x180042c69  mov     r9d, eax
0x180042c6c  mov     [rsp+8F0h+var_8A0], eax
0x180042c70  test    eax, eax
0x180042c72  jz      short loc_180042C8A
0x180042c74  cmp     qword ptr cs:xmmword_1800710A0, r14
0x180042c7b  jz      loc_180042D0F
0x180042c81  lea     rdx, aSFailedToOpenI; "%s: Failed to open ikev2 config reg key"...
0x180042c88  jmp     short loc_180042CB2
0x180042c8a  mov     r8, rbx
0x180042c8d  mov     rcx, [rsp+8F0h+hKey]; hKey
0x180042c92  call    SetIkev2ConfigParams
0x180042c97  mov     r9d, eax
0x180042c9a  mov     [rsp+8F0h+var_8A0], eax
0x180042c9e  test    eax, eax
0x180042ca0  jz      short loc_180042D0F
0x180042ca2  cmp     qword ptr cs:xmmword_1800710A0, r14
0x180042ca9  jz      short loc_180042D0F
0x180042cab  lea     rdx, aSSetikev2confi; "%s: SetIkev2ConfigParams Failed. error "...
0x180042cb2  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180042cb9  mov     word ptr [rbp+7F0h+var_820], r14w
0x180042cbe  movdqu  [rbp+7F0h+var_858], xmm0
0x180042cc3  mov     word ptr [rbp+7F0h+var_848], r14w
0x180042cc8  lea     r8, aRrasroutingdom_6; "RRasRoutingDomainConfig::UpdateIkev2Con"...
0x180042ccf  lea     rcx, [rbp+7F0h+var_820]
0x180042cd3  call    FormatRRASErrorString
0x180042cd8  lea     rax, [rbp+7F0h+var_848]
0x180042cdc  mov     qword ptr [rsp+8F0h+samDesired], rax
0x180042ce1  lea     r9, [rbp+7F0h+var_858]
0x180042ce5  test    rdi, rdi
0x180042ce8  mov     qword ptr [rsp+8F0h+dwOptions], r14
0x180042ced  cmovnz  r9, rdi
0x180042cf1  lea     r8, [rbp+7F0h+var_820]
0x180042cf5  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180042cfc  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180042d03  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180042d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d0f  mov     rcx, [rsp+8F0h+hKey]; hKey
0x180042d14  test    rcx, rcx
0x180042d17  jz      short loc_180042D1F
0x180042d19  call    cs:__imp_RegCloseKey
0x180042d1f  mov     ebx, [rsp+8F0h+var_8A0]
0x180042d23  lea     rcx, [rsp+8F0h+var_890]; this
0x180042d28  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180042d2d  mov     eax, ebx
0x180042d2f  mov     rcx, [rbp+7F0h+var_20]
0x180042d36  xor     rcx, rsp; StackCookie
0x180042d39  call    __security_check_cookie
0x180042d3e  lea     r11, [rsp+8F0h+var_10]
0x180042d46  mov     rbx, [r11+30h]
0x180042d4a  mov     rsi, [r11+38h]
0x180042d4e  mov     rsp, r11
0x180042d51  pop     r14
0x180042d53  pop     rdi
0x180042d54  pop     rbp
0x180042d55  retn
```
