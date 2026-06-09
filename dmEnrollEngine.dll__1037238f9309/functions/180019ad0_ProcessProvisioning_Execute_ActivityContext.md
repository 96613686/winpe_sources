# ProcessProvisioning::Execute(ActivityContext *)

- ea: `0x180019ad0`
- end: `0x180019e84`
- name: `?Execute@ProcessProvisioning@@UEAAJPEAVActivityContext@@@Z`
- size: `948`
- prototype: `int(ProcessProvisioning *__hidden this, struct ActivityContext *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000de50`
- `0x18000e0d0`
- `0x18000e508`
- `0x180010490`
- `0x180019ad0`
- `0x180019e8c`
- `0x18001a86c`
- `0x18001aec8`
- `0x18002e1a0`
- `0x18003ebe0`
- `0x18003ee54`
- `0x18004107c`
- `0x180050558`
- `0x180072c70`
- `0x18007b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180019b39`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180019b50`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180019c99`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180019cd2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180019b39`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180019b50`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180019c99`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180019cd2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019dc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019dc8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019dba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019dba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019c39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019c39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019c1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019c64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019dec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019e4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019c1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019c64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019dec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019e4a`

## string_xrefs

- `0x180019d60`: `DiscoveryServiceFullURL`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ProcessProvisioning::Execute(ProcessProvisioning *this, struct ActivityContext *a2)
{
  __int16 v4; // r15
  char *v5; // rsi
  bool v6; // zf
  int v7; // eax
  int KeyAsString; // edi
  EEDBManager *v9; // rcx
  HKEY v10; // rcx
  LSTATUS v11; // eax
  int v12; // r14d
  BOOL v13; // ecx
  const unsigned __int16 *v14; // r9
  int v15; // esi
  unsigned __int16 *v16; // rdi
  CEnrollmentLogger *Logger; // rax
  const unsigned __int16 *v18; // rcx
  HANDLE ProcessHeap; // rax
  HKEY v20; // rcx
  GlobalConfig *v21; // rcx
  const unsigned __int16 *v22; // rdx
  HKEY v23; // rcx
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v26; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp-A0h] BYREF
  struct IEnrollmentInfo *v28; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v30; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v31; // [rsp+88h] [rbp-78h] BYREF
  struct _GUID v32; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SubKey[40]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v34[40]; // [rsp+F0h] [rbp-10h] BYREF

  lpMem = 0;
  v31 = 0;
  phkResult = 0;
  v30 = 0;
  v4 = word_1800AFC84;
  v5 = (char *)a2 + 448;
  if ( !(unsigned int)_o__wcsnicmp((char *)a2 + 448) || (v6 = (unsigned int)_o__wcsnicmp(v5) == 0, v7 = 1, v6) )
    v7 = 0;
  *((_DWORD *)this + 6) = v7;
  KeyAsString = ActivityContext::get_KeyAsString(a2, SubKey);
  if ( KeyAsString < 0 )
    goto LABEL_38;
  *(_OWORD *)hKey = *(_OWORD *)((char *)a2 + 8);
  KeyAsString = EEDBManager::GetEnrollmentAuthPolicy((struct _GUID *)hKey, (enum MDMAuthPolicy *)&v30);
  if ( KeyAsString < 0 )
    goto LABEL_38;
  v28 = 0;
  *(_OWORD *)hKey = *(_OWORD *)((char *)a2 + 8);
  v26 = 63;
  if ( (int)EEDBManager::GetEnrollmentInfo(v9, (struct _GUID *)hKey, &v28) >= 0 )
    (*(void (__fastcall **)(struct IEnrollmentInfo *, unsigned int *))(*(_QWORD *)v28 + 48LL))(v28, &v26);
  ActivityContext::get_KeyAsString(a2, v34);
  hKey[0] = 0;
  KeyAsString = EEDBManager::OpenEnrollmentsHKEY(0x2001Fu, hKey);
  v10 = hKey[0];
  if ( KeyAsString < 0 )
  {
    hKey[0] = 0;
LABEL_10:
    if ( v10 )
      RegCloseKey(v10);
    goto LABEL_37;
  }
  v11 = RegOpenKeyExW(hKey[0], SubKey, 0, 0x2001Fu, &phkResult);
  KeyAsString = v11;
  if ( v11 > 0 )
    KeyAsString = (unsigned __int16)v11 | 0x80070000;
  v10 = hKey[0];
  hKey[0] = 0;
  if ( KeyAsString < 0 )
    goto LABEL_10;
  v12 = 0;
  if ( v10 )
    RegCloseKey(v10);
  v32 = *(struct _GUID *)((char *)a2 + 8);
  EEDBManager::GetEnrollmentString(&v32, L"SID", &v31);
  if ( !(unsigned int)_o__wcsnicmp(v5) )
  {
    v12 = 1;
    v32 = *(struct _GUID *)((char *)a2 + 8);
    EEDBManager::GetEnrollmentString(&v32, L"ProviderID", (unsigned __int16 **)&lpMem);
  }
  v13 = _o__wcsnicmp(v5) == 0;
  v14 = (const unsigned __int16 *)((char *)a2 + 144);
  if ( *((_QWORD *)a2 + 21) > 7u )
    v14 = *(const unsigned __int16 **)v14;
  v15 = ProcessProvisioning(
          SubKey,
          v26,
          phkResult,
          v14,
          (struct _FILETIME)v31,
          v4,
          *((_DWORD *)a2 + 18),
          v12,
          v13,
          (unsigned __int16 **)&lpMem);
  v16 = (unsigned __int16 *)lpMem;
  if ( !v12 )
  {
    v32 = *(struct _GUID *)((char *)a2 + 8);
    EEDBManager::SetProviderID(&v32, (const unsigned __int16 *)lpMem);
  }
  lpMem = 0;
  v32 = *(struct _GUID *)((char *)a2 + 8);
  EEDBManager::GetEnrollmentString(&v32, L"DiscoveryServiceFullURL", (unsigned __int16 **)&lpMem);
  Logger = CEnrollmentLogger::GetLogger();
  v18 = (const unsigned __int16 *)((char *)a2 + 112);
  if ( *((_QWORD *)a2 + 17) > 7u )
    v18 = *(const unsigned __int16 **)v18;
  CEnrollmentLogger::LogProvisioningEvent(Logger, v34, v30, (const unsigned __int16 *)lpMem, v18, v16, v26);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&lpMem);
  if ( v16 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v16);
  }
  if ( v15 >= 0 )
  {
    v21 = (GlobalConfig *)*((unsigned int *)a2 + 243);
    if ( (_DWORD)v21 == 5 )
    {
      v22 = L"UserOwned";
    }
    else
    {
      if ( ((1LL << (char)v21) & 0xD402061) == 0 )
      {
        KeyAsString = 0;
        goto LABEL_37;
      }
      v22 = L"CorpOwned";
    }
    KeyAsString = GlobalConfig::UpdateDeviceOwnership(v21, v22, 1);
LABEL_37:
    wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&v28);
