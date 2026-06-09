# RRasConfigStore::ReleaseRoutingDomainHandle(void *)

- ea: `0x1800410bc`
- end: `0x180041208`
- name: `?ReleaseRoutingDomainHandle@RRasConfigStore@@QEAAKPEAX@Z`
- size: `332`
- prototype: `unsigned int __fastcall(RRasConfigStore *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180037690`

## callees

- `0x1800410bc`
- `0x18004583c`
- `0x180045ad4`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800411c4`
- `ntdll!RtlReleaseResource` at `0x1800411ce`
- `ntdll!RtlReleaseResource` at `0x1800411c4`
- `ntdll!RtlReleaseResource` at `0x1800411ce`

## string_xrefs

- `0x180041150`: `RRasConfigStore::ReleaseRoutingDomainHandle`
- `0x180041184`: `RRasConfigStore::ReleaseRoutingDomainHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  if ( *((_QWORD *)&xmmword_180071090 + 1) )
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
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v14) = 0;
      FormatRRASErrorString(
        &v14,
        L"%hs(Line#%d): Invalid parameter.",
        "RRasConfigStore::ReleaseRoutingDomainHandle",
        910);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
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
0x1800410bc  mov     [rsp-8+arg_10], rbx
0x1800410c1  mov     [rsp-8+arg_18], rdi
0x1800410c6  push    rbp
0x1800410c7  lea     rbp, [rsp-770h]
0x1800410cf  sub     rsp, 870h
0x1800410d6  mov     rax, cs:__security_cookie
0x1800410dd  xor     rax, rsp
0x1800410e0  mov     [rbp+770h+var_10], rax
0x1800410e7  mov     rbx, rdx
0x1800410ea  mov     rdi, rcx
0x1800410ed  mov     [rsp+870h+var_850], 0
0x1800410f5  xor     eax, eax
0x1800410f7  mov     [rsp+870h+var_810], eax
0x1800410fb  xor     edx, edx; Val
0x1800410fd  mov     r8d, 7FCh; Size
0x180041103  lea     rcx, [rsp+870h+var_80C]; void *
0x180041108  call    memset_0
0x18004110d  xorps   xmm0, xmm0
0x180041110  movdqu  [rsp+870h+var_840], xmm0
0x180041116  mov     [rsp+870h+var_848], 0
0x18004111f  xorps   xmm1, xmm1
0x180041122  movdqu  [rsp+870h+var_830], xmm1
0x180041128  mov     [rsp+870h+var_820], 0
0x180041131  mov     [rsp+870h+var_818], 0FFFFFFFFh
0x180041139  mov     [rsp+870h+var_814], 0
0x180041141  cmp     qword ptr cs:xmmword_180071090+8, 0
0x180041149  jz      short loc_180041161
0x18004114b  lea     r8, [rsp+870h+var_850]; unsigned int *
0x180041150  lea     rdx, aRrasconfigstor_25; "RRasConfigStore::ReleaseRoutingDomainHa"...
0x180041157  lea     rcx, [rsp+870h+var_848]; this
0x18004115c  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180041161  test    rbx, rbx
0x180041164  jnz     short loc_1800411BD
0x180041166  mov     [rsp+870h+var_850], 57h ; 'W'
0x18004116e  cmp     qword ptr cs:xmmword_180071090, rbx
0x180041175  jz      short loc_1800411D4
0x180041177  xor     eax, eax
0x180041179  mov     word ptr [rsp+870h+var_810], ax
0x18004117e  mov     r9d, 38Eh
0x180041184  lea     r8, aRrasconfigstor_20; "RRasConfigStore::ReleaseRoutingDomainHa"...
0x18004118b  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x180041192  lea     rcx, [rsp+870h+var_810]
0x180041197  call    FormatRRASErrorString
0x18004119c  lea     r8, [rsp+870h+var_810]
0x1800411a1  mov     rdx, qword ptr cs:xmmword_180071090
0x1800411a8  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x1800411af  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800411b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411bb  jmp     short loc_1800411D4
0x1800411bd  lea     rcx, [rbx+2D8h]; Resource
0x1800411c4  call    cs:__imp_RtlReleaseResource
0x1800411ca  lea     rcx, [rdi+70h]; Resource
0x1800411ce  call    cs:__imp_RtlReleaseResource
0x1800411d4  mov     ebx, [rsp+870h+var_850]
0x1800411d8  lea     rcx, [rsp+870h+var_848]; this
0x1800411dd  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800411e2  mov     eax, ebx
0x1800411e4  mov     rcx, [rbp+770h+var_10]
0x1800411eb  xor     rcx, rsp; StackCookie
0x1800411ee  call    __security_check_cookie
0x1800411f3  lea     r11, [rsp+870h+var_s0]
0x1800411fb  mov     rbx, [r11+20h]
0x1800411ff  mov     rdi, [r11+28h]
0x180041203  mov     rsp, r11
0x180041206  pop     rbp
0x180041207  retn
```
