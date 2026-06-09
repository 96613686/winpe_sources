# CleanUpRrasConfigurationStore

- ea: `0x180040b1c`
- end: `0x180040d3f`
- name: `CleanUpRrasConfigurationStore`
- size: `547`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x1800178ac`
- `0x180017960`
- `0x1800267f0`

## callees

- `0x180040b1c`
- `0x1800442cc`
- `0x18004467c`
- `0x180048b84`
- `0x180050b2c`
- `0x180050cd4`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180040cb6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180040cb6`

## string_xrefs

- `0x180040b6f`: `CleanUpRrasConfigurationStore`
- `0x180040bca`: `%s: Cleaning up Rras Configuration Store...`
- `0x180040c1d`: `%s: The config store instance could not be found.`
- `0x180040c7d`: `%s: cfgStore->CleanupConfigStore failed: %d.`
- `0x180040cd3`: `%s: Rras Configuration Store cleanup Done.`

## pseudocode

```c
__int64 CleanUpRrasConfigurationStore()
{
  void (*v0)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  RRasConfigStore *Instance; // rax
  __int64 v2; // r9
  __int64 v3; // rdx
  RRasConfigStore *v4; // rbx
  unsigned int v5; // ebx
  unsigned int v7; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v8; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v9; // [rsp+30h] [rbp-D0h]
  __int128 v10; // [rsp+40h] [rbp-C0h]
  __int64 v11; // [rsp+50h] [rbp-B0h]
  int v12; // [rsp+58h] [rbp-A8h]
  int v13; // [rsp+5Ch] [rbp-A4h]
  int v14; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v15[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v7 = 0;
  v14 = 0;
  memset_0(v15, 0, sizeof(v15));
  v8 = 0;
  v11 = 0;
  v9 = 0;
  v12 = -1;
  v10 = 0;
  v13 = 0;
  if ( *((_QWORD *)&xmmword_180078C50 + 1) )
  {
    EtwFuncEntryExitTracer::Initialize((EtwFuncEntryExitTracer *)&v8, L"CleanUpRrasConfigurationStore", &v7, v0);
    if ( *((_QWORD *)&xmmword_180078C50 + 1) )
    {
      LOWORD(v14) = 0;
      FormatRRASErrorString(&v14, L"%s: Cleaning up Rras Configuration Store...", L"CleanUpRrasConfigurationStore");
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        *((_QWORD *)&xmmword_180078C50 + 1),
        &v14);
    }
  }
  Instance = RRasConfigStore::GetInstance();
  if ( !Instance )
  {
    if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v14) = 0;
      FormatRRASErrorString(
        &v14,
        L"%s: The config store instance could not be found.",
        L"CleanUpRrasConfigurationStore");
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
        &v14);
    }
    v7 = 1003;
    goto LABEL_16;
  }
  v7 = RRasConfigStore::CleanupConfigStore(Instance);
  v2 = v7;
  if ( v7 )
  {
    if ( !(_QWORD)xmmword_180078C50 )
      goto LABEL_16;
    LOWORD(v14) = 0;
    FormatRRASErrorString(&v14, L"%s: cfgStore->CleanupConfigStore failed: %d.", L"CleanUpRrasConfigurationStore", v7);
    v3 = xmmword_180078C50;
LABEL_15:
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      v3,
      &v14);
    goto LABEL_16;
  }
  v4 = RRasConfigStore::configStoreObj;
  if ( RRasConfigStore::configStoreObj )
  {
    RRasConfigStore::~RRasConfigStore(RRasConfigStore::configStoreObj);
    operator delete(v4);
    RRasConfigStore::configStoreObj = 0;
  }
  if ( *((_QWORD *)&xmmword_180078C50 + 1) )
  {
    LOWORD(v14) = 0;
    FormatRRASErrorString(&v14, L"%s: Rras Configuration Store cleanup Done.", L"CleanUpRrasConfigurationStore", v2);
    v3 = *((_QWORD *)&xmmword_180078C50 + 1);
    goto LABEL_15;
  }
LABEL_16:
  v5 = v7;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v8);
  return v5;
}

```

## disassembly

