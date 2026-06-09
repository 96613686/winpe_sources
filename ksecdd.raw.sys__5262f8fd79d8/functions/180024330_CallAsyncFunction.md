# CallAsyncFunction

- ea: `0x180024330`
- end: `0x18002480f`
- name: `CallAsyncFunction`
- size: `1247`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180024130`
- `0x180027788`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x180001f90`
- `0x180002820`
- `0x180007ba8`
- `0x18000f900`
- `0x1800108a0`
- `0x180010980`
- `0x180024330`
- `0x180026580`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x180024597`
- `ntoskrnl!PsGetCurrentThreadId` at `0x180024597`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x1800243ea`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x1800243ea`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x180024415`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x180024415`
- `ntoskrnl!ZwQueryInformationToken` at `0x18002444f`
- `ntoskrnl!ZwQueryInformationToken` at `0x18002444f`
- `ntoskrnl!ZwDuplicateToken` at `0x1800244cd`
- `ntoskrnl!ZwDuplicateToken` at `0x1800244cd`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x180024618`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x180024618`
- `ntoskrnl!ZwClose` at `0x1800244df`
- `ntoskrnl!ZwClose` at `0x18002474d`
- `ntoskrnl!ZwClose` at `0x1800244df`
- `ntoskrnl!ZwClose` at `0x18002474d`
- `ntoskrnl!ZwDuplicateObject` at `0x18002451c`
- `ntoskrnl!ZwDuplicateObject` at `0x1800247ed`
- `ntoskrnl!ZwDuplicateObject` at `0x18002451c`
- `ntoskrnl!ZwDuplicateObject` at `0x1800247ed`
- `HAL!KeQueryPerformanceCounter` at `0x18002438b`
- `HAL!KeQueryPerformanceCounter` at `0x180024559`
- `HAL!KeQueryPerformanceCounter` at `0x18002469b`
- `HAL!KeQueryPerformanceCounter` at `0x18002438b`
- `HAL!KeQueryPerformanceCounter` at `0x180024559`
- `HAL!KeQueryPerformanceCounter` at `0x18002469b`

## pseudocode

```c
__int64 __fastcall CallAsyncFunction(__int64 a1, int a2)
{
  bool v4; // r15
  LARGE_INTEGER PerformanceCounter; // rbx
  __int64 v6; // r13
  NTSTATUS v7; // edi
  HANDLE v8; // rdx
  LARGE_INTEGER v9; // rax
  int v10; // ecx
  __int64 CurrentThreadId; // rcx
  __int64 (__fastcall *v12)(int, int, int, int, __int64); // rdi
  __int64 v13; // r12
  __int64 v14; // r13
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // r14d
  __int64 v18; // r14
  __int64 v19; // r15
  __int64 v20; // r12
  volatile signed __int64 *v21; // r14
  volatile signed __int64 *v22; // r15
  volatile signed __int64 *v23; // r12
  LARGE_INTEGER v24; // rax
  __int64 v26; // rax
  void *v27; // r13
  __int64 v28; // rax
  HANDLE v29; // rdx
  HANDLE ExistingTokenHandle; // [rsp+40h] [rbp-49h] BYREF
  __int64 v31; // [rsp+48h] [rbp-41h] BYREF
  int TokenInformation; // [rsp+50h] [rbp-39h] BYREF
  int v33; // [rsp+54h] [rbp-35h] BYREF
  _BYTE v34[8]; // [rsp+58h] [rbp-31h] BYREF
  ULONG ReturnLength; // [rsp+60h] [rbp-29h] BYREF
  HANDLE TargetHandle; // [rsp+68h] [rbp-21h] BYREF
  HANDLE SourceHandle; // [rsp+70h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-11h] BYREF
  _DWORD v39[4]; // [rsp+A8h] [rbp+1Fh] BYREF

  v31 = 0;
  v33 = 0;
  TargetHandle = 0;
  v4 = a1 && *(_QWORD *)a1;
  PerformanceCounter = KeQueryPerformanceCounter(0);
  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)v34);
  if ( !KsecddLsaStateRef::IsValid((KsecddLsaStateRef *)v34) )
  {
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)v34);
    return 3221226238LL;
  }
  v6 = KsecddLsaStateRef::operator _KSECDDLSASTATE *(v34);
  ExistingTokenHandle = 0;
  v7 = ZwOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, 0x200u, &ExistingTokenHandle);
  if ( v7 == -1073741700 )
    v7 = ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0xCu, 0x200u, &ExistingTokenHandle);
  if ( v7 < 0 )
    goto LABEL_45;
  TokenInformation = 0;
  ReturnLength = 0;
  v7 = ZwQueryInformationToken(ExistingTokenHandle, TokenType, &TokenInformation, 4u, &ReturnLength);
  if ( v7 < 0 )
  {
    ZwClose(ExistingTokenHandle);
    goto LABEL_45;
  }
  if ( TokenInformation != 2 )
  {
    ObjectAttributes.SecurityQualityOfService = v39;
    v39[2] = 1;
    v39[0] = 12;
    v39[1] = 2;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    *(_QWORD *)&ObjectAttributes.Attributes = 512;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = 0;
    ObjectAttributes.SecurityDescriptor = 0;
    SourceHandle = 0;
    v7 = ZwDuplicateToken(ExistingTokenHandle, 0xCu, &ObjectAttributes, 0, TokenImpersonation, &SourceHandle);
    ZwClose(ExistingTokenHandle);
    if ( v7 >= 0 )
    {
      v8 = SourceHandle;
      ExistingTokenHandle = SourceHandle;
      goto LABEL_12;
    }
LABEL_45:
    if ( TargetHandle )
    {
      v28 = KsecddLsaStateRef::operator _KSECDDLSASTATE *(v34);
      ZwDuplicateObject(*(HANDLE *)(v28 + 8), v29, 0, 0, 0, 0, 1u);
    }
    goto LABEL_19;
  }
  v8 = ExistingTokenHandle;
