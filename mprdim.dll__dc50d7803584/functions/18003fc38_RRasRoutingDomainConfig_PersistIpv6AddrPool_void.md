# RRasRoutingDomainConfig::PersistIpv6AddrPool(void)

- ea: `0x18003fc38`
- end: `0x18003fdd7`
- name: `?PersistIpv6AddrPool@RRasRoutingDomainConfig@@AEAAKXZ`
- size: `415`
- prototype: `unsigned int __fastcall(RRasRoutingDomainConfig *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18003f104`
- `0x1800416fc`

## callees

- `0x18003fc38`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18003fd12`
- `ADVAPI32!RegSetValueExW` at `0x18003fd12`

## string_xrefs

- `0x18003fd58`: `%s: Couldn't write value %s: %d`
- `0x18003fcd6`: `RRasRoutingDomainConfig::PersistIpv6AddrPool`
- `0x18003fd51`: `RRasRoutingDomainConfig::PersistIpv6AddrPool`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RRasRoutingDomainConfig::PersistIpv6AddrPool(RRasRoutingDomainConfig *this)
{
  void (*v2)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  GUID *v3; // rdi
  unsigned int v4; // ebx
  GUID *v5; // r9
  BYTE *lpData; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *cbData; // [rsp+28h] [rbp-D8h]
  unsigned int v9; // [rsp+30h] [rbp-D0h]
  unsigned int v10; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v11; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v12; // [rsp+50h] [rbp-B0h]
  __int128 v13; // [rsp+60h] [rbp-A0h]
  __int64 v14; // [rsp+70h] [rbp-90h]
  int v15; // [rsp+78h] [rbp-88h]
  int v16; // [rsp+7Ch] [rbp-84h]
  GUID v17; // [rsp+80h] [rbp-80h] BYREF
  int v18; // [rsp+90h] [rbp-70h] BYREF
  __int128 v19; // [rsp+94h] [rbp-6Ch]
  __int128 v20; // [rsp+A4h] [rbp-5Ch]
  int v21; // [rsp+B4h] [rbp-4Ch]
  int v22; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v23[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v10 = 0;
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v12 = 0;
  v11 = 0;
  v13 = 0;
  v14 = 0;
  v15 = -1;
  v16 = 0;
  v3 = (GUID *)((char *)this + 516);
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v11,
      L"RRasRoutingDomainConfig::PersistIpv6AddrPool",
      &v10,
      v2,
      (struct _GUID *)((char *)this + 516),
      cbData,
      v9);
  v4 = RegSetValueExW(*((HKEY *)this + 103), L"Ipv6AddrPrefix", 0, 3u, (const BYTE *)this + 600, 0x10u);
  v10 = v4;
  if ( v4 && (_QWORD)xmmword_1800710A0 )
  {
    LOWORD(v22) = 0;
    v17 = GUID_NULL;
    LOWORD(v18) = 0;
    LODWORD(lpData) = v4;
    FormatRRASErrorString(
      &v22,
      L"%s: Couldn't write value %s: %d",
      L"RRasRoutingDomainConfig::PersistIpv6AddrPool",
      L"Ipv6AddrPrefix",
      lpData);
    v5 = &v17;
    if ( v3 )
      v5 = v3;
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_1800710A0,
      &v22,
      v5,
      0,
      &v18);
    v4 = v10;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v11);
  return v4;
}

