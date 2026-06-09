# CEffectCompilationTask::Compile_WorkerThread(void)

- ea: `0x1801a07f4`
- end: `0x1801a0997`
- name: `?Compile_WorkerThread@CEffectCompilationTask@@AEAAXXZ`
- size: `419`
- prototype: `void __fastcall(CEffectCompilationTask *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1802422d0`

## callees

- `0x18004a92c`
- `0x180050270`
- `0x1800516b0`
- `0x18012d74c`
- `0x1801a07f4`
- `0x1801a09a0`
- `0x1801d8a14`
- `0x1801d8a78`
- `0x18020a2d8`
- `0x180242358`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1801a080e`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1801a080e`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a0964`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a0964`
- `wuceffects!CompileEffectDescription` at `0x1801a0834`
- `wuceffects!CompileEffectDescription` at `0x1801a0834`

## pseudocode

```c
void __fastcall CEffectCompilationTask::Compile_WorkerThread(CEffectCompilationTask *this)
{
  __int64 v2; // rcx
  int v3; // esi
  _QWORD *v4; // rax
  void (__fastcall ***v5)(_QWORD); // rcx
  _QWORD *v6; // rdi
  __int64 v7; // rdx
  OLECHAR *v8; // rbp
  CEffectCompilationService *v9; // rcx
  void (__fastcall ***v10)(_QWORD); // rcx
  void (__fastcall ***v11)(_QWORD); // [rsp+50h] [rbp+8h] BYREF
  char v12; // [rsp+58h] [rbp+10h] BYREF

  v11 = 0;
  SetRestrictedErrorInfo(0);
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x10) != 0 )
    McTemplateU0x_EventWriteTransfer(v2, EVTDESC_COMPILE_EFFECT_Start);
  Microsoft::WRL::ComPtr<CBrushRenderingGraph>::InternalRelease(&v11);
  v3 = CompileEffectDescription(*((_QWORD *)this + 7), &v11);
  if ( v3 < 0 )
  {
    v8 = (OLECHAR *)*((_QWORD *)this + 11);
    if ( v8 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v12);
      SysFreeString(v8);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v12);
    }
    *((_QWORD *)this + 11) = 0;
    CEffectCompilationTask::GetRestrictedErrorDescription((unsigned __int16 **)this + 11);
  }
  else
  {
    v4 = MIDL_user_allocate(0x28u);
    v6 = v4;
    if ( v4 )
    {
      v5 = v11;
      *v4 = 0;
      v4[1] = 0;
      *((_DWORD *)v4 + 4) = 0;
      v4[3] = this;
      v4[4] = v5;
      if ( v5 )
        (**v5)(v5);
    }
    else
    {
      v6 = 0;
    }
    v7 = *((_QWORD *)this + 10);
    *((_QWORD *)this + 10) = v6;
    if ( v7 )
      std::default_delete<CCompiledEffectCache>::operator()();
    if ( !*((_QWORD *)this + 10) )
    {
      v3 = -2147024882;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024882, 0xB9u, 0);
    }
  }
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x10) != 0 )
    McTemplateU0x_EventWriteTransfer(v5, EVTDESC_COMPILE_EFFECT_Stop);
  v9 = (CEffectCompilationService *)*((_QWORD *)this + 2);
  *((_DWORD *)this + 19) = v3;
  *((_DWORD *)this + 18) = (v3 >> 31) + 3;
  CEffectCompilationService::OnTaskCompleted_AnyThread(v9, this, 0);
  v10 = v11;
  if ( v11 )
  {
    v11 = 0;
    (*v10)[1](v10);
  }
}

```

## disassembly

