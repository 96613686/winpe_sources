# Microsoft::HostGuardian::Client::HgServiceController::RequestAndStoreCAIntermediateCert(void)

- ea: `0x18000dab8`
- end: `0x18000dc55`
- name: `?RequestAndStoreCAIntermediateCert@HgServiceController@Client@HostGuardian@Microsoft@@AEAAXXZ`
- size: `413`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::HgServiceController *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d348`

## callees

- `0x18000a7bc`
- `0x18000c45c`
- `0x18000c740`
- `0x18000dab8`
- `0x18000dc5c`
- `0x180014e74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000db35`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000db35`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dbee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dc3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dbee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dc3a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000dadf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000dadf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000db1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000dc0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000db1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000dc0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000db22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dbce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000db22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dbce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbbb`
- `CRYPT32!CertFreeCertificateContext` at `0x18000dbc6`
- `CRYPT32!CertFreeCertificateContext` at `0x18000dbc6`
- `CRYPT32!CertCreateCertificateContext` at `0x18000dba6`
- `CRYPT32!CertCreateCertificateContext` at `0x18000dba6`

## string_xrefs

- `0x18000dc43`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::HgServiceController::RequestAndStoreCAIntermediateCert(
        Microsoft::HostGuardian::Client::HgServiceController *this)
{
  RTL_SRWLOCK *v2; // rsi
  RTL_SRWLOCK *v3; // rbx
  __int64 v4; // rcx
  unsigned int v5; // r8d
  const char *v6; // r9
  DWORD LastError; // ebx
  __int64 v8; // rcx
  __int64 v9; // rax
  PCCERT_CONTEXT CertificateContext; // r12
  const CERT_CONTEXT *v11; // r15
  DWORD v12; // edi
  __int64 *v13; // rdx
  __int64 v14; // [rsp+0h] [rbp-88h] BYREF
  BYTE *pbCertEncoded[2]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v16; // [rsp+30h] [rbp-58h]
  char *v17; // [rsp+38h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  RTL_SRWLOCK *SRWLock; // [rsp+A0h] [rbp+18h]

  v2 = (RTL_SRWLOCK *)((char *)this + 152);
  SRWLock = (RTL_SRWLOCK *)((char *)this + 152);
  AcquireSRWLockShared((PSRWLOCK)this + 19);
  try
  {
    v3 = v2;
    v4 = *((_QWORD *)this + 18);
    if ( !v4 || (unsigned int)Microsoft::HostGuardian::Client::Utilities::GetCertificateDurationStatus(v4) != 1 )
    {
      if ( v2 )
      {
        LastError = GetLastError();
        ReleaseSRWLockShared(v2);
        SetLastError(LastError);
      }
      v3 = 0;
      AcquireSRWLockExclusive(v2);
      v8 = *((_QWORD *)this + 18);
      if ( !v8 || (unsigned int)Microsoft::HostGuardian::Client::Utilities::GetCertificateDurationStatus(v8) != 1 )
      {
        *(_OWORD *)pbCertEncoded = 0;
        v16 = 0;
        v9 = Microsoft::HostGuardian::Client::HgServiceController::RequestCAIntermediateCertificate(this);
        std::vector<unsigned char>::operator=(pbCertEncoded, v9);
        std::vector<unsigned char>::~vector<unsigned char>(&v17);
        CertificateContext = CertCreateCertificateContext(
                               0x10001u,
                               pbCertEncoded[0],
                               LODWORD(pbCertEncoded[1]) - LODWORD(pbCertEncoded[0]));
        v11 = (const CERT_CONTEXT *)*((_QWORD *)this + 18);
        if ( v11 )
        {
          v12 = GetLastError();
          CertFreeCertificateContext(v11);
          SetLastError(v12);
        }
        *((_QWORD *)this + 18) = CertificateContext;
        std::vector<unsigned char>::~vector<unsigned char>((char **)pbCertEncoded);
      }
      if ( v2 )
        ReleaseSRWLockExclusive(v2);
    }
  }
  catch ( ... )
  {
    v13 = &v14;
    if ( *((_QWORD *)this + 18)
      || (unsigned int)Microsoft::HostGuardian::Client::Utilities::GetCertificateDurationStatus(*((_QWORD *)this + 18)) != 2 )
    {
      wil::details::in1diag3::Throw_CaughtException(retaddr, v13, v5, v6);
    }
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x270,
      (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
      v6);
    std::vector<unsigned char>::~vector<unsigned char>((char **)pbCertEncoded);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return;
  }
  if ( !*((_QWORD *)this + 18) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x27E,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
      v6);
  if ( v3 )
    ReleaseSRWLockShared(v3);
}

```

## disassembly

