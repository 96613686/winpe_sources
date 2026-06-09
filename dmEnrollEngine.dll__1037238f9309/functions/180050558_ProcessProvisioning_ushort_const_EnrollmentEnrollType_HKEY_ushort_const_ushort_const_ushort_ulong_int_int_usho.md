# ProcessProvisioning(ushort const *,EnrollmentEnrollType,HKEY__ *,ushort const *,ushort const *,ushort,ulong,int,int,ushort * &)

- ea: `0x180050558`
- end: `0x18005087b`
- name: `?ProcessProvisioning@@YAJPEBGW4EnrollmentEnrollType@@PEAUHKEY__@@00GKHHAEAPEAG@Z`
- size: `803`
- prototype: `__int64 __fastcall(OLECHAR *, unsigned int, HKEY, const unsigned __int16 *, struct _FILETIME, __int16, unsigned int, int, int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180019ad0`

## callees

- `0x18000e508`
- `0x18001aec8`
- `0x18002d48c`
- `0x18002d634`
- `0x18002d724`
- `0x18002d850`
- `0x18002e1a0`
- `0x18003708c`
- `0x18003b068`
- `0x18003b118`
- `0x18003b170`
- `0x18004ecb8`
- `0x18004ef34`
- `0x18004ff88`
- `0x180050558`
- `0x180050884`
- `0x180050d7c`
- `0x180050f68`
- `0x180065d70`
- `0x1800723ec`
- `0x180072464`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180050825`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180050825`
- `DMCmnUtils!DmRunTask` at `0x18005079a`
- `DMCmnUtils!DmRunTask` at `0x1800507ba`
- `DMCmnUtils!DmRunTask` at `0x1800507da`
- `DMCmnUtils!DmRunTask` at `0x18005079a`
- `DMCmnUtils!DmRunTask` at `0x1800507ba`
- `DMCmnUtils!DmRunTask` at `0x1800507da`

## string_xrefs

- `0x180050786`: `Schedule #1 created by enrollment client`
- `0x1800507ad`: `Maintenance Schedule created by enrollment client`
- `0x1800507cd`: `Schedule #3 created by enrollment client`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProcessProvisioning(
        OLECHAR *a1,
        unsigned int a2,
        HKEY a3,
        const unsigned __int16 *a4,
        struct _FILETIME a5,
        __int16 a6,
        unsigned int a7,
        int a8,
        int a9,
        unsigned __int16 **a10)
{
  int NodeStringValue; // ebx
  bool v14; // zf
  CEnrollmentLogger *Logger; // rax
  unsigned int v16; // r14d
  unsigned int v17; // r15d
  unsigned int v18; // r12d
  int v19; // r13d
  int DeviceCertExpiryTime; // eax
  __int64 v21; // r8
  int v22; // eax
  CEnrollmentLogger *v23; // rax
  unsigned __int16 *Data; // [rsp+30h] [rbp-61h]
  int v26; // [rsp+50h] [rbp-41h] BYREF
  int v27; // [rsp+54h] [rbp-3Dh] BYREF
  unsigned int v28; // [rsp+58h] [rbp-39h] BYREF
  unsigned int v29; // [rsp+5Ch] [rbp-35h] BYREF
  unsigned int v30; // [rsp+60h] [rbp-31h] BYREF
  struct IXMLDOMDocument2 *v31; // [rsp+68h] [rbp-29h] BYREF
  struct _FILETIME v32; // [rsp+70h] [rbp-21h] BYREF

  v26 = a2;
  v32 = a5;
  v27 = 0;
  v31 = 0;
  NodeStringValue = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v27, a2);
  if ( NodeStringValue < 0 )
  {
    wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v31);
    v14 = v27 == 0;
    goto LABEL_34;
  }
  if ( a8 )
    CMachineEnroller::SaveDMClientOnRenewal(a3, a1, *a10, a7);
  NodeStringValue = CMachineEnroller::ReadInProvisioningXML(a4, &v31);
  if ( NodeStringValue >= 0 )
  {
    if ( a8 )
      goto LABEL_12;
    NodeStringValue = CMachineEnroller::ExtractNodeStringValue(
                        v31,
                        L"//characteristic[@type='APPLICATION']/parm[@name='PROVIDER-ID']/@value",
                        a10,
                        0);
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
      McTemplateU0z_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, PrintProviderId, *a10);
    if ( NodeStringValue == -2102788095 )
    {
      Logger = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogEnrollProvisioningBadXMLError(Logger, "ProcessProvisioning");
      goto LABEL_16;
    }
    if ( NodeStringValue >= 0 )
    {
LABEL_12:
      NodeStringValue = CMachineEnroller::OnXmlStored(a3, v31, *a10, a1, v26, *(_QWORD *)&v32, a6, a8, a9, a7);
      if ( NodeStringValue >= 0 && !a8 && !a9 )
        NodeStringValue = CMachineEnroller::SaveDMClientOnNewEnrollment(a1, *a10);
    }
  }
