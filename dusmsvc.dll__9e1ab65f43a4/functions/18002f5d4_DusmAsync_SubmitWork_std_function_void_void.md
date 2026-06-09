# DusmAsync::SubmitWork(std::function<void (void)> &&)

- ea: `0x18002f5d4`
- end: `0x18002f688`
- name: `?SubmitWork@DusmAsync@@SAX$$QEAV?$function@$$A6AXXZ@std@@@Z`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c508`

## callees

- `0x18000f094`
- `0x18001db50`
- `0x18002e9d8`
- `0x18002ea7c`
- `0x18002ec00`
- `0x18002f5d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f605`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f605`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002f660`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002f660`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DusmAsync::SubmitWork(__int64 a1)
{
  DusmAsync *v1; // rdi
  __int64 v2; // rdx
  __int64 result; // rax
  wil *v4; // rcx
  __int64 v5; // rdx
  wil *v6; // rcx
  int v7; // ebx
  wil *v8; // rcx
  const wil::ResultException *v9; // rdi
  __int64 v10; // r9
  _DWORD *v11; // r8
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // ebx
  int v16; // edi
  unsigned int *v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // [rsp+50h] [rbp-88h] BYREF
  char *v21; // [rsp+58h] [rbp-80h] BYREF
  int v22; // [rsp+60h] [rbp-78h] BYREF
  const WCHAR *v23; // [rsp+68h] [rbp-70h] BYREF
  const wchar_t *v24; // [rsp+70h] [rbp-68h] BYREF
  const wil::ResultException *v25; // [rsp+78h] [rbp-60h] BYREF
  int v26; // [rsp+80h] [rbp-58h] BYREF
  _BYTE v27[80]; // [rsp+88h] [rbp-50h] BYREF

  v1 = DusmAsync::s_pInstance;
  v26 = 0;
  std::function<void (void)>::function<void (void)>(v27, a1);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 8));
  try
  {
    v21 = (char *)v1 + 8;
    if ( *((_BYTE *)v1 + 272) )
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v21);
    }
    else
    {
      if ( *(_DWORD *)v1 == 1 )
        std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__DusmAsync::SubmitWork_::_3_::_lambda_1___(
          (char *)v1 + 152,
          &v26);
      else
        std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__DusmAsync::SubmitWork_::_3_::_lambda_1___(
          (char *)v1 + 232,
          &v26);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v21);
      _InterlockedIncrement64((volatile signed __int64 *)v1 + 17);
      SubmitThreadpoolWork(*((PTP_WORK *)v1 + 16));
    }
    result = std::function<long (void)>::~function<long (void)>((__int64)v27, v2);
  }
  catch ( const wil::ResultException *v25 )
  {
    if ( (int)wil::ResultFromCaughtException(v4) < 0 )
    {
      if ( (wil::ResultFromCaughtException(v6) & 0x1FFF0000) == 0x70000 )
        v7 = (unsigned __int16)wil::ResultFromCaughtException(v8);
      else
        v7 = wil::ResultFromCaughtException(v8);
    }
    else
    {
      v7 = 0;
    }
    v9 = v25;
    result = wil::details::static_lazy<DusmTraceLoggingProvider>::get(v6, v5);
    v11 = *(_DWORD **)(result + 8);
    if ( *v11 > 5u )
    {
      v23 = (const WCHAR *)*((_QWORD *)v9 + 6);
      v22 = *((_DWORD *)v9 + 22);
      v24 = (const wchar_t *)*((_QWORD *)v9 + 10);
      v20 = *((_DWORD *)v9 + 8);
      LODWORD(v21) = v7;
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
               (int)v11,
               (int)&byte_180058A2B,
               (__int64)v11,
               v10,
               (__int64)&v21,
               (__int64)&v20,
               &v24,
               (__int64)&v22,
               &v23);
    }
    return result;
  }
  catch ( ... )
  {
    v12 = wil::ResultFromCaughtException(v4);
    v15 = v12;
    if ( v12 < 0 )
    {
      v16 = (unsigned __int16)v12;
      if ( (v12 & 0x1FFF0000) != 0x70000 )
        v16 = v12;
    }
    else
    {
      v16 = 0;
    }
    v17 = *(unsigned int **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v14, v13) + 8);
    result = *v17;
    if ( (unsigned int)result > 5 )
    {
      LODWORD(v21) = v15;
      v20 = v16;
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
               (int)v17,
               (int)byte_1800589F9,
               v18,
               v19,
               (__int64)&v20,
               (__int64)&v21);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002f5d4  mov     rax, rsp
0x18002f5d7  mov     [rax+10h], rbx
0x18002f5db  push    rdi
0x18002f5dc  sub     rsp, 0D0h
0x18002f5e3  mov     rdi, cs:?s_pInstance@DusmAsync@@0PEAV1@EA; DusmAsync * DusmAsync::s_pInstance
0x18002f5ea  mov     dword ptr [rax-58h], 0
0x18002f5f1  mov     rdx, rcx
0x18002f5f4  lea     rcx, [rax-50h]
0x18002f5f8  call    ??0?$function@$$A6AXXZ@std@@QEAA@$$QEAV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> &&)
0x18002f5fd  nop
0x18002f5fe  lea     rbx, [rdi+8]
0x18002f602  mov     rcx, rbx; lpCriticalSection
0x18002f605  call    cs:__imp_EnterCriticalSection
0x18002f60b  mov     [rsp+0D8h+var_80], rbx
0x18002f610  lea     rcx, [rdi+98h]
0x18002f617  cmp     byte ptr [rcx+78h], 0
0x18002f61b  jz      short loc_18002F629
0x18002f61d  lea     rcx, [rsp+0D8h+var_80]
0x18002f622  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002f627  jmp     short loc_18002F667
0x18002f629  lea     rdx, [rsp+0D8h+var_58]
0x18002f631  cmp     dword ptr [rdi], 1
0x18002f634  jnz     short loc_18002F63D
0x18002f636  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__DusmAsync__SubmitWork____3____lambda_1___
0x18002f63b  jmp     short loc_18002F647
0x18002f63d  add     rcx, 50h ; 'P'
0x18002f641  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__DusmAsync__SubmitWork____3____lambda_1___
0x18002f646  nop
0x18002f647  lea     rcx, [rsp+0D8h+var_80]
0x18002f64c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002f651  lock inc qword ptr [rdi+88h]
0x18002f659  mov     rcx, [rdi+80h]; pwk
0x18002f660  call    cs:__imp_SubmitThreadpoolWork
0x18002f666  nop
0x18002f667  lea     rcx, [rsp+0D8h+var_50]
0x18002f66f  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x18002f674  nop
0x18002f675  mov     rbx, [rsp+0D8h+arg_8]
0x18002f67d  add     rsp, 0D0h
0x18002f684  pop     rdi
0x18002f685  retn
0x18002f686  jmp     short loc_18002F675
```