```asm
0x18000dab8  mov     [rsp+arg_0], rcx
0x18000dabd  push    rbx
0x18000dabe  push    rsi
0x18000dabf  push    rdi
0x18000dac0  push    r12
0x18000dac2  push    r14
0x18000dac4  push    r15
0x18000dac6  sub     rsp, 58h
0x18000daca  mov     r14, rcx
0x18000dacd  lea     rsi, [rcx+98h]
0x18000dad4  mov     [rsp+88h+SRWLock], rsi
0x18000dadc  mov     rcx, rsi; SRWLock
0x18000dadf  call    cs:__imp_AcquireSRWLockShared
0x18000dae5  mov     rbx, rsi
0x18000dae8  mov     [rsp+88h+arg_8], rbx
0x18000daf0  mov     rcx, [r14+90h]
0x18000daf7  test    rcx, rcx
0x18000dafa  jz      short loc_18000DB0A
0x18000dafc  call    ?GetCertificateDurationStatus@Utilities@Client@HostGuardian@Microsoft@@YA?AW4DurationStatus@1234@PEBU_CERT_CONTEXT@@@Z; Microsoft::HostGuardian::Client::Utilities::GetCertificateDurationStatus(_CERT_CONTEXT const *)
0x18000db01  cmp     eax, 1
0x18000db04  jz      loc_18000DBF4
0x18000db0a  test    rsi, rsi
0x18000db0d  jz      short loc_18000DB28
0x18000db0f  call    cs:__imp_GetLastError
0x18000db15  mov     ebx, eax
0x18000db17  mov     rcx, rsi; SRWLock
0x18000db1a  call    cs:__imp_ReleaseSRWLockShared
0x18000db20  mov     ecx, ebx; dwErrCode
0x18000db22  call    cs:__imp_SetLastError
0x18000db28  xor     ebx, ebx
0x18000db2a  mov     [rsp+88h+arg_8], rbx
0x18000db32  mov     rcx, rsi; SRWLock
0x18000db35  call    cs:__imp_AcquireSRWLockExclusive
0x18000db3b  mov     [rsp+88h+arg_18], rsi
0x18000db43  mov     rcx, [r14+90h]
0x18000db4a  test    rcx, rcx
0x18000db4d  jz      short loc_18000DB5D
0x18000db4f  call    ?GetCertificateDurationStatus@Utilities@Client@HostGuardian@Microsoft@@YA?AW4DurationStatus@1234@PEBU_CERT_CONTEXT@@@Z; Microsoft::HostGuardian::Client::Utilities::GetCertificateDurationStatus(_CERT_CONTEXT const *)
0x18000db54  cmp     eax, 1
0x18000db57  jz      loc_18000DBE6
0x18000db5d  xorps   xmm0, xmm0
0x18000db60  movdqu  xmmword ptr [rsp+88h+pbCertEncoded], xmm0
0x18000db66  mov     [rsp+88h+var_58], 0
0x18000db6f  lea     rdx, [rsp+88h+var_50]
0x18000db74  mov     rcx, r14; this
0x18000db77  call    ?RequestCAIntermediateCertificate@HgServiceController@Client@HostGuardian@Microsoft@@AEAA?AV?$vector@EV?$allocator@E@std@@@std@@XZ; Microsoft::HostGuardian::Client::HgServiceController::RequestCAIntermediateCertificate(void)
0x18000db7c  mov     rdx, rax
0x18000db7f  lea     rcx, [rsp+88h+pbCertEncoded]
0x18000db84  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x18000db89  lea     rcx, [rsp+88h+var_50]
0x18000db8e  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000db93  nop
0x18000db94  mov     r8d, dword ptr [rsp+88h+pbCertEncoded+8]
0x18000db99  mov     rdx, [rsp+88h+pbCertEncoded]; pbCertEncoded
0x18000db9e  sub     r8d, edx; cbCertEncoded
0x18000dba1  mov     ecx, 10001h; dwCertEncodingType
0x18000dba6  call    cs:__imp_CertCreateCertificateContext
0x18000dbac  mov     r12, rax
0x18000dbaf  mov     r15, [r14+90h]
0x18000dbb6  test    r15, r15
0x18000dbb9  jz      short loc_18000DBD4
0x18000dbbb  call    cs:__imp_GetLastError
0x18000dbc1  mov     edi, eax
0x18000dbc3  mov     rcx, r15; pCertContext
0x18000dbc6  call    cs:__imp_CertFreeCertificateContext
0x18000dbcc  mov     ecx, edi; dwErrCode
0x18000dbce  call    cs:__imp_SetLastError
0x18000dbd4  mov     [r14+90h], r12
0x18000dbdb  lea     rcx, [rsp+88h+pbCertEncoded]
0x18000dbe0  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000dbe5  nop
0x18000dbe6  test    rsi, rsi
0x18000dbe9  jz      short loc_18000DBF4
0x18000dbeb  mov     rcx, rsi; SRWLock
0x18000dbee  call    cs:__imp_ReleaseSRWLockExclusive
0x18000dbf4  mov     rcx, [rsp+88h]; this
0x18000dbfc  cmp     qword ptr [r14+90h], 0
0x18000dc04  jz      short loc_18000DC43
0x18000dc06  test    rbx, rbx
0x18000dc09  jz      short loc_18000DC14
0x18000dc0b  mov     rcx, rbx; SRWLock
0x18000dc0e  call    cs:__imp_ReleaseSRWLockShared
0x18000dc14  add     rsp, 58h
0x18000dc18  pop     r15
0x18000dc1a  pop     r14
0x18000dc1c  pop     r12
0x18000dc1e  pop     rdi
0x18000dc1f  pop     rsi
0x18000dc20  pop     rbx
0x18000dc21  retn
0x18000dc22  lea     rcx, [rsp+88h+pbCertEncoded]
0x18000dc27  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000dc2c  nop
0x18000dc2d  mov     rcx, [rsp+88h+SRWLock]; SRWLock
0x18000dc35  test    rcx, rcx
0x18000dc38  jz      short loc_18000DC41
0x18000dc3a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000dc40  nop
0x18000dc41  jmp     short loc_18000DC14
0x18000dc43  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000dc4a  mov     edx, 27Eh; void *
0x18000dc4f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
