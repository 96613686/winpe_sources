# SetRoutingDomainConfiguration

- ea: `0x1800379b0`
- end: `0x180037bb5`
- name: `SetRoutingDomainConfiguration`
- size: `517`
- prototype: `__int64 __usercall@<rax>(struct _GUID *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180016884`

## callees

- `0x1800379b0`
- `0x18003d380`
- `0x180041edc`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## string_xrefs

- `0x180037a8a`: `%s: The config store is not available.`
- `0x180037a54`: `SetRoutingDomainConfiguration`
- `0x180037a7f`: `SetRoutingDomainConfiguration`
- `0x180037b24`: `SetRoutingDomainConfiguration`
- `0x180037b32`: `%s: cfgStore->SetRoutingDomainConfiguration failed: %d.`

## pseudocode

```c
__int64 __fastcall SetRoutingDomainConfiguration(
        struct _GUID *a1,
        unsigned int a2,
        unsigned int a3,
        int a4,
        __int64 a5)
{
  void (*v9)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  struct RRasConfigStore *Instance; // rax
  const struct _GUID *v11; // r9
  unsigned int v12; // ebx
  const struct _GUID *v13; // r9
  unsigned __int16 *v15; // [rsp+28h] [rbp-D8h]
  unsigned int v16; // [rsp+30h] [rbp-D0h]
  unsigned int v17; // [rsp+40h] [rbp-C0h] BYREF
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

  v17 = 0;
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
      L"SetRoutingDomainConfiguration",
      &v17,
      v9,
      a1,
      v15,
      v16);
  Instance = RRasConfigStore::GetInstance();
  if ( Instance )
  {
    v17 = RRasConfigStore::SetRoutingDomainConfiguration(Instance, a1, a2, a3, a4, a5);
    v12 = v17;
    if ( v17 && (_QWORD)xmmword_1800710A0 )
    {
      LOWORD(v29) = 0;
      LOWORD(v25) = 0;
      v24 = GUID_NULL;
      FormatRRASErrorString(
        &v29,
        L"%s: cfgStore->SetRoutingDomainConfiguration failed: %d.",
        L"SetRoutingDomainConfiguration",
        v17);
      v13 = &v24;
      if ( a1 )
        v13 = a1;
      gCfgStoreParamTemplateFunc(
        gCfgStoreEtwContext,
        (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
        (const unsigned __int16 *)&v29,
        v13,
        0,
        (const unsigned __int16 *)&v25);
      v12 = v17;
    }
  }
  else
  {
    if ( (_QWORD)xmmword_1800710A0 )
    {
      LOWORD(v29) = 0;
      LOWORD(v25) = 0;
      v24 = GUID_NULL;
      FormatRRASErrorString(&v29, L"%s: The config store is not available.", L"SetRoutingDomainConfiguration");
      v11 = &v24;
      if ( a1 )
        v11 = a1;
      gCfgStoreParamTemplateFunc(
        gCfgStoreEtwContext,
        (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
        (const unsigned __int16 *)&v29,
        v11,
        0,
        (const unsigned __int16 *)&v25);
    }
    v12 = 1003;
    v17 = 1003;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v18);
  return v12;
}

```

## disassembly

