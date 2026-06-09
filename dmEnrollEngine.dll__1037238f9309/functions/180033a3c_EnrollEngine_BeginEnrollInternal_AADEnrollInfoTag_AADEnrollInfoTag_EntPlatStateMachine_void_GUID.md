# EnrollEngine::BeginEnrollInternal<AADEnrollInfoTag>(AADEnrollInfoTag *,EntPlatStateMachine,void * *,_GUID *)

- ea: `0x180033a3c`
- end: `0x180033c33`
- name: `??$BeginEnrollInternal@UAADEnrollInfoTag@@@EnrollEngine@@AEAAJPEAUAADEnrollInfoTag@@W4EntPlatStateMachine@@PEAPEAXPEAU_GUID@@@Z`
- size: `503`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *, UUID *Uuid)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180035f30`

## callees

- `0x180004870`
- `0x18000e508`
- `0x18000fbf4`
- `0x180033a3c`
- `0x180034500`
- `0x180036ed8`
- `0x18003b118`
- `0x18003b170`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033ab4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033ab4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033b2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033b2d`
- `omadmapi!__imp_OmaDmCreateInternalAcctID` at `0x180033ae5`
- `omadmapi!__imp_OmaDmCreateInternalAcctID` at `0x180033ae5`
- `RPCRT4!UuidFromStringW` at `0x180033b06`
- `RPCRT4!UuidFromStringW` at `0x180033b17`
- `RPCRT4!UuidFromStringW` at `0x180033b06`
- `RPCRT4!UuidFromStringW` at `0x180033b17`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall EnrollEngine::BeginEnrollInternal<AADEnrollInfoTag>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        UUID *Uuid)
{
  signed int Enroll; // ebx
  UUID *v9; // rsi
  __int64 v10; // rax
  int v11; // eax
  RPC_WSTR StringUuid[2]; // [rsp+30h] [rbp-10h] BYREF
  struct Enrollment *v14; // [rsp+88h] [rbp+48h] BYREF

  if ( a4 )
    *a4 = 0;
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, MDMEnrollStart, off_1800AF298);
  if ( a4 && (*a4 = 0, a2) )
  {
    v14 = (struct Enrollment *)(a1 + 88);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
    v9 = Uuid;
    v10 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)&Uuid->Data1;
    if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)&Uuid->Data1 )
      v10 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)Uuid->Data4;
    if ( v10
      || (StringUuid[0] = 0, Enroll = OmaDmCreateInternalAcctID(0, StringUuid), Enroll >= 0)
      && (!UuidFromStringW(StringUuid[0], v9)
        ? (Enroll = 0)
        : (Enroll = UuidFromStringW(StringUuid[0], v9) | 0x80010000),
          LocalFree(StringUuid[0]),
          Enroll >= 0) )
    {
      *(UUID *)StringUuid = *v9;
      v11 = EnrollEngine::CheckExistingRequestInQueue(a1, StringUuid, 0);
      Enroll = v11;
      if ( v11 >= 0 )
      {
        if ( v11 == 1
          || (*(UUID *)StringUuid = *v9,
              Enroll = EnrollEngine::CreateEnrollRequest<AADEnrollInfoTag>(a1, a2, StringUuid),
              Enroll >= 0) )
        {
          gate<critical_section>::~gate<critical_section>(&v14);
          return (unsigned int)Enroll;
        }
      }
    }
    gate<critical_section>::~gate<critical_section>(&v14);
  }
  else
  {
    Enroll = -2147024809;
  }
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
    McTemplateU0q_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, MDMEnrollStartError, (unsigned int)Enroll);
  return (unsigned int)Enroll;
}

