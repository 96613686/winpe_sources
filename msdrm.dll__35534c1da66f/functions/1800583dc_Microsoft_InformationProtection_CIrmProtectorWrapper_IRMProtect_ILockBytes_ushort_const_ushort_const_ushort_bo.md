# Microsoft::InformationProtection::CIrmProtectorWrapper::IRMProtect(ILockBytes *,ushort const *,ushort const *,ushort * *,bool)

- ea: `0x1800583dc`
- end: `0x1800589df`
- name: `?IRMProtect@CIrmProtectorWrapper@InformationProtection@Microsoft@@AEAAXPEAUILockBytes@@PEBG1PEAPEAG_N@Z`
- size: `1539`
- prototype: `void __fastcall(Microsoft::InformationProtection::CIrmProtectorWrapper *__hidden this, struct ILockBytes *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180058ae0`
- `0x180058ca0`

## callees

- `0x18000343a`
- `0x1800516b8`
- `0x1800583dc`
- `0x18005a9cc`
- `0x18005bdc0`
- `0x18005f010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800586aa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800586aa`

## string_xrefs

- `0x180058752`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\irmprotectorwrapper\cirmprotectorwrapper.cpp`
- `0x180058788`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\irmprotectorwrapper\cirmprotectorwrapper.cpp`
- `0x1800587ba`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\irmprotectorwrapper\cirmprotectorwrapper.cpp`
- `0x1800587f0`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\irmprotectorwrapper\cirmprotectorwrapper.cpp`
- `0x180058826`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\irmprotectorwrapper\cirmprotectorwrapper.cpp`
- `0x180058858`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\irmprotectorwrapper\cirmprotectorwrapper.cpp`
- `0x18005888e`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\irmprotectorwrapper\cirmprotectorwrapper.cpp`
- `0x1800588c4`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\irmprotectorwrapper\cirmprotectorwrapper.cpp`
- `0x1800588f6`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\irmprotectorwrapper\cirmprotectorwrapper.cpp`
- `0x180058928`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\irmprotectorwrapper\cirmprotectorwrapper.cpp`
- `0x18005895a`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\irmprotectorwrapper\cirmprotectorwrapper.cpp`
- `0x18005898c`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\irmprotectorwrapper\cirmprotectorwrapper.cpp`
- `0x1800589be`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\irmprotectorwrapper\cirmprotectorwrapper.cpp`
- `0x18005891b`: `pIrmDocument->HrInit(m_pIrmClient, wszTemplate, wszEmailAddress, fEncrypt)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Microsoft::InformationProtection::CIrmProtectorWrapper::IRMProtect(
        Microsoft::InformationProtection::CIrmProtectorWrapper *this,
        struct ILockBytes *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 **a5,
        bool a6)
{
  __int64 v7; // r13
  int v8; // eax
  _QWORD *v9; // rsi
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  volatile signed __int32 *v13; // rbx
  volatile signed __int32 *v14; // rbx
  int v15; // eax
  __int64 v16; // rdi
  int v17; // eax
  int v18; // eax
  __int64 *v19; // rcx
  __int64 v20; // rax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // ebx
  unsigned __int16 *v25; // rax
  OLECHAR *v26; // rcx
  unsigned __int16 *v27; // [rsp+30h] [rbp-D0h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v29; // [rsp+40h] [rbp-C0h] BYREF
  struct ILockBytes *v30; // [rsp+48h] [rbp-B8h]
  __int64 v31; // [rsp+50h] [rbp-B0h]
  __int64 v32; // [rsp+58h] [rbp-A8h] BYREF
  volatile signed __int32 *v33; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v34; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v35; // [rsp+70h] [rbp-90h]
  __int64 v36; // [rsp+78h] [rbp-88h]
  char v37; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pExceptionObject[1216]; // [rsp+90h] [rbp-70h] BYREF

  v36 = -2;
  v34 = a4;
  v35 = a3;
  v30 = a2;
  v29 = 0;
  v31 = 0;
  LODWORD(v27) = 0;
  bstrString = 0;
  if ( a6 && !a5 )
  {
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\irmprotectorwrapper\\cirmprotectorwrapper.cpp",
      0xC0u,
      L"pbstrContentId",
      -2147024809);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  v7 = *((_QWORD *)this + 5);
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 **))(**((_QWORD **)this + 3) + 32LL))(
         *((_QWORD *)this + 3),
         v7,
         &v27);
  if ( v8 < 0 )
  {
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\irmprotectorwrapper\\cirmprotectorwrapper.cpp",
      0xC3u,
      L"m_pIrmProtector->HrIsProtected(pilbIn, &dwStatus)",
      v8);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  if ( (_DWORD)v27 != 1 && (_DWORD)v27 != 2 )
  {
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\irmprotectorwrapper\\cirmprotectorwrapper.cpp",
      0xC6u,
      &Src,
      -2147168382);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  if ( a6 )
  {
    if ( (_DWORD)v27 == 1 )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\irmprotectorwrapper\\cirmprotectorwrapper.cpp",
        0xCAu,
        &Src,
        -2147168377);
      throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
    }
  }
  else if ( (_DWORD)v27 == 2 )
  {
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\irmprotectorwrapper\\cirmprotectorwrapper.cpp",
      0xCEu,
      &Src,
      -2147168376);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  LODWORD(v27) = 0;
  v9 = (_QWORD *)((char *)this + 8);
  if ( *((_QWORD *)this + 1) )
  {
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\irmprotectorwrapper\\cirmprotectorwrapper.cpp",
      0xD9u,
      &Src,
      -2147418113);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  v10 = (**(__int64 (__fastcall ***)(__int64, __int64 *))Microsoft::InformationProtection::IIrmClientFactory::s_IrmClientFactory)(
          Microsoft::InformationProtection::IIrmClientFactory::s_IrmClientFactory,
          &v32);
  if ( &v37 == (char *)v10 )
  {
    v11 = 0;
    v12 = 0;
  }
  else
  {
    v11 = *(_QWORD *)(v10 + 8);
    *(_QWORD *)(v10 + 8) = 0;
    v12 = *(_QWORD *)v10;
    *(_QWORD *)v10 = 0;
  }
  v13 = (volatile signed __int32 *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = v11;
  *v9 = v12;
  if ( v13 )
  {
    if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  v14 = v33;
  if ( v33 )
  {
    if ( _InterlockedExchangeAdd(v33 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v9 + 8LL))(
          *v9,
          *((unsigned int *)this + 14),
          *((unsigned int *)this + 15));
  if ( v15 < 0 )
  {
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\irmprotectorwrapper\\cirmprotectorwrapper.cpp",
      0xD5u,
      L"m_pIrmClient->HrInit(m_hEnv, m_hDefaultLibrary)",
      v15);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  v16 = *(_QWORD *)(**(__int64 (__fastcall ***)(__int64, __int64 *))Microsoft::InformationProtection::IIrmDocumentFactory::s_IrmDocumentFactory)(
                     Microsoft::InformationProtection::IIrmDocumentFactory::s_IrmDocumentFactory,
                     &v32);
  v31 = v16;
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  v17 = (*(__int64 (__fastcall **)(__int64, char *, const unsigned __int16 *, const unsigned __int16 *, bool))(*(_QWORD *)v16 + 88LL))(
          v16,
          (char *)this + 8,
          v35,
          v34,
          a6);
  if ( v17 < 0 )
  {
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\irmprotectorwrapper\\cirmprotectorwrapper.cpp",
      0xDEu,
      L"pIrmDocument->HrInit(m_pIrmClient, wszTemplate, wszEmailAddress, fEncrypt)",
      v17);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  v18 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v16)(v16, &IID_I_IrmPolicyInfoRMS, &v29);
  if ( v18 < 0 )
  {
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\irmprotectorwrapper\\cirmprotectorwrapper.cpp",
      0xDFu,
      L"pIrmDocument->QueryInterface(IID_I_IrmPolicyInfoRMS, (void**)&pIrmPolicyInfoRMS)",
      v18);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  v19 = (__int64 *)*((_QWORD *)this + 3);
  v20 = *v19;
  if ( a6 )
  {
    v21 = (*(__int64 (__fastcall **)(__int64 *, __int64, struct ILockBytes *, __int64, unsigned __int16 **))(v20 + 48))(
            v19,
            v7,
            v30,
            v29,
            &v27);
    if ( v21 < 0 )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\irmprotectorwrapper\\cirmprotectorwrapper.cpp",
        0xE3u,
        L"m_pIrmProtector->HrProtectRMS(pilbIn, pilbOutputByteStream, pIrmPolicyInfoRMS, &dwStatus)",
        v21);
      throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
    }
    v22 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v16 + 96LL))(v16, &bstrString);
    if ( v22 < 0 )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\irmprotectorwrapper\\cirmprotectorwrapper.cpp",
        0xE4u,
        L"pIrmDocument->HrGetContentId(&bstrContentId)",
        v22);
      throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
    }
  }
  else
  {
    v23 = (*(__int64 (__fastcall **)(__int64 *, __int64, struct ILockBytes *, __int64, unsigned __int16 **))(v20 + 56))(
            v19,
            v7,
            v30,
            v29,
            &v27);
    if ( v23 < 0 )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\irmprotectorwrapper\\cirmprotectorwrapper.cpp",
        0xE8u,
        L"m_pIrmProtector->HrUnprotectRMS(pilbIn, pilbOutputByteStream, pIrmPolicyInfoRMS, &dwStatus)",
        v23);
      throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
    }
  }
  v24 = -2147467259;
  if ( (_DWORD)v27 != 1 && (_DWORD)v27 != 2 )
  {
    switch ( (_DWORD)v27 )
    {
      case 7:
        v24 = -2147168378;
        break;
      case 9:
        v24 = -2147168382;
        break;
      case 0xA:
        v24 = -2147168381;
        break;
      case 0xB:
        v24 = -2147168379;
        break;
      case 0xC:
        v24 = -2147168380;
        break;
    }
    Microsoft::InformationProtection::DebugLog(
      (Microsoft::InformationProtection *)L"MapStatusToHresult original status code: %d",
      (const unsigned __int16 *)(unsigned int)v27);
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\irmprotectorwrapper\\cirmprotectorwrapper.cpp",
      0xECu,
      L"MapStatusToHresult(dwStatus)",
      v24);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  if ( a6 )
  {
    v25 = bstrString;
    v26 = 0;
    bstrString = 0;
    *a5 = v25;
  }
  else
  {
    v26 = bstrString;
  }
  SysFreeString(v26);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
}