LABEL_38:
    v23 = phkResult;
    phkResult = 0;
    if ( v23 )
      RegCloseKey(v23);
    goto LABEL_40;
  }
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&v28);
  v20 = phkResult;
  phkResult = 0;
  if ( v20 )
    RegCloseKey(v20);
  KeyAsString = v15;
LABEL_40:
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v31);
  return (unsigned int)KeyAsString;
}

```

## disassembly

```asm
0x180019ad0  mov     [rsp-8+arg_10], rbx
0x180019ad5  mov     [rsp-8+arg_18], rsi
0x180019ada  push    rbp
0x180019adb  push    rdi
0x180019adc  push    r12
0x180019ade  push    r14
0x180019ae0  push    r15
0x180019ae2  lea     rbp, [rsp-50h]
0x180019ae7  sub     rsp, 150h
0x180019aee  mov     rax, cs:__security_cookie
0x180019af5  xor     rax, rsp
0x180019af8  mov     [rbp+70h+var_30], rax
0x180019afc  mov     rbx, rdx
0x180019aff  mov     rdi, rcx
0x180019b02  xor     r12d, r12d
0x180019b05  mov     [rsp+170h+lpMem], r12
0x180019b0a  mov     [rbp+70h+var_E8], r12
0x180019b0e  mov     [rsp+170h+var_120], r12
0x180019b13  mov     [rbp+70h+var_F0], r12d
0x180019b17  movzx   r15d, cs:word_1800AFC84
0x180019b1f  lea     rsi, [rdx+1C0h]
0x180019b26  mov     r14d, 104h
0x180019b2c  mov     r8d, r14d
0x180019b2f  mov     rdx, cs:off_1800AF248; "OR_RENEW"
0x180019b36  mov     rcx, rsi
0x180019b39  call    cs:__imp__o__wcsnicmp
0x180019b3f  test    eax, eax
0x180019b41  jz      short loc_180019B5F
0x180019b43  mov     r8d, r14d
0x180019b46  mov     rdx, cs:off_1800AF2C8; "OR_MDMRECOVERY"
0x180019b4d  mov     rcx, rsi
0x180019b50  call    cs:__imp__o__wcsnicmp
0x180019b56  test    eax, eax
0x180019b58  lea     eax, [r12+1]
0x180019b5d  jnz     short loc_180019B62
0x180019b5f  mov     eax, r12d
0x180019b62  mov     [rdi+18h], eax
0x180019b65  lea     rdx, [rbp+70h+SubKey]; unsigned __int16 *
0x180019b69  mov     rcx, rbx; this
0x180019b6c  call    ?get_KeyAsString@ActivityContext@@QEAAJQEAG@Z; ActivityContext::get_KeyAsString(ushort * const)
0x180019b71  mov     edi, eax
0x180019b73  test    eax, eax
0x180019b75  js      loc_180019E3B
0x180019b7b  movups  xmm0, xmmword ptr [rbx+8]
0x180019b7f  movdqu  xmmword ptr [rsp+170h+hKey], xmm0
0x180019b85  lea     rdx, [rbp+70h+var_F0]; enum MDMAuthPolicy *
0x180019b89  lea     rcx, [rsp+170h+hKey]; struct _GUID
0x180019b8e  call    ?GetEnrollmentAuthPolicy@EEDBManager@@SAJU_GUID@@PEAW4MDMAuthPolicy@@@Z; EEDBManager::GetEnrollmentAuthPolicy(_GUID,MDMAuthPolicy *)
0x180019b93  mov     edi, eax
0x180019b95  test    eax, eax
0x180019b97  js      loc_180019E3B
0x180019b9d  mov     [rsp+170h+var_108], r12
0x180019ba2  movups  xmm0, xmmword ptr [rbx+8]
0x180019ba6  movdqu  xmmword ptr [rsp+170h+hKey], xmm0
0x180019bac  lea     r8, [rsp+170h+var_108]; struct IEnrollmentInfo **
0x180019bb1  lea     rdx, [rsp+170h+hKey]; struct _GUID
0x180019bb6  call    ?GetEnrollmentInfo@EEDBManager@@QEAAJU_GUID@@PEAPEAUIEnrollmentInfo@@@Z; EEDBManager::GetEnrollmentInfo(_GUID,IEnrollmentInfo * *)
0x180019bbb  mov     [rsp+170h+var_118], 3Fh ; '?'
0x180019bc3  test    eax, eax
0x180019bc5  js      short loc_180019BDD
0x180019bc7  mov     rcx, [rsp+170h+var_108]
0x180019bcc  mov     rax, [rcx]
0x180019bcf  lea     rdx, [rsp+170h+var_118]
0x180019bd4  mov     rax, [rax+30h]
0x180019bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bdd  lea     rdx, [rbp+70h+var_80]; unsigned __int16 *
0x180019be1  mov     rcx, rbx; this
0x180019be4  call    ?get_KeyAsString@ActivityContext@@QEAAJQEAG@Z; ActivityContext::get_KeyAsString(ushort * const)
0x180019be9  mov     [rsp+170h+hKey], r12
0x180019bee  lea     rdx, [rsp+170h+hKey]; HKEY *
0x180019bf3  mov     r14d, 2001Fh
0x180019bf9  mov     ecx, r14d; unsigned int
0x180019bfc  call    ?OpenEnrollmentsHKEY@EEDBManager@@SAJKPEAPEAUHKEY__@@@Z; EEDBManager::OpenEnrollmentsHKEY(ulong,HKEY__ * *)
0x180019c01  mov     edi, eax
0x180019c03  mov     rcx, [rsp+170h+hKey]; hKey
0x180019c08  test    eax, eax
0x180019c0a  jns     short loc_180019C25
0x180019c0c  mov     [rsp+170h+hKey], r12
0x180019c11  test    rcx, rcx
0x180019c14  jz      loc_180019E30
0x180019c1a  call    cs:__imp_RegCloseKey
0x180019c20  jmp     loc_180019E30
0x180019c25  lea     rax, [rsp+170h+var_120]
0x180019c2a  mov     [rsp+170h+phkResult], rax; phkResult
0x180019c2f  mov     r9d, r14d; samDesired
0x180019c32  xor     r8d, r8d; ulOptions
0x180019c35  lea     rdx, [rbp+70h+SubKey]; lpSubKey
0x180019c39  call    cs:__imp_RegOpenKeyExW
0x180019c3f  mov     edi, eax
0x180019c41  test    eax, eax
0x180019c43  jle     short loc_180019C4E
0x180019c45  movzx   edi, ax
0x180019c48  or      edi, 80070000h
0x180019c4e  mov     rcx, [rsp+170h+hKey]; hKey
0x180019c53  mov     [rsp+170h+hKey], r12
0x180019c58  test    edi, edi
0x180019c5a  js      short loc_180019C11
0x180019c5c  mov     r14d, r12d
0x180019c5f  test    rcx, rcx
0x180019c62  jz      short loc_180019C6A
0x180019c64  call    cs:__imp_RegCloseKey
0x180019c6a  movups  xmm0, xmmword ptr [rbx+8]
0x180019c6e  movdqu  xmmword ptr [rbp+70h+var_E0.Data1], xmm0
0x180019c73  lea     r8, [rbp+70h+var_E8]; unsigned __int16 **
0x180019c77  lea     rdx, aSid; "SID"
0x180019c7e  lea     rcx, [rbp+70h+var_E0]; struct _GUID
0x180019c82  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x180019c87  mov     edi, 104h
0x180019c8c  mov     r8d, edi
0x180019c8f  mov     rdx, cs:off_1800AF248; "OR_RENEW"
0x180019c96  mov     rcx, rsi
0x180019c99  call    cs:__imp__o__wcsnicmp
0x180019c9f  test    eax, eax
0x180019ca1  jnz     short loc_180019CC5
0x180019ca3  lea     r14d, [rax+1]
0x180019ca7  movups  xmm0, xmmword ptr [rbx+8]
0x180019cab  movdqu  xmmword ptr [rbp+70h+var_E0.Data1], xmm0
0x180019cb0  lea     r8, [rsp+170h+lpMem]; unsigned __int16 **
0x180019cb5  lea     rdx, aProviderid; "ProviderID"
0x180019cbc  lea     rcx, [rbp+70h+var_E0]; struct _GUID
0x180019cc0  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x180019cc5  mov     r8, rdi
0x180019cc8  mov     rdx, cs:off_1800AF2C8; "OR_MDMRECOVERY"
0x180019ccf  mov     rcx, rsi
0x180019cd2  call    cs:__imp__o__wcsnicmp
0x180019cd8  mov     ecx, r12d
0x180019cdb  test    eax, eax
0x180019cdd  setz    cl
0x180019ce0  mov     eax, [rbx+48h]
0x180019ce3  mov     rdx, [rbp+70h+var_E8]
0x180019ce7  lea     r9, [rbx+90h]
0x180019cee  cmp     qword ptr [r9+18h], 7
0x180019cf3  jbe     short loc_180019CF8
0x180019cf5  mov     r9, [r9]
0x180019cf8  lea     r8, [rsp+170h+lpMem]
0x180019cfd  mov     [rsp+170h+var_128], r8
0x180019d02  mov     [rsp+170h+var_130], ecx
0x180019d06  mov     [rsp+170h+var_138], r14d
0x180019d0b  mov     [rsp+170h+var_140], eax
0x180019d0f  mov     word ptr [rsp+170h+var_148], r15w
0x180019d15  mov     [rsp+170h+phkResult], rdx
0x180019d1a  mov     r8, [rsp+170h+var_120]
0x180019d1f  mov     edx, [rsp+170h+var_118]
0x180019d23  lea     rcx, [rbp+70h+SubKey]
0x180019d27  call    ?ProcessProvisioning@@YAJPEBGW4EnrollmentEnrollType@@PEAUHKEY__@@00GKHHAEAPEAG@Z; ProcessProvisioning(ushort const *,EnrollmentEnrollType,HKEY__ *,ushort const *,ushort const *,ushort,ulong,int,int,ushort * &)
0x180019d2c  mov     esi, eax
0x180019d2e  mov     rdi, [rsp+170h+lpMem]
0x180019d33  test    r14d, r14d
0x180019d36  jnz     short loc_180019D4D
0x180019d38  movups  xmm0, xmmword ptr [rbx+8]
0x180019d3c  movdqu  xmmword ptr [rbp+70h+var_E0.Data1], xmm0
0x180019d41  mov     rdx, rdi; unsigned __int16 *
0x180019d44  lea     rcx, [rbp+70h+var_E0]; struct _GUID
0x180019d48  call    ?SetProviderID@EEDBManager@@SAJU_GUID@@PEBG@Z; EEDBManager::SetProviderID(_GUID,ushort const *)
0x180019d4d  mov     [rsp+170h+lpMem], r12
0x180019d52  movups  xmm0, xmmword ptr [rbx+8]
0x180019d56  movdqu  xmmword ptr [rbp+70h+var_E0.Data1], xmm0
0x180019d5b  lea     r8, [rsp+170h+lpMem]; unsigned __int16 **
0x180019d60  lea     rdx, aDiscoveryservi; "DiscoveryServiceFullURL"
0x180019d67  lea     rcx, [rbp+70h+var_E0]; struct _GUID
0x180019d6b  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x180019d70  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180019d75  mov     edx, [rsp+170h+var_118]
0x180019d79  lea     rcx, [rbx+70h]
0x180019d7d  cmp     qword ptr [rcx+18h], 7
0x180019d82  jbe     short loc_180019D87
0x180019d84  mov     rcx, [rcx]
0x180019d87  mov     [rsp+170h+var_140], edx; unsigned int
0x180019d8b  mov     [rsp+170h+var_148], rdi; unsigned __int16 *
0x180019d90  mov     [rsp+170h+phkResult], rcx; unsigned __int16 *
0x180019d95  mov     r9, [rsp+170h+lpMem]; unsigned __int16 *
0x180019d9a  mov     r8d, [rbp+70h+var_F0]; unsigned int
0x180019d9e  lea     rdx, [rbp+70h+var_80]; unsigned __int16 *
0x180019da2  mov     rcx, rax; this
0x180019da5  call    ?LogProvisioningEvent@CEnrollmentLogger@@QEAAXPEBGK000K@Z; CEnrollmentLogger::LogProvisioningEvent(ushort const *,ulong,ushort const *,ushort const *,ushort const *,ulong)
0x180019daa  nop
0x180019dab  lea     rcx, [rsp+170h+lpMem]
0x180019db0  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180019db5  test    rdi, rdi
0x180019db8  jz      short loc_180019DCE
0x180019dba  call    cs:__imp_GetProcessHeap
0x180019dc0  mov     r8, rdi; lpMem
0x180019dc3  xor     edx, edx; dwFlags
0x180019dc5  mov     rcx, rax; hHeap
0x180019dc8  call    cs:__imp_HeapFree
0x180019dce  test    esi, esi
0x180019dd0  jns     short loc_180019DF6
0x180019dd2  lea     rcx, [rsp+170h+var_108]
0x180019dd7  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x180019ddc  nop
0x180019ddd  mov     rcx, [rsp+170h+var_120]; hKey
0x180019de2  mov     [rsp+170h+var_120], r12
0x180019de7  test    rcx, rcx
0x180019dea  jz      short loc_180019DF2
0x180019dec  call    cs:__imp_RegCloseKey
0x180019df2  mov     edi, esi
0x180019df4  jmp     short loc_180019E51
0x180019df6  mov     ecx, [rbx+3CCh]; this
0x180019dfc  cmp     ecx, 5
0x180019dff  jnz     short loc_180019E14
0x180019e01  lea     rdx, aUserowned; "UserOwned"
0x180019e08  mov     r8b, 1; bool
0x180019e0b  call    ?UpdateDeviceOwnership@GlobalConfig@@AEAAJPEBG_N@Z; GlobalConfig::UpdateDeviceOwnership(ushort const *,bool)
0x180019e10  mov     edi, eax
0x180019e12  jmp     short loc_180019E30
0x180019e14  mov     eax, 1
0x180019e19  shl     rax, cl
0x180019e1c  test    rax, 0D402061h
0x180019e22  jz      short loc_180019E2D
0x180019e24  lea     rdx, aCorpowned; "CorpOwned"
0x180019e2b  jmp     short loc_180019E08
0x180019e2d  mov     edi, r12d
0x180019e30  lea     rcx, [rsp+170h+var_108]
0x180019e35  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x180019e3a  nop
0x180019e3b  mov     rcx, [rsp+170h+var_120]; hKey
0x180019e40  mov     [rsp+170h+var_120], r12
0x180019e45  test    rcx, rcx
0x180019e48  jz      short loc_180019E51
0x180019e4a  call    cs:__imp_RegCloseKey
0x180019e50  nop
0x180019e51  lea     rcx, [rbp+70h+var_E8]
0x180019e55  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180019e5a  mov     eax, edi
0x180019e5c  mov     rcx, [rbp+70h+var_30]
0x180019e60  xor     rcx, rsp; StackCookie
0x180019e63  call    __security_check_cookie
0x180019e68  lea     r11, [rsp+170h+var_20]
0x180019e70  mov     rbx, [r11+40h]
0x180019e74  mov     rsi, [r11+48h]
0x180019e78  mov     rsp, r11
0x180019e7b  pop     r15
0x180019e7d  pop     r14
0x180019e7f  pop     r12
0x180019e81  pop     rdi
0x180019e82  pop     rbp
0x180019e83  retn
```
