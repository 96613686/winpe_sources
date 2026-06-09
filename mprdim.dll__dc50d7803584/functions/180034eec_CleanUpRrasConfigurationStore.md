# CleanUpRrasConfigurationStore

- ea: `0x180034eec`
- end: `0x18003510f`
- name: `CleanUpRrasConfigurationStore`
- size: `547`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x1800115c8`

## callees

- `0x180034eec`
- `0x180038a78`
- `0x180038dc0`
- `0x18003d380`
- `0x18004583c`
- `0x180045ad4`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180035086`
- `msvcrt!??3@YAXPEAX@Z` at `0x180035086`

## string_xrefs

- `0x180034f3f`: `CleanUpRrasConfigurationStore`
- `0x180034f9a`: `%s: Cleaning up Rras Configuration Store...`
- `0x180034fed`: `%s: The config store instance could not be found.`
- `0x18003504d`: `%s: cfgStore->CleanupConfigStore failed: %d.`
- `0x1800350a3`: `%s: Rras Configuration Store cleanup Done.`

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
  if ( *((_QWORD *)&xmmword_180071090 + 1) )
  {
    EtwFuncEntryExitTracer::Initialize((EtwFuncEntryExitTracer *)&v8, L"CleanUpRrasConfigurationStore", &v7, v0);
    if ( *((_QWORD *)&xmmword_180071090 + 1) )
    {
      LOWORD(v14) = 0;
      FormatRRASErrorString(&v14, L"%s: Cleaning up Rras Configuration Store...", L"CleanUpRrasConfigurationStore");
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        *((_QWORD *)&xmmword_180071090 + 1),
        &v14);
    }
  }
  Instance = RRasConfigStore::GetInstance();
  if ( !Instance )
  {
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v14) = 0;
      FormatRRASErrorString(
        &v14,
        L"%s: The config store instance could not be found.",
        L"CleanUpRrasConfigurationStore");
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v14);
    }
    v7 = 1003;
    goto LABEL_16;
  }
  v7 = RRasConfigStore::CleanupConfigStore(Instance);
  v2 = v7;
  if ( v7 )
  {
    if ( !(_QWORD)xmmword_180071090 )
      goto LABEL_16;
    LOWORD(v14) = 0;
    FormatRRASErrorString(&v14, L"%s: cfgStore->CleanupConfigStore failed: %d.", L"CleanUpRrasConfigurationStore", v7);
    v3 = xmmword_180071090;
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
  if ( *((_QWORD *)&xmmword_180071090 + 1) )
  {
    LOWORD(v14) = 0;
    FormatRRASErrorString(&v14, L"%s: Rras Configuration Store cleanup Done.", L"CleanUpRrasConfigurationStore", v2);
    v3 = *((_QWORD *)&xmmword_180071090 + 1);
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
0x180034eec  mov     [rsp-8+arg_0], rbx
0x180034ef1  mov     [rsp-8+arg_8], rsi
0x180034ef6  push    rbp
0x180034ef7  lea     rbp, [rsp-770h]
0x180034eff  sub     rsp, 870h
0x180034f06  mov     rax, cs:__security_cookie
0x180034f0d  xor     rax, rsp
0x180034f10  mov     [rbp+770h+var_10], rax
0x180034f17  xor     eax, eax
0x180034f19  mov     [rsp+870h+var_850], 0
0x180034f21  xor     edx, edx; Val
0x180034f23  mov     [rsp+870h+var_810], eax
0x180034f27  mov     r8d, 7FCh; Size
0x180034f2d  lea     rcx, [rsp+870h+var_80C]; void *
0x180034f32  call    memset_0
0x180034f37  cmp     qword ptr cs:xmmword_180071090+8, 0
0x180034f3f  lea     rsi, aCleanuprrascon; "CleanUpRrasConfigurationStore"
0x180034f46  xorps   xmm0, xmm0
0x180034f49  mov     [rsp+870h+var_848], 0
0x180034f52  xorps   xmm1, xmm1
0x180034f55  mov     [rsp+870h+var_820], 0
0x180034f5e  movdqu  [rsp+870h+var_840], xmm0
0x180034f64  mov     [rsp+870h+var_818], 0FFFFFFFFh
0x180034f6c  movdqu  [rsp+870h+var_830], xmm1
0x180034f72  mov     [rsp+870h+var_814], 0
0x180034f7a  jz      short loc_180034FD2
0x180034f7c  lea     r8, [rsp+870h+var_850]; unsigned int *
0x180034f81  mov     rdx, rsi; unsigned __int16 *
0x180034f84  lea     rcx, [rsp+870h+var_848]; this
0x180034f89  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180034f8e  cmp     qword ptr cs:xmmword_180071090+8, 0
0x180034f96  jz      short loc_180034FD2
0x180034f98  xor     eax, eax
0x180034f9a  lea     rdx, aSCleaningUpRra; "%s: Cleaning up Rras Configuration Stor"...
0x180034fa1  mov     r8, rsi
0x180034fa4  mov     word ptr [rsp+870h+var_810], ax
0x180034fa9  lea     rcx, [rsp+870h+var_810]
0x180034fae  call    FormatRRASErrorString
0x180034fb3  mov     rdx, qword ptr cs:xmmword_180071090+8
0x180034fba  lea     r8, [rsp+870h+var_810]
0x180034fbf  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180034fc6  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180034fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034fd2  call    ?GetInstance@RRasConfigStore@@SAPEAV1@XZ; RRasConfigStore::GetInstance(void)
0x180034fd7  test    rax, rax
0x180034fda  jnz     short loc_18003502A
0x180034fdc  cmp     qword ptr cs:xmmword_180071090, rax
0x180034fe3  jz      short loc_18003501D
0x180034fe5  mov     r8, rsi
0x180034fe8  mov     word ptr [rsp+870h+var_810], ax
0x180034fed  lea     rdx, aSTheConfigStor; "%s: The config store instance could not"...
0x180034ff4  lea     rcx, [rsp+870h+var_810]
0x180034ff9  call    FormatRRASErrorString
0x180034ffe  mov     rdx, qword ptr cs:xmmword_180071090
0x180035005  lea     r8, [rsp+870h+var_810]
0x18003500a  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180035011  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180035018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003501d  mov     [rsp+870h+var_850], 3EBh
0x180035025  jmp     loc_1800350DB
0x18003502a  mov     rcx, rax; this
0x18003502d  call    ?CleanupConfigStore@RRasConfigStore@@QEAAKXZ; RRasConfigStore::CleanupConfigStore(void)
0x180035032  mov     [rsp+870h+var_850], eax
0x180035036  mov     r9d, eax
0x180035039  test    eax, eax
0x18003503b  jz      short loc_18003506F
0x18003503d  cmp     qword ptr cs:xmmword_180071090, 0
0x180035045  jz      loc_1800350DB
0x18003504b  xor     eax, eax
0x18003504d  lea     rdx, aSCfgstoreClean; "%s: cfgStore->CleanupConfigStore failed"...
0x180035054  mov     r8, rsi
0x180035057  mov     word ptr [rsp+870h+var_810], ax
0x18003505c  lea     rcx, [rsp+870h+var_810]
0x180035061  call    FormatRRASErrorString
0x180035066  mov     rdx, qword ptr cs:xmmword_180071090
0x18003506d  jmp     short loc_1800350C3
0x18003506f  mov     rbx, cs:?configStoreObj@RRasConfigStore@@0PEAV1@EA; RRasConfigStore * RRasConfigStore::configStoreObj
0x180035076  test    rbx, rbx
0x180035079  jz      short loc_180035097
0x18003507b  mov     rcx, rbx; this
0x18003507e  call    ??1RRasConfigStore@@QEAA@XZ; RRasConfigStore::~RRasConfigStore(void)
0x180035083  mov     rcx, rbx
0x180035086  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003508c  mov     cs:?configStoreObj@RRasConfigStore@@0PEAV1@EA, 0; RRasConfigStore * RRasConfigStore::configStoreObj
0x180035097  cmp     qword ptr cs:xmmword_180071090+8, 0
0x18003509f  jz      short loc_1800350DB
0x1800350a1  xor     eax, eax
0x1800350a3  lea     rdx, aSRrasConfigura; "%s: Rras Configuration Store cleanup Do"...
0x1800350aa  mov     r8, rsi
0x1800350ad  mov     word ptr [rsp+870h+var_810], ax
0x1800350b2  lea     rcx, [rsp+870h+var_810]
0x1800350b7  call    FormatRRASErrorString
0x1800350bc  mov     rdx, qword ptr cs:xmmword_180071090+8
0x1800350c3  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x1800350ca  lea     r8, [rsp+870h+var_810]
0x1800350cf  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800350d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800350db  mov     ebx, [rsp+870h+var_850]
0x1800350df  lea     rcx, [rsp+870h+var_848]; this
0x1800350e4  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800350e9  mov     eax, ebx
0x1800350eb  mov     rcx, [rbp+770h+var_10]
0x1800350f2  xor     rcx, rsp; StackCookie
0x1800350f5  call    __security_check_cookie
0x1800350fa  lea     r11, [rsp+870h+var_s0]
0x180035102  mov     rbx, [r11+10h]
0x180035106  mov     rsi, [r11+18h]
0x18003510a  mov     rsp, r11
0x18003510d  pop     rbp
0x18003510e  retn
```
