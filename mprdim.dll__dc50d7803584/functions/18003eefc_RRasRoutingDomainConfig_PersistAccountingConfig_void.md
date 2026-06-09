# RRasRoutingDomainConfig::PersistAccountingConfig(void)

- ea: `0x18003eefc`
- end: `0x18003f0fe`
- name: `?PersistAccountingConfig@RRasRoutingDomainConfig@@AEAAKXZ`
- size: `514`
- prototype: `unsigned int __fastcall(RRasRoutingDomainConfig *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18003f104`
- `0x1800416fc`

## callees

- `0x18003eefc`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18003efe7`
- `ADVAPI32!RegSetValueExW` at `0x18003f036`
- `ADVAPI32!RegSetValueExW` at `0x18003efe7`
- `ADVAPI32!RegSetValueExW` at `0x18003f036`

## string_xrefs

- `0x18003f07c`: `%s: Couldn't write value %s: %d`
- `0x18003ef84`: `RRasRoutingDomainConfig::PersistAccountingConfig`
- `0x18003f075`: `RRasRoutingDomainConfig::PersistAccountingConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  unsigned __int16 *cbData; // [rsp+28h] [rbp-D8h]
  unsigned int v12; // [rsp+30h] [rbp-D0h]
  unsigned int v13; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v15; // [rsp+50h] [rbp-B0h]
  __int128 v16; // [rsp+60h] [rbp-A0h]
  __int64 v17; // [rsp+70h] [rbp-90h]
  int v18; // [rsp+78h] [rbp-88h]
  int v19; // [rsp+7Ch] [rbp-84h]
  GUID v20; // [rsp+80h] [rbp-80h] BYREF
  int v21; // [rsp+90h] [rbp-70h] BYREF
  __int128 v22; // [rsp+94h] [rbp-6Ch]
  __int128 v23; // [rsp+A4h] [rbp-5Ch]
  int v24; // [rsp+B4h] [rbp-4Ch]
  int v25; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v26[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v13 = 0;
  v15 = 0;
  v14 = 0;
  v16 = 0;
  v17 = 0;
  v18 = -1;
  v19 = 0;
  v5 = (GUID *)((char *)this + 516);
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v14,
      L"RRasRoutingDomainConfig::PersistAccountingConfig",
      &v13,
      a4,
      (struct _GUID *)((char *)this + 516),
      cbData,
      v12);
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v6 = RegSetValueExW(*((HKEY *)this + 103), L"InterimAcctEnabled", 0, 4u, (const BYTE *)this + 572, 4u);
  v13 = v6;
  if ( v6 )
  {
    if ( !(_QWORD)xmmword_1800710A0 )
      goto LABEL_12;
    v7 = L"InterimAcctEnabled";
  }
  else
  {
    v6 = RegSetValueExW(*((HKEY *)this + 103), L"InterimAcctInterval", 0, 4u, (const BYTE *)this + 576, 4u);
    v13 = v6;
    if ( !v6 || !(_QWORD)xmmword_1800710A0 )
      goto LABEL_12;
    v7 = L"InterimAcctInterval";
  }
  LODWORD(lpData) = v6;
  LOWORD(v25) = 0;
  v20 = GUID_NULL;
  LOWORD(v21) = 0;
  FormatRRASErrorString(
    &v25,
    L"%s: Couldn't write value %s: %d",
    L"RRasRoutingDomainConfig::PersistAccountingConfig",
    v7,
    lpData);
  v8 = &v20;
  if ( v5 )
    v8 = v5;
  ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
    gCfgStoreEtwContext,
    xmmword_1800710A0,
    &v25,
    v8,
    0,
    &v21);
  v6 = v13;
LABEL_12:
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v14);
  return v6;
}

```

## disassembly

