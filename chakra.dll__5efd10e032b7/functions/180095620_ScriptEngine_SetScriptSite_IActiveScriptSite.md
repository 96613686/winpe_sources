# ScriptEngine::SetScriptSite(IActiveScriptSite *)

- ea: `0x180095620`
- end: `0x18009581c`
- name: `?SetScriptSite@ScriptEngine@@UEAAJPEAUIActiveScriptSite@@@Z`
- size: `508`
- prototype: `__int64 __fastcall(ScriptEngine *__hidden this, struct IActiveScriptSite *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1803faed8`

## callees

- `0x180095620`
- `0x180095824`
- `0x180095914`
- `0x180095978`
- `0x180095b04`
- `0x180096968`
- `0x18011bd38`
- `0x18011c8d8`
- `0x18041f650`
- `0x180540c78`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800957db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800957db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009578a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009578a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180095671`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180095671`
- `OLEAUT32!__imp_SysFreeString` at `0x1800957f0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800957f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ScriptEngine::SetScriptSite(ScriptEngine *this, struct IActiveScriptSite *a2)
{
  __int64 result; // rax
  ScriptEngine *v4; // rdi
  struct ScriptEngine *v5; // rsi
  int v6; // r8d
  char *v7; // r15
  ScriptEngine *v8; // r14
  OLECHAR *v9; // rbx
  Js::ScriptContext **v10; // r14
  __int64 v11; // rax
  int v12; // r12d
  int i; // r14d
  BSTR bstrString; // [rsp+20h] [rbp-48h] BYREF
  ScriptEngine *v15; // [rsp+28h] [rbp-40h]
  struct ScriptEngine *v16; // [rsp+30h] [rbp-38h]
  __int64 v17; // [rsp+38h] [rbp-30h]

  v17 = -2;
  if ( !a2 )
    return 2147500035LL;
  v4 = this;
  v5 = (ScriptEngine *)((char *)this - 56);
  v16 = (ScriptEngine *)((char *)this - 56);
  if ( *((_QWORD *)this + 32) )
    return 2147549183LL;
  *((_DWORD *)this + 76) = GetCurrentThreadId();
  if ( *((_DWORD *)this - 1) )
    return 2147549183LL;
  v7 = (char *)this - 24;
  result = ScriptSite::Create(v5, a2, v6, (struct ScriptSite **)this - 3);
  if ( (int)result >= 0 )
  {
    v8 = this;
    v15 = this;
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v7 + 160LL) + 32LL) = v5;
    *(_DWORD *)(*(_QWORD *)v7 + 212LL) = *((_DWORD *)this + 70);
    *((_QWORD *)this + 32) = a2;
    ((void (__fastcall *)(struct IActiveScriptSite *))a2->lpVtbl->AddRef)(a2);
    bstrString = 0;
    if ( (int)ScriptEngine::GetUrl(v5, &bstrString) >= 0 )
    {
      try
      {
        v9 = bstrString;
        Js::ScriptContext::SetUrl(*((Js::ScriptContext **)this - 6), bstrString);
      }
      catch ( Js::OutOfMemoryException )
      {
        v4 = this;
        v8 = v15;
        v5 = v16;
        goto LABEL_8;
      }
    }
    else
    {
LABEL_8:
      v9 = bstrString;
    }
    ScriptEngine::RegisterNamedItems(v5);
    if ( *((_DWORD *)v4 + 77) )
      ScriptEngine::ChangeScriptState(v5, SCRIPTSTATE_INITIALIZED);
    *((_BYTE *)v4 + 824) &= ~1u;
    if ( (unsigned int)ScriptEngine::IsDebuggerEnvironmentAvailable(v5, 1) )
    {
      v10 = (Js::ScriptContext **)((char *)v4 - 48);
      Js::ScriptContext::InitializeDebugging(*((Js::ScriptContext **)v4 - 6));
    }
    else
    {
      v10 = (Js::ScriptContext **)((char *)v8 - 48);
    }
    if ( Js::ScriptContext::IsScriptContextInSourceRundownOrDebugMode(*v10) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v4 + 584));
      v11 = *((_QWORD *)v4 + 86);
      if ( v11 )
      {
        v12 = *(_DWORD *)(v11 + 28);
        if ( v12 > 0 )
        {
          for ( i = 0; i < v12; ++i )
            ScriptEngine::DbgRegisterScriptBlock(
              v5,
              *(struct CScriptBody **)(*(_DWORD *)(*((_QWORD *)v4 + 86) + 12LL) * i
                                     + *(_QWORD *)(*((_QWORD *)v4 + 86) + 16LL)
                                     + 8LL));
        }
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v4 + 584));
    }
    if ( v9 )
      SysFreeString(v9);
    return 0;
  }
  else
  {
    *((_DWORD *)this + 76) = -1;
  }
  return result;
}

```

