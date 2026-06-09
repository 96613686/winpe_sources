# ScriptEngine::SetScriptSite(IActiveScriptSite *)

- ea: `0x1801c9590`
- end: `0x1801c9877`
- name: `?SetScriptSite@ScriptEngine@@UEAAJPEAUIActiveScriptSite@@@Z`
- size: `743`
- prototype: `__int64 __fastcall(ScriptEngine *__hidden this, struct IActiveScriptSite *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801c9468`
- `0x18020b6a0`

## callees

- `0x180135188`
- `0x180135c88`
- `0x180198310`
- `0x1801b2cec`
- `0x1801b4a18`
- `0x1801c9590`
- `0x18021b92c`
- `0x18021c12c`
- `0x180220d04`
- `0x1802229ac`
- `0x180224d90`
- `0x180257570`
- `0x18027566c`
- `0x180364010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1801c9778`
- `KERNEL32!EnterCriticalSection` at `0x1801c9778`
- `KERNEL32!LeaveCriticalSection` at `0x1801c97ce`
- `KERNEL32!LeaveCriticalSection` at `0x1801c97ce`
- `KERNEL32!GetCurrentThreadId` at `0x1801c95e5`
- `KERNEL32!GetCurrentThreadId` at `0x1801c95e5`
- `OLEAUT32!__imp_SysFreeString` at `0x1801c9719`
- `OLEAUT32!__imp_SysFreeString` at `0x1801c984a`
- `OLEAUT32!__imp_SysFreeString` at `0x1801c9719`
- `OLEAUT32!__imp_SysFreeString` at `0x1801c984a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ScriptEngine::SetScriptSite(ScriptEngine *this, struct IActiveScriptSite *a2)
{
  struct IActiveScriptSite *v2; // r15
  __int64 result; // rax
  ScriptEngine *v4; // rsi
  struct ScriptEngine *v5; // r14
  __int64 v6; // r8
  char *v7; // rbx
  OLECHAR *v8; // rbx
  ScriptEngine *v9; // rcx
  int v10; // r12d
  int (*v11)(struct Js::ScriptContext *, struct Js::FunctionBody *, const unsigned __int16 *); // rdx
  __int64 v12; // rax
  int v13; // eax
  int v14; // r12d
  int v15; // ebx
  unsigned int v16; // [rsp+20h] [rbp-58h] BYREF
  struct ScriptEngine *v17; // [rsp+28h] [rbp-50h] BYREF
  BSTR bstrString; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v19[8]; // [rsp+38h] [rbp-40h] BYREF

  v19[1] = -2;
  v2 = a2;
  if ( !a2 )
    return 2147500035LL;
  v4 = this;
  v5 = (ScriptEngine *)((char *)this - 48);
  v17 = (ScriptEngine *)((char *)this - 48);
  if ( *((_QWORD *)this + 27) )
    return 2147549183LL;
  *((_DWORD *)this + 75) = GetCurrentThreadId();
  if ( *((_DWORD *)this - 1) )
    return 2147549183LL;
  v7 = (char *)this - 16;
  result = ScriptSite::Create(v5, v2, v6, (struct ScriptSite **)this - 2);
  if ( (int)result >= 0 )
  {
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v7 + 160LL) + 24LL) = v5;
    *(_DWORD *)(*(_QWORD *)v7 + 204LL) = *((_DWORD *)this + 64);
    *((_QWORD *)this + 27) = v2;
    ((void (__fastcall *)(struct IActiveScriptSite *))v2->lpVtbl->AddRef)(v2);
    bstrString = 0;
    if ( (int)ScriptEngine::GetUrl(v5, &bstrString) >= 0 )
    {
      try
      {
        v8 = bstrString;
        Js::ScriptContext::SetUrl(*((Js::ScriptContext **)this - 5), bstrString);
      }
      catch ( Js::OutOfMemoryException )
      {
        v4 = this;
        v2 = a2;
        v5 = v17;
        goto LABEL_8;
      }
    }
    else
    {
LABEL_8:
      v8 = bstrString;
    }
    *((_QWORD *)v4 + 110) = 0;
    v16 = 0;
    if ( ((int (__fastcall *)(struct IActiveScriptSite *, unsigned int *))v2->lpVtbl->GetLCID)(v2, &v16) >= 0
      && (unsigned int)ScriptEngine::SetCurrentLocale(v5, v16) )
    {
      *((_DWORD *)v4 + 71) = *((_DWORD *)v4 + 70);
    }
    ScriptEngine::RegisterNamedItems(v5);
    v9 = (ScriptEngine *)*((_QWORD *)v4 + 87);
    if ( v9 && (v10 = ScriptEngine::CloneScriptBodies(v9, v5), *((_QWORD *)v4 + 87) = 0, v10 < 0) )
    {
      SysFreeString(v8);
      return (unsigned int)v10;
    }
    else
    {
      if ( *((_DWORD *)v4 + 76) )
        ScriptEngine::ChangeScriptState(v5, SCRIPTSTATE_INITIALIZED);
      *((_DWORD *)v4 + 204) &= ~1u;
      if ( (unsigned int)ScriptEngine::IsDebuggerEnvironmentAvailable(v5, 1) )
        Js::ScriptContext::InitializeDebugging(*((Js::ScriptContext **)v4 - 5), v11);
      if ( ScriptEngine::CanRegisterDebugSources(v5) )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v4 + 584));
        v12 = *((_QWORD *)v4 + 88);
        if ( v12 )
        {
          v13 = *(_DWORD *)(v12 + 28);
          if ( v13 > 0 )
          {
            v14 = 0;
            v15 = v13;
            do
              ScriptEngine::DbgRegisterScriptBlock(
                v5,
                *(struct CScriptBody **)(*(_DWORD *)(*((_QWORD *)v4 + 88) + 12LL) * v14++
                                       + *(_QWORD *)(*((_QWORD *)v4 + 88) + 16LL)
                                       + 8LL));
            while ( v14 < v15 );
            v8 = bstrString;
          }
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v4 + 584));
      }
      v19[0] = 0;
      if ( (unsigned int)QueryProtectedPolicyPtr((Js::NullEnumerator *)PPID_ProhibitUnsafeExtensions, (int *)v19)
        && v19[0] == 2 )
      {
        v17 = 0;
        if ( ((__int64 (__fastcall *)(struct IActiveScriptSite *, GUID *, struct ScriptEngine **))v2->lpVtbl->QueryInterface)(
               v2,
               &IID_IActiveScriptSiteDebugEx,
               &v17) < 0 )
          SuppressUnsafeExtensionPolicy();
        else
          (*(void (__fastcall **)(struct ScriptEngine *))(*(_QWORD *)v17 + 16LL))(v17);
      }
      SysFreeString(v8);
      return 0;
    }
  }
  else
  {
    *((_DWORD *)this + 75) = -1;
  }
  return result;
}

```

