# ScriptEngine::SetScriptSite(IActiveScriptSite *)

- ea: `0x1801c6c10`
- end: `0x1801c6ed8`
- name: `?SetScriptSite@ScriptEngine@@UEAAJPEAUIActiveScriptSite@@@Z`
- size: `712`
- prototype: `__int64 __fastcall(ScriptEngine *__hidden this, struct IActiveScriptSite *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801c6af0`
- `0x180208120`

## callees

- `0x18010fccc`
- `0x180111520`
- `0x180195a98`
- `0x1801b049c`
- `0x1801b24f0`
- `0x1801c6c10`
- `0x180218008`
- `0x180218808`
- `0x18021d004`
- `0x18021ec3c`
- `0x180220ee8`
- `0x180252f3c`
- `0x180270af8`
- `0x18035e010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1801c6dec`
- `KERNEL32!EnterCriticalSection` at `0x1801c6dec`
- `KERNEL32!LeaveCriticalSection` at `0x1801c6e3c`
- `KERNEL32!LeaveCriticalSection` at `0x1801c6e3c`
- `KERNEL32!GetCurrentThreadId` at `0x1801c6c65`
- `KERNEL32!GetCurrentThreadId` at `0x1801c6c65`
- `OLEAUT32!__imp_SysFreeString` at `0x1801c6d93`
- `OLEAUT32!__imp_SysFreeString` at `0x1801c6eb2`
- `OLEAUT32!__imp_SysFreeString` at `0x1801c6d93`
- `OLEAUT32!__imp_SysFreeString` at `0x1801c6eb2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ScriptEngine::SetScriptSite(ScriptEngine *this, struct IActiveScriptSite *a2)
{
  struct IActiveScriptSite *v2; // r15
  __int64 result; // rax
  ScriptEngine *v4; // rsi
  struct ScriptEngine *v5; // r14
  int v6; // r8d
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
      if ( (unsigned int)QueryProtectedPolicyPtr((Js::NullEnumerator *)&PPID_ProhibitUnsafeExtensions, (int *)v19)
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
0x1801c6c10  mov     rax, rsp
0x1801c6c13  mov     [rax+10h], rdx
0x1801c6c17  mov     [rax+8], rcx
0x1801c6c1b  push    rsi
0x1801c6c1c  push    r12
0x1801c6c1e  push    r13
0x1801c6c20  push    r14
0x1801c6c22  push    r15
0x1801c6c24  sub     rsp, 50h
0x1801c6c28  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x1801c6c30  mov     [rax+18h], rbx
0x1801c6c34  mov     r15, rdx
0x1801c6c37  test    rdx, rdx
0x1801c6c3a  jnz     short loc_1801C6C46
0x1801c6c3c  mov     eax, 80004003h
0x1801c6c41  jmp     loc_1801C6EC2
0x1801c6c46  mov     rsi, [rsp+78h+arg_0]
0x1801c6c4e  lea     r14, [rsi-30h]
0x1801c6c52  mov     [rsp+78h+var_50], r14
0x1801c6c57  cmp     qword ptr [r14+108h], 0
0x1801c6c5f  jnz     loc_1801C6EBD
0x1801c6c65  call    cs:__imp_GetCurrentThreadId
0x1801c6c6b  mov     [rsi+12Ch], eax
0x1801c6c71  cmp     dword ptr [rsi-4], 0
0x1801c6c75  jnz     loc_1801C6EBD
0x1801c6c7b  lea     rbx, [rsi-10h]
0x1801c6c7f  mov     r9, rbx; struct ScriptSite **
0x1801c6c82  mov     rdx, r15; struct IActiveScriptSite *
0x1801c6c85  mov     rcx, r14; struct ScriptEngine *
0x1801c6c88  call    ?Create@ScriptSite@@SAJPEAVScriptEngine@@PEAUIActiveScriptSite@@HPEAPEAV1@@Z; ScriptSite::Create(ScriptEngine *,IActiveScriptSite *,int,ScriptSite * *)
0x1801c6c8d  test    eax, eax
0x1801c6c8f  jns     short loc_1801C6CA0
0x1801c6c91  mov     dword ptr [rsi+12Ch], 0FFFFFFFFh
0x1801c6c9b  jmp     loc_1801C6EC2
0x1801c6ca0  mov     rax, [rbx]
0x1801c6ca3  mov     rcx, [rax+0A0h]
0x1801c6caa  mov     [rcx+18h], r14
0x1801c6cae  mov     rcx, [rbx]
0x1801c6cb1  mov     eax, [rsi+100h]
0x1801c6cb7  mov     [rcx+0CCh], eax
0x1801c6cbd  mov     [rsi+0D8h], r15
0x1801c6cc4  mov     rax, [r15]
0x1801c6cc7  mov     rcx, r15
0x1801c6cca  mov     rax, [rax+8]
0x1801c6cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c6cd3  mov     [rsp+78h+bstrString], 0
0x1801c6cdc  lea     rdx, [rsp+78h+bstrString]; unsigned __int16 **
0x1801c6ce1  mov     rcx, r14; this
0x1801c6ce4  call    ?GetUrl@ScriptEngine@@AEAAJPEAPEAG@Z; ScriptEngine::GetUrl(ushort * *)
0x1801c6ce9  test    eax, eax
0x1801c6ceb  js      short loc_1801C6D16
0x1801c6ced  mov     rbx, [rsp+78h+bstrString]
0x1801c6cf2  mov     rdx, rbx; unsigned __int16 *
0x1801c6cf5  mov     rcx, [rsi-28h]; this
0x1801c6cf9  call    ?SetUrl@ScriptContext@Js@@QEAAXPEAG@Z; Js::ScriptContext::SetUrl(ushort *)
0x1801c6cfe  nop
0x1801c6cff  jmp     short loc_1801C6D1B
0x1801c6d01  mov     rsi, [rsp+78h+arg_0]
0x1801c6d09  mov     r15, [rsp+78h+arg_8]
0x1801c6d11  mov     r14, [rsp+78h+var_50]
0x1801c6d16  mov     rbx, [rsp+78h+bstrString]
0x1801c6d1b  mov     qword ptr [rsi+370h], 0
0x1801c6d26  mov     [rsp+78h+var_58], 0
0x1801c6d2e  mov     rax, [r15]
0x1801c6d31  lea     rdx, [rsp+78h+var_58]
0x1801c6d36  mov     rcx, r15
0x1801c6d39  mov     rax, [rax+18h]
0x1801c6d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c6d42  test    eax, eax
0x1801c6d44  js      short loc_1801C6D62
0x1801c6d46  mov     edx, [rsp+78h+var_58]; unsigned int
0x1801c6d4a  mov     rcx, r14; this
0x1801c6d4d  call    ?SetCurrentLocale@ScriptEngine@@QEAAHK@Z; ScriptEngine::SetCurrentLocale(ulong)
0x1801c6d52  test    eax, eax
0x1801c6d54  jz      short loc_1801C6D62
0x1801c6d56  mov     eax, [rsi+118h]
0x1801c6d5c  mov     [rsi+11Ch], eax
0x1801c6d62  mov     rcx, r14; this
0x1801c6d65  call    ?RegisterNamedItems@ScriptEngine@@AEAAJXZ; ScriptEngine::RegisterNamedItems(void)
0x1801c6d6a  mov     rcx, [rsi+2B8h]; this
0x1801c6d71  test    rcx, rcx
0x1801c6d74  jz      short loc_1801C6DA2
0x1801c6d76  mov     rdx, r14; struct ScriptEngine *
0x1801c6d79  call    ?CloneScriptBodies@ScriptEngine@@AEAAJPEAV1@@Z; ScriptEngine::CloneScriptBodies(ScriptEngine *)
0x1801c6d7e  mov     r12d, eax
0x1801c6d81  mov     qword ptr [rsi+2B8h], 0
0x1801c6d8c  test    eax, eax
0x1801c6d8e  jns     short loc_1801C6DA2
0x1801c6d90  mov     rcx, rbx; bstrString
0x1801c6d93  call    cs:__imp_SysFreeString
0x1801c6d99  nop
0x1801c6d9a  mov     eax, r12d
0x1801c6d9d  jmp     loc_1801C6EC2
0x1801c6da2  cmp     dword ptr [rsi+130h], 0
0x1801c6da9  jz      short loc_1801C6DB8
0x1801c6dab  mov     edx, 5; enum tagSCRIPTSTATE
0x1801c6db0  mov     rcx, r14; this
0x1801c6db3  call    ?ChangeScriptState@ScriptEngine@@AEAAXW4tagSCRIPTSTATE@@@Z; ScriptEngine::ChangeScriptState(tagSCRIPTSTATE)
0x1801c6db8  and     dword ptr [rsi+330h], 0FFFFFFFEh
0x1801c6dbf  mov     dl, 1; bool
0x1801c6dc1  mov     rcx, r14; this
0x1801c6dc4  call    ?IsDebuggerEnvironmentAvailable@ScriptEngine@@QEAAH_N@Z; ScriptEngine::IsDebuggerEnvironmentAvailable(bool)
0x1801c6dc9  test    eax, eax
0x1801c6dcb  jz      short loc_1801C6DD6
0x1801c6dcd  mov     rcx, [rsi-28h]; this
0x1801c6dd1  call    ?InitializeDebugging@ScriptContext@Js@@QEAA_NP6AJPEAV12@PEAVFunctionBody@2@PEBG@Z@Z; Js::ScriptContext::InitializeDebugging(long (*)(Js::ScriptContext *,Js::FunctionBody *,ushort const *))
0x1801c6dd6  mov     rcx, r14; this
0x1801c6dd9  call    ?CanRegisterDebugSources@ScriptEngine@@QEAA_NXZ; ScriptEngine::CanRegisterDebugSources(void)
0x1801c6dde  test    al, al
0x1801c6de0  jz      short loc_1801C6E42
0x1801c6de2  lea     r13, [rsi+248h]
0x1801c6de9  mov     rcx, r13; lpCriticalSection
0x1801c6dec  call    cs:__imp_EnterCriticalSection
0x1801c6df2  mov     rax, [rsi+2C0h]
0x1801c6df9  test    rax, rax
0x1801c6dfc  jz      short loc_1801C6E39
0x1801c6dfe  mov     eax, [rax+1Ch]
0x1801c6e01  test    eax, eax
0x1801c6e03  jle     short loc_1801C6E39
0x1801c6e05  xor     r12d, r12d
0x1801c6e08  mov     ebx, eax
0x1801c6e0a  mov     rdx, [rsi+2C0h]
0x1801c6e11  mov     eax, r12d
0x1801c6e14  imul    eax, [rdx+0Ch]
0x1801c6e18  movsxd  r8, eax
0x1801c6e1b  mov     rdx, [rdx+10h]
0x1801c6e1f  mov     rdx, [r8+rdx+8]; struct CScriptBody *
0x1801c6e24  mov     rcx, r14; this
0x1801c6e27  call    ?DbgRegisterScriptBlock@ScriptEngine@@QEAAJPEAVCScriptBody@@@Z; ScriptEngine::DbgRegisterScriptBlock(CScriptBody *)
0x1801c6e2c  inc     r12d
0x1801c6e2f  cmp     r12d, ebx
0x1801c6e32  jl      short loc_1801C6E0A
0x1801c6e34  mov     rbx, [rsp+78h+bstrString]
0x1801c6e39  mov     rcx, r13; lpCriticalSection
0x1801c6e3c  call    cs:__imp_LeaveCriticalSection
0x1801c6e42  mov     [rsp+78h+var_40], 0
0x1801c6e4b  mov     rax, cs:QueryProtectedPolicyPtr
0x1801c6e52  lea     rdx, [rsp+78h+var_40]
0x1801c6e57  lea     rcx, PPID_ProhibitUnsafeExtensions
0x1801c6e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c6e63  test    eax, eax
0x1801c6e65  jz      short loc_1801C6EAF
0x1801c6e67  cmp     [rsp+78h+var_40], 2
0x1801c6e6d  jnz     short loc_1801C6EAF
0x1801c6e6f  mov     [rsp+78h+var_50], 0
0x1801c6e78  mov     rax, [r15]
0x1801c6e7b  lea     r8, [rsp+78h+var_50]
0x1801c6e80  lea     rdx, IID_IActiveScriptSiteDebugEx
0x1801c6e87  mov     rcx, r15
0x1801c6e8a  mov     rax, [rax]
0x1801c6e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c6e92  test    eax, eax
0x1801c6e94  js      short loc_1801C6EA9
0x1801c6e96  mov     rcx, [rsp+78h+var_50]
0x1801c6e9b  mov     rax, [rcx]
0x1801c6e9e  mov     rax, [rax+10h]
0x1801c6ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c6ea7  jmp     short loc_1801C6EAF
0x1801c6ea9  call    SuppressUnsafeExtensionPolicy
0x1801c6eae  nop
0x1801c6eaf  mov     rcx, rbx; bstrString
0x1801c6eb2  call    cs:__imp_SysFreeString
0x1801c6eb8  nop
0x1801c6eb9  xor     eax, eax
0x1801c6ebb  jmp     short loc_1801C6EC2
0x1801c6ebd  mov     eax, 8000FFFFh
0x1801c6ec2  mov     rbx, [rsp+78h+arg_10]
0x1801c6eca  add     rsp, 50h
0x1801c6ece  pop     r15
0x1801c6ed0  pop     r14
0x1801c6ed2  pop     r13
0x1801c6ed4  pop     r12
0x1801c6ed6  pop     rsi
0x1801c6ed7  retn
```
