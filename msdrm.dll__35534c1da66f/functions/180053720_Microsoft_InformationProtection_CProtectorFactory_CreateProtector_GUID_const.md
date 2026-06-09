# Microsoft::InformationProtection::CProtectorFactory::CreateProtector(_GUID const &)

- ea: `0x180053720`
- end: `0x1800537d2`
- name: `?CreateProtector@CProtectorFactory@InformationProtection@Microsoft@@UEAA?AV?$CComPtr@UIUnknown@@@ATL@@AEBU_GUID@@@Z`
- size: `178`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000343a`
- `0x1800516b8`
- `0x180053720`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180053778`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180053778`

## string_xrefs

- `0x1800537a2`: `CoCreateInstance(clsid, NULL, CLSCTX_INPROC, IID_IUnknown, (void **)&pIUnknown)`
- `0x1800537af`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\inc\Cprotectorfactory.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LPVOID *__fastcall Microsoft::InformationProtection::CProtectorFactory::CreateProtector(
        __int64 a1,
        LPVOID *ppv,
        const IID *a3)
{
  HRESULT Instance; // eax
  _BYTE pExceptionObject[1216]; // [rsp+50h] [rbp-4D8h] BYREF

  *ppv = 0;
  Instance = CoCreateInstance(a3, 0, 3u, &IID_IUnknown, ppv);
  if ( Instance < 0 )
  {
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\inc\\Cprotectorfactory.h",
      0x1Bu,
      L"CoCreateInstance(clsid, NULL, CLSCTX_INPROC, IID_IUnknown, (void **)&pIUnknown)",
      Instance);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  return ppv;
}

```

## disassembly

```asm
0x180053720  push    rbx
0x180053722  sub     rsp, 520h
0x180053729  mov     [rsp+528h+var_4F0], 0FFFFFFFFFFFFFFFEh
0x180053732  mov     rax, cs:__security_cookie
0x180053739  xor     rax, rsp
0x18005373c  mov     [rsp+528h+var_18], rax
0x180053744  mov     rcx, r8; rclsid
0x180053747  mov     rbx, rdx
0x18005374a  mov     [rsp+528h+var_4E8], rdx
0x18005374f  mov     [rsp+528h+var_4F8], 0
0x180053757  mov     qword ptr [rdx], 0
0x18005375e  mov     [rsp+528h+var_4F8], 1
0x180053766  mov     [rsp+528h+ppv], rdx; ppv
0x18005376b  lea     r9, IID_IUnknown; riid
0x180053772  xor     edx, edx; pUnkOuter
0x180053774  lea     r8d, [rdx+3]; dwClsContext
0x180053778  call    cs:__imp_CoCreateInstance
0x18005377e  test    eax, eax
0x180053780  js      short loc_18005379E
0x180053782  mov     rax, rbx
0x180053785  mov     rcx, [rsp+528h+var_18]
0x18005378d  xor     rcx, rsp; StackCookie
0x180053790  call    __security_check_cookie
0x180053795  add     rsp, 520h
0x18005379c  pop     rbx
0x18005379d  retn
0x18005379e  mov     dword ptr [rsp+528h+ppv], eax; int
0x1800537a2  lea     r9, aCocreateinstan; "CoCreateInstance(clsid, NULL, CLSCTX_IN"...
0x1800537a9  mov     r8d, 1Bh; unsigned int
0x1800537af  lea     rdx, aDsSecurityRmSr_9; "ds\\security\\rm\\src\\client\\promethi"...
0x1800537b6  lea     rcx, [rsp+528h+pExceptionObject]; this
0x1800537bb  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800537c0  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x1800537c7  lea     rcx, [rsp+528h+pExceptionObject]; pExceptionObject
0x1800537cc  call    _CxxThrowException_0
```
