# Microsoft::InformationProtection::CProtectedFile::CreateProtectorWrapper(ATL::CComPtr<IUnknown> &,ulong,_IPC_PROMPT_CTX const *,ulong,ulong)

- ea: `0x180053888`
- end: `0x180053a9e`
- name: `?CreateProtectorWrapper@CProtectedFile@InformationProtection@Microsoft@@AEAA?AV?$shared_ptr@VIProtectorWrapper@InformationProtection@Microsoft@@@tr1@std@@AEAV?$CComPtr@UIUnknown@@@ATL@@KPEBU_IPC_PROMPT_CTX@@KK@Z`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180052f50`

## callees

- `0x18000343a`
- `0x1800516b8`
- `0x1800534fc`
- `0x180053888`
- `0x18005bdc0`
- `0x18005f010`

## string_xrefs

- `0x180053a11`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\protectedfile\cprotectedfile.cpp`
- `0x180053a47`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\protectedfile\cprotectedfile.cpp`
- `0x180053a7d`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\protectedfile\cprotectedfile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall Microsoft::InformationProtection::CProtectedFile::CreateProtectorWrapper(
        __int64 a1,
        _QWORD *a2,
        __int64 (__fastcall ****a3)(_QWORD, GUID *, _QWORD *),
        __int64 a4,
        int a5,
        int a6,
        int a7)
{
  __int64 (__fastcall ***v10)(_QWORD, GUID *, _QWORD *); // rcx
  int v11; // eax
  __int64 v12; // rax
  volatile signed __int32 *v13; // rbx
  _QWORD v15[3]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v16; // [rsp+78h] [rbp-90h] BYREF
  volatile signed __int32 *v17; // [rsp+80h] [rbp-88h]
  _BYTE pExceptionObject[1216]; // [rsp+88h] [rbp-80h] BYREF

  v15[1] = -2;
  v15[2] = a2;
  *a2 = 0;
  a2[1] = 0;
  v10 = *a3;
  if ( !*a3 )
  {
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\protectedfile\\cprotectedfile.cpp",
      0xAEu,
      &Src,
      -2147221164);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  v15[0] = 0;
  v11 = (**v10)(v10, &IID_I_IrmProtector, v15);
  if ( v11 < 0 )
  {
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\protectedfile\\cprotectedfile.cpp",
      0xB3u,
      L"pIUnknownProtector->QueryInterface(IID_I_IrmProtector, (void **)&pIrmProtector)",
      v11);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  if ( !v15[0] )
  {
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\protectedfile\\cprotectedfile.cpp",
      0xC2u,
      &Src,
      -2147467263);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  v12 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *), __int64, __int64, _QWORD, int, int))Microsoft::InformationProtection::IProtectorWrapperFactory::s_IrmProtectorWrapperFactory)(
          Microsoft::InformationProtection::IProtectorWrapperFactory::s_IrmProtectorWrapperFactory,
          &v16,
          a3,
          a1 + 8,
          a1 + 16,
          0,
          a6,
          a7);
  std::tr1::shared_ptr<Microsoft::InformationProtection::IProtectorWrapper>::operator=(a2, v12);
  v13 = v17;
  if ( v17 )
  {
    if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  if ( v15[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v15[0] + 16LL))(v15[0]);
  return a2;
}

```

## disassembly