```

## disassembly

```asm
0x1800583dc  push    rbp
0x1800583de  push    rbx
0x1800583df  push    rsi
0x1800583e0  push    rdi
0x1800583e1  push    r12
0x1800583e3  push    r13
0x1800583e5  push    r14
0x1800583e7  push    r15
0x1800583e9  lea     rbp, [rsp-468h]
0x1800583f1  sub     rsp, 568h
0x1800583f8  mov     [rsp+5A0h+var_528], 0FFFFFFFFFFFFFFFEh
0x180058401  mov     rax, cs:__security_cookie
0x180058408  xor     rax, rsp
0x18005840b  mov     [rbp+4A0h+var_50], rax
0x180058412  mov     [rsp+5A0h+var_538], r9
0x180058417  mov     [rsp+5A0h+var_530], r8
0x18005841c  mov     [rsp+5A0h+var_558], rdx
0x180058421  mov     r15, rcx
0x180058424  mov     r12, [rbp+4A0h+arg_20]
0x18005842b  xor     edi, edi
0x18005842d  mov     [rsp+5A0h+var_560], rdi
0x180058432  mov     [rsp+5A0h+var_550], rdi
0x180058437  mov     dword ptr [rsp+5A0h+var_570], edi
0x18005843b  mov     [rsp+5A0h+bstrString], rdi
0x180058440  movzx   r14d, [rbp+4A0h+arg_28]
0x180058448  test    r14b, r14b
0x18005844b  jz      short loc_180058456
0x18005844d  test    r12, r12
0x180058450  jz      loc_180058811
0x180058456  mov     r13, [rcx+28h]
0x18005845a  mov     rcx, [rcx+18h]
0x18005845e  mov     rax, [rcx]
0x180058461  lea     r8, [rsp+5A0h+var_570]
0x180058466  mov     rdx, r13
0x180058469  mov     rax, [rax+20h]
0x18005846d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058472  test    eax, eax
0x180058474  js      loc_180058847
0x18005847a  mov     eax, dword ptr [rsp+5A0h+var_570]
0x18005847e  cmp     eax, 1
0x180058481  jz      short loc_18005848C
0x180058483  cmp     eax, 2
0x180058486  jnz     loc_180058879
0x18005848c  test    r14b, r14b
0x18005848f  jz      short loc_18005849C
0x180058491  cmp     eax, 1
0x180058494  jz      loc_180058773
0x18005849a  jmp     short loc_1800584A5
0x18005849c  cmp     eax, 2
0x18005849f  jz      loc_1800588AF
0x1800584a5  mov     dword ptr [rsp+5A0h+var_570], edi
0x1800584a9  lea     rsi, [r15+8]
0x1800584ad  cmp     [rsi], rdi
0x1800584b0  jnz     loc_1800587DB
0x1800584b6  mov     rcx, qword ptr cs:?s_IrmClientFactory@IIrmClientFactory@InformationProtection@Microsoft@@2V?$shared_ptr@VIIrmClientFactory@InformationProtection@Microsoft@@@tr1@std@@A; std::tr1::shared_ptr<Microsoft::InformationProtection::IIrmClientFactory> Microsoft::InformationProtection::IIrmClientFactory::s_IrmClientFactory
0x1800584bd  mov     rax, [rcx]
0x1800584c0  lea     rdx, [rsp+5A0h+var_548]
0x1800584c5  mov     rax, [rax]
0x1800584c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800584cd  lea     rcx, [rbp+4A0h+var_520]
0x1800584d1  cmp     rcx, rax
0x1800584d4  jz      short loc_1800584E6
0x1800584d6  mov     rcx, [rax+8]
0x1800584da  mov     [rax+8], rdi
0x1800584de  mov     rdx, [rax]
0x1800584e1  mov     [rax], rdi
0x1800584e4  jmp     short loc_1800584EC
0x1800584e6  mov     rcx, rdi
0x1800584e9  mov     rdx, rdi
0x1800584ec  mov     rbx, [rsi+8]
0x1800584f0  mov     [rsi+8], rcx
0x1800584f4  mov     [rsi], rdx
0x1800584f7  test    rbx, rbx
0x1800584fa  jz      short loc_180058534
0x1800584fc  or      eax, 0FFFFFFFFh
0x1800584ff  lock xadd [rbx+8], eax
0x180058504  cmp     eax, 1
0x180058507  jnz     short loc_180058534
0x180058509  mov     rax, [rbx]
0x18005850c  mov     rcx, rbx
0x18005850f  mov     rax, [rax]
0x180058512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058517  or      eax, 0FFFFFFFFh
0x18005851a  lock xadd [rbx+0Ch], eax
0x18005851f  cmp     eax, 1
0x180058522  jnz     short loc_180058534
0x180058524  mov     rax, [rbx]
0x180058527  mov     rcx, rbx
0x18005852a  mov     rax, [rax+8]
0x18005852e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058533  nop
0x180058534  mov     rbx, [rsp+5A0h+var_540]
0x180058539  test    rbx, rbx
0x18005853c  jz      short loc_180058576
0x18005853e  or      eax, 0FFFFFFFFh
0x180058541  lock xadd [rbx+8], eax
0x180058546  cmp     eax, 1
0x180058549  jnz     short loc_180058576
0x18005854b  mov     rax, [rbx]
0x18005854e  mov     rcx, rbx
0x180058551  mov     rax, [rax]
0x180058554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058559  or      eax, 0FFFFFFFFh
0x18005855c  lock xadd [rbx+0Ch], eax
0x180058561  cmp     eax, 1
0x180058564  jnz     short loc_180058576
0x180058566  mov     rax, [rbx]
0x180058569  mov     rcx, rbx
0x18005856c  mov     rax, [rax+8]
0x180058570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058575  nop
0x180058576  mov     rcx, [rsi]
0x180058579  mov     rax, [rcx]
0x18005857c  mov     r8d, [r15+3Ch]
0x180058580  mov     edx, [r15+38h]
0x180058584  mov     rax, [rax+8]
0x180058588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005858d  test    eax, eax
0x18005858f  js      loc_1800588E5
0x180058595  mov     rcx, qword ptr cs:?s_IrmDocumentFactory@IIrmDocumentFactory@InformationProtection@Microsoft@@2V?$shared_ptr@VIIrmDocumentFactory@InformationProtection@Microsoft@@@tr1@std@@A; std::tr1::shared_ptr<Microsoft::InformationProtection::IIrmDocumentFactory> Microsoft::InformationProtection::IIrmDocumentFactory::s_IrmDocumentFactory
0x18005859c  mov     rax, [rcx]
0x18005859f  lea     rdx, [rsp+5A0h+var_548]
0x1800585a4  mov     rax, [rax]
0x1800585a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800585ac  mov     rdi, [rax]
0x1800585af  mov     [rsp+5A0h+var_550], rdi
0x1800585b4  mov     rcx, [rsp+5A0h+var_548]
0x1800585b9  test    rcx, rcx
0x1800585bc  jz      short loc_1800585CB
0x1800585be  mov     rax, [rcx]
0x1800585c1  mov     rax, [rax+10h]
0x1800585c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800585ca  nop
0x1800585cb  mov     rax, [rdi]
0x1800585ce  mov     [rsp+5A0h+var_580], r14d
0x1800585d3  mov     r9, [rsp+5A0h+var_538]
0x1800585d8  mov     r8, [rsp+5A0h+var_530]
0x1800585dd  mov     rdx, rsi
0x1800585e0  mov     rcx, rdi
0x1800585e3  mov     rax, [rax+58h]
0x1800585e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800585ec  test    eax, eax
0x1800585ee  js      loc_180058917
0x1800585f4  mov     rax, [rdi]
0x1800585f7  lea     r8, [rsp+5A0h+var_560]
0x1800585fc  lea     rdx, IID_I_IrmPolicyInfoRMS
0x180058603  mov     rcx, rdi
0x180058606  mov     rax, [rax]
0x180058609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005860e  test    eax, eax
0x180058610  js      loc_180058949
0x180058616  mov     rcx, [r15+18h]
0x18005861a  mov     rax, [rcx]
0x18005861d  lea     rdx, [rsp+5A0h+var_570]
0x180058622  mov     r9, [rsp+5A0h+var_560]
0x180058627  mov     r8, [rsp+5A0h+var_558]
0x18005862c  mov     qword ptr [rsp+5A0h+var_580], rdx
0x180058631  mov     rdx, r13
0x180058634  test    r14b, r14b
0x180058637  jz      short loc_180058668
0x180058639  mov     rax, [rax+30h]
0x18005863d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058642  test    eax, eax
0x180058644  js      loc_18005897B
0x18005864a  mov     rax, [rdi]
0x18005864d  lea     rdx, [rsp+5A0h+bstrString]
0x180058652  mov     rcx, rdi
0x180058655  mov     rax, [rax+60h]
0x180058659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005865e  test    eax, eax
0x180058660  js      loc_1800587A9
0x180058666  jmp     short loc_180058679
0x180058668  mov     rax, [rax+38h]
0x18005866c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058671  test    eax, eax
0x180058673  js      loc_1800589AD
0x180058679  mov     edx, dword ptr [rsp+5A0h+var_570]; unsigned __int16 *
0x18005867d  mov     ebx, 80004005h
0x180058682  mov     eax, edx
0x180058684  sub     eax, 1
0x180058687  jz      short loc_18005868E
0x180058689  sub     eax, 1
0x18005868c  jnz     short loc_1800586FB
0x18005868e  test    r14b, r14b
0x180058691  jz      short loc_1800586A5
0x180058693  mov     rax, [rsp+5A0h+bstrString]
0x180058698  xor     ecx, ecx
0x18005869a  mov     [rsp+5A0h+bstrString], rcx
0x18005869f  mov     [r12], rax
0x1800586a3  jmp     short loc_1800586AA
0x1800586a5  mov     rcx, [rsp+5A0h+bstrString]; bstrString
0x1800586aa  call    cs:__imp_SysFreeString
0x1800586b0  nop
0x1800586b1  mov     rax, [rdi]
0x1800586b4  mov     rcx, rdi
0x1800586b7  mov     rax, [rax+10h]
0x1800586bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800586c0  nop
0x1800586c1  mov     rcx, [rsp+5A0h+var_560]
0x1800586c6  test    rcx, rcx
0x1800586c9  jz      short loc_1800586D8
0x1800586cb  mov     rax, [rcx]
0x1800586ce  mov     rax, [rax+10h]
0x1800586d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800586d7  nop
0x1800586d8  mov     rcx, [rbp+4A0h+var_50]
0x1800586df  xor     rcx, rsp; StackCookie
0x1800586e2  call    __security_check_cookie
0x1800586e7  add     rsp, 568h
0x1800586ee  pop     r15
0x1800586f0  pop     r14
0x1800586f2  pop     r13
0x1800586f4  pop     r12
0x1800586f6  pop     rdi
0x1800586f7  pop     rsi
0x1800586f8  pop     rbx
0x1800586f9  pop     rbp
0x1800586fa  retn
0x1800586fb  sub     eax, 5
0x1800586fe  jz      short loc_180058730
0x180058700  sub     eax, 2
0x180058703  jz      short loc_180058729
0x180058705  sub     eax, 1
0x180058708  jz      short loc_180058722
0x18005870a  sub     eax, 1
0x18005870d  jz      short loc_18005871B
0x18005870f  cmp     eax, 1
0x180058712  jnz     short loc_180058735
0x180058714  mov     ebx, 8004CF84h
0x180058719  jmp     short loc_180058735
0x18005871b  mov     ebx, 8004CF85h
0x180058720  jmp     short loc_180058735
0x180058722  mov     ebx, 8004CF83h
0x180058727  jmp     short loc_180058735
0x180058729  mov     ebx, 8004CF82h
0x18005872e  jmp     short loc_180058735
0x180058730  mov     ebx, 8004CF86h
0x180058735  lea     rcx, aMapstatustohre; "MapStatusToHresult original status code"...
0x18005873c  call    ?DebugLog@InformationProtection@Microsoft@@YAXPEBGZZ; Microsoft::InformationProtection::DebugLog(ushort const *,...)
0x180058741  mov     [rsp+5A0h+var_580], ebx; int
0x180058745  lea     r9, aMapstatustohre_0; "MapStatusToHresult(dwStatus)"
0x18005874c  mov     r8d, 0ECh; unsigned int
0x180058752  lea     rdx, aDsSecurityRmSr_3; "ds\\security\\rm\\src\\client\\promethi"...
0x180058759  lea     rcx, [rbp+4A0h+pExceptionObject]; this
0x18005875d  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180058762  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180058769  lea     rcx, [rbp+4A0h+pExceptionObject]; pExceptionObject
0x18005876d  call    _CxxThrowException_0
0x180058773  mov     [rsp+5A0h+var_580], 8004CF87h; int
0x18005877b  lea     r9, Src; unsigned __int16 *
0x180058782  mov     r8d, 0CAh; unsigned int
0x180058788  lea     rdx, aDsSecurityRmSr_3; "ds\\security\\rm\\src\\client\\promethi"...
0x18005878f  lea     rcx, [rbp+4A0h+pExceptionObject]; this
0x180058793  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180058798  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x18005879f  lea     rcx, [rbp+4A0h+pExceptionObject]; pExceptionObject
0x1800587a3  call    _CxxThrowException_0
0x1800587a9  mov     [rsp+5A0h+var_580], eax; int
0x1800587ad  lea     r9, aPirmdocumentHr_0; "pIrmDocument->HrGetContentId(&bstrConte"...
0x1800587b4  mov     r8d, 0E4h; unsigned int
0x1800587ba  lea     rdx, aDsSecurityRmSr_3; "ds\\security\\rm\\src\\client\\promethi"...
0x1800587c1  lea     rcx, [rbp+4A0h+pExceptionObject]; this
0x1800587c5  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800587ca  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x1800587d1  lea     rcx, [rbp+4A0h+pExceptionObject]; pExceptionObject
0x1800587d5  call    _CxxThrowException_0
0x1800587db  mov     [rsp+5A0h+var_580], 8000FFFFh; int
0x1800587e3  lea     r9, Src; unsigned __int16 *
0x1800587ea  mov     r8d, 0D9h; unsigned int
0x1800587f0  lea     rdx, aDsSecurityRmSr_3; "ds\\security\\rm\\src\\client\\promethi"...
0x1800587f7  lea     rcx, [rbp+4A0h+pExceptionObject]; this
0x1800587fb  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180058800  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180058807  lea     rcx, [rbp+4A0h+pExceptionObject]; pExceptionObject
0x18005880b  call    _CxxThrowException_0
0x180058811  mov     [rsp+5A0h+var_580], 80070057h; int
0x180058819  lea     r9, aPbstrcontentid; "pbstrContentId"
0x180058820  mov     r8d, 0C0h; unsigned int
0x180058826  lea     rdx, aDsSecurityRmSr_3; "ds\\security\\rm\\src\\client\\promethi"...
0x18005882d  lea     rcx, [rbp+4A0h+pExceptionObject]; this
0x180058831  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180058836  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x18005883d  lea     rcx, [rbp+4A0h+pExceptionObject]; pExceptionObject
0x180058841  call    _CxxThrowException_0
0x180058847  mov     [rsp+5A0h+var_580], eax; int
0x18005884b  lea     r9, aMPirmprotector; "m_pIrmProtector->HrIsProtected(pilbIn, "...
0x180058852  mov     r8d, 0C3h; unsigned int
0x180058858  lea     rdx, aDsSecurityRmSr_3; "ds\\security\\rm\\src\\client\\promethi"...
0x18005885f  lea     rcx, [rbp+4A0h+pExceptionObject]; this
0x180058863  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180058868  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x18005886f  lea     rcx, [rbp+4A0h+pExceptionObject]; pExceptionObject
0x180058873  call    _CxxThrowException_0
0x180058879  mov     [rsp+5A0h+var_580], 8004CF82h; int
0x180058881  lea     r9, Src; unsigned __int16 *
0x180058888  mov     r8d, 0C6h; unsigned int
0x18005888e  lea     rdx, aDsSecurityRmSr_3; "ds\\security\\rm\\src\\client\\promethi"...
0x180058895  lea     rcx, [rbp+4A0h+pExceptionObject]; this
0x180058899  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18005889e  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
  ... truncated ...
```
