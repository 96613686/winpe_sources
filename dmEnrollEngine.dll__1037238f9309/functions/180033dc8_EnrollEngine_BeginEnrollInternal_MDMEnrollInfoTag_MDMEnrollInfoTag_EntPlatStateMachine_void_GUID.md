# EnrollEngine::BeginEnrollInternal<MDMEnrollInfoTag>(MDMEnrollInfoTag *,EntPlatStateMachine,void * *,_GUID *)

- ea: `0x180033dc8`
- end: `0x180033fe2`
- name: `??$BeginEnrollInternal@UMDMEnrollInfoTag@@@EnrollEngine@@AEAAJPEAUMDMEnrollInfoTag@@W4EntPlatStateMachine@@PEAPEAXPEAU_GUID@@@Z`
- size: `538`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, _QWORD *, GUID *pguid)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180036220`
- `0x180036760`

## callees

- `0x180004870`
- `0x18000e508`
- `0x18000fbf4`
- `0x180033dc8`
- `0x180034a30`
- `0x180036ed8`
- `0x18003b118`
- `0x18003b170`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033e47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033e47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033ed8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033ed8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180033e7c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180033e7c`
- `omadmapi!__imp_OmaDmCreateInternalAcctID` at `0x180033e90`
- `omadmapi!__imp_OmaDmCreateInternalAcctID` at `0x180033e90`
- `RPCRT4!UuidFromStringW` at `0x180033eb1`
- `RPCRT4!UuidFromStringW` at `0x180033ec2`
- `RPCRT4!UuidFromStringW` at `0x180033eb1`
- `RPCRT4!UuidFromStringW` at `0x180033ec2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnrollEngine::BeginEnrollInternal<MDMEnrollInfoTag>(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        _QWORD *a4,
        GUID *pguid)
{
  int v9; // r15d
  int InternalAcctID; // ebx
  UUID *v11; // rdi
  __int64 v12; // rax
  EEDBManager *v13; // rcx
  int v14; // eax
  RPC_WSTR StringUuid[2]; // [rsp+30h] [rbp-10h] BYREF
  int v17; // [rsp+90h] [rbp+50h] BYREF
  struct Enrollment *v18; // [rsp+98h] [rbp+58h] BYREF

  v9 = 0;
  v17 = 0;
  if ( a4 )
    *a4 = 0;
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, MDMEnrollStart, (&off_1800AF218)[2 * (int)a3]);
  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      v18 = (struct Enrollment *)(a1 + 88);
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
      v11 = pguid;
      v12 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)&pguid->Data1;
      if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)&pguid->Data1 )
        v12 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)pguid->Data4;
      if ( !v12 )
      {
        if ( !a3 || a3 == 10 )
        {
          StringUuid[0] = 0;
          InternalAcctID = OmaDmCreateInternalAcctID(0, StringUuid);
          if ( InternalAcctID < 0 )
            goto LABEL_15;
          if ( UuidFromStringW(StringUuid[0], v11) )
            InternalAcctID = UuidFromStringW(StringUuid[0], v11) | 0x80010000;
          else
            InternalAcctID = 0;
          LocalFree(StringUuid[0]);
        }
        else
        {
          InternalAcctID = CoCreateGuid(pguid);
        }
        if ( InternalAcctID < 0 )
          goto LABEL_15;
      }
      *(UUID *)StringUuid = *v11;
      v14 = EnrollEngine::CheckExistingRequestInQueue(a1, StringUuid, 0);
      InternalAcctID = v14;
      if ( v14 >= 0 )
      {
        if ( v14 == 1
          || (*(UUID *)StringUuid = *v11,
              InternalAcctID = ((__int64 (__fastcall *)(__int64, __int64, RPC_WSTR *, _QWORD, int *, _QWORD *))EnrollEngine::CreateEnrollRequest<MDMEnrollInfoTag>)(
                                 a1,
                                 a2,
                                 StringUuid,
                                 a3,
                                 &v17,
                                 a4),
              InternalAcctID >= 0) )
        {
          gate<critical_section>::~gate<critical_section>(&v18);
          return (unsigned int)InternalAcctID;
        }
        gate<critical_section>::~gate<critical_section>(&v18);
        v9 = v17;
        goto LABEL_25;
      }
LABEL_15:
      gate<critical_section>::~gate<critical_section>(&v18);
LABEL_25:
      if ( v9 )
      {
        v18 = 0;
        *(UUID *)StringUuid = *v11;
        if ( !EEDBManager::GetEnrollmentByKey(v13, (struct _GUID *)StringUuid, &v18) )
        {
          *(_OWORD *)StringUuid = *(_OWORD *)((char *)v18 + 28);
          ((void (__fastcall *)(void ***, RPC_WSTR *))*off_1800AF740)(&off_1800AF740, StringUuid);
        }
        wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v18);
      }
      goto LABEL_29;
    }
  }
  InternalAcctID = -2147024809;
LABEL_29:
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
    McTemplateU0q_EventWriteTransfer(
      WP_ENROLLMENT_API_PROVIDER_Context,
      MDMEnrollStartError,
      (unsigned int)InternalAcctID);
  return (unsigned int)InternalAcctID;
}

```

