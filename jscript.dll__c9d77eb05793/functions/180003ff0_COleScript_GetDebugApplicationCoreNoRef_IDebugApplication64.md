# COleScript::GetDebugApplicationCoreNoRef(IDebugApplication64 * *)

- ea: `0x180003ff0`
- end: `0x1800041a2`
- name: `?GetDebugApplicationCoreNoRef@COleScript@@IEAAJPEAPEAUIDebugApplication64@@@Z`
- size: `434`
- prototype: `__int64 __fastcall(COleScript *__hidden this, struct IDebugApplication64 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180003fac`
- `0x18004e630`

## callees

- `0x180003ff0`
- `0x180048764`
- `0x18005078c`
- `0x1800789cc`
- `0x18007af1c`
- `0x180092cf0`
- `0x180096010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000413d`
- `ole32!CoCreateInstance` at `0x18000413d`

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
0x180003ff0  push    rbx
0x180003ff2  push    rsi
0x180003ff3  push    rdi
0x180003ff4  push    r14
0x180003ff6  sub     rsp, 38h
0x180003ffa  mov     r14, rdx
0x180003ffd  mov     [rsp+58h+arg_10], 0
0x180004006  lea     rdx, [rsp+58h+arg_10]; struct IActiveScriptSiteDebug64 **
0x18000400b  mov     rbx, rcx
0x18000400e  call    ?GetDebugSiteNoRef@COleScript@@QEAAJPEAPEAUIActiveScriptSiteDebug64@@@Z; COleScript::GetDebugSiteNoRef(IActiveScriptSiteDebug64 * *)
0x180004013  test    eax, eax
0x180004015  js      short loc_18000403B
0x180004017  mov     rcx, [rsp+58h+arg_10]
0x18000401c  lea     rsi, [rbx+318h]
0x180004023  mov     rdx, rsi
0x180004026  mov     rax, [rcx]
0x180004029  mov     rax, [rax+20h]
0x18000402d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004032  mov     edi, eax
0x180004034  test    eax, eax
0x180004036  jmp     loc_18000417D
0x18000403b  mov     [rsp+58h+arg_10], 0
0x180004044  call    FUserWantsDebugger
0x180004049  test    eax, eax
0x18000404b  jnz     loc_180004103
0x180004051  mov     edi, 80004005h
0x180004056  or      dword ptr [rbx+350h], 1
0x18000405d  cmp     qword ptr [rbx+318h], 0
0x180004065  jz      loc_1800040F7
0x18000406b  mov     rcx, [rbx+320h]
0x180004072  test    rcx, rcx
0x180004075  jz      short loc_18000408E
0x180004077  mov     rax, [rcx]
0x18000407a  mov     rax, [rax+10h]
0x18000407e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004083  mov     qword ptr [rbx+320h], 0
0x18000408e  mov     rcx, [rbx+328h]
0x180004095  test    rcx, rcx
0x180004098  jz      short loc_1800040B1
0x18000409a  mov     rax, [rcx]
0x18000409d  mov     rax, [rax+10h]
0x1800040a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040a6  mov     qword ptr [rbx+328h], 0
0x1800040b1  mov     rcx, [rbx+330h]
0x1800040b8  test    rcx, rcx
0x1800040bb  jz      short loc_1800040D4
0x1800040bd  mov     rax, [rcx]
0x1800040c0  mov     rax, [rax+10h]
0x1800040c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040c9  mov     qword ptr [rbx+330h], 0
0x1800040d4  mov     rcx, [rbx+318h]
0x1800040db  test    rcx, rcx
0x1800040de  jz      short loc_1800040F7
0x1800040e0  mov     rax, [rcx]
0x1800040e3  mov     rax, [rax+10h]
0x1800040e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040ec  mov     qword ptr [rbx+318h], 0
0x1800040f7  mov     eax, edi
0x1800040f9  add     rsp, 38h
0x1800040fd  pop     r14
0x1800040ff  pop     rdi
0x180004100  pop     rsi
0x180004101  pop     rbx
0x180004102  retn
0x180004103  call    ?IsHostIE@@YAHXZ; IsHostIE(void)
0x180004108  lea     rcx, CLSID_ProcessDebugManager; struct _GUID *
0x18000410f  test    eax, eax
0x180004111  jz      short loc_180004126
0x180004113  lea     r8, [rsp+58h+arg_10]; ppv
0x180004118  lea     rdx, IID_IProcessDebugManager64; riid
0x18000411f  call    ?LoadLatestPDM@@YAJAEBU_GUID@@0PEAPEAX@Z; LoadLatestPDM(_GUID const &,_GUID const &,void * *)
0x180004124  jmp     short loc_180004143
0x180004126  xor     edx, edx; pUnkOuter
0x180004128  lea     rax, [rsp+58h+arg_10]
0x18000412d  lea     r9, IID_IProcessDebugManager64; riid
0x180004134  mov     [rsp+58h+ppv], rax; ppv
0x180004139  lea     r8d, [rdx+17h]; dwClsContext
0x18000413d  call    cs:__imp_CoCreateInstance
0x180004143  mov     edi, eax
0x180004145  test    eax, eax
0x180004147  js      loc_180004056
0x18000414d  mov     rcx, [rsp+58h+arg_10]
0x180004152  lea     rsi, [rbx+318h]
0x180004159  mov     rdx, rsi
0x18000415c  mov     rax, [rcx]
0x18000415f  mov     rax, [rax+20h]
0x180004163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004168  mov     rcx, [rsp+58h+arg_10]
0x18000416d  mov     edi, eax
0x18000416f  mov     rax, [rcx]
0x180004172  mov     rax, [rax+10h]
0x180004176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000417b  test    edi, edi
0x18000417d  js      loc_180004056
0x180004183  mov     rcx, rbx; this
0x180004186  call    ?SetupNewDebugApplication@COleScript@@IEAAJXZ; COleScript::SetupNewDebugApplication(void)
0x18000418b  mov     edi, eax
0x18000418d  test    eax, eax
0x18000418f  js      loc_180004056
0x180004195  mov     rax, [rsi]
0x180004198  mov     [r14], rax
0x18000419b  xor     eax, eax
0x18000419d  jmp     loc_1800040F9
```
