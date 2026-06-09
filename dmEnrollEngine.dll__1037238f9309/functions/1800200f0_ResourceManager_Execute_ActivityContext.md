# ResourceManager::Execute(ActivityContext *)

- ea: `0x1800200f0`
- end: `0x180020334`
- name: `?Execute@ResourceManager@@UEAAJPEAVActivityContext@@@Z`
- size: `580`
- prototype: `int(ResourceManager *__hidden this, struct ActivityContext *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800067a0`
- `0x1800071c0`
- `0x18000de50`
- `0x180013ec0`
- `0x180019e8c`
- `0x18001a86c`
- `0x18001aec8`
- `0x1800200f0`
- `0x18002033c`
- `0x18002e1a0`
- `0x18002ec8c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800201e5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800201e5`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180020231`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180020231`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800202ab`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800202ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002029a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002029a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020226`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800202d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020226`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800202d7`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18002017b`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18002017b`
- `unenrollhook!EnterpriseResourceManager_UnenrollHook` at `0x1800202c5`
- `unenrollhook!EnterpriseResourceManager_UnenrollHook` at `0x1800202c5`
- `unenrollhook!EnterpriseResourceManager_MoveAllResources` at `0x1800201fc`
- `unenrollhook!EnterpriseResourceManager_MoveAllResources` at `0x1800201fc`
- `DeclaredConfigurationAPI!FindMdmEnrollmentWithLinkedEnrollment` at `0x1800201cc`
- `DeclaredConfigurationAPI!FindMdmEnrollmentWithLinkedEnrollment` at `0x1800201cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ResourceManager::Execute(ResourceManager *this, struct ActivityContext *a2)
{
  int KeyAsString; // ebx
  CEnrollmentLogger *v5; // rax
  char IsStateSeparationEnabled; // al
  const wchar_t *v7; // r9
  CEnrollmentLogger *Logger; // rax
  unsigned __int16 *v10[2]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v12[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v13[40]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v14[40]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR SubKey[264]; // [rsp+100h] [rbp+0h] BYREF

  v12[0] = 0;
  v10[0] = 0;
  KeyAsString = ActivityContext::get_KeyAsString(a2, v13);
  if ( KeyAsString < 0 )
    goto LABEL_20;
  if ( !*((_DWORD *)this + 6) )
  {
    *(_OWORD *)hKey = *(_OWORD *)((char *)a2 + 8);
    KeyAsString = EEDBManager::GetEnrollmentString((struct _GUID *)hKey, L"SID", v10);
    if ( KeyAsString == -2147024894 )
      KeyAsString = DmGetActiveUserSid(v10);
    if ( KeyAsString < 0 )
    {
LABEL_20:
      Logger = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogUnenrollResourceManagerFail(Logger, KeyAsString);
LABEL_21:
      ResourceManager::CleanLeakedTH2Biometrics(v13);
      goto LABEL_22;
    }
  }
  *(_OWORD *)hKey = *(_OWORD *)((char *)a2 + 8);
  EEDBManager::GetEnrollmentString((struct _GUID *)hKey, L"ProviderID", v12);
  memset_0(v14, 0, 0x4Eu);
  hKey[0] = 0;
  if ( (int)FindMdmEnrollmentWithLinkedEnrollment(v13, v14) < 0 || !(unsigned int)_o__wcsicmp(v14, &wszURI) )
  {
    KeyAsString = EnterpriseResourceManager_UnenrollHook(v13, *((_DWORD *)this + 6), v12[0], v10[0]);
    goto LABEL_17;
  }
  KeyAsString = EnterpriseResourceManager_MoveAllResources(v13, v14);
  if ( KeyAsString >= 0 )
  {
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
    v7 = L"OSData\\Software\\Microsoft\\EnterpriseResourceManager\\Tracked";
    if ( !IsStateSeparationEnabled )
      v7 = L"Software\\Microsoft\\EnterpriseResourceManager\\Tracked";
    KeyAsString = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", v7, v13);
    if ( KeyAsString >= 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        hKey,
        0);
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2011Fu, hKey) )
        RegDeleteTreeW(hKey[0], 0);
    }
LABEL_17:
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    if ( KeyAsString >= 0 )
      goto LABEL_21;
    goto LABEL_20;
  }
  v5 = CEnrollmentLogger::GetLogger();
  CEnrollmentLogger::LogUnenrollResourceManagerFail(v5, KeyAsString);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
LABEL_22:
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)v10);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)v12);
  return (unsigned int)KeyAsString;
}

```