```

## disassembly

```asm
0x180033a3c  mov     [rsp-28h+arg_0], rbx
0x180033a41  mov     [rsp-28h+arg_8], rsi
0x180033a46  mov     [rsp-28h+arg_10], r8d
0x180033a4b  push    rbp
0x180033a4c  push    rdi
0x180033a4d  push    r13
0x180033a4f  push    r14
0x180033a51  push    r15
0x180033a53  mov     rbp, rsp
0x180033a56  sub     rsp, 40h
0x180033a5a  mov     rdi, r9
0x180033a5d  mov     r15, rdx
0x180033a60  mov     r13, rcx
0x180033a63  xor     r14d, r14d
0x180033a66  mov     [rbp+arg_10], r14d
0x180033a6a  test    r9, r9
0x180033a6d  jz      short loc_180033A72
0x180033a6f  mov     [r9], r14
0x180033a72  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x180033a79  jz      short loc_180033A95
0x180033a7b  mov     r8, cs:off_1800AF298; "OR_AADENROLL"
0x180033a82  lea     rdx, MDMEnrollStart
0x180033a89  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180033a90  call    McTemplateU0z_EventWriteTransfer
0x180033a95  test    rdi, rdi
0x180033a98  jnz     short loc_180033AA4
0x180033a9a  mov     ebx, 80070057h
0x180033a9f  jmp     loc_180033BF0
0x180033aa4  mov     [rdi], r14
0x180033aa7  test    r15, r15
0x180033aaa  jz      short loc_180033A9A
0x180033aac  lea     rcx, [r13+58h]; lpCriticalSection
0x180033ab0  mov     [rbp+arg_18], rcx
0x180033ab4  call    cs:__imp_EnterCriticalSection
0x180033aba  nop
0x180033abb  mov     rsi, [rbp+Uuid]
0x180033abf  mov     rax, qword ptr cs:GUID_NULL.Data1
0x180033ac6  sub     rax, [rsi]
0x180033ac9  jnz     short loc_180033AD6
0x180033acb  mov     rax, qword ptr cs:GUID_NULL.Data4
0x180033ad2  sub     rax, [rsi+8]
0x180033ad6  test    rax, rax
0x180033ad9  jnz     short loc_180033B37
0x180033adb  mov     [rbp+StringUuid], rax
0x180033adf  lea     rdx, [rbp+StringUuid]
0x180033ae3  xor     ecx, ecx
0x180033ae5  call    cs:__imp_OmaDmCreateInternalAcctID
0x180033aeb  mov     ebx, eax
0x180033aed  test    eax, eax
0x180033aef  jns     short loc_180033AFF
0x180033af1  lea     rcx, [rbp+arg_18]
0x180033af5  call    ??1?$gate@Vcritical_section@@@@QEAA@XZ; gate<critical_section>::~gate<critical_section>(void)
0x180033afa  jmp     loc_180033B99
0x180033aff  mov     rdx, rsi; Uuid
0x180033b02  mov     rcx, [rbp+StringUuid]; StringUuid
0x180033b06  call    cs:__imp_UuidFromStringW
0x180033b0c  test    eax, eax
0x180033b0e  jz      short loc_180033B27
0x180033b10  mov     rdx, rsi; Uuid
0x180033b13  mov     rcx, [rbp+StringUuid]; StringUuid
0x180033b17  call    cs:__imp_UuidFromStringW
0x180033b1d  mov     ebx, eax
0x180033b1f  or      ebx, 80010000h
0x180033b25  jmp     short loc_180033B29
0x180033b27  xor     ebx, ebx
0x180033b29  mov     rcx, [rbp+StringUuid]; hMem
0x180033b2d  call    cs:__imp_LocalFree
0x180033b33  test    ebx, ebx
0x180033b35  js      short loc_180033AF1
0x180033b37  movups  xmm0, xmmword ptr [rsi]
0x180033b3a  movdqu  xmmword ptr [rbp+StringUuid], xmm0
0x180033b3f  xor     r8d, r8d
0x180033b42  lea     rdx, [rbp+StringUuid]
0x180033b46  mov     rcx, r13
0x180033b49  call    ?CheckExistingRequestInQueue@EnrollEngine@@AEAAJU_GUID@@W4RequestType@@@Z; EnrollEngine::CheckExistingRequestInQueue(_GUID,RequestType)
0x180033b4e  mov     ebx, eax
0x180033b50  test    eax, eax
0x180033b52  js      short loc_180033AF1
0x180033b54  cmp     eax, 1
0x180033b57  jz      loc_180033C11
0x180033b5d  movups  xmm0, xmmword ptr [rsi]
0x180033b60  movdqu  xmmword ptr [rbp+StringUuid], xmm0
0x180033b65  mov     [rsp+40h+var_18], rdi
0x180033b6a  lea     rax, [rbp+arg_10]
0x180033b6e  mov     [rsp+40h+var_20], rax
0x180033b73  lea     r8, [rbp+StringUuid]
0x180033b77  mov     rdx, r15
0x180033b7a  mov     rcx, r13
0x180033b7d  call    ??$CreateEnrollRequest@UAADEnrollInfoTag@@@EnrollEngine@@AEAAJPEAUAADEnrollInfoTag@@U_GUID@@W4EntPlatStateMachine@@PEAHPEAPEAX@Z; EnrollEngine::CreateEnrollRequest<AADEnrollInfoTag>(AADEnrollInfoTag *,_GUID,EntPlatStateMachine,int *,void * *)
0x180033b82  mov     ebx, eax
0x180033b84  test    eax, eax
0x180033b86  jns     loc_180033C11
0x180033b8c  lea     rcx, [rbp+arg_18]
0x180033b90  call    ??1?$gate@Vcritical_section@@@@QEAA@XZ; gate<critical_section>::~gate<critical_section>(void)
0x180033b95  mov     r14d, [rbp+arg_10]
0x180033b99  test    r14d, r14d
0x180033b9c  jz      short loc_180033BF0
0x180033b9e  mov     [rbp+arg_18], 0
0x180033ba6  movups  xmm0, xmmword ptr [rsi]
0x180033ba9  movdqu  xmmword ptr [rbp+StringUuid], xmm0
0x180033bae  lea     r8, [rbp+arg_18]; struct Enrollment **
0x180033bb2  lea     rdx, [rbp+StringUuid]; struct _GUID
0x180033bb6  call    ?GetEnrollmentByKey@EEDBManager@@QEAAJU_GUID@@PEAPEAVEnrollment@@@Z; EEDBManager::GetEnrollmentByKey(_GUID,Enrollment * *)
0x180033bbb  test    eax, eax
0x180033bbd  jnz     short loc_180033BE7
0x180033bbf  mov     rax, [rbp+arg_18]
0x180033bc3  movups  xmm0, xmmword ptr [rax+1Ch]
0x180033bc7  movdqu  xmmword ptr [rbp+StringUuid], xmm0
0x180033bcc  mov     rax, cs:off_1800AF740
0x180033bd3  lea     rdx, [rbp+StringUuid]
0x180033bd7  lea     rcx, off_1800AF740
0x180033bde  mov     rax, [rax]
0x180033be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033be6  nop
0x180033be7  lea     rcx, [rbp+arg_18]
0x180033beb  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x180033bf0  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x180033bf7  jz      short loc_180033C1A
0x180033bf9  mov     r8d, ebx
0x180033bfc  lea     rdx, MDMEnrollStartError
0x180033c03  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180033c0a  call    McTemplateU0q_EventWriteTransfer
0x180033c0f  jmp     short loc_180033C1A
0x180033c11  lea     rcx, [rbp+arg_18]
0x180033c15  call    ??1?$gate@Vcritical_section@@@@QEAA@XZ; gate<critical_section>::~gate<critical_section>(void)
0x180033c1a  mov     eax, ebx
0x180033c1c  mov     rbx, [rsp+40h+arg_0]
0x180033c21  mov     rsi, [rsp+40h+arg_8]
0x180033c26  add     rsp, 40h
0x180033c2a  pop     r15
0x180033c2c  pop     r14
0x180033c2e  pop     r13
0x180033c30  pop     rdi
0x180033c31  pop     rbp
0x180033c32  retn
```