LABEL_12:
  v7 = ZwDuplicateObject((HANDLE)0xFFFFFFFFFFFFFFFFLL, v8, *(HANDLE *)(v6 + 8), &TargetHandle, 0, 0, 3u);
  if ( v7 < 0 )
    goto LABEL_45;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *, int *))(a1 + 224))(a1, &v31, &v33);
  if ( v7 < 0 )
    goto LABEL_45;
  *(_DWORD *)(a1 + 16) = a2;
  v9 = KeQueryPerformanceCounter(0);
  v10 = *(_DWORD *)(a1 + 16);
  *(LARGE_INTEGER *)(a1 + 24) = v9;
  *(_DWORD *)(v31 + 8) = v10;
  *(_DWORD *)(v31 + 40) = v33;
  *(_QWORD *)(v31 + 32) = TargetHandle;
  *(_QWORD *)(v31 + 16) = (unsigned int)KsecSystemProcessId;
  CurrentThreadId = (unsigned int)PsGetCurrentThreadId();
  v12 = AsyncSspiHandleIoctlIpcResponse;
  if ( !v4 )
    v12 = 0;
  *(_QWORD *)(v31 + 24) = CurrentThreadId;
  v13 = v31;
  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&ExistingTokenHandle);
  if ( KsecddLsaStateRef::IsValid((KsecddLsaStateRef *)&ExistingTokenHandle) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 15, &WPP_f9740104427135617d8c60794f45a901_Traceguids);
    v27 = (void *)KsecddLsaStateRef::operator _KSECDDLSASTATE *(&ExistingTokenHandle);
    v7 = PendingCallPush(v13, v12, a1, v27);
    if ( v7 >= 0 )
    {
      v26 = KsecddLsaStateRef::operator _KSECDDLSASTATE *(&ExistingTokenHandle);
      if ( *(_QWORD *)(v26 + 88) != v26 + 88 )
        HandlePendingIrps(v27);
    }
  }
  else
  {
    v7 = -1073741058;
  }
  KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&ExistingTokenHandle);
  if ( v7 < 0 )
    goto LABEL_45;