## disassembly

```asm
0x180033dc8  mov     [rsp-38h+arg_0], rbx
0x180033dcd  push    rbp
0x180033dce  push    rsi
0x180033dcf  push    rdi
0x180033dd0  push    r12
0x180033dd2  push    r13
0x180033dd4  push    r14
0x180033dd6  push    r15
0x180033dd8  mov     rbp, rsp
0x180033ddb  sub     rsp, 40h
0x180033ddf  mov     rsi, r9
0x180033de2  movsxd  r14, r8d
0x180033de5  mov     r12, rdx
0x180033de8  mov     r13, rcx
0x180033deb  xor     ebx, ebx
0x180033ded  mov     r15d, ebx
0x180033df0  mov     [rbp+arg_10], ebx
0x180033df3  test    r9, r9
0x180033df6  jz      short loc_180033DFB
0x180033df8  mov     [r9], rbx
0x180033dfb  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x180033e02  jz      short loc_180033E28
0x180033e04  mov     r8, r14
0x180033e07  add     r8, r8
0x180033e0a  lea     rax, off_1800AF218; "OR_MDMENROLL"
0x180033e11  mov     r8, [rax+r8*8]
0x180033e15  lea     rdx, MDMEnrollStart
0x180033e1c  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180033e23  call    McTemplateU0z_EventWriteTransfer
0x180033e28  test    rsi, rsi
0x180033e2b  jnz     short loc_180033E37
0x180033e2d  mov     ebx, 80070057h
0x180033e32  jmp     loc_180033F9E
0x180033e37  mov     [rsi], rbx
0x180033e3a  test    r12, r12
0x180033e3d  jz      short loc_180033E2D
0x180033e3f  lea     rcx, [r13+58h]; lpCriticalSection
0x180033e43  mov     [rbp+arg_18], rcx
0x180033e47  call    cs:__imp_EnterCriticalSection
0x180033e4d  nop
0x180033e4e  mov     rdi, [rbp+pguid]
0x180033e52  mov     rax, qword ptr cs:GUID_NULL.Data1
0x180033e59  sub     rax, [rdi]
0x180033e5c  jnz     short loc_180033E69
0x180033e5e  mov     rax, qword ptr cs:GUID_NULL.Data4
0x180033e65  sub     rax, [rdi+8]
0x180033e69  test    rax, rax
0x180033e6c  jnz     short loc_180033EE2
0x180033e6e  test    r14d, r14d
0x180033e71  jz      short loc_180033E86
0x180033e73  cmp     r14d, 0Ah
0x180033e77  jz      short loc_180033E86
0x180033e79  mov     rcx, rdi; pguid
0x180033e7c  call    cs:__imp_CoCreateGuid
0x180033e82  mov     ebx, eax
0x180033e84  jmp     short loc_180033EDE
0x180033e86  mov     [rbp+StringUuid], rbx
0x180033e8a  lea     rdx, [rbp+StringUuid]
0x180033e8e  xor     ecx, ecx
0x180033e90  call    cs:__imp_OmaDmCreateInternalAcctID
0x180033e96  mov     ebx, eax
0x180033e98  test    eax, eax
0x180033e9a  jns     short loc_180033EAA
0x180033e9c  lea     rcx, [rbp+arg_18]
0x180033ea0  call    ??1?$gate@Vcritical_section@@@@QEAA@XZ; gate<critical_section>::~gate<critical_section>(void)
0x180033ea5  jmp     loc_180033F47
0x180033eaa  mov     rdx, rdi; Uuid
0x180033ead  mov     rcx, [rbp+StringUuid]; StringUuid
0x180033eb1  call    cs:__imp_UuidFromStringW
0x180033eb7  test    eax, eax
0x180033eb9  jz      short loc_180033ED2
0x180033ebb  mov     rdx, rdi; Uuid
0x180033ebe  mov     rcx, [rbp+StringUuid]; StringUuid
0x180033ec2  call    cs:__imp_UuidFromStringW
0x180033ec8  mov     ebx, eax
0x180033eca  or      ebx, 80010000h
0x180033ed0  jmp     short loc_180033ED4
0x180033ed2  xor     ebx, ebx
0x180033ed4  mov     rcx, [rbp+StringUuid]; hMem
0x180033ed8  call    cs:__imp_LocalFree
0x180033ede  test    ebx, ebx
0x180033ee0  js      short loc_180033E9C
0x180033ee2  movups  xmm0, xmmword ptr [rdi]
0x180033ee5  movdqu  xmmword ptr [rbp+StringUuid], xmm0
0x180033eea  xor     r8d, r8d
0x180033eed  lea     rdx, [rbp+StringUuid]
0x180033ef1  mov     rcx, r13
0x180033ef4  call    ?CheckExistingRequestInQueue@EnrollEngine@@AEAAJU_GUID@@W4RequestType@@@Z; EnrollEngine::CheckExistingRequestInQueue(_GUID,RequestType)
0x180033ef9  mov     ebx, eax
0x180033efb  test    eax, eax
0x180033efd  js      short loc_180033E9C
0x180033eff  cmp     eax, 1
0x180033f02  jz      loc_180033FBF
0x180033f08  movups  xmm0, xmmword ptr [rdi]
0x180033f0b  movdqu  xmmword ptr [rbp+StringUuid], xmm0
0x180033f10  mov     [rsp+40h+var_18], rsi
0x180033f15  lea     rax, [rbp+arg_10]
0x180033f19  mov     [rsp+40h+var_20], rax
0x180033f1e  mov     r9d, r14d
0x180033f21  lea     r8, [rbp+StringUuid]
0x180033f25  mov     rdx, r12
0x180033f28  mov     rcx, r13
0x180033f2b  call    ??$CreateEnrollRequest@UMDMEnrollInfoTag@@@EnrollEngine@@AEAAJPEAUMDMEnrollInfoTag@@U_GUID@@W4EntPlatStateMachine@@PEAHPEAPEAX@Z; EnrollEngine::CreateEnrollRequest<MDMEnrollInfoTag>(MDMEnrollInfoTag *,_GUID,EntPlatStateMachine,int *,void * *)
0x180033f30  mov     ebx, eax
0x180033f32  test    eax, eax
0x180033f34  jns     loc_180033FBF
0x180033f3a  lea     rcx, [rbp+arg_18]
0x180033f3e  call    ??1?$gate@Vcritical_section@@@@QEAA@XZ; gate<critical_section>::~gate<critical_section>(void)
0x180033f43  mov     r15d, [rbp+arg_10]
0x180033f47  test    r15d, r15d
0x180033f4a  jz      short loc_180033F9E
0x180033f4c  mov     [rbp+arg_18], 0
0x180033f54  movups  xmm0, xmmword ptr [rdi]
0x180033f57  movdqu  xmmword ptr [rbp+StringUuid], xmm0
0x180033f5c  lea     r8, [rbp+arg_18]; struct Enrollment **
0x180033f60  lea     rdx, [rbp+StringUuid]; struct _GUID
0x180033f64  call    ?GetEnrollmentByKey@EEDBManager@@QEAAJU_GUID@@PEAPEAVEnrollment@@@Z; EEDBManager::GetEnrollmentByKey(_GUID,Enrollment * *)
0x180033f69  test    eax, eax
0x180033f6b  jnz     short loc_180033F95
0x180033f6d  mov     rax, [rbp+arg_18]
0x180033f71  movups  xmm0, xmmword ptr [rax+1Ch]
0x180033f75  movdqu  xmmword ptr [rbp+StringUuid], xmm0
0x180033f7a  mov     rax, cs:off_1800AF740
0x180033f81  lea     rdx, [rbp+StringUuid]
0x180033f85  lea     rcx, off_1800AF740
0x180033f8c  mov     rax, [rax]
0x180033f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f94  nop
0x180033f95  lea     rcx, [rbp+arg_18]
0x180033f99  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x180033f9e  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x180033fa5  jz      short loc_180033FC8
0x180033fa7  mov     r8d, ebx
0x180033faa  lea     rdx, MDMEnrollStartError
0x180033fb1  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180033fb8  call    McTemplateU0q_EventWriteTransfer
0x180033fbd  jmp     short loc_180033FC8
0x180033fbf  lea     rcx, [rbp+arg_18]
0x180033fc3  call    ??1?$gate@Vcritical_section@@@@QEAA@XZ; gate<critical_section>::~gate<critical_section>(void)
0x180033fc8  mov     eax, ebx
0x180033fca  mov     rbx, [rsp+40h+arg_0]
0x180033fd2  add     rsp, 40h
0x180033fd6  pop     r15
0x180033fd8  pop     r14
0x180033fda  pop     r13
0x180033fdc  pop     r12
0x180033fde  pop     rdi
0x180033fdf  pop     rsi
0x180033fe0  pop     rbp
0x180033fe1  retn
```
