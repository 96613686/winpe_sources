# DeleteSecurityContextInternal

- ea: `0x180025e00`
- end: `0x18002635c`
- name: `DeleteSecurityContextInternal`
- size: `1372`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180024910`
- `0x180025220`
- `0x180025db0`
- `0x180025dd0`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x180001f90`
- `0x180002820`
- `0x180003c38`
- `0x180007ba8`
- `0x18000c400`
- `0x18000f900`
- `0x1800108a0`
- `0x180010980`
- `0x180025e00`
- `0x180026580`
- `0x1800298e0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1800260ef`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1800260ef`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x180025f3f`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x180025f3f`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x180025f6a`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x180025f6a`
- `ntoskrnl!ZwQueryInformationToken` at `0x180025fa4`
- `ntoskrnl!ZwQueryInformationToken` at `0x180025fa4`
- `ntoskrnl!ZwDuplicateToken` at `0x180026022`
- `ntoskrnl!ZwDuplicateToken` at `0x180026022`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x18002616c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x18002616c`
- `ntoskrnl!ZwClose` at `0x180026034`
- `ntoskrnl!ZwClose` at `0x1800262b7`
- `ntoskrnl!ZwClose` at `0x180026034`
- `ntoskrnl!ZwClose` at `0x1800262b7`
- `ntoskrnl!ZwDuplicateObject` at `0x180026071`
- `ntoskrnl!ZwDuplicateObject` at `0x1800262f5`
- `ntoskrnl!ZwDuplicateObject` at `0x180026071`
- `ntoskrnl!ZwDuplicateObject` at `0x1800262f5`
- `HAL!KeQueryPerformanceCounter` at `0x180025ee0`
- `HAL!KeQueryPerformanceCounter` at `0x1800260b1`
- `HAL!KeQueryPerformanceCounter` at `0x1800261b1`
- `HAL!KeQueryPerformanceCounter` at `0x180025ee0`
- `HAL!KeQueryPerformanceCounter` at `0x1800260b1`
- `HAL!KeQueryPerformanceCounter` at `0x1800261b1`

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
  __int64 (__fastcall *v14)(int, int, int, int, __int64); // rdi
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
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 15, &WPP_f9740104427135617d8c60794f45a901_Traceguids);
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
0x180025e00  push    rbp
0x180025e02  push    rbx
0x180025e03  push    rsi
0x180025e04  push    r12
0x180025e06  push    r13
0x180025e08  lea     rbp, [rsp-37h]
0x180025e0d  sub     rsp, 0E0h
0x180025e14  mov     rax, cs:__security_cookie
0x180025e1b  xor     rax, rsp
0x180025e1e  mov     [rbp+57h+var_38], rax
0x180025e22  xor     r13d, r13d
0x180025e25  lea     r12, WPP_GLOBAL_Control
0x180025e2c  xorps   xmm0, xmm0
0x180025e2f  mov     rbx, r8
0x180025e32  mov     rsi, rcx
0x180025e35  movups  [rbp+57h+var_48], xmm0
0x180025e39  test    r8, r8
0x180025e3c  jnz     loc_180026259
0x180025e42  mov     ecx, 80090301h
0x180025e47  movups  xmm0, xmmword ptr [rbx]
0x180025e4a  movups  [rbp+57h+var_48], xmm0
0x180025e4e  jmp     short loc_180025E60
0x180025e50  test    ecx, ecx
0x180025e52  js      short loc_180025E47
0x180025e54  cmp     ecx, 90323h
0x180025e5a  jz      loc_180026225
0x180025e60  mov     [rsp+100h+arg_8], rdi
0x180025e68  cmp     ecx, 80090302h
0x180025e6e  mov     edi, r13d
0x180025e71  cmovnz  edi, ecx
0x180025e74  test    edi, edi
0x180025e76  js      loc_1800261F8
0x180025e7c  cmp     qword ptr [rbp+57h+var_48+8], r13
0x180025e80  jz      loc_1800261F8
0x180025e86  test    rsi, rsi
0x180025e89  jz      loc_180026229
0x180025e8f  lea     rax, DeleteSecurityContextMarshalParams
0x180025e96  mov     dword ptr [rsi+14h], 90368h
0x180025e9d  mov     [rsi+0E0h], rax
0x180025ea4  lea     rax, DeleteSecurityContextUnMarshalResponse
0x180025eab  mov     [rsi+0E8h], rax
0x180025eb2  lea     rax, [rbp+57h+var_48]
0x180025eb6  mov     [rsi+28h], rax
0x180025eba  mov     [rsi+20h], rsi
0x180025ebe  mov     [rsp+100h+var_30], r15
0x180025ec6  mov     [rbp+57h+var_B8], r13
0x180025eca  mov     [rbp+57h+var_AC], r13d
0x180025ece  mov     [rbp+57h+TargetHandle], r13
0x180025ed2  cmp     [rsi], r13
0x180025ed5  jz      loc_1800262AB
0x180025edb  mov     r15b, 1
0x180025ede  xor     ecx, ecx; PerformanceFrequency
0x180025ee0  call    cs:__imp_KeQueryPerformanceCounter
0x180025ee7  nop     dword ptr [rax+rax+00h]
0x180025eec  lea     rcx, [rbp+57h+var_A8]; this
0x180025ef0  mov     rbx, rax
0x180025ef3  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180025ef8  lea     rcx, [rbp+57h+var_A8]; this
0x180025efc  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x180025f01  test    al, al
0x180025f03  jz      loc_18002621E
0x180025f09  lea     rcx, [rbp+57h+var_A8]
0x180025f0d  mov     [rsp+100h+var_28], r14
0x180025f15  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x180025f1a  mov     r14, rax
0x180025f1d  mov     [rbp+57h+ExistingTokenHandle], r13
0x180025f21  lea     rax, [rbp+57h+ExistingTokenHandle]
0x180025f25  mov     r9d, 200h; HandleAttributes
0x180025f2b  mov     r8b, 1; OpenAsSelf
0x180025f2e  mov     [rsp+100h+TokenHandle], rax; TokenHandle
0x180025f33  mov     edx, 0Ch; DesiredAccess
0x180025f38  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180025f3f  call    cs:__imp_ZwOpenThreadTokenEx
0x180025f46  nop     dword ptr [rax+rax+00h]
0x180025f4b  mov     edi, eax
0x180025f4d  cmp     eax, 0C000007Ch
0x180025f52  jnz     short loc_180025F78
0x180025f54  lea     r9, [rbp+57h+ExistingTokenHandle]; TokenHandle
0x180025f58  mov     edx, 0Ch; DesiredAccess
0x180025f5d  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180025f64  mov     r8d, 200h; HandleAttributes
0x180025f6a  call    cs:__imp_ZwOpenProcessTokenEx
0x180025f71  nop     dword ptr [rax+rax+00h]
0x180025f76  mov     edi, eax
0x180025f78  test    edi, edi
0x180025f7a  js      loc_1800262C3
0x180025f80  mov     rcx, [rbp+57h+ExistingTokenHandle]; TokenHandle
0x180025f84  lea     rax, [rbp+57h+ReturnLength]
0x180025f88  mov     r9d, 4; TokenInformationLength
0x180025f8e  mov     [rsp+100h+TokenHandle], rax; ReturnLength
0x180025f93  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180025f97  mov     [rbp+57h+TokenInformation], r13d
0x180025f9b  mov     edx, 8; TokenInformationClass
0x180025fa0  mov     [rbp+57h+ReturnLength], r13d
0x180025fa4  call    cs:__imp_ZwQueryInformationToken
0x180025fab  nop     dword ptr [rax+rax+00h]
0x180025fb0  mov     edi, eax
0x180025fb2  test    eax, eax
0x180025fb4  js      loc_1800262B3
0x180025fba  cmp     [rbp+57h+TokenInformation], 2
0x180025fbe  jz      loc_180026306
0x180025fc4  mov     rcx, [rbp+57h+ExistingTokenHandle]; ExistingTokenHandle
0x180025fc8  lea     rax, [rbp+57h+var_58]
0x180025fcc  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x180025fd0  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180025fd4  lea     rax, [rbp+57h+SourceHandle]
0x180025fd8  mov     [rbp+57h+var_50], 1
0x180025fdf  mov     [rsp+100h+NewTokenHandle], rax; NewTokenHandle
0x180025fe4  xor     r9d, r9d; EffectiveOnly
0x180025fe7  mov     edx, 0Ch; DesiredAccess
0x180025fec  mov     dword ptr [rsp+100h+TokenHandle], 2; TokenType
0x180025ff4  mov     [rbp+57h+var_58], 0Ch
0x180025ffb  mov     [rbp+57h+var_54], 2
0x180026002  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18002600a  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x180026012  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x180026016  mov     [rbp+57h+ObjectAttributes.ObjectName], r13
0x18002601a  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r13
0x18002601e  mov     [rbp+57h+SourceHandle], r13
0x180026022  call    cs:__imp_ZwDuplicateToken
0x180026029  nop     dword ptr [rax+rax+00h]
0x18002602e  mov     rcx, [rbp+57h+ExistingTokenHandle]; Handle
0x180026032  mov     edi, eax
0x180026034  call    cs:__imp_ZwClose
0x18002603b  nop     dword ptr [rax+rax+00h]
0x180026040  test    edi, edi
0x180026042  js      loc_1800262C3
0x180026048  mov     rdx, [rbp+57h+SourceHandle]; SourceHandle
0x18002604c  mov     [rbp+57h+ExistingTokenHandle], rdx
0x180026050  mov     r8, [r14+8]; TargetProcessHandle
0x180026054  lea     r9, [rbp+57h+TargetHandle]; TargetHandle
0x180026058  mov     [rsp+100h+Options], 3; Options
0x180026060  mov     rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x180026067  mov     dword ptr [rsp+100h+NewTokenHandle], r13d; HandleAttributes
0x18002606c  mov     dword ptr [rsp+100h+TokenHandle], r13d; DesiredAccess
0x180026071  call    cs:__imp_ZwDuplicateObject
0x180026078  nop     dword ptr [rax+rax+00h]
0x18002607d  mov     edi, eax
0x18002607f  test    eax, eax
0x180026081  js      loc_1800262C3
0x180026087  mov     rax, [rsi+0E0h]
0x18002608e  lea     r8, [rbp+57h+var_AC]
0x180026092  lea     rdx, [rbp+57h+var_B8]
0x180026096  mov     rcx, rsi
0x180026099  call    _guard_dispatch_icall
0x18002609e  mov     edi, eax
0x1800260a0  test    eax, eax
0x1800260a2  js      loc_1800262C3
0x1800260a8  xor     ecx, ecx; PerformanceFrequency
0x1800260aa  mov     dword ptr [rsi+10h], 3
0x1800260b1  call    cs:__imp_KeQueryPerformanceCounter
0x1800260b8  nop     dword ptr [rax+rax+00h]
0x1800260bd  mov     ecx, [rsi+10h]
0x1800260c0  mov     [rsi+18h], rax
0x1800260c4  mov     rax, [rbp+57h+var_B8]
0x1800260c8  mov     [rax+8], ecx
0x1800260cb  mov     rax, [rbp+57h+var_B8]
0x1800260cf  mov     ecx, [rbp+57h+var_AC]
0x1800260d2  mov     [rax+28h], ecx
0x1800260d5  mov     rcx, [rbp+57h+var_B8]
0x1800260d9  mov     rax, [rbp+57h+TargetHandle]
0x1800260dd  mov     [rcx+20h], rax
0x1800260e1  mov     rax, [rbp+57h+var_B8]
0x1800260e5  mov     ecx, cs:KsecSystemProcessId
0x1800260eb  mov     [rax+10h], rcx
0x1800260ef  call    cs:__imp_PsGetCurrentThreadId
0x1800260f6  nop     dword ptr [rax+rax+00h]
0x1800260fb  mov     ecx, eax
0x1800260fd  test    r15b, r15b
0x180026100  mov     rax, [rbp+57h+var_B8]
0x180026104  lea     rdi, AsyncSspiHandleIoctlIpcResponse
0x18002610b  cmovz   rdi, r13
0x18002610f  mov     [rax+18h], rcx
0x180026113  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x180026117  mov     r14, [rbp+57h+var_B8]
0x18002611b  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180026120  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x180026124  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x180026129  test    al, al
0x18002612b  jnz     loc_18002630F
0x180026131  mov     edi, 0C00002FEh
0x180026136  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x18002613a  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18002613f  test    edi, edi
0x180026141  js      loc_1800262C3
0x180026147  test    r15b, r15b
0x18002614a  jnz     loc_1800261DF
0x180026150  mov     r13, [rsi+18h]
0x180026154  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x180026158  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x18002615d  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x180026161  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x180026166  test    al, al
0x180026168  jz      short loc_1800261D3
0x18002616a  xor     ecx, ecx; ProcNumber
0x18002616c  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x180026173  nop     dword ptr [rax+rax+00h]
0x180026178  mov     eax, eax
0x18002617a  lea     rcx, [rbp+57h+ExistingTokenHandle]
0x18002617e  imul    rdx, rax, 88h
0x180026185  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x18002618a  lea     r12, [rdx+70h]
0x18002618e  mov     rcx, [rax+138h]
0x180026195  add     r12, rcx
0x180026198  jz      short loc_1800261D3
0x18002619a  lea     r14, [rdx+78h]
0x18002619e  add     r14, rcx
0x1800261a1  jz      short loc_1800261D3
0x1800261a3  lea     r15, [rdx+80h]
0x1800261aa  add     r15, rcx
0x1800261ad  jz      short loc_1800261D3
0x1800261af  xor     ecx, ecx; PerformanceFrequency
0x1800261b1  call    cs:__imp_KeQueryPerformanceCounter
0x1800261b8  nop     dword ptr [rax+rax+00h]
0x1800261bd  lock inc qword ptr [r12]
0x1800261c2  mov     rcx, rax
0x1800261c5  sub     rcx, rbx
0x1800261c8  lock add [r14], rcx
0x1800261cc  sub     rax, r13
0x1800261cf  lock add [r15], rax
0x1800261d3  lea     rcx, [rbp+57h+ExistingTokenHandle]; this
0x1800261d7  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x1800261dc  mov     [rsi+14h], edi
0x1800261df  mov     r14, [rsp+100h+var_28]
0x1800261e7  lea     rcx, [rbp+57h+var_A8]; this
0x1800261eb  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x1800261f0  mov     r15, [rsp+100h+var_30]
0x1800261f8  mov     eax, edi
0x1800261fa  mov     rdi, [rsp+100h+arg_8]
0x180026202  mov     rcx, [rbp+57h+var_38]
0x180026206  xor     rcx, rsp; StackCookie
0x180026209  call    __security_check_cookie
0x18002620e  add     rsp, 0E0h
0x180026215  pop     r13
0x180026217  pop     r12
0x180026219  pop     rsi
0x18002621a  pop     rbx
0x18002621b  pop     rbp
0x18002621c  retn
0x18002621e  mov     edi, 0C00002FEh
0x180026223  jmp     short loc_1800261E7
0x180026225  xor     eax, eax
0x180026227  jmp     short loc_180026202
0x180026229  lea     rcx, [rbp+57h+var_48]
0x18002622d  call    SspipDeleteSecurityContext
0x180026232  mov     edi, eax
0x180026234  jmp     short loc_1800261F8
0x180026236  lea     rcx, [rbp+57h+ExistingTokenHandle]
0x18002623a  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x18002623f  add     rax, 58h ; 'X'
0x180026243  cmp     [rax], rax
0x180026246  jz      loc_180026136
0x18002624c  mov     rcx, r12; InsertContext
0x18002624f  call    HandlePendingIrps
0x180026254  jmp     loc_180026136
0x180026259  mov     rdx, [rbx+8]
0x18002625d  lea     r8, [rbp+57h+var_48+8]
0x180026261  mov     rcx, [rbx]
0x180026264  call    ?InvokeById@?$CallValidator@PEQ_SECPKG_KERNEL_FUNCTION_TABLE@@P6AJ_KPEA_K@Z$07@KernelPackageCallValidatorWorkers@@SAJ_K0PEA_K@Z; KernelPackageCallValidatorWorkers::CallValidator<long (*_SECPKG_KERNEL_FUNCTION_TABLE::*)(unsigned __int64,unsigned __int64 *),8>::InvokeById(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180026269  mov     ecx, eax
0x18002626b  cmp     eax, 0C0000008h
0x180026270  jnz     short loc_180026297
0x180026272  mov     rcx, cs:WPP_GLOBAL_Control
0x180026279  cmp     rcx, r12
0x18002627c  jz      short loc_180026292
0x18002627e  mov     eax, [rcx+2Ch]
0x180026281  test    al, 2
0x180026283  jz      short loc_180026292
0x180026285  mov     r9, [rbx+8]
0x180026289  mov     rcx, [rcx+18h]
0x18002628d  call    WPP_SF_P
0x180026292  mov     ecx, r13d
0x180026295  jmp     short loc_18002629F
0x180026297  test    eax, eax
0x180026299  js      loc_180025E50
0x18002629f  mov     rax, [rbx]
0x1800262a2  mov     qword ptr [rbp+57h+var_48], rax
0x1800262a6  jmp     loc_180025E50
0x1800262ab  xor     r15b, r15b
0x1800262ae  jmp     loc_180025EDE
0x1800262b3  mov     rcx, [rbp+57h+ExistingTokenHandle]; Handle
0x1800262b7  call    cs:__imp_ZwClose
0x1800262be  nop     dword ptr [rax+rax+00h]
0x1800262c3  mov     rdx, [rbp+57h+TargetHandle]
0x1800262c7  test    rdx, rdx
0x1800262ca  jz      loc_180026147
0x1800262d0  lea     rcx, [rbp+57h+var_A8]
0x1800262d4  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x1800262d9  mov     [rsp+100h+Options], 1; Options
0x1800262e1  xor     r9d, r9d; TargetHandle
0x1800262e4  mov     dword ptr [rsp+100h+NewTokenHandle], r13d; HandleAttributes
0x1800262e9  xor     r8d, r8d; TargetProcessHandle
0x1800262ec  mov     dword ptr [rsp+100h+TokenHandle], r13d; DesiredAccess
0x1800262f1  mov     rcx, [rax+8]; SourceProcessHandle
0x1800262f5  call    cs:__imp_ZwDuplicateObject
0x1800262fc  nop     dword ptr [rax+rax+00h]
0x180026301  jmp     loc_180026147
0x180026306  mov     rdx, [rbp+57h+ExistingTokenHandle]
0x18002630a  jmp     loc_180026050
0x18002630f  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