LABEL_19:
  if ( !v4 )
  {
    v14 = *(_QWORD *)(a1 + 24);
    KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&ExistingTokenHandle);
    if ( KsecddLsaStateRef::IsValid((KsecddLsaStateRef *)&ExistingTokenHandle) )
    {
      KeGetCurrentProcessorNumberEx(0);
      v16 = *(_QWORD *)(KsecddLsaStateRef::operator _KSECDDLSASTATE *(&ExistingTokenHandle) + 312);
      if ( a2 == 2 )
      {
        v18 = v15 + 40;
        v19 = v15 + 48;
        v20 = v15 + 56;
        goto LABEL_28;
      }
      if ( !a2 )
      {
        v18 = v15 + 88;
        v19 = v15 + 96;
        v20 = v15 + 104;
        goto LABEL_28;
      }
      v17 = a2 - 1;
      if ( !v17 )
      {
        v18 = v15 + 64;
        v19 = v15 + 72;
        v20 = v15 + 80;
        goto LABEL_28;
      }
      if ( v17 == 2 )
      {
        v18 = v15 + 112;
        v19 = v15 + 120;
        v20 = v15 + 128;
LABEL_28:
        v21 = (volatile signed __int64 *)(v16 + v18);
        v22 = (volatile signed __int64 *)(v16 + v19);
        v23 = (volatile signed __int64 *)(v16 + v20);
        if ( v21 && v22 )
        {
          if ( v23 )
          {
            v24 = KeQueryPerformanceCounter(0);
            _InterlockedIncrement64(v21);
            _InterlockedAdd64(v22, v24.QuadPart - PerformanceCounter.QuadPart);
            _InterlockedAdd64(v23, v24.QuadPart - v14);
          }
        }
      }
    }
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&ExistingTokenHandle);
    *(_DWORD *)(a1 + 20) = v7;
  }
  KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)v34);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180024330  mov     [rsp-8+arg_18], rbx
