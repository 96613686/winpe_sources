# KsecProcessSecurityContext

- ea: `0x1800248c0`
- end: `0x180025080`
- name: `KsecProcessSecurityContext`
- size: `1984`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180022d40`
- `0x1800247d0`
- `0x180024850`

## callees

- `0x1800017c4`
- `0x180001c00`
- `0x180001cf0`
- `0x180001f90`
- `0x180002820`
- `0x180002a84`
- `0x180007ba8`
- `0x18000f898`
- `0x180010840`
- `0x180010920`
- `0x1800248c0`
- `0x180025090`
- `0x180025db0`
- `0x180026530`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x180024c7b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x180024c7b`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x180024acb`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x180024acb`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x180024af6`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x180024af6`
- `ntoskrnl!ZwQueryInformationToken` at `0x180024b33`
- `ntoskrnl!ZwQueryInformationToken` at `0x180024b33`
- `ntoskrnl!ZwDuplicateToken` at `0x180024bb1`
- `ntoskrnl!ZwDuplicateToken` at `0x180024bb1`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x180024cfc`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x180024cfc`
- `ntoskrnl!ZwClose` at `0x180024bc3`
- `ntoskrnl!ZwClose` at `0x180024faa`
- `ntoskrnl!ZwClose` at `0x180024bc3`
- `ntoskrnl!ZwClose` at `0x180024faa`
- `ntoskrnl!ZwDuplicateObject` at `0x180024c00`
- `ntoskrnl!ZwDuplicateObject` at `0x18002504a`
- `ntoskrnl!ZwDuplicateObject` at `0x180024c00`
- `ntoskrnl!ZwDuplicateObject` at `0x18002504a`
- `HAL!KeQueryPerformanceCounter` at `0x180024a74`
- `HAL!KeQueryPerformanceCounter` at `0x180024c3d`
- `HAL!KeQueryPerformanceCounter` at `0x180024d87`
- `HAL!KeQueryPerformanceCounter` at `0x180024a74`
- `HAL!KeQueryPerformanceCounter` at `0x180024c3d`
- `HAL!KeQueryPerformanceCounter` at `0x180024d87`

## pseudocode

