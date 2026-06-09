# RRasRoutingDomainConfig::RRasRoutingDomainConfig(HKEY__ *,_GUID)

- ea: `0x180043e78`
- end: `0x180044147`
- name: `??0RRasRoutingDomainConfig@@QEAA@PEAUHKEY__@@U_GUID@@@Z`
- size: `719`
- prototype: `RRasRoutingDomainConfig *__fastcall(RRasRoutingDomainConfig *__hidden this, HKEY, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180047508`
- `0x180049728`

## callees

- `0x1800302d0`
- `0x180043e78`
- `0x18004d468`
- `0x180050b2c`
- `0x180050be8`
- `0x180050cd4`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `ntdll!RtlInitializeResource` at `0x180044050`
- `ntdll!RtlInitializeResource` at `0x180044050`

## string_xrefs

- `0x180043f1f`: `RRasRoutingDomainConfig::RRasRoutingDomainConfig`
- `0x1800440b7`: `RRasRoutingDomainConfig::RRasRoutingDomainConfig`
- `0x1800440be`: `%s: UpdateCompartmentIdAndName failed for (%ws): %d.`
- `0x180043f60`: `RRasRoutingDomainConfig::Initialize`

## pseudocode

```c
RRasRoutingDomainConfig *__fastcall RRasRoutingDomainConfig::RRasRoutingDomainConfig(
        RRasRoutingDomainConfig *this,
        HKEY a2,
        struct _GUID *a3)
{
  void (*v6)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int v7; // r8d
  unsigned int updated; // eax
  GUID *v9; // r9
  struct _GUID *v11; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v12; // [rsp+28h] [rbp-D8h]
  unsigned int v13; // [rsp+30h] [rbp-D0h]
  unsigned int v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v16; // [rsp+50h] [rbp-B0h]
  __int128 v17; // [rsp+60h] [rbp-A0h]
  __int64 v18; // [rsp+70h] [rbp-90h]
  int v19; // [rsp+78h] [rbp-88h]
  int v20; // [rsp+7Ch] [rbp-84h]
  __int64 v21; // [rsp+80h] [rbp-80h] BYREF
  __int128 v22; // [rsp+88h] [rbp-78h]
  __int128 v23; // [rsp+98h] [rbp-68h]
  __int64 v24; // [rsp+A8h] [rbp-58h]
  int v25; // [rsp+B0h] [rbp-50h]
  int v26; // [rsp+B4h] [rbp-4Ch]
  GUID v27; // [rsp+B8h] [rbp-48h] BYREF
  int v28; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v29; // [rsp+CCh] [rbp-34h]
  __int128 v30; // [rsp+DCh] [rbp-24h]
  int v31; // [rsp+ECh] [rbp-14h]
  _BYTE v32[80]; // [rsp+F0h] [rbp-10h] BYREF
  int v33; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v34[2044]; // [rsp+144h] [rbp+44h] BYREF

  v14 = 0;
  memset_0(v32, 0, sizeof(v32));
  v33 = 0;
  memset_0(v34, 0, sizeof(v34));
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v22 = 0;
  v21 = 0;
  v23 = 0;
  v24 = 0;
  v25 = -1;
  v26 = 0;
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v21,
      L"RRasRoutingDomainConfig::RRasRoutingDomainConfig",
      &v14,
      v6,
      a3,
      v12,
      v13);
  v16 = 0;
  v15 = 0;
  v17 = 0;
  v18 = 0;
  v19 = -1;
  v20 = 0;
  if ( *((_QWORD *)&xmmword_180078C50 + 1) )
    EtwFuncEntryExitTracer::Initialize((EtwFuncEntryExitTracer *)&v15, L"RRasRoutingDomainConfig::Initialize", 0, v6);
  memset_0(this, 0, 0x202u);
  *(_OWORD *)((char *)this + 584) = 0;
  *(_OWORD *)((char *)this + 600) = 0;
  *((_DWORD *)this + 154) = 0;
  *(_OWORD *)((char *)this + 516) = 0;
  *(_QWORD *)((char *)this + 572) = 0;
  memset_0((char *)this + 624, 0, 0x68u);
  *(_QWORD *)((char *)this + 548) = 0;
  *(_QWORD *)((char *)this + 556) = 0;
  *(_QWORD *)((char *)this + 564) = 0;
  *(_OWORD *)((char *)this + 840) = 0;
  *((_QWORD *)this + 104) = -2147483646;
  *(_QWORD *)((char *)this + 532) = 0;
  *((_DWORD *)this + 135) = 0;
  *((_QWORD *)this + 103) = 0;
  *((_DWORD *)this + 136) = 2;
  v7 = 0;
  do
  {
    *((_DWORD *)this + 3 * v7 + 138) = v7 != 0;
    *((_DWORD *)this + 3 * v7++ + 139) = _InterlockedIncrement(&dword_180078CC0);
  }
  while ( v7 < *((_DWORD *)this + 136) );
  RtlInitializeResource((PRTL_RESOURCE)((char *)this + 728));
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v15);
  *((_QWORD *)this + 104) = a2;
  *(struct _GUID *)((char *)this + 516) = *a3;
  MprConvertGuidToString((char *)this + 516, 40, v32);
  updated = RRasRoutingDomainConfig::UpdateCompartmentIdAndName(this);
  v14 = updated;
  if ( updated )
  {
    if ( (_QWORD)xmmword_180078C60 )
    {
      LOWORD(v33) = 0;
      v27 = GUID_NULL;
      LOWORD(v28) = 0;
      LODWORD(v11) = updated;
      FormatRRASErrorString(
        &v33,
        L"%s: UpdateCompartmentIdAndName failed for (%ws): %d.",
        L"RRasRoutingDomainConfig::RRasRoutingDomainConfig",
        v32,
        v11);
      v9 = &v27;
      if ( a3 )
        v9 = a3;
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C60,
        &v33,
        v9,
        0,
        &v28);
    }
    *((_DWORD *)this + 133) &= ~1u;
  }
  else
  {
    *((_DWORD *)this + 133) |= 1u;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v21);
  return this;
}

```