0x180024335  push    rbp
0x180024336  push    rsi
0x180024337  push    r12
0x180024339  push    r14
0x18002433b  push    r15
0x18002433d  lea     rbp, [rsp-37h]
0x180024342  sub     rsp, 0C0h
0x180024349  mov     rax, cs:__security_cookie
0x180024350  xor     rax, rsp
0x180024353  mov     [rbp+57h+var_28], rax
0x180024357  xor     r12d, r12d
0x18002435a  mov     r14d, edx
0x18002435d  mov     [rbp+57h+var_98], r12
0x180024361  mov     rsi, rcx
0x180024364  mov     [rbp+57h+var_8C], r12d
0x180024368  mov     [rbp+57h+TargetHandle], r12
0x18002436c  test    rcx, rcx
0x18002436f  jz      loc_18002466D
0x180024375  cmp     [rcx], r12
0x180024378  jz      loc_18002466D
0x18002437e  mov     r15b, 1
0x180024381  xor     ecx, ecx; PerformanceFrequency
0x180024383  mov     [rsp+0E0h+arg_8], rdi
0x18002438b  call    cs:__imp_KeQueryPerformanceCounter
0x180024392  nop     dword ptr [rax+rax+00h]
0x180024397  lea     rcx, [rbp+57h+var_88]; this
0x18002439b  mov     rbx, rax
0x18002439e  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x1800243a3  lea     rcx, [rbp+57h+var_88]; this
0x1800243a7  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x1800243ac  lea     rcx, [rbp+57h+var_88]; this
0x1800243b0  test    al, al
0x1800243b2  jz      loc_18002471A
0x1800243b8  mov     [rsp+0E0h+arg_10], r13
0x1800243c0  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x1800243c5  mov     r13, rax
0x1800243c8  mov     [rbp+57h+ExistingTokenHandle], r12
0x1800243cc  lea     rax, [rbp+57h+ExistingTokenHandle]
0x1800243d0  mov     r9d, 200h; HandleAttributes
0x1800243d6  mov     r8b, 1; OpenAsSelf
0x1800243d9  mov     [rsp+0E0h+TokenHandle], rax; TokenHandle
0x1800243de  mov     edx, 0Ch; DesiredAccess
0x1800243e3  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800243ea  call    cs:__imp_ZwOpenThreadTokenEx
0x1800243f1  nop     dword ptr [rax+rax+00h]
0x1800243f6  mov     edi, eax
0x1800243f8  cmp     eax, 0C000007Ch
0x1800243fd  jnz     short loc_180024423
0x1800243ff  lea     r9, [rbp+57h+ExistingTokenHandle]; TokenHandle
0x180024403  mov     edx, 0Ch; DesiredAccess
0x180024408  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18002440f  mov     r8d, 200h; HandleAttributes
0x180024415  call    cs:__imp_ZwOpenProcessTokenEx
0x18002441c  nop     dword ptr [rax+rax+00h]
0x180024421  mov     edi, eax
0x180024423  test    edi, edi
0x180024425  js      loc_1800247BB
0x18002442b  mov     rcx, [rbp+57h+ExistingTokenHandle]; TokenHandle
0x18002442f  lea     rax, [rbp+57h+ReturnLength]
0x180024433  mov     r9d, 4; TokenInformationLength
0x180024439  mov     [rsp+0E0h+TokenHandle], rax; ReturnLength
0x18002443e  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180024442  mov     [rbp+57h+TokenInformation], r12d
0x180024446  mov     edx, 8; TokenInformationClass
0x18002444b  mov     [rbp+57h+ReturnLength], r12d
0x18002444f  call    cs:__imp_ZwQueryInformationToken
0x180024456  nop     dword ptr [rax+rax+00h]
0x18002445b  mov     edi, eax
0x18002445d  test    eax, eax
0x18002445f  js      loc_180024749
0x180024465  cmp     [rbp+57h+TokenInformation], 2
0x180024469  jz      loc_18002475B
0x18002446f  mov     rcx, [rbp+57h+ExistingTokenHandle]; ExistingTokenHandle
0x180024473  lea     rax, [rbp+57h+var_38]
0x180024477  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x18002447b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002447f  lea     rax, [rbp+57h+SourceHandle]
0x180024483  mov     [rbp+57h+var_30], 1
0x18002448a  mov     [rsp+0E0h+NewTokenHandle], rax; NewTokenHandle
0x18002448f  xor     r9d, r9d; EffectiveOnly
0x180024492  mov     edx, 0Ch; DesiredAccess
0x180024497  mov     dword ptr [rsp+0E0h+TokenHandle], 2; TokenType
0x18002449f  mov     [rbp+57h+var_38], 0Ch
0x1800244a6  mov     [rbp+57h+var_34], 2
0x1800244ad  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800244b5  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x1800244bd  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x1800244c1  mov     [rbp+57h+ObjectAttributes.ObjectName], r12
0x1800244c5  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r12
0x1800244c9  mov     [rbp+57h+SourceHandle], r12
0x1800244cd  call    cs:__imp_ZwDuplicateToken
0x1800244d4  nop     dword ptr [rax+rax+00h]
0x1800244d9  mov     rcx, [rbp+57h+ExistingTokenHandle]; Handle
0x1800244dd  mov     edi, eax
0x1800244df  call    cs:__imp_ZwClose
0x1800244e6  nop     dword ptr [rax+rax+00h]
0x1800244eb  test    edi, edi
0x1800244ed  js      loc_1800247BB
0x1800244f3  mov     rdx, [rbp+57h+SourceHandle]; SourceHandle
0x1800244f7  mov     [rbp+57h+ExistingTokenHandle], rdx
0x1800244fb  mov     r8, [r13+8]; TargetProcessHandle
0x1800244ff  lea     r9, [rbp+57h+TargetHandle]; TargetHandle
0x180024503  mov     [rsp+0E0h+Options], 3; Options
0x18002450b  mov     rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x180024512  mov     dword ptr [rsp+0E0h+NewTokenHandle], r12d; HandleAttributes
0x180024517  mov     dword ptr [rsp+0E0h+TokenHandle], r12d; DesiredAccess
0x18002451c  call    cs:__imp_ZwDuplicateObject
0x180024523  nop     dword ptr [rax+rax+00h]
0x180024528  mov     edi, eax
0x18002452a  test    eax, eax
0x18002452c  js      loc_1800247BB
0x180024532  mov     rax, [rsi+0E0h]
0x180024539  lea     r8, [rbp+57h+var_8C]
0x18002453d  lea     rdx, [rbp+57h+var_98]
0x180024541  mov     rcx, rsi
0x180024544  call    _guard_dispatch_icall
0x180024549  mov     edi, eax
0x18002454b  test    eax, eax
0x18002454d  js      loc_1800247BB
0x180024553  xor     ecx, ecx; PerformanceFrequency
0x180024555  mov     [rsi+10h], r14d
0x180024559  call    cs:__imp_KeQueryPerformanceCounter
0x180024560  nop     dword ptr [rax+rax+00h]
0x180024565  mov     ecx, [rsi+10h]
0x180024568  mov     [rsi+18h], rax
0x18002456c  mov     rax, [rbp+57h+var_98]
0x180024570  mov     [rax+8], ecx
0x180024573  mov     rax, [rbp+57h+var_98]
0x180024577  mov     ecx, [rbp+57h+var_8C]
0x18002457a  mov     [rax+28h], ecx
0x18002457d  mov     rcx, [rbp+57h+var_98]
0x180024581  mov     rax, [rbp+57h+TargetHandle]
0x180024585  mov     [rcx+20h], rax
0x180024589  mov     rax, [rbp+57h+var_98]
0x18002458d  mov     ecx, cs:KsecSystemProcessId
0x180024593  mov     [rax+10h], rcx
0x180024597  call    cs:__imp_PsGetCurrentThreadId
0x18002459e  nop     dword ptr [rax+rax+00h]
0x1800245a3  mov     ecx, eax
0x1800245a5  test    r15b, r15b
0x1800245a8  mov     rax, [rbp+57h+var_98]
0x1800245ac  lea     rdi, AsyncSspiHandleIoctlIpcResponse
0x1800245b3  cmovz   rdi, r12
0x1800245b7  mov     [rax+18h], rcx
0x1800245bb  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x1800245bf  mov     r12, [rbp+57h+var_98]
0x1800245c3  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x1800245c8  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x1800245cc  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x1800245d1  test    al, al
0x1800245d3  jnz     loc_180024764
0x1800245d9  mov     edi, 0C00002FEh
0x1800245de  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x1800245e2  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x1800245e7  test    edi, edi
0x1800245e9  js      loc_1800247B8
0x1800245ef  test    r15b, r15b
0x1800245f2  jnz     loc_1800246C9
0x1800245f8  mov     r13, [rsi+18h]
0x1800245fc  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x180024600  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180024605  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x180024609  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x18002460e  test    al, al
0x180024610  jz      loc_1800246BD
0x180024616  xor     ecx, ecx; ProcNumber
0x180024618  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x18002461f  nop     dword ptr [rax+rax+00h]
0x180024624  mov     eax, eax
0x180024626  lea     rcx, [rbp+57h+ExistingTokenHandle]
0x18002462a  imul    rdx, rax, 88h
0x180024631  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x180024636  mov     rcx, [rax+138h]
0x18002463d  cmp     r14d, 2
0x180024641  jz      short loc_180024675
0x180024643  test    r14d, r14d
0x180024646  jz      loc_180024709
0x18002464c  sub     r14d, 1
0x180024650  jz      loc_1800247FE
0x180024656  cmp     r14d, 2
0x18002465a  jnz     short loc_1800246BD
0x18002465c  lea     r14, [rdx+70h]
0x180024660  lea     r15, [rdx+78h]
0x180024664  lea     r12, [rdx+80h]
0x18002466b  jmp     short loc_180024681
0x18002466d  xor     r15b, r15b
0x180024670  jmp     loc_180024381
0x180024675  lea     r14, [rdx+28h]
0x180024679  lea     r15, [rdx+30h]
0x18002467d  lea     r12, [rdx+38h]
0x180024681  add     r14, rcx
0x180024684  add     r15, rcx
0x180024687  add     r12, rcx
0x18002468a  test    r14, r14
0x18002468d  jz      short loc_1800246BD
0x18002468f  test    r15, r15
0x180024692  jz      short loc_1800246BD
0x180024694  test    r12, r12
0x180024697  jz      short loc_1800246BD
0x180024699  xor     ecx, ecx; PerformanceFrequency
0x18002469b  call    cs:__imp_KeQueryPerformanceCounter
0x1800246a2  nop     dword ptr [rax+rax+00h]
0x1800246a7  lock inc qword ptr [r14]
0x1800246ab  mov     rcx, rax
0x1800246ae  sub     rcx, rbx
0x1800246b1  lock add [r15], rcx
0x1800246b5  sub     rax, r13
0x1800246b8  lock add [r12], rax
0x1800246bd  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x1800246c1  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x1800246c6  mov     [rsi+14h], edi
0x1800246c9  lea     rcx, [rbp+57h+var_88]; this
0x1800246cd  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x1800246d2  mov     r13, [rsp+0E0h+arg_10]
0x1800246da  mov     eax, edi
0x1800246dc  mov     rdi, [rsp+0E0h+arg_8]
0x1800246e4  mov     rcx, [rbp+57h+var_28]
0x1800246e8  xor     rcx, rsp; StackCookie
0x1800246eb  call    __security_check_cookie
0x1800246f0  mov     rbx, [rsp+0E0h+arg_18]
0x1800246f8  add     rsp, 0C0h
0x1800246ff  pop     r15
0x180024701  pop     r14
0x180024703  pop     r12
0x180024705  pop     rsi
0x180024706  pop     rbp
0x180024707  retn
0x180024709  lea     r14, [rdx+58h]
0x18002470d  lea     r15, [rdx+60h]
0x180024711  lea     r12, [rdx+68h]
0x180024715  jmp     loc_180024681
0x18002471a  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18002471f  mov     eax, 0C00002FEh
0x180024724  jmp     short loc_1800246DC
0x180024726  lea     rcx, [rbp+57h+ExistingTokenHandle]
0x18002472a  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x18002472f  add     rax, 58h ; 'X'
0x180024733  cmp     [rax], rax
0x180024736  jz      loc_1800245DE
0x18002473c  mov     rcx, r13; InsertContext
0x18002473f  call    HandlePendingIrps
0x180024744  jmp     loc_1800245DE
0x180024749  mov     rcx, [rbp+57h+ExistingTokenHandle]; Handle
0x18002474d  call    cs:__imp_ZwClose
0x180024754  nop     dword ptr [rax+rax+00h]
0x180024759  jmp     short loc_1800247BB
0x18002475b  mov     rdx, [rbp+57h+ExistingTokenHandle]
0x18002475f  jmp     loc_1800244FB
0x180024764  mov     rcx, cs:WPP_GLOBAL_Control
0x18002476b  lea     rax, WPP_GLOBAL_Control
0x180024772  cmp     rcx, rax
0x180024775  jz      short loc_18002478C
0x180024777  mov     rcx, [rcx+18h]
0x18002477b  lea     r8, WPP_f9740104427135617d8c60794f45a901_Traceguids
0x180024782  mov     edx, 0Fh
0x180024787  call    WPP_SF_
0x18002478c  lea     rcx, [rbp+57h+ExistingTokenHandle]
0x180024790  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x180024795  mov     r9, rax
0x180024798  mov     r8, rsi
0x18002479b  mov     rdx, rdi
0x18002479e  mov     rcx, r12
0x1800247a1  mov     r13, rax
0x1800247a4  call    PendingCallPush
0x1800247a9  mov     edi, eax
0x1800247ab  test    eax, eax
0x1800247ad  js      loc_1800245DE
0x1800247b3  jmp     loc_180024726
0x1800247b8  xor     r12d, r12d
0x1800247bb  mov     rdx, [rbp+57h+TargetHandle]
0x1800247bf  test    rdx, rdx
0x1800247c2  jz      loc_1800245EF
0x1800247c8  lea     rcx, [rbp+57h+var_88]
0x1800247cc  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x1800247d1  mov     [rsp+0E0h+Options], 1; Options
0x1800247d9  xor     r9d, r9d; TargetHandle
0x1800247dc  mov     dword ptr [rsp+0E0h+NewTokenHandle], r12d; HandleAttributes
0x1800247e1  xor     r8d, r8d; TargetProcessHandle
0x1800247e4  mov     dword ptr [rsp+0E0h+TokenHandle], r12d; DesiredAccess
0x1800247e9  mov     rcx, [rax+8]; SourceProcessHandle
0x1800247ed  call    cs:__imp_ZwDuplicateObject
0x1800247f4  nop     dword ptr [rax+rax+00h]
0x1800247f9  jmp     loc_1800245EF
0x1800247fe  lea     r14, [rdx+40h]
0x180024802  lea     r15, [rdx+48h]
0x180024806  lea     r12, [rdx+50h]
0x18002480a  jmp     loc_180024681
```
