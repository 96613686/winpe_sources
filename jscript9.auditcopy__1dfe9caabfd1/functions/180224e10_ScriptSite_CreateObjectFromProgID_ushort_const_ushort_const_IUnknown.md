# ScriptSite::CreateObjectFromProgID(ushort const *,ushort const *,IUnknown * *)

- ea: `0x180224e10`
- end: `0x180225089`
- name: `?CreateObjectFromProgID@ScriptSite@@QEAAJPEBG0PEAPEAUIUnknown@@@Z`
- size: `633`
- prototype: `__int64 __fastcall(ScriptSite *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801b2964`
- `0x180225b14`

## callees

- `0x18021aecc`
- `0x18021b0c8`
- `0x180221514`
- `0x180224e10`
- `0x180227e2c`
- `0x180228010`
- `0x180257210`
- `0x1803481f0`
- `0x180364010`

## import_xrefs

- `api-ms-win-downlevel-ole32-l1-1-0!CoGetClassObject` at `0x180224f42`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetClassObject` at `0x180224f42`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromProgID` at `0x180224eb6`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromProgID` at `0x180224eb6`
- `ole32!CLSIDFromProgIDEx` at `0x180224ea8`
- `ole32!CLSIDFromProgIDEx` at `0x180224ea8`

## pseudocode

```c
__int64 __fastcall ScriptSite::CreateObjectFromProgID(
        ScriptSite *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IUnknown **a4)
{
  __int64 v8; // rdx
  void *v9; // r12
  BOOL IsSafeMode; // r15d
  HRESULT v11; // eax
  DWORD v12; // edx
  bool v13; // sf
  __int64 v14; // rax
  int v15; // eax
  SiteService *v16; // rdi
  int v17; // ebx
  void (*v18)(void); // rax
  LPVOID ppv; // [rsp+30h] [rbp-50h] BYREF
  __int64 v21; // [rsp+38h] [rbp-48h] BYREF
  struct SiteService *v22; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v23[4]; // [rsp+48h] [rbp-38h] BYREF
  GUID clsid; // [rsp+68h] [rbp-18h] BYREF

  v23[0] = 0;
  v8 = *((_QWORD *)this + 1);
  clsid = 0;
  v23[1] = a3;
  v9 = (void *)((unsigned __int64)v23 & -(__int64)(a3 != 0));
  v23[2] = 0;
  v23[3] = 0;
  IsSafeMode = ScriptEngine::IsSafeMode(this, *(_DWORD *)(v8 + 924), 0);
  if ( IsSafeMode )
    v11 = CLSIDFromProgID(a2, &clsid);
  else
    v11 = CLSIDFromProgIDEx(a2, &clsid);
  if ( v11 < 0
    || (unsigned int)IsProhibitedUnsafeExtension(&clsid)
    || !(unsigned int)ScriptEngine::CanCreateObject(*((ScriptEngine **)this + 1), &clsid) )
  {
    return (unsigned int)-2146827859;
  }
  v12 = 5;
  if ( a3 )
  {
    if ( *(int *)(*((_QWORD *)this + 20) + 2336LL) >= 3 || IsSafeMode )
      return (unsigned int)-2146827859;
    v12 = 16;
  }
  ppv = 0;
  v21 = 0;
  if ( CoGetClassObject(&clsid, v12, v9, &IID_IClassFactory, &ppv) < 0 )
    return (unsigned int)-2146827859;
  v13 = (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IClassFactoryEx, &v21) < 0;
  v14 = *(_QWORD *)ppv;
  if ( v13 )
  {
    v17 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, struct IUnknown **))(v14 + 24))(ppv, 0, &IID_IUnknown, a4);
    v18 = *(void (**)(void))(*(_QWORD *)ppv + 16LL);
    if ( v17 < 0 )
    {
      v18();
      return (unsigned int)v17;
    }
    v18();
  }
  else
  {
    (*(void (**)(void))(v14 + 16))();
    v22 = 0;
    v15 = SiteService::Create(&v22, this);
    v16 = v22;
    v17 = v15;
    if ( v15 < 0
      || (v17 = (*(__int64 (__fastcall **)(__int64, struct SiteService *, _QWORD, GUID *, struct IUnknown **))(*(_QWORD *)v21 + 40LL))(
                  v21,
                  v22,
                  0,
                  &IID_IUnknown,
                  a4),
          v17 < 0) )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      if ( v16 )
        SiteService::Release(v16);
      return (unsigned int)v17;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    SiteService::Release(v16);
  }
  if ( !(unsigned int)ScriptEngine::CanObjectRun(*((ScriptEngine **)this + 1), &clsid, *a4) )
  {
    ((void (__fastcall *)(_QWORD))(*a4)->lpVtbl->Release)(*a4);
    *a4 = 0;
    return (unsigned int)-2146827859;
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180224e10  mov     rax, rsp
0x180224e13  mov     [rax+20h], r9
0x180224e17  mov     [rax+18h], r8
0x180224e1b  mov     [rax+10h], rdx
0x180224e1f  mov     [rax+8], rcx
0x180224e23  push    rbp
0x180224e24  push    rbx
0x180224e25  push    rsi
0x180224e26  push    rdi
0x180224e27  push    r12
0x180224e29  push    r14
0x180224e2b  push    r15
0x180224e2d  mov     rbp, rsp
0x180224e30  sub     rsp, 80h
0x180224e37  mov     rax, cs:__security_cookie
0x180224e3e  xor     rax, rsp
0x180224e41  mov     [rbp+var_8], rax
0x180224e45  mov     rdi, [rbp+arg_10]
0x180224e49  xorps   xmm0, xmm0
0x180224e4c  mov     rsi, [rbp+arg_0]
0x180224e50  mov     rax, rdi
0x180224e53  mov     rbx, [rbp+lpszProgID]
0x180224e57  neg     rax
0x180224e5a  mov     r14, [rbp+arg_18]
0x180224e5e  lea     rax, [rbp+var_38]
0x180224e62  sbb     r12, r12
0x180224e65  mov     [rbp+var_38], 0
0x180224e6d  mov     rdx, [rsi+8]
0x180224e71  xor     r8d, r8d; struct _GUID *
0x180224e74  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x180224e78  mov     [rbp+var_30], rdi
0x180224e7c  and     r12, rax
0x180224e7f  mov     [rbp+var_28], 0
0x180224e87  mov     [rbp+var_20], 0
0x180224e8f  mov     edx, [rdx+39Ch]; unsigned int
0x180224e95  call    ?IsSafeMode@ScriptEngine@@QEAAHKPEBU_GUID@@@Z; ScriptEngine::IsSafeMode(ulong,_GUID const *)
0x180224e9a  lea     rdx, [rbp+clsid]; lpclsid
0x180224e9e  mov     r15d, eax
0x180224ea1  mov     rcx, rbx; lpszProgID
0x180224ea4  test    eax, eax
0x180224ea6  jnz     short loc_180224EB6
0x180224ea8  call    cs:__imp_CLSIDFromProgIDEx
0x180224eaf  nop     dword ptr [rax+rax+00h]
0x180224eb4  jmp     short loc_180224EC2
0x180224eb6  call    cs:__imp_CLSIDFromProgID
0x180224ebd  nop     dword ptr [rax+rax+00h]
0x180224ec2  test    eax, eax
0x180224ec4  js      loc_180225063
0x180224eca  lea     rcx, [rbp+clsid]
0x180224ece  call    IsProhibitedUnsafeExtension
0x180224ed3  test    eax, eax
0x180224ed5  jnz     loc_180225063
0x180224edb  mov     rcx, [rsi+8]; this
0x180224edf  lea     rdx, [rbp+clsid]; struct _GUID *
0x180224ee3  call    ?CanCreateObject@ScriptEngine@@QEAAHAEBU_GUID@@@Z; ScriptEngine::CanCreateObject(_GUID const &)
0x180224ee8  test    eax, eax
0x180224eea  jz      loc_180225063
0x180224ef0  mov     edx, 5
0x180224ef5  test    rdi, rdi
0x180224ef8  jz      short loc_180224F1B
0x180224efa  mov     rax, [rsi+0A0h]
0x180224f01  cmp     dword ptr [rax+920h], 3
0x180224f08  jge     loc_180225063
0x180224f0e  test    r15d, r15d
0x180224f11  jnz     loc_180225063
0x180224f17  lea     edx, [r15+10h]; dwClsContext
0x180224f1b  lea     rax, [rbp+var_50]
0x180224f1f  mov     [rbp+var_50], 0
0x180224f27  lea     r9, IID_IClassFactory; riid
0x180224f2e  mov     [rsp+80h+ppv], rax; ppv
0x180224f33  mov     r8, r12; pvReserved
0x180224f36  mov     [rbp+var_48], 0
0x180224f3e  lea     rcx, [rbp+clsid]; rclsid
0x180224f42  call    cs:__imp_CoGetClassObject
0x180224f49  nop     dword ptr [rax+rax+00h]
0x180224f4e  test    eax, eax
0x180224f50  js      loc_180225063
0x180224f56  mov     rcx, [rbp+var_50]
0x180224f5a  lea     r8, [rbp+var_48]
0x180224f5e  lea     rdx, IID_IClassFactoryEx
0x180224f65  mov     rax, [rcx]
0x180224f68  mov     rax, [rax]
0x180224f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180224f70  mov     rcx, [rbp+var_50]
0x180224f74  test    eax, eax
0x180224f76  mov     rax, [rcx]
0x180224f79  js      loc_180225007
0x180224f7f  mov     rax, [rax+10h]
0x180224f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180224f88  mov     rdx, rsi; struct ScriptSite *
0x180224f8b  mov     [rbp+var_40], 0
0x180224f93  lea     rcx, [rbp+var_40]; struct SiteService **
0x180224f97  call    ?Create@SiteService@@SAJPEAPEAV1@PEAVScriptSite@@@Z; SiteService::Create(SiteService * *,ScriptSite *)
0x180224f9c  mov     rdi, [rbp+var_40]
0x180224fa0  mov     ebx, eax
0x180224fa2  test    eax, eax
0x180224fa4  js      short loc_180224FE8
0x180224fa6  mov     rcx, [rbp+var_48]
0x180224faa  lea     r9, IID_IUnknown
0x180224fb1  xor     r8d, r8d
0x180224fb4  mov     [rsp+80h+ppv], r14
0x180224fb9  mov     rdx, rdi
0x180224fbc  mov     rax, [rcx]
0x180224fbf  mov     rax, [rax+28h]
0x180224fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180224fc8  mov     ebx, eax
0x180224fca  test    eax, eax
0x180224fcc  js      short loc_180224FE8
0x180224fce  mov     rcx, [rbp+var_48]
0x180224fd2  mov     rax, [rcx]
0x180224fd5  mov     rax, [rax+10h]
0x180224fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180224fde  mov     rcx, rdi; this
0x180224fe1  call    ?Release@SiteService@@UEAAKXZ; SiteService::Release(void)
0x180224fe6  jmp     short loc_180225039
0x180224fe8  mov     rcx, [rbp+var_48]
0x180224fec  mov     rax, [rcx]
0x180224fef  mov     rax, [rax+10h]
0x180224ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180224ff8  test    rdi, rdi
0x180224ffb  jz      short loc_180225068
0x180224ffd  mov     rcx, rdi; this
0x180225000  call    ?Release@SiteService@@UEAAKXZ; SiteService::Release(void)
0x180225005  jmp     short loc_180225068
0x180225007  mov     rax, [rax+18h]
0x18022500b  lea     r8, IID_IUnknown
0x180225012  mov     r9, r14
0x180225015  xor     edx, edx
0x180225017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022501c  mov     rcx, [rbp+var_50]
0x180225020  mov     ebx, eax
0x180225022  test    eax, eax
0x180225024  mov     rax, [rcx]
0x180225027  mov     rax, [rax+10h]
0x18022502b  jns     short loc_180225034
0x18022502d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180225032  jmp     short loc_180225068
0x180225034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180225039  mov     r8, [r14]; struct IUnknown *
0x18022503c  lea     rdx, [rbp+clsid]; struct _GUID *
0x180225040  mov     rcx, [rsi+8]; this
0x180225044  call    ?CanObjectRun@ScriptEngine@@QEAAHAEBU_GUID@@PEAUIUnknown@@@Z; ScriptEngine::CanObjectRun(_GUID const &,IUnknown *)
0x180225049  test    eax, eax
0x18022504b  jnz     short loc_180225068
0x18022504d  mov     rcx, [r14]
0x180225050  mov     rax, [rcx]
0x180225053  mov     rax, [rax+10h]
0x180225057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022505c  mov     qword ptr [r14], 0
0x180225063  mov     ebx, 800A01ADh
0x180225068  mov     eax, ebx
0x18022506a  mov     rcx, [rbp+var_8]
0x18022506e  xor     rcx, rsp; StackCookie
0x180225071  call    __security_check_cookie
0x180225076  add     rsp, 80h
0x18022507d  pop     r15
0x18022507f  pop     r14
0x180225081  pop     r12
0x180225083  pop     rdi
0x180225084  pop     rsi
0x180225085  pop     rbx
0x180225086  pop     rbp
0x180225087  retn
```
