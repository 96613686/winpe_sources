# LogMasterKeyDescription(ushort const *,_GUID,uchar *,ushort *)

- ea: `0x18001b234`
- end: `0x18001b546`
- name: `?LogMasterKeyDescription@@YAJPEBGU_GUID@@PEAEPEAG@Z`
- size: `786`
- prototype: `__int64 __fastcall(RPC_WSTR StringUuid, struct _GUID *__struct_ptr, unsigned __int8 *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e9c0`
- `0x1800180cc`
- `0x18002d8f0`
- `0x18002ea4c`

## callees

- `0x180001224`
- `0x180008300`
- `0x180010d14`
- `0x180010dc4`
- `0x18001142c`
- `0x180011668`
- `0x1800116ec`
- `0x1800125e8`
- `0x1800142ac`
- `0x18001467c`
- `0x18001b234`
- `0x18001c760`
- `0x18001c808`
- `0x18001c974`
- `0x18001d810`
- `0x18003aca0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001b44f`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001b44f`
- `RPCRT4!UuidFromStringW` at `0x18001b33b`
- `RPCRT4!UuidFromStringW` at `0x18001b33b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001b4e6`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001b4e6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001b471`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001b471`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b2e2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b383`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b2e2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b383`

## string_xrefs

- `0x18001b315`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\masterkeydiagnosticlog.cpp`
- `0x18001b3b6`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\masterkeydiagnosticlog.cpp`
- `0x18001b49c`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\masterkeydiagnosticlog.cpp`

## pseudocode

