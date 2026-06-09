# RRasRoutingDomainConfig::PopulateIpv6AddrPool(void)

- ea: `0x1800406cc`
- end: `0x18004089f`
- name: `?PopulateIpv6AddrPool@RRasRoutingDomainConfig@@AEAAKXZ`
- size: `467`
- prototype: `unsigned int __fastcall(RRasRoutingDomainConfig *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18003c810`
- `0x18003fde0`

## callees

- `0x1800406cc`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800407b8`
- `ADVAPI32!RegQueryValueExW` at `0x1800407b8`

## string_xrefs

- `0x18004076b`: `RRasRoutingDomainConfig::PopulateIpv6AddrPool`
- `0x180040806`: `RRasRoutingDomainConfig::PopulateIpv6AddrPool`
- `0x18004080d`: `%s: Couldn't read value %s: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RRasRoutingDomainConfig::PopulateIpv6AddrPool(RRasRoutingDomainConfig *this)
{
  void (*v2)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int v3; // ebx
  unsigned int v4; // eax
  unsigned int *v5; // rcx
  GUID *v6; // r9
  LPBYTE lpData; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *lpcbData; // [rsp+28h] [rbp-D8h]
  unsigned int v10; // [rsp+30h] [rbp-D0h]
  unsigned int v11; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v14; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v15; // [rsp+58h] [rbp-A8h]
  __int128 v16; // [rsp+68h] [rbp-98h]
  __int64 v17; // [rsp+78h] [rbp-88h]
  int v18; // [rsp+80h] [rbp-80h]
  int v19; // [rsp+84h] [rbp-7Ch]
  GUID v20; // [rsp+88h] [rbp-78h] BYREF
  int v21; // [rsp+98h] [rbp-68h] BYREF
  __int128 v22; // [rsp+9Ch] [rbp-64h]
  __int128 v23; // [rsp+ACh] [rbp-54h]
  int v24; // [rsp+BCh] [rbp-44h]
  int v25; // [rsp+C0h] [rbp-40h] BYREF
  char v26[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v11 = 0;
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v15 = 0;
  v14 = 0;
  v16 = 0;
  v17 = 0;
  v18 = -1;
  v19 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v14,
      L"RRasRoutingDomainConfig::PopulateIpv6AddrPool",
      &v11,
      v2,
      (struct _GUID *)((char *)this + 516),
      lpcbData,
      v10);
  Type = 3;
  cbData = 16;
  v3 = RegQueryValueExW(*((HKEY *)this + 103), L"Ipv6AddrPrefix", 0, &Type, (LPBYTE)this + 600, &cbData);
  v11 = v3;
  if ( v3 || Type != 3 )
  {
    if ( (_QWORD)xmmword_1800710A0 )
    {
      LOWORD(v25) = 0;
      v20 = GUID_NULL;
      LOWORD(v21) = 0;
      LODWORD(lpData) = v3;
      FormatRRASErrorString(
        &v25,
        L"%s: Couldn't read value %s: %d",
        L"RRasRoutingDomainConfig::PopulateIpv6AddrPool",
        L"Ipv6AddrPrefix",
        lpData);
      v6 = &v20;
      if ( this != (RRasRoutingDomainConfig *)-516LL )
        v6 = (GUID *)((char *)this + 516);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_1800710A0,
        &v25,
        v6,
        0,
        &v21);
    }
    v3 = 1168;
    v11 = 1168;
    v4 = 0;
    v5 = (unsigned int *)((char *)this + 616);
  }
  else
  {
    v4 = v3 + 64;
    v5 = (unsigned int *)((char *)this + 616);
  }
  *v5 = v4;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v14);
  return v3;
}