```c
__int64 __fastcall KsecProcessSecurityContext(
        __int64 a1,
        __int128 *a2,
        __int64 *a3,
        __int64 a4,
        struct _SecBufferDesc *a5,
        int a6,
        int a7,
        __int128 *a8,
        __int64 a9,
        _DWORD *a10,
        __int64 a11)
{
  unsigned int v11; // edi
  __int64 v13; // r8
  _DWORD *v15; // rdx
  struct _SecBufferDesc *v17; // rcx
  __int64 v19; // r9
  __int64 v20; // r10
  __int128 v21; // xmm6
  __int64 v22; // rax
  int v23; // edi
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  int v26; // r14d
  bool v27; // zf
  char v28; // r15
  LARGE_INTEGER PerformanceCounter; // rbx
  __int64 v30; // r13
  HANDLE v31; // rdx
  LARGE_INTEGER v32; // rax
  int v33; // ecx
  __int64 CurrentThreadId; // rcx
  __int64 (__fastcall *(__fastcall *v35)(__int64, int, __int64, unsigned int, __int64))(__int64, _QWORD); // rdi
  __int64 v36; // r12
  __int64 v37; // r13
  __int64 v38; // rdx
  __int64 v39; // rcx
  int v40; // r14d
  __int64 v41; // r14
  __int64 v42; // r15
  __int64 v43; // r12
  volatile signed __int64 *v44; // r14
  volatile signed __int64 *v45; // r15
  volatile signed __int64 *v46; // r12
  LARGE_INTEGER v47; // rax
  __int64 pvBuffer; // r9
  __int64 v50; // r10
  unsigned int cBuffers; // r11d
  __int64 v52; // rdx
  char v53; // r14
  int inited; // esi
  __int64 v55; // rcx
  PSecBuffer pBuffers; // rdx
  __int64 v57; // rsi
  unsigned int BufferType; // eax
  __int64 v59; // rax
  void *v60; // r13
  __int64 v61; // rax
  HANDLE v62; // rdx
  bool v63; // [rsp+80h] [rbp-80h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+88h] [rbp-78h] BYREF
  __int64 v65; // [rsp+90h] [rbp-70h] BYREF
  int v66; // [rsp+98h] [rbp-68h] BYREF
  __int64 v67; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE TargetHandle; // [rsp+A8h] [rbp-58h] BYREF
  int TokenInformation; // [rsp+B0h] [rbp-50h] BYREF
  ULONG ReturnLength[2]; // [rsp+B8h] [rbp-48h] BYREF
  HANDLE SourceHandle[2]; // [rsp+C0h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v73; // [rsp+100h] [rbp+0h] BYREF
  __int128 v74; // [rsp+110h] [rbp+10h] BYREF
  __int128 v75; // [rsp+120h] [rbp+20h] BYREF

  v11 = 0;
  v13 = a11;
  v15 = a10;
  v17 = a5;
  ExistingTokenHandle = a5;
  TargetHandle = a10;
  *(_QWORD *)ReturnLength = a11;
  v74 = 0u;
  v75 = 0u;
  if ( !a3 && !a2 || !a8 )
    return (unsigned int)-2146893055;
  v19 = 0;
  v67 = 0;
  v20 = 0;
  v65 = 0;
  if ( a2 )
    v75 = *a2;
  v21 = *a8;
  if ( a3 )
  {
    v22 = *a3;
    v65 = a3[1];
    v67 = v22;
    v23 = MapKernelContextHandle(a3, &v74);
    if ( v23 < 0 )
      return (unsigned int)v23;
    v17 = (struct _SecBufferDesc *)ExistingTokenHandle;
    v11 = 0;
    v15 = TargetHandle;
    v13 = *(_QWORD *)ReturnLength;
    v19 = v67;
    v20 = v65;
    if ( !a2 )
      *(_QWORD *)&v75 = v74;
  }
  if ( *(_DWORD *)(a9 + 4) > 0x12u )
    return (unsigned int)-2146892963;
  v66 = 0;
  if ( a1 )
  {
    v24 = v74;
    *(_DWORD *)(a1 + 20) = 590696;
    v25 = v75;
    *(_QWORD *)(a1 + 224) = ProcessSecurityContextMarshalParams;
    *(_QWORD *)(a1 + 32) = a1;
    *(_QWORD *)(a1 + 232) = ProcessSecurityContextUnMarshalResponse;
    v26 = 1;
    *(_DWORD *)(a1 + 88) = a6;
    *(_DWORD *)(a1 + 92) = a7;
    if ( !a4 )
      v26 = 2;
    *(_QWORD *)(a1 + 72) = a4;
    *(_OWORD *)(a1 + 40) = v25;
    *(_QWORD *)(a1 + 80) = v17;
    *(_OWORD *)(a1 + 56) = v24;
    *(_QWORD *)(a1 + 96) = a8;
    *(_QWORD *)(a1 + 104) = a9;
    *(_QWORD *)(a1 + 112) = v15;
    *(_QWORD *)(a1 + 120) = v13;
    *(_OWORD *)(a1 + 128) = v24;
    *(_QWORD *)(a1 + 144) = v19;
    *(_QWORD *)(a1 + 152) = v20;
    *(_OWORD *)(a1 + 160) = v21;
    v27 = *(_QWORD *)a1 == 0;
    v65 = 0;
    TargetHandle = 0;
    v28 = !v27;
    PerformanceCounter = KeQueryPerformanceCounter(0);
    KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v67);
    if ( !KsecddLsaStateRef::IsValid((KsecddLsaStateRef *)&v67) )
    {
      v23 = -1073741058;
      goto LABEL_44;
    }
    v30 = KsecddLsaStateRef::operator _KSECDDLSASTATE *(&v67);
    ExistingTokenHandle = 0;
    v23 = ZwOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, 0x200u, &ExistingTokenHandle);
    if ( v23 == -1073741700 )
      v23 = ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0xCu, 0x200u, &ExistingTokenHandle);
    if ( v23 < 0 )
      goto LABEL_78;
    TokenInformation = 0;
    ReturnLength[0] = 0;
    v23 = ZwQueryInformationToken(ExistingTokenHandle, TokenType, &TokenInformation, 4u, ReturnLength);
    if ( v23 < 0 )
    {
      ZwClose(ExistingTokenHandle);
    }
    else
    {
      if ( TokenInformation == 2 )
      {
        v31 = ExistingTokenHandle;
      }
      else
      {
        ObjectAttributes.SecurityQualityOfService = &v73;
        LODWORD(v73) = 12;
        *(_QWORD *)((char *)&v73 + 4) = 0x100000002LL;
        *(_QWORD *)&ObjectAttributes.Length = 48;
        *(_QWORD *)&ObjectAttributes.Attributes = 512;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.ObjectName = 0;
        ObjectAttributes.SecurityDescriptor = 0;
        SourceHandle[0] = 0;
        v23 = ZwDuplicateToken(ExistingTokenHandle, 0xCu, &ObjectAttributes, 0, TokenImpersonation, SourceHandle);
        ZwClose(ExistingTokenHandle);
        if ( v23 < 0 )
          goto LABEL_78;
        v31 = SourceHandle[0];
        ExistingTokenHandle = SourceHandle[0];
      }
      v23 = ZwDuplicateObject((HANDLE)0xFFFFFFFFFFFFFFFFLL, v31, *(HANDLE *)(v30 + 8), &TargetHandle, 0, 0, 3u);
      if ( v23 >= 0 )
      {
        v23 = (*(__int64 (__fastcall **)(__int64, __int64 *, int *))(a1 + 224))(a1, &v65, &v66);
        if ( v23 >= 0 )
        {
          *(_DWORD *)(a1 + 16) = v26;
          v32 = KeQueryPerformanceCounter(0);
          v33 = *(_DWORD *)(a1 + 16);
          *(LARGE_INTEGER *)(a1 + 24) = v32;
          *(_DWORD *)(v65 + 8) = v33;
          *(_DWORD *)(v65 + 40) = v66;
          *(_QWORD *)(v65 + 32) = TargetHandle;
          *(_QWORD *)(v65 + 16) = (unsigned int)KsecSystemProcessId;
          CurrentThreadId = (unsigned int)PsGetCurrentThreadId();
          v35 = AsyncSspiHandleIoctlIpcResponse;
          if ( !v28 )
            v35 = 0;
          *(_QWORD *)(v65 + 24) = CurrentThreadId;
          v36 = v65;
          KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&ExistingTokenHandle);
          if ( KsecddLsaStateRef::IsValid((KsecddLsaStateRef *)&ExistingTokenHandle) )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 15, WPP_f9740104427135617d8c60794f45a901_Traceguids);
            v60 = (void *)KsecddLsaStateRef::operator _KSECDDLSASTATE *(&ExistingTokenHandle);
            v23 = PendingCallPush(v36, v35, a1, v60);
            if ( v23 >= 0 )
            {
              v59 = KsecddLsaStateRef::operator _KSECDDLSASTATE *(&ExistingTokenHandle);
              if ( *(_QWORD *)(v59 + 88) != v59 + 88 )
                HandlePendingIrps(v60);
            }
          }
          else
          {
            v23 = -1073741058;
          }
          KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&ExistingTokenHandle);
          if ( v23 >= 0 )
          {
LABEL_30:
            if ( v28 )
            {
LABEL_44:
              KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v67);
              return (unsigned int)v23;
            }
            v37 = *(_QWORD *)(a1 + 24);
            KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&ExistingTokenHandle);
            if ( KsecddLsaStateRef::IsValid((KsecddLsaStateRef *)&ExistingTokenHandle) )
            {
              KeGetCurrentProcessorNumberEx(0);
              v39 = *(_QWORD *)(KsecddLsaStateRef::operator _KSECDDLSASTATE *(&ExistingTokenHandle) + 312);
              if ( v26 == 2 )
              {
                v41 = v38 + 40;
                v42 = v38 + 48;
                v43 = v38 + 56;
                goto LABEL_39;
              }
              v40 = v26 - 1;
              if ( !v40 )
              {
                v41 = v38 + 64;
                v42 = v38 + 72;
                v43 = v38 + 80;
                goto LABEL_39;
              }
              if ( v40 == 2 )
              {
                v41 = v38 + 112;
                v42 = v38 + 120;
                v43 = v38 + 128;
LABEL_39:
                v44 = (volatile signed __int64 *)(v39 + v41);
                v45 = (volatile signed __int64 *)(v39 + v42);
                v46 = (volatile signed __int64 *)(v39 + v43);
                if ( v44 && v45 && v46 )
                {
                  v47 = KeQueryPerformanceCounter(0);
                  _InterlockedIncrement64(v44);
                  _InterlockedAdd64(v45, v47.QuadPart - PerformanceCounter.QuadPart);
                  _InterlockedAdd64(v46, v47.QuadPart - v37);
                }
              }
            }
            KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&ExistingTokenHandle);
            *(_DWORD *)(a1 + 20) = v23;
            goto LABEL_44;
          }
        }
      }
    }
LABEL_78:
    if ( TargetHandle )
    {
      v61 = KsecddLsaStateRef::operator _KSECDDLSASTATE *(&v67);
      ZwDuplicateObject(*(HANDLE *)(v61 + 8), v62, 0, 0, 0, 0, 1u);
    }
    goto LABEL_30;
  }
  v63 = 0;
  pvBuffer = 0;
  v73 = 0u;
  v50 = 0;
  if ( v17 )
  {
    cBuffers = v17->cBuffers;
    if ( cBuffers )
    {
      pBuffers = v17->pBuffers;
      v57 = 0;
      do
      {
        BufferType = pBuffers[v57].BufferType;
        if ( BufferType == 129 )
        {
          pvBuffer = (__int64)pBuffers[v57].pvBuffer;
        }
        else if ( BufferType == 130 )
        {
          v50 = (__int64)pBuffers[v57].pvBuffer;
        }
        ++v11;
        ++v57;
      }
      while ( v11 < cBuffers );
      v15 = TargetHandle;
    }
  }
  v23 = SspipProcessSecurityContext(
          &v75,
          &v74,
          a4,
          v17,
          a6,
          a7,
          a8,
          a9,
          v15,
          v13,
          &v63,
          (__int64)&v73,
          &v66,
          pvBuffer,
          v50);
  *(_OWORD *)SourceHandle = v73;
  if ( v23 >= 0 )
  {
    if ( v63 )
    {
      v53 = v66;
      if ( *((_QWORD *)a8 + 1) && *(_QWORD *)a8 )
      {
        inited = InitUserModeContext(a8, SourceHandle, a8);
        if ( inited >= 0 )
          return (unsigned int)v23;
      }
      else
      {
        inited = -2146893056;
      }
      if ( !a3 || (v53 & 0x20) != 0 )
      {
        DeleteSecurityContextInternal(0, v52, a8);
        *a8 = v21;
      }
      return (unsigned int)inited;
    }
    else if ( a3 && *((_QWORD *)a8 + 1) == *((_QWORD *)&v74 + 1) )
    {
      v55 = v65;
      *(_QWORD *)a8 = v67;
      *((_QWORD *)a8 + 1) = v55;
    }
  }
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x1800248c0  push    rbp
0x1800248c2  push    rbx
0x1800248c3  push    rsi
0x1800248c4  push    rdi
0x1800248c5  push    r12
0x1800248c7  push    r13
0x1800248c9  push    r14
0x1800248cb  push    r15
0x1800248cd  lea     rbp, [rsp-58h]
0x1800248d2  sub     rsp, 158h
0x1800248d9  mov     rax, cs:__security_cookie
0x1800248e0  xor     rax, rsp
0x1800248e3  mov     [rbp+90h+var_60], rax
0x1800248e7  mov     r15, [rbp+90h+arg_38]
0x1800248ee  xor     edi, edi
0x1800248f0  mov     r12, [rbp+90h+arg_40]
0x1800248f7  mov     rbx, r8
0x1800248fa  mov     r8, [rbp+90h+arg_50]
0x180024901  mov     r14, rdx
0x180024904  mov     rdx, [rbp+90h+arg_48]
0x18002490b  mov     rsi, rcx
0x18002490e  mov     rcx, [rbp+90h+arg_20]
0x180024915  mov     r13, r9
0x180024918  mov     [rbp+90h+ExistingTokenHandle], rcx
0x18002491c  mov     [rbp+90h+TargetHandle], rdx
0x180024920  mov     qword ptr [rbp+90h+ReturnLength], r8
0x180024924  mov     qword ptr [rbp+90h+var_80], rdi
0x180024928  mov     qword ptr [rbp+90h+var_80+8], rdi
0x18002492c  mov     qword ptr [rbp+90h+var_70], rdi
0x180024930  mov     qword ptr [rbp+90h+var_70+8], rdi
0x180024934  test    rbx, rbx
0x180024937  jz      loc_180024D51
0x18002493d  test    r15, r15
0x180024940  jz      loc_180024D5A
0x180024946  movaps  [rsp+190h+var_50], xmm6
0x18002494e  mov     r9, rdi
0x180024951  mov     [rbp+90h+var_F0], rdi
0x180024955  mov     r10, rdi
0x180024958  mov     [rbp+90h+var_100], rdi
0x18002495c  test    r14, r14
0x18002495f  jz      short loc_180024969
0x180024961  movups  xmm0, xmmword ptr [r14]
0x180024965  movups  [rbp+90h+var_70], xmm0
0x180024969  movups  xmm6, xmmword ptr [r15]
0x18002496d  test    rbx, rbx
0x180024970  jz      short loc_1800249B6
0x180024972  mov     rcx, [rbx+8]
0x180024976  lea     rdx, [rbp+90h+var_80]
0x18002497a  mov     rax, [rbx]
0x18002497d  mov     [rbp+90h+var_100], rcx
0x180024981  mov     rcx, rbx
0x180024984  mov     [rbp+90h+var_F0], rax
0x180024988  call    MapKernelContextHandle
0x18002498d  mov     edi, eax
0x18002498f  test    eax, eax
0x180024991  js      loc_180024DBE
0x180024997  mov     rcx, [rbp+90h+ExistingTokenHandle]
0x18002499b  xor     edi, edi
0x18002499d  mov     rdx, [rbp+90h+TargetHandle]
0x1800249a1  mov     r8, qword ptr [rbp+90h+ReturnLength]
0x1800249a5  mov     r9, [rbp+90h+var_F0]
0x1800249a9  mov     r10, [rbp+90h+var_100]
0x1800249ad  test    r14, r14
0x1800249b0  jz      loc_180024F91
0x1800249b6  cmp     dword ptr [r12+4], 12h
0x1800249bc  ja      loc_180024E01
0x1800249c2  mov     [rbp+90h+var_F8], edi
0x1800249c5  test    rsi, rsi
0x1800249c8  jz      loc_180024E08
0x1800249ce  movups  xmm1, [rbp+90h+var_80]
0x1800249d2  mov     dword ptr [rsi+14h], 90368h
0x1800249d9  lea     rax, ProcessSecurityContextMarshalParams
0x1800249e0  movups  xmm0, [rbp+90h+var_70]
0x1800249e4  mov     [rsi+0E0h], rax
0x1800249eb  test    r13, r13
0x1800249ee  lea     rax, ProcessSecurityContextUnMarshalResponse
0x1800249f5  mov     [rsi+20h], rsi
0x1800249f9  mov     [rsi+0E8h], rax
0x180024a00  mov     r14d, 1
0x180024a06  mov     eax, [rbp+90h+arg_28]
0x180024a0c  mov     [rsi+58h], eax
0x180024a0f  mov     eax, [rbp+90h+arg_30]
0x180024a15  mov     [rsi+5Ch], eax
0x180024a18  mov     eax, 2
0x180024a1d  cmovz   r14d, eax
0x180024a21  mov     [rsi+48h], r13
0x180024a25  movups  xmmword ptr [rsi+28h], xmm0
0x180024a29  mov     [rsi+50h], rcx
0x180024a2d  movups  xmmword ptr [rsi+38h], xmm1
0x180024a31  mov     [rsi+60h], r15
0x180024a35  mov     [rsi+68h], r12
0x180024a39  mov     [rsi+70h], rdx
0x180024a3d  mov     [rsi+78h], r8
0x180024a41  movups  xmmword ptr [rsi+80h], xmm1
0x180024a48  mov     [rsi+90h], r9
0x180024a4f  mov     [rsi+98h], r10
0x180024a56  movups  xmmword ptr [rsi+0A0h], xmm6
0x180024a5d  cmp     qword ptr [rsi], 0
0x180024a61  mov     [rbp+90h+var_100], rdi
0x180024a65  mov     [rbp+90h+TargetHandle], rdi
0x180024a69  jz      loc_180024F9E
0x180024a6f  mov     r15b, 1
0x180024a72  xor     ecx, ecx; PerformanceFrequency
0x180024a74  call    cs:__imp_KeQueryPerformanceCounter
0x180024a7b  nop     dword ptr [rax+rax+00h]
0x180024a80  lea     rcx, [rbp+90h+var_F0]; this
0x180024a84  mov     rbx, rax
0x180024a87  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180024a8c  lea     rcx, [rbp+90h+var_F0]; this
0x180024a90  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x180024a95  test    al, al
0x180024a97  jz      loc_180024DFA
0x180024a9d  lea     rcx, [rbp+90h+var_F0]
0x180024aa1  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x180024aa6  mov     r13, rax
0x180024aa9  mov     [rbp+90h+ExistingTokenHandle], rdi
0x180024aad  lea     rax, [rbp+90h+ExistingTokenHandle]
0x180024ab1  mov     r9d, 200h; HandleAttributes
0x180024ab7  mov     r8b, 1; OpenAsSelf
0x180024aba  mov     [rsp+190h+TokenHandle], rax; TokenHandle
0x180024abf  mov     edx, 0Ch; DesiredAccess
0x180024ac4  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180024acb  call    cs:__imp_ZwOpenThreadTokenEx
0x180024ad2  nop     dword ptr [rax+rax+00h]
0x180024ad7  mov     edi, eax
0x180024ad9  cmp     eax, 0C000007Ch
0x180024ade  jnz     short loc_180024B04
0x180024ae0  lea     r9, [rbp+90h+ExistingTokenHandle]; TokenHandle
0x180024ae4  mov     edx, 0Ch; DesiredAccess
0x180024ae9  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180024af0  mov     r8d, 200h; HandleAttributes
0x180024af6  call    cs:__imp_ZwOpenProcessTokenEx
0x180024afd  nop     dword ptr [rax+rax+00h]
0x180024b02  mov     edi, eax
0x180024b04  xor     r12d, r12d
0x180024b07  test    edi, edi
0x180024b09  js      loc_180025018
0x180024b0f  mov     rcx, [rbp+90h+ExistingTokenHandle]; TokenHandle
0x180024b13  lea     rax, [rbp+90h+ReturnLength]
0x180024b17  mov     r9d, 4; TokenInformationLength
0x180024b1d  mov     [rsp+190h+TokenHandle], rax; ReturnLength
0x180024b22  lea     r8, [rbp+90h+TokenInformation]; TokenInformation
0x180024b26  mov     [rbp+90h+TokenInformation], r12d
0x180024b2a  mov     edx, 8; TokenInformationClass
0x180024b2f  mov     [rbp+90h+ReturnLength], r12d
0x180024b33  call    cs:__imp_ZwQueryInformationToken
0x180024b3a  nop     dword ptr [rax+rax+00h]
0x180024b3f  mov     edi, eax
0x180024b41  test    eax, eax
0x180024b43  js      loc_180024FA6
0x180024b49  cmp     [rbp+90h+TokenInformation], 2
0x180024b4d  jz      loc_180024FB8
0x180024b53  mov     rcx, [rbp+90h+ExistingTokenHandle]; ExistingTokenHandle
0x180024b57  lea     rax, [rbp+90h+var_90]
0x180024b5b  mov     [rbp+90h+ObjectAttributes.SecurityQualityOfService], rax
0x180024b5f  lea     r8, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x180024b63  lea     rax, [rbp+90h+SourceHandle]
0x180024b67  mov     dword ptr [rbp+90h+var_90+8], 1
0x180024b6e  mov     [rsp+190h+NewTokenHandle], rax; NewTokenHandle
0x180024b73  xor     r9d, r9d; EffectiveOnly
0x180024b76  mov     edx, 0Ch; DesiredAccess
0x180024b7b  mov     dword ptr [rsp+190h+TokenHandle], 2; TokenType
0x180024b83  mov     dword ptr [rbp+90h+var_90], 0Ch
0x180024b8a  mov     dword ptr [rbp+90h+var_90+4], 2
0x180024b91  mov     qword ptr [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x180024b99  mov     qword ptr [rbp+90h+ObjectAttributes.Attributes], 200h
0x180024ba1  mov     [rbp+90h+ObjectAttributes.RootDirectory], r12
0x180024ba5  mov     [rbp+90h+ObjectAttributes.ObjectName], r12
0x180024ba9  mov     [rbp+90h+ObjectAttributes.SecurityDescriptor], r12
0x180024bad  mov     [rbp+90h+SourceHandle], r12
0x180024bb1  call    cs:__imp_ZwDuplicateToken
0x180024bb8  nop     dword ptr [rax+rax+00h]
0x180024bbd  mov     rcx, [rbp+90h+ExistingTokenHandle]; Handle
0x180024bc1  mov     edi, eax
0x180024bc3  call    cs:__imp_ZwClose
0x180024bca  nop     dword ptr [rax+rax+00h]
0x180024bcf  test    edi, edi
0x180024bd1  js      loc_180025018
0x180024bd7  mov     rdx, [rbp+90h+SourceHandle]; SourceHandle
0x180024bdb  mov     [rbp+90h+ExistingTokenHandle], rdx
0x180024bdf  mov     r8, [r13+8]; TargetProcessHandle
0x180024be3  lea     r9, [rbp+90h+TargetHandle]; TargetHandle
0x180024be7  mov     [rsp+190h+Options], 3; Options
0x180024bef  mov     rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x180024bf6  mov     dword ptr [rsp+190h+NewTokenHandle], r12d; HandleAttributes
0x180024bfb  mov     dword ptr [rsp+190h+TokenHandle], r12d; DesiredAccess
0x180024c00  call    cs:__imp_ZwDuplicateObject
0x180024c07  nop     dword ptr [rax+rax+00h]
0x180024c0c  mov     edi, eax
0x180024c0e  test    eax, eax
0x180024c10  js      loc_180025018
0x180024c16  mov     rax, [rsi+0E0h]
0x180024c1d  lea     r8, [rbp+90h+var_F8]
0x180024c21  lea     rdx, [rbp+90h+var_100]
0x180024c25  mov     rcx, rsi
0x180024c28  call    _guard_dispatch_icall
0x180024c2d  mov     edi, eax
0x180024c2f  test    eax, eax
0x180024c31  js      loc_180025018
0x180024c37  xor     ecx, ecx; PerformanceFrequency
0x180024c39  mov     [rsi+10h], r14d
0x180024c3d  call    cs:__imp_KeQueryPerformanceCounter
0x180024c44  nop     dword ptr [rax+rax+00h]
0x180024c49  mov     ecx, [rsi+10h]
0x180024c4c  mov     [rsi+18h], rax
0x180024c50  mov     rax, [rbp+90h+var_100]
0x180024c54  mov     [rax+8], ecx
0x180024c57  mov     rcx, [rbp+90h+var_100]
0x180024c5b  mov     eax, [rbp+90h+var_F8]
0x180024c5e  mov     [rcx+28h], eax
0x180024c61  mov     rcx, [rbp+90h+var_100]
0x180024c65  mov     rax, [rbp+90h+TargetHandle]
0x180024c69  mov     [rcx+20h], rax
0x180024c6d  mov     rax, [rbp+90h+var_100]
0x180024c71  mov     ecx, cs:KsecSystemProcessId
0x180024c77  mov     [rax+10h], rcx
0x180024c7b  call    cs:__imp_PsGetCurrentThreadId
0x180024c82  nop     dword ptr [rax+rax+00h]
0x180024c87  mov     ecx, eax
0x180024c89  test    r15b, r15b
0x180024c8c  mov     rax, [rbp+90h+var_100]
0x180024c90  lea     rdi, AsyncSspiHandleIoctlIpcResponse
0x180024c97  cmovz   rdi, r12
0x180024c9b  mov     [rax+18h], rcx
0x180024c9f  lea     rcx, [rbp+90h+ExistingTokenHandle]; this
0x180024ca3  mov     r12, [rbp+90h+var_100]
0x180024ca7  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180024cac  lea     rcx, [rbp+90h+ExistingTokenHandle]; this
0x180024cb0  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x180024cb5  test    al, al
0x180024cb7  jnz     loc_180024FC1
0x180024cbd  mov     edi, 0C00002FEh
0x180024cc2  lea     rcx, [rbp+90h+ExistingTokenHandle]; this
0x180024cc6  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180024ccb  test    edi, edi
0x180024ccd  js      loc_180025015
0x180024cd3  test    r15b, r15b
0x180024cd6  jnz     loc_180024DB5
0x180024cdc  mov     r13, [rsi+18h]
0x180024ce0  lea     rcx, [rbp+90h+ExistingTokenHandle]; this
0x180024ce4  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180024ce9  lea     rcx, [rbp+90h+ExistingTokenHandle]; this
0x180024ced  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x180024cf2  test    al, al
0x180024cf4  jz      loc_180024DA9
0x180024cfa  xor     ecx, ecx; ProcNumber
0x180024cfc  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x180024d03  nop     dword ptr [rax+rax+00h]
0x180024d08  mov     eax, eax
0x180024d0a  lea     rcx, [rbp+90h+ExistingTokenHandle]
0x180024d0e  imul    rdx, rax, 88h
0x180024d15  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x180024d1a  mov     rcx, [rax+138h]
0x180024d21  cmp     r14d, 2
0x180024d25  jz      short loc_180024D61
0x180024d27  test    r14d, r14d
0x180024d2a  jz      loc_180024DE9
0x180024d30  sub     r14d, 1
0x180024d34  jz      loc_18002505B
0x180024d3a  cmp     r14d, 2
0x180024d3e  jnz     short loc_180024DA9
0x180024d40  lea     r14, [rdx+70h]
0x180024d44  lea     r15, [rdx+78h]
0x180024d48  lea     r12, [rdx+80h]
0x180024d4f  jmp     short loc_180024D6D
0x180024d51  test    r14, r14
0x180024d54  jnz     loc_18002493D
0x180024d5a  mov     edi, 80090301h
0x180024d5f  jmp     short loc_180024DC6
0x180024d61  lea     r14, [rdx+28h]
0x180024d65  lea     r15, [rdx+30h]
0x180024d69  lea     r12, [rdx+38h]
0x180024d6d  add     r14, rcx
0x180024d70  add     r15, rcx
0x180024d73  add     r12, rcx
0x180024d76  test    r14, r14
0x180024d79  jz      short loc_180024DA9
0x180024d7b  test    r15, r15
0x180024d7e  jz      short loc_180024DA9
0x180024d80  test    r12, r12
0x180024d83  jz      short loc_180024DA9
0x180024d85  xor     ecx, ecx; PerformanceFrequency
0x180024d87  call    cs:__imp_KeQueryPerformanceCounter
0x180024d8e  nop     dword ptr [rax+rax+00h]
0x180024d93  lock inc qword ptr [r14]
0x180024d97  mov     rcx, rax
0x180024d9a  sub     rcx, rbx
0x180024d9d  lock add [r15], rcx
0x180024da1  sub     rax, r13
0x180024da4  lock add [r12], rax
0x180024da9  lea     rcx, [rbp+90h+ExistingTokenHandle]; this
0x180024dad  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180024db2  mov     [rsi+14h], edi
0x180024db5  lea     rcx, [rbp+90h+var_F0]; this
0x180024db9  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180024dbe  movaps  xmm6, [rsp+190h+var_50]
0x180024dc6  mov     eax, edi
0x180024dc8  mov     rcx, [rbp+90h+var_60]
0x180024dcc  xor     rcx, rsp; StackCookie
0x180024dcf  call    __security_check_cookie
  ... truncated ...
```