LABEL_16:
  v32 = 0;
  v16 = 0;
  v28 = 0;
  v17 = 0;
  v29 = 0;
  v18 = 0;
  v30 = 0;
  v19 = 0;
  v26 = 0;
  if ( NodeStringValue < 0 )
    goto LABEL_26;
  if ( a8 )
    goto LABEL_25;
  DeviceCertExpiryTime = GetDeviceCertExpiryTime(a1, &v32);
  NodeStringValue = DeviceCertExpiryTime;
  if ( DeviceCertExpiryTime == -2147024894 )
    goto LABEL_25;
  if ( DeviceCertExpiryTime >= 0 )
  {
    NodeStringValue = GetRenewPeriodInSeconds(a1, &v28);
    if ( NodeStringValue >= 0 )
    {
      NodeStringValue = GetRenewRetryIntervalInSeconds(a1, 1, &v29);
      if ( NodeStringValue >= 0 )
      {
        NodeStringValue = GetRenewRetryIntervalInSeconds(a1, 0, &v30);
        if ( NodeStringValue >= 0 )
        {
          NodeStringValue = IsROBOMode(a1, &v26);
          if ( NodeStringValue >= 0 )
          {
            v16 = v28;
            v17 = v29;
            v18 = v30;
            v19 = v26;
LABEL_25:
            NodeStringValue = SetupAllEnrollmentSchedules(a1, v32, v16, v17, v18, v19, Data);
          }
        }
      }
    }
  }
LABEL_26:
  CMachineEnroller::DeleteTemporaryFiles();
  if ( NodeStringValue >= 0 )
  {
    NodeStringValue = DmRunTask(
                        L"\\Microsoft\\Windows\\EnterpriseMgmt",
                        a1,
                        L"Schedule #1 created by enrollment client",
                        0);
    if ( NodeStringValue >= 0
      || (NodeStringValue = DmRunTask(
                              L"\\Microsoft\\Windows\\EnterpriseMgmt",
                              a1,
                              L"Maintenance Schedule created by enrollment client",
                              0),
          NodeStringValue >= 0)
      || (v22 = DmRunTask(L"\\Microsoft\\Windows\\EnterpriseMgmt", a1, L"Schedule #3 created by enrollment client", 0),
          NodeStringValue = v22,
          v22 >= 0) )
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 2) != 0 )
        McGenEventWrite_EventWriteTransfer(
          MDM_ENTERPRISE_DIAGNOSTICS_Context,
          EnterpriseDiagnosticsEnrollProvisioningSuccess,
          v21,
          1,
          &v32);
      goto LABEL_33;
    }
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      McTemplateU0q_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, RunFirstScheduleFailed, (unsigned int)v22);
  }
  v23 = CEnrollmentLogger::GetLogger();
  CEnrollmentLogger::LogEnrollProvisioningFail(v23, NodeStringValue);
LABEL_33:
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v31);
  v14 = v27 == 0;
LABEL_34:
  if ( !v14 )
    CoUninitialize();
  return (unsigned int)NodeStringValue;
}

