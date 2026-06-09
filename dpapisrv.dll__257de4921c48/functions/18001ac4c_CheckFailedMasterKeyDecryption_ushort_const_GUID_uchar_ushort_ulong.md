# CheckFailedMasterKeyDecryption(ushort const *,_GUID,uchar *,ushort *,ulong)

- ea: `0x18001ac4c`
- end: `0x18001af87`
- name: `?CheckFailedMasterKeyDecryption@@YAJPEBGU_GUID@@PEAEPEAGK@Z`
- size: `827`
- prototype: `__int64 __fastcall(RPC_WSTR StringUuid, struct _GUID *Buf1, PUCHAR pbSecret, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000abf0`
- `0x18000e9c0`

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
- `0x18001ac4c`
- `0x18001c760`
- `0x18001c808`
- `0x18001c974`
- `0x18001d810`
- `0x18003aca0`
- `0x18003c620`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001ae88`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001ae88`
- `RPCRT4!UuidFromStringW` at `0x18001ad56`
- `RPCRT4!UuidFromStringW` at `0x18001ad56`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001af2c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001af2c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001aeb7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001aeb7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001acfd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ad9c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001acfd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ad9c`

## string_xrefs

- `0x18001ad30`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\masterkeydiagnosticlog.cpp`
- `0x18001adcf`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\masterkeydiagnosticlog.cpp`
- `0x18001aee2`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\masterkeydiagnosticlog.cpp`

## pseudocode

