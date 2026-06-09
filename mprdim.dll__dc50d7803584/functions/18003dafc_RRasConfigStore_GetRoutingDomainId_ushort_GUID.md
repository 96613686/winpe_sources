# RRasConfigStore::GetRoutingDomainId(ushort *,_GUID *)

- ea: `0x18003dafc`
- end: `0x18003dd36`
- name: `?GetRoutingDomainId@RRasConfigStore@@QEAAKPEAGPEAU_GUID@@@Z`
- size: `570`
- prototype: `unsigned int(RRasConfigStore *__hidden this, unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180035f20`

## callees

- `0x18003d8c4`
- `0x18003dafc`
- `0x18004583c`
- `0x180045ad4`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003dbdf`
- `msvcrt!_wcsicmp` at `0x18003dbdf`
- `ntdll!RtlReleaseResource` at `0x18003dca7`
- `ntdll!RtlReleaseResource` at `0x18003dca7`
- `ntdll!RtlAcquireResourceShared` at `0x18003dbc2`
- `ntdll!RtlAcquireResourceShared` at `0x18003dbc2`

## string_xrefs

- `0x18003db93`: `RRasConfigStore::GetRoutingDomainId`
- `0x18003dc0e`: `RRasConfigStore::GetRoutingDomainId`
- `0x18003dc6c`: `RRasConfigStore::GetRoutingDomainId`
- `0x18003dcce`: `RRasConfigStore::GetRoutingDomainId`
- `0x18003dc15`: `%s: No Routing Domain object with name '%ws' is configured for RRAS. Trying to get it from Network stack`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RRasConfigStore::GetRoutingDomainId(RRasConfigStore *this, unsigned __int16 *a2, struct _GUID *a3)
{
  void (*v6)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  RRasConfigStore *v7; // rcx
  _QWORD *v8; // rbx
  __int64 v9; // r14
  unsigned int v10; // ebx
  unsigned int RoutingDomainIDFromStack; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v13; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v14; // [rsp+30h] [rbp-D0h]
  __int128 v15; // [rsp+40h] [rbp-C0h]
  __int64 v16; // [rsp+50h] [rbp-B0h]
  int v17; // [rsp+58h] [rbp-A8h]
  int v18; // [rsp+5Ch] [rbp-A4h]
  int v19; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  RoutingDomainIDFromStack = 0;
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  v14 = 0;
  v13 = 0;
  v15 = 0;
  v16 = 0;
  v17 = -1;
  v18 = 0;
  if ( *((_QWORD *)&xmmword_180071090 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v13,
      L"RRasConfigStore::GetRoutingDomainId",
      &RoutingDomainIDFromStack,
      v6);
  if ( a3 && a2 )
  {
    *a3 = 0;
    RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 112), 1u);
    v8 = (_QWORD *)*((_QWORD *)this + 3);
    while ( 1 )
    {
      v8 = (_QWORD *)*v8;
      if ( v8 == *((_QWORD **)this + 3) )
        break;
      v9 = v8[4];
      if ( !_wcsicmp((const wchar_t *)v9, a2) )
      {
        *a3 = *(struct _GUID *)(v9 + 516);
        goto LABEL_14;
      }
    }
    if ( *((_QWORD *)&xmmword_180071090 + 1) )
    {
      LOWORD(v19) = 0;
      FormatRRASErrorString(
        &v19,
        L"%s: No Routing Domain object with name '%ws' is configured for RRAS. Trying to get it from Network stack",
        L"RRasConfigStore::GetRoutingDomainId",
        a2);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        *((_QWORD *)&xmmword_180071090 + 1),
        &v19);
    }
    RoutingDomainIDFromStack = RRasConfigStore::GetRoutingDomainIDFromStack(v7, a2, a3);
    if ( RoutingDomainIDFromStack && (_QWORD)xmmword_180071090 )
    {
      LOWORD(v19) = 0;
      FormatRRASErrorString(
        &v19,
        L"%s: No Routing Domain object found with name '%ws'",
        L"RRasConfigStore::GetRoutingDomainId",
        a2);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v19);
    }
LABEL_14:
    RtlReleaseResource((PRTL_RESOURCE)((char *)this + 112));
  }
  else
  {
    RoutingDomainIDFromStack = 87;
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v19) = 0;
      FormatRRASErrorString(&v19, L"%hs(Line#%d): Invalid parameter.", "RRasConfigStore::GetRoutingDomainId", 787);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v19);
    }
  }
  v10 = RoutingDomainIDFromStack;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v13);
  return v10;
}

```

