# COleScript::GetDebugApplicationCoreNoRef(IDebugApplication64 * *)

- ea: `0x180032410`
- end: `0x1800325c9`
- name: `?GetDebugApplicationCoreNoRef@COleScript@@IEAAJPEAPEAUIDebugApplication64@@@Z`
- size: `441`
- prototype: `__int64 __fastcall(COleScript *__hidden this, struct IDebugApplication64 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800323cc`
- `0x18004f274`

## callees

- `0x180032410`
- `0x180049828`
- `0x180051618`
- `0x180079ffc`
- `0x18007c704`
- `0x180095084`
- `0x180098010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18003255e`
- `ole32!CoCreateInstance` at `0x18003255e`

## pseudocode

```c
__int64 __fastcall COleScript::GetDebugApplicationCoreNoRef(COleScript *this, struct IDebugApplication64 **a2)
{
  struct IDebugApplication64 **v4; // rsi
  int v5; // edi
  bool v6; // sf
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  HRESULT LatestPDM; // eax
  struct IActiveScriptSiteDebug64 *ppv; // [rsp+70h] [rbp+18h] BYREF

  ppv = 0;
  if ( (int)COleScript::GetDebugSiteNoRef(this, &ppv) < 0 )
  {
    ppv = 0;
    if ( !(unsigned int)FUserWantsDebugger() )
    {
      v5 = -2147467259;
      goto LABEL_5;
    }
    if ( (unsigned int)IsHostIE() )
      LatestPDM = LoadLatestPDM(&CLSID_ProcessDebugManager, &IID_IProcessDebugManager64, (LPVOID *)&ppv);
    else
      LatestPDM = CoCreateInstance(&CLSID_ProcessDebugManager, 0, 0x17u, &IID_IProcessDebugManager64, (LPVOID *)&ppv);
    v5 = LatestPDM;
    if ( LatestPDM < 0 )
      goto LABEL_5;
    v4 = (struct IDebugApplication64 **)((char *)this + 792);
    v5 = ((__int64 (__fastcall *)(struct IActiveScriptSiteDebug64 *, char *))ppv->lpVtbl->GetApplication)(
           ppv,
           (char *)this + 792);
    ((void (__fastcall *)(struct IActiveScriptSiteDebug64 *))ppv->lpVtbl->Release)(ppv);
    v6 = v5 < 0;
  }
  else
  {
    v4 = (struct IDebugApplication64 **)((char *)this + 792);
    v5 = ((__int64 (__fastcall *)(struct IActiveScriptSiteDebug64 *, char *))ppv->lpVtbl->GetApplication)(
           ppv,
           (char *)this + 792);
    v6 = v5 < 0;
  }
  if ( !v6 )
  {
    v5 = COleScript::SetupNewDebugApplication(this);
    if ( v5 >= 0 )
    {
      *a2 = *v4;
      return 0;
    }
  }
LABEL_5:
  *((_DWORD *)this + 212) |= 1u;
  if ( *((_QWORD *)this + 99) )
  {
    v7 = *((_QWORD *)this + 100);
    if ( v7 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      *((_QWORD *)this + 100) = 0;
    }
    v8 = *((_QWORD *)this + 101);
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      *((_QWORD *)this + 101) = 0;
    }
    v9 = *((_QWORD *)this + 102);
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      *((_QWORD *)this + 102) = 0;
    }
    v10 = *((_QWORD *)this + 99);
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      *((_QWORD *)this + 99) = 0;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180032410  push    rbx
0x180032412  push    rsi
0x180032413  push    rdi
0x180032414  push    r14
0x180032416  sub     rsp, 38h
0x18003241a  mov     r14, rdx
0x18003241d  mov     [rsp+58h+arg_10], 0
0x180032426  lea     rdx, [rsp+58h+arg_10]; struct IActiveScriptSiteDebug64 **
0x18003242b  mov     rbx, rcx
0x18003242e  call    ?GetDebugSiteNoRef@COleScript@@QEAAJPEAPEAUIActiveScriptSiteDebug64@@@Z; COleScript::GetDebugSiteNoRef(IActiveScriptSiteDebug64 * *)
0x180032433  test    eax, eax
0x180032435  js      short loc_18003245B
0x180032437  mov     rcx, [rsp+58h+arg_10]
0x18003243c  lea     rsi, [rbx+318h]
0x180032443  mov     rdx, rsi
0x180032446  mov     rax, [rcx]
0x180032449  mov     rax, [rax+20h]
0x18003244d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032452  mov     edi, eax
0x180032454  test    eax, eax
0x180032456  jmp     loc_1800325A4
0x18003245b  mov     [rsp+58h+arg_10], 0
0x180032464  call    FUserWantsDebugger
0x180032469  test    eax, eax
0x18003246b  jnz     loc_180032524
0x180032471  mov     edi, 80004005h
0x180032476  or      dword ptr [rbx+350h], 1
0x18003247d  cmp     qword ptr [rbx+318h], 0
0x180032485  jz      loc_180032517
0x18003248b  mov     rcx, [rbx+320h]
0x180032492  test    rcx, rcx
0x180032495  jz      short loc_1800324AE
0x180032497  mov     rax, [rcx]
0x18003249a  mov     rax, [rax+10h]
0x18003249e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324a3  mov     qword ptr [rbx+320h], 0
0x1800324ae  mov     rcx, [rbx+328h]
0x1800324b5  test    rcx, rcx
0x1800324b8  jz      short loc_1800324D1
0x1800324ba  mov     rax, [rcx]
0x1800324bd  mov     rax, [rax+10h]
0x1800324c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324c6  mov     qword ptr [rbx+328h], 0
0x1800324d1  mov     rcx, [rbx+330h]
0x1800324d8  test    rcx, rcx
0x1800324db  jz      short loc_1800324F4
0x1800324dd  mov     rax, [rcx]
0x1800324e0  mov     rax, [rax+10h]
0x1800324e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324e9  mov     qword ptr [rbx+330h], 0
0x1800324f4  mov     rcx, [rbx+318h]
0x1800324fb  test    rcx, rcx
0x1800324fe  jz      short loc_180032517
0x180032500  mov     rax, [rcx]
0x180032503  mov     rax, [rax+10h]
0x180032507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003250c  mov     qword ptr [rbx+318h], 0
0x180032517  mov     eax, edi
0x180032519  add     rsp, 38h
0x18003251d  pop     r14
0x18003251f  pop     rdi
0x180032520  pop     rsi
0x180032521  pop     rbx
0x180032522  retn
0x180032524  call    ?IsHostIE@@YAHXZ; IsHostIE(void)
0x180032529  lea     rcx, CLSID_ProcessDebugManager; struct _GUID *
0x180032530  test    eax, eax
0x180032532  jz      short loc_180032547
0x180032534  lea     r8, [rsp+58h+arg_10]; ppv
0x180032539  lea     rdx, IID_IProcessDebugManager64; riid
0x180032540  call    ?LoadLatestPDM@@YAJAEBU_GUID@@0PEAPEAX@Z; LoadLatestPDM(_GUID const &,_GUID const &,void * *)
0x180032545  jmp     short loc_18003256A
0x180032547  xor     edx, edx; pUnkOuter
0x180032549  lea     rax, [rsp+58h+arg_10]
0x18003254e  lea     r9, IID_IProcessDebugManager64; riid
0x180032555  mov     [rsp+58h+ppv], rax; ppv
0x18003255a  lea     r8d, [rdx+17h]; dwClsContext
0x18003255e  call    cs:__imp_CoCreateInstance
0x180032565  nop     dword ptr [rax+rax+00h]
0x18003256a  mov     edi, eax
0x18003256c  test    eax, eax
0x18003256e  js      loc_180032476
0x180032574  mov     rcx, [rsp+58h+arg_10]
0x180032579  lea     rsi, [rbx+318h]
0x180032580  mov     rdx, rsi
0x180032583  mov     rax, [rcx]
0x180032586  mov     rax, [rax+20h]
0x18003258a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003258f  mov     rcx, [rsp+58h+arg_10]
0x180032594  mov     edi, eax
0x180032596  mov     rax, [rcx]
0x180032599  mov     rax, [rax+10h]
0x18003259d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325a2  test    edi, edi
0x1800325a4  js      loc_180032476
0x1800325aa  mov     rcx, rbx; this
0x1800325ad  call    ?SetupNewDebugApplication@COleScript@@IEAAJXZ; COleScript::SetupNewDebugApplication(void)
0x1800325b2  mov     edi, eax
0x1800325b4  test    eax, eax
0x1800325b6  js      loc_180032476
0x1800325bc  mov     rax, [rsi]
0x1800325bf  mov     [r14], rax
0x1800325c2  xor     eax, eax
0x1800325c4  jmp     loc_180032519
```