```c
__int64 __fastcall CheckFailedMasterKeyDecryption(
        RPC_WSTR StringUuid,
        struct _GUID *Buf1,
        PUCHAR pbSecret,
        unsigned __int16 *a4,
        unsigned int a5)
{
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  HLOCAL v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // r8d
  unsigned int v16; // ebx
  HLOCAL v17; // rax
  struct _GUID *v18; // rbx
  _OWORD *v19; // rbx
  PTP_WORK ThreadpoolWork; // rax
  const char *v21; // r9
  unsigned int LastError; // ebx
  unsigned int v23; // [rsp+20h] [rbp-88h]
  UUID *Uuid; // [rsp+30h] [rbp-78h] BYREF
  struct _GUID *v25; // [rsp+38h] [rbp-70h] BYREF
  PTP_WORK pwk; // [rsp+40h] [rbp-68h] BYREF
  PVOID pv[2]; // [rsp+48h] [rbp-60h] BYREF
  unsigned __int8 v28[16]; // [rsp+58h] [rbp-50h] BYREF
  int v29; // [rsp+68h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  if ( pbSecret )
  {
    Uuid = 0;
    v13 = LocalAlloc(0, 0x10u);
    wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::reset(
      &Uuid,
      v13);
    if ( Uuid )
    {
      v14 = UuidFromStringW(StringUuid, Uuid);
      if ( v14 )
      {
        v16 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x355, v15, (const char *)v14, v23);
        wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>((void **)&Uuid);
        return v16;
      }
      else
      {
        v25 = 0;
        v17 = LocalAlloc(0, 0x10u);
        wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::reset(
          &v25,
          v17);
        v18 = v25;
        if ( v25 )
        {
          if ( !memcmp_0(Buf1, &GUID_NULL, 0x10u) )
            *(_OWORD *)pv = 0;
          else
            *v18 = *Buf1;
          *(_OWORD *)v28 = 0;
          v29 = 0;
          DeriveStoringKey(pbSecret, v28);
          std::make_unique<ThreadPoolWorkPayload,,0>(pv);
          v19 = pv[0];
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>>::operator=(
            pv[0],
            &Uuid);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>>::operator=(
            (char *)v19 + 8,
            &v25);
          v19[1] = *(_OWORD *)v28;
          *((_DWORD *)v19 + 8) = v29;
          _o_wcsncpy_s((char *)v19 + 36, 261, a4, 261);
          *((_DWORD *)v19 + 140) = a5;
          pwk = 0;
          ThreadpoolWork = CreateThreadpoolWork(CheckFailedMasterKeyDecryptionFn, v19, 0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
            &pwk,
            ThreadpoolWork);
          if ( pwk )
          {
            pv[0] = 0;
            SubmitThreadpoolWork(pwk);
            wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(&pwk);
            std::unique_ptr<ThreadPoolWorkPayload>::~unique_ptr<ThreadPoolWorkPayload>(pv);
            wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>((void **)&v25);
            wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>((void **)&Uuid);
            return 0;
          }
          else
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x37A,
                          (unsigned int)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\masterkeydiagnosticlog.cpp",
                          v21);
            wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(&pwk);
            std::unique_ptr<ThreadPoolWorkPayload>::~unique_ptr<ThreadPoolWorkPayload>(pv);
            wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>((void **)&v25);
            wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>((void **)&Uuid);
            return LastError;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x359,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\masterkeydiagnosticlog.cpp",
            (const char *)0x8007000ELL,
            v23);
          wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>((void **)&v25);
          wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>((void **)&Uuid);
          return 2147942414LL;
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x353,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\masterkeydiagnosticlog.cpp",
        (const char *)0x8007000ELL,
        v23);
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
          v9,
          (int)byte_180045443,
          v10,
          v11,
          (__int64)pv);
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18001ac4c  push    rbx
0x18001ac4e  push    rsi
0x18001ac4f  push    rdi
0x18001ac50  push    r12
0x18001ac52  push    r14
0x18001ac54  sub     rsp, 80h
0x18001ac5b  mov     rax, cs:__security_cookie
0x18001ac62  xor     rax, rsp
0x18001ac65  mov     [rsp+0A8h+var_38], rax
0x18001ac6a  mov     r14, r9
0x18001ac6d  mov     rdi, r8
0x18001ac70  mov     rsi, rdx
0x18001ac73  mov     rbx, rcx
0x18001ac76  test    r8, r8
0x18001ac79  jnz     short loc_18001ACE9
0x18001ac7b  test    cs:byte_18004CC41, 2
0x18001ac82  jz      short loc_18001AC9E
0x18001ac84  lea     rax, [rsp+0A8h+pv]
0x18001ac89  mov     qword ptr [rsp+0A8h+var_88], rax
0x18001ac8e  lea     r9d, [r8+1]
0x18001ac92  lea     rdx, ETW_LOG_DIAGNOSTICFILE_RECEIVED_NULL_CRED_KEY
0x18001ac99  call    McGenEventWrite_EtwEventWriteTransfer
0x18001ac9e  mov     eax, cs:dword_18004C260
0x18001aca4  cmp     eax, 5
0x18001aca7  jbe     short loc_18001ACE2
0x18001aca9  mov     rdx, 400000000000h
0x18001acb3  lea     rcx, dword_18004C260
0x18001acba  call    _tlgKeywordOn
0x18001acbf  test    al, al
0x18001acc1  jz      short loc_18001ACE2
0x18001acc3  mov     [rsp+0A8h+pv], 1000000h
0x18001accc  lea     rax, [rsp+0A8h+pv]
0x18001acd1  mov     qword ptr [rsp+0A8h+var_88], rax
0x18001acd6  lea     rdx, byte_180045443
0x18001acdd  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18001ace2  xor     eax, eax
0x18001ace4  jmp     loc_18001AF6A
0x18001ace9  mov     [rsp+0A8h+Uuid], 0
0x18001acf2  mov     r12d, 10h
0x18001acf8  mov     edx, r12d; uBytes
0x18001acfb  xor     ecx, ecx; uFlags
0x18001acfd  call    cs:__imp_LocalAlloc
0x18001ad04  nop     dword ptr [rax+rax+00h]
0x18001ad09  mov     rdx, rax
0x18001ad0c  lea     rcx, [rsp+0A8h+Uuid]
0x18001ad11  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_GUID@@@Z; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::reset(_GUID *)
0x18001ad16  mov     rdx, [rsp+0A8h+Uuid]; Uuid
0x18001ad1b  test    rdx, rdx
0x18001ad1e  jnz     short loc_18001AD53
0x18001ad20  mov     rcx, [rsp+0A8h]; this
0x18001ad28  mov     ebx, 8007000Eh
0x18001ad2d  mov     r9d, ebx; char *
0x18001ad30  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18001ad37  mov     edx, 353h; void *
0x18001ad3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ad41  nop
0x18001ad42  lea     rcx, [rsp+0A8h+Uuid]
0x18001ad47  call    ??1?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>(void)
0x18001ad4c  mov     eax, ebx
0x18001ad4e  jmp     loc_18001AF6A
0x18001ad53  mov     rcx, rbx; StringUuid
0x18001ad56  call    cs:__imp_UuidFromStringW
0x18001ad5d  nop     dword ptr [rax+rax+00h]
0x18001ad62  test    eax, eax
0x18001ad64  jz      short loc_18001AD8E
0x18001ad66  mov     rcx, [rsp+0A8h]; this
0x18001ad6e  mov     r9d, eax; char *
0x18001ad71  mov     edx, 355h; void *
0x18001ad76  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001ad7b  mov     ebx, eax
0x18001ad7d  lea     rcx, [rsp+0A8h+Uuid]
0x18001ad82  call    ??1?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>(void)
0x18001ad87  mov     eax, ebx
0x18001ad89  jmp     loc_18001AF6A
0x18001ad8e  mov     [rsp+0A8h+var_70], 0
0x18001ad97  mov     rdx, r12; uBytes
0x18001ad9a  xor     ecx, ecx; uFlags
0x18001ad9c  call    cs:__imp_LocalAlloc
0x18001ada3  nop     dword ptr [rax+rax+00h]
0x18001ada8  mov     rdx, rax
0x18001adab  lea     rcx, [rsp+0A8h+var_70]
0x18001adb0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_GUID@@@Z; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::reset(_GUID *)
0x18001adb5  mov     rbx, [rsp+0A8h+var_70]
0x18001adba  test    rbx, rbx
0x18001adbd  jnz     short loc_18001ADFD
0x18001adbf  mov     rcx, [rsp+0A8h]; this
0x18001adc7  mov     ebx, 8007000Eh
0x18001adcc  mov     r9d, ebx; char *
0x18001adcf  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18001add6  mov     edx, 359h; void *
0x18001addb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ade0  nop
0x18001ade1  lea     rcx, [rsp+0A8h+var_70]
0x18001ade6  call    ??1?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>(void)
0x18001adeb  nop
0x18001adec  lea     rcx, [rsp+0A8h+Uuid]
0x18001adf1  call    ??1?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>(void)
0x18001adf6  mov     eax, ebx
0x18001adf8  jmp     loc_18001AF6A
0x18001adfd  mov     r8, r12; Size
0x18001ae00  lea     rdx, GUID_NULL; Buf2
0x18001ae07  mov     rcx, rsi; Buf1
0x18001ae0a  call    memcmp_0
0x18001ae0f  test    eax, eax
0x18001ae11  jz      short loc_18001AE1C
0x18001ae13  movups  xmm0, xmmword ptr [rsi]
0x18001ae16  movdqu  xmmword ptr [rbx], xmm0
0x18001ae1a  jmp     short loc_18001AE24
0x18001ae1c  xorps   xmm0, xmm0
0x18001ae1f  movups  xmmword ptr [rsp+0A8h+pv], xmm0
0x18001ae24  xorps   xmm0, xmm0
0x18001ae27  xor     eax, eax
0x18001ae29  movups  xmmword ptr [rsp+0A8h+var_50], xmm0
0x18001ae2e  mov     [rsp+0A8h+var_40], eax
0x18001ae32  lea     rdx, [rsp+0A8h+var_50]; unsigned __int8 *
0x18001ae37  mov     rcx, rdi; pbSecret
0x18001ae3a  call    ?DeriveStoringKey@@YAXQEAE0@Z; DeriveStoringKey(uchar * const,uchar * const)
0x18001ae3f  lea     rcx, [rsp+0A8h+pv]
0x18001ae44  call    ??$make_unique@UThreadPoolWorkPayload@@$$V$0A@@std@@YA?AV?$unique_ptr@UThreadPoolWorkPayload@@U?$default_delete@UThreadPoolWorkPayload@@@std@@@0@XZ; std::make_unique<ThreadPoolWorkPayload,,0>(void)
0x18001ae49  lea     rdx, [rsp+0A8h+Uuid]
0x18001ae4e  mov     rbx, [rsp+0A8h+pv]
0x18001ae53  mov     rcx, rbx
0x18001ae56  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>> &&)
0x18001ae5b  lea     rcx, [rbx+8]
0x18001ae5f  lea     rdx, [rsp+0A8h+var_70]
0x18001ae64  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>> &&)
0x18001ae69  movups  xmm0, xmmword ptr [rsp+0A8h+var_50]
0x18001ae6e  movups  xmmword ptr [rbx+10h], xmm0
0x18001ae72  mov     eax, [rsp+0A8h+var_40]
0x18001ae76  mov     [rbx+20h], eax
0x18001ae79  lea     rcx, [rbx+24h]
0x18001ae7d  mov     edx, 105h
0x18001ae82  mov     r9d, edx
0x18001ae85  mov     r8, r14
0x18001ae88  call    cs:__imp__o_wcsncpy_s
0x18001ae8f  nop     dword ptr [rax+rax+00h]
0x18001ae94  mov     eax, [rsp+0A8h+arg_20]
0x18001ae9b  mov     [rbx+230h], eax
0x18001aea1  mov     [rsp+0A8h+pwk], 0
0x18001aeaa  xor     r8d, r8d; pcbe
0x18001aead  mov     rdx, rbx; pv
0x18001aeb0  lea     rcx, ?CheckFailedMasterKeyDecryptionFn@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001aeb7  call    cs:__imp_CreateThreadpoolWork
0x18001aebe  nop     dword ptr [rax+rax+00h]
0x18001aec3  mov     rdx, rax
0x18001aec6  lea     rcx, [rsp+0A8h+pwk]
0x18001aecb  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x18001aed0  mov     rcx, [rsp+0A8h+pwk]; pwk
0x18001aed5  test    rcx, rcx
0x18001aed8  jnz     short loc_18001AF23
0x18001aeda  mov     rcx, [rsp+0A8h]; this
0x18001aee2  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18001aee9  mov     edx, 37Ah; void *
0x18001aeee  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001aef3  mov     ebx, eax
0x18001aef5  lea     rcx, [rsp+0A8h+pwk]
0x18001aefa  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x18001aeff  lea     rcx, [rsp+0A8h+pv]
0x18001af04  call    ??1?$unique_ptr@UThreadPoolWorkPayload@@U?$default_delete@UThreadPoolWorkPayload@@@std@@@std@@QEAA@XZ; std::unique_ptr<ThreadPoolWorkPayload>::~unique_ptr<ThreadPoolWorkPayload>(void)
0x18001af09  nop
0x18001af0a  lea     rcx, [rsp+0A8h+var_70]
0x18001af0f  call    ??1?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>(void)
0x18001af14  nop
0x18001af15  lea     rcx, [rsp+0A8h+Uuid]
0x18001af1a  call    ??1?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>(void)
0x18001af1f  mov     eax, ebx
0x18001af21  jmp     short loc_18001AF6A
0x18001af23  mov     [rsp+0A8h+pv], 0
0x18001af2c  call    cs:__imp_SubmitThreadpoolWork
0x18001af33  nop     dword ptr [rax+rax+00h]
0x18001af38  lea     rcx, [rsp+0A8h+pwk]
0x18001af3d  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x18001af42  lea     rcx, [rsp+0A8h+pv]
0x18001af47  call    ??1?$unique_ptr@UThreadPoolWorkPayload@@U?$default_delete@UThreadPoolWorkPayload@@@std@@@std@@QEAA@XZ; std::unique_ptr<ThreadPoolWorkPayload>::~unique_ptr<ThreadPoolWorkPayload>(void)
0x18001af4c  nop
0x18001af4d  lea     rcx, [rsp+0A8h+var_70]
0x18001af52  call    ??1?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>(void)
0x18001af57  nop
0x18001af58  lea     rcx, [rsp+0A8h+Uuid]
0x18001af5d  call    ??1?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>(void)
0x18001af62  xor     eax, eax
0x18001af64  jmp     short loc_18001AF6A
0x18001af66  mov     eax, dword ptr [rsp+0A8h+Uuid]
0x18001af6a  mov     rcx, [rsp+0A8h+var_38]
0x18001af6f  xor     rcx, rsp; StackCookie
0x18001af72  call    __security_check_cookie
0x18001af77  add     rsp, 80h
0x18001af7e  pop     r14
0x18001af80  pop     r12
0x18001af82  pop     rdi
0x18001af83  pop     rsi
0x18001af84  pop     rbx
0x18001af85  retn
```
