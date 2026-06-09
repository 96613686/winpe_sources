# GetRoutingDomainConfigObject

- ea: `0x180035b0c`
- end: `0x180035d05`
- name: `GetRoutingDomainConfigObject`
- size: `505`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, unsigned int@<edx>, unsigned int@<r8d>, struct _MPRI_ROUTING_DOMAIN_CONFIG_EX **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000da10`
- `0x18000e9a0`

## callees

- `0x180035b0c`
- `0x18003d380`
- `0x18003d3f4`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## string_xrefs

- `0x180035be1`: `%s: The config store is not available.`
- `0x180035bab`: `GetRoutingDomainConfigObject`
- `0x180035bd6`: `GetRoutingDomainConfigObject`
- `0x180035c76`: `GetRoutingDomainConfigObject`
- `0x180035c84`: `%s: cfgStore->GetRoutingDomainConfigObject failed: %d.`

## pseudocode

```c
__int64 __fastcall GetRoutingDomainConfigObject(
        struct _GUID *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        struct _MPRI_ROUTING_DOMAIN_CONFIG_EX **a5)
{
  void (*v8)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  RRasConfigStore *Instance; // rax
  const struct _GUID *v10; // r9
  unsigned int v11; // ebx
  const struct _GUID *v12; // r9
  int v14; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v15; // [rsp+28h] [rbp-D8h]
  unsigned int v16; // [rsp+30h] [rbp-D0h]
  unsigned int RoutingDomainConfigObject; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v19; // [rsp+50h] [rbp-B0h]
  __int128 v20; // [rsp+60h] [rbp-A0h]
  __int64 v21; // [rsp+70h] [rbp-90h]
  int v22; // [rsp+78h] [rbp-88h]
  int v23; // [rsp+7Ch] [rbp-84h]
  GUID v24; // [rsp+80h] [rbp-80h] BYREF
  int v25; // [rsp+90h] [rbp-70h] BYREF
  __int128 v26; // [rsp+94h] [rbp-6Ch]
  __int128 v27; // [rsp+A4h] [rbp-5Ch]
  int v28; // [rsp+B4h] [rbp-4Ch]
  int v29; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v30[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  RoutingDomainConfigObject = 0;
  v29 = 0;
  memset_0(v30, 0, sizeof(v30));
  v22 = -1;
  v25 = 0;
  v26 = 0;
  v28 = 0;
  v27 = 0;
  v18 = 0;
  v19 = 0;
  v21 = 0;
  v20 = 0;
  v23 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v18,
      L"GetRoutingDomainConfigObject",
      &RoutingDomainConfigObject,
      v8,
      a1,
      v15,
      v16);
  Instance = RRasConfigStore::GetInstance();
  if ( Instance )
  {
    RoutingDomainConfigObject = RRasConfigStore::GetRoutingDomainConfigObject(Instance, a1, a2, a3, v14, a5);
    v11 = RoutingDomainConfigObject;
    if ( RoutingDomainConfigObject && (_QWORD)xmmword_1800710A0 )
    {
      LOWORD(v29) = 0;
      LOWORD(v25) = 0;
      v24 = GUID_NULL;
      FormatRRASErrorString(
        &v29,
        L"%s: cfgStore->GetRoutingDomainConfigObject failed: %d.",
        L"GetRoutingDomainConfigObject",
        RoutingDomainConfigObject);
      v12 = &v24;
      if ( a1 )
        v12 = a1;
      gCfgStoreParamTemplateFunc(
        gCfgStoreEtwContext,
        (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
        (const unsigned __int16 *)&v29,
        v12,
        0,
        (const unsigned __int16 *)&v25);
      v11 = RoutingDomainConfigObject;
    }
  }
  else
  {
    if ( (_QWORD)xmmword_1800710A0 )
    {
      LOWORD(v29) = 0;
      LOWORD(v25) = 0;
      v24 = GUID_NULL;
      FormatRRASErrorString(&v29, L"%s: The config store is not available.", L"GetRoutingDomainConfigObject");
      v10 = &v24;
      if ( a1 )
        v10 = a1;
      gCfgStoreParamTemplateFunc(
        gCfgStoreEtwContext,
        (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
        (const unsigned __int16 *)&v29,
        v10,
        0,
        (const unsigned __int16 *)&v25);
    }
    v11 = 1003;
    RoutingDomainConfigObject = 1003;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v18);
  return v11;
}

```

## disassembly

```asm
0x180035b0c  push    rbp
0x180035b0e  push    rbx
0x180035b0f  push    rsi
0x180035b10  push    rdi
0x180035b11  push    r14
0x180035b13  lea     rbp, [rsp-7D0h]
0x180035b1b  sub     rsp, 8D0h
0x180035b22  mov     rax, cs:__security_cookie
0x180035b29  xor     rax, rsp
0x180035b2c  mov     [rbp+7F0h+var_30], rax
0x180035b33  mov     r14, [rbp+7F0h+arg_20]
0x180035b3a  mov     esi, r8d
0x180035b3d  mov     ebx, edx
0x180035b3f  mov     [rsp+8F0h+var_8B0], 0
0x180035b47  mov     rdi, rcx
0x180035b4a  xor     eax, eax
0x180035b4c  xor     edx, edx; Val
0x180035b4e  mov     [rbp+7F0h+var_830], eax
0x180035b51  mov     r8d, 7FCh; Size
0x180035b57  lea     rcx, [rbp+7F0h+var_82C]; void *
0x180035b5b  call    memset_0
0x180035b60  xor     eax, eax
0x180035b62  mov     [rsp+8F0h+var_878], 0FFFFFFFFh
0x180035b6a  cmp     qword ptr cs:xmmword_1800710A0+8, rax
0x180035b71  xorps   xmm0, xmm0
0x180035b74  xorps   xmm1, xmm1
0x180035b77  mov     [rbp+7F0h+var_860], eax
0x180035b7a  movups  [rbp+7F0h+var_85C], xmm0
0x180035b7e  mov     [rbp+7F0h+var_83C], eax
0x180035b81  movups  [rbp+7F0h+var_84C], xmm0
0x180035b85  mov     [rsp+8F0h+var_8A8], rax
0x180035b8a  movdqu  [rsp+8F0h+var_8A0], xmm0
0x180035b90  mov     [rsp+8F0h+var_880], rax
0x180035b95  movdqu  [rsp+8F0h+var_890], xmm1
0x180035b9b  mov     [rsp+8F0h+var_874], eax
0x180035b9f  jz      short loc_180035BBC
0x180035ba1  lea     r8, [rsp+8F0h+var_8B0]; unsigned int *
0x180035ba6  mov     [rsp+8F0h+var_8D0], rdi; int
0x180035bab  lea     rdx, aGetroutingdoma; "GetRoutingDomainConfigObject"
0x180035bb2  lea     rcx, [rsp+8F0h+var_8A8]; this
0x180035bb7  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180035bbc  call    ?GetInstance@RRasConfigStore@@SAPEAV1@XZ; RRasConfigStore::GetInstance(void)
0x180035bc1  test    rax, rax
0x180035bc4  jnz     short loc_180035C43
0x180035bc6  cmp     qword ptr cs:xmmword_1800710A0, rax
0x180035bcd  jz      short loc_180035C35
0x180035bcf  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180035bd6  lea     r8, aGetroutingdoma; "GetRoutingDomainConfigObject"
0x180035bdd  mov     word ptr [rbp+7F0h+var_830], ax
0x180035be1  lea     rdx, aSTheConfigStor_0; "%s: The config store is not available."
0x180035be8  mov     word ptr [rbp+7F0h+var_860], ax
0x180035bec  lea     rcx, [rbp+7F0h+var_830]
0x180035bf0  movdqu  [rbp+7F0h+var_870], xmm0
0x180035bf5  call    FormatRRASErrorString
0x180035bfa  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180035c01  lea     rax, [rbp+7F0h+var_860]
0x180035c05  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180035c0c  lea     r9, [rbp+7F0h+var_870]
0x180035c10  mov     [rsp+8F0h+var_8C8], rax
0x180035c15  lea     r8, [rbp+7F0h+var_830]
0x180035c19  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180035c20  test    rdi, rdi
0x180035c23  mov     [rsp+8F0h+var_8D0], 0
0x180035c2c  cmovnz  r9, rdi
0x180035c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c35  mov     ebx, 3EBh
0x180035c3a  mov     [rsp+8F0h+var_8B0], ebx
0x180035c3e  jmp     loc_180035CDC
0x180035c43  mov     r9d, esi; unsigned int
0x180035c46  mov     [rsp+8F0h+var_8C8], r14; struct _MPRI_ROUTING_DOMAIN_CONFIG_EX **
0x180035c4b  mov     r8d, ebx; unsigned int
0x180035c4e  mov     rdx, rdi; struct _GUID *
0x180035c51  mov     rcx, rax; this
0x180035c54  call    ?GetRoutingDomainConfigObject@RRasConfigStore@@QEAAKPEAU_GUID@@KKHPEAPEAU_MPRI_ROUTING_DOMAIN_CONFIG_EX@@@Z; RRasConfigStore::GetRoutingDomainConfigObject(_GUID *,ulong,ulong,int,_MPRI_ROUTING_DOMAIN_CONFIG_EX * *)
0x180035c59  mov     [rsp+8F0h+var_8B0], eax
0x180035c5d  mov     ebx, eax
0x180035c5f  test    eax, eax
0x180035c61  jz      short loc_180035CDC
0x180035c63  cmp     qword ptr cs:xmmword_1800710A0, 0
0x180035c6b  jz      short loc_180035CDC
0x180035c6d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180035c74  xor     eax, eax
0x180035c76  lea     r8, aGetroutingdoma; "GetRoutingDomainConfigObject"
0x180035c7d  mov     r9d, ebx
0x180035c80  mov     word ptr [rbp+7F0h+var_830], ax
0x180035c84  lea     rdx, aSCfgstoreGetro_0; "%s: cfgStore->GetRoutingDomainConfigObj"...
0x180035c8b  mov     word ptr [rbp+7F0h+var_860], ax
0x180035c8f  lea     rcx, [rbp+7F0h+var_830]
0x180035c93  movdqu  [rbp+7F0h+var_870], xmm0
0x180035c98  call    FormatRRASErrorString
0x180035c9d  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180035ca4  lea     rax, [rbp+7F0h+var_860]
0x180035ca8  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180035caf  lea     r9, [rbp+7F0h+var_870]
0x180035cb3  mov     [rsp+8F0h+var_8C8], rax
0x180035cb8  lea     r8, [rbp+7F0h+var_830]
0x180035cbc  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180035cc3  test    rdi, rdi
0x180035cc6  mov     [rsp+8F0h+var_8D0], 0
0x180035ccf  cmovnz  r9, rdi
0x180035cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035cd8  mov     ebx, [rsp+8F0h+var_8B0]
0x180035cdc  lea     rcx, [rsp+8F0h+var_8A8]; this
0x180035ce1  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180035ce6  mov     eax, ebx
0x180035ce8  mov     rcx, [rbp+7F0h+var_30]
0x180035cef  xor     rcx, rsp; StackCookie
0x180035cf2  call    __security_check_cookie
0x180035cf7  add     rsp, 8D0h
0x180035cfe  pop     r14
0x180035d00  pop     rdi
0x180035d01  pop     rsi
0x180035d02  pop     rbx
0x180035d03  pop     rbp
0x180035d04  retn
```