```asm
0x1801a07f4  mov     [rsp+arg_10], rbx
0x1801a07f9  push    rbp
0x1801a07fa  push    rsi
0x1801a07fb  push    rdi
0x1801a07fc  sub     rsp, 30h
0x1801a0800  mov     rbx, rcx
0x1801a0803  mov     [rsp+48h+arg_0], 0
0x1801a080c  xor     ecx, ecx
0x1801a080e  call    cs:__imp_SetRestrictedErrorInfo
0x1801a0814  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x1801a081b  jnz     loc_1801A0943
0x1801a0821  lea     rcx, [rsp+48h+arg_0]
0x1801a0826  call    ?InternalRelease@?$ComPtr@VCBrushRenderingGraph@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CBrushRenderingGraph>::InternalRelease(void)
0x1801a082b  mov     rcx, [rbx+38h]
0x1801a082f  lea     rdx, [rsp+48h+arg_0]
0x1801a0834  call    cs:__imp_CompileEffectDescription
0x1801a083a  mov     esi, eax
0x1801a083c  test    eax, eax
0x1801a083e  js      loc_1801A08CD
0x1801a0844  mov     ecx, 28h ; '('; size
0x1801a0849  call    MIDL_user_allocate
0x1801a084e  mov     rdi, rax
0x1801a0851  test    rax, rax
0x1801a0854  jz      loc_1801A093C
0x1801a085a  mov     rcx, [rsp+48h+arg_0]
0x1801a085f  mov     qword ptr [rax], 0
0x1801a0866  mov     qword ptr [rax+8], 0
0x1801a086e  mov     dword ptr [rax+10h], 0
0x1801a0875  mov     [rax+18h], rbx
0x1801a0879  mov     [rax+20h], rcx
0x1801a087d  test    rcx, rcx
0x1801a0880  jz      short loc_1801A088D
0x1801a0882  mov     rdx, [rcx]
0x1801a0885  mov     rax, [rdx]
0x1801a0888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a088d  mov     rdx, [rbx+50h]
0x1801a0891  mov     [rbx+50h], rdi
0x1801a0895  test    rdx, rdx
0x1801a0898  jnz     loc_1801A0979
0x1801a089e  cmp     qword ptr [rbx+50h], 0
0x1801a08a3  jnz     short loc_1801A08E8
0x1801a08a5  xor     edx, edx; int *
0x1801a08a7  mov     [rsp+48h+var_20], 0; void *
0x1801a08b0  mov     esi, 8007000Eh
0x1801a08b5  mov     [rsp+48h+var_28], 0B9h; unsigned int
0x1801a08bd  mov     r9d, esi; int
0x1801a08c0  xor     r8d, r8d; unsigned int
0x1801a08c3  lea     ecx, [rdx+14h]; unsigned int
0x1801a08c6  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801a08cb  jmp     short loc_1801A08E8
0x1801a08cd  lea     rdi, [rbx+58h]
0x1801a08d1  mov     rbp, [rdi]
0x1801a08d4  test    rbp, rbp
0x1801a08d7  jnz     short loc_1801A0957
0x1801a08d9  mov     rcx, rdi; unsigned __int16 **
0x1801a08dc  mov     qword ptr [rdi], 0
0x1801a08e3  call    ?GetRestrictedErrorDescription@CEffectCompilationTask@@SAJPEAPEAG@Z; CEffectCompilationTask::GetRestrictedErrorDescription(ushort * *)
0x1801a08e8  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x1801a08ef  jnz     loc_1801A0983
0x1801a08f5  mov     rcx, [rbx+10h]; this
0x1801a08f9  xor     r8d, r8d; bool
0x1801a08fc  mov     [rbx+4Ch], esi
0x1801a08ff  mov     rdx, rbx; struct CEffectCompilationTask *
0x1801a0902  sar     esi, 1Fh
0x1801a0905  add     esi, 3
0x1801a0908  mov     [rbx+48h], esi
0x1801a090b  call    ?OnTaskCompleted_AnyThread@CEffectCompilationService@@AEAAXPEAVCEffectCompilationTask@@_N@Z; CEffectCompilationService::OnTaskCompleted_AnyThread(CEffectCompilationTask *,bool)
0x1801a0910  mov     rcx, [rsp+48h+arg_0]
0x1801a0915  test    rcx, rcx
0x1801a0918  jz      short loc_1801A092F
0x1801a091a  mov     [rsp+48h+arg_0], 0
0x1801a0923  mov     rax, [rcx]
0x1801a0926  mov     rax, [rax+8]
0x1801a092a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a092f  mov     rbx, [rsp+48h+arg_10]
0x1801a0934  add     rsp, 30h
0x1801a0938  pop     rdi
0x1801a0939  pop     rsi
0x1801a093a  pop     rbp
0x1801a093b  retn
0x1801a093c  xor     edi, edi
0x1801a093e  jmp     loc_1801A088D
0x1801a0943  mov     r8, rbx
0x1801a0946  lea     rdx, EVTDESC_COMPILE_EFFECT_Start
0x1801a094d  call    McTemplateU0x_EventWriteTransfer
0x1801a0952  jmp     loc_1801A0821
0x1801a0957  lea     rcx, [rsp+48h+arg_8]; this
0x1801a095c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801a0961  mov     rcx, rbp; bstrString
0x1801a0964  call    cs:__imp_SysFreeString
0x1801a096a  lea     rcx, [rsp+48h+arg_8]; this
0x1801a096f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801a0974  jmp     loc_1801A08D9
0x1801a0979  call    ??R?$default_delete@VCCompiledEffectCache@@@std@@QEBAXPEAVCCompiledEffectCache@@@Z; std::default_delete<CCompiledEffectCache>::operator()(CCompiledEffectCache *)
0x1801a097e  jmp     loc_1801A089E
0x1801a0983  mov     r8, rbx
0x1801a0986  lea     rdx, EVTDESC_COMPILE_EFFECT_Stop
0x1801a098d  call    McTemplateU0x_EventWriteTransfer
0x1801a0992  jmp     loc_1801A08F5
```