## disassembly

```asm
0x180043e78  mov     [rsp-8+arg_8], rbx
0x180043e7d  push    rbp
0x180043e7e  push    rsi
0x180043e7f  push    rdi
0x180043e80  push    r14
0x180043e82  push    r15
0x180043e84  lea     rbp, [rsp-850h]
0x180043e8c  sub     rsp, 950h
0x180043e93  mov     rax, cs:__security_cookie
0x180043e9a  xor     rax, rsp
0x180043e9d  mov     [rbp+870h+var_30], rax
0x180043ea4  mov     rdi, r8
0x180043ea7  mov     r14, rdx
0x180043eaa  mov     rbx, rcx
0x180043ead  xor     r15d, r15d
0x180043eb0  mov     [rsp+970h+var_930], r15d
0x180043eb5  xor     edx, edx; Val
0x180043eb7  lea     r8d, [r15+50h]; Size
0x180043ebb  lea     rcx, [rbp+870h+var_880]; void *
0x180043ebf  call    memset_0
0x180043ec4  mov     [rbp+870h+var_830], r15d
0x180043ec8  xor     edx, edx; Val
0x180043eca  mov     r8d, 7FCh; Size
0x180043ed0  lea     rcx, [rbp+870h+var_82C]; void *
0x180043ed4  call    memset_0
0x180043ed9  mov     [rbp+870h+var_8A8], r15d
0x180043edd  xorps   xmm0, xmm0
0x180043ee0  xor     eax, eax
0x180043ee2  movups  [rbp+870h+var_8A4], xmm0
0x180043ee6  movups  [rbp+870h+var_894], xmm0
0x180043eea  mov     [rbp+870h+var_884], eax
0x180043eed  movdqu  [rbp+870h+var_8E8], xmm0
0x180043ef2  mov     [rbp+870h+var_8F0], r15
0x180043ef6  xorps   xmm1, xmm1
0x180043ef9  movdqu  [rbp+870h+var_8D8], xmm1
0x180043efe  mov     [rbp+870h+var_8C8], r15
0x180043f02  or      esi, 0FFFFFFFFh
0x180043f05  mov     [rbp+870h+var_8C0], esi
0x180043f08  mov     [rbp+870h+var_8BC], r15d
0x180043f0c  cmp     qword ptr cs:xmmword_180078C60+8, r15
0x180043f13  jz      short loc_180043F2F
0x180043f15  mov     [rsp+970h+var_950], rdi; struct _GUID *
0x180043f1a  lea     r8, [rsp+970h+var_930]; unsigned int *
0x180043f1f  lea     rdx, aRrasroutingdom_2; "RRasRoutingDomainConfig::RRasRoutingDom"...
0x180043f26  lea     rcx, [rbp+870h+var_8F0]; this
0x180043f2a  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180043f2f  xorps   xmm0, xmm0
0x180043f32  movdqu  [rsp+970h+var_920], xmm0
0x180043f38  mov     [rsp+970h+var_928], r15
0x180043f3d  xorps   xmm1, xmm1
0x180043f40  movdqu  [rsp+970h+var_910], xmm1
0x180043f46  mov     [rsp+970h+var_900], r15
0x180043f4b  mov     [rsp+970h+var_8F8], esi
0x180043f4f  mov     [rsp+970h+var_8F4], r15d
0x180043f54  cmp     qword ptr cs:xmmword_180078C50+8, r15
0x180043f5b  jz      short loc_180043F71
0x180043f5d  xor     r8d, r8d; unsigned int *
0x180043f60  lea     rdx, aRrasroutingdom_24; "RRasRoutingDomainConfig::Initialize"
0x180043f67  lea     rcx, [rsp+970h+var_928]; this
0x180043f6c  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180043f71  xor     edx, edx; Val
0x180043f73  mov     r8d, 202h; Size
0x180043f79  mov     rcx, rbx; void *
0x180043f7c  call    memset_0
0x180043f81  xorps   xmm0, xmm0
0x180043f84  movups  xmmword ptr [rbx+248h], xmm0
0x180043f8b  xorps   xmm1, xmm1
0x180043f8e  xor     eax, eax
0x180043f90  movups  xmmword ptr [rbx+258h], xmm1
0x180043f97  mov     [rbx+268h], eax
0x180043f9d  lea     rsi, [rbx+204h]
0x180043fa4  movups  xmmword ptr [rsi], xmm0
0x180043fa7  mov     [rbx+23Ch], rax
0x180043fae  lea     rcx, [rbx+270h]; void *
0x180043fb5  xor     edx, edx; Val
0x180043fb7  lea     r8d, [rax+68h]; Size
0x180043fbb  call    memset_0
0x180043fc0  mov     [rbx+224h], r15
0x180043fc7  mov     [rbx+22Ch], r15
0x180043fce  mov     [rbx+234h], r15
0x180043fd5  xorps   xmm0, xmm0
0x180043fd8  movups  xmmword ptr [rbx+348h], xmm0
0x180043fdf  mov     qword ptr [rbx+340h], 0FFFFFFFF80000002h
0x180043fea  mov     [rbx+214h], r15
0x180043ff1  mov     [rbx+21Ch], r15d
0x180043ff8  mov     [rbx+338h], r15
0x180043fff  mov     dword ptr [rbx+220h], 2
0x180044009  mov     r8d, r15d
0x18004400c  mov     edx, r8d
0x18004400f  mov     ecx, r15d
0x180044012  test    r8d, r8d
0x180044015  setnz   cl
0x180044018  lea     rax, [rdx+rdx*2]
0x18004401c  mov     [rbx+rax*4+228h], ecx
0x180044023  mov     ecx, 1
0x180044028  lock xadd cs:dword_180078CC0, ecx
0x180044030  inc     ecx
0x180044032  lea     rax, [rdx+rdx*2]
0x180044036  mov     [rbx+rax*4+22Ch], ecx
0x18004403d  inc     r8d
0x180044040  cmp     r8d, [rbx+220h]
0x180044047  jb      short loc_18004400C
0x180044049  lea     rcx, [rbx+2D8h]; Resource
0x180044050  call    cs:__imp_RtlInitializeResource
0x180044056  nop
0x180044057  lea     rcx, [rsp+970h+var_928]; this
0x18004405c  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180044061  mov     [rbx+340h], r14
0x180044068  movaps  xmm0, xmmword ptr [rdi]
0x18004406b  movdqu  xmmword ptr [rsi], xmm0
0x18004406f  lea     r8, [rbp+870h+var_880]
0x180044073  mov     edx, 28h ; '('
0x180044078  mov     rcx, rsi
0x18004407b  call    MprConvertGuidToString
0x180044080  mov     rcx, rbx; this
0x180044083  call    ?UpdateCompartmentIdAndName@RRasRoutingDomainConfig@@QEAAKXZ; RRasRoutingDomainConfig::UpdateCompartmentIdAndName(void)
0x180044088  mov     [rsp+970h+var_930], eax
0x18004408c  test    eax, eax
0x18004408e  jz      short loc_18004410E
0x180044090  cmp     qword ptr cs:xmmword_180078C60, r15
0x180044097  jz      short loc_180044105
0x180044099  mov     word ptr [rbp+870h+var_830], r15w
0x18004409e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800440a5  movdqu  [rbp+870h+var_8B8], xmm0
0x1800440aa  mov     word ptr [rbp+870h+var_8A8], r15w
0x1800440af  mov     dword ptr [rsp+970h+var_950], eax
0x1800440b3  lea     r9, [rbp+870h+var_880]
0x1800440b7  lea     r8, aRrasroutingdom_2; "RRasRoutingDomainConfig::RRasRoutingDom"...
0x1800440be  lea     rdx, aSUpdatecompart; "%s: UpdateCompartmentIdAndName failed f"...
0x1800440c5  lea     rcx, [rbp+870h+var_830]
0x1800440c9  call    FormatRRASErrorString
0x1800440ce  lea     r9, [rbp+870h+var_8B8]
0x1800440d2  test    rdi, rdi
0x1800440d5  cmovnz  r9, rdi
0x1800440d9  lea     rax, [rbp+870h+var_8A8]
0x1800440dd  mov     [rsp+970h+var_948], rax
0x1800440e2  mov     [rsp+970h+var_950], r15
0x1800440e7  lea     r8, [rbp+870h+var_830]
0x1800440eb  mov     rdx, qword ptr cs:xmmword_180078C60
0x1800440f2  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x1800440f9  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180044100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044105  and     dword ptr [rbx+214h], 0FFFFFFFEh
0x18004410c  jmp     short loc_180044115
0x18004410e  or      dword ptr [rbx+214h], 1
0x180044115  lea     rcx, [rbp+870h+var_8F0]; this
0x180044119  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18004411e  mov     rax, rbx
0x180044121  mov     rcx, [rbp+870h+var_30]
0x180044128  xor     rcx, rsp; StackCookie
0x18004412b  call    __security_check_cookie
0x180044130  mov     rbx, [rsp+970h+arg_8]
0x180044138  add     rsp, 950h
0x18004413f  pop     r15
0x180044141  pop     r14
0x180044143  pop     rdi
0x180044144  pop     rsi
0x180044145  pop     rbp
0x180044146  retn
```
