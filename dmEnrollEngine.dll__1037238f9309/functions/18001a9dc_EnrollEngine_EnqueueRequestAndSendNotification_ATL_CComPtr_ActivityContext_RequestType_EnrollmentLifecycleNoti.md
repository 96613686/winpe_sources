# EnrollEngine::EnqueueRequestAndSendNotification(ATL::CComPtr<ActivityContext> &,RequestType,EnrollmentLifecycleNotificationType)

- ea: `0x18001a9dc`
- end: `0x18001ab38`
- name: `?EnqueueRequestAndSendNotification@EnrollEngine@@AEAAJAEAV?$CComPtr@VActivityContext@@@ATL@@W4RequestType@@W4EnrollmentLifecycleNotificationType@@@Z`
- size: `348`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180034500`
- `0x180034a30`
- `0x180034d68`
- `0x180037230`
- `0x180038ecc`

## callees

- `0x18000de50`
- `0x18000dec0`
- `0x18000e508`
- `0x18000e52c`
- `0x18000fbf4`
- `0x180019e8c`
- `0x18001a9dc`
- `0x18001ab40`
- `0x18003a918`
- `0x180040240`
- `0x18004252c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001aab7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001aab7`
- `DMCmnUtils!DmRevertToSelf` at `0x18001aa5a`
- `DMCmnUtils!DmRevertToSelf` at `0x18001aa5a`
- `DMCmnUtils!DmImpersonate` at `0x18001aa50`
- `DMCmnUtils!DmImpersonate` at `0x18001aa50`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EnrollEngine::EnqueueRequestAndSendNotification(
        __int64 a1,
        struct IUnknown **a2,
        unsigned int a3,
        int a4)
{
  struct IUnknownVtbl *lpVtbl; // rdi
  int v9; // eax
  __int64 v11; // rcx
  int v12; // ebx
  int v13; // [rsp+20h] [rbp-38h]
  struct _GUID v14; // [rsp+30h] [rbp-28h] BYREF
  struct _SYSTEMTIME v15; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  LPCWSTR lpSubKey; // [rsp+98h] [rbp+40h] BYREF

  if ( !*a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  lpVtbl = (*a2)[52].lpVtbl;
  if ( !lpVtbl )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( a3 == 2 )
  {
    lpSubKey = 0;
    v14 = *(struct _GUID *)&(*a2)[1].lpVtbl;
    if ( EEDBManager::GetEnrollmentString(&v14, L"SID", (unsigned __int16 **)&lpSubKey) >= 0 )
    {
      if ( (int)DmImpersonate(lpSubKey) < 0 )
      {
        if ( !(unsigned int)IsSIDInvalid(lpSubKey) )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
          CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&lpSubKey);
          return 1;
        }
      }
      else
      {
        v9 = DmRevertToSelf();
        if ( v9 < 0 )
          wil::details::in1diag3::_FailFast_Hr(
            retaddr,
            (void *)0x7F1,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\core\\enrollengine.cpp",
            (const char *)(unsigned int)v9,
            v13);
      }
    }
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&lpSubKey);
  }
  lpSubKey = (LPCWSTR)(a1 + 128);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 128));
  *(_QWORD *)v14.Data4 = 0;
  v14.Data1 = a3;
  if ( *a2 )
    ATL::AtlComPtrAssign((struct IUnknown **)v14.Data4, *a2);
  v12 = RequestQueue::EnqueueRequest((RequestQueue *)(a1 + 8), (const struct Request *)&v14, 0);
  if ( v12 >= 0 )
  {
    v15 = *(struct _SYSTEMTIME *)((char *)&lpVtbl[1].QueryInterface + 4);
    v12 = EEDBManager::SetNotificationStatus(v11, lpVtbl[74].Release, &v15, a4, 0);
  }
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)v14.Data4);
  gate<critical_section>::~gate<critical_section>((struct _RTL_CRITICAL_SECTION **)&lpSubKey);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001a9dc  push    rbp
0x18001a9de  push    rbx
0x18001a9df  push    rsi
0x18001a9e0  push    rdi
0x18001a9e1  push    r14
0x18001a9e3  push    r15
0x18001a9e5  mov     rbp, rsp
0x18001a9e8  sub     rsp, 58h
0x18001a9ec  mov     r15d, r9d
0x18001a9ef  mov     esi, r8d
0x18001a9f2  mov     rbx, rdx
0x18001a9f5  mov     r14, rcx
0x18001a9f8  cmp     qword ptr [rdx], 0
0x18001a9fc  jnz     short loc_18001AA03
0x18001a9fe  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "spContext != NULL")
0x18001aa03  mov     rax, [rbx]
0x18001aa06  mov     rdi, [rax+1A0h]
0x18001aa0d  test    rdi, rdi
0x18001aa10  jnz     short loc_18001AA17
0x18001aa12  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pEnroll != NULL")
0x18001aa17  cmp     esi, 2
0x18001aa1a  jnz     loc_18001AAAC
0x18001aa20  mov     [rbp+lpSubKey], 0
0x18001aa28  mov     rax, [rbx]
0x18001aa2b  movups  xmm0, xmmword ptr [rax+8]
0x18001aa2f  movdqu  xmmword ptr [rbp+var_28.Data1], xmm0
0x18001aa34  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x18001aa38  lea     rdx, aSid; "SID"
0x18001aa3f  lea     rcx, [rbp+var_28]; struct _GUID
0x18001aa43  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x18001aa48  test    eax, eax
0x18001aa4a  js      short loc_18001AAA3
0x18001aa4c  mov     rcx, [rbp+lpSubKey]
0x18001aa50  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x18001aa56  test    eax, eax
0x18001aa58  js      short loc_18001AA7D
0x18001aa5a  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18001aa60  mov     rcx, [rbp+30h]; this
0x18001aa64  test    eax, eax
0x18001aa66  jns     short loc_18001AAA3
0x18001aa68  mov     r9d, eax; char *
0x18001aa6b  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001aa72  mov     edx, 7F1h; void *
0x18001aa77  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001aa7d  mov     rcx, [rbp+lpSubKey]; lpSubKey
0x18001aa81  call    ?IsSIDInvalid@@YAHPEBG@Z; IsSIDInvalid(ushort const *)
0x18001aa86  test    eax, eax
0x18001aa88  jnz     short loc_18001AAA3
0x18001aa8a  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FALSE")
0x18001aa8f  nop
0x18001aa90  lea     rcx, [rbp+lpSubKey]
0x18001aa94  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18001aa99  mov     eax, 1
0x18001aa9e  jmp     loc_18001AB2B
0x18001aaa3  lea     rcx, [rbp+lpSubKey]
0x18001aaa7  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18001aaac  lea     rcx, [r14+80h]; lpCriticalSection
0x18001aab3  mov     [rbp+lpSubKey], rcx
0x18001aab7  call    cs:__imp_EnterCriticalSection
0x18001aabd  nop
0x18001aabe  mov     qword ptr [rbp+var_28.Data4], 0
0x18001aac6  mov     [rbp+var_28.Data1], esi
0x18001aac9  mov     rdx, [rbx]; struct IUnknown *
0x18001aacc  test    rdx, rdx
0x18001aacf  jz      short loc_18001AADA
0x18001aad1  lea     rcx, [rbp+var_28.Data4]; struct IUnknown **
0x18001aad5  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001aada  lea     rcx, [r14+8]; this
0x18001aade  xor     r8d, r8d; int
0x18001aae1  lea     rdx, [rbp+var_28]; struct Request *
0x18001aae5  call    ?EnqueueRequest@RequestQueue@@AEAAJAEBURequest@@H@Z; RequestQueue::EnqueueRequest(Request const &,int)
0x18001aaea  mov     ebx, eax
0x18001aaec  test    eax, eax
0x18001aaee  js      short loc_18001AB16
0x18001aaf0  movups  xmm0, xmmword ptr [rdi+1Ch]
0x18001aaf4  movdqu  xmmword ptr [rbp+var_18.wYear], xmm0
0x18001aaf9  mov     [rsp+58h+var_38], 0
0x18001ab01  mov     r9d, r15d
0x18001ab04  lea     r8, [rbp+var_18]
0x18001ab08  mov     rdx, [rdi+700h]
0x18001ab0f  call    ?SetNotificationStatus@EEDBManager@@QEAAJPEAXU_GUID@@W4EnrollmentLifecycleNotificationType@@JK@Z; EEDBManager::SetNotificationStatus(void *,_GUID,EnrollmentLifecycleNotificationType,long,ulong)
0x18001ab14  mov     ebx, eax
0x18001ab16  lea     rcx, [rbp+var_28.Data4]
0x18001ab1a  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18001ab1f  nop
0x18001ab20  lea     rcx, [rbp+lpSubKey]
0x18001ab24  call    ??1?$gate@Vcritical_section@@@@QEAA@XZ; gate<critical_section>::~gate<critical_section>(void)
0x18001ab29  mov     eax, ebx
0x18001ab2b  add     rsp, 58h
0x18001ab2f  pop     r15
0x18001ab31  pop     r14
0x18001ab33  pop     rdi
0x18001ab34  pop     rsi
0x18001ab35  pop     rbx
0x18001ab36  pop     rbp
0x18001ab37  retn
```