## disassembly

```asm
0x18003dafc  push    rbp
0x18003dafe  push    rbx
0x18003daff  push    rsi
0x18003db00  push    rdi
0x18003db01  push    r12
0x18003db03  push    r14
0x18003db05  push    r15
0x18003db07  lea     rbp, [rsp-770h]
0x18003db0f  sub     rsp, 870h
0x18003db16  mov     rax, cs:__security_cookie
0x18003db1d  xor     rax, rsp
0x18003db20  mov     [rbp+7A0h+var_40], rax
0x18003db27  mov     rsi, r8
0x18003db2a  mov     rdi, rdx
0x18003db2d  mov     r15, rcx
0x18003db30  mov     [rsp+8A0h+var_880], 0
0x18003db38  xor     eax, eax
0x18003db3a  mov     [rsp+8A0h+var_840], eax
0x18003db3e  xor     edx, edx; Val
0x18003db40  mov     r8d, 7FCh; Size
0x18003db46  lea     rcx, [rsp+8A0h+var_83C]; void *
0x18003db4b  call    memset_0
0x18003db50  xorps   xmm0, xmm0
0x18003db53  movdqu  [rsp+8A0h+var_870], xmm0
0x18003db59  mov     [rsp+8A0h+var_878], 0
0x18003db62  xorps   xmm1, xmm1
0x18003db65  movdqu  [rsp+8A0h+var_860], xmm1
0x18003db6b  mov     [rsp+8A0h+var_850], 0
0x18003db74  mov     [rsp+8A0h+var_848], 0FFFFFFFFh
0x18003db7c  mov     [rsp+8A0h+var_844], 0
0x18003db84  cmp     qword ptr cs:xmmword_180071090+8, 0
0x18003db8c  jz      short loc_18003DBA4
0x18003db8e  lea     r8, [rsp+8A0h+var_880]; unsigned int *
0x18003db93  lea     rdx, aRrasconfigstor_32; "RRasConfigStore::GetRoutingDomainId"
0x18003db9a  lea     rcx, [rsp+8A0h+var_878]; this
0x18003db9f  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18003dba4  test    rsi, rsi
0x18003dba7  jz      loc_18003DCAF
0x18003dbad  test    rdi, rdi
0x18003dbb0  jz      loc_18003DCAF
0x18003dbb6  xorps   xmm0, xmm0
0x18003dbb9  movups  xmmword ptr [rsi], xmm0
0x18003dbbc  mov     dl, 1; Wait
0x18003dbbe  lea     rcx, [r15+70h]; Resource
0x18003dbc2  call    cs:__imp_RtlAcquireResourceShared
0x18003dbc8  mov     rbx, [r15+18h]
0x18003dbcc  mov     rbx, [rbx]
0x18003dbcf  cmp     rbx, [r15+18h]
0x18003dbd3  jz      short loc_18003DBFA
0x18003dbd5  mov     r14, [rbx+20h]
0x18003dbd9  mov     rdx, rdi; String2
0x18003dbdc  mov     rcx, r14; String1
0x18003dbdf  call    cs:__imp__wcsicmp
0x18003dbe5  test    eax, eax
0x18003dbe7  jnz     short loc_18003DBCC
0x18003dbe9  movups  xmm0, xmmword ptr [r14+204h]
0x18003dbf1  movdqu  xmmword ptr [rsi], xmm0
0x18003dbf5  jmp     loc_18003DCA3
0x18003dbfa  cmp     qword ptr cs:xmmword_180071090+8, 0
0x18003dc02  jz      short loc_18003DC45
0x18003dc04  xor     eax, eax
0x18003dc06  mov     word ptr [rsp+8A0h+var_840], ax
0x18003dc0b  mov     r9, rdi
0x18003dc0e  lea     r8, aRrasconfigstor_32; "RRasConfigStore::GetRoutingDomainId"
0x18003dc15  lea     rdx, aSNoRoutingDoma; "%s: No Routing Domain object with name "...
0x18003dc1c  lea     rcx, [rsp+8A0h+var_840]
0x18003dc21  call    FormatRRASErrorString
0x18003dc26  lea     r8, [rsp+8A0h+var_840]
0x18003dc2b  mov     rdx, qword ptr cs:xmmword_180071090+8
0x18003dc32  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003dc39  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003dc40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc45  mov     r8, rsi; struct _GUID *
0x18003dc48  mov     rdx, rdi; unsigned __int16 *
0x18003dc4b  call    ?GetRoutingDomainIDFromStack@RRasConfigStore@@AEAAKPEAGPEAU_GUID@@@Z; RRasConfigStore::GetRoutingDomainIDFromStack(ushort *,_GUID *)
0x18003dc50  mov     [rsp+8A0h+var_880], eax
0x18003dc54  test    eax, eax
0x18003dc56  jz      short loc_18003DCA3
0x18003dc58  cmp     qword ptr cs:xmmword_180071090, 0
0x18003dc60  jz      short loc_18003DCA3
0x18003dc62  xor     eax, eax
0x18003dc64  mov     word ptr [rsp+8A0h+var_840], ax
0x18003dc69  mov     r9, rdi
0x18003dc6c  lea     r8, aRrasconfigstor_32; "RRasConfigStore::GetRoutingDomainId"
0x18003dc73  lea     rdx, aSNoRoutingDoma_0; "%s: No Routing Domain object found with"...
0x18003dc7a  lea     rcx, [rsp+8A0h+var_840]
0x18003dc7f  call    FormatRRASErrorString
0x18003dc84  lea     r8, [rsp+8A0h+var_840]
0x18003dc89  mov     rdx, qword ptr cs:xmmword_180071090
0x18003dc90  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003dc97  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003dc9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dca3  lea     rcx, [r15+70h]; Resource
0x18003dca7  call    cs:__imp_RtlReleaseResource
0x18003dcad  jmp     short loc_18003DD05
0x18003dcaf  mov     [rsp+8A0h+var_880], 57h ; 'W'
0x18003dcb7  cmp     qword ptr cs:xmmword_180071090, 0
0x18003dcbf  jz      short loc_18003DD05
0x18003dcc1  xor     eax, eax
0x18003dcc3  mov     word ptr [rsp+8A0h+var_840], ax
0x18003dcc8  mov     r9d, 313h
0x18003dcce  lea     r8, aRrasconfigstor_14; "RRasConfigStore::GetRoutingDomainId"
0x18003dcd5  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18003dcdc  lea     rcx, [rsp+8A0h+var_840]
0x18003dce1  call    FormatRRASErrorString
0x18003dce6  lea     r8, [rsp+8A0h+var_840]
0x18003dceb  mov     rdx, qword ptr cs:xmmword_180071090
0x18003dcf2  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003dcf9  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003dd00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd05  mov     ebx, [rsp+8A0h+var_880]
0x18003dd09  lea     rcx, [rsp+8A0h+var_878]; this
0x18003dd0e  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003dd13  mov     eax, ebx
0x18003dd15  mov     rcx, [rbp+7A0h+var_40]
0x18003dd1c  xor     rcx, rsp; StackCookie
0x18003dd1f  call    __security_check_cookie
0x18003dd24  add     rsp, 870h
0x18003dd2b  pop     r15
0x18003dd2d  pop     r14
0x18003dd2f  pop     r12
0x18003dd31  pop     rdi
0x18003dd32  pop     rsi
0x18003dd33  pop     rbx
0x18003dd34  pop     rbp
0x18003dd35  retn
```
