# CCompiledEffectTemplate::ProcessUpdate(CResourceTable *,tagMILCMD_COMPILEDEFFECTTEMPLATE const *)

- ea: `0x1800f83f4`
- end: `0x1800f85d0`
- name: `?ProcessUpdate@CCompiledEffectTemplate@@QEAAJPEAVCResourceTable@@PEBUtagMILCMD_COMPILEDEFFECTTEMPLATE@@@Z`
- size: `476`
- prototype: `__int64 __fastcall(CCompiledEffectTemplate *__hidden this, struct CResourceTable *, const struct tagMILCMD_COMPILEDEFFECTTEMPLATE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180191ca0`

## callees

- `0x180037eec`
- `0x180039620`
- `0x180042de0`
- `0x180048ac0`
- `0x18005224c`
- `0x1800f7d00`
- `0x1800f83f4`
- `0x1800f85e0`
- `0x1800f8708`
- `0x1800f8f00`
- `0x18020a2b8`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800f8457`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800f8457`
- `CoreMessaging!CoreUICallSend` at `0x1800f855d`
- `CoreMessaging!CoreUICallSend` at `0x1800f855d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f858e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f858e`
- `wuceffects!DeserializeEffectDescription` at `0x1800f8467`
- `wuceffects!DeserializeEffectDescription` at `0x1800f8467`

## pseudocode