## disassembly

```asm
0x1800200f0  mov     [rsp-8+arg_10], rbx
0x1800200f5  push    rbp
0x1800200f6  push    rsi
0x1800200f7  push    rdi
0x1800200f8  lea     rbp, [rsp-220h]
0x180020100  sub     rsp, 320h
0x180020107  mov     rax, cs:__security_cookie
0x18002010e  xor     rax, rsp
0x180020111  mov     [rbp+230h+var_20], rax
0x180020118  mov     rdi, rdx
0x18002011b  mov     rsi, rcx
0x18002011e  mov     [rsp+330h+var_2E0], 0
0x180020127  mov     [rsp+330h+var_300], 0
0x180020130  lea     rdx, [rsp+330h+var_2D0]; unsigned __int16 *
0x180020135  mov     rcx, rdi; this
0x180020138  call    ?get_KeyAsString@ActivityContext@@QEAAJQEAG@Z; ActivityContext::get_KeyAsString(ushort * const)
0x18002013d  mov     ebx, eax
0x18002013f  test    eax, eax
0x180020141  js      loc_1800202E1
0x180020147  cmp     dword ptr [rsi+18h], 0
0x18002014b  jnz     short loc_18002018B
0x18002014d  movups  xmm0, xmmword ptr [rdi+8]
0x180020151  movdqu  xmmword ptr [rsp+330h+hKey], xmm0
0x180020157  lea     r8, [rsp+330h+var_300]; unsigned __int16 **
0x18002015c  lea     rdx, aSid; "SID"
0x180020163  lea     rcx, [rsp+330h+hKey]; struct _GUID
0x180020168  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x18002016d  mov     ebx, eax
0x18002016f  cmp     eax, 80070002h
0x180020174  jnz     short loc_180020183
0x180020176  lea     rcx, [rsp+330h+var_300]
0x18002017b  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x180020181  mov     ebx, eax
0x180020183  test    ebx, ebx
0x180020185  js      loc_1800202E1
0x18002018b  movups  xmm0, xmmword ptr [rdi+8]
0x18002018f  movdqu  xmmword ptr [rsp+330h+hKey], xmm0
0x180020195  lea     r8, [rsp+330h+var_2E0]; unsigned __int16 **
0x18002019a  lea     rdx, aProviderid; "ProviderID"
0x1800201a1  lea     rcx, [rsp+330h+hKey]; struct _GUID
0x1800201a6  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x1800201ab  xor     edx, edx; Val
0x1800201ad  lea     r8d, [rdx+4Eh]; Size
0x1800201b1  lea     rcx, [rbp+230h+var_280]; void *
0x1800201b5  call    memset_0
0x1800201ba  mov     [rsp+330h+hKey], 0
0x1800201c3  lea     rdx, [rbp+230h+var_280]
0x1800201c7  lea     rcx, [rsp+330h+var_2D0]
0x1800201cc  call    cs:__imp_?FindMdmEnrollmentWithLinkedEnrollment@@YAJPEBGPEAG@Z; FindMdmEnrollmentWithLinkedEnrollment(ushort const *,ushort *)
0x1800201d2  test    eax, eax
0x1800201d4  js      loc_1800202B3
0x1800201da  lea     rdx, wszURI
0x1800201e1  lea     rcx, [rbp+230h+var_280]
0x1800201e5  call    cs:__imp__o__wcsicmp
0x1800201eb  test    eax, eax
0x1800201ed  jz      loc_1800202B3
0x1800201f3  lea     rdx, [rbp+230h+var_280]
0x1800201f7  lea     rcx, [rsp+330h+var_2D0]
0x1800201fc  call    cs:__imp_?EnterpriseResourceManager_MoveAllResources@@YAJPEBG0@Z; EnterpriseResourceManager_MoveAllResources(ushort const *,ushort const *)
0x180020202  mov     ebx, eax
0x180020204  test    eax, eax
0x180020206  jns     short loc_180020231
0x180020208  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18002020d  mov     edx, ebx; int
0x18002020f  mov     rcx, rax; this
0x180020212  call    ?LogUnenrollResourceManagerFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogUnenrollResourceManagerFail(long)
0x180020217  nop
0x180020218  mov     rcx, [rsp+330h+hKey]; hKey
0x18002021d  test    rcx, rcx
0x180020220  jz      loc_1800202FB
0x180020226  call    cs:__imp_RegCloseKey
0x18002022c  jmp     loc_1800202FB
0x180020231  call    cs:__imp_RtlIsStateSeparationEnabled
0x180020237  lea     rcx, aSoftwareMicros_7; "Software\\Microsoft\\EnterpriseResource"...
0x18002023e  lea     r9, aOsdataSoftware_9; "OSData\\Software\\Microsoft\\Enterprise"...
0x180020245  test    al, al
0x180020247  cmovz   r9, rcx
0x18002024b  lea     rax, [rsp+330h+var_2D0]
0x180020250  mov     [rsp+330h+phkResult], rax
0x180020255  lea     r8, aSS_0; "%s\\%s"
0x18002025c  mov     edx, 104h; unsigned __int64
0x180020261  lea     rcx, [rbp+230h+SubKey]; unsigned __int16 *
0x180020265  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002026a  mov     ebx, eax
0x18002026c  test    eax, eax
0x18002026e  js      short loc_1800202CD
0x180020270  xor     edx, edx
0x180020272  lea     rcx, [rsp+330h+hKey]
0x180020277  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002027c  lea     rax, [rsp+330h+hKey]
0x180020281  mov     [rsp+330h+phkResult], rax; phkResult
0x180020286  mov     r9d, 2011Fh; samDesired
0x18002028c  xor     r8d, r8d; ulOptions
0x18002028f  lea     rdx, [rbp+230h+SubKey]; lpSubKey
0x180020293  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002029a  call    cs:__imp_RegOpenKeyExW
0x1800202a0  test    eax, eax
0x1800202a2  jnz     short loc_1800202CD
0x1800202a4  xor     edx, edx; lpSubKey
0x1800202a6  mov     rcx, [rsp+330h+hKey]; hKey
0x1800202ab  call    cs:__imp_RegDeleteTreeW
0x1800202b1  jmp     short loc_1800202CD
0x1800202b3  mov     r9, [rsp+330h+var_300]
0x1800202b8  mov     r8, [rsp+330h+var_2E0]
0x1800202bd  mov     edx, [rsi+18h]
0x1800202c0  lea     rcx, [rsp+330h+var_2D0]
0x1800202c5  call    cs:__imp_?EnterpriseResourceManager_UnenrollHook@@YAJPEBGH00@Z; EnterpriseResourceManager_UnenrollHook(ushort const *,int,ushort const *,ushort const *)
0x1800202cb  mov     ebx, eax
0x1800202cd  mov     rcx, [rsp+330h+hKey]; hKey
0x1800202d2  test    rcx, rcx
0x1800202d5  jz      short loc_1800202DD
0x1800202d7  call    cs:__imp_RegCloseKey
0x1800202dd  test    ebx, ebx
0x1800202df  jns     short loc_1800202F0
0x1800202e1  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800202e6  mov     edx, ebx; int
0x1800202e8  mov     rcx, rax; this
0x1800202eb  call    ?LogUnenrollResourceManagerFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogUnenrollResourceManagerFail(long)
0x1800202f0  lea     rcx, [rsp+330h+var_2D0]; unsigned __int16 *
0x1800202f5  call    ?CleanLeakedTH2Biometrics@ResourceManager@@SAXPEBG@Z; ResourceManager::CleanLeakedTH2Biometrics(ushort const *)
0x1800202fa  nop
0x1800202fb  lea     rcx, [rsp+330h+var_300]
0x180020300  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180020305  nop
0x180020306  lea     rcx, [rsp+330h+var_2E0]
0x18002030b  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180020310  mov     eax, ebx
0x180020312  mov     rcx, [rbp+230h+var_20]
0x180020319  xor     rcx, rsp; StackCookie
0x18002031c  call    __security_check_cookie
0x180020321  mov     rbx, [rsp+330h+arg_10]
0x180020329  add     rsp, 320h
0x180020330  pop     rdi
0x180020331  pop     rsi
0x180020332  pop     rbp
0x180020333  retn
```
