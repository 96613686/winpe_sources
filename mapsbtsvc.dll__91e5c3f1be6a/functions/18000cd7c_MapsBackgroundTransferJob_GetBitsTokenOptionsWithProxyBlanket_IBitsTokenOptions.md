# MapsBackgroundTransferJob::GetBitsTokenOptionsWithProxyBlanket(IBitsTokenOptions * *)

- ea: `0x18000cd7c`
- end: `0x18000cf64`
- name: `?GetBitsTokenOptionsWithProxyBlanket@MapsBackgroundTransferJob@@AEAAJPEAPEAUIBitsTokenOptions@@@Z`
- size: `488`
- prototype: `__int64 __fastcall(MapsBackgroundTransferJob *__hidden this, struct IBitsTokenOptions **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ef18`

## callees

- `0x1800033d4`
- `0x1800043e4`
- `0x180004680`
- `0x1800047cc`
- `0x18000cd7c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ce59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ce59`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000ce05`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000ce05`

## string_xrefs

- `0x18000cdfc`: `MapsBackgroundTransferJob::GetBitsTokenOptionsWithProxyBlanket`

## pseudocode

```c
__int64 __fastcall MapsBackgroundTransferJob::GetBitsTokenOptionsWithProxyBlanket(
        MapsBackgroundTransferJob *this,
        struct IBitsTokenOptions **a2)
{
  int v4; // eax
  int v5; // r8d
  unsigned int v6; // ebx
  __int64 v7; // rsi
  __int64 (__fastcall *v8)(__int64, struct IBitsTokenOptions *, unsigned int *, unsigned int *, LPVOID *, int *, _QWORD, __int64 *, unsigned int *); // r14
  void *v9; // rbx
  struct IBitsTokenOptions *v10; // rax
  unsigned int v12; // [rsp+50h] [rbp-30h] BYREF
  struct IBitsTokenOptions *v13; // [rsp+58h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-20h] BYREF
  __int64 v15; // [rsp+68h] [rbp-18h] BYREF
  __int64 v16; // [rsp+70h] [rbp-10h] BYREF
  _BYTE v17[8]; // [rsp+78h] [rbp-8h] BYREF
  unsigned int v18; // [rsp+B0h] [rbp+30h] BYREF
  int v19; // [rsp+C0h] [rbp+40h] BYREF
  unsigned int v20; // [rsp+C8h] [rbp+48h] BYREF

  v16 = 0;
  v13 = 0;
  v15 = 0;
  pv = 0;
  v12 = 0;
  v20 = 0;
  v19 = 0;
  v18 = 0;
  v4 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IBitsTokenOptions **))this + 3))(
         *((_QWORD *)this + 3),
         &GUID_9a2584c3_f7d2_457a_9a5e_22b67bffc7d2,
         &v13);
  if ( v4 >= 0 )
  {
    v4 = ((__int64 (__fastcall *)(struct IBitsTokenOptions *, GUID *, __int64 *))v13->lpVtbl->QueryInterface)(
           v13,
           &GUID_0000013d_0000_0000_c000_000000000046,
           &v15);
    if ( v4 >= 0 )
    {
      v7 = v15;
      v8 = *(__int64 (__fastcall **)(__int64, struct IBitsTokenOptions *, unsigned int *, unsigned int *, LPVOID *, int *, _QWORD, __int64 *, unsigned int *))(*(_QWORD *)v15 + 24LL);
      v9 = pv;
      if ( pv )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v17);
        CoTaskMemFree(v9);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v17);
      }
      pv = 0;
      v4 = v8(v7, v13, &v12, &v20, &pv, &v19, 0, &v16, &v18);
      if ( v4 >= 0 )
      {
        v18 = v18 & 0xFFFFFF9F | 0x40;
        v4 = (*(__int64 (__fastcall **)(__int64, struct IBitsTokenOptions *, _QWORD, _QWORD, LPVOID, int, int, __int64, unsigned int))(*(_QWORD *)v15 + 32LL))(
               v15,
               v13,
               v12,
               v20,
               pv,
               v19,
               3,
               v16,
               v18);
        if ( v4 >= 0 )
        {
          v6 = 0;
          v10 = v13;
          v13 = 0;
          *a2 = v10;
          goto LABEL_13;
        }
        v5 = 1463;
      }
      else
      {
        v5 = 1447;
      }
    }
    else
    {
      v5 = 1436;
    }
  }
  else
  {
    v5 = 1434;
  }
  v6 = ZTraceReportPropagation(v4, "MapsBackgroundTransferJob::GetBitsTokenOptionsWithProxyBlanket", v5, this);
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v13);
  return v6;
}

```

## disassembly