```c
__int64 __fastcall CCompiledEffectTemplate::ProcessUpdate(
        CChannelContext **this,
        struct CResourceTable *a2,
        const struct tagMILCMD_COMPILEDEFFECTTEMPLATE *a3)
{
  int v3; // esi
  CSharedSectionBase *Resource; // rax
  const void *v7; // r14
  int v8; // eax
  int v9; // ebx
  struct Windows::UI::Composition::IEffectDescription *v10; // rcx
  unsigned int v12; // eax
  unsigned int ChannelCallbackId; // eax
  int v14; // edx
  int v15; // eax
  __int64 v16; // r14
  int v17; // ebx
  unsigned int v18; // [rsp+20h] [rbp-30h]
  _QWORD v19[2]; // [rsp+40h] [rbp-10h] BYREF
  struct Windows::UI::Composition::IEffectDescription *v20; // [rsp+80h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp+48h] BYREF

  v3 = 0;
  v20 = 0;
  if ( this[10] )
  {
    v9 = -2003303422;
    v12 = 36;
  }
  else
  {
    Resource = (CSharedSectionBase *)CResourceTable::GetResource(a2, *((unsigned int *)a3 + 2), 133);
    if ( Resource )
    {
      v7 = CSharedSectionBase::ResolveAllocation(Resource, *((unsigned int *)a3 + 3), *((unsigned int *)a3 + 4));
      if ( v7 )
      {
        SetRestrictedErrorInfo(0);
        v8 = DeserializeEffectDescription(v7, *((unsigned int *)a3 + 4), &v20);
        v3 = v8;
        if ( v8 < 0 )
        {
          v9 = v8;
          v12 = 55;
        }
        else
        {
          CChannelContext::IncreasePendingEffectCompilations(this[7]);
          v9 = CEffectCompilationService::BeginCompile(
                 *((CEffectCompilationService **)this[3] + 81),
                 (struct CCompiledEffectTemplate *)this,
                 v20,
                 this + 10);
          if ( v9 >= 0 )
          {
            (*((void (__fastcall **)(CChannelContext **, _QWORD, _QWORD))*this + 10))(this, 0, 0);
            v9 = 0;
            goto LABEL_7;
          }
          CChannelContext::DecreasePendingEffectCompilations(this[7]);
          CComposition::ScheduleCompositionPass(this[3], 0x1000000, 0);
          v12 = 70;
        }
      }
      else
      {
        v9 = -2147024882;
        v12 = 49;
      }
    }
    else
    {
      v9 = -2003303421;
      v12 = 44;
    }
  }
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v9, v12, 0);
  if ( CNotificationResource::ShouldNotify((CNotificationResource *)this) )
  {
    v16 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this[3] + 798) + 72LL))(
            *((_QWORD *)this[3] + 798),
            5);
    if ( v16 )
    {
      v17 = -2147467259;
      bstrString = 0;
      if ( v3 < 0 )
      {
        v17 = v3;
        CEffectCompilationTask::GetRestrictedErrorDescription(&bstrString);
      }
      ChannelCallbackId = CNotificationResource::GetChannelCallbackId((CNotificationResource *)this);
      v19[1] = *((unsigned int *)this + 18);
      v19[0] = ChannelCallbackId;
      LOWORD(v18) = 1;
      v15 = CoreUICallSend(v16, v19, 2, 5, v18, byte_1802D4E7D, v17, v14);
      v9 = v15;
      if ( v15 < 0 )
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v15, 0x67u, 0);
      SysFreeString(bstrString);
    }
  }
  if ( v3 < 0 )
    v9 = 0;
LABEL_7:
  v10 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(struct Windows::UI::Composition::IEffectDescription *))(*(_QWORD *)v10 + 8LL))(v10);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800f83f4  mov     [rsp-28h+arg_8], rbx
0x1800f83f9  push    rbp
0x1800f83fa  push    rsi
0x1800f83fb  push    rdi
0x1800f83fc  push    r14
0x1800f83fe  push    r15
0x1800f8400  mov     rbp, rsp
0x1800f8403  sub     rsp, 50h
0x1800f8407  xor     esi, esi
0x1800f8409  mov     rbx, r8
0x1800f840c  mov     rax, rdx
0x1800f840f  mov     rdi, rcx
0x1800f8412  mov     [rbp+arg_0], rsi
0x1800f8416  cmp     [rcx+50h], rsi
0x1800f841a  jnz     loc_1800F8504
0x1800f8420  mov     edx, [rbx+8]
0x1800f8423  mov     r8d, 85h
0x1800f8429  mov     rcx, rax
0x1800f842c  call    ?GetResource@CResourceTable@@QEBAPEAVCResource@@IW4MIL_RESOURCE_TYPE@@@Z; CResourceTable::GetResource(uint,MIL_RESOURCE_TYPE)
0x1800f8431  test    rax, rax
0x1800f8434  jz      loc_1800F8510
0x1800f843a  mov     r8d, [rbx+10h]; unsigned __int64
0x1800f843e  mov     rcx, rax; this
0x1800f8441  mov     edx, [rbx+0Ch]; unsigned __int64
0x1800f8444  call    ?ResolveAllocation@CSharedSectionBase@@QEAAPEBX_K0@Z; CSharedSectionBase::ResolveAllocation(unsigned __int64,unsigned __int64)
0x1800f8449  mov     r14, rax
0x1800f844c  test    rax, rax
0x1800f844f  jz      loc_1800F84EE
0x1800f8455  xor     ecx, ecx
0x1800f8457  call    cs:__imp_SetRestrictedErrorInfo
0x1800f845d  mov     edx, [rbx+10h]
0x1800f8460  lea     r8, [rbp+arg_0]
0x1800f8464  mov     rcx, r14
0x1800f8467  call    cs:__imp_DeserializeEffectDescription
0x1800f846d  mov     esi, eax
0x1800f846f  test    eax, eax
0x1800f8471  js      loc_1800F85C4
0x1800f8477  mov     rcx, [rdi+38h]; this
0x1800f847b  call    ?IncreasePendingEffectCompilations@CChannelContext@@QEAAXXZ; CChannelContext::IncreasePendingEffectCompilations(void)
0x1800f8480  mov     rcx, [rdi+18h]
0x1800f8484  lea     r9, [rdi+50h]; struct CEffectCompilationTask **
0x1800f8488  mov     r8, [rbp+arg_0]; struct Windows::UI::Composition::IEffectDescription *
0x1800f848c  mov     rdx, rdi; struct CCompiledEffectTemplate *
0x1800f848f  mov     rcx, [rcx+288h]; this
0x1800f8496  call    ?BeginCompile@CEffectCompilationService@@QEAAJPEAVCCompiledEffectTemplate@@PEAUIEffectDescription@Composition@UI@Windows@@PEAPEAVCEffectCompilationTask@@@Z; CEffectCompilationService::BeginCompile(CCompiledEffectTemplate *,Windows::UI::Composition::IEffectDescription *,CEffectCompilationTask * *)
0x1800f849b  mov     ebx, eax
0x1800f849d  test    eax, eax
0x1800f849f  js      loc_1800F85A0
0x1800f84a5  mov     rax, [rdi]
0x1800f84a8  xor     r8d, r8d
0x1800f84ab  xor     edx, edx
0x1800f84ad  mov     rcx, rdi
0x1800f84b0  mov     rax, [rax+50h]
0x1800f84b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f84b9  xor     ebx, ebx
0x1800f84bb  mov     rcx, [rbp+arg_0]
0x1800f84bf  test    rcx, rcx
0x1800f84c2  jz      short loc_1800F84D8
0x1800f84c4  mov     [rbp+arg_0], 0
0x1800f84cc  mov     rdx, [rcx]
0x1800f84cf  mov     rax, [rdx+8]
0x1800f84d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f84d8  mov     eax, ebx
0x1800f84da  mov     rbx, [rsp+50h+arg_8]
0x1800f84e2  add     rsp, 50h
0x1800f84e6  pop     r15
0x1800f84e8  pop     r14
0x1800f84ea  pop     rdi
0x1800f84eb  pop     rsi
0x1800f84ec  pop     rbp
0x1800f84ed  retn
0x1800f84ee  mov     ebx, 8007000Eh
0x1800f84f3  mov     eax, 31h ; '1'
0x1800f84f8  xor     edx, edx
0x1800f84fa  xor     r8d, r8d
0x1800f84fd  xor     ecx, ecx
0x1800f84ff  jmp     loc_1802A4925
0x1800f8504  mov     ebx, 88980402h
0x1800f8509  mov     eax, 24h ; '$'
0x1800f850e  jmp     short loc_1800F84F8
0x1800f8510  mov     ebx, 88980403h
0x1800f8515  mov     eax, 2Ch ; ','
0x1800f851a  jmp     short loc_1800F84F8
0x1800f851c  mov     rcx, rdi; this
0x1800f851f  call    ?GetChannelCallbackId@CNotificationResource@@IEBAIXZ; CNotificationResource::GetChannelCallbackId(void)
0x1800f8524  mov     ecx, eax
0x1800f8526  mov     r9d, r15d
0x1800f8529  mov     eax, [rdi+48h]
0x1800f852c  mov     r8d, 2
0x1800f8532  mov     [rsp+50h+var_18], rdx
0x1800f8537  lea     rdx, [rbp+var_10]
0x1800f853b  mov     [rbp+var_8], rax
0x1800f853f  lea     rax, byte_1802D4E7D
0x1800f8546  mov     [rbp+var_10], rcx
0x1800f854a  mov     rcx, r14
0x1800f854d  mov     [rsp+50h+var_20], ebx
0x1800f8551  mov     [rsp+50h+var_28], rax
0x1800f8556  mov     word ptr [rsp+50h+var_30], 1
0x1800f855d  call    cs:__imp_CoreUICallSend
0x1800f8563  mov     ebx, eax
0x1800f8565  test    eax, eax
0x1800f8567  jns     short loc_1800F858A
0x1800f8569  xor     edx, edx; int *
0x1800f856b  mov     [rsp+50h+var_28], 0; void *
0x1800f8574  mov     r9d, eax; int
0x1800f8577  mov     [rsp+50h+var_30], 67h ; 'g'; unsigned int
0x1800f857f  xor     r8d, r8d; unsigned int
0x1800f8582  lea     ecx, [rdx+14h]; unsigned int
0x1800f8585  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800f858a  mov     rcx, [rbp+bstrString]; bstrString
0x1800f858e  call    cs:__imp_SysFreeString
0x1800f8594  xor     eax, eax
0x1800f8596  test    esi, esi
0x1800f8598  cmovs   ebx, eax
0x1800f859b  jmp     loc_1800F84BB
0x1800f85a0  mov     rcx, [rdi+38h]; this
0x1800f85a4  call    ?DecreasePendingEffectCompilations@CChannelContext@@QEAAXXZ; CChannelContext::DecreasePendingEffectCompilations(void)
0x1800f85a9  mov     rcx, [rdi+18h]
0x1800f85ad  xor     r8d, r8d
0x1800f85b0  mov     edx, 1000000h
0x1800f85b5  call    ?ScheduleCompositionPass@CComposition@@QEAAXW4CompositionReason@@K@Z; CComposition::ScheduleCompositionPass(CompositionReason,ulong)
0x1800f85ba  mov     eax, 46h ; 'F'
0x1800f85bf  jmp     loc_1802A491E
0x1800f85c4  mov     ebx, eax
0x1800f85c6  mov     eax, 37h ; '7'
0x1800f85cb  jmp     loc_1802A491E
0x1802a491e  xor     edx, edx; int *
0x1802a4920  xor     r8d, r8d; unsigned int
0x1802a4923  mov     ecx, edx
0x1802a4925  mov     [rsp+50h+var_28], rcx; void *
0x1802a492a  mov     r9d, ebx; int
0x1802a492d  mov     ecx, 14h; unsigned int
0x1802a4932  mov     [rsp+50h+var_30], eax; unsigned int
0x1802a4936  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1802a493b  mov     rcx, rdi; this
0x1802a493e  call    ?ShouldNotify@CNotificationResource@@IEBA_NXZ; CNotificationResource::ShouldNotify(void)
0x1802a4943  test    al, al
0x1802a4945  jz      loc_1800F8594
0x1802a494b  mov     rax, [rdi+18h]
0x1802a494f  mov     r15d, 5
0x1802a4955  mov     edx, r15d
0x1802a4958  mov     rcx, [rax+18F0h]
0x1802a495f  mov     rax, [rcx]
0x1802a4962  mov     rax, [rax+48h]
0x1802a4966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802a496b  mov     r14, rax
0x1802a496e  test    rax, rax
0x1802a4971  jz      loc_1800F8594
0x1802a4977  xor     edx, edx
0x1802a4979  mov     ebx, 80004005h
0x1802a497e  mov     [rbp+bstrString], rdx
0x1802a4982  test    esi, esi
0x1802a4984  jns     loc_1800F851C
0x1802a498a  lea     rcx, [rbp+bstrString]; unsigned __int16 **
0x1802a498e  mov     ebx, esi
0x1802a4990  call    ?GetRestrictedErrorDescription@CEffectCompilationTask@@SAJPEAPEAG@Z; CEffectCompilationTask::GetRestrictedErrorDescription(ushort * *)
0x1802a4995  mov     rdx, [rbp+bstrString]
0x1802a4999  jmp     loc_1800F851C
```