```c
__int64 __fastcall LogMasterKeyDescription(
        RPC_WSTR StringUuid,
        struct _GUID *a2,
        unsigned __int8 *a3,
        unsigned __int16 *a4)
{
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  HLOCAL v12; // rax
  unsigned int v13; // eax
  unsigned int v14; // r8d
  unsigned int v15; // ebx
  HLOCAL v16; // rax
  _OWORD *v17; // rbx
  PTP_WORK ThreadpoolWork; // rax
  const char *v19; // r9
  unsigned int LastError; // ebx
  unsigned int v21; // [rsp+20h] [rbp-78h]
  UUID *Uuid; // [rsp+30h] [rbp-68h] BYREF
  struct _GUID *v23; // [rsp+38h] [rbp-60h] BYREF
  PTP_WORK pwk; // [rsp+40h] [rbp-58h] BYREF
  PVOID pv[2]; // [rsp+48h] [rbp-50h] BYREF
  unsigned __int8 v26[16]; // [rsp+58h] [rbp-40h] BYREF
  int v27; // [rsp+68h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( a3 )
  {
    Uuid = 0;
    v12 = LocalAlloc(0, 0x10u);
    wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::reset(
      &Uuid,
      v12);
    if ( Uuid )
    {
      v13 = UuidFromStringW(StringUuid, Uuid);
      if ( v13 )
      {
        v15 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x308, v14, (const char *)v13, v21);
        wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>((void **)&Uuid);
        return v15;
      }
      else
      {
        v23 = 0;
        v16 = LocalAlloc(0, 0x10u);
        wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::reset(
          &v23,
          v16);
        if ( v23 )
        {
          *v23 = *a2;
          *(_OWORD *)v26 = 0;
          v27 = 0;
          DeriveStoringKey(a3, v26);
          std::make_unique<ThreadPoolWorkPayload,,0>(pv);
          v17 = pv[0];
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>>::operator=(
            pv[0],
            &Uuid);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>>::operator=(
            (char *)v17 + 8,
            &v23);
          v17[1] = *(_OWORD *)v26;
          *((_DWORD *)v17 + 8) = v27;
          _o_wcsncpy_s((char *)v17 + 36, 261, a4, 261);
          pwk = 0;
          ThreadpoolWork = CreateThreadpoolWork(LogMasterKeyDescriptionFn, v17, 0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
            &pwk,
            ThreadpoolWork);
          if ( pwk )
          {
            pv[0] = 0;
            SubmitThreadpoolWork(pwk);
            wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(&pwk);
            std::unique_ptr<ThreadPoolWorkPayload>::~unique_ptr<ThreadPoolWorkPayload>(pv);
            wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>((void **)&v23);
            wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>((void **)&Uuid);
            return 0;
          }
          else
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x325,
                          (unsigned int)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\masterkeydiagnosticlog.cpp",
                          v19);
            wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(&pwk);
            std::unique_ptr<ThreadPoolWorkPayload>::~unique_ptr<ThreadPoolWorkPayload>(pv);
            wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>((void **)&v23);
            wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>((void **)&Uuid);
            return LastError;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x30C,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\masterkeydiagnosticlog.cpp",
            (const char *)0x8007000ELL,
            v21);
          wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>((void **)&v23);
          wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>((void **)&Uuid);
          return 2147942414LL;
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x306,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\masterkeydiagnosticlog.cpp",
        (const char *)0x8007000ELL,
        v21);
      wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>((void **)&Uuid);
      return 2147942414LL;
    }
  }
  else
  {
    if ( (byte_18004CC41 & 2) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        (_DWORD)StringUuid,
        (unsigned int)ETW_LOG_DIAGNOSTICFILE_RECEIVED_NULL_CRED_KEY,
        0,
        1,
        (__int64)pv);
    if ( (unsigned int)dword_18004C260 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x400000000000LL) )
      {
        pv[0] = (PVOID)0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
          v8,
          (int)byte_1800453B5,
          v9,
          v10,
          (__int64)pv);
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18001b234  mov     [rsp+arg_8], rbx
0x18001b239  push    rsi
0x18001b23a  push    rdi
0x18001b23b  push    r14
0x18001b23d  sub     rsp, 80h
0x18001b244  mov     rax, cs:__security_cookie
0x18001b24b  xor     rax, rsp
0x18001b24e  mov     [rsp+98h+var_28], rax
0x18001b253  mov     r14, r9
0x18001b256  mov     rbx, r8
0x18001b259  mov     rsi, rdx
0x18001b25c  mov     rdi, rcx
0x18001b25f  test    rbx, rbx
0x18001b262  jnz     short loc_18001B2D2
0x18001b264  test    cs:byte_18004CC41, 2
0x18001b26b  jz      short loc_18001B287
0x18001b26d  lea     rax, [rsp+98h+pv]
0x18001b272  mov     qword ptr [rsp+98h+var_78], rax
0x18001b277  lea     r9d, [r8+1]
0x18001b27b  lea     rdx, ETW_LOG_DIAGNOSTICFILE_RECEIVED_NULL_CRED_KEY
0x18001b282  call    McGenEventWrite_EtwEventWriteTransfer
0x18001b287  mov     eax, cs:dword_18004C260
0x18001b28d  cmp     eax, 5
0x18001b290  jbe     short loc_18001B2CB
0x18001b292  mov     rdx, 400000000000h
0x18001b29c  lea     rcx, dword_18004C260
0x18001b2a3  call    _tlgKeywordOn
0x18001b2a8  test    al, al
0x18001b2aa  jz      short loc_18001B2CB
0x18001b2ac  mov     [rsp+98h+pv], 1000000h
0x18001b2b5  lea     rax, [rsp+98h+pv]
0x18001b2ba  mov     qword ptr [rsp+98h+var_78], rax
0x18001b2bf  lea     rdx, byte_1800453B5
0x18001b2c6  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18001b2cb  xor     eax, eax
0x18001b2cd  jmp     loc_18001B524
0x18001b2d2  mov     [rsp+98h+Uuid], 0
0x18001b2db  mov     edx, 10h; uBytes
0x18001b2e0  xor     ecx, ecx; uFlags
0x18001b2e2  call    cs:__imp_LocalAlloc
0x18001b2e9  nop     dword ptr [rax+rax+00h]
0x18001b2ee  mov     rdx, rax
0x18001b2f1  lea     rcx, [rsp+98h+Uuid]
0x18001b2f6  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_GUID@@@Z; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::reset(_GUID *)
0x18001b2fb  mov     rdx, [rsp+98h+Uuid]; Uuid
0x18001b300  test    rdx, rdx
0x18001b303  jnz     short loc_18001B338
0x18001b305  mov     rcx, [rsp+98h]; this
0x18001b30d  mov     ebx, 8007000Eh
0x18001b312  mov     r9d, ebx; char *
0x18001b315  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18001b31c  mov     edx, 306h; void *
0x18001b321  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b326  nop
0x18001b327  lea     rcx, [rsp+98h+Uuid]
0x18001b32c  call    ??1?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>(void)
0x18001b331  mov     eax, ebx
0x18001b333  jmp     loc_18001B524
0x18001b338  mov     rcx, rdi; StringUuid
0x18001b33b  call    cs:__imp_UuidFromStringW
0x18001b342  nop     dword ptr [rax+rax+00h]
0x18001b347  test    eax, eax
0x18001b349  jz      short loc_18001B373
0x18001b34b  mov     rcx, [rsp+98h]; this
0x18001b353  mov     r9d, eax; char *
0x18001b356  mov     edx, 308h; void *
0x18001b35b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001b360  mov     ebx, eax
0x18001b362  lea     rcx, [rsp+98h+Uuid]
0x18001b367  call    ??1?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>(void)
0x18001b36c  mov     eax, ebx
0x18001b36e  jmp     loc_18001B524
0x18001b373  mov     [rsp+98h+var_60], 0
0x18001b37c  mov     edx, 10h; uBytes
0x18001b381  xor     ecx, ecx; uFlags
0x18001b383  call    cs:__imp_LocalAlloc
0x18001b38a  nop     dword ptr [rax+rax+00h]
0x18001b38f  mov     rdx, rax
0x18001b392  lea     rcx, [rsp+98h+var_60]
0x18001b397  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_GUID@@@Z; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::reset(_GUID *)
0x18001b39c  mov     rax, [rsp+98h+var_60]
0x18001b3a1  test    rax, rax
0x18001b3a4  jnz     short loc_18001B3E4
0x18001b3a6  mov     rcx, [rsp+98h]; this
0x18001b3ae  mov     ebx, 8007000Eh
0x18001b3b3  mov     r9d, ebx; char *
0x18001b3b6  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18001b3bd  mov     edx, 30Ch; void *
0x18001b3c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b3c7  nop
0x18001b3c8  lea     rcx, [rsp+98h+var_60]
0x18001b3cd  call    ??1?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>(void)
0x18001b3d2  nop
0x18001b3d3  lea     rcx, [rsp+98h+Uuid]
0x18001b3d8  call    ??1?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>(void)
0x18001b3dd  mov     eax, ebx
0x18001b3df  jmp     loc_18001B524
0x18001b3e4  movups  xmm0, xmmword ptr [rsi]
0x18001b3e7  movdqu  xmmword ptr [rax], xmm0
0x18001b3eb  xorps   xmm1, xmm1
0x18001b3ee  xor     eax, eax
0x18001b3f0  movups  xmmword ptr [rsp+98h+var_40], xmm1
0x18001b3f5  mov     [rsp+98h+var_30], eax
0x18001b3f9  lea     rdx, [rsp+98h+var_40]; unsigned __int8 *
0x18001b3fe  mov     rcx, rbx; pbSecret
0x18001b401  call    ?DeriveStoringKey@@YAXQEAE0@Z; DeriveStoringKey(uchar * const,uchar * const)
0x18001b406  lea     rcx, [rsp+98h+pv]
0x18001b40b  call    ??$make_unique@UThreadPoolWorkPayload@@$$V$0A@@std@@YA?AV?$unique_ptr@UThreadPoolWorkPayload@@U?$default_delete@UThreadPoolWorkPayload@@@std@@@0@XZ; std::make_unique<ThreadPoolWorkPayload,,0>(void)
0x18001b410  lea     rdx, [rsp+98h+Uuid]
0x18001b415  mov     rbx, [rsp+98h+pv]
0x18001b41a  mov     rcx, rbx
0x18001b41d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>> &&)
0x18001b422  lea     rcx, [rbx+8]
0x18001b426  lea     rdx, [rsp+98h+var_60]
0x18001b42b  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>> &&)
0x18001b430  movups  xmm0, xmmword ptr [rsp+98h+var_40]
0x18001b435  movups  xmmword ptr [rbx+10h], xmm0
0x18001b439  mov     eax, [rsp+98h+var_30]
0x18001b43d  mov     [rbx+20h], eax
0x18001b440  lea     rcx, [rbx+24h]
0x18001b444  mov     edx, 105h
0x18001b449  mov     r9d, edx
0x18001b44c  mov     r8, r14
0x18001b44f  call    cs:__imp__o_wcsncpy_s
0x18001b456  nop     dword ptr [rax+rax+00h]
0x18001b45b  mov     [rsp+98h+pwk], 0
0x18001b464  xor     r8d, r8d; pcbe
0x18001b467  mov     rdx, rbx; pv
0x18001b46a  lea     rcx, ?LogMasterKeyDescriptionFn@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001b471  call    cs:__imp_CreateThreadpoolWork
0x18001b478  nop     dword ptr [rax+rax+00h]
0x18001b47d  mov     rdx, rax
0x18001b480  lea     rcx, [rsp+98h+pwk]
0x18001b485  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x18001b48a  mov     rcx, [rsp+98h+pwk]; pwk
0x18001b48f  test    rcx, rcx
0x18001b492  jnz     short loc_18001B4DD
0x18001b494  mov     rcx, [rsp+98h]; this
0x18001b49c  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18001b4a3  mov     edx, 325h; void *
0x18001b4a8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001b4ad  mov     ebx, eax
0x18001b4af  lea     rcx, [rsp+98h+pwk]
0x18001b4b4  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x18001b4b9  lea     rcx, [rsp+98h+pv]
0x18001b4be  call    ??1?$unique_ptr@UThreadPoolWorkPayload@@U?$default_delete@UThreadPoolWorkPayload@@@std@@@std@@QEAA@XZ; std::unique_ptr<ThreadPoolWorkPayload>::~unique_ptr<ThreadPoolWorkPayload>(void)
0x18001b4c3  nop
0x18001b4c4  lea     rcx, [rsp+98h+var_60]
0x18001b4c9  call    ??1?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>(void)
0x18001b4ce  nop
0x18001b4cf  lea     rcx, [rsp+98h+Uuid]
0x18001b4d4  call    ??1?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>(void)
0x18001b4d9  mov     eax, ebx
0x18001b4db  jmp     short loc_18001B524
0x18001b4dd  mov     [rsp+98h+pv], 0
0x18001b4e6  call    cs:__imp_SubmitThreadpoolWork
0x18001b4ed  nop     dword ptr [rax+rax+00h]
0x18001b4f2  lea     rcx, [rsp+98h+pwk]
0x18001b4f7  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x18001b4fc  lea     rcx, [rsp+98h+pv]
0x18001b501  call    ??1?$unique_ptr@UThreadPoolWorkPayload@@U?$default_delete@UThreadPoolWorkPayload@@@std@@@std@@QEAA@XZ; std::unique_ptr<ThreadPoolWorkPayload>::~unique_ptr<ThreadPoolWorkPayload>(void)
0x18001b506  nop
0x18001b507  lea     rcx, [rsp+98h+var_60]
0x18001b50c  call    ??1?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>(void)
0x18001b511  nop
0x18001b512  lea     rcx, [rsp+98h+Uuid]
0x18001b517  call    ??1?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>(void)
0x18001b51c  xor     eax, eax
0x18001b51e  jmp     short loc_18001B524
0x18001b520  mov     eax, dword ptr [rsp+98h+Uuid]
0x18001b524  mov     rcx, [rsp+98h+var_28]
0x18001b529  xor     rcx, rsp; StackCookie
0x18001b52c  call    __security_check_cookie
0x18001b531  mov     rbx, [rsp+98h+arg_8]
0x18001b539  add     rsp, 80h
0x18001b540  pop     r14
0x18001b542  pop     rdi
0x18001b543  pop     rsi
0x18001b544  retn
```