## disassembly

```asm
0x180095620  mov     rax, rsp
0x180095623  mov     [rax+10h], rdx
0x180095627  mov     [rax+8], rcx
0x18009562b  push    rsi
0x18009562c  push    rdi
0x18009562d  push    r12
0x18009562f  push    r14
0x180095631  push    r15
0x180095633  sub     rsp, 40h
0x180095637  mov     qword ptr [rax-30h], 0FFFFFFFFFFFFFFFEh
0x18009563f  mov     [rax+18h], rbx
0x180095643  mov     rbx, rdx
0x180095646  test    rdx, rdx
0x180095649  jnz     short loc_180095655
0x18009564b  mov     eax, 80004003h
0x180095650  jmp     loc_180095806
0x180095655  mov     rdi, [rsp+68h+arg_0]
0x18009565a  lea     rsi, [rdi-38h]
0x18009565e  mov     [rsp+68h+var_38], rsi
0x180095663  cmp     qword ptr [rsi+138h], 0
0x18009566b  jnz     loc_180095801
0x180095671  call    cs:__imp_GetCurrentThreadId
0x180095678  nop     dword ptr [rax+rax+00h]
0x18009567d  mov     [rdi+130h], eax
0x180095683  cmp     dword ptr [rdi-4], 0
0x180095687  jnz     loc_180095801
0x18009568d  lea     r15, [rdi-18h]
0x180095691  mov     r9, r15; struct ScriptSite **
0x180095694  mov     rdx, rbx; struct IActiveScriptSite *
0x180095697  mov     rcx, rsi; struct ScriptEngine *
0x18009569a  call    ?Create@ScriptSite@@SAJPEAVScriptEngine@@PEAUIActiveScriptSite@@HPEAPEAV1@@Z; ScriptSite::Create(ScriptEngine *,IActiveScriptSite *,int,ScriptSite * *)
0x18009569f  test    eax, eax
0x1800956a1  jns     short loc_1800956B2
0x1800956a3  mov     dword ptr [rdi+130h], 0FFFFFFFFh
0x1800956ad  jmp     loc_180095806
0x1800956b2  mov     r14, rdi
0x1800956b5  mov     [rsp+68h+var_40], rdi
0x1800956ba  mov     rax, [r15]
0x1800956bd  mov     rdx, [rax+0A0h]
0x1800956c4  mov     [rdx+20h], rsi
0x1800956c8  mov     rdx, [r15]
0x1800956cb  mov     eax, [rdi+118h]
0x1800956d1  mov     [rdx+0D4h], eax
0x1800956d7  mov     [rdi+100h], rbx
0x1800956de  mov     rax, [rbx]
0x1800956e1  mov     rcx, rbx
0x1800956e4  mov     rax, [rax+8]
0x1800956e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800956ed  mov     [rsp+68h+bstrString], 0
0x1800956f6  lea     rdx, [rsp+68h+bstrString]; unsigned __int16 **
0x1800956fb  mov     rcx, rsi; this
0x1800956fe  call    ?GetUrl@ScriptEngine@@AEAAJPEAPEAG@Z; ScriptEngine::GetUrl(ushort * *)
0x180095703  test    eax, eax
0x180095705  js      short loc_18009572A
0x180095707  mov     rbx, [rsp+68h+bstrString]
0x18009570c  mov     rdx, rbx; unsigned __int16 *
0x18009570f  mov     rcx, [rdi-30h]; this
0x180095713  call    ?SetUrl@ScriptContext@Js@@QEAAXPEAG@Z; Js::ScriptContext::SetUrl(ushort *)
0x180095718  nop
0x180095719  jmp     short loc_18009572F
0x18009571b  mov     rdi, [rsp+68h+arg_0]
0x180095720  mov     r14, [rsp+68h+var_40]
0x180095725  mov     rsi, [rsp+68h+var_38]
0x18009572a  mov     rbx, [rsp+68h+bstrString]
0x18009572f  mov     rcx, rsi; this
0x180095732  call    ?RegisterNamedItems@ScriptEngine@@AEAAJXZ; ScriptEngine::RegisterNamedItems(void)
0x180095737  cmp     dword ptr [rdi+134h], 0
0x18009573e  jz      short loc_18009574D
0x180095740  mov     edx, 5; enum tagSCRIPTSTATE
0x180095745  mov     rcx, rsi; this
0x180095748  call    ?ChangeScriptState@ScriptEngine@@AEAAXW4tagSCRIPTSTATE@@@Z; ScriptEngine::ChangeScriptState(tagSCRIPTSTATE)
0x18009574d  and     byte ptr [rdi+338h], 0FEh
0x180095754  mov     dl, 1; bool
0x180095756  mov     rcx, rsi; this
0x180095759  call    ?IsDebuggerEnvironmentAvailable@ScriptEngine@@QEAAH_N@Z; ScriptEngine::IsDebuggerEnvironmentAvailable(bool)
0x18009575e  test    eax, eax
0x180095760  jz      short loc_180095770
0x180095762  lea     r14, [rdi-30h]
0x180095766  mov     rcx, [r14]; this
0x180095769  call    ?InitializeDebugging@ScriptContext@Js@@QEAAXXZ; Js::ScriptContext::InitializeDebugging(void)
0x18009576e  jmp     short loc_180095774
0x180095770  add     r14, 0FFFFFFFFFFFFFFD0h
0x180095774  mov     rcx, [r14]; this
0x180095777  call    ?IsScriptContextInSourceRundownOrDebugMode@ScriptContext@Js@@QEBA_NXZ; Js::ScriptContext::IsScriptContextInSourceRundownOrDebugMode(void)
0x18009577c  test    al, al
0x18009577e  jz      short loc_1800957E8
0x180095780  lea     r15, [rdi+248h]
0x180095787  mov     rcx, r15; lpCriticalSection
0x18009578a  call    cs:__imp_EnterCriticalSection
0x180095791  nop     dword ptr [rax+rax+00h]
0x180095796  mov     rax, [rdi+2B0h]
0x18009579d  test    rax, rax
0x1800957a0  jz      short loc_1800957D8
0x1800957a2  mov     r12d, [rax+1Ch]
0x1800957a6  test    r12d, r12d
0x1800957a9  jle     short loc_1800957D8
0x1800957ab  xor     r14d, r14d
0x1800957ae  mov     rdx, [rdi+2B0h]
0x1800957b5  mov     eax, r14d
0x1800957b8  imul    eax, [rdx+0Ch]
0x1800957bc  movsxd  r8, eax
0x1800957bf  mov     rdx, [rdx+10h]
0x1800957c3  mov     rdx, [r8+rdx+8]; struct CScriptBody *
0x1800957c8  mov     rcx, rsi; this
0x1800957cb  call    ?DbgRegisterScriptBlock@ScriptEngine@@QEAAJPEAVCScriptBody@@@Z; ScriptEngine::DbgRegisterScriptBlock(CScriptBody *)
0x1800957d0  inc     r14d
0x1800957d3  cmp     r14d, r12d
0x1800957d6  jl      short loc_1800957AE
0x1800957d8  mov     rcx, r15; lpCriticalSection
0x1800957db  call    cs:__imp_LeaveCriticalSection
0x1800957e2  nop     dword ptr [rax+rax+00h]
0x1800957e7  nop
0x1800957e8  test    rbx, rbx
0x1800957eb  jz      short loc_1800957FD
0x1800957ed  mov     rcx, rbx; bstrString
0x1800957f0  call    cs:__imp_SysFreeString
0x1800957f7  nop     dword ptr [rax+rax+00h]
0x1800957fc  nop
0x1800957fd  xor     eax, eax
0x1800957ff  jmp     short loc_180095806
0x180095801  mov     eax, 8000FFFFh
0x180095806  mov     rbx, [rsp+68h+arg_10]
0x18009580e  add     rsp, 40h
0x180095812  pop     r15
0x180095814  pop     r14
0x180095816  pop     r12
0x180095818  pop     rdi
0x180095819  pop     rsi
0x18009581a  retn
```
