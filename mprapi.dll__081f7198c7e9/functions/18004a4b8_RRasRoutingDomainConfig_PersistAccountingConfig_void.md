# RRasRoutingDomainConfig::PersistAccountingConfig(void)

- ea: `0x18004a4b8`
- end: `0x18004a6ba`
- name: `?PersistAccountingConfig@RRasRoutingDomainConfig@@AEAAKXZ`
- size: `514`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, __int64, __int64, void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18004a6c0`
- `0x18004c944`

## callees

- `0x18004a4b8`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004a5a3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004a5f2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004a5a3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004a5f2`

## string_xrefs

- `0x18004a638`: `%s: Couldn't write value %s: %d`
- `0x18004a540`: `RRasRoutingDomainConfig::PersistAccountingConfig`
- `0x18004a631`: `RRasRoutingDomainConfig::PersistAccountingConfig`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::PersistAccountingConfig(
        RRasRoutingDomainConfig *this,
        __int64 a2,
        __int64 a3,
        void (*a4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))
{
  GUID *v5; // rsi
  unsigned int v6; // ebx
  const WCHAR *v7; // r9
  GUID *v8; // r9
  BYTE *lpData; // [rsp+20h] [rbp-E0h]
  unsigned int v11; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v13; // [rsp+50h] [rbp-B0h]
  __int128 v14; // [rsp+60h] [rbp-A0h]
  __int64 v15; // [rsp+70h] [rbp-90h]
  int v16; // [rsp+78h] [rbp-88h]
  int v17; // [rsp+7Ch] [rbp-84h]
  GUID v18; // [rsp+80h] [rbp-80h] BYREF
  int v19; // [rsp+90h] [rbp-70h] BYREF
  __int128 v20; // [rsp+94h] [rbp-6Ch]
  __int128 v21; // [rsp+A4h] [rbp-5Ch]
  int v22; // [rsp+B4h] [rbp-4Ch]
  int v23; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v24[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v11 = 0;
  v13 = 0;
  v12 = 0;
  v14 = 0;
  v15 = 0;
  v16 = -1;
  v17 = 0;
  v5 = (GUID *)((char *)this + 516);
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v12,
      L"RRasRoutingDomainConfig::PersistAccountingConfig",
      &v11,
      a4,
      (struct _GUID *)((char *)this + 516));
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v6 = RegSetValueExW(*((HKEY *)this + 103), L"InterimAcctEnabled", 0, 4u, (const BYTE *)this + 572, 4u);
  v11 = v6;
  if ( v6 )
  {
    if ( !(_QWORD)xmmword_180078C60 )
      goto LABEL_12;
    v7 = L"InterimAcctEnabled";
  }
  else
  {
    v6 = RegSetValueExW(*((HKEY *)this + 103), L"InterimAcctInterval", 0, 4u, (const BYTE *)this + 576, 4u);
    v11 = v6;
    if ( !v6 || !(_QWORD)xmmword_180078C60 )
      goto LABEL_12;
    v7 = L"InterimAcctInterval";
  }
  LODWORD(lpData) = v6;
  LOWORD(v23) = 0;
  v18 = GUID_NULL;
  LOWORD(v19) = 0;
  FormatRRASErrorString(
    &v23,
    L"%s: Couldn't write value %s: %d",
    L"RRasRoutingDomainConfig::PersistAccountingConfig",
    v7,
    lpData);
  v8 = &v18;
  if ( v5 )
    v8 = v5;
  ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
    gCfgStoreEtwContext,
    xmmword_180078C60,
    &v23,
    v8,
    0,
    &v19);
  v6 = v11;
LABEL_12:
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v12);
  return v6;
}