```asm
0x180040b1c  mov     [rsp-8+arg_0], rbx
0x180040b21  mov     [rsp-8+arg_8], rsi
0x180040b26  push    rbp
0x180040b27  lea     rbp, [rsp-770h]
0x180040b2f  sub     rsp, 870h
0x180040b36  mov     rax, cs:__security_cookie
0x180040b3d  xor     rax, rsp
0x180040b40  mov     [rbp+770h+var_10], rax
0x180040b47  xor     eax, eax
0x180040b49  mov     [rsp+870h+var_850], 0
0x180040b51  xor     edx, edx; Val
0x180040b53  mov     [rsp+870h+var_810], eax
0x180040b57  mov     r8d, 7FCh; Size
0x180040b5d  lea     rcx, [rsp+870h+var_80C]; void *
0x180040b62  call    memset_0
0x180040b67  cmp     qword ptr cs:xmmword_180078C50+8, 0
0x180040b6f  lea     rsi, aCleanuprrascon; "CleanUpRrasConfigurationStore"
0x180040b76  xorps   xmm0, xmm0
0x180040b79  mov     [rsp+870h+var_848], 0
0x180040b82  xorps   xmm1, xmm1
0x180040b85  mov     [rsp+870h+var_820], 0
0x180040b8e  movdqu  [rsp+870h+var_840], xmm0
0x180040b94  mov     [rsp+870h+var_818], 0FFFFFFFFh
0x180040b9c  movdqu  [rsp+870h+var_830], xmm1
0x180040ba2  mov     [rsp+870h+var_814], 0
0x180040baa  jz      short loc_180040C02
0x180040bac  lea     r8, [rsp+870h+var_850]; unsigned int *
0x180040bb1  mov     rdx, rsi; unsigned __int16 *
0x180040bb4  lea     rcx, [rsp+870h+var_848]; this
0x180040bb9  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180040bbe  cmp     qword ptr cs:xmmword_180078C50+8, 0
0x180040bc6  jz      short loc_180040C02
0x180040bc8  xor     eax, eax
0x180040bca  lea     rdx, aSCleaningUpRra; "%s: Cleaning up Rras Configuration Stor"...
0x180040bd1  mov     r8, rsi
0x180040bd4  mov     word ptr [rsp+870h+var_810], ax
0x180040bd9  lea     rcx, [rsp+870h+var_810]
0x180040bde  call    FormatRRASErrorString
0x180040be3  mov     rdx, qword ptr cs:xmmword_180078C50+8
0x180040bea  lea     r8, [rsp+870h+var_810]
0x180040bef  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180040bf6  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180040bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c02  call    ?GetInstance@RRasConfigStore@@SAPEAV1@XZ; RRasConfigStore::GetInstance(void)
0x180040c07  test    rax, rax
0x180040c0a  jnz     short loc_180040C5A
0x180040c0c  cmp     qword ptr cs:xmmword_180078C50, rax
0x180040c13  jz      short loc_180040C4D
0x180040c15  mov     r8, rsi
0x180040c18  mov     word ptr [rsp+870h+var_810], ax
0x180040c1d  lea     rdx, aSTheConfigStor; "%s: The config store instance could not"...
0x180040c24  lea     rcx, [rsp+870h+var_810]
0x180040c29  call    FormatRRASErrorString
0x180040c2e  mov     rdx, qword ptr cs:xmmword_180078C50
0x180040c35  lea     r8, [rsp+870h+var_810]
0x180040c3a  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180040c41  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180040c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c4d  mov     [rsp+870h+var_850], 3EBh
0x180040c55  jmp     loc_180040D0B
0x180040c5a  mov     rcx, rax; this
0x180040c5d  call    ?CleanupConfigStore@RRasConfigStore@@QEAAKXZ; RRasConfigStore::CleanupConfigStore(void)
0x180040c62  mov     [rsp+870h+var_850], eax
0x180040c66  mov     r9d, eax
0x180040c69  test    eax, eax
0x180040c6b  jz      short loc_180040C9F
0x180040c6d  cmp     qword ptr cs:xmmword_180078C50, 0
0x180040c75  jz      loc_180040D0B
0x180040c7b  xor     eax, eax
0x180040c7d  lea     rdx, aSCfgstoreClean; "%s: cfgStore->CleanupConfigStore failed"...
0x180040c84  mov     r8, rsi
0x180040c87  mov     word ptr [rsp+870h+var_810], ax
0x180040c8c  lea     rcx, [rsp+870h+var_810]
0x180040c91  call    FormatRRASErrorString
0x180040c96  mov     rdx, qword ptr cs:xmmword_180078C50
0x180040c9d  jmp     short loc_180040CF3
0x180040c9f  mov     rbx, cs:?configStoreObj@RRasConfigStore@@0PEAV1@EA; RRasConfigStore * RRasConfigStore::configStoreObj
0x180040ca6  test    rbx, rbx
0x180040ca9  jz      short loc_180040CC7
0x180040cab  mov     rcx, rbx; this
0x180040cae  call    ??1RRasConfigStore@@QEAA@XZ; RRasConfigStore::~RRasConfigStore(void)
0x180040cb3  mov     rcx, rbx
0x180040cb6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180040cbc  mov     cs:?configStoreObj@RRasConfigStore@@0PEAV1@EA, 0; RRasConfigStore * RRasConfigStore::configStoreObj
0x180040cc7  cmp     qword ptr cs:xmmword_180078C50+8, 0
0x180040ccf  jz      short loc_180040D0B
0x180040cd1  xor     eax, eax
0x180040cd3  lea     rdx, aSRrasConfigura; "%s: Rras Configuration Store cleanup Do"...
0x180040cda  mov     r8, rsi
0x180040cdd  mov     word ptr [rsp+870h+var_810], ax
0x180040ce2  lea     rcx, [rsp+870h+var_810]
0x180040ce7  call    FormatRRASErrorString
0x180040cec  mov     rdx, qword ptr cs:xmmword_180078C50+8
0x180040cf3  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180040cfa  lea     r8, [rsp+870h+var_810]
0x180040cff  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180040d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d0b  mov     ebx, [rsp+870h+var_850]
0x180040d0f  lea     rcx, [rsp+870h+var_848]; this
0x180040d14  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180040d19  mov     eax, ebx
0x180040d1b  mov     rcx, [rbp+770h+var_10]
0x180040d22  xor     rcx, rsp; StackCookie
0x180040d25  call    __security_check_cookie
0x180040d2a  lea     r11, [rsp+870h+var_s0]
0x180040d32  mov     rbx, [r11+10h]
0x180040d36  mov     rsi, [r11+18h]
0x180040d3a  mov     rsp, r11
0x180040d3d  pop     rbp
0x180040d3e  retn
```
