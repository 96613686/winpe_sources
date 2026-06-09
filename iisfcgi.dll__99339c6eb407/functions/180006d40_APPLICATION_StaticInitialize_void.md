# APPLICATION::StaticInitialize(void)

- ea: `0x180006d40`
- end: `0x180006edd`
- name: `?StaticInitialize@APPLICATION@@SAJXZ`
- size: `413`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007e1c`

## callees

- `0x180006d40`
- `0x18000edde`
- `0x18000ee10`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006db3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006db3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006d99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006d99`
- `api-ms-win-core-job-l1-1-0!IsProcessInJob` at `0x180006da9`
- `api-ms-win-core-job-l1-1-0!IsProcessInJob` at `0x180006da9`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x180006e33`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x180006e33`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x180006e0c`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x180006e0c`
- `api-ms-win-core-job-l2-1-0!QueryInformationJobObject` at `0x180006df8`
- `api-ms-win-core-job-l2-1-0!QueryInformationJobObject` at `0x180006df8`

## pseudocode

```c
__int64 APPLICATION::StaticInitialize(void)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  int v2; // ebx
  HANDLE JobObjectW; // rax
  __int64 v4; // rcx
  WINBOOL Result; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v7; // [rsp+38h] [rbp-C8h] BYREF
  int JobObjectInformation; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v9[12]; // [rsp+44h] [rbp-BCh] BYREF
  int v10; // [rsp+50h] [rbp-B0h]
  int v11; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v12[12]; // [rsp+D4h] [rbp-2Ch] BYREF
  int v13; // [rsp+E0h] [rbp-20h]

  Result = 0;
  JobObjectInformation = 0;
  memset_0(v9, 0, 0x8Cu);
  v11 = 0;
  memset_0(v12, 0, 0x8Cu);
  CurrentProcess = GetCurrentProcess();
  if ( !IsProcessInJob(CurrentProcess, 0, &Result) )
    goto LABEL_2;
  if ( Result != 1 )
    goto LABEL_18;
  if ( !QueryInformationJobObject(0, JobObjectExtendedLimitInformation, &JobObjectInformation, 0x90u, 0) )
    goto LABEL_2;
  if ( (v10 & 0x2000) == 0 )
  {
LABEL_18:
    JobObjectW = CreateJobObjectW(0, 0);
    APPLICATION::sm_hJobObject = JobObjectW;
    if ( !JobObjectW
      || (v13 = 0x2000, !SetInformationJobObject(JobObjectW, JobObjectExtendedLimitInformation, &v11, 0x90u)) )
    {
LABEL_2:
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      return (unsigned int)v2;
    }
  }
  v7 = 0;
  v2 = (*(__int64 (__fastcall **)(struct IHttpServer *, __int64 *))(*(_QWORD *)g_pGlobalInfo + 160LL))(
         g_pGlobalInfo,
         &v7);
  if ( v2 < 0
    || (v2 = (*(__int64 (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v7 + 16LL))(
               v7,
               6,
               &APPLICATION::sm_IdleTimeoutAction),
        v2 < 0) )
  {
    v4 = v7;
  }
  else
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
    v4 = 0;
    v7 = 0;
  }
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180006d40  mov     [rsp-8+arg_0], rbx
0x180006d45  push    rbp
0x180006d46  lea     rbp, [rsp-70h]
0x180006d4b  sub     rsp, 170h
0x180006d52  mov     rax, cs:__security_cookie
0x180006d59  xor     rax, rsp
0x180006d5c  mov     [rbp+70h+var_10], rax
0x180006d60  mov     ebx, 8Ch
0x180006d65  mov     [rsp+170h+Result], 0
0x180006d6d  mov     r8d, ebx; Size
0x180006d70  mov     [rsp+170h+JobObjectInformation], 0
0x180006d78  xor     edx, edx; Val
0x180006d7a  lea     rcx, [rsp+170h+var_12C]; void *
0x180006d7f  call    memset_0
0x180006d84  mov     r8d, ebx; Size
0x180006d87  mov     [rbp+70h+var_A0], 0
0x180006d8e  xor     edx, edx; Val
0x180006d90  lea     rcx, [rbp+70h+var_9C]; void *
0x180006d94  call    memset_0
0x180006d99  call    cs:__imp_GetCurrentProcess
0x180006d9f  lea     r8, [rsp+170h+Result]; Result
0x180006da4  xor     edx, edx; JobHandle
0x180006da6  mov     rcx, rax; ProcessHandle
0x180006da9  call    cs:__imp_IsProcessInJob
0x180006daf  test    eax, eax
0x180006db1  jnz     short loc_180006DD1
0x180006db3  call    cs:__imp_GetLastError
0x180006db9  mov     ebx, eax
0x180006dbb  test    eax, eax
0x180006dbd  jle     loc_180006EBE
0x180006dc3  movzx   ebx, ax
0x180006dc6  or      ebx, 80070000h
0x180006dcc  jmp     loc_180006EBE
0x180006dd1  cmp     [rsp+170h+Result], 1
0x180006dd6  mov     ebx, 2000h
0x180006ddb  jnz     short loc_180006E08
0x180006ddd  mov     r9d, 90h; cbJobObjectInformationLength
0x180006de3  mov     [rsp+170h+lpReturnLength], 0; lpReturnLength
0x180006dec  lea     r8, [rsp+170h+JobObjectInformation]; lpJobObjectInformation
0x180006df1  mov     edx, 9; JobObjectInformationClass
0x180006df6  xor     ecx, ecx; hJob
0x180006df8  call    cs:__imp_QueryInformationJobObject
0x180006dfe  test    eax, eax
0x180006e00  jz      short loc_180006DB3
0x180006e02  test    [rsp+170h+var_120], ebx
0x180006e06  jnz     short loc_180006E41
0x180006e08  xor     edx, edx; lpName
0x180006e0a  xor     ecx, ecx; lpJobAttributes
0x180006e0c  call    cs:__imp_CreateJobObjectW
0x180006e12  mov     cs:?sm_hJobObject@APPLICATION@@0PEAXEA, rax; void * APPLICATION::sm_hJobObject
0x180006e19  test    rax, rax
0x180006e1c  jz      short loc_180006DB3
0x180006e1e  mov     r9d, 90h; cbJobObjectInformationLength
0x180006e24  mov     [rbp+70h+var_90], ebx
0x180006e27  lea     r8, [rbp+70h+var_A0]; lpJobObjectInformation
0x180006e2b  mov     edx, 9; JobObjectInformationClass
0x180006e30  mov     rcx, rax; hJob
0x180006e33  call    cs:__imp_SetInformationJobObject
0x180006e39  test    eax, eax
0x180006e3b  jz      loc_180006DB3
0x180006e41  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180006e48  lea     rdx, [rsp+170h+var_138]
0x180006e4d  mov     [rsp+170h+var_138], 0
0x180006e56  mov     rax, [rcx]
0x180006e59  mov     rax, [rax+0A0h]
0x180006e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e65  mov     ebx, eax
0x180006e67  test    eax, eax
0x180006e69  js      short loc_180006EA8
0x180006e6b  mov     rcx, [rsp+170h+var_138]
0x180006e70  lea     r8, ?sm_IdleTimeoutAction@APPLICATION@@0W4IdleTimeoutAction@@A; IdleTimeoutAction APPLICATION::sm_IdleTimeoutAction
0x180006e77  mov     edx, 6
0x180006e7c  mov     rax, [rcx]
0x180006e7f  mov     rax, [rax+10h]
0x180006e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e88  mov     ebx, eax
0x180006e8a  test    eax, eax
0x180006e8c  js      short loc_180006EA8
0x180006e8e  mov     rcx, [rsp+170h+var_138]
0x180006e93  mov     rax, [rcx]
0x180006e96  mov     rax, [rax+8]
0x180006e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e9f  xor     ecx, ecx
0x180006ea1  mov     [rsp+170h+var_138], rcx
0x180006ea6  jmp     short loc_180006EAD
0x180006ea8  mov     rcx, [rsp+170h+var_138]
0x180006ead  test    rcx, rcx
0x180006eb0  jz      short loc_180006EBE
0x180006eb2  mov     rdx, [rcx]
0x180006eb5  mov     rax, [rdx+8]
0x180006eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ebe  mov     eax, ebx
0x180006ec0  mov     rcx, [rbp+70h+var_10]
0x180006ec4  xor     rcx, rsp; StackCookie
0x180006ec7  call    __security_check_cookie
0x180006ecc  mov     rbx, [rsp+170h+arg_0]
0x180006ed4  add     rsp, 170h
0x180006edb  pop     rbp
0x180006edc  retn
```
