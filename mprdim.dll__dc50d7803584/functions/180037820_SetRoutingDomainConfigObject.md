# SetRoutingDomainConfigObject

- ea: `0x180037820`
- end: `0x1800379a7`
- name: `SetRoutingDomainConfigObject`
- size: `391`
- prototype: `__int64 __fastcall(__int64, struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000eb60`

## callees

- `0x180037820`
- `0x18003d380`
- `0x180041ca4`
- `0x18004583c`
- `0x180045ad4`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## string_xrefs

- `0x1800378dc`: `%s: The config store is not available.`
- `0x1800378ac`: `SetRoutingDomainConfigObject`
- `0x1800378d0`: `SetRoutingDomainConfigObject`
- `0x180037938`: `SetRoutingDomainConfigObject`
- `0x180037947`: `%s: cfgStore->SetRoutingDomainConfigObject failed: %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SetRoutingDomainConfigObject(__int64 a1, struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *a2)
{
  void (*v3)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  RRasConfigStore *Instance; // rax
  int v5; // edx
  unsigned int v6; // ebx
  unsigned int v8; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v9; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v10; // [rsp+30h] [rbp-D0h]
  __int128 v11; // [rsp+40h] [rbp-C0h]
  __int64 v12; // [rsp+50h] [rbp-B0h]
  int v13; // [rsp+58h] [rbp-A8h]
  int v14; // [rsp+5Ch] [rbp-A4h]
  int v15; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v16[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v8 = 0;
  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  v9 = 0;
  v10 = 0;
  v12 = 0;
  v11 = 0;
  v13 = -1;
  v14 = 0;
  if ( *((_QWORD *)&xmmword_180071090 + 1) )
    EtwFuncEntryExitTracer::Initialize((EtwFuncEntryExitTracer *)&v9, L"SetRoutingDomainConfigObject", &v8, v3);
  Instance = RRasConfigStore::GetInstance();
  if ( Instance )
  {
    v8 = RRasConfigStore::SetRoutingDomainConfigObject(Instance, v5, a2);
    v6 = v8;
    if ( v8 && (_QWORD)xmmword_180071090 )
    {
      LOWORD(v15) = 0;
      FormatRRASErrorString(
        &v15,
        L"%s: cfgStore->SetRoutingDomainConfigObject failed: %d.",
        L"SetRoutingDomainConfigObject",
        v8);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v15);
      v6 = v8;
    }
  }
  else
  {
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v15) = 0;
      FormatRRASErrorString(&v15, L"%s: The config store is not available.", L"SetRoutingDomainConfigObject");
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v15);
    }
    v6 = 1003;
    v8 = 1003;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v9);
  return v6;
}

```

## disassembly

```asm
0x180037820  mov     [rsp-8+arg_0], rbx
0x180037825  push    rbp
0x180037826  lea     rbp, [rsp-770h]
0x18003782e  sub     rsp, 870h
0x180037835  mov     rax, cs:__security_cookie
0x18003783c  xor     rax, rsp
0x18003783f  mov     [rbp+770h+var_10], rax
0x180037846  mov     rbx, rdx
0x180037849  mov     [rsp+870h+var_850], 0
0x180037851  xor     eax, eax
0x180037853  lea     rcx, [rsp+870h+var_80C]; void *
0x180037858  xor     edx, edx; Val
0x18003785a  mov     [rsp+870h+var_810], eax
0x18003785e  mov     r8d, 7FCh; Size
0x180037864  call    memset_0
0x180037869  cmp     qword ptr cs:xmmword_180071090+8, 0
0x180037871  xorps   xmm0, xmm0
0x180037874  xorps   xmm1, xmm1
0x180037877  mov     [rsp+870h+var_848], 0
0x180037880  movdqu  [rsp+870h+var_840], xmm0
0x180037886  mov     [rsp+870h+var_820], 0
0x18003788f  movdqu  [rsp+870h+var_830], xmm1
0x180037895  mov     [rsp+870h+var_818], 0FFFFFFFFh
0x18003789d  mov     [rsp+870h+var_814], 0
0x1800378a5  jz      short loc_1800378BD
0x1800378a7  lea     r8, [rsp+870h+var_850]; unsigned int *
0x1800378ac  lea     rdx, aSetroutingdoma; "SetRoutingDomainConfigObject"
0x1800378b3  lea     rcx, [rsp+870h+var_848]; this
0x1800378b8  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x1800378bd  call    ?GetInstance@RRasConfigStore@@SAPEAV1@XZ; RRasConfigStore::GetInstance(void)
0x1800378c2  test    rax, rax
0x1800378c5  jnz     short loc_180037917
0x1800378c7  cmp     qword ptr cs:xmmword_180071090, rax
0x1800378ce  jz      short loc_18003790C
0x1800378d0  lea     r8, aSetroutingdoma; "SetRoutingDomainConfigObject"
0x1800378d7  mov     word ptr [rsp+870h+var_810], ax
0x1800378dc  lea     rdx, aSTheConfigStor_0; "%s: The config store is not available."
0x1800378e3  lea     rcx, [rsp+870h+var_810]
0x1800378e8  call    FormatRRASErrorString
0x1800378ed  mov     rdx, qword ptr cs:xmmword_180071090
0x1800378f4  lea     r8, [rsp+870h+var_810]
0x1800378f9  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180037900  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180037907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003790c  mov     ebx, 3EBh
0x180037911  mov     [rsp+870h+var_850], ebx
0x180037915  jmp     short loc_18003797B
0x180037917  mov     r8, rbx; struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *
0x18003791a  mov     rcx, rax; this
0x18003791d  call    ?SetRoutingDomainConfigObject@RRasConfigStore@@QEAAKHPEAU_MPRI_ROUTING_DOMAIN_CONFIG_EX@@@Z; RRasConfigStore::SetRoutingDomainConfigObject(int,_MPRI_ROUTING_DOMAIN_CONFIG_EX *)
0x180037922  mov     [rsp+870h+var_850], eax
0x180037926  mov     ebx, eax
0x180037928  test    eax, eax
0x18003792a  jz      short loc_18003797B
0x18003792c  cmp     qword ptr cs:xmmword_180071090, 0
0x180037934  jz      short loc_18003797B
0x180037936  xor     eax, eax
0x180037938  lea     r8, aSetroutingdoma; "SetRoutingDomainConfigObject"
0x18003793f  mov     r9d, ebx
0x180037942  mov     word ptr [rsp+870h+var_810], ax
0x180037947  lea     rdx, aSCfgstoreSetro; "%s: cfgStore->SetRoutingDomainConfigObj"...
0x18003794e  lea     rcx, [rsp+870h+var_810]
0x180037953  call    FormatRRASErrorString
0x180037958  mov     rdx, qword ptr cs:xmmword_180071090
0x18003795f  lea     r8, [rsp+870h+var_810]
0x180037964  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003796b  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180037972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037977  mov     ebx, [rsp+870h+var_850]
0x18003797b  lea     rcx, [rsp+870h+var_848]; this
0x180037980  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180037985  mov     eax, ebx
0x180037987  mov     rcx, [rbp+770h+var_10]
0x18003798e  xor     rcx, rsp; StackCookie
0x180037991  call    __security_check_cookie
0x180037996  mov     rbx, [rsp+870h+arg_0]
0x18003799e  add     rsp, 870h
0x1800379a5  pop     rbp
0x1800379a6  retn
```
