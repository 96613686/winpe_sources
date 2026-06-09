# RRasConfigStore::ReleaseRoutingDomainHandle(void *)

- ea: `0x18004c2f4`
- end: `0x18004c440`
- name: `?ReleaseRoutingDomainHandle@RRasConfigStore@@QEAAKPEAX@Z`
- size: `332`
- prototype: `__int64 __fastcall(RRasConfigStore *this, char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180042d40`

## callees

- `0x18004c2f4`
- `0x180050b2c`
- `0x180050cd4`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18004c3fc`
- `ntdll!RtlReleaseResource` at `0x18004c406`
- `ntdll!RtlReleaseResource` at `0x18004c3fc`
- `ntdll!RtlReleaseResource` at `0x18004c406`

## string_xrefs

- `0x18004c388`: `RRasConfigStore::ReleaseRoutingDomainHandle`
- `0x18004c3bc`: `RRasConfigStore::ReleaseRoutingDomainHandle`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::ReleaseRoutingDomainHandle(RRasConfigStore *this, char *a2)
{
  void (*v4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
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
  v9 = 0;
  v8 = 0;
  v10 = 0;
  v11 = 0;
  v12 = -1;
  v13 = 0;
  if ( *((_QWORD *)&xmmword_180078C50 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v8,
      L"RRasConfigStore::ReleaseRoutingDomainHandle",
      &v7,
      v4);
  if ( a2 )
  {
    RtlReleaseResource((PRTL_RESOURCE)(a2 + 728));
    RtlReleaseResource((PRTL_RESOURCE)((char *)this + 112));
  }
  else
  {
    v7 = 87;
    if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v14) = 0;
      FormatRRASErrorString(
        &v14,
        L"%hs(Line#%d): Invalid parameter.",
        "RRasConfigStore::ReleaseRoutingDomainHandle",
        910);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
        &v14);
    }
  }
  v5 = v7;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v8);
  return v5;
}

```

## disassembly

```asm
0x18004c2f4  mov     [rsp-8+arg_10], rbx
0x18004c2f9  mov     [rsp-8+arg_18], rdi
0x18004c2fe  push    rbp
0x18004c2ff  lea     rbp, [rsp-770h]
0x18004c307  sub     rsp, 870h
0x18004c30e  mov     rax, cs:__security_cookie
0x18004c315  xor     rax, rsp
0x18004c318  mov     [rbp+770h+var_10], rax
0x18004c31f  mov     rbx, rdx
0x18004c322  mov     rdi, rcx
0x18004c325  mov     [rsp+870h+var_850], 0
0x18004c32d  xor     eax, eax
0x18004c32f  mov     [rsp+870h+var_810], eax
0x18004c333  xor     edx, edx; Val
0x18004c335  mov     r8d, 7FCh; Size
0x18004c33b  lea     rcx, [rsp+870h+var_80C]; void *
0x18004c340  call    memset_0
0x18004c345  xorps   xmm0, xmm0
0x18004c348  movdqu  [rsp+870h+var_840], xmm0
0x18004c34e  mov     [rsp+870h+var_848], 0
0x18004c357  xorps   xmm1, xmm1
0x18004c35a  movdqu  [rsp+870h+var_830], xmm1
0x18004c360  mov     [rsp+870h+var_820], 0
0x18004c369  mov     [rsp+870h+var_818], 0FFFFFFFFh
0x18004c371  mov     [rsp+870h+var_814], 0
0x18004c379  cmp     qword ptr cs:xmmword_180078C50+8, 0
0x18004c381  jz      short loc_18004C399
0x18004c383  lea     r8, [rsp+870h+var_850]; unsigned int *
0x18004c388  lea     rdx, aRrasconfigstor_20; "RRasConfigStore::ReleaseRoutingDomainHa"...
0x18004c38f  lea     rcx, [rsp+870h+var_848]; this
0x18004c394  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18004c399  test    rbx, rbx
0x18004c39c  jnz     short loc_18004C3F5
0x18004c39e  mov     [rsp+870h+var_850], 57h ; 'W'
0x18004c3a6  cmp     qword ptr cs:xmmword_180078C50, rbx
0x18004c3ad  jz      short loc_18004C40C
0x18004c3af  xor     eax, eax
0x18004c3b1  mov     word ptr [rsp+870h+var_810], ax
0x18004c3b6  mov     r9d, 38Eh
0x18004c3bc  lea     r8, aRrasconfigstor_16; "RRasConfigStore::ReleaseRoutingDomainHa"...
0x18004c3c3  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18004c3ca  lea     rcx, [rsp+870h+var_810]
0x18004c3cf  call    FormatRRASErrorString
0x18004c3d4  lea     r8, [rsp+870h+var_810]
0x18004c3d9  mov     rdx, qword ptr cs:xmmword_180078C50
0x18004c3e0  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004c3e7  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004c3ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c3f3  jmp     short loc_18004C40C
0x18004c3f5  lea     rcx, [rbx+2D8h]; Resource
0x18004c3fc  call    cs:__imp_RtlReleaseResource
0x18004c402  lea     rcx, [rdi+70h]; Resource
0x18004c406  call    cs:__imp_RtlReleaseResource
0x18004c40c  mov     ebx, [rsp+870h+var_850]
0x18004c410  lea     rcx, [rsp+870h+var_848]; this
0x18004c415  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18004c41a  mov     eax, ebx
0x18004c41c  mov     rcx, [rbp+770h+var_10]
0x18004c423  xor     rcx, rsp; StackCookie
0x18004c426  call    __security_check_cookie
0x18004c42b  lea     r11, [rsp+870h+var_s0]
0x18004c433  mov     rbx, [r11+20h]
0x18004c437  mov     rdi, [r11+28h]
0x18004c43b  mov     rsp, r11
0x18004c43e  pop     rbp
0x18004c43f  retn
```
