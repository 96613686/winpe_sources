# EnrollEngine::BeginEnrollInternal<MMPCEnrollInfoTag>(MMPCEnrollInfoTag *,EntPlatStateMachine,void * *,_GUID *)

- ea: `0x180033fe8`
- end: `0x1800341df`
- name: `??$BeginEnrollInternal@UMMPCEnrollInfoTag@@@EnrollEngine@@AEAAJPEAUMMPCEnrollInfoTag@@W4EntPlatStateMachine@@PEAPEAXPEAU_GUID@@@Z`
- size: `503`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *, UUID *Uuid)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180036660`

## callees

- `0x180004870`
- `0x18000e508`
- `0x18000fbf4`
- `0x180033fe8`
- `0x180034d68`
- `0x180036ed8`
- `0x18003b118`
- `0x18003b170`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034060`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034060`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800340d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800340d9`
- `omadmapi!__imp_OmaDmCreateInternalAcctID` at `0x180034091`
- `omadmapi!__imp_OmaDmCreateInternalAcctID` at `0x180034091`
- `RPCRT4!UuidFromStringW` at `0x1800340b2`
- `RPCRT4!UuidFromStringW` at `0x1800340c3`
- `RPCRT4!UuidFromStringW` at `0x1800340b2`
- `RPCRT4!UuidFromStringW` at `0x1800340c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall EnrollEngine::BeginEnrollInternal<MMPCEnrollInfoTag>(
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
    McTemplateU0z_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, MDMEnrollStart, off_1800AF2B8);
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
              Enroll = EnrollEngine::CreateEnrollRequest<MMPCEnrollInfoTag>(a1, a2, StringUuid),
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
0x180033fe8  mov     [rsp-28h+arg_0], rbx
0x180033fed  mov     [rsp-28h+arg_8], rsi
0x180033ff2  mov     [rsp-28h+arg_10], r8d
0x180033ff7  push    rbp
0x180033ff8  push    rdi
0x180033ff9  push    r13
0x180033ffb  push    r14
0x180033ffd  push    r15
0x180033fff  mov     rbp, rsp
0x180034002  sub     rsp, 40h
0x180034006  mov     rdi, r9
0x180034009  mov     r15, rdx
0x18003400c  mov     r13, rcx
0x18003400f  xor     r14d, r14d
0x180034012  mov     [rbp+arg_10], r14d
0x180034016  test    r9, r9
0x180034019  jz      short loc_18003401E
0x18003401b  mov     [r9], r14
0x18003401e  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x180034025  jz      short loc_180034041
0x180034027  mov     r8, cs:off_1800AF2B8; "OR_MMPCENROLL"
0x18003402e  lea     rdx, MDMEnrollStart
0x180034035  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18003403c  call    McTemplateU0z_EventWriteTransfer
0x180034041  test    rdi, rdi
0x180034044  jnz     short loc_180034050
0x180034046  mov     ebx, 80070057h
0x18003404b  jmp     loc_18003419C
0x180034050  mov     [rdi], r14
0x180034053  test    r15, r15
0x180034056  jz      short loc_180034046
0x180034058  lea     rcx, [r13+58h]; lpCriticalSection
0x18003405c  mov     [rbp+arg_18], rcx
0x180034060  call    cs:__imp_EnterCriticalSection
0x180034066  nop
0x180034067  mov     rsi, [rbp+Uuid]
0x18003406b  mov     rax, qword ptr cs:GUID_NULL.Data1
0x180034072  sub     rax, [rsi]
0x180034075  jnz     short loc_180034082
0x180034077  mov     rax, qword ptr cs:GUID_NULL.Data4
0x18003407e  sub     rax, [rsi+8]
0x180034082  test    rax, rax
0x180034085  jnz     short loc_1800340E3
0x180034087  mov     [rbp+StringUuid], rax
0x18003408b  lea     rdx, [rbp+StringUuid]
0x18003408f  xor     ecx, ecx
0x180034091  call    cs:__imp_OmaDmCreateInternalAcctID
0x180034097  mov     ebx, eax
0x180034099  test    eax, eax
0x18003409b  jns     short loc_1800340AB
0x18003409d  lea     rcx, [rbp+arg_18]
0x1800340a1  call    ??1?$gate@Vcritical_section@@@@QEAA@XZ; gate<critical_section>::~gate<critical_section>(void)
0x1800340a6  jmp     loc_180034145
0x1800340ab  mov     rdx, rsi; Uuid
0x1800340ae  mov     rcx, [rbp+StringUuid]; StringUuid
0x1800340b2  call    cs:__imp_UuidFromStringW
0x1800340b8  test    eax, eax
0x1800340ba  jz      short loc_1800340D3
0x1800340bc  mov     rdx, rsi; Uuid
0x1800340bf  mov     rcx, [rbp+StringUuid]; StringUuid
0x1800340c3  call    cs:__imp_UuidFromStringW
0x1800340c9  mov     ebx, eax
0x1800340cb  or      ebx, 80010000h
0x1800340d1  jmp     short loc_1800340D5
0x1800340d3  xor     ebx, ebx
0x1800340d5  mov     rcx, [rbp+StringUuid]; hMem
0x1800340d9  call    cs:__imp_LocalFree
0x1800340df  test    ebx, ebx
0x1800340e1  js      short loc_18003409D
0x1800340e3  movups  xmm0, xmmword ptr [rsi]
0x1800340e6  movdqu  xmmword ptr [rbp+StringUuid], xmm0
0x1800340eb  xor     r8d, r8d
0x1800340ee  lea     rdx, [rbp+StringUuid]
0x1800340f2  mov     rcx, r13
0x1800340f5  call    ?CheckExistingRequestInQueue@EnrollEngine@@AEAAJU_GUID@@W4RequestType@@@Z; EnrollEngine::CheckExistingRequestInQueue(_GUID,RequestType)
0x1800340fa  mov     ebx, eax
0x1800340fc  test    eax, eax
0x1800340fe  js      short loc_18003409D
0x180034100  cmp     eax, 1
0x180034103  jz      loc_1800341BD
0x180034109  movups  xmm0, xmmword ptr [rsi]
0x18003410c  movdqu  xmmword ptr [rbp+StringUuid], xmm0
0x180034111  mov     [rsp+40h+var_18], rdi
0x180034116  lea     rax, [rbp+arg_10]
0x18003411a  mov     [rsp+40h+var_20], rax
0x18003411f  lea     r8, [rbp+StringUuid]
0x180034123  mov     rdx, r15
0x180034126  mov     rcx, r13
0x180034129  call    ??$CreateEnrollRequest@UMMPCEnrollInfoTag@@@EnrollEngine@@AEAAJPEAUMMPCEnrollInfoTag@@U_GUID@@W4EntPlatStateMachine@@PEAHPEAPEAX@Z; EnrollEngine::CreateEnrollRequest<MMPCEnrollInfoTag>(MMPCEnrollInfoTag *,_GUID,EntPlatStateMachine,int *,void * *)
0x18003412e  mov     ebx, eax
0x180034130  test    eax, eax
0x180034132  jns     loc_1800341BD
0x180034138  lea     rcx, [rbp+arg_18]
0x18003413c  call    ??1?$gate@Vcritical_section@@@@QEAA@XZ; gate<critical_section>::~gate<critical_section>(void)
0x180034141  mov     r14d, [rbp+arg_10]
0x180034145  test    r14d, r14d
0x180034148  jz      short loc_18003419C
0x18003414a  mov     [rbp+arg_18], 0
0x180034152  movups  xmm0, xmmword ptr [rsi]
0x180034155  movdqu  xmmword ptr [rbp+StringUuid], xmm0
0x18003415a  lea     r8, [rbp+arg_18]; struct Enrollment **
0x18003415e  lea     rdx, [rbp+StringUuid]; struct _GUID
0x180034162  call    ?GetEnrollmentByKey@EEDBManager@@QEAAJU_GUID@@PEAPEAVEnrollment@@@Z; EEDBManager::GetEnrollmentByKey(_GUID,Enrollment * *)
0x180034167  test    eax, eax
0x180034169  jnz     short loc_180034193
0x18003416b  mov     rax, [rbp+arg_18]
0x18003416f  movups  xmm0, xmmword ptr [rax+1Ch]
0x180034173  movdqu  xmmword ptr [rbp+StringUuid], xmm0
0x180034178  mov     rax, cs:off_1800AF740
0x18003417f  lea     rdx, [rbp+StringUuid]
0x180034183  lea     rcx, off_1800AF740
0x18003418a  mov     rax, [rax]
0x18003418d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034192  nop
0x180034193  lea     rcx, [rbp+arg_18]
0x180034197  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18003419c  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x1800341a3  jz      short loc_1800341C6
0x1800341a5  mov     r8d, ebx
0x1800341a8  lea     rdx, MDMEnrollStartError
0x1800341af  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x1800341b6  call    McTemplateU0q_EventWriteTransfer
0x1800341bb  jmp     short loc_1800341C6
0x1800341bd  lea     rcx, [rbp+arg_18]
0x1800341c1  call    ??1?$gate@Vcritical_section@@@@QEAA@XZ; gate<critical_section>::~gate<critical_section>(void)
0x1800341c6  mov     eax, ebx
0x1800341c8  mov     rbx, [rsp+40h+arg_0]
0x1800341cd  mov     rsi, [rsp+40h+arg_8]
0x1800341d2  add     rsp, 40h
0x1800341d6  pop     r15
0x1800341d8  pop     r14
0x1800341da  pop     r13
0x1800341dc  pop     rdi
0x1800341dd  pop     rbp
0x1800341de  retn
```