```

## disassembly

```asm
0x180050558  push    rbp
0x18005055a  push    rbx
0x18005055b  push    rsi
0x18005055c  push    rdi
0x18005055d  push    r12
0x18005055f  push    r13
0x180050561  push    r14
0x180050563  push    r15
0x180050565  lea     rbp, [rsp-7]
0x18005056a  sub     rsp, 98h
0x180050571  mov     rax, cs:__security_cookie
0x180050578  xor     rax, rsp
0x18005057b  mov     [rbp+3Fh+var_50], rax
0x18005057f  mov     r12, r9
0x180050582  mov     r13, r8
0x180050585  mov     [rbp+3Fh+var_80], edx
0x180050588  mov     rdi, rcx
0x18005058b  mov     rax, [rbp+3Fh+arg_20]
0x18005058f  mov     qword ptr [rbp+3Fh+var_60.dwLowDateTime], rax
0x180050593  mov     r14, [rbp+3Fh+arg_48]
0x18005059a  xor     esi, esi
0x18005059c  mov     [rbp+3Fh+var_7C], esi
0x18005059f  mov     [rbp+3Fh+var_68], rsi
0x1800505a3  lea     rcx, [rbp+3Fh+var_7C]; this
0x1800505a7  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x1800505ac  mov     ebx, eax
0x1800505ae  test    eax, eax
0x1800505b0  jns     short loc_1800505C4
0x1800505b2  lea     rcx, [rbp+3Fh+var_68]
0x1800505b6  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x1800505bb  nop
0x1800505bc  cmp     [rbp+3Fh+var_7C], esi
0x1800505bf  jmp     loc_180050823
0x1800505c4  mov     r15d, [rbp+3Fh+arg_30]
0x1800505c8  mov     esi, [rbp+3Fh+arg_38]
0x1800505ce  test    esi, esi
0x1800505d0  jz      short loc_1800505E3
0x1800505d2  mov     r9d, r15d; unsigned int
0x1800505d5  mov     r8, [r14]; OLECHAR *
0x1800505d8  mov     rdx, rdi; psz
0x1800505db  mov     rcx, r13; HKEY
0x1800505de  call    ?SaveDMClientOnRenewal@CMachineEnroller@@SAJPEAUHKEY__@@PEBG1K@Z; CMachineEnroller::SaveDMClientOnRenewal(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800505e3  lea     rdx, [rbp+3Fh+var_68]; struct IXMLDOMDocument2 **
0x1800505e7  mov     rcx, r12; unsigned __int16 *
0x1800505ea  call    ?ReadInProvisioningXML@CMachineEnroller@@SAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; CMachineEnroller::ReadInProvisioningXML(ushort const *,IXMLDOMDocument2 * *)
0x1800505ef  mov     ebx, eax
0x1800505f1  test    eax, eax
0x1800505f3  js      loc_1800506B2
0x1800505f9  test    esi, esi
0x1800505fb  jnz     short loc_180050656
0x1800505fd  xor     r9d, r9d; int
0x180050600  mov     r8, r14; unsigned __int16 **
0x180050603  lea     rdx, aCharacteristic_2; "//characteristic[@type='APPLICATION']/p"...
0x18005060a  mov     rcx, [rbp+3Fh+var_68]; struct IXMLDOMDocument2 *
0x18005060e  call    ?ExtractNodeStringValue@CMachineEnroller@@SAJPEAUIXMLDOMDocument2@@PEBGPEAPEAGH@Z; CMachineEnroller::ExtractNodeStringValue(IXMLDOMDocument2 *,ushort const *,ushort * *,int)
0x180050613  mov     ebx, eax
0x180050615  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18005061c  jz      short loc_180050634
0x18005061e  mov     r8, [r14]
0x180050621  lea     rdx, PrintProviderId
0x180050628  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18005062f  call    McTemplateU0z_EventWriteTransfer
0x180050634  cmp     ebx, 82AA0001h
0x18005063a  jnz     short loc_180050652
0x18005063c  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180050641  lea     rdx, aProcessprovisi; "ProcessProvisioning"
0x180050648  mov     rcx, rax; this
0x18005064b  call    ?LogEnrollProvisioningBadXMLError@CEnrollmentLogger@@QEAAXPEBD@Z; CEnrollmentLogger::LogEnrollProvisioningBadXMLError(char const *)
0x180050650  jmp     short loc_1800506B2
0x180050652  test    ebx, ebx
0x180050654  js      short loc_1800506B2
0x180050656  mov     [rsp+0D0h+var_88], r15d
0x18005065b  mov     r15d, [rbp+3Fh+arg_40]
0x180050662  mov     [rsp+0D0h+var_90], r15d
0x180050667  mov     [rsp+0D0h+var_98], esi
0x18005066b  movzx   eax, [rbp+3Fh+arg_28]
0x18005066f  mov     word ptr [rsp+0D0h+Data], ax; Data
0x180050674  mov     rax, qword ptr [rbp+3Fh+var_60.dwLowDateTime]
0x180050678  mov     qword ptr [rsp+0D0h+var_A8], rax
0x18005067d  mov     eax, [rbp+3Fh+var_80]
0x180050680  mov     [rsp+0D0h+var_B0], eax
0x180050684  mov     r9, rdi
0x180050687  mov     r8, [r14]
0x18005068a  mov     rdx, [rbp+3Fh+var_68]
0x18005068e  mov     rcx, r13
0x180050691  call    ?OnXmlStored@CMachineEnroller@@SAJPEAUHKEY__@@PEAUIXMLDOMDocument2@@PEAGPEBGW4EnrollmentEnrollType@@3GHHK@Z; CMachineEnroller::OnXmlStored(HKEY__ *,IXMLDOMDocument2 *,ushort *,ushort const *,EnrollmentEnrollType,ushort const *,ushort,int,int,ulong)
0x180050696  mov     ebx, eax
0x180050698  test    eax, eax
0x18005069a  js      short loc_1800506B2
0x18005069c  test    esi, esi
0x18005069e  jnz     short loc_1800506B2
0x1800506a0  test    r15d, r15d
0x1800506a3  jnz     short loc_1800506B2
0x1800506a5  mov     rdx, [r14]; OLECHAR *
0x1800506a8  mov     rcx, rdi; psz
0x1800506ab  call    ?SaveDMClientOnNewEnrollment@CMachineEnroller@@SAJPEBG0@Z; CMachineEnroller::SaveDMClientOnNewEnrollment(ushort const *,ushort const *)
0x1800506b0  mov     ebx, eax
0x1800506b2  mov     qword ptr [rbp+3Fh+var_60.dwLowDateTime], 0
0x1800506ba  xor     r14d, r14d
0x1800506bd  mov     [rbp+3Fh+var_78], r14d
0x1800506c1  xor     r15d, r15d
0x1800506c4  mov     [rbp+3Fh+var_74], r15d
0x1800506c8  xor     r12d, r12d
0x1800506cb  mov     [rbp+3Fh+var_70], r12d
0x1800506cf  xor     r13d, r13d
0x1800506d2  mov     [rbp+3Fh+var_80], r13d
0x1800506d6  test    ebx, ebx
0x1800506d8  js      loc_180050776
0x1800506de  test    esi, esi
0x1800506e0  jnz     short loc_180050758
0x1800506e2  lea     rdx, [rbp+3Fh+var_60]; struct _FILETIME *
0x1800506e6  mov     rcx, rdi; unsigned __int16 *
0x1800506e9  call    ?GetDeviceCertExpiryTime@@YAJPEBGPEAU_FILETIME@@@Z; GetDeviceCertExpiryTime(ushort const *,_FILETIME *)
0x1800506ee  mov     ebx, eax
0x1800506f0  cmp     eax, 80070002h
0x1800506f5  jz      short loc_180050758
0x1800506f7  test    eax, eax
0x1800506f9  js      short loc_180050776
0x1800506fb  lea     rdx, [rbp+3Fh+var_78]; unsigned int *
0x1800506ff  mov     rcx, rdi; unsigned __int16 *
0x180050702  call    ?GetRenewPeriodInSeconds@@YAJPEBGPEAK@Z; GetRenewPeriodInSeconds(ushort const *,ulong *)
0x180050707  mov     ebx, eax
0x180050709  test    eax, eax
0x18005070b  js      short loc_180050776
0x18005070d  lea     r8, [rbp+3Fh+var_74]; unsigned int *
0x180050711  lea     edx, [rsi+1]; int
0x180050714  mov     rcx, rdi; unsigned __int16 *
0x180050717  call    ?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z; GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)
0x18005071c  mov     ebx, eax
0x18005071e  test    eax, eax
0x180050720  js      short loc_180050776
0x180050722  lea     r8, [rbp+3Fh+var_70]; unsigned int *
0x180050726  xor     edx, edx; int
0x180050728  mov     rcx, rdi; unsigned __int16 *
0x18005072b  call    ?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z; GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)
0x180050730  mov     ebx, eax
0x180050732  test    eax, eax
0x180050734  js      short loc_180050776
0x180050736  lea     rdx, [rbp+3Fh+var_80]; int *
0x18005073a  mov     rcx, rdi; unsigned __int16 *
0x18005073d  call    ?IsROBOMode@@YAJPEBGPEAH@Z; IsROBOMode(ushort const *,int *)
0x180050742  mov     ebx, eax
0x180050744  test    eax, eax
0x180050746  js      short loc_180050776
0x180050748  mov     r14d, [rbp+3Fh+var_78]
0x18005074c  mov     r15d, [rbp+3Fh+var_74]
0x180050750  mov     r12d, [rbp+3Fh+var_70]
0x180050754  mov     r13d, [rbp+3Fh+var_80]
0x180050758  mov     [rsp+0D0h+var_A8], r13d; int
0x18005075d  mov     [rsp+0D0h+var_B0], r12d; unsigned int
0x180050762  mov     r9d, r15d; unsigned int
0x180050765  mov     r8d, r14d; unsigned int
0x180050768  mov     rdx, qword ptr [rbp+3Fh+var_60.dwLowDateTime]; struct _FILETIME
0x18005076c  mov     rcx, rdi; unsigned __int16 *
0x18005076f  call    ?SetupAllEnrollmentSchedules@@YAJPEBGU_FILETIME@@KKKH0@Z; SetupAllEnrollmentSchedules(ushort const *,_FILETIME,ulong,ulong,ulong,int,ushort const *)
0x180050774  mov     ebx, eax
0x180050776  call    ?DeleteTemporaryFiles@CMachineEnroller@@SAJXZ; CMachineEnroller::DeleteTemporaryFiles(void)
0x18005077b  test    ebx, ebx
0x18005077d  js      loc_180050805
0x180050783  xor     r9d, r9d
0x180050786  lea     r8, aSchedule1Creat; "Schedule #1 created by enrollment clien"...
0x18005078d  mov     rdx, rdi
0x180050790  lea     rsi, aMicrosoftWindo_3; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x180050797  mov     rcx, rsi
0x18005079a  call    cs:__imp_?DmRunTask@@YAJPEBG00PEAPEAX@Z; DmRunTask(ushort const *,ushort const *,ushort const *,void * *)
0x1800507a0  mov     ebx, eax
0x1800507a2  test    eax, eax
0x1800507a4  jns     loc_18005084D
0x1800507aa  xor     r9d, r9d
0x1800507ad  lea     r8, aMaintenanceSch; "Maintenance Schedule created by enrollm"...
0x1800507b4  mov     rdx, rdi
0x1800507b7  mov     rcx, rsi
0x1800507ba  call    cs:__imp_?DmRunTask@@YAJPEBG00PEAPEAX@Z; DmRunTask(ushort const *,ushort const *,ushort const *,void * *)
0x1800507c0  mov     ebx, eax
0x1800507c2  test    eax, eax
0x1800507c4  jns     loc_18005084D
0x1800507ca  xor     r9d, r9d
0x1800507cd  lea     r8, aSchedule3Creat; "Schedule #3 created by enrollment clien"...
0x1800507d4  mov     rdx, rdi
0x1800507d7  mov     rcx, rsi
0x1800507da  call    cs:__imp_?DmRunTask@@YAJPEBG00PEAPEAX@Z; DmRunTask(ushort const *,ushort const *,ushort const *,void * *)
0x1800507e0  mov     ebx, eax
0x1800507e2  test    eax, eax
0x1800507e4  jns     short loc_18005084D
0x1800507e6  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x1800507ed  jz      short loc_180050805
0x1800507ef  mov     r8d, eax
0x1800507f2  lea     rdx, RunFirstScheduleFailed
0x1800507f9  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180050800  call    McTemplateU0q_EventWriteTransfer
0x180050805  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18005080a  mov     edx, ebx; int
0x18005080c  mov     rcx, rax; this
0x18005080f  call    ?LogEnrollProvisioningFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogEnrollProvisioningFail(long)
0x180050814  nop
0x180050815  lea     rcx, [rbp+3Fh+var_68]
0x180050819  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18005081e  nop
0x18005081f  cmp     [rbp+3Fh+var_7C], 0
0x180050823  jz      short loc_18005082B
0x180050825  call    cs:__imp_CoUninitialize
0x18005082b  mov     eax, ebx
0x18005082d  mov     rcx, [rbp+3Fh+var_50]
0x180050831  xor     rcx, rsp; StackCookie
0x180050834  call    __security_check_cookie
0x180050839  add     rsp, 98h
0x180050840  pop     r15
0x180050842  pop     r14
0x180050844  pop     r13
0x180050846  pop     r12
0x180050848  pop     rdi
0x180050849  pop     rsi
0x18005084a  pop     rbx
0x18005084b  pop     rbp
0x18005084c  retn
0x18005084d  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 2
0x180050854  jz      short loc_180050815
0x180050856  lea     rax, [rbp+3Fh+var_60]
0x18005085a  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18005085f  mov     r9d, 1
0x180050865  lea     rdx, EnterpriseDiagnosticsEnrollProvisioningSuccess
0x18005086c  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x180050873  call    McGenEventWrite_EventWriteTransfer
0x180050878  jmp     short loc_180050815
```