```asm
0x1800379b0  push    rbp
0x1800379b2  push    rbx
0x1800379b3  push    rsi
0x1800379b4  push    rdi
0x1800379b5  push    r14
0x1800379b7  push    r15
0x1800379b9  lea     rbp, [rsp-7D8h]
0x1800379c1  sub     rsp, 8D8h
0x1800379c8  mov     rax, cs:__security_cookie
0x1800379cf  xor     rax, rsp
0x1800379d2  mov     [rbp+800h+var_40], rax
0x1800379d9  mov     r15, [rbp+800h+arg_20]
0x1800379e0  mov     esi, r8d
0x1800379e3  mov     ebx, edx
0x1800379e5  mov     [rsp+900h+var_8C0], 0
0x1800379ed  mov     rdi, rcx
0x1800379f0  xor     eax, eax
0x1800379f2  xor     edx, edx; Val
0x1800379f4  mov     [rbp+800h+var_840], eax
0x1800379f7  mov     r8d, 7FCh; Size
0x1800379fd  lea     rcx, [rbp+800h+var_83C]; void *
0x180037a01  mov     r14d, r9d
0x180037a04  call    memset_0
0x180037a09  xor     eax, eax
0x180037a0b  mov     [rsp+900h+var_888], 0FFFFFFFFh
0x180037a13  cmp     qword ptr cs:xmmword_1800710A0+8, rax
0x180037a1a  xorps   xmm0, xmm0
0x180037a1d  xorps   xmm1, xmm1
0x180037a20  mov     [rbp+800h+var_870], eax
0x180037a23  movups  [rbp+800h+var_86C], xmm0
0x180037a27  mov     [rbp+800h+var_84C], eax
0x180037a2a  movups  [rbp+800h+var_85C], xmm0
0x180037a2e  mov     [rsp+900h+var_8B8], rax
0x180037a33  movdqu  [rsp+900h+var_8B0], xmm0
0x180037a39  mov     [rsp+900h+var_890], rax
0x180037a3e  movdqu  [rsp+900h+var_8A0], xmm1
0x180037a44  mov     [rsp+900h+var_884], eax
0x180037a48  jz      short loc_180037A65
0x180037a4a  lea     r8, [rsp+900h+var_8C0]; unsigned int *
0x180037a4f  mov     [rsp+900h+var_8E0], rdi; struct _GUID *
0x180037a54  lea     rdx, aSetroutingdoma_0; "SetRoutingDomainConfiguration"
0x180037a5b  lea     rcx, [rsp+900h+var_8B8]; this
0x180037a60  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180037a65  call    ?GetInstance@RRasConfigStore@@SAPEAV1@XZ; RRasConfigStore::GetInstance(void)
0x180037a6a  test    rax, rax
0x180037a6d  jnz     short loc_180037AEC
0x180037a6f  cmp     qword ptr cs:xmmword_1800710A0, rax
0x180037a76  jz      short loc_180037ADE
0x180037a78  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180037a7f  lea     r8, aSetroutingdoma_0; "SetRoutingDomainConfiguration"
0x180037a86  mov     word ptr [rbp+800h+var_840], ax
0x180037a8a  lea     rdx, aSTheConfigStor_0; "%s: The config store is not available."
0x180037a91  mov     word ptr [rbp+800h+var_870], ax
0x180037a95  lea     rcx, [rbp+800h+var_840]
0x180037a99  movdqu  [rbp+800h+var_880], xmm0
0x180037a9e  call    FormatRRASErrorString
0x180037aa3  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180037aaa  lea     rax, [rbp+800h+var_870]
0x180037aae  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180037ab5  lea     r9, [rbp+800h+var_880]
0x180037ab9  mov     [rsp+900h+var_8D8], rax
0x180037abe  lea     r8, [rbp+800h+var_840]
0x180037ac2  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180037ac9  test    rdi, rdi
0x180037acc  mov     [rsp+900h+var_8E0], 0
0x180037ad5  cmovnz  r9, rdi
0x180037ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037ade  mov     ebx, 3EBh
0x180037ae3  mov     [rsp+900h+var_8C0], ebx
0x180037ae7  jmp     loc_180037B8A
0x180037aec  mov     [rsp+900h+var_8D8], r15
0x180037af1  mov     r9d, esi
0x180037af4  mov     r8d, ebx
0x180037af7  mov     dword ptr [rsp+900h+var_8E0], r14d
0x180037afc  mov     rdx, rdi
0x180037aff  mov     rcx, rax
0x180037b02  call    ?SetRoutingDomainConfiguration@RRasConfigStore@@QEAAKPEAU_GUID@@W4_RRAS_RD_CONFIG_TYPE@@HKPEAX@Z; RRasConfigStore::SetRoutingDomainConfiguration(_GUID *,_RRAS_RD_CONFIG_TYPE,int,ulong,void *)
0x180037b07  mov     [rsp+900h+var_8C0], eax
0x180037b0b  mov     ebx, eax
0x180037b0d  test    eax, eax
0x180037b0f  jz      short loc_180037B8A
0x180037b11  cmp     qword ptr cs:xmmword_1800710A0, 0
0x180037b19  jz      short loc_180037B8A
0x180037b1b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180037b22  xor     eax, eax
0x180037b24  lea     r8, aSetroutingdoma_0; "SetRoutingDomainConfiguration"
0x180037b2b  mov     r9d, ebx
0x180037b2e  mov     word ptr [rbp+800h+var_840], ax
0x180037b32  lea     rdx, aSCfgstoreSetro_0; "%s: cfgStore->SetRoutingDomainConfigura"...
0x180037b39  mov     word ptr [rbp+800h+var_870], ax
0x180037b3d  lea     rcx, [rbp+800h+var_840]
0x180037b41  movdqu  [rbp+800h+var_880], xmm0
0x180037b46  call    FormatRRASErrorString
0x180037b4b  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180037b52  lea     rax, [rbp+800h+var_870]
0x180037b56  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180037b5d  lea     r9, [rbp+800h+var_880]
0x180037b61  mov     [rsp+900h+var_8D8], rax
0x180037b66  lea     r8, [rbp+800h+var_840]
0x180037b6a  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180037b71  test    rdi, rdi
0x180037b74  mov     [rsp+900h+var_8E0], 0
0x180037b7d  cmovnz  r9, rdi
0x180037b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b86  mov     ebx, [rsp+900h+var_8C0]
0x180037b8a  lea     rcx, [rsp+900h+var_8B8]; this
0x180037b8f  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180037b94  mov     eax, ebx
0x180037b96  mov     rcx, [rbp+800h+var_40]
0x180037b9d  xor     rcx, rsp; StackCookie
0x180037ba0  call    __security_check_cookie
0x180037ba5  add     rsp, 8D8h
0x180037bac  pop     r15
0x180037bae  pop     r14
0x180037bb0  pop     rdi
0x180037bb1  pop     rsi
0x180037bb2  pop     rbx
0x180037bb3  pop     rbp
0x180037bb4  retn
```