```asm
0x18000cd7c  mov     [rsp-28h+arg_8], rbx
0x18000cd81  push    rbp
0x18000cd82  push    rsi
0x18000cd83  push    rdi
0x18000cd84  push    r14
0x18000cd86  push    r15
0x18000cd88  mov     rbp, rsp
0x18000cd8b  sub     rsp, 80h
0x18000cd92  mov     r15, rdx
0x18000cd95  mov     rdi, rcx
0x18000cd98  mov     [rbp+var_10], 0
0x18000cda0  mov     [rbp+var_28], 0
0x18000cda8  mov     [rbp+var_18], 0
0x18000cdb0  mov     [rbp+pv], 0
0x18000cdb8  mov     [rbp+var_30], 0
0x18000cdbf  mov     [rbp+arg_18], 0
0x18000cdc6  mov     [rbp+arg_10], 0
0x18000cdcd  mov     [rbp+arg_0], 0
0x18000cdd4  mov     rcx, [rcx+18h]
0x18000cdd8  mov     rax, [rcx]
0x18000cddb  lea     r8, [rbp+var_28]
0x18000cddf  lea     rdx, _GUID_9a2584c3_f7d2_457a_9a5e_22b67bffc7d2
0x18000cde6  mov     rax, [rax]
0x18000cde9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdee  nop
0x18000cdef  test    eax, eax
0x18000cdf1  jns     short loc_18000CE12
0x18000cdf3  mov     r8d, 59Ah
0x18000cdf9  mov     r9, rdi
0x18000cdfc  lea     rdx, aMapsbackground_18; "MapsBackgroundTransferJob::GetBitsToken"...
0x18000ce03  mov     ecx, eax
0x18000ce05  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000ce0b  mov     ebx, eax
0x18000ce0d  jmp     loc_18000CF2E
0x18000ce12  mov     rcx, [rbp+var_28]
0x18000ce16  mov     rax, [rcx]
0x18000ce19  lea     r8, [rbp+var_18]
0x18000ce1d  lea     rdx, _GUID_0000013d_0000_0000_c000_000000000046
0x18000ce24  mov     rax, [rax]
0x18000ce27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce2c  nop
0x18000ce2d  test    eax, eax
0x18000ce2f  jns     short loc_18000CE39
0x18000ce31  mov     r8d, 59Ch
0x18000ce37  jmp     short loc_18000CDF9
0x18000ce39  mov     rsi, [rbp+var_18]
0x18000ce3d  mov     rax, [rsi]
0x18000ce40  mov     r14, [rax+18h]
0x18000ce44  mov     rbx, [rbp+pv]
0x18000ce48  test    rbx, rbx
0x18000ce4b  jz      short loc_18000CE68
0x18000ce4d  lea     rcx, [rbp+var_8]; this
0x18000ce51  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000ce56  mov     rcx, rbx; pv
0x18000ce59  call    cs:__imp_CoTaskMemFree
0x18000ce5f  lea     rcx, [rbp+var_8]; this
0x18000ce63  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000ce68  mov     [rbp+pv], 0
0x18000ce70  lea     rax, [rbp+arg_0]
0x18000ce74  mov     [rsp+80h+var_40], rax
0x18000ce79  lea     rax, [rbp+var_10]
0x18000ce7d  mov     [rsp+80h+var_48], rax
0x18000ce82  mov     [rsp+80h+var_50], 0
0x18000ce8b  lea     rax, [rbp+arg_10]
0x18000ce8f  mov     [rsp+80h+var_58], rax
0x18000ce94  lea     rax, [rbp+pv]
0x18000ce98  mov     [rsp+80h+var_60], rax
0x18000ce9d  lea     r9, [rbp+arg_18]
0x18000cea1  lea     r8, [rbp+var_30]
0x18000cea5  mov     rdx, [rbp+var_28]
0x18000cea9  mov     rcx, rsi
0x18000ceac  mov     rax, r14
0x18000ceaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ceb4  test    eax, eax
0x18000ceb6  jns     short loc_18000CEC3
0x18000ceb8  mov     r8d, 5A7h
0x18000cebe  jmp     loc_18000CDF9
0x18000cec3  mov     edx, [rbp+arg_0]
0x18000cec6  and     edx, 0FFFFFFDFh
0x18000cec9  or      edx, 40h
0x18000cecc  mov     [rbp+arg_0], edx
0x18000cecf  mov     rcx, [rbp+var_18]
0x18000ced3  mov     r10, [rbp+var_10]
0x18000ced7  mov     r11d, [rbp+arg_10]
0x18000cedb  mov     rbx, [rbp+pv]
0x18000cedf  mov     rax, [rcx]
0x18000cee2  mov     dword ptr [rsp+80h+var_40], edx
0x18000cee6  mov     [rsp+80h+var_48], r10
0x18000ceeb  mov     dword ptr [rsp+80h+var_50], 3
0x18000cef3  mov     dword ptr [rsp+80h+var_58], r11d
0x18000cef8  mov     [rsp+80h+var_60], rbx
0x18000cefd  mov     r9d, [rbp+arg_18]
0x18000cf01  mov     r8d, [rbp+var_30]
0x18000cf05  mov     rdx, [rbp+var_28]
0x18000cf09  mov     rax, [rax+20h]
0x18000cf0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf12  test    eax, eax
0x18000cf14  jns     short loc_18000CF21
0x18000cf16  mov     r8d, 5B7h
0x18000cf1c  jmp     loc_18000CDF9
0x18000cf21  xor     ebx, ebx
0x18000cf23  mov     rax, [rbp+var_28]
0x18000cf27  mov     [rbp+var_28], rbx
0x18000cf2b  mov     [r15], rax
0x18000cf2e  lea     rcx, [rbp+pv]
0x18000cf32  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000cf37  nop
0x18000cf38  lea     rcx, [rbp+var_18]
0x18000cf3c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000cf41  nop
0x18000cf42  lea     rcx, [rbp+var_28]
0x18000cf46  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000cf4b  mov     eax, ebx
0x18000cf4d  mov     rbx, [rsp+80h+arg_8]
0x18000cf55  add     rsp, 80h
0x18000cf5c  pop     r15
0x18000cf5e  pop     r14
0x18000cf60  pop     rdi
0x18000cf61  pop     rsi
0x18000cf62  pop     rbp
0x18000cf63  retn
```
