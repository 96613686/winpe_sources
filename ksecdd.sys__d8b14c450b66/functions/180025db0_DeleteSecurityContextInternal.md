# DeleteSecurityContextInternal

- ea: `0x180025db0`
- end: `0x18002630c`
- name: `DeleteSecurityContextInternal`
- size: `1372`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800248c0`
- `0x1800251d0`
- `0x180025d60`
- `0x180025d80`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x180001f90`
- `0x180002820`
- `0x180003c38`
- `0x180007ba8`
- `0x18000c400`
- `0x18000f898`
- `0x180010840`
- `0x180010920`
- `0x180025db0`
- `0x180026530`
- `0x1800298e0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x18002609f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x18002609f`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x180025eef`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x180025eef`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x180025f1a`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x180025f1a`
- `ntoskrnl!ZwQueryInformationToken` at `0x180025f54`
- `ntoskrnl!ZwQueryInformationToken` at `0x180025f54`
- `ntoskrnl!ZwDuplicateToken` at `0x180025fd2`
- `ntoskrnl!ZwDuplicateToken` at `0x180025fd2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x18002611c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x18002611c`
- `ntoskrnl!ZwClose` at `0x180025fe4`
- `ntoskrnl!ZwClose` at `0x180026267`
- `ntoskrnl!ZwClose` at `0x180025fe4`
- `ntoskrnl!ZwClose` at `0x180026267`
- `ntoskrnl!ZwDuplicateObject` at `0x180026021`
- `ntoskrnl!ZwDuplicateObject` at `0x1800262a5`
- `ntoskrnl!ZwDuplicateObject` at `0x180026021`
- `ntoskrnl!ZwDuplicateObject` at `0x1800262a5`
- `HAL!KeQueryPerformanceCounter` at `0x180025e90`
- `HAL!KeQueryPerformanceCounter` at `0x180026061`
- `HAL!KeQueryPerformanceCounter` at `0x180026161`
- `HAL!KeQueryPerformanceCounter` at `0x180025e90`
- `HAL!KeQueryPerformanceCounter` at `0x180026061`
- `HAL!KeQueryPerformanceCounter` at `0x180026161`

## pseudocode

