# KsecProcessSecurityContext

- ea: `0x180024910`
- end: `0x1800250d0`
- name: `KsecProcessSecurityContext`
- size: `1984`
- prototype: `__int64 __fastcall(__int64, __int128 *, __int64 *, __int64, _DWORD *, int, int, __int128 *, __int64, void *, __int64)`
- caller_count: `3`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180022d90`
- `0x180024820`
- `0x1800248a0`

## callees

- `0x1800017c4`
- `0x180001c00`
- `0x180001cf0`
- `0x180001f90`
- `0x180002820`
- `0x180002a84`
- `0x180007ba8`
- `0x18000f900`
- `0x1800108a0`
- `0x180010980`
- `0x180024910`
- `0x1800250e0`
- `0x180025e00`
- `0x180026580`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x180024ccb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x180024ccb`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x180024b1b`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x180024b1b`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x180024b46`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x180024b46`
- `ntoskrnl!ZwQueryInformationToken` at `0x180024b83`
- `ntoskrnl!ZwQueryInformationToken` at `0x180024b83`
- `ntoskrnl!ZwDuplicateToken` at `0x180024c01`
- `ntoskrnl!ZwDuplicateToken` at `0x180024c01`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x180024d4c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x180024d4c`
- `ntoskrnl!ZwClose` at `0x180024c13`
- `ntoskrnl!ZwClose` at `0x180024ffa`
- `ntoskrnl!ZwClose` at `0x180024c13`
- `ntoskrnl!ZwClose` at `0x180024ffa`
- `ntoskrnl!ZwDuplicateObject` at `0x180024c50`
- `ntoskrnl!ZwDuplicateObject` at `0x18002509a`
- `ntoskrnl!ZwDuplicateObject` at `0x180024c50`
- `ntoskrnl!ZwDuplicateObject` at `0x18002509a`
- `HAL!KeQueryPerformanceCounter` at `0x180024ac4`
- `HAL!KeQueryPerformanceCounter` at `0x180024c8d`
- `HAL!KeQueryPerformanceCounter` at `0x180024dd7`
- `HAL!KeQueryPerformanceCounter` at `0x180024ac4`
- `HAL!KeQueryPerformanceCounter` at `0x180024c8d`
- `HAL!KeQueryPerformanceCounter` at `0x180024dd7`

## pseudocode

```c
__int64 __fastcall KsecProcessSecurityContext(
        __int64 a1,
        __int128 *a2,
        __int64 *a3,
        __int64 a4,
        _DWORD *a5,
        int a6,
        int a7,
        __int128 *a8,
        __int64 a9,
        void *a10,
        __int64 a11)
{
  unsigned int v11; // edi
  __int64 v13; // r8
  HANDLE v15; // rdx
  _DWORD *v17; // rcx
  __int64 v19; // r9
  __int64 v20; // r10
  __int128 v21; // xmm6
  __int64 v22; // rax
  NTSTATUS v23; // edi
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
  __int64 (__fastcall *v35)(int, int, int, int, __int64); // rdi
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
  __int64 v49; // r9
  __int64 v50; // r10
  unsigned int v51; // r11d
  __int64 v52; // rdx
  char v53; // r14
  int inited; // esi
  __int64 v55; // rcx
  __int64 v56; // rdx
  __int64 v57; // rsi
  int v58; // eax
  __int64 v59; // rax
  void *v60; // r13
  __int64 v61; // rax
  HANDLE v62; // rdx
  char v63[8]; // [rsp+80h] [rbp-80h] BYREF
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
    v23 = MapKernelContextHandle(a3, &v74, a11, 0);
    if ( v23 < 0 )
      return (unsigned int)v23;
    v17 = ExistingTokenHandle;
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
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 15, &WPP_f9740104427135617d8c60794f45a901_Traceguids);
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
  v63[0] = 0;
  v49 = 0;
  v73 = 0u;
  v50 = 0;
  if ( v17 )
  {
    v51 = v17[1];
    if ( v51 )
    {
      v56 = *((_QWORD *)v17 + 1);
      v57 = 0;
      do
      {
        v58 = *(_DWORD *)(v56 + 16 * v57 + 4);
        if ( v58 == 129 )
        {
          v49 = *(_QWORD *)(v56 + 16 * v57 + 8);
        }
        else if ( v58 == 130 )
        {
          v50 = *(_QWORD *)(v56 + 16 * v57 + 8);
        }
        ++v11;
        ++v57;
      }
      while ( v11 < v51 );
      v15 = TargetHandle;
    }
  }
  v23 = SspipProcessSecurityContext(&v75, &v74, a4, v17, a6, a7, a8, a9, v15, v13, v63, &v73, &v66, v49, v50);
  *(_OWORD *)SourceHandle = v73;
  if ( v23 >= 0 )
  {
    if ( v63[0] )
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
0x180024910  push    rbp
0x180024912  push    rbx
0x180024913  push    rsi
0x180024914  push    rdi
0x180024915  push    r12
0x180024917  push    r13
0x180024919  push    r14
0x18002491b  push    r15
0x18002491d  lea     rbp, [rsp-58h]
0x180024922  sub     rsp, 158h
0x180024929  mov     rax, cs:__security_cookie
0x180024930  xor     rax, rsp
0x180024933  mov     [rbp+90h+var_60], rax
0x180024937  mov     r15, [rbp+90h+arg_38]
0x18002493e  xor     edi, edi
0x180024940  mov     r12, [rbp+90h+arg_40]
0x180024947  mov     rbx, r8
0x18002494a  mov     r8, [rbp+90h+arg_50]
0x180024951  mov     r14, rdx
0x180024954  mov     rdx, [rbp+90h+arg_48]
0x18002495b  mov     rsi, rcx
0x18002495e  mov     rcx, [rbp+90h+arg_20]
0x180024965  mov     r13, r9
0x180024968  mov     [rbp+90h+ExistingTokenHandle], rcx
0x18002496c  mov     [rbp+90h+TargetHandle], rdx
0x180024970  mov     qword ptr [rbp+90h+ReturnLength], r8
0x180024974  mov     qword ptr [rbp+90h+var_80], rdi
0x180024978  mov     qword ptr [rbp+90h+var_80+8], rdi
0x18002497c  mov     qword ptr [rbp+90h+var_70], rdi
0x180024980  mov     qword ptr [rbp+90h+var_70+8], rdi
0x180024984  test    rbx, rbx
0x180024987  jz      loc_180024DA1
0x18002498d  test    r15, r15
0x180024990  jz      loc_180024DAA
0x180024996  movaps  [rsp+190h+var_50], xmm6
0x18002499e  mov     r9, rdi
0x1800249a1  mov     [rbp+90h+var_F0], rdi
0x1800249a5  mov     r10, rdi
0x1800249a8  mov     [rbp+90h+var_100], rdi
0x1800249ac  test    r14, r14
0x1800249af  jz      short loc_1800249B9
0x1800249b1  movups  xmm0, xmmword ptr [r14]
0x1800249b5  movups  [rbp+90h+var_70], xmm0
0x1800249b9  movups  xmm6, xmmword ptr [r15]
0x1800249bd  test    rbx, rbx
0x1800249c0  jz      short loc_180024A06
0x1800249c2  mov     rcx, [rbx+8]
0x1800249c6  lea     rdx, [rbp+90h+var_80]
0x1800249ca  mov     rax, [rbx]
0x1800249cd  mov     [rbp+90h+var_100], rcx
0x1800249d1  mov     rcx, rbx
0x1800249d4  mov     [rbp+90h+var_F0], rax
0x1800249d8  call    MapKernelContextHandle
0x1800249dd  mov     edi, eax
0x1800249df  test    eax, eax
0x1800249e1  js      loc_180024E0E
0x1800249e7  mov     rcx, [rbp+90h+ExistingTokenHandle]
0x1800249eb  xor     edi, edi
0x1800249ed  mov     rdx, [rbp+90h+TargetHandle]
0x1800249f1  mov     r8, qword ptr [rbp+90h+ReturnLength]
0x1800249f5  mov     r9, [rbp+90h+var_F0]
0x1800249f9  mov     r10, [rbp+90h+var_100]
0x1800249fd  test    r14, r14
0x180024a00  jz      loc_180024FE1
0x180024a06  cmp     dword ptr [r12+4], 12h
0x180024a0c  ja      loc_180024E51
0x180024a12  mov     [rbp+90h+var_F8], edi
0x180024a15  test    rsi, rsi
0x180024a18  jz      loc_180024E58
0x180024a1e  movups  xmm1, [rbp+90h+var_80]
0x180024a22  mov     dword ptr [rsi+14h], 90368h
0x180024a29  lea     rax, ProcessSecurityContextMarshalParams
0x180024a30  movups  xmm0, [rbp+90h+var_70]
0x180024a34  mov     [rsi+0E0h], rax
0x180024a3b  test    r13, r13
0x180024a3e  lea     rax, ProcessSecurityContextUnMarshalResponse
0x180024a45  mov     [rsi+20h], rsi
0x180024a49  mov     [rsi+0E8h], rax
0x180024a50  mov     r14d, 1
0x180024a56  mov     eax, [rbp+90h+arg_28]
0x180024a5c  mov     [rsi+58h], eax
0x180024a5f  mov     eax, [rbp+90h+arg_30]
0x180024a65  mov     [rsi+5Ch], eax
0x180024a68  mov     eax, 2
0x180024a6d  cmovz   r14d, eax
0x180024a71  mov     [rsi+48h], r13
0x180024a75  movups  xmmword ptr [rsi+28h], xmm0
0x180024a79  mov     [rsi+50h], rcx
0x180024a7d  movups  xmmword ptr [rsi+38h], xmm1
0x180024a81  mov     [rsi+60h], r15
0x180024a85  mov     [rsi+68h], r12
0x180024a89  mov     [rsi+70h], rdx
0x180024a8d  mov     [rsi+78h], r8
0x180024a91  movups  xmmword ptr [rsi+80h], xmm1
0x180024a98  mov     [rsi+90h], r9
0x180024a9f  mov     [rsi+98h], r10
0x180024aa6  movups  xmmword ptr [rsi+0A0h], xmm6
0x180024aad  cmp     qword ptr [rsi], 0
0x180024ab1  mov     [rbp+90h+var_100], rdi
0x180024ab5  mov     [rbp+90h+TargetHandle], rdi
0x180024ab9  jz      loc_180024FEE
0x180024abf  mov     r15b, 1
0x180024ac2  xor     ecx, ecx; PerformanceFrequency
0x180024ac4  call    cs:__imp_KeQueryPerformanceCounter
0x180024acb  nop     dword ptr [rax+rax+00h]
0x180024ad0  lea     rcx, [rbp+90h+var_F0]; this
0x180024ad4  mov     rbx, rax
0x180024ad7  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180024adc  lea     rcx, [rbp+90h+var_F0]; this
0x180024ae0  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x180024ae5  test    al, al
0x180024ae7  jz      loc_180024E4A
0x180024aed  lea     rcx, [rbp+90h+var_F0]
0x180024af1  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x180024af6  mov     r13, rax
0x180024af9  mov     [rbp+90h+ExistingTokenHandle], rdi
0x180024afd  lea     rax, [rbp+90h+ExistingTokenHandle]
0x180024b01  mov     r9d, 200h; HandleAttributes
0x180024b07  mov     r8b, 1; OpenAsSelf
0x180024b0a  mov     [rsp+190h+TokenHandle], rax; TokenHandle
0x180024b0f  mov     edx, 0Ch; DesiredAccess
0x180024b14  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180024b1b  call    cs:__imp_ZwOpenThreadTokenEx
0x180024b22  nop     dword ptr [rax+rax+00h]
0x180024b27  mov     edi, eax
0x180024b29  cmp     eax, 0C000007Ch
0x180024b2e  jnz     short loc_180024B54
0x180024b30  lea     r9, [rbp+90h+ExistingTokenHandle]; TokenHandle
0x180024b34  mov     edx, 0Ch; DesiredAccess
0x180024b39  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180024b40  mov     r8d, 200h; HandleAttributes
0x180024b46  call    cs:__imp_ZwOpenProcessTokenEx
0x180024b4d  nop     dword ptr [rax+rax+00h]
0x180024b52  mov     edi, eax
0x180024b54  xor     r12d, r12d
0x180024b57  test    edi, edi
0x180024b59  js      loc_180025068
0x180024b5f  mov     rcx, [rbp+90h+ExistingTokenHandle]; TokenHandle
0x180024b63  lea     rax, [rbp+90h+ReturnLength]
0x180024b67  mov     r9d, 4; TokenInformationLength
0x180024b6d  mov     [rsp+190h+TokenHandle], rax; ReturnLength
0x180024b72  lea     r8, [rbp+90h+TokenInformation]; TokenInformation
0x180024b76  mov     [rbp+90h+TokenInformation], r12d
0x180024b7a  mov     edx, 8; TokenInformationClass
0x180024b7f  mov     [rbp+90h+ReturnLength], r12d
0x180024b83  call    cs:__imp_ZwQueryInformationToken
0x180024b8a  nop     dword ptr [rax+rax+00h]
0x180024b8f  mov     edi, eax
0x180024b91  test    eax, eax
0x180024b93  js      loc_180024FF6
0x180024b99  cmp     [rbp+90h+TokenInformation], 2
0x180024b9d  jz      loc_180025008
0x180024ba3  mov     rcx, [rbp+90h+ExistingTokenHandle]; ExistingTokenHandle
0x180024ba7  lea     rax, [rbp+90h+var_90]
0x180024bab  mov     [rbp+90h+ObjectAttributes.SecurityQualityOfService], rax
0x180024baf  lea     r8, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x180024bb3  lea     rax, [rbp+90h+SourceHandle]
0x180024bb7  mov     dword ptr [rbp+90h+var_90+8], 1
0x180024bbe  mov     [rsp+190h+NewTokenHandle], rax; NewTokenHandle
0x180024bc3  xor     r9d, r9d; EffectiveOnly
0x180024bc6  mov     edx, 0Ch; DesiredAccess
0x180024bcb  mov     dword ptr [rsp+190h+TokenHandle], 2; TokenType
0x180024bd3  mov     dword ptr [rbp+90h+var_90], 0Ch
0x180024bda  mov     dword ptr [rbp+90h+var_90+4], 2
0x180024be1  mov     qword ptr [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x180024be9  mov     qword ptr [rbp+90h+ObjectAttributes.Attributes], 200h
0x180024bf1  mov     [rbp+90h+ObjectAttributes.RootDirectory], r12
0x180024bf5  mov     [rbp+90h+ObjectAttributes.ObjectName], r12
0x180024bf9  mov     [rbp+90h+ObjectAttributes.SecurityDescriptor], r12
0x180024bfd  mov     [rbp+90h+SourceHandle], r12
0x180024c01  call    cs:__imp_ZwDuplicateToken
0x180024c08  nop     dword ptr [rax+rax+00h]
0x180024c0d  mov     rcx, [rbp+90h+ExistingTokenHandle]; Handle
0x180024c11  mov     edi, eax
0x180024c13  call    cs:__imp_ZwClose
0x180024c1a  nop     dword ptr [rax+rax+00h]
0x180024c1f  test    edi, edi
0x180024c21  js      loc_180025068
0x180024c27  mov     rdx, [rbp+90h+SourceHandle]; SourceHandle
0x180024c2b  mov     [rbp+90h+ExistingTokenHandle], rdx
0x180024c2f  mov     r8, [r13+8]; TargetProcessHandle
0x180024c33  lea     r9, [rbp+90h+TargetHandle]; TargetHandle
0x180024c37  mov     [rsp+190h+Options], 3; Options
0x180024c3f  mov     rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x180024c46  mov     dword ptr [rsp+190h+NewTokenHandle], r12d; HandleAttributes
0x180024c4b  mov     dword ptr [rsp+190h+TokenHandle], r12d; DesiredAccess
0x180024c50  call    cs:__imp_ZwDuplicateObject
0x180024c57  nop     dword ptr [rax+rax+00h]
0x180024c5c  mov     edi, eax
0x180024c5e  test    eax, eax
0x180024c60  js      loc_180025068
0x180024c66  mov     rax, [rsi+0E0h]
0x180024c6d  lea     r8, [rbp+90h+var_F8]
0x180024c71  lea     rdx, [rbp+90h+var_100]
0x180024c75  mov     rcx, rsi
0x180024c78  call    _guard_dispatch_icall
0x180024c7d  mov     edi, eax
0x180024c7f  test    eax, eax
0x180024c81  js      loc_180025068
0x180024c87  xor     ecx, ecx; PerformanceFrequency
0x180024c89  mov     [rsi+10h], r14d
0x180024c8d  call    cs:__imp_KeQueryPerformanceCounter
0x180024c94  nop     dword ptr [rax+rax+00h]
0x180024c99  mov     ecx, [rsi+10h]
0x180024c9c  mov     [rsi+18h], rax
0x180024ca0  mov     rax, [rbp+90h+var_100]
0x180024ca4  mov     [rax+8], ecx
0x180024ca7  mov     rcx, [rbp+90h+var_100]
0x180024cab  mov     eax, [rbp+90h+var_F8]
0x180024cae  mov     [rcx+28h], eax
0x180024cb1  mov     rcx, [rbp+90h+var_100]
0x180024cb5  mov     rax, [rbp+90h+TargetHandle]
0x180024cb9  mov     [rcx+20h], rax
0x180024cbd  mov     rax, [rbp+90h+var_100]
0x180024cc1  mov     ecx, cs:KsecSystemProcessId
0x180024cc7  mov     [rax+10h], rcx
0x180024ccb  call    cs:__imp_PsGetCurrentThreadId
0x180024cd2  nop     dword ptr [rax+rax+00h]
0x180024cd7  mov     ecx, eax
0x180024cd9  test    r15b, r15b
0x180024cdc  mov     rax, [rbp+90h+var_100]
0x180024ce0  lea     rdi, AsyncSspiHandleIoctlIpcResponse
0x180024ce7  cmovz   rdi, r12
0x180024ceb  mov     [rax+18h], rcx
0x180024cef  lea     rcx, [rbp+90h+ExistingTokenHandle]; this
0x180024cf3  mov     r12, [rbp+90h+var_100]
0x180024cf7  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180024cfc  lea     rcx, [rbp+90h+ExistingTokenHandle]; this
0x180024d00  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x180024d05  test    al, al
0x180024d07  jnz     loc_180025011
0x180024d0d  mov     edi, 0C00002FEh
0x180024d12  lea     rcx, [rbp+90h+ExistingTokenHandle]; this
0x180024d16  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180024d1b  test    edi, edi
0x180024d1d  js      loc_180025065
0x180024d23  test    r15b, r15b
0x180024d26  jnz     loc_180024E05
0x180024d2c  mov     r13, [rsi+18h]
0x180024d30  lea     rcx, [rbp+90h+ExistingTokenHandle]; this
0x180024d34  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180024d39  lea     rcx, [rbp+90h+ExistingTokenHandle]; this
0x180024d3d  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x180024d42  test    al, al
0x180024d44  jz      loc_180024DF9
0x180024d4a  xor     ecx, ecx; ProcNumber
0x180024d4c  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x180024d53  nop     dword ptr [rax+rax+00h]
0x180024d58  mov     eax, eax
0x180024d5a  lea     rcx, [rbp+90h+ExistingTokenHandle]
0x180024d5e  imul    rdx, rax, 88h
0x180024d65  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x180024d6a  mov     rcx, [rax+138h]
0x180024d71  cmp     r14d, 2
0x180024d75  jz      short loc_180024DB1
0x180024d77  test    r14d, r14d
0x180024d7a  jz      loc_180024E39
0x180024d80  sub     r14d, 1
0x180024d84  jz      loc_1800250AB
0x180024d8a  cmp     r14d, 2
0x180024d8e  jnz     short loc_180024DF9
0x180024d90  lea     r14, [rdx+70h]
0x180024d94  lea     r15, [rdx+78h]
0x180024d98  lea     r12, [rdx+80h]
0x180024d9f  jmp     short loc_180024DBD
0x180024da1  test    r14, r14
0x180024da4  jnz     loc_18002498D
0x180024daa  mov     edi, 80090301h
0x180024daf  jmp     short loc_180024E16
0x180024db1  lea     r14, [rdx+28h]
0x180024db5  lea     r15, [rdx+30h]
0x180024db9  lea     r12, [rdx+38h]
0x180024dbd  add     r14, rcx
0x180024dc0  add     r15, rcx
0x180024dc3  add     r12, rcx
0x180024dc6  test    r14, r14
0x180024dc9  jz      short loc_180024DF9
0x180024dcb  test    r15, r15
0x180024dce  jz      short loc_180024DF9
0x180024dd0  test    r12, r12
0x180024dd3  jz      short loc_180024DF9
0x180024dd5  xor     ecx, ecx; PerformanceFrequency
0x180024dd7  call    cs:__imp_KeQueryPerformanceCounter
0x180024dde  nop     dword ptr [rax+rax+00h]
0x180024de3  lock inc qword ptr [r14]
0x180024de7  mov     rcx, rax
0x180024dea  sub     rcx, rbx
0x180024ded  lock add [r15], rcx
0x180024df1  sub     rax, r13
0x180024df4  lock add [r12], rax
0x180024df9  lea     rcx, [rbp+90h+ExistingTokenHandle]; this
0x180024dfd  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180024e02  mov     [rsi+14h], edi
0x180024e05  lea     rcx, [rbp+90h+var_F0]; this
0x180024e09  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180024e0e  movaps  xmm6, [rsp+190h+var_50]
0x180024e16  mov     eax, edi
0x180024e18  mov     rcx, [rbp+90h+var_60]
0x180024e1c  xor     rcx, rsp; StackCookie
0x180024e1f  call    __security_check_cookie
  ... truncated ...
```