```

## disassembly

```asm
0x18004a4b8  mov     [rsp-8+arg_8], rbx
0x18004a4bd  mov     [rsp-8+arg_10], rsi
0x18004a4c2  push    rbp
0x18004a4c3  push    rdi
0x18004a4c4  push    r14
0x18004a4c6  lea     rbp, [rsp-7D0h]
0x18004a4ce  sub     rsp, 8D0h
0x18004a4d5  mov     rax, cs:__security_cookie
0x18004a4dc  xor     rax, rsp
0x18004a4df  mov     [rbp+7E0h+var_20], rax
0x18004a4e6  mov     rdi, rcx
0x18004a4e9  mov     [rsp+8E0h+var_8A0], 0
0x18004a4f1  xorps   xmm0, xmm0
0x18004a4f4  movdqu  [rsp+8E0h+var_890], xmm0
0x18004a4fa  mov     [rsp+8E0h+var_898], 0
0x18004a503  xorps   xmm1, xmm1
0x18004a506  movdqu  [rsp+8E0h+var_880], xmm1
0x18004a50c  mov     [rsp+8E0h+var_870], 0
0x18004a515  mov     [rsp+8E0h+var_868], 0FFFFFFFFh
0x18004a51d  mov     [rsp+8E0h+var_864], 0
0x18004a525  lea     rsi, [rcx+204h]
0x18004a52c  cmp     qword ptr cs:xmmword_180078C60+8, 0
0x18004a534  jz      short loc_18004A551
0x18004a536  mov     [rsp+8E0h+lpData], rsi; struct _GUID *
0x18004a53b  lea     r8, [rsp+8E0h+var_8A0]; unsigned int *
0x18004a540  lea     rdx, aRrasroutingdom_30; "RRasRoutingDomainConfig::PersistAccount"...
0x18004a547  lea     rcx, [rsp+8E0h+var_898]; this
0x18004a54c  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18004a551  xor     eax, eax
0x18004a553  mov     [rbp+7E0h+var_820], eax
0x18004a556  xor     edx, edx; Val
0x18004a558  mov     r8d, 7FCh; Size
0x18004a55e  lea     rcx, [rbp+7E0h+var_81C]; void *
0x18004a562  call    memset_0
0x18004a567  xor     eax, eax
0x18004a569  mov     [rbp+7E0h+var_850], eax
0x18004a56c  xorps   xmm0, xmm0
0x18004a56f  movups  [rbp+7E0h+var_84C], xmm0
0x18004a573  movups  [rbp+7E0h+var_83C], xmm0
0x18004a577  mov     [rbp+7E0h+var_82C], eax
0x18004a57a  lea     r14, [rdi+23Ch]
0x18004a581  mov     [rsp+8E0h+cbData], 4; cbData
0x18004a589  mov     [rsp+8E0h+lpData], r14; lpData
0x18004a58e  lea     r9d, [rax+4]; dwType
0x18004a592  xor     r8d, r8d; Reserved
0x18004a595  lea     rdx, aInterimacctena; "InterimAcctEnabled"
0x18004a59c  mov     rcx, [rdi+338h]; hKey
0x18004a5a3  call    cs:__imp_RegSetValueExW
0x18004a5a9  mov     ebx, eax
0x18004a5ab  mov     [rsp+8E0h+var_8A0], eax
0x18004a5af  test    eax, eax
0x18004a5b1  jz      short loc_18004A5CA
0x18004a5b3  cmp     qword ptr cs:xmmword_180078C60, 0
0x18004a5bb  jz      loc_18004A687
0x18004a5c1  lea     r9, aInterimacctena; "InterimAcctEnabled"
0x18004a5c8  jmp     short loc_18004A617
0x18004a5ca  lea     rax, [r14+4]
0x18004a5ce  mov     [rsp+8E0h+cbData], 4; cbData
0x18004a5d6  mov     [rsp+8E0h+lpData], rax; lpData
0x18004a5db  mov     r9d, 4; dwType
0x18004a5e1  xor     r8d, r8d; Reserved
0x18004a5e4  lea     rdx, aInterimacctint; "InterimAcctInterval"
0x18004a5eb  mov     rcx, [rdi+338h]; hKey
0x18004a5f2  call    cs:__imp_RegSetValueExW
0x18004a5f8  mov     ebx, eax
0x18004a5fa  mov     [rsp+8E0h+var_8A0], eax
0x18004a5fe  test    eax, eax
0x18004a600  jz      loc_18004A687
0x18004a606  cmp     qword ptr cs:xmmword_180078C60, 0
0x18004a60e  jz      short loc_18004A687
0x18004a610  lea     r9, aInterimacctint; "InterimAcctInterval"
0x18004a617  xor     eax, eax
0x18004a619  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004a620  mov     dword ptr [rsp+8E0h+lpData], ebx
0x18004a624  mov     word ptr [rbp+7E0h+var_820], ax
0x18004a628  movdqu  [rbp+7E0h+var_860], xmm0
0x18004a62d  mov     word ptr [rbp+7E0h+var_850], ax
0x18004a631  lea     r8, aRrasroutingdom_30; "RRasRoutingDomainConfig::PersistAccount"...
0x18004a638  lea     rdx, aSCouldnTWriteV_0; "%s: Couldn't write value %s: %d"
0x18004a63f  lea     rcx, [rbp+7E0h+var_820]
0x18004a643  call    FormatRRASErrorString
0x18004a648  lea     rax, [rbp+7E0h+var_850]
0x18004a64c  mov     qword ptr [rsp+8E0h+cbData], rax
0x18004a651  lea     r9, [rbp+7E0h+var_860]
0x18004a655  test    rsi, rsi
0x18004a658  mov     [rsp+8E0h+lpData], 0
0x18004a661  cmovnz  r9, rsi
0x18004a665  lea     r8, [rbp+7E0h+var_820]
0x18004a669  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004a670  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004a677  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004a67e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a683  mov     ebx, [rsp+8E0h+var_8A0]
0x18004a687  lea     rcx, [rsp+8E0h+var_898]; this
0x18004a68c  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18004a691  mov     eax, ebx
0x18004a693  mov     rcx, [rbp+7E0h+var_20]
0x18004a69a  xor     rcx, rsp; StackCookie
0x18004a69d  call    __security_check_cookie
0x18004a6a2  lea     r11, [rsp+8E0h+var_10]
0x18004a6aa  mov     rbx, [r11+28h]
0x18004a6ae  mov     rsi, [r11+30h]
0x18004a6b2  mov     rsp, r11
0x18004a6b5  pop     r14
0x18004a6b7  pop     rdi
0x18004a6b8  pop     rbp
0x18004a6b9  retn
```