```c
__int64 __fastcall DeleteSecurityContextInternal(LARGE_INTEGER *a1, __int64 a2, _QWORD *a3)
{
  int v5; // ecx
  NTSTATUS v6; // edi
  bool v7; // r15
  LARGE_INTEGER PerformanceCounter; // rbx
  __int64 v9; // r14
  HANDLE v10; // rdx
  LARGE_INTEGER v11; // rax
  ULONG LowPart; // ecx
  __int64 CurrentThreadId; // rcx
  __int64 (__fastcall *(__fastcall *v14)(__int64, int, __int64, unsigned int, __int64))(__int64, _QWORD); // rdi
  __int64 v15; // r14
  LARGE_INTEGER v16; // r13
  __int64 v17; // rdx
  __int64 v18; // rcx
  volatile signed __int64 *v19; // r12
  volatile signed __int64 *v20; // r14
  volatile signed __int64 *v21; // r15
  LARGE_INTEGER v22; // rax
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rax
  HANDLE v29; // rdx
  void *v30; // r12
  HANDLE ExistingTokenHandle; // [rsp+40h] [rbp-69h] BYREF
  __int64 v32; // [rsp+48h] [rbp-61h] BYREF
  int TokenInformation; // [rsp+50h] [rbp-59h] BYREF
  int v34; // [rsp+54h] [rbp-55h] BYREF
  _BYTE v35[8]; // [rsp+58h] [rbp-51h] BYREF
  ULONG ReturnLength; // [rsp+60h] [rbp-49h] BYREF
  HANDLE TargetHandle; // [rsp+68h] [rbp-41h] BYREF
  HANDLE SourceHandle; // [rsp+70h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-31h] BYREF
  _DWORD v40[4]; // [rsp+A8h] [rbp-1h] BYREF
  __int128 v41; // [rsp+B8h] [rbp+Fh] BYREF

  v41 = 0;
  if ( !a3 )
  {
    v5 = -2146893055;
LABEL_3:
    v41 = *(_OWORD *)a3;
    goto LABEL_6;
  }
  v25 = KernelPackageCallValidatorWorkers::CallValidator<long (*_SECPKG_KERNEL_FUNCTION_TABLE::*)(unsigned __int64,unsigned __int64 *),8>::InvokeById(
          *a3,
          a3[1],
          (char *)&v41 + 8);
  v5 = v25;
  if ( v25 == -1073741816 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0 )
      WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 3), v26, v27, a3[1]);
    v5 = 0;
  }
  else if ( v25 < 0 )
  {
    goto LABEL_4;
  }
  *(_QWORD *)&v41 = *a3;
LABEL_4:
  if ( v5 < 0 )
    goto LABEL_3;
  if ( v5 != 590627 )
  {
LABEL_6:
    v6 = 0;
    if ( v5 != -2146893054 )
      v6 = v5;
    if ( v6 < 0 || !*((_QWORD *)&v41 + 1) )
      return (unsigned int)v6;
    if ( !a1 )
      return (unsigned int)SspipDeleteSecurityContext(&v41);
    a1[2].HighPart = 590696;
    a1[28].QuadPart = (LONGLONG)DeleteSecurityContextMarshalParams;
    a1[29].QuadPart = (LONGLONG)DeleteSecurityContextUnMarshalResponse;
    a1[5].QuadPart = (LONGLONG)&v41;
    a1[4].QuadPart = (LONGLONG)a1;
    v32 = 0;
    v34 = 0;
    TargetHandle = 0;
    v7 = a1->QuadPart != 0;
    PerformanceCounter = KeQueryPerformanceCounter(0);
    KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)v35);
    if ( !KsecddLsaStateRef::IsValid((KsecddLsaStateRef *)v35) )
    {
      v6 = -1073741058;
LABEL_33:
      KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)v35);
      return (unsigned int)v6;
    }
    v9 = KsecddLsaStateRef::operator _KSECDDLSASTATE *(v35);
    ExistingTokenHandle = 0;
    v6 = ZwOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, 0x200u, &ExistingTokenHandle);
    if ( v6 == -1073741700 )
      v6 = ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0xCu, 0x200u, &ExistingTokenHandle);
    if ( v6 >= 0 )
    {
      TokenInformation = 0;
      ReturnLength = 0;
      v6 = ZwQueryInformationToken(ExistingTokenHandle, TokenType, &TokenInformation, 4u, &ReturnLength);
      if ( v6 < 0 )
      {
        ZwClose(ExistingTokenHandle);
      }
      else
      {
        if ( TokenInformation == 2 )
        {
          v10 = ExistingTokenHandle;
LABEL_19:
          v6 = ZwDuplicateObject((HANDLE)0xFFFFFFFFFFFFFFFFLL, v10, *(HANDLE *)(v9 + 8), &TargetHandle, 0, 0, 3u);
          if ( v6 >= 0 )
          {
            v6 = ((__int64 (__fastcall *)(LARGE_INTEGER *, __int64 *, int *))a1[28].QuadPart)(a1, &v32, &v34);
            if ( v6 >= 0 )
            {
              a1[2].LowPart = 3;
              v11 = KeQueryPerformanceCounter(0);
              LowPart = a1[2].LowPart;
              a1[3] = v11;
              *(_DWORD *)(v32 + 8) = LowPart;
              *(_DWORD *)(v32 + 40) = v34;
              *(_QWORD *)(v32 + 32) = TargetHandle;
              *(_QWORD *)(v32 + 16) = (unsigned int)KsecSystemProcessId;
              CurrentThreadId = (unsigned int)PsGetCurrentThreadId();
              v14 = AsyncSspiHandleIoctlIpcResponse;
              if ( !v7 )
                v14 = 0;
              *(_QWORD *)(v32 + 24) = CurrentThreadId;
              v15 = v32;
              KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&ExistingTokenHandle);
              if ( KsecddLsaStateRef::IsValid((KsecddLsaStateRef *)&ExistingTokenHandle) )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 15, WPP_f9740104427135617d8c60794f45a901_Traceguids);
                v30 = (void *)KsecddLsaStateRef::operator _KSECDDLSASTATE *(&ExistingTokenHandle);
                v6 = PendingCallPush(v15, v14, a1, v30);
                if ( v6 >= 0 )
                {
                  v24 = KsecddLsaStateRef::operator _KSECDDLSASTATE *(&ExistingTokenHandle);
                  if ( *(_QWORD *)(v24 + 88) != v24 + 88 )
                    HandlePendingIrps(v30);
                }
              }
              else
              {
                v6 = -1073741058;
              }
              KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&ExistingTokenHandle);
              if ( v6 >= 0 )
                goto LABEL_26;
            }
          }
          goto LABEL_48;
        }
        ObjectAttributes.SecurityQualityOfService = v40;
        v40[2] = 1;
        v40[0] = 12;
        v40[1] = 2;
        *(_QWORD *)&ObjectAttributes.Length = 48;
        *(_QWORD *)&ObjectAttributes.Attributes = 512;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.ObjectName = 0;
        ObjectAttributes.SecurityDescriptor = 0;
        SourceHandle = 0;
        v6 = ZwDuplicateToken(ExistingTokenHandle, 0xCu, &ObjectAttributes, 0, TokenImpersonation, &SourceHandle);
        ZwClose(ExistingTokenHandle);
        if ( v6 >= 0 )
        {
          v10 = SourceHandle;
          ExistingTokenHandle = SourceHandle;
          goto LABEL_19;
        }
      }
    }
LABEL_48:
    if ( TargetHandle )
    {
      v28 = KsecddLsaStateRef::operator _KSECDDLSASTATE *(v35);
      ZwDuplicateObject(*(HANDLE *)(v28 + 8), v29, 0, 0, 0, 0, 1u);
    }
LABEL_26:
    if ( !v7 )
    {
      v16 = a1[3];
      KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&ExistingTokenHandle);
      if ( KsecddLsaStateRef::IsValid((KsecddLsaStateRef *)&ExistingTokenHandle) )
      {
        KeGetCurrentProcessorNumberEx(0);
        v18 = *(_QWORD *)(KsecddLsaStateRef::operator _KSECDDLSASTATE *(&ExistingTokenHandle) + 312);
        v19 = (volatile signed __int64 *)(v18 + v17 + 112);
        if ( v19 )
        {
          v20 = (volatile signed __int64 *)(v18 + v17 + 120);
          if ( v20 )
          {
            v21 = (volatile signed __int64 *)(v18 + v17 + 128);
            if ( v21 )
            {
              v22 = KeQueryPerformanceCounter(0);
              _InterlockedIncrement64(v19);
              _InterlockedAdd64(v20, v22.QuadPart - PerformanceCounter.QuadPart);
              _InterlockedAdd64(v21, v22.QuadPart - v16.QuadPart);
            }
          }
        }
      }
      KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&ExistingTokenHandle);
      a1[2].HighPart = v6;
    }
    goto LABEL_33;
  }
  return 0;
}

```