```asm
0x180053888  mov     rax, rsp
0x18005388b  push    rbp
0x18005388c  push    rsi
0x18005388d  push    rdi
0x18005388e  push    r14
0x180053890  push    r15
0x180053892  lea     rbp, [rax-478h]
0x180053899  sub     rsp, 550h
0x1800538a0  mov     [rsp+570h+var_510], 0FFFFFFFFFFFFFFFEh
0x1800538a9  mov     [rax+20h], rbx
0x1800538ad  mov     rax, cs:__security_cookie
0x1800538b4  xor     rax, rsp
0x1800538b7  mov     [rbp+470h+var_30], rax
0x1800538be  mov     rbx, r8
0x1800538c1  mov     rdi, rdx
0x1800538c4  mov     rsi, rcx
0x1800538c7  mov     qword ptr [rsp+570h+var_508], rdx
0x1800538cc  mov     r14d, [rbp+470h+arg_28]
0x1800538d3  mov     r15d, [rbp+470h+arg_30]
0x1800538da  mov     dword ptr [rsp+570h+var_520], 0
0x1800538e2  mov     qword ptr [rdx], 0
0x1800538e9  mov     qword ptr [rdx+8], 0
0x1800538f1  mov     dword ptr [rsp+570h+var_520], 1
0x1800538f9  mov     rcx, [r8]
0x1800538fc  test    rcx, rcx
0x1800538ff  jz      loc_180053A68
0x180053905  mov     [rsp+570h+var_518], 0
0x18005390e  mov     rax, [rcx]
0x180053911  lea     r8, [rsp+570h+var_518]
0x180053916  lea     rdx, IID_I_IrmProtector
0x18005391d  mov     rax, [rax]
0x180053920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053925  test    eax, eax
0x180053927  js      loc_180053A00
0x18005392d  cmp     [rsp+570h+var_518], 0
0x180053933  jz      loc_180053A32
0x180053939  mov     rcx, cs:?s_IrmProtectorWrapperFactory@IProtectorWrapperFactory@InformationProtection@Microsoft@@2V?$shared_ptr@VIProtectorWrapperFactory@InformationProtection@Microsoft@@@tr1@std@@A; std::tr1::shared_ptr<Microsoft::InformationProtection::IProtectorWrapperFactory> Microsoft::InformationProtection::IProtectorWrapperFactory::s_IrmProtectorWrapperFactory
0x180053940  mov     rax, [rcx]
0x180053943  lea     rdx, [rsi+10h]
0x180053947  lea     r9, [rsi+8]
0x18005394b  mov     [rsp+38h], r15d
0x180053950  mov     [rsp+570h+var_540], r14d
0x180053955  mov     qword ptr [rsp+570h+var_548], 0
0x18005395e  mov     qword ptr [rsp+570h+var_550], rdx
0x180053963  mov     r8, rbx
0x180053966  lea     rdx, [rsp+570h+var_500]
0x18005396b  mov     rax, [rax]
0x18005396e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053973  mov     rdx, rax
0x180053976  mov     rcx, rdi
0x180053979  call    ??4?$shared_ptr@VIProtectorWrapper@InformationProtection@Microsoft@@@tr1@std@@QEAAAEAV012@$$QEAV012@@Z; std::tr1::shared_ptr<Microsoft::InformationProtection::IProtectorWrapper>::operator=(std::tr1::shared_ptr<Microsoft::InformationProtection::IProtectorWrapper> &&)
0x18005397e  nop
0x18005397f  mov     rbx, [rsp+570h+var_4F8]
0x180053984  test    rbx, rbx
0x180053987  jz      short loc_1800539C0
0x180053989  or      esi, 0FFFFFFFFh
0x18005398c  mov     eax, esi
0x18005398e  lock xadd [rbx+8], eax
0x180053993  add     eax, esi
0x180053995  jnz     short loc_1800539C0
0x180053997  mov     rax, [rbx]
0x18005399a  mov     rcx, rbx
0x18005399d  mov     rax, [rax]
0x1800539a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800539a5  mov     eax, esi
0x1800539a7  lock xadd [rbx+0Ch], eax
0x1800539ac  add     eax, esi
0x1800539ae  jnz     short loc_1800539C0
0x1800539b0  mov     rax, [rbx]
0x1800539b3  mov     rcx, rbx
0x1800539b6  mov     rax, [rax+8]
0x1800539ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800539bf  nop
0x1800539c0  mov     rcx, [rsp+570h+var_518]
0x1800539c5  test    rcx, rcx
0x1800539c8  jz      short loc_1800539D7
0x1800539ca  mov     rdx, [rcx]
0x1800539cd  mov     rax, [rdx+10h]
0x1800539d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800539d6  nop
0x1800539d7  mov     rax, rdi
0x1800539da  mov     rcx, [rbp+470h+var_30]
0x1800539e1  xor     rcx, rsp; StackCookie
0x1800539e4  call    __security_check_cookie
0x1800539e9  mov     rbx, [rsp+570h+arg_18]
0x1800539f1  add     rsp, 550h
0x1800539f8  pop     r15
0x1800539fa  pop     r14
0x1800539fc  pop     rdi
0x1800539fd  pop     rsi
0x1800539fe  pop     rbp
0x1800539ff  retn
0x180053a00  mov     [rsp+570h+var_550], eax; int
0x180053a04  lea     r9, aPiunknownprote; "pIUnknownProtector->QueryInterface(IID_"...
0x180053a0b  mov     r8d, 0B3h; unsigned int
0x180053a11  lea     rdx, aDsSecurityRmSr_0; "ds\\security\\rm\\src\\client\\promethi"...
0x180053a18  lea     rcx, [rbp+470h+pExceptionObject]; this
0x180053a1c  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180053a21  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180053a28  lea     rcx, [rbp+470h+pExceptionObject]; pExceptionObject
0x180053a2c  call    _CxxThrowException_0
0x180053a32  mov     [rsp+570h+var_550], 80004001h; int
0x180053a3a  lea     r9, Src; unsigned __int16 *
0x180053a41  mov     r8d, 0C2h; unsigned int
0x180053a47  lea     rdx, aDsSecurityRmSr_0; "ds\\security\\rm\\src\\client\\promethi"...
0x180053a4e  lea     rcx, [rbp+470h+pExceptionObject]; this
0x180053a52  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180053a57  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180053a5e  lea     rcx, [rbp+470h+pExceptionObject]; pExceptionObject
0x180053a62  call    _CxxThrowException_0
0x180053a68  mov     [rsp+570h+var_550], 80040154h; int
0x180053a70  lea     r9, Src; unsigned __int16 *
0x180053a77  mov     r8d, 0AEh; unsigned int
0x180053a7d  lea     rdx, aDsSecurityRmSr_0; "ds\\security\\rm\\src\\client\\promethi"...
0x180053a84  lea     rcx, [rbp+470h+pExceptionObject]; this
0x180053a88  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180053a8d  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180053a94  lea     rcx, [rbp+470h+pExceptionObject]; pExceptionObject
0x180053a98  call    _CxxThrowException_0
```