```

## disassembly

```asm
0x1800406cc  mov     [rsp-8+arg_8], rbx
0x1800406d1  mov     [rsp-8+arg_10], rsi
0x1800406d6  push    rbp
0x1800406d7  push    rdi
0x1800406d8  push    r14
0x1800406da  lea     rbp, [rsp-7D0h]
0x1800406e2  sub     rsp, 8D0h
0x1800406e9  mov     rax, cs:__security_cookie
0x1800406f0  xor     rax, rsp
0x1800406f3  mov     [rbp+7E0h+var_20], rax
0x1800406fa  mov     rdi, rcx
0x1800406fd  mov     [rsp+8E0h+var_8A0], 0
0x180040705  xor     eax, eax
0x180040707  mov     [rbp+7E0h+var_820], eax
0x18004070a  xor     edx, edx; Val
0x18004070c  mov     r8d, 7FCh; Size
0x180040712  lea     rcx, [rbp+7E0h+var_81C]; void *
0x180040716  call    memset_0
0x18004071b  xor     eax, eax
0x18004071d  mov     [rbp+7E0h+var_848], eax
0x180040720  xorps   xmm0, xmm0
0x180040723  movups  [rbp+7E0h+var_844], xmm0
0x180040727  movups  [rbp+7E0h+var_834], xmm0
0x18004072b  mov     [rbp+7E0h+var_824], eax
0x18004072e  movdqu  [rsp+8E0h+var_888], xmm0
0x180040734  mov     [rsp+8E0h+var_890], rax
0x180040739  xorps   xmm1, xmm1
0x18004073c  movdqu  [rsp+8E0h+var_878], xmm1
0x180040742  mov     [rsp+8E0h+var_868], rax
0x180040747  mov     [rbp+7E0h+var_860], 0FFFFFFFFh
0x18004074e  mov     [rbp+7E0h+var_85C], eax
0x180040751  lea     r14, [rdi+204h]
0x180040758  cmp     qword ptr cs:xmmword_1800710A0+8, rax
0x18004075f  jz      short loc_18004077C
0x180040761  mov     [rsp+8E0h+lpData], r14; struct _GUID *
0x180040766  lea     r8, [rsp+8E0h+var_8A0]; unsigned int *
0x18004076b  lea     rdx, aRrasroutingdom_15; "RRasRoutingDomainConfig::PopulateIpv6Ad"...
0x180040772  lea     rcx, [rsp+8E0h+var_890]; this
0x180040777  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18004077c  mov     [rsp+8E0h+Type], 3
0x180040784  mov     [rsp+8E0h+cbData], 10h
0x18004078c  lea     rsi, [rdi+258h]
0x180040793  lea     rax, [rsp+8E0h+cbData]
0x180040798  mov     [rsp+8E0h+lpcbData], rax; lpcbData
0x18004079d  mov     [rsp+8E0h+lpData], rsi; lpData
0x1800407a2  lea     r9, [rsp+8E0h+Type]; lpType
0x1800407a7  xor     r8d, r8d; lpReserved
0x1800407aa  lea     rdx, aIpv6addrprefix; "Ipv6AddrPrefix"
0x1800407b1  mov     rcx, [rdi+338h]; hKey
0x1800407b8  call    cs:__imp_RegQueryValueExW
0x1800407be  mov     ebx, eax
0x1800407c0  mov     [rsp+8E0h+var_8A0], eax
0x1800407c4  test    eax, eax
0x1800407c6  jnz     short loc_1800407DB
0x1800407c8  cmp     [rsp+8E0h+Type], 3
0x1800407cd  jnz     short loc_1800407DB
0x1800407cf  lea     eax, [rbx+40h]
0x1800407d2  lea     rcx, [rsi+10h]
0x1800407d6  jmp     loc_18004086A
0x1800407db  cmp     qword ptr cs:xmmword_1800710A0, 0
0x1800407e3  jz      short loc_180040858
0x1800407e5  xor     eax, eax
0x1800407e7  mov     word ptr [rbp+7E0h+var_820], ax
0x1800407eb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800407f2  movdqu  [rbp+7E0h+var_858], xmm0
0x1800407f7  mov     word ptr [rbp+7E0h+var_848], ax
0x1800407fb  mov     dword ptr [rsp+8E0h+lpData], ebx
0x1800407ff  lea     r9, aIpv6addrprefix; "Ipv6AddrPrefix"
0x180040806  lea     r8, aRrasroutingdom_15; "RRasRoutingDomainConfig::PopulateIpv6Ad"...
0x18004080d  lea     rdx, aSCouldnTReadVa; "%s: Couldn't read value %s: %d"
0x180040814  lea     rcx, [rbp+7E0h+var_820]
0x180040818  call    FormatRRASErrorString
0x18004081d  lea     r9, [rbp+7E0h+var_858]
0x180040821  test    r14, r14
0x180040824  cmovnz  r9, r14
0x180040828  lea     rax, [rbp+7E0h+var_848]
0x18004082c  mov     [rsp+8E0h+lpcbData], rax
0x180040831  mov     [rsp+8E0h+lpData], 0
0x18004083a  lea     r8, [rbp+7E0h+var_820]
0x18004083e  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180040845  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004084c  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180040853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040858  mov     ebx, 490h
0x18004085d  mov     [rsp+8E0h+var_8A0], ebx
0x180040861  xor     eax, eax
0x180040863  lea     rcx, [rdi+268h]
0x18004086a  mov     [rcx], eax
0x18004086c  lea     rcx, [rsp+8E0h+var_890]; this
0x180040871  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180040876  mov     eax, ebx
0x180040878  mov     rcx, [rbp+7E0h+var_20]
0x18004087f  xor     rcx, rsp; StackCookie
0x180040882  call    __security_check_cookie
0x180040887  lea     r11, [rsp+8E0h+var_10]
0x18004088f  mov     rbx, [r11+28h]
0x180040893  mov     rsi, [r11+30h]
0x180040897  mov     rsp, r11
0x18004089a  pop     r14
0x18004089c  pop     rdi
0x18004089d  pop     rbp
0x18004089e  retn
```