```

## disassembly

```asm
0x18003fc38  mov     [rsp-8+arg_8], rbx
0x18003fc3d  mov     [rsp-8+arg_10], rdi
0x18003fc42  push    rbp
0x18003fc43  lea     rbp, [rsp-7D0h]
0x18003fc4b  sub     rsp, 8D0h
0x18003fc52  mov     rax, cs:__security_cookie
0x18003fc59  xor     rax, rsp
0x18003fc5c  mov     [rbp+7D0h+var_10], rax
0x18003fc63  mov     rbx, rcx
0x18003fc66  mov     [rsp+8D0h+var_890], 0
0x18003fc6e  xor     eax, eax
0x18003fc70  mov     [rbp+7D0h+var_810], eax
0x18003fc73  xor     edx, edx; Val
0x18003fc75  mov     r8d, 7FCh; Size
0x18003fc7b  lea     rcx, [rbp+7D0h+var_80C]; void *
0x18003fc7f  call    memset_0
0x18003fc84  xor     eax, eax
0x18003fc86  mov     [rbp+7D0h+var_840], eax
0x18003fc89  xorps   xmm0, xmm0
0x18003fc8c  movups  [rbp+7D0h+var_83C], xmm0
0x18003fc90  movups  [rbp+7D0h+var_82C], xmm0
0x18003fc94  mov     [rbp+7D0h+var_81C], eax
0x18003fc97  movdqu  [rsp+8D0h+var_880], xmm0
0x18003fc9d  mov     [rsp+8D0h+var_888], rax
0x18003fca2  xorps   xmm1, xmm1
0x18003fca5  movdqu  [rsp+8D0h+var_870], xmm1
0x18003fcab  mov     [rsp+8D0h+var_860], rax
0x18003fcb0  mov     [rsp+8D0h+var_858], 0FFFFFFFFh
0x18003fcb8  mov     [rsp+8D0h+var_854], eax
0x18003fcbc  lea     rdi, [rbx+204h]
0x18003fcc3  cmp     qword ptr cs:xmmword_1800710A0+8, rax
0x18003fcca  jz      short loc_18003FCE7
0x18003fccc  mov     [rsp+8D0h+lpData], rdi; struct _GUID *
0x18003fcd1  lea     r8, [rsp+8D0h+var_890]; unsigned int *
0x18003fcd6  lea     rdx, aRrasroutingdom_8; "RRasRoutingDomainConfig::PersistIpv6Add"...
0x18003fcdd  lea     rcx, [rsp+8D0h+var_888]; this
0x18003fce2  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18003fce7  lea     rax, [rbx+258h]
0x18003fcee  mov     [rsp+8D0h+cbData], 10h; cbData
0x18003fcf6  mov     [rsp+8D0h+lpData], rax; lpData
0x18003fcfb  mov     r9d, 3; dwType
0x18003fd01  xor     r8d, r8d; Reserved
0x18003fd04  lea     rdx, aIpv6addrprefix; "Ipv6AddrPrefix"
0x18003fd0b  mov     rcx, [rbx+338h]; hKey
0x18003fd12  call    cs:__imp_RegSetValueExW
0x18003fd18  mov     ebx, eax
0x18003fd1a  mov     [rsp+8D0h+var_890], eax
0x18003fd1e  test    eax, eax
0x18003fd20  jz      loc_18003FDA7
0x18003fd26  cmp     qword ptr cs:xmmword_1800710A0, 0
0x18003fd2e  jz      short loc_18003FDA7
0x18003fd30  xor     eax, eax
0x18003fd32  mov     word ptr [rbp+7D0h+var_810], ax
0x18003fd36  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003fd3d  movdqu  [rbp+7D0h+var_850], xmm0
0x18003fd42  mov     word ptr [rbp+7D0h+var_840], ax
0x18003fd46  mov     dword ptr [rsp+8D0h+lpData], ebx
0x18003fd4a  lea     r9, aIpv6addrprefix; "Ipv6AddrPrefix"
0x18003fd51  lea     r8, aRrasroutingdom_8; "RRasRoutingDomainConfig::PersistIpv6Add"...
0x18003fd58  lea     rdx, aSCouldnTWriteV_0; "%s: Couldn't write value %s: %d"
0x18003fd5f  lea     rcx, [rbp+7D0h+var_810]
0x18003fd63  call    FormatRRASErrorString
0x18003fd68  lea     r9, [rbp+7D0h+var_850]
0x18003fd6c  test    rdi, rdi
0x18003fd6f  cmovnz  r9, rdi
0x18003fd73  lea     rax, [rbp+7D0h+var_840]
0x18003fd77  mov     qword ptr [rsp+8D0h+cbData], rax
0x18003fd7c  mov     [rsp+8D0h+lpData], 0
0x18003fd85  lea     r8, [rbp+7D0h+var_810]
0x18003fd89  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003fd90  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003fd97  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003fd9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fda3  mov     ebx, [rsp+8D0h+var_890]
0x18003fda7  lea     rcx, [rsp+8D0h+var_888]; this
0x18003fdac  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003fdb1  mov     eax, ebx
0x18003fdb3  mov     rcx, [rbp+7D0h+var_10]
0x18003fdba  xor     rcx, rsp; StackCookie
0x18003fdbd  call    __security_check_cookie
0x18003fdc2  lea     r11, [rsp+8D0h+var_s0]
0x18003fdca  mov     rbx, [r11+18h]
0x18003fdce  mov     rdi, [r11+20h]
0x18003fdd2  mov     rsp, r11
0x18003fdd5  pop     rbp
0x18003fdd6  retn
```
