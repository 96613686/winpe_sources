# Microsoft::Windows::MDM::OmadmClient::CertificateManager::IsAccountConfiguredToUseClientCert(tagOMADMACCTINFO &,int *)

- ea: `0x140022a90`
- end: `0x140022b69`
- name: `?IsAccountConfiguredToUseClientCert@CertificateManager@OmadmClient@MDM@Windows@Microsoft@@UEAAJAEAUtagOMADMACCTINFO@@PEAH@Z`
- size: `217`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::CertificateManager *__hidden this, struct tagOMADMACCTINFO *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000e610`
- `0x140013404`
- `0x14001391c`
- `0x140022a90`

## import_xrefs

- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140022b00`
- `omadmapi!__imp_OmaDmGetValueFromStruct` at `0x140022b00`

## string_xrefs

- `0x140022abc`: `IsAccountConfiguredToUseClientCert`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::CertificateManager::IsAccountConfiguredToUseClientCert(
        Microsoft::Windows::MDM::OmadmClient::CertificateManager *this,
        struct tagOMADMACCTINFO *a2,
        int *a3)
{
  int ValueFromStruct; // eax
  unsigned int v6; // ebx
  struct COmaDmLogger *Logger; // rax
  _QWORD v9[3]; // [rsp+30h] [rbp-30h] BYREF
  int v10; // [rsp+48h] [rbp-18h]
  int *v11; // [rsp+50h] [rbp-10h]
  int v12; // [rsp+80h] [rbp+20h] BYREF
  _QWORD *v13; // [rsp+88h] [rbp+28h] BYREF

  v12 = 0;
  v9[0] = 0;
  v9[1] = "IsAccountConfiguredToUseClientCert";
  v9[2] = COmaDmLogger::GetLogger();
  v10 = 2;
  v11 = &v12;
  v13 = 0;
  *a3 = 1;
  ValueFromStruct = OmaDmGetValueFromStruct(23, a2, 0xFFFFFFFFLL, &v13, 0);
  v6 = ValueFromStruct;
  v12 = ValueFromStruct;
  if ( ValueFromStruct >= 0 )
  {
    if ( !*v13 )
    {
      Logger = COmaDmLogger::GetLogger();
      Microsoft::Windows::TelemetryLogger::LogMeasure(Logger, 1, 3001, 0);
      *a3 = 0;
    }
    v6 = 0;
  }
  else
  {
    LODWORD(v9[0]) = 6031;
    HIDWORD(v9[0]) = ValueFromStruct;
  }
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v9);
  return v6;
}

```

## disassembly

```asm
0x140022a90  mov     [rsp-8+arg_0], rbx
0x140022a95  mov     [rsp-8+arg_8], rdi
0x140022a9a  push    rbp
0x140022a9b  mov     rbp, rsp
0x140022a9e  sub     rsp, 60h
0x140022aa2  mov     rdi, r8
0x140022aa5  mov     rbx, rdx
0x140022aa8  mov     [rbp+arg_10], 0
0x140022aaf  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x140022ab4  mov     [rbp+var_30], 0
0x140022abc  lea     rcx, aIsaccountconfi; "IsAccountConfiguredToUseClientCert"
0x140022ac3  mov     [rbp+var_28], rcx
0x140022ac7  mov     [rbp+var_20], rax
0x140022acb  mov     [rbp+var_18], 2
0x140022ad2  lea     rax, [rbp+arg_10]
0x140022ad6  mov     [rbp+var_10], rax
0x140022ada  mov     [rbp+arg_18], 0
0x140022ae2  mov     dword ptr [rdi], 1
0x140022ae8  mov     [rsp+60h+var_40], 0
0x140022af1  lea     r9, [rbp+arg_18]
0x140022af5  or      r8d, 0FFFFFFFFh
0x140022af9  mov     rdx, rbx
0x140022afc  lea     ecx, [r8+18h]
0x140022b00  call    cs:__imp_OmaDmGetValueFromStruct
0x140022b07  nop     dword ptr [rax+rax+00h]
0x140022b0c  mov     ebx, eax
0x140022b0e  mov     [rbp+arg_10], eax
0x140022b11  test    eax, eax
0x140022b13  jns     short loc_140022B21
0x140022b15  mov     dword ptr [rbp+var_30], 178Fh
0x140022b1c  mov     dword ptr [rbp+var_30+4], eax
0x140022b1f  jmp     short loc_140022B4D
0x140022b21  mov     rax, [rbp+arg_18]
0x140022b25  cmp     qword ptr [rax], 0
0x140022b29  jnz     short loc_140022B4B
0x140022b2b  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x140022b30  xor     r9d, r9d
0x140022b33  lea     edx, [r9+1]
0x140022b37  mov     r8d, 0BB9h
0x140022b3d  mov     rcx, rax
0x140022b40  call    ?LogMeasure@TelemetryLogger@Windows@Microsoft@@QEAAXW4TracingLevel@23@KPEBGZZ; Microsoft::Windows::TelemetryLogger::LogMeasure(Microsoft::Windows::TracingLevel,ulong,ushort const *,...)
0x140022b45  mov     dword ptr [rdi], 0
0x140022b4b  xor     ebx, ebx
0x140022b4d  lea     rcx, [rbp+var_30]; this
0x140022b51  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x140022b56  mov     eax, ebx
0x140022b58  mov     rbx, [rsp+60h+arg_0]
0x140022b5d  mov     rdi, [rsp+60h+arg_8]
0x140022b62  add     rsp, 60h
0x140022b66  pop     rbp
0x140022b67  retn
```