```asm
0x18003eefc  mov     [rsp-8+arg_8], rbx
0x18003ef01  mov     [rsp-8+arg_10], rsi
0x18003ef06  push    rbp
0x18003ef07  push    rdi
0x18003ef08  push    r14
0x18003ef0a  lea     rbp, [rsp-7D0h]
0x18003ef12  sub     rsp, 8D0h
0x18003ef19  mov     rax, cs:__security_cookie
0x18003ef20  xor     rax, rsp
0x18003ef23  mov     [rbp+7E0h+var_20], rax
0x18003ef2a  mov     rdi, rcx
0x18003ef2d  mov     [rsp+8E0h+var_8A0], 0
0x18003ef35  xorps   xmm0, xmm0
0x18003ef38  movdqu  [rsp+8E0h+var_890], xmm0
0x18003ef3e  mov     [rsp+8E0h+var_898], 0
0x18003ef47  xorps   xmm1, xmm1
0x18003ef4a  movdqu  [rsp+8E0h+var_880], xmm1
0x18003ef50  mov     [rsp+8E0h+var_870], 0
0x18003ef59  mov     [rsp+8E0h+var_868], 0FFFFFFFFh
0x18003ef61  mov     [rsp+8E0h+var_864], 0
0x18003ef69  lea     rsi, [rcx+204h]
0x18003ef70  cmp     qword ptr cs:xmmword_1800710A0+8, 0
0x18003ef78  jz      short loc_18003EF95
0x18003ef7a  mov     [rsp+8E0h+lpData], rsi; struct _GUID *
0x18003ef7f  lea     r8, [rsp+8E0h+var_8A0]; unsigned int *
0x18003ef84  lea     rdx, aRrasroutingdom_31; "RRasRoutingDomainConfig::PersistAccount"...
0x18003ef8b  lea     rcx, [rsp+8E0h+var_898]; this
0x18003ef90  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18003ef95  xor     eax, eax
0x18003ef97  mov     [rbp+7E0h+var_820], eax
0x18003ef9a  xor     edx, edx; Val
0x18003ef9c  mov     r8d, 7FCh; Size
0x18003efa2  lea     rcx, [rbp+7E0h+var_81C]; void *
0x18003efa6  call    memset_0
0x18003efab  xor     eax, eax
0x18003efad  mov     [rbp+7E0h+var_850], eax
0x18003efb0  xorps   xmm0, xmm0
0x18003efb3  movups  [rbp+7E0h+var_84C], xmm0
0x18003efb7  movups  [rbp+7E0h+var_83C], xmm0
0x18003efbb  mov     [rbp+7E0h+var_82C], eax
0x18003efbe  lea     r14, [rdi+23Ch]
0x18003efc5  mov     [rsp+8E0h+cbData], 4; cbData
0x18003efcd  mov     [rsp+8E0h+lpData], r14; lpData
0x18003efd2  lea     r9d, [rax+4]; dwType
0x18003efd6  xor     r8d, r8d; Reserved
0x18003efd9  lea     rdx, aInterimacctena; "InterimAcctEnabled"
0x18003efe0  mov     rcx, [rdi+338h]; hKey
0x18003efe7  call    cs:__imp_RegSetValueExW
0x18003efed  mov     ebx, eax
0x18003efef  mov     [rsp+8E0h+var_8A0], eax
0x18003eff3  test    eax, eax
0x18003eff5  jz      short loc_18003F00E
0x18003eff7  cmp     qword ptr cs:xmmword_1800710A0, 0
0x18003efff  jz      loc_18003F0CB
0x18003f005  lea     r9, aInterimacctena; "InterimAcctEnabled"
0x18003f00c  jmp     short loc_18003F05B
0x18003f00e  lea     rax, [r14+4]
0x18003f012  mov     [rsp+8E0h+cbData], 4; cbData
0x18003f01a  mov     [rsp+8E0h+lpData], rax; lpData
0x18003f01f  mov     r9d, 4; dwType
0x18003f025  xor     r8d, r8d; Reserved
0x18003f028  lea     rdx, aInterimacctint; "InterimAcctInterval"
0x18003f02f  mov     rcx, [rdi+338h]; hKey
0x18003f036  call    cs:__imp_RegSetValueExW
0x18003f03c  mov     ebx, eax
0x18003f03e  mov     [rsp+8E0h+var_8A0], eax
0x18003f042  test    eax, eax
0x18003f044  jz      loc_18003F0CB
0x18003f04a  cmp     qword ptr cs:xmmword_1800710A0, 0
0x18003f052  jz      short loc_18003F0CB
0x18003f054  lea     r9, aInterimacctint; "InterimAcctInterval"
0x18003f05b  xor     eax, eax
0x18003f05d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003f064  mov     dword ptr [rsp+8E0h+lpData], ebx
0x18003f068  mov     word ptr [rbp+7E0h+var_820], ax
0x18003f06c  movdqu  [rbp+7E0h+var_860], xmm0
0x18003f071  mov     word ptr [rbp+7E0h+var_850], ax
0x18003f075  lea     r8, aRrasroutingdom_31; "RRasRoutingDomainConfig::PersistAccount"...
0x18003f07c  lea     rdx, aSCouldnTWriteV_0; "%s: Couldn't write value %s: %d"
0x18003f083  lea     rcx, [rbp+7E0h+var_820]
0x18003f087  call    FormatRRASErrorString
0x18003f08c  lea     rax, [rbp+7E0h+var_850]
0x18003f090  mov     qword ptr [rsp+8E0h+cbData], rax
0x18003f095  lea     r9, [rbp+7E0h+var_860]
0x18003f099  test    rsi, rsi
0x18003f09c  mov     [rsp+8E0h+lpData], 0
0x18003f0a5  cmovnz  r9, rsi
0x18003f0a9  lea     r8, [rbp+7E0h+var_820]
0x18003f0ad  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003f0b4  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003f0bb  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003f0c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f0c7  mov     ebx, [rsp+8E0h+var_8A0]
0x18003f0cb  lea     rcx, [rsp+8E0h+var_898]; this
0x18003f0d0  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003f0d5  mov     eax, ebx
0x18003f0d7  mov     rcx, [rbp+7E0h+var_20]
0x18003f0de  xor     rcx, rsp; StackCookie
0x18003f0e1  call    __security_check_cookie
0x18003f0e6  lea     r11, [rsp+8E0h+var_10]
0x18003f0ee  mov     rbx, [r11+28h]
0x18003f0f2  mov     rsi, [r11+30h]
0x18003f0f6  mov     rsp, r11
0x18003f0f9  pop     r14
0x18003f0fb  pop     rdi
0x18003f0fc  pop     rbp
0x18003f0fd  retn
```
