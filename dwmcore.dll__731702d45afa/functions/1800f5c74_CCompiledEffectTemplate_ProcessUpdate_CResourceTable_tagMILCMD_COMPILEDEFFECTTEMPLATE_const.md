# CCompiledEffectTemplate::ProcessUpdate(CResourceTable *,tagMILCMD_COMPILEDEFFECTTEMPLATE const *)

- ea: `0x1800f5c74`
- end: `0x1800f5e50`
- name: `?ProcessUpdate@CCompiledEffectTemplate@@QEAAJPEAVCResourceTable@@PEBUtagMILCMD_COMPILEDEFFECTTEMPLATE@@@Z`
- size: `476`
- prototype: `__int64 __fastcall(CCompiledEffectTemplate *__hidden this, struct CResourceTable *, const struct tagMILCMD_COMPILEDEFFECTTEMPLATE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180192cd0`

## callees

- `0x180044150`
- `0x180050270`
- `0x180055f50`
- `0x1800f5580`
- `0x1800f5c74`
- `0x1800f5e60`
- `0x1800f5f88`
- `0x1800f6780`
- `0x18012ca38`
- `0x1801bc4a8`
- `0x18020a2d8`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800f5cd7`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800f5cd7`
- `CoreMessaging!CoreUICallSend` at `0x1800f5ddd`
- `CoreMessaging!CoreUICallSend` at `0x1800f5ddd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f5e0e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f5e0e`
- `wuceffects!DeserializeEffectDescription` at `0x1800f5ce7`
- `wuceffects!DeserializeEffectDescription` at `0x1800f5ce7`

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
  __int64 v14; // rdx
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
      v15 = ((__int64 (__fastcall *)(__int64, _QWORD *, __int64, __int64, unsigned int, char *, int, __int64))CoreUICallSend)(
              v16,
              v19,
              2,
              5,
              v18,
              byte_1802D26CD,
              v17,
              v14);
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
0x1800f5c74  mov     [rsp-28h+arg_8], rbx
0x1800f5c79  push    rbp
0x1800f5c7a  push    rsi
0x1800f5c7b  push    rdi
0x1800f5c7c  push    r14
0x1800f5c7e  push    r15
0x1800f5c80  mov     rbp, rsp
0x1800f5c83  sub     rsp, 50h
0x1800f5c87  xor     esi, esi
0x1800f5c89  mov     rbx, r8
0x1800f5c8c  mov     rax, rdx
0x1800f5c8f  mov     rdi, rcx
0x1800f5c92  mov     [rbp+arg_0], rsi
0x1800f5c96  cmp     [rcx+50h], rsi
0x1800f5c9a  jnz     loc_1800F5D84
0x1800f5ca0  mov     edx, [rbx+8]
0x1800f5ca3  mov     r8d, 85h
0x1800f5ca9  mov     rcx, rax
0x1800f5cac  call    ?GetResource@CResourceTable@@QEBAPEAVCResource@@IW4MIL_RESOURCE_TYPE@@@Z; CResourceTable::GetResource(uint,MIL_RESOURCE_TYPE)
0x1800f5cb1  test    rax, rax
0x1800f5cb4  jz      loc_1800F5D90
0x1800f5cba  mov     r8d, [rbx+10h]; unsigned __int64
0x1800f5cbe  mov     rcx, rax; this
0x1800f5cc1  mov     edx, [rbx+0Ch]; unsigned __int64
0x1800f5cc4  call    ?ResolveAllocation@CSharedSectionBase@@QEAAPEBX_K0@Z; CSharedSectionBase::ResolveAllocation(unsigned __int64,unsigned __int64)
0x1800f5cc9  mov     r14, rax
0x1800f5ccc  test    rax, rax
0x1800f5ccf  jz      loc_1800F5D6E
0x1800f5cd5  xor     ecx, ecx
0x1800f5cd7  call    cs:__imp_SetRestrictedErrorInfo
0x1800f5cdd  mov     edx, [rbx+10h]
0x1800f5ce0  lea     r8, [rbp+arg_0]
0x1800f5ce4  mov     rcx, r14
0x1800f5ce7  call    cs:__imp_DeserializeEffectDescription
0x1800f5ced  mov     esi, eax
0x1800f5cef  test    eax, eax
0x1800f5cf1  js      loc_1800F5E44
0x1800f5cf7  mov     rcx, [rdi+38h]; this
0x1800f5cfb  call    ?IncreasePendingEffectCompilations@CChannelContext@@QEAAXXZ; CChannelContext::IncreasePendingEffectCompilations(void)
0x1800f5d00  mov     rcx, [rdi+18h]
0x1800f5d04  lea     r9, [rdi+50h]; struct CEffectCompilationTask **
0x1800f5d08  mov     r8, [rbp+arg_0]; struct Windows::UI::Composition::IEffectDescription *
0x1800f5d0c  mov     rdx, rdi; struct CCompiledEffectTemplate *
0x1800f5d0f  mov     rcx, [rcx+288h]; this
0x1800f5d16  call    ?BeginCompile@CEffectCompilationService@@QEAAJPEAVCCompiledEffectTemplate@@PEAUIEffectDescription@Composition@UI@Windows@@PEAPEAVCEffectCompilationTask@@@Z; CEffectCompilationService::BeginCompile(CCompiledEffectTemplate *,Windows::UI::Composition::IEffectDescription *,CEffectCompilationTask * *)
0x1800f5d1b  mov     ebx, eax
0x1800f5d1d  test    eax, eax
0x1800f5d1f  js      loc_1800F5E20
0x1800f5d25  mov     rax, [rdi]
0x1800f5d28  xor     r8d, r8d
0x1800f5d2b  xor     edx, edx
0x1800f5d2d  mov     rcx, rdi
0x1800f5d30  mov     rax, [rax+50h]
0x1800f5d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5d39  xor     ebx, ebx
0x1800f5d3b  mov     rcx, [rbp+arg_0]
0x1800f5d3f  test    rcx, rcx
0x1800f5d42  jz      short loc_1800F5D58
0x1800f5d44  mov     [rbp+arg_0], 0
0x1800f5d4c  mov     rdx, [rcx]
0x1800f5d4f  mov     rax, [rdx+8]
0x1800f5d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5d58  mov     eax, ebx
0x1800f5d5a  mov     rbx, [rsp+50h+arg_8]
0x1800f5d62  add     rsp, 50h
0x1800f5d66  pop     r15
0x1800f5d68  pop     r14
0x1800f5d6a  pop     rdi
0x1800f5d6b  pop     rsi
0x1800f5d6c  pop     rbp
0x1800f5d6d  retn
0x1800f5d6e  mov     ebx, 8007000Eh
0x1800f5d73  mov     eax, 31h ; '1'
0x1800f5d78  xor     edx, edx
0x1800f5d7a  xor     r8d, r8d
0x1800f5d7d  xor     ecx, ecx
0x1800f5d7f  jmp     loc_1802A3503
0x1800f5d84  mov     ebx, 88980402h
0x1800f5d89  mov     eax, 24h ; '$'
0x1800f5d8e  jmp     short loc_1800F5D78
0x1800f5d90  mov     ebx, 88980403h
0x1800f5d95  mov     eax, 2Ch ; ','
0x1800f5d9a  jmp     short loc_1800F5D78
0x1800f5d9c  mov     rcx, rdi; this
0x1800f5d9f  call    ?GetChannelCallbackId@CNotificationResource@@IEBAIXZ; CNotificationResource::GetChannelCallbackId(void)
0x1800f5da4  mov     ecx, eax
0x1800f5da6  mov     r9d, r15d
0x1800f5da9  mov     eax, [rdi+48h]
0x1800f5dac  mov     r8d, 2
0x1800f5db2  mov     [rsp+50h+var_18], rdx
0x1800f5db7  lea     rdx, [rbp+var_10]
0x1800f5dbb  mov     [rbp+var_8], rax
0x1800f5dbf  lea     rax, byte_1802D26CD
0x1800f5dc6  mov     [rbp+var_10], rcx
0x1800f5dca  mov     rcx, r14
0x1800f5dcd  mov     [rsp+50h+var_20], ebx
0x1800f5dd1  mov     [rsp+50h+var_28], rax
0x1800f5dd6  mov     word ptr [rsp+50h+var_30], 1
0x1800f5ddd  call    cs:__imp_CoreUICallSend
0x1800f5de3  mov     ebx, eax
0x1800f5de5  test    eax, eax
0x1800f5de7  jns     short loc_1800F5E0A
0x1800f5de9  xor     edx, edx; int *
0x1800f5deb  mov     [rsp+50h+var_28], 0; void *
0x1800f5df4  mov     r9d, eax; int
0x1800f5df7  mov     [rsp+50h+var_30], 67h ; 'g'; unsigned int
0x1800f5dff  xor     r8d, r8d; unsigned int
0x1800f5e02  lea     ecx, [rdx+14h]; unsigned int
0x1800f5e05  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800f5e0a  mov     rcx, [rbp+bstrString]; bstrString
0x1800f5e0e  call    cs:__imp_SysFreeString
0x1800f5e14  xor     eax, eax
0x1800f5e16  test    esi, esi
0x1800f5e18  cmovs   ebx, eax
0x1800f5e1b  jmp     loc_1800F5D3B
0x1800f5e20  mov     rcx, [rdi+38h]; this
0x1800f5e24  call    ?DecreasePendingEffectCompilations@CChannelContext@@QEAAXXZ; CChannelContext::DecreasePendingEffectCompilations(void)
0x1800f5e29  mov     rcx, [rdi+18h]
0x1800f5e2d  xor     r8d, r8d
0x1800f5e30  mov     edx, 1000000h
0x1800f5e35  call    ?ScheduleCompositionPass@CComposition@@QEAAXW4CompositionReason@@K@Z; CComposition::ScheduleCompositionPass(CompositionReason,ulong)
0x1800f5e3a  mov     eax, 46h ; 'F'
0x1800f5e3f  jmp     loc_1802A34FC
0x1800f5e44  mov     ebx, eax
0x1800f5e46  mov     eax, 37h ; '7'
0x1800f5e4b  jmp     loc_1802A34FC
0x1802a34fc  xor     edx, edx; int *
0x1802a34fe  xor     r8d, r8d; unsigned int
0x1802a3501  mov     ecx, edx
0x1802a3503  mov     [rsp+50h+var_28], rcx; void *
0x1802a3508  mov     r9d, ebx; int
0x1802a350b  mov     ecx, 14h; unsigned int
0x1802a3510  mov     [rsp+50h+var_30], eax; unsigned int
0x1802a3514  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1802a3519  mov     rcx, rdi; this
0x1802a351c  call    ?ShouldNotify@CNotificationResource@@IEBA_NXZ; CNotificationResource::ShouldNotify(void)
0x1802a3521  test    al, al
0x1802a3523  jz      loc_1800F5E14
0x1802a3529  mov     rax, [rdi+18h]
0x1802a352d  mov     r15d, 5
0x1802a3533  mov     edx, r15d
0x1802a3536  mov     rcx, [rax+18F0h]
0x1802a353d  mov     rax, [rcx]
0x1802a3540  mov     rax, [rax+48h]
0x1802a3544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802a3549  mov     r14, rax
0x1802a354c  test    rax, rax
0x1802a354f  jz      loc_1800F5E14
0x1802a3555  xor     edx, edx
0x1802a3557  mov     ebx, 80004005h
0x1802a355c  mov     [rbp+bstrString], rdx
0x1802a3560  test    esi, esi
0x1802a3562  jns     loc_1800F5D9C
0x1802a3568  lea     rcx, [rbp+bstrString]; unsigned __int16 **
0x1802a356c  mov     ebx, esi
0x1802a356e  call    ?GetRestrictedErrorDescription@CEffectCompilationTask@@SAJPEAPEAG@Z; CEffectCompilationTask::GetRestrictedErrorDescription(ushort * *)
0x1802a3573  mov     rdx, [rbp+bstrString]
0x1802a3577  jmp     loc_1800F5D9C
```