## disassembly

```asm
0x180025db0  push    rbp
0x180025db2  push    rbx
0x180025db3  push    rsi
0x180025db4  push    r12
0x180025db6  push    r13
0x180025db8  lea     rbp, [rsp-37h]
0x180025dbd  sub     rsp, 0E0h
0x180025dc4  mov     rax, cs:__security_cookie
0x180025dcb  xor     rax, rsp
0x180025dce  mov     [rbp+57h+var_38], rax
0x180025dd2  xor     r13d, r13d
0x180025dd5  lea     r12, WPP_GLOBAL_Control
0x180025ddc  xorps   xmm0, xmm0
0x180025ddf  mov     rbx, r8
0x180025de2  mov     rsi, rcx
0x180025de5  movups  [rbp+57h+var_48], xmm0
0x180025de9  test    r8, r8
0x180025dec  jnz     loc_180026209
0x180025df2  mov     ecx, 80090301h
0x180025df7  movups  xmm0, xmmword ptr [rbx]
0x180025dfa  movups  [rbp+57h+var_48], xmm0
0x180025dfe  jmp     short loc_180025E10
0x180025e00  test    ecx, ecx
0x180025e02  js      short loc_180025DF7
0x180025e04  cmp     ecx, 90323h
0x180025e0a  jz      loc_1800261D5
0x180025e10  mov     [rsp+100h+arg_8], rdi
0x180025e18  cmp     ecx, 80090302h
0x180025e1e  mov     edi, r13d
0x180025e21  cmovnz  edi, ecx
0x180025e24  test    edi, edi
0x180025e26  js      loc_1800261A8
0x180025e2c  cmp     qword ptr [rbp+57h+var_48+8], r13
0x180025e30  jz      loc_1800261A8
0x180025e36  test    rsi, rsi
0x180025e39  jz      loc_1800261D9
0x180025e3f  lea     rax, DeleteSecurityContextMarshalParams
0x180025e46  mov     dword ptr [rsi+14h], 90368h
0x180025e4d  mov     [rsi+0E0h], rax
0x180025e54  lea     rax, DeleteSecurityContextUnMarshalResponse
0x180025e5b  mov     [rsi+0E8h], rax
0x180025e62  lea     rax, [rbp+57h+var_48]
0x180025e66  mov     [rsi+28h], rax
0x180025e6a  mov     [rsi+20h], rsi
0x180025e6e  mov     [rsp+100h+var_30], r15
0x180025e76  mov     [rbp+57h+var_B8], r13
0x180025e7a  mov     [rbp+57h+var_AC], r13d
0x180025e7e  mov     [rbp+57h+TargetHandle], r13
0x180025e82  cmp     [rsi], r13
0x180025e85  jz      loc_18002625B
0x180025e8b  mov     r15b, 1
0x180025e8e  xor     ecx, ecx; PerformanceFrequency
0x180025e90  call    cs:__imp_KeQueryPerformanceCounter
0x180025e97  nop     dword ptr [rax+rax+00h]
0x180025e9c  lea     rcx, [rbp+57h+var_A8]; this
0x180025ea0  mov     rbx, rax
0x180025ea3  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180025ea8  lea     rcx, [rbp+57h+var_A8]; this
0x180025eac  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x180025eb1  test    al, al
0x180025eb3  jz      loc_1800261CE
0x180025eb9  lea     rcx, [rbp+57h+var_A8]
0x180025ebd  mov     [rsp+100h+var_28], r14
0x180025ec5  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x180025eca  mov     r14, rax
0x180025ecd  mov     [rbp+57h+ExistingTokenHandle], r13
0x180025ed1  lea     rax, [rbp+57h+ExistingTokenHandle]
0x180025ed5  mov     r9d, 200h; HandleAttributes
0x180025edb  mov     r8b, 1; OpenAsSelf
0x180025ede  mov     [rsp+100h+TokenHandle], rax; TokenHandle
0x180025ee3  mov     edx, 0Ch; DesiredAccess
0x180025ee8  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180025eef  call    cs:__imp_ZwOpenThreadTokenEx
0x180025ef6  nop     dword ptr [rax+rax+00h]
0x180025efb  mov     edi, eax
0x180025efd  cmp     eax, 0C000007Ch
0x180025f02  jnz     short loc_180025F28
0x180025f04  lea     r9, [rbp+57h+ExistingTokenHandle]; TokenHandle
0x180025f08  mov     edx, 0Ch; DesiredAccess
0x180025f0d  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180025f14  mov     r8d, 200h; HandleAttributes
0x180025f1a  call    cs:__imp_ZwOpenProcessTokenEx
0x180025f21  nop     dword ptr [rax+rax+00h]
0x180025f26  mov     edi, eax
0x180025f28  test    edi, edi
0x180025f2a  js      loc_180026273
0x180025f30  mov     rcx, [rbp+57h+ExistingTokenHandle]; TokenHandle
0x180025f34  lea     rax, [rbp+57h+ReturnLength]
0x180025f38  mov     r9d, 4; TokenInformationLength
0x180025f3e  mov     [rsp+100h+TokenHandle], rax; ReturnLength
0x180025f43  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180025f47  mov     [rbp+57h+TokenInformation], r13d
0x180025f4b  mov     edx, 8; TokenInformationClass
0x180025f50  mov     [rbp+57h+ReturnLength], r13d
0x180025f54  call    cs:__imp_ZwQueryInformationToken
0x180025f5b  nop     dword ptr [rax+rax+00h]
0x180025f60  mov     edi, eax
0x180025f62  test    eax, eax
0x180025f64  js      loc_180026263
0x180025f6a  cmp     [rbp+57h+TokenInformation], 2
0x180025f6e  jz      loc_1800262B6
0x180025f74  mov     rcx, [rbp+57h+ExistingTokenHandle]; ExistingTokenHandle
0x180025f78  lea     rax, [rbp+57h+var_58]
0x180025f7c  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x180025f80  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180025f84  lea     rax, [rbp+57h+SourceHandle]
0x180025f88  mov     [rbp+57h+var_50], 1
0x180025f8f  mov     [rsp+100h+NewTokenHandle], rax; NewTokenHandle
0x180025f94  xor     r9d, r9d; EffectiveOnly
0x180025f97  mov     edx, 0Ch; DesiredAccess
0x180025f9c  mov     dword ptr [rsp+100h+TokenHandle], 2; TokenType
0x180025fa4  mov     [rbp+57h+var_58], 0Ch
0x180025fab  mov     [rbp+57h+var_54], 2
0x180025fb2  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180025fba  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x180025fc2  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x180025fc6  mov     [rbp+57h+ObjectAttributes.ObjectName], r13
0x180025fca  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r13
0x180025fce  mov     [rbp+57h+SourceHandle], r13
0x180025fd2  call    cs:__imp_ZwDuplicateToken
0x180025fd9  nop     dword ptr [rax+rax+00h]
0x180025fde  mov     rcx, [rbp+57h+ExistingTokenHandle]; Handle
0x180025fe2  mov     edi, eax
0x180025fe4  call    cs:__imp_ZwClose
0x180025feb  nop     dword ptr [rax+rax+00h]
0x180025ff0  test    edi, edi
0x180025ff2  js      loc_180026273
0x180025ff8  mov     rdx, [rbp+57h+SourceHandle]; SourceHandle
0x180025ffc  mov     [rbp+57h+ExistingTokenHandle], rdx
0x180026000  mov     r8, [r14+8]; TargetProcessHandle
0x180026004  lea     r9, [rbp+57h+TargetHandle]; TargetHandle
0x180026008  mov     [rsp+100h+Options], 3; Options
0x180026010  mov     rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x180026017  mov     dword ptr [rsp+100h+NewTokenHandle], r13d; HandleAttributes
0x18002601c  mov     dword ptr [rsp+100h+TokenHandle], r13d; DesiredAccess
0x180026021  call    cs:__imp_ZwDuplicateObject
0x180026028  nop     dword ptr [rax+rax+00h]
0x18002602d  mov     edi, eax
0x18002602f  test    eax, eax
0x180026031  js      loc_180026273
0x180026037  mov     rax, [rsi+0E0h]
0x18002603e  lea     r8, [rbp+57h+var_AC]
0x180026042  lea     rdx, [rbp+57h+var_B8]
0x180026046  mov     rcx, rsi
0x180026049  call    _guard_dispatch_icall
0x18002604e  mov     edi, eax
0x180026050  test    eax, eax
0x180026052  js      loc_180026273
0x180026058  xor     ecx, ecx; PerformanceFrequency
0x18002605a  mov     dword ptr [rsi+10h], 3
0x180026061  call    cs:__imp_KeQueryPerformanceCounter
0x180026068  nop     dword ptr [rax+rax+00h]
0x18002606d  mov     ecx, [rsi+10h]
0x180026070  mov     [rsi+18h], rax
0x180026074  mov     rax, [rbp+57h+var_B8]
0x180026078  mov     [rax+8], ecx
0x18002607b  mov     rax, [rbp+57h+var_B8]
0x18002607f  mov     ecx, [rbp+57h+var_AC]
0x180026082  mov     [rax+28h], ecx
0x180026085  mov     rcx, [rbp+57h+var_B8]
0x180026089  mov     rax, [rbp+57h+TargetHandle]
0x18002608d  mov     [rcx+20h], rax
0x180026091  mov     rax, [rbp+57h+var_B8]
0x180026095  mov     ecx, cs:KsecSystemProcessId
0x18002609b  mov     [rax+10h], rcx
0x18002609f  call    cs:__imp_PsGetCurrentThreadId
0x1800260a6  nop     dword ptr [rax+rax+00h]
0x1800260ab  mov     ecx, eax
0x1800260ad  test    r15b, r15b
0x1800260b0  mov     rax, [rbp+57h+var_B8]
0x1800260b4  lea     rdi, AsyncSspiHandleIoctlIpcResponse
0x1800260bb  cmovz   rdi, r13
0x1800260bf  mov     [rax+18h], rcx
0x1800260c3  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x1800260c7  mov     r14, [rbp+57h+var_B8]
0x1800260cb  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x1800260d0  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x1800260d4  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x1800260d9  test    al, al
0x1800260db  jnz     loc_1800262BF
0x1800260e1  mov     edi, 0C00002FEh
0x1800260e6  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x1800260ea  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x1800260ef  test    edi, edi
0x1800260f1  js      loc_180026273
0x1800260f7  test    r15b, r15b
0x1800260fa  jnz     loc_18002618F
0x180026100  mov     r13, [rsi+18h]
0x180026104  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x180026108  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x18002610d  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x180026111  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x180026116  test    al, al
0x180026118  jz      short loc_180026183
0x18002611a  xor     ecx, ecx; ProcNumber
0x18002611c  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x180026123  nop     dword ptr [rax+rax+00h]
0x180026128  mov     eax, eax
0x18002612a  lea     rcx, [rbp+57h+ExistingTokenHandle]
0x18002612e  imul    rdx, rax, 88h
0x180026135  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x18002613a  lea     r12, [rdx+70h]
0x18002613e  mov     rcx, [rax+138h]
0x180026145  add     r12, rcx
0x180026148  jz      short loc_180026183
0x18002614a  lea     r14, [rdx+78h]
0x18002614e  add     r14, rcx
0x180026151  jz      short loc_180026183
0x180026153  lea     r15, [rdx+80h]
0x18002615a  add     r15, rcx
0x18002615d  jz      short loc_180026183
0x18002615f  xor     ecx, ecx; PerformanceFrequency
0x180026161  call    cs:__imp_KeQueryPerformanceCounter
0x180026168  nop     dword ptr [rax+rax+00h]
0x18002616d  lock inc qword ptr [r12]
0x180026172  mov     rcx, rax
0x180026175  sub     rcx, rbx
0x180026178  lock add [r14], rcx
0x18002617c  sub     rax, r13
0x18002617f  lock add [r15], rax
0x180026183  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x180026187  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18002618c  mov     [rsi+14h], edi
0x18002618f  mov     r14, [rsp+100h+var_28]
0x180026197  lea     rcx, [rbp+57h+var_A8]; this
0x18002619b  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x1800261a0  mov     r15, [rsp+100h+var_30]
0x1800261a8  mov     eax, edi
0x1800261aa  mov     rdi, [rsp+100h+arg_8]
0x1800261b2  mov     rcx, [rbp+57h+var_38]
0x1800261b6  xor     rcx, rsp; StackCookie
0x1800261b9  call    __security_check_cookie
0x1800261be  add     rsp, 0E0h
0x1800261c5  pop     r13
0x1800261c7  pop     r12
0x1800261c9  pop     rsi
0x1800261ca  pop     rbx
0x1800261cb  pop     rbp
0x1800261cc  retn
0x1800261ce  mov     edi, 0C00002FEh
0x1800261d3  jmp     short loc_180026197
0x1800261d5  xor     eax, eax
0x1800261d7  jmp     short loc_1800261B2
0x1800261d9  lea     rcx, [rbp+57h+var_48]
0x1800261dd  call    SspipDeleteSecurityContext
0x1800261e2  mov     edi, eax
0x1800261e4  jmp     short loc_1800261A8
0x1800261e6  lea     rcx, [rbp+57h+ExistingTokenHandle]
0x1800261ea  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x1800261ef  add     rax, 58h ; 'X'
0x1800261f3  cmp     [rax], rax
0x1800261f6  jz      loc_1800260E6
0x1800261fc  mov     rcx, r12; InsertContext
0x1800261ff  call    HandlePendingIrps
0x180026204  jmp     loc_1800260E6
0x180026209  mov     rdx, [rbx+8]
0x18002620d  lea     r8, [rbp+57h+var_48+8]
0x180026211  mov     rcx, [rbx]
0x180026214  call    ?InvokeById@?$CallValidator@PEQ_SECPKG_KERNEL_FUNCTION_TABLE@@P6AJ_KPEA_K@Z$07@KernelPackageCallValidatorWorkers@@SAJ_K0PEA_K@Z; KernelPackageCallValidatorWorkers::CallValidator<long (*_SECPKG_KERNEL_FUNCTION_TABLE::*)(unsigned __int64,unsigned __int64 *),8>::InvokeById(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180026219  mov     ecx, eax
0x18002621b  cmp     eax, 0C0000008h
0x180026220  jnz     short loc_180026247
0x180026222  mov     rcx, cs:WPP_GLOBAL_Control
0x180026229  cmp     rcx, r12
0x18002622c  jz      short loc_180026242
0x18002622e  mov     eax, [rcx+2Ch]
0x180026231  test    al, 2
0x180026233  jz      short loc_180026242
0x180026235  mov     r9, [rbx+8]
0x180026239  mov     rcx, [rcx+18h]
0x18002623d  call    WPP_SF_P
0x180026242  mov     ecx, r13d
0x180026245  jmp     short loc_18002624F
0x180026247  test    eax, eax
0x180026249  js      loc_180025E00
0x18002624f  mov     rax, [rbx]
0x180026252  mov     qword ptr [rbp+57h+var_48], rax
0x180026256  jmp     loc_180025E00
0x18002625b  xor     r15b, r15b
0x18002625e  jmp     loc_180025E8E
0x180026263  mov     rcx, [rbp+57h+ExistingTokenHandle]; Handle
0x180026267  call    cs:__imp_ZwClose
0x18002626e  nop     dword ptr [rax+rax+00h]
0x180026273  mov     rdx, [rbp+57h+TargetHandle]
0x180026277  test    rdx, rdx
0x18002627a  jz      loc_1800260F7
0x180026280  lea     rcx, [rbp+57h+var_A8]
0x180026284  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x180026289  mov     [rsp+100h+Options], 1; Options
0x180026291  xor     r9d, r9d; TargetHandle
0x180026294  mov     dword ptr [rsp+100h+NewTokenHandle], r13d; HandleAttributes
0x180026299  xor     r8d, r8d; TargetProcessHandle
0x18002629c  mov     dword ptr [rsp+100h+TokenHandle], r13d; DesiredAccess
0x1800262a1  mov     rcx, [rax+8]; SourceProcessHandle
0x1800262a5  call    cs:__imp_ZwDuplicateObject
0x1800262ac  nop     dword ptr [rax+rax+00h]
0x1800262b1  jmp     loc_1800260F7
0x1800262b6  mov     rdx, [rbp+57h+ExistingTokenHandle]
0x1800262ba  jmp     loc_180026000
0x1800262bf  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