## disassembly

```asm
0x1801c9590  mov     rax, rsp
0x1801c9593  mov     [rax+10h], rdx
0x1801c9597  mov     [rax+8], rcx
0x1801c959b  push    rsi
0x1801c959c  push    r12
0x1801c959e  push    r13
0x1801c95a0  push    r14
0x1801c95a2  push    r15
0x1801c95a4  sub     rsp, 50h
0x1801c95a8  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x1801c95b0  mov     [rax+18h], rbx
0x1801c95b4  mov     r15, rdx
0x1801c95b7  test    rdx, rdx
0x1801c95ba  jnz     short loc_1801C95C6
0x1801c95bc  mov     eax, 80004003h
0x1801c95c1  jmp     loc_1801C9860
0x1801c95c6  mov     rsi, [rsp+78h+arg_0]
0x1801c95ce  lea     r14, [rsi-30h]
0x1801c95d2  mov     [rsp+78h+var_50], r14
0x1801c95d7  cmp     qword ptr [r14+108h], 0
0x1801c95df  jnz     loc_1801C985B
0x1801c95e5  call    cs:__imp_GetCurrentThreadId
0x1801c95ec  nop     dword ptr [rax+rax+00h]
0x1801c95f1  mov     [rsi+12Ch], eax
0x1801c95f7  cmp     dword ptr [rsi-4], 0
0x1801c95fb  jnz     loc_1801C985B
0x1801c9601  lea     rbx, [rsi-10h]
0x1801c9605  mov     r9, rbx; struct ScriptSite **
0x1801c9608  mov     rdx, r15; struct IActiveScriptSite *
0x1801c960b  mov     rcx, r14; struct ScriptEngine *
0x1801c960e  call    ?Create@ScriptSite@@SAJPEAVScriptEngine@@PEAUIActiveScriptSite@@HPEAPEAV1@@Z; ScriptSite::Create(ScriptEngine *,IActiveScriptSite *,int,ScriptSite * *)
0x1801c9613  test    eax, eax
0x1801c9615  jns     short loc_1801C9626
0x1801c9617  mov     dword ptr [rsi+12Ch], 0FFFFFFFFh
0x1801c9621  jmp     loc_1801C9860
0x1801c9626  mov     rax, [rbx]
0x1801c9629  mov     rcx, [rax+0A0h]
0x1801c9630  mov     [rcx+18h], r14
0x1801c9634  mov     rcx, [rbx]
0x1801c9637  mov     eax, [rsi+100h]
0x1801c963d  mov     [rcx+0CCh], eax
0x1801c9643  mov     [rsi+0D8h], r15
0x1801c964a  mov     rax, [r15]
0x1801c964d  mov     rcx, r15
0x1801c9650  mov     rax, [rax+8]
0x1801c9654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c9659  mov     [rsp+78h+bstrString], 0
0x1801c9662  lea     rdx, [rsp+78h+bstrString]; unsigned __int16 **
0x1801c9667  mov     rcx, r14; this
0x1801c966a  call    ?GetUrl@ScriptEngine@@AEAAJPEAPEAG@Z; ScriptEngine::GetUrl(ushort * *)
0x1801c966f  test    eax, eax
0x1801c9671  js      short loc_1801C969C
0x1801c9673  mov     rbx, [rsp+78h+bstrString]
0x1801c9678  mov     rdx, rbx; unsigned __int16 *
0x1801c967b  mov     rcx, [rsi-28h]; this
0x1801c967f  call    ?SetUrl@ScriptContext@Js@@QEAAXPEAG@Z; Js::ScriptContext::SetUrl(ushort *)
0x1801c9684  nop
0x1801c9685  jmp     short loc_1801C96A1
0x1801c9687  mov     rsi, [rsp+78h+arg_0]
0x1801c968f  mov     r15, [rsp+78h+arg_8]
0x1801c9697  mov     r14, [rsp+78h+var_50]
0x1801c969c  mov     rbx, [rsp+78h+bstrString]
0x1801c96a1  mov     qword ptr [rsi+370h], 0
0x1801c96ac  mov     [rsp+78h+var_58], 0
0x1801c96b4  mov     rax, [r15]
0x1801c96b7  lea     rdx, [rsp+78h+var_58]
0x1801c96bc  mov     rcx, r15
0x1801c96bf  mov     rax, [rax+18h]
0x1801c96c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c96c8  test    eax, eax
0x1801c96ca  js      short loc_1801C96E8
0x1801c96cc  mov     edx, [rsp+78h+var_58]; unsigned int
0x1801c96d0  mov     rcx, r14; this
0x1801c96d3  call    ?SetCurrentLocale@ScriptEngine@@QEAAHK@Z; ScriptEngine::SetCurrentLocale(ulong)
0x1801c96d8  test    eax, eax
0x1801c96da  jz      short loc_1801C96E8
0x1801c96dc  mov     eax, [rsi+118h]
0x1801c96e2  mov     [rsi+11Ch], eax
0x1801c96e8  mov     rcx, r14; this
0x1801c96eb  call    ?RegisterNamedItems@ScriptEngine@@AEAAJXZ; ScriptEngine::RegisterNamedItems(void)
0x1801c96f0  mov     rcx, [rsi+2B8h]; this
0x1801c96f7  test    rcx, rcx
0x1801c96fa  jz      short loc_1801C972E
0x1801c96fc  mov     rdx, r14; struct ScriptEngine *
0x1801c96ff  call    ?CloneScriptBodies@ScriptEngine@@AEAAJPEAV1@@Z; ScriptEngine::CloneScriptBodies(ScriptEngine *)
0x1801c9704  mov     r12d, eax
0x1801c9707  mov     qword ptr [rsi+2B8h], 0
0x1801c9712  test    eax, eax
0x1801c9714  jns     short loc_1801C972E
0x1801c9716  mov     rcx, rbx; bstrString
0x1801c9719  call    cs:__imp_SysFreeString
0x1801c9720  nop     dword ptr [rax+rax+00h]
0x1801c9725  nop
0x1801c9726  mov     eax, r12d
0x1801c9729  jmp     loc_1801C9860
0x1801c972e  cmp     dword ptr [rsi+130h], 0
0x1801c9735  jz      short loc_1801C9744
0x1801c9737  mov     edx, 5; enum tagSCRIPTSTATE
0x1801c973c  mov     rcx, r14; this
0x1801c973f  call    ?ChangeScriptState@ScriptEngine@@AEAAXW4tagSCRIPTSTATE@@@Z; ScriptEngine::ChangeScriptState(tagSCRIPTSTATE)
0x1801c9744  and     dword ptr [rsi+330h], 0FFFFFFFEh
0x1801c974b  mov     dl, 1; bool
0x1801c974d  mov     rcx, r14; this
0x1801c9750  call    ?IsDebuggerEnvironmentAvailable@ScriptEngine@@QEAAH_N@Z; ScriptEngine::IsDebuggerEnvironmentAvailable(bool)
0x1801c9755  test    eax, eax
0x1801c9757  jz      short loc_1801C9762
0x1801c9759  mov     rcx, [rsi-28h]; this
0x1801c975d  call    ?InitializeDebugging@ScriptContext@Js@@QEAA_NP6AJPEAV12@PEAVFunctionBody@2@PEBG@Z@Z; Js::ScriptContext::InitializeDebugging(long (*)(Js::ScriptContext *,Js::FunctionBody *,ushort const *))
0x1801c9762  mov     rcx, r14; this
0x1801c9765  call    ?CanRegisterDebugSources@ScriptEngine@@QEAA_NXZ; ScriptEngine::CanRegisterDebugSources(void)
0x1801c976a  test    al, al
0x1801c976c  jz      short loc_1801C97DA
0x1801c976e  lea     r13, [rsi+248h]
0x1801c9775  mov     rcx, r13; lpCriticalSection
0x1801c9778  call    cs:__imp_EnterCriticalSection
0x1801c977f  nop     dword ptr [rax+rax+00h]
0x1801c9784  mov     rax, [rsi+2C0h]
0x1801c978b  test    rax, rax
0x1801c978e  jz      short loc_1801C97CB
0x1801c9790  mov     eax, [rax+1Ch]
0x1801c9793  test    eax, eax
0x1801c9795  jle     short loc_1801C97CB
0x1801c9797  xor     r12d, r12d
0x1801c979a  mov     ebx, eax
0x1801c979c  mov     rdx, [rsi+2C0h]
0x1801c97a3  mov     eax, r12d
0x1801c97a6  imul    eax, [rdx+0Ch]
0x1801c97aa  movsxd  r8, eax
0x1801c97ad  mov     rdx, [rdx+10h]
0x1801c97b1  mov     rdx, [r8+rdx+8]; struct CScriptBody *
0x1801c97b6  mov     rcx, r14; this
0x1801c97b9  call    ?DbgRegisterScriptBlock@ScriptEngine@@QEAAJPEAVCScriptBody@@@Z; ScriptEngine::DbgRegisterScriptBlock(CScriptBody *)
0x1801c97be  inc     r12d
0x1801c97c1  cmp     r12d, ebx
0x1801c97c4  jl      short loc_1801C979C
0x1801c97c6  mov     rbx, [rsp+78h+bstrString]
0x1801c97cb  mov     rcx, r13; lpCriticalSection
0x1801c97ce  call    cs:__imp_LeaveCriticalSection
0x1801c97d5  nop     dword ptr [rax+rax+00h]
0x1801c97da  mov     [rsp+78h+var_40], 0
0x1801c97e3  mov     rax, cs:QueryProtectedPolicyPtr
0x1801c97ea  lea     rdx, [rsp+78h+var_40]
0x1801c97ef  lea     rcx, PPID_ProhibitUnsafeExtensions
0x1801c97f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c97fb  test    eax, eax
0x1801c97fd  jz      short loc_1801C9847
0x1801c97ff  cmp     [rsp+78h+var_40], 2
0x1801c9805  jnz     short loc_1801C9847
0x1801c9807  mov     [rsp+78h+var_50], 0
0x1801c9810  mov     rax, [r15]
0x1801c9813  lea     r8, [rsp+78h+var_50]
0x1801c9818  lea     rdx, IID_IActiveScriptSiteDebugEx
0x1801c981f  mov     rcx, r15
0x1801c9822  mov     rax, [rax]
0x1801c9825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c982a  test    eax, eax
0x1801c982c  js      short loc_1801C9841
0x1801c982e  mov     rcx, [rsp+78h+var_50]
0x1801c9833  mov     rax, [rcx]
0x1801c9836  mov     rax, [rax+10h]
0x1801c983a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c983f  jmp     short loc_1801C9847
0x1801c9841  call    SuppressUnsafeExtensionPolicy
0x1801c9846  nop
0x1801c9847  mov     rcx, rbx; bstrString
0x1801c984a  call    cs:__imp_SysFreeString
0x1801c9851  nop     dword ptr [rax+rax+00h]
0x1801c9856  nop
0x1801c9857  xor     eax, eax
0x1801c9859  jmp     short loc_1801C9860
0x1801c985b  mov     eax, 8000FFFFh
0x1801c9860  mov     rbx, [rsp+78h+arg_10]
0x1801c9868  add     rsp, 50h
0x1801c986c  pop     r15
0x1801c986e  pop     r14
0x1801c9870  pop     r13
0x1801c9872  pop     r12
0x1801c9874  pop     rsi
0x1801c9875  retn
```
