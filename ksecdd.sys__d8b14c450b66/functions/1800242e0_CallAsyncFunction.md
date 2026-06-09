# CallAsyncFunction

- ea: `0x1800242e0`
- end: `0x1800247bf`
- name: `CallAsyncFunction`
- size: `1247`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800240e0`
- `0x180027738`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x180001f90`
- `0x180002820`
- `0x180007ba8`
- `0x18000f898`
- `0x180010840`
- `0x180010920`
- `0x1800242e0`
- `0x180026530`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x180024547`
- `ntoskrnl!PsGetCurrentThreadId` at `0x180024547`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x18002439a`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x18002439a`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x1800243c5`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x1800243c5`
- `ntoskrnl!ZwQueryInformationToken` at `0x1800243ff`
- `ntoskrnl!ZwQueryInformationToken` at `0x1800243ff`
- `ntoskrnl!ZwDuplicateToken` at `0x18002447d`
- `ntoskrnl!ZwDuplicateToken` at `0x18002447d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1800245c8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1800245c8`
- `ntoskrnl!ZwClose` at `0x18002448f`
- `ntoskrnl!ZwClose` at `0x1800246fd`
- `ntoskrnl!ZwClose` at `0x18002448f`
- `ntoskrnl!ZwClose` at `0x1800246fd`
- `ntoskrnl!ZwDuplicateObject` at `0x1800244cc`
- `ntoskrnl!ZwDuplicateObject` at `0x18002479d`
- `ntoskrnl!ZwDuplicateObject` at `0x1800244cc`
- `ntoskrnl!ZwDuplicateObject` at `0x18002479d`
- `HAL!KeQueryPerformanceCounter` at `0x18002433b`
- `HAL!KeQueryPerformanceCounter` at `0x180024509`
- `HAL!KeQueryPerformanceCounter` at `0x18002464b`
- `HAL!KeQueryPerformanceCounter` at `0x18002433b`
- `HAL!KeQueryPerformanceCounter` at `0x180024509`
- `HAL!KeQueryPerformanceCounter` at `0x18002464b`

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
  __int64 (__fastcall *(__fastcall *v12)(__int64, int, __int64, unsigned int, __int64))(__int64, _QWORD); // rdi
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 15, WPP_f9740104427135617d8c60794f45a901_Traceguids);
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
0x1800242e0  mov     [rsp-8+arg_18], rbx
0x1800242e5  push    rbp
0x1800242e6  push    rsi
0x1800242e7  push    r12
0x1800242e9  push    r14
0x1800242eb  push    r15
0x1800242ed  lea     rbp, [rsp-37h]
0x1800242f2  sub     rsp, 0C0h
0x1800242f9  mov     rax, cs:__security_cookie
0x180024300  xor     rax, rsp
0x180024303  mov     [rbp+57h+var_28], rax
0x180024307  xor     r12d, r12d
0x18002430a  mov     r14d, edx
0x18002430d  mov     [rbp+57h+var_98], r12
0x180024311  mov     rsi, rcx
0x180024314  mov     [rbp+57h+var_8C], r12d
0x180024318  mov     [rbp+57h+TargetHandle], r12
0x18002431c  test    rcx, rcx
0x18002431f  jz      loc_18002461D
0x180024325  cmp     [rcx], r12
0x180024328  jz      loc_18002461D
0x18002432e  mov     r15b, 1
0x180024331  xor     ecx, ecx; PerformanceFrequency
0x180024333  mov     [rsp+0E0h+arg_8], rdi
0x18002433b  call    cs:__imp_KeQueryPerformanceCounter
0x180024342  nop     dword ptr [rax+rax+00h]
0x180024347  lea     rcx, [rbp+57h+var_88]; this
0x18002434b  mov     rbx, rax
0x18002434e  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180024353  lea     rcx, [rbp+57h+var_88]; this
0x180024357  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x18002435c  lea     rcx, [rbp+57h+var_88]; this
0x180024360  test    al, al
0x180024362  jz      loc_1800246CA
0x180024368  mov     [rsp+0E0h+arg_10], r13
0x180024370  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x180024375  mov     r13, rax
0x180024378  mov     [rbp+57h+ExistingTokenHandle], r12
0x18002437c  lea     rax, [rbp+57h+ExistingTokenHandle]
0x180024380  mov     r9d, 200h; HandleAttributes
0x180024386  mov     r8b, 1; OpenAsSelf
0x180024389  mov     [rsp+0E0h+TokenHandle], rax; TokenHandle
0x18002438e  mov     edx, 0Ch; DesiredAccess
0x180024393  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18002439a  call    cs:__imp_ZwOpenThreadTokenEx
0x1800243a1  nop     dword ptr [rax+rax+00h]
0x1800243a6  mov     edi, eax
0x1800243a8  cmp     eax, 0C000007Ch
0x1800243ad  jnz     short loc_1800243D3
0x1800243af  lea     r9, [rbp+57h+ExistingTokenHandle]; TokenHandle
0x1800243b3  mov     edx, 0Ch; DesiredAccess
0x1800243b8  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800243bf  mov     r8d, 200h; HandleAttributes
0x1800243c5  call    cs:__imp_ZwOpenProcessTokenEx
0x1800243cc  nop     dword ptr [rax+rax+00h]
0x1800243d1  mov     edi, eax
0x1800243d3  test    edi, edi
0x1800243d5  js      loc_18002476B
0x1800243db  mov     rcx, [rbp+57h+ExistingTokenHandle]; TokenHandle
0x1800243df  lea     rax, [rbp+57h+ReturnLength]
0x1800243e3  mov     r9d, 4; TokenInformationLength
0x1800243e9  mov     [rsp+0E0h+TokenHandle], rax; ReturnLength
0x1800243ee  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800243f2  mov     [rbp+57h+TokenInformation], r12d
0x1800243f6  mov     edx, 8; TokenInformationClass
0x1800243fb  mov     [rbp+57h+ReturnLength], r12d
0x1800243ff  call    cs:__imp_ZwQueryInformationToken
0x180024406  nop     dword ptr [rax+rax+00h]
0x18002440b  mov     edi, eax
0x18002440d  test    eax, eax
0x18002440f  js      loc_1800246F9
0x180024415  cmp     [rbp+57h+TokenInformation], 2
0x180024419  jz      loc_18002470B
0x18002441f  mov     rcx, [rbp+57h+ExistingTokenHandle]; ExistingTokenHandle
0x180024423  lea     rax, [rbp+57h+var_38]
0x180024427  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x18002442b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002442f  lea     rax, [rbp+57h+SourceHandle]
0x180024433  mov     [rbp+57h+var_30], 1
0x18002443a  mov     [rsp+0E0h+NewTokenHandle], rax; NewTokenHandle
0x18002443f  xor     r9d, r9d; EffectiveOnly
0x180024442  mov     edx, 0Ch; DesiredAccess
0x180024447  mov     dword ptr [rsp+0E0h+TokenHandle], 2; TokenType
0x18002444f  mov     [rbp+57h+var_38], 0Ch
0x180024456  mov     [rbp+57h+var_34], 2
0x18002445d  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180024465  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x18002446d  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x180024471  mov     [rbp+57h+ObjectAttributes.ObjectName], r12
0x180024475  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r12
0x180024479  mov     [rbp+57h+SourceHandle], r12
0x18002447d  call    cs:__imp_ZwDuplicateToken
0x180024484  nop     dword ptr [rax+rax+00h]
0x180024489  mov     rcx, [rbp+57h+ExistingTokenHandle]; Handle
0x18002448d  mov     edi, eax
0x18002448f  call    cs:__imp_ZwClose
0x180024496  nop     dword ptr [rax+rax+00h]
0x18002449b  test    edi, edi
0x18002449d  js      loc_18002476B
0x1800244a3  mov     rdx, [rbp+57h+SourceHandle]; SourceHandle
0x1800244a7  mov     [rbp+57h+ExistingTokenHandle], rdx
0x1800244ab  mov     r8, [r13+8]; TargetProcessHandle
0x1800244af  lea     r9, [rbp+57h+TargetHandle]; TargetHandle
0x1800244b3  mov     [rsp+0E0h+Options], 3; Options
0x1800244bb  mov     rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x1800244c2  mov     dword ptr [rsp+0E0h+NewTokenHandle], r12d; HandleAttributes
0x1800244c7  mov     dword ptr [rsp+0E0h+TokenHandle], r12d; DesiredAccess
0x1800244cc  call    cs:__imp_ZwDuplicateObject
0x1800244d3  nop     dword ptr [rax+rax+00h]
0x1800244d8  mov     edi, eax
0x1800244da  test    eax, eax
0x1800244dc  js      loc_18002476B
0x1800244e2  mov     rax, [rsi+0E0h]
0x1800244e9  lea     r8, [rbp+57h+var_8C]
0x1800244ed  lea     rdx, [rbp+57h+var_98]
0x1800244f1  mov     rcx, rsi
0x1800244f4  call    _guard_dispatch_icall
0x1800244f9  mov     edi, eax
0x1800244fb  test    eax, eax
0x1800244fd  js      loc_18002476B
0x180024503  xor     ecx, ecx; PerformanceFrequency
0x180024505  mov     [rsi+10h], r14d
0x180024509  call    cs:__imp_KeQueryPerformanceCounter
0x180024510  nop     dword ptr [rax+rax+00h]
0x180024515  mov     ecx, [rsi+10h]
0x180024518  mov     [rsi+18h], rax
0x18002451c  mov     rax, [rbp+57h+var_98]
0x180024520  mov     [rax+8], ecx
0x180024523  mov     rax, [rbp+57h+var_98]
0x180024527  mov     ecx, [rbp+57h+var_8C]
0x18002452a  mov     [rax+28h], ecx
0x18002452d  mov     rcx, [rbp+57h+var_98]
0x180024531  mov     rax, [rbp+57h+TargetHandle]
0x180024535  mov     [rcx+20h], rax
0x180024539  mov     rax, [rbp+57h+var_98]
0x18002453d  mov     ecx, cs:KsecSystemProcessId
0x180024543  mov     [rax+10h], rcx
0x180024547  call    cs:__imp_PsGetCurrentThreadId
0x18002454e  nop     dword ptr [rax+rax+00h]
0x180024553  mov     ecx, eax
0x180024555  test    r15b, r15b
0x180024558  mov     rax, [rbp+57h+var_98]
0x18002455c  lea     rdi, AsyncSspiHandleIoctlIpcResponse
0x180024563  cmovz   rdi, r12
0x180024567  mov     [rax+18h], rcx
0x18002456b  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x18002456f  mov     r12, [rbp+57h+var_98]
0x180024573  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180024578  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x18002457c  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x180024581  test    al, al
0x180024583  jnz     loc_180024714
0x180024589  mov     edi, 0C00002FEh
0x18002458e  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x180024592  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180024597  test    edi, edi
0x180024599  js      loc_180024768
0x18002459f  test    r15b, r15b
0x1800245a2  jnz     loc_180024679
0x1800245a8  mov     r13, [rsi+18h]
0x1800245ac  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x1800245b0  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x1800245b5  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x1800245b9  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x1800245be  test    al, al
0x1800245c0  jz      loc_18002466D
0x1800245c6  xor     ecx, ecx; ProcNumber
0x1800245c8  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1800245cf  nop     dword ptr [rax+rax+00h]
0x1800245d4  mov     eax, eax
0x1800245d6  lea     rcx, [rbp+57h+ExistingTokenHandle]
0x1800245da  imul    rdx, rax, 88h
0x1800245e1  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x1800245e6  mov     rcx, [rax+138h]
0x1800245ed  cmp     r14d, 2
0x1800245f1  jz      short loc_180024625
0x1800245f3  test    r14d, r14d
0x1800245f6  jz      loc_1800246B9
0x1800245fc  sub     r14d, 1
0x180024600  jz      loc_1800247AE
0x180024606  cmp     r14d, 2
0x18002460a  jnz     short loc_18002466D
0x18002460c  lea     r14, [rdx+70h]
0x180024610  lea     r15, [rdx+78h]
0x180024614  lea     r12, [rdx+80h]
0x18002461b  jmp     short loc_180024631
0x18002461d  xor     r15b, r15b
0x180024620  jmp     loc_180024331
0x180024625  lea     r14, [rdx+28h]
0x180024629  lea     r15, [rdx+30h]
0x18002462d  lea     r12, [rdx+38h]
0x180024631  add     r14, rcx
0x180024634  add     r15, rcx
0x180024637  add     r12, rcx
0x18002463a  test    r14, r14
0x18002463d  jz      short loc_18002466D
0x18002463f  test    r15, r15
0x180024642  jz      short loc_18002466D
0x180024644  test    r12, r12
0x180024647  jz      short loc_18002466D
0x180024649  xor     ecx, ecx; PerformanceFrequency
0x18002464b  call    cs:__imp_KeQueryPerformanceCounter
0x180024652  nop     dword ptr [rax+rax+00h]
0x180024657  lock inc qword ptr [r14]
0x18002465b  mov     rcx, rax
0x18002465e  sub     rcx, rbx
0x180024661  lock add [r15], rcx
0x180024665  sub     rax, r13
0x180024668  lock add [r12], rax
0x18002466d  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x180024671  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180024676  mov     [rsi+14h], edi
0x180024679  lea     rcx, [rbp+57h+var_88]; this
0x18002467d  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180024682  mov     r13, [rsp+0E0h+arg_10]
0x18002468a  mov     eax, edi
0x18002468c  mov     rdi, [rsp+0E0h+arg_8]
0x180024694  mov     rcx, [rbp+57h+var_28]
0x180024698  xor     rcx, rsp; StackCookie
0x18002469b  call    __security_check_cookie
0x1800246a0  mov     rbx, [rsp+0E0h+arg_18]
0x1800246a8  add     rsp, 0C0h
0x1800246af  pop     r15
0x1800246b1  pop     r14
0x1800246b3  pop     r12
0x1800246b5  pop     rsi
0x1800246b6  pop     rbp
0x1800246b7  retn
0x1800246b9  lea     r14, [rdx+58h]
0x1800246bd  lea     r15, [rdx+60h]
0x1800246c1  lea     r12, [rdx+68h]
0x1800246c5  jmp     loc_180024631
0x1800246ca  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x1800246cf  mov     eax, 0C00002FEh
0x1800246d4  jmp     short loc_18002468C
0x1800246d6  lea     rcx, [rbp+57h+ExistingTokenHandle]
0x1800246da  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x1800246df  add     rax, 58h ; 'X'
0x1800246e3  cmp     [rax], rax
0x1800246e6  jz      loc_18002458E
0x1800246ec  mov     rcx, r13; InsertContext
0x1800246ef  call    HandlePendingIrps
0x1800246f4  jmp     loc_18002458E
0x1800246f9  mov     rcx, [rbp+57h+ExistingTokenHandle]; Handle
0x1800246fd  call    cs:__imp_ZwClose
0x180024704  nop     dword ptr [rax+rax+00h]
0x180024709  jmp     short loc_18002476B
0x18002470b  mov     rdx, [rbp+57h+ExistingTokenHandle]
0x18002470f  jmp     loc_1800244AB
0x180024714  mov     rcx, cs:WPP_GLOBAL_Control
0x18002471b  lea     rax, WPP_GLOBAL_Control
0x180024722  cmp     rcx, rax
0x180024725  jz      short loc_18002473C
0x180024727  mov     rcx, [rcx+18h]
0x18002472b  lea     r8, WPP_f9740104427135617d8c60794f45a901_Traceguids
0x180024732  mov     edx, 0Fh
0x180024737  call    WPP_SF_
0x18002473c  lea     rcx, [rbp+57h+ExistingTokenHandle]
0x180024740  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x180024745  mov     r9, rax
0x180024748  mov     r8, rsi
0x18002474b  mov     rdx, rdi
0x18002474e  mov     rcx, r12
0x180024751  mov     r13, rax
0x180024754  call    PendingCallPush
0x180024759  mov     edi, eax
0x18002475b  test    eax, eax
0x18002475d  js      loc_18002458E
0x180024763  jmp     loc_1800246D6
0x180024768  xor     r12d, r12d
0x18002476b  mov     rdx, [rbp+57h+TargetHandle]
0x18002476f  test    rdx, rdx
0x180024772  jz      loc_18002459F
0x180024778  lea     rcx, [rbp+57h+var_88]
0x18002477c  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x180024781  mov     [rsp+0E0h+Options], 1; Options
0x180024789  xor     r9d, r9d; TargetHandle
0x18002478c  mov     dword ptr [rsp+0E0h+NewTokenHandle], r12d; HandleAttributes
0x180024791  xor     r8d, r8d; TargetProcessHandle
0x180024794  mov     dword ptr [rsp+0E0h+TokenHandle], r12d; DesiredAccess
0x180024799  mov     rcx, [rax+8]; SourceProcessHandle
0x18002479d  call    cs:__imp_ZwDuplicateObject
0x1800247a4  nop     dword ptr [rax+rax+00h]
0x1800247a9  jmp     loc_18002459F
0x1800247ae  lea     r14, [rdx+40h]
0x1800247b2  lea     r15, [rdx+48h]
0x1800247b6  lea     r12, [rdx+50h]
0x1800247ba  jmp     loc_180024631
```
