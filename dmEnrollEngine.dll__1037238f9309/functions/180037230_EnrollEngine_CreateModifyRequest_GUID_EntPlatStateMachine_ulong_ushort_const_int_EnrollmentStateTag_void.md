# EnrollEngine::CreateModifyRequest(_GUID,EntPlatStateMachine,ulong,ushort const *,int *,EnrollmentStateTag *,void * *)

- ea: `0x180037230`
- end: `0x1800375e4`
- name: `?CreateModifyRequest@EnrollEngine@@AEAAJU_GUID@@W4EntPlatStateMachine@@KPEBGPEAHPEAW4EnrollmentStateTag@@PEAPEAX@Z`
- size: `948`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d42c`

## callees

- `0x1800010c0`
- `0x180004870`
- `0x18000dec0`
- `0x18000e508`
- `0x180010fcc`
- `0x18001a9dc`
- `0x18001ac7c`
- `0x18001d580`
- `0x18001ee2c`
- `0x18002e5ac`
- `0x1800359c4`
- `0x180037230`
- `0x18003a020`
- `0x180041420`
- `0x180041490`
- `0x1800414cc`
- `0x180041574`
- `0x1800415c0`
- `0x180041668`
- `0x180041778`
- `0x1800417cc`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003755e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003755e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180037527`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180037530`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180037527`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180037530`
- `api-ms-win-core-handle-l1-1-0!GetHandleInformation` at `0x18003732f`
- `api-ms-win-core-handle-l1-1-0!GetHandleInformation` at `0x180037516`
- `api-ms-win-core-handle-l1-1-0!GetHandleInformation` at `0x18003732f`
- `api-ms-win-core-handle-l1-1-0!GetHandleInformation` at `0x180037516`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180037554`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180037554`
- `omadmapi!__imp_OmaDmCreateInternalAcctID` at `0x1800374b1`
- `omadmapi!__imp_OmaDmCreateInternalAcctID` at `0x1800374b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall EnrollEngine::CreateModifyRequest(
        EEDBManager *a1,
        ActivityContext *a2,
        __int64 a3,
        __int64 a4,
        ActivityContext *a5,
        _DWORD *a6,
        _DWORD *a7,
        void **lpTargetHandle)
{
  __int64 v8; // r14
  ActivityContext *v9; // rdi
  signed int v11; // esi
  int EnrollmentByKey; // eax
  unsigned int v13; // edx
  Enrollment *v14; // rdi
  int NotifEventHandle; // eax
  ActivityContext *v16; // rax
  struct IUnknown *v17; // rax
  struct IUnknown *v18; // rbx
  const unsigned __int16 *v19; // rdx
  unsigned int v20; // eax
  void *v21; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v23; // rax
  signed int LastError; // eax
  ActivityContext *v26; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int16 *v27; // [rsp+48h] [rbp-41h] BYREF
  DWORD dwFlags; // [rsp+50h] [rbp-39h] BYREF
  Enrollment *v29; // [rsp+58h] [rbp-31h] BYREF
  struct IUnknown *v30; // [rsp+60h] [rbp-29h] BYREF
  ActivityContext *v31; // [rsp+68h] [rbp-21h] BYREF
  ActivityContext *v32; // [rsp+70h] [rbp-19h] BYREF
  struct _GUID v33; // [rsp+80h] [rbp-9h] BYREF

  LODWORD(v27) = a4;
  v8 = (int)a3;
  v9 = a2;
  v26 = a2;
  v31 = a5;
  v30 = 0;
  v32 = 0;
  v29 = 0;
  if ( !a6 || !a7 )
  {
    v11 = -2147024809;
    goto LABEL_44;
  }
  *a6 = 0;
  v33 = *(struct _GUID *)a2;
  EnrollmentByKey = EEDBManager::GetEnrollmentByKey(a1, &v33, &v29);
  v11 = EnrollmentByKey;
  if ( EnrollmentByKey != -2147024894 )
  {
    if ( EnrollmentByKey < 0 )
      goto LABEL_44;
    dwFlags = 0;
    if ( (((_DWORD)v8 - 5) & 0xFFFFFFFD) == 0 && lpTargetHandle && GetHandleInformation(*lpTargetHandle, &dwFlags) )
    {
      v14 = v29;
      NotifEventHandle = Enrollment::SetNotifEventHandle(v29, *lpTargetHandle);
    }
    else
    {
      *lpTargetHandle = 0;
      v14 = v29;
      NotifEventHandle = Enrollment::CreateNotifEventHandle(v29);
    }
    v11 = NotifEventHandle;
    if ( NotifEventHandle < 0 )
      goto LABEL_43;
    *a7 = *((_DWORD *)v14 + 6);
    v33 = *(struct _GUID *)((char *)v14 + 28);
    if ( (int)EEDBManager::SetEnrollState(&v33) >= 0 )
      *a6 = 1;
    v16 = (ActivityContext *)operator new(0x3D8u, (const struct std::nothrow_t *)&std::nothrow);
    *(_QWORD *)&v33.Data1 = v16;
    if ( !v16
      || (v17 = (struct IUnknown *)ActivityContext::ActivityContext(v16)) == 0
      || (ATL::AtlComPtrAssign(&v30, v17), (v18 = v30) == 0) )
    {
      v11 = -2147024882;
      goto LABEL_43;
    }
    v11 = ActivityContext::set_Key((ActivityContext *)v30, (const struct _GUID *)((char *)v14 + 28));
    if ( v11 >= 0 )
    {
      v18[3].lpVtbl = (struct IUnknownVtbl *)a1;
      if ( (_DWORD)v8 == 11 )
      {
        if ( !v31 )
        {
          v11 = -2147024809;
          goto LABEL_43;
        }
        v19 = (const unsigned __int16 *)v31;
      }
      else
      {
        v19 = &wszURI;
      }
      v11 = ActivityContext::set_Secret((ActivityContext *)v18, v19);
      if ( v11 < 0 )
        goto LABEL_43;
      LODWORD(v18[9].lpVtbl) = (_DWORD)v27;
      if ( !v18[52].lpVtbl )
      {
        v11 = ActivityContext::set_Enrollment((ActivityContext *)v18, v14);
        if ( v11 < 0 )
          goto LABEL_43;
        HIDWORD(v18[121].lpVtbl) = *((_DWORD *)v14 + 15);
        v11 = ActivityContext::set_OrchestratorType((ActivityContext *)v18, (&off_1800AF218)[2 * v8]);
        if ( v11 < 0 )
          goto LABEL_43;
      }
      if ( !ActivityContext::get_CorrelationID((ActivityContext *)v18) )
      {
        v27 = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v27,
          0);
        v11 = OmaDmCreateInternalAcctID(0, &v27);
        if ( v11 < 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
          goto LABEL_43;
        }
        ActivityContext::set_CorrelationID((ActivityContext *)v18, v27);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
      }
      v20 = StateToRequestType((unsigned int)v8);
      v11 = EnrollEngine::EnqueueRequestAndSendNotification(a1, &v30, v20, 4);
      if ( v11 >= 0 && ((_DWORD)v8 != 5 || !*lpTargetHandle || !GetHandleInformation(*lpTargetHandle, &dwFlags)) )
      {
        v21 = (void *)*((_QWORD *)v14 + 224);
        CurrentProcess = GetCurrentProcess();
        v23 = GetCurrentProcess();
        if ( DuplicateHandle(v23, v21, CurrentProcess, lpTargetHandle, 0, 0, 2u) )
        {
          v11 = 0;
        }
        else
        {
          LastError = GetLastError();
          v11 = LastError;
          if ( LastError > 0 )
            v11 = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
LABEL_43:
    v9 = v26;
    goto LABEL_44;
  }
  v26 = 0;
  if ( (*(int (__fastcall **)(_QWORD *, ActivityContext *, ActivityContext **))(**((_QWORD **)a1 + 25) + 16LL))(
         *((_QWORD **)a1 + 25),
         v9,
         &v32) >= 0 )
  {
    v26 = v32;
    (*(void (__fastcall **)(_QWORD *))(**((_QWORD **)a1 + 25) + 32LL))(*((_QWORD **)a1 + 25));
  }
  v11 = -2145910757;
  std::unique_ptr<ActivityContext>::~unique_ptr<ActivityContext>(&v26, v13);
LABEL_44:
  if ( (unsigned int)dword_1800AF3E8 > 5 )
  {
    LODWORD(v27) = v11;
    v31 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      (__int64)a1,
      (__int64)byte_18009E32D,
      a3,
      a4,
      &v31,
      (__int64)&v27);
  }
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&v29);
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&v30);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180037230  mov     [rsp-8+arg_18], rbx
0x180037235  push    rbp
0x180037236  push    rsi
0x180037237  push    rdi
0x180037238  push    r12
0x18003723a  push    r13
0x18003723c  push    r14
0x18003723e  push    r15
0x180037240  lea     rbp, [rsp-7]
0x180037245  sub     rsp, 90h
0x18003724c  mov     dword ptr [rbp+37h+var_78], r9d
0x180037250  movsxd  r14, r8d
0x180037253  mov     rdi, rdx
0x180037256  mov     [rbp+37h+var_80], rdx
0x18003725a  mov     r13, rcx
0x18003725d  mov     rax, [rbp+37h+arg_20]
0x180037261  mov     [rbp+37h+var_58], rax
0x180037265  mov     r12, [rbp+37h+arg_28]
0x180037269  mov     rbx, [rbp+37h+arg_30]
0x18003726d  mov     r15, [rbp+37h+lpTargetHandle]
0x180037271  xor     eax, eax
0x180037273  mov     [rbp+37h+var_60], rax
0x180037277  mov     [rbp+37h+var_50], rax
0x18003727b  mov     [rbp+37h+var_68], rax
0x18003727f  test    r12, r12
0x180037282  jnz     short loc_18003728E
0x180037284  mov     esi, 80070057h
0x180037289  jmp     loc_180037583
0x18003728e  test    rbx, rbx
0x180037291  jz      short loc_180037284
0x180037293  mov     [r12], eax
0x180037297  movups  xmm0, xmmword ptr [rdx]
0x18003729a  movdqu  xmmword ptr [rbp+37h+var_40.Data1], xmm0
0x18003729f  lea     r8, [rbp+37h+var_68]; struct Enrollment **
0x1800372a3  lea     rdx, [rbp+37h+var_40]; struct _GUID
0x1800372a7  call    ?GetEnrollmentByKey@EEDBManager@@QEAAJU_GUID@@PEAPEAVEnrollment@@@Z; EEDBManager::GetEnrollmentByKey(_GUID,Enrollment * *)
0x1800372ac  mov     esi, eax
0x1800372ae  cmp     eax, 80070002h
0x1800372b3  jnz     short loc_180037309
0x1800372b5  mov     [rbp+37h+var_80], 0
0x1800372bd  mov     rcx, [r13+0C8h]
0x1800372c4  mov     rax, [rcx]
0x1800372c7  lea     r8, [rbp+37h+var_50]
0x1800372cb  mov     rdx, rdi
0x1800372ce  mov     rax, [rax+10h]
0x1800372d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800372d7  test    eax, eax
0x1800372d9  js      short loc_1800372F6
0x1800372db  mov     rdx, [rbp+37h+var_50]
0x1800372df  mov     [rbp+37h+var_80], rdx
0x1800372e3  mov     rcx, [r13+0C8h]
0x1800372ea  mov     rax, [rcx]
0x1800372ed  mov     rax, [rax+20h]
0x1800372f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800372f6  mov     esi, 8018001Bh
0x1800372fb  lea     rcx, [rbp+37h+var_80]
0x1800372ff  call    ??1?$unique_ptr@VActivityContext@@U?$default_delete@VActivityContext@@@std@@@std@@QEAA@XZ; std::unique_ptr<ActivityContext>::~unique_ptr<ActivityContext>(void)
0x180037304  jmp     loc_180037583
0x180037309  test    eax, eax
0x18003730b  js      loc_180037583
0x180037311  mov     [rbp+37h+dwFlags], 0
0x180037318  lea     eax, [r14-5]
0x18003731c  test    eax, 0FFFFFFFDh
0x180037321  jnz     short loc_18003734A
0x180037323  test    r15, r15
0x180037326  jz      short loc_18003734A
0x180037328  lea     rdx, [rbp+37h+dwFlags]; lpdwFlags
0x18003732c  mov     rcx, [r15]; hObject
0x18003732f  call    cs:__imp_GetHandleInformation
0x180037335  test    eax, eax
0x180037337  jz      short loc_18003734A
0x180037339  mov     rdx, [r15]; void *
0x18003733c  mov     rdi, [rbp+37h+var_68]
0x180037340  mov     rcx, rdi; this
0x180037343  call    ?SetNotifEventHandle@Enrollment@@QEAAJPEAX@Z; Enrollment::SetNotifEventHandle(void *)
0x180037348  jmp     short loc_18003735D
0x18003734a  mov     qword ptr [r15], 0
0x180037351  mov     rdi, [rbp+37h+var_68]
0x180037355  mov     rcx, rdi; this
0x180037358  call    ?CreateNotifEventHandle@Enrollment@@QEAAJXZ; Enrollment::CreateNotifEventHandle(void)
0x18003735d  mov     esi, eax
0x18003735f  test    eax, eax
0x180037361  js      loc_18003757F
0x180037367  mov     eax, [rdi+18h]
0x18003736a  mov     [rbx], eax
0x18003736c  mov     edx, 3
0x180037371  cmp     r14d, edx
0x180037374  jz      short loc_180037385
0x180037376  mov     edx, 4
0x18003737b  lea     eax, [rdx+2]
0x18003737e  cmp     r14d, 0Bh
0x180037382  cmovz   edx, eax
0x180037385  movups  xmm0, xmmword ptr [rdi+1Ch]
0x180037389  movdqu  xmmword ptr [rbp+37h+var_40.Data1], xmm0
0x18003738e  lea     rcx, [rbp+37h+var_40]
0x180037392  call    ?SetEnrollState@EEDBManager@@SAJU_GUID@@W4EnrollmentStateTag@@@Z; EEDBManager::SetEnrollState(_GUID,EnrollmentStateTag)
0x180037397  test    eax, eax
0x180037399  js      short loc_1800373A3
0x18003739b  mov     dword ptr [r12], 1
0x1800373a3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800373aa  mov     ecx, 3D8h; unsigned __int64
0x1800373af  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800373b4  mov     qword ptr [rbp+37h+var_40.Data1], rax
0x1800373b8  xor     r12d, r12d
0x1800373bb  test    rax, rax
0x1800373be  jz      loc_18003757A
0x1800373c4  mov     rcx, rax; this
0x1800373c7  call    ??0ActivityContext@@QEAA@XZ; ActivityContext::ActivityContext(void)
0x1800373cc  test    rax, rax
0x1800373cf  jz      loc_18003757A
0x1800373d5  mov     rdx, rax; struct IUnknown *
0x1800373d8  lea     rcx, [rbp+37h+var_60]; struct IUnknown **
0x1800373dc  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800373e1  mov     rbx, [rbp+37h+var_60]
0x1800373e5  test    rbx, rbx
0x1800373e8  jz      loc_18003757A
0x1800373ee  lea     rdx, [rdi+1Ch]; struct _GUID *
0x1800373f2  mov     rcx, rbx; this
0x1800373f5  call    ?set_Key@ActivityContext@@QEAAJAEBU_GUID@@@Z; ActivityContext::set_Key(_GUID const &)
0x1800373fa  mov     esi, eax
0x1800373fc  test    eax, eax
0x1800373fe  js      loc_18003757F
0x180037404  mov     [rbx+18h], r13
0x180037408  cmp     r14d, 0Bh
0x18003740c  jnz     short loc_180037426
0x18003740e  mov     rax, [rbp+37h+var_58]
0x180037412  test    rax, rax
0x180037415  jnz     short loc_180037421
0x180037417  mov     esi, 80070057h
0x18003741c  jmp     loc_18003757F
0x180037421  mov     rdx, rax
0x180037424  jmp     short loc_18003742D
0x180037426  lea     rdx, wszURI; unsigned __int16 *
0x18003742d  mov     rcx, rbx; this
0x180037430  call    ?set_Secret@ActivityContext@@QEAAJPEBG@Z; ActivityContext::set_Secret(ushort const *)
0x180037435  test    eax, eax
0x180037437  mov     esi, eax
0x180037439  js      loc_18003757F
0x18003743f  mov     eax, dword ptr [rbp+37h+var_78]
0x180037442  mov     [rbx+48h], eax
0x180037445  cmp     [rbx+1A0h], r12
0x18003744c  jnz     short loc_18003748F
0x18003744e  mov     rdx, rdi; struct Enrollment *
0x180037451  mov     rcx, rbx; this
0x180037454  call    ?set_Enrollment@ActivityContext@@QEAAJPEAVEnrollment@@@Z; ActivityContext::set_Enrollment(Enrollment *)
0x180037459  mov     esi, eax
0x18003745b  test    eax, eax
0x18003745d  js      loc_18003757F
0x180037463  mov     eax, [rdi+3Ch]
0x180037466  mov     [rbx+3CCh], eax
0x18003746c  mov     rdx, r14
0x18003746f  add     rdx, rdx
0x180037472  lea     rax, off_1800AF218; "OR_MDMENROLL"
0x180037479  mov     rdx, [rax+rdx*8]; unsigned __int16 *
0x18003747d  mov     rcx, rbx; this
0x180037480  call    ?set_OrchestratorType@ActivityContext@@QEAAJPEBG@Z; ActivityContext::set_OrchestratorType(ushort const *)
0x180037485  mov     esi, eax
0x180037487  test    eax, eax
0x180037489  js      loc_18003757F
0x18003748f  mov     rcx, rbx; this
0x180037492  call    ?get_CorrelationID@ActivityContext@@QEBAPEBGXZ; ActivityContext::get_CorrelationID(void)
0x180037497  test    rax, rax
0x18003749a  jnz     short loc_1800374E1
0x18003749c  mov     [rbp+37h+var_78], r12
0x1800374a0  xor     edx, edx
0x1800374a2  lea     rcx, [rbp+37h+var_78]
0x1800374a6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800374ab  lea     rdx, [rbp+37h+var_78]
0x1800374af  xor     ecx, ecx
0x1800374b1  call    cs:__imp_OmaDmCreateInternalAcctID
0x1800374b7  mov     esi, eax
0x1800374b9  test    eax, eax
0x1800374bb  jns     short loc_1800374CB
0x1800374bd  lea     rcx, [rbp+37h+var_78]
0x1800374c1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800374c6  jmp     loc_18003757F
0x1800374cb  mov     rdx, [rbp+37h+var_78]; unsigned __int16 *
0x1800374cf  mov     rcx, rbx; this
0x1800374d2  call    ?set_CorrelationID@ActivityContext@@QEAAXPEBG@Z; ActivityContext::set_CorrelationID(ushort const *)
0x1800374d7  nop
0x1800374d8  lea     rcx, [rbp+37h+var_78]
0x1800374dc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800374e1  mov     ecx, r14d
0x1800374e4  call    StateToRequestType
0x1800374e9  mov     r8d, eax
0x1800374ec  mov     r9d, 4
0x1800374f2  lea     rdx, [rbp+37h+var_60]
0x1800374f6  mov     rcx, r13
0x1800374f9  call    ?EnqueueRequestAndSendNotification@EnrollEngine@@AEAAJAEAV?$CComPtr@VActivityContext@@@ATL@@W4RequestType@@W4EnrollmentLifecycleNotificationType@@@Z; EnrollEngine::EnqueueRequestAndSendNotification(ATL::CComPtr<ActivityContext> &,RequestType,EnrollmentLifecycleNotificationType)
0x1800374fe  mov     esi, eax
0x180037500  test    eax, eax
0x180037502  js      short loc_18003757F
0x180037504  cmp     r14d, 5
0x180037508  jnz     short loc_180037520
0x18003750a  mov     rcx, [r15]; hObject
0x18003750d  test    rcx, rcx
0x180037510  jz      short loc_180037520
0x180037512  lea     rdx, [rbp+37h+dwFlags]; lpdwFlags
0x180037516  call    cs:__imp_GetHandleInformation
0x18003751c  test    eax, eax
0x18003751e  jnz     short loc_18003757F
0x180037520  mov     rdi, [rdi+700h]
0x180037527  call    cs:__imp_GetCurrentProcess
0x18003752d  mov     rbx, rax
0x180037530  call    cs:__imp_GetCurrentProcess
0x180037536  mov     [rsp+0C0h+dwOptions], 2; dwOptions
0x18003753e  mov     [rsp+0C0h+bInheritHandle], r12d; bInheritHandle
0x180037543  mov     [rsp+0C0h+dwDesiredAccess], r12d; dwDesiredAccess
0x180037548  mov     r9, r15; lpTargetHandle
0x18003754b  mov     r8, rbx; hTargetProcessHandle
0x18003754e  mov     rdx, rdi; hSourceHandle
0x180037551  mov     rcx, rax; hSourceProcessHandle
0x180037554  call    cs:__imp_DuplicateHandle
0x18003755a  test    eax, eax
0x18003755c  jnz     short loc_180037575
0x18003755e  call    cs:__imp_GetLastError
0x180037564  mov     esi, eax
0x180037566  test    eax, eax
0x180037568  jle     short loc_18003757F
0x18003756a  movzx   esi, ax
0x18003756d  or      esi, 80070000h
0x180037573  jmp     short loc_18003757F
0x180037575  mov     esi, r12d
0x180037578  jmp     short loc_18003757F
0x18003757a  mov     esi, 8007000Eh
0x18003757f  mov     rdi, [rbp+37h+var_80]
0x180037583  mov     eax, cs:dword_1800AF3E8
0x180037589  cmp     eax, 5
0x18003758c  jbe     short loc_1800375B4
0x18003758e  mov     dword ptr [rbp+37h+var_78], esi
0x180037591  mov     [rbp+37h+var_58], rdi
0x180037595  lea     rax, [rbp+37h+var_78]
0x180037599  mov     qword ptr [rsp+0C0h+bInheritHandle], rax
0x18003759e  lea     rax, [rbp+37h+var_58]
0x1800375a2  mov     qword ptr [rsp+0C0h+dwDesiredAccess], rax
0x1800375a7  lea     rdx, byte_18009E32D
0x1800375ae  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x1800375b3  nop
0x1800375b4  lea     rcx, [rbp+37h+var_68]
0x1800375b8  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x1800375bd  nop
0x1800375be  lea     rcx, [rbp+37h+var_60]
0x1800375c2  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x1800375c7  mov     eax, esi
0x1800375c9  mov     rbx, [rsp+0C0h+arg_18]
0x1800375d1  add     rsp, 90h
0x1800375d8  pop     r15
0x1800375da  pop     r14
0x1800375dc  pop     r13
0x1800375de  pop     r12
0x1800375e0  pop     rdi
0x1800375e1  pop     rsi
0x1800375e2  pop     rbp
0x1800375e3  retn
```
