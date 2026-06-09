# EndpointDlp::DlpPolicy::GetDlpQuarantineConfiguration(DlpQuarantineConfiguration *)

- ea: `0x18002b500`
- end: `0x18002b89d`
- name: `?GetDlpQuarantineConfiguration@DlpPolicy@EndpointDlp@@QEAAJPEAUDlpQuarantineConfiguration@@@Z`
- size: `925`
- prototype: `__int64 __fastcall(EndpointDlp::DlpPolicy *__hidden this, struct DlpQuarantineConfiguration *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18002a83c`

## callees

- `0x1800058a4`
- `0x18002b500`
- `0x1800301a0`
- `0x1800ad914`
- `0x1800cc08c`
- `0x18010cb40`
- `0x1801b83c8`
- `0x1801b8420`
- `0x18023a6d0`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18002b79f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002b7fc`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002b79f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002b7fc`
- `ADVAPI32!EventWriteTransfer` at `0x18002b6ef`
- `ADVAPI32!EventWriteTransfer` at `0x18002b779`
- `ADVAPI32!EventWriteTransfer` at `0x18002b6ef`
- `ADVAPI32!EventWriteTransfer` at `0x18002b779`

## string_xrefs

- `0x18002b66e`: `Configured quarantine path is too long to fill in the input buffer`
- `0x18002b6fa`: `Configured quarantine replacement text is too long to fill in the input buffer`
- `0x18002b863`: `Invalid argument for GetDlpQuarantineConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EndpointDlp::DlpPolicy::GetDlpQuarantineConfiguration(EndpointDlp::DlpPolicy *this, void **a2)
{
  char v4; // si
  __int64 v5; // r8
  _QWORD *v6; // rdx
  __int64 v7; // r8
  _QWORD *v8; // rdx
  _QWORD *v10; // rax
  _DWORD *v11; // rcx
  _QWORD *v12; // rax
  _DWORD *v13; // rcx
  __int64 *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  struct EndpointDlp::TraceLoggingProvider *v20; // rax
  int v21; // r8d
  int v22; // r9d
  _DWORD *v23; // rcx
  RTL_SRWLOCK *v24; // [rsp+30h] [rbp-50h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-38h] BYREF
  char *v27; // [rsp+58h] [rbp-28h]
  int v28; // [rsp+60h] [rbp-20h]
  int v29; // [rsp+64h] [rbp-1Ch]
  const wchar_t *v30; // [rsp+68h] [rbp-18h]
  __int64 v31; // [rsp+70h] [rbp-10h]

  v4 = 0;
  if ( a2 )
  {
    v5 = *((_QWORD *)this + 16);
    if ( *((unsigned int *)a2 + 4) < (unsigned __int64)(v5 + 1) )
    {
      v10 = (_QWORD *)EndpointDlp::TraceLoggingProvider::s_instance;
      if ( !EndpointDlp::TraceLoggingProvider::s_instance )
      {
        AcquireSRWLockExclusive(&EndpointDlp::TraceLoggingProvider::s_instanceLock);
        *(_QWORD *)&EventDescriptor.Id = &EndpointDlp::TraceLoggingProvider::s_instanceLock;
        if ( !EndpointDlp::TraceLoggingProvider::s_instance )
        {
          v14 = (__int64 *)std::make_unique<EndpointDlp::TraceLoggingProvider,,0>(&v24);
          v15 = *v14;
          *v14 = 0;
          v16 = EndpointDlp::TraceLoggingProvider::s_instance;
          EndpointDlp::TraceLoggingProvider::s_instance = v15;
          if ( v16 )
            std::default_delete<EndpointDlp::TraceLoggingProvider>::operator()();
          std::unique_ptr<EndpointDlp::TraceLoggingProvider>::~unique_ptr<EndpointDlp::TraceLoggingProvider>(&v24);
        }
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&EventDescriptor);
        v10 = (_QWORD *)EndpointDlp::TraceLoggingProvider::s_instance;
      }
      v11 = (_DWORD *)*v10;
      if ( *(_DWORD *)*v10 > 5u )
      {
        v30 = L"Configured quarantine path is too long to fill in the input buffer";
        v31 = 134;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 5;
        EventDescriptor.Keyword = 0;
        UserData.Ptr = *((_QWORD *)v11 + 1);
        UserData.Size = *(unsigned __int16 *)UserData.Ptr;
        UserData.Reserved = 2;
        v27 = &byte_1802C8F0F;
        v28 = 24;
        v29 = 1;
        LODWORD(v24) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(*((_QWORD *)v11 + 4), &EventDescriptor, 0, 0, 3u, &UserData);
      }
      v4 = 1;
    }
    else
    {
      v6 = (_QWORD *)((char *)this + 112);
      if ( *((_QWORD *)this + 17) > 7u )
        v6 = (_QWORD *)*v6;
      memmove(*a2, v6, 2 * v5);
      *((_WORD *)*a2 + *((_QWORD *)this + 16)) = 0;
    }
    *((_DWORD *)a2 + 4) = *((_DWORD *)this + 32) + 1;
    v7 = *((_QWORD *)this + 20);
    if ( *((unsigned int *)a2 + 5) < (unsigned __int64)(v7 + 1) )
    {
      v12 = (_QWORD *)EndpointDlp::TraceLoggingProvider::s_instance;
      if ( !EndpointDlp::TraceLoggingProvider::s_instance )
      {
        AcquireSRWLockExclusive(&EndpointDlp::TraceLoggingProvider::s_instanceLock);
        v24 = &EndpointDlp::TraceLoggingProvider::s_instanceLock;
        if ( !EndpointDlp::TraceLoggingProvider::s_instance )
        {
          v17 = (__int64 *)std::make_unique<EndpointDlp::TraceLoggingProvider,,0>(&EventDescriptor);
          v18 = *v17;
          *v17 = 0;
          v19 = EndpointDlp::TraceLoggingProvider::s_instance;
          EndpointDlp::TraceLoggingProvider::s_instance = v18;
          if ( v19 )
            std::default_delete<EndpointDlp::TraceLoggingProvider>::operator()();
          std::unique_ptr<EndpointDlp::TraceLoggingProvider>::~unique_ptr<EndpointDlp::TraceLoggingProvider>(&EventDescriptor);
        }
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v24);
        v12 = (_QWORD *)EndpointDlp::TraceLoggingProvider::s_instance;
      }
      v13 = (_DWORD *)*v12;
      if ( *(_DWORD *)*v12 > 5u )
      {
        v30 = L"Configured quarantine replacement text is too long to fill in the input buffer";
        v31 = 158;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 5;
        EventDescriptor.Keyword = 0;
        UserData.Ptr = *((_QWORD *)v13 + 1);
        UserData.Size = *(unsigned __int16 *)UserData.Ptr;
        UserData.Reserved = 2;
        v27 = byte_1802C8D55;
        v28 = 24;
        v29 = 1;
        LODWORD(v24) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(*((_QWORD *)v13 + 4), &EventDescriptor, 0, 0, 3u, &UserData);
      }
      *((_DWORD *)a2 + 5) = *((_DWORD *)this + 40) + 1;
      return 2147942522LL;
    }
    v8 = (_QWORD *)((char *)this + 144);
    if ( *((_QWORD *)this + 21) > 7u )
      v8 = (_QWORD *)*v8;
    memmove(a2[1], v8, 2 * v7);
    *((_WORD *)a2[1] + *((_QWORD *)this + 20)) = 0;
    *((_DWORD *)a2 + 5) = *((_DWORD *)this + 40) + 1;
    if ( v4 )
      return 2147942522LL;
    *((_BYTE *)a2 + 24) = *((_BYTE *)this + 104);
    *((_BYTE *)a2 + 25) = *((_BYTE *)this + 176);
    return 0;
  }
  else
  {
    v20 = EndpointDlp::TraceLoggingProvider::Instance();
    v23 = *(_DWORD **)v20;
    if ( **(_DWORD **)v20 > 2u )
    {
      *(_QWORD *)&EventDescriptor.Id = L"Invalid argument for GetDlpQuarantineConfiguration";
      LODWORD(v24) = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        (_DWORD)v23,
        (unsigned int)&word_1802C8F96,
        v21,
        v22,
        (__int64)&v24,
        (__int64)&EventDescriptor);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18002b500  mov     [rsp-38h+arg_10], rbx
0x18002b505  push    rbp
0x18002b506  push    rsi
0x18002b507  push    rdi
0x18002b508  push    r12
0x18002b50a  push    r13
0x18002b50c  push    r14
0x18002b50e  push    r15
0x18002b510  mov     rbp, rsp
0x18002b513  sub     rsp, 80h
0x18002b51a  mov     rax, cs:__security_cookie
0x18002b521  xor     rax, rsp
0x18002b524  mov     [rbp+var_8], rax
0x18002b528  mov     rbx, rdx
0x18002b52b  mov     rdi, rcx
0x18002b52e  xor     sil, sil
0x18002b531  test    rdx, rdx
0x18002b534  jz      loc_18002B856
0x18002b53a  mov     r8, [rcx+80h]
0x18002b541  lea     rcx, [r8+1]
0x18002b545  mov     eax, [rdx+10h]
0x18002b548  lea     r13, ?s_instanceLock@TraceLoggingProvider@EndpointDlp@@0Vsrwlock@wil@@A; wil::srwlock EndpointDlp::TraceLoggingProvider::s_instanceLock
0x18002b54f  lea     r15, _TraceLoggingMetadataEnd
0x18002b556  lea     r12, _TraceLoggingMetadata
0x18002b55d  cmp     rax, rcx
0x18002b560  jb      loc_18002B622
0x18002b566  lea     rdx, [rdi+70h]
0x18002b56a  cmp     qword ptr [rdx+18h], 7
0x18002b56f  jbe     short loc_18002B574
0x18002b571  mov     rdx, [rdx]; Src
0x18002b574  add     r8, r8; Size
0x18002b577  mov     rcx, [rbx]; void *
0x18002b57a  call    memmove
0x18002b57f  mov     rcx, [rdi+80h]
0x18002b586  mov     rax, [rbx]
0x18002b589  xor     r14d, r14d
0x18002b58c  mov     [rax+rcx*2], r14w
0x18002b591  mov     eax, [rdi+80h]
0x18002b597  inc     eax
0x18002b599  mov     [rbx+10h], eax
0x18002b59c  mov     r8, [rdi+0A0h]
0x18002b5a3  lea     rcx, [r8+1]
0x18002b5a7  mov     eax, [rbx+14h]
0x18002b5aa  cmp     rax, rcx
0x18002b5ad  jb      loc_18002B645
0x18002b5b3  lea     rdx, [rdi+90h]; Src
0x18002b5ba  mov     rcx, [rbx+8]; void *
0x18002b5be  cmp     qword ptr [rdx+18h], 7
0x18002b5c3  ja      short loc_18002B61D
0x18002b5c5  add     r8, r8; Size
0x18002b5c8  call    memmove
0x18002b5cd  mov     rcx, [rdi+0A0h]
0x18002b5d4  mov     rax, [rbx+8]
0x18002b5d8  mov     [rax+rcx*2], r14w
0x18002b5dd  mov     eax, [rdi+0A0h]
0x18002b5e3  inc     eax
0x18002b5e5  mov     [rbx+14h], eax
0x18002b5e8  test    sil, sil
0x18002b5eb  jz      loc_18002B784
0x18002b5f1  mov     eax, 8007007Ah
0x18002b5f6  mov     rcx, [rbp+var_8]
0x18002b5fa  xor     rcx, rsp; StackCookie
0x18002b5fd  call    __security_check_cookie
0x18002b602  mov     rbx, [rsp+80h+arg_10]
0x18002b60a  add     rsp, 80h
0x18002b611  pop     r15
0x18002b613  pop     r14
0x18002b615  pop     r13
0x18002b617  pop     r12
0x18002b619  pop     rdi
0x18002b61a  pop     rsi
0x18002b61b  pop     rbp
0x18002b61c  retn
0x18002b61d  mov     rdx, [rdx]
0x18002b620  jmp     short loc_18002B5C5
0x18002b622  xor     r14d, r14d
0x18002b625  mov     rax, cs:?s_instance@TraceLoggingProvider@EndpointDlp@@0V?$unique_ptr@VTraceLoggingProvider@EndpointDlp@@U?$default_delete@VTraceLoggingProvider@EndpointDlp@@@std@@@std@@A; std::unique_ptr<EndpointDlp::TraceLoggingProvider> EndpointDlp::TraceLoggingProvider::s_instance
0x18002b62c  test    rax, rax
0x18002b62f  jz      loc_18002B79C
0x18002b635  mov     rcx, [rax]
0x18002b638  cmp     dword ptr [rcx], 5
0x18002b63b  ja      short loc_18002B66E
0x18002b63d  mov     sil, 1
0x18002b640  jmp     loc_18002B591
0x18002b645  mov     rax, cs:?s_instance@TraceLoggingProvider@EndpointDlp@@0V?$unique_ptr@VTraceLoggingProvider@EndpointDlp@@U?$default_delete@VTraceLoggingProvider@EndpointDlp@@@std@@@std@@A; std::unique_ptr<EndpointDlp::TraceLoggingProvider> EndpointDlp::TraceLoggingProvider::s_instance
0x18002b64c  test    rax, rax
0x18002b64f  jz      loc_18002B7F9
0x18002b655  mov     rcx, [rax]
0x18002b658  cmp     dword ptr [rcx], 5
0x18002b65b  ja      loc_18002B6FA
0x18002b661  mov     eax, [rdi+0A0h]
0x18002b667  inc     eax
0x18002b669  mov     [rbx+14h], eax
0x18002b66c  jmp     short loc_18002B5F1
0x18002b66e  lea     rax, aConfiguredQuar; "Configured quarantine path is too long "...
0x18002b675  mov     [rbp+var_18], rax
0x18002b679  mov     [rbp+var_10], 86h
0x18002b681  mov     dword ptr [rbp+EventDescriptor.Id], 0B000000h
0x18002b688  movzx   eax, cs:word_1802C8F05
0x18002b68f  mov     dword ptr [rbp+EventDescriptor.Level], eax
0x18002b692  mov     [rbp+EventDescriptor.Keyword], r14
0x18002b696  mov     rax, [rcx+8]
0x18002b69a  mov     [rbp+var_38.Ptr], rax
0x18002b69e  movzx   eax, word ptr [rax]
0x18002b6a1  mov     [rbp+var_38.Size], eax
0x18002b6a4  mov     dword ptr [rbp+var_38.0Ch], 2
0x18002b6ab  lea     rax, byte_1802C8F0F
0x18002b6b2  mov     [rbp+var_28], rax
0x18002b6b6  mov     [rbp+var_20], 18h
0x18002b6bd  mov     [rbp+var_1C], 1
0x18002b6c4  mov     rax, r15
0x18002b6c7  sub     eax, r12d
0x18002b6ca  mov     dword ptr [rbp+var_50], eax
0x18002b6cd  mov     eax, dword ptr [rbp+var_50]
0x18002b6d0  lea     rax, [rbp+var_38]
0x18002b6d4  mov     [rsp+80h+UserData], rax; UserData
0x18002b6d9  mov     [rsp+80h+UserDataCount], 3; UserDataCount
0x18002b6e1  xor     r9d, r9d; RelatedActivityId
0x18002b6e4  xor     r8d, r8d; ActivityId
0x18002b6e7  lea     rdx, [rbp+EventDescriptor]; EventDescriptor
0x18002b6eb  mov     rcx, [rcx+20h]; RegHandle
0x18002b6ef  call    cs:__imp_EventWriteTransfer
0x18002b6f5  jmp     loc_18002B63D
0x18002b6fa  lea     rax, aConfiguredQuar_0; "Configured quarantine replacement text "...
0x18002b701  mov     [rbp+var_18], rax
0x18002b705  mov     [rbp+var_10], 9Eh
0x18002b70d  mov     dword ptr [rbp+EventDescriptor.Id], 0B000000h
0x18002b714  movzx   eax, cs:word_1802C8D4B
0x18002b71b  mov     dword ptr [rbp+EventDescriptor.Level], eax
0x18002b71e  mov     [rbp+EventDescriptor.Keyword], r14
0x18002b722  mov     rax, [rcx+8]
0x18002b726  mov     [rbp+var_38.Ptr], rax
0x18002b72a  movzx   eax, word ptr [rax]
0x18002b72d  mov     [rbp+var_38.Size], eax
0x18002b730  mov     dword ptr [rbp+var_38.0Ch], 2
0x18002b737  lea     rax, byte_1802C8D55
0x18002b73e  mov     [rbp+var_28], rax
0x18002b742  mov     [rbp+var_20], 18h
0x18002b749  mov     [rbp+var_1C], 1
0x18002b750  sub     r15d, r12d
0x18002b753  mov     dword ptr [rbp+var_50], r15d
0x18002b757  mov     eax, dword ptr [rbp+var_50]
0x18002b75a  lea     rax, [rbp+var_38]
0x18002b75e  mov     [rsp+80h+UserData], rax; UserData
0x18002b763  mov     [rsp+80h+UserDataCount], 3; UserDataCount
0x18002b76b  xor     r9d, r9d; RelatedActivityId
0x18002b76e  xor     r8d, r8d; ActivityId
0x18002b771  lea     rdx, [rbp+EventDescriptor]; EventDescriptor
0x18002b775  mov     rcx, [rcx+20h]; RegHandle
0x18002b779  call    cs:__imp_EventWriteTransfer
0x18002b77f  jmp     loc_18002B661
0x18002b784  movzx   eax, byte ptr [rdi+68h]
0x18002b788  mov     [rbx+18h], al
0x18002b78b  movzx   eax, byte ptr [rdi+0B0h]
0x18002b792  mov     [rbx+19h], al
0x18002b795  xor     eax, eax
0x18002b797  jmp     loc_18002B5F6
0x18002b79c  mov     rcx, r13; SRWLock
0x18002b79f  call    cs:__imp_AcquireSRWLockExclusive
0x18002b7a5  mov     qword ptr [rbp+EventDescriptor.Id], r13
0x18002b7a9  cmp     cs:?s_instance@TraceLoggingProvider@EndpointDlp@@0V?$unique_ptr@VTraceLoggingProvider@EndpointDlp@@U?$default_delete@VTraceLoggingProvider@EndpointDlp@@@std@@@std@@A, 0; std::unique_ptr<EndpointDlp::TraceLoggingProvider> EndpointDlp::TraceLoggingProvider::s_instance
0x18002b7b1  jnz     short loc_18002B7E4
0x18002b7b3  lea     rcx, [rbp+var_50]
0x18002b7b7  call    ??$make_unique@VTraceLoggingProvider@EndpointDlp@@$$V$0A@@std@@YA?AV?$unique_ptr@VTraceLoggingProvider@EndpointDlp@@U?$default_delete@VTraceLoggingProvider@EndpointDlp@@@std@@@0@XZ; std::make_unique<EndpointDlp::TraceLoggingProvider,,0>(void)
0x18002b7bc  mov     rcx, [rax]
0x18002b7bf  mov     [rax], r14
0x18002b7c2  mov     rdx, cs:?s_instance@TraceLoggingProvider@EndpointDlp@@0V?$unique_ptr@VTraceLoggingProvider@EndpointDlp@@U?$default_delete@VTraceLoggingProvider@EndpointDlp@@@std@@@std@@A; std::unique_ptr<EndpointDlp::TraceLoggingProvider> EndpointDlp::TraceLoggingProvider::s_instance
0x18002b7c9  mov     cs:?s_instance@TraceLoggingProvider@EndpointDlp@@0V?$unique_ptr@VTraceLoggingProvider@EndpointDlp@@U?$default_delete@VTraceLoggingProvider@EndpointDlp@@@std@@@std@@A, rcx; std::unique_ptr<EndpointDlp::TraceLoggingProvider> EndpointDlp::TraceLoggingProvider::s_instance
0x18002b7d0  test    rdx, rdx
0x18002b7d3  jz      short loc_18002B7DA
0x18002b7d5  call    ??R?$default_delete@VTraceLoggingProvider@EndpointDlp@@@std@@QEBAXPEAVTraceLoggingProvider@EndpointDlp@@@Z; std::default_delete<EndpointDlp::TraceLoggingProvider>::operator()(EndpointDlp::TraceLoggingProvider *)
0x18002b7da  lea     rcx, [rbp+var_50]
0x18002b7de  call    ??1?$unique_ptr@VTraceLoggingProvider@EndpointDlp@@U?$default_delete@VTraceLoggingProvider@EndpointDlp@@@std@@@std@@QEAA@XZ; std::unique_ptr<EndpointDlp::TraceLoggingProvider>::~unique_ptr<EndpointDlp::TraceLoggingProvider>(void)
0x18002b7e3  nop
0x18002b7e4  lea     rcx, [rbp+EventDescriptor]
0x18002b7e8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002b7ed  mov     rax, cs:?s_instance@TraceLoggingProvider@EndpointDlp@@0V?$unique_ptr@VTraceLoggingProvider@EndpointDlp@@U?$default_delete@VTraceLoggingProvider@EndpointDlp@@@std@@@std@@A; std::unique_ptr<EndpointDlp::TraceLoggingProvider> EndpointDlp::TraceLoggingProvider::s_instance
0x18002b7f4  jmp     loc_18002B635
0x18002b7f9  mov     rcx, r13; SRWLock
0x18002b7fc  call    cs:__imp_AcquireSRWLockExclusive
0x18002b802  mov     [rbp+var_50], r13
0x18002b806  cmp     cs:?s_instance@TraceLoggingProvider@EndpointDlp@@0V?$unique_ptr@VTraceLoggingProvider@EndpointDlp@@U?$default_delete@VTraceLoggingProvider@EndpointDlp@@@std@@@std@@A, 0; std::unique_ptr<EndpointDlp::TraceLoggingProvider> EndpointDlp::TraceLoggingProvider::s_instance
0x18002b80e  jnz     short loc_18002B841
0x18002b810  lea     rcx, [rbp+EventDescriptor]
0x18002b814  call    ??$make_unique@VTraceLoggingProvider@EndpointDlp@@$$V$0A@@std@@YA?AV?$unique_ptr@VTraceLoggingProvider@EndpointDlp@@U?$default_delete@VTraceLoggingProvider@EndpointDlp@@@std@@@0@XZ; std::make_unique<EndpointDlp::TraceLoggingProvider,,0>(void)
0x18002b819  mov     rcx, [rax]
0x18002b81c  mov     [rax], r14
0x18002b81f  mov     rdx, cs:?s_instance@TraceLoggingProvider@EndpointDlp@@0V?$unique_ptr@VTraceLoggingProvider@EndpointDlp@@U?$default_delete@VTraceLoggingProvider@EndpointDlp@@@std@@@std@@A; std::unique_ptr<EndpointDlp::TraceLoggingProvider> EndpointDlp::TraceLoggingProvider::s_instance
0x18002b826  mov     cs:?s_instance@TraceLoggingProvider@EndpointDlp@@0V?$unique_ptr@VTraceLoggingProvider@EndpointDlp@@U?$default_delete@VTraceLoggingProvider@EndpointDlp@@@std@@@std@@A, rcx; std::unique_ptr<EndpointDlp::TraceLoggingProvider> EndpointDlp::TraceLoggingProvider::s_instance
0x18002b82d  test    rdx, rdx
0x18002b830  jz      short loc_18002B837
0x18002b832  call    ??R?$default_delete@VTraceLoggingProvider@EndpointDlp@@@std@@QEBAXPEAVTraceLoggingProvider@EndpointDlp@@@Z; std::default_delete<EndpointDlp::TraceLoggingProvider>::operator()(EndpointDlp::TraceLoggingProvider *)
0x18002b837  lea     rcx, [rbp+EventDescriptor]
0x18002b83b  call    ??1?$unique_ptr@VTraceLoggingProvider@EndpointDlp@@U?$default_delete@VTraceLoggingProvider@EndpointDlp@@@std@@@std@@QEAA@XZ; std::unique_ptr<EndpointDlp::TraceLoggingProvider>::~unique_ptr<EndpointDlp::TraceLoggingProvider>(void)
0x18002b840  nop
0x18002b841  lea     rcx, [rbp+var_50]
0x18002b845  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002b84a  mov     rax, cs:?s_instance@TraceLoggingProvider@EndpointDlp@@0V?$unique_ptr@VTraceLoggingProvider@EndpointDlp@@U?$default_delete@VTraceLoggingProvider@EndpointDlp@@@std@@@std@@A; std::unique_ptr<EndpointDlp::TraceLoggingProvider> EndpointDlp::TraceLoggingProvider::s_instance
0x18002b851  jmp     loc_18002B655
0x18002b856  call    ?Instance@TraceLoggingProvider@EndpointDlp@@SAAEAV12@XZ; EndpointDlp::TraceLoggingProvider::Instance(void)
0x18002b85b  mov     rcx, [rax]
0x18002b85e  cmp     dword ptr [rcx], 2
0x18002b861  jbe     short loc_18002B893
0x18002b863  lea     rdx, aInvalidArgumen_0; "Invalid argument for GetDlpQuarantineCo"...
0x18002b86a  mov     qword ptr [rbp+EventDescriptor.Id], rdx
0x18002b86e  mov     dword ptr [rbp+var_50], 80070057h
0x18002b875  lea     rdx, [rbp+EventDescriptor]
0x18002b879  mov     [rsp+80h+UserData], rdx
0x18002b87e  lea     rdx, [rbp+var_50]
0x18002b882  mov     qword ptr [rsp+80h+UserDataCount], rdx
0x18002b887  lea     rdx, word_1802C8F96
0x18002b88e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x18002b893  mov     eax, 80070057h
0x18002b898  jmp     loc_18002B5F6
```
