# JOB_OBJECT::Initialize(APP_POOL *,unsigned __int64)

- ea: `0x180034988`
- end: `0x180034c02`
- name: `?Initialize@JOB_OBJECT@@QEAAJPEAVAPP_POOL@@_K@Z`
- size: `634`
- prototype: `__int64 __fastcall(JOB_OBJECT *__hidden this, struct APP_POOL *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800181ac`

## callees

- `0x1800074b0`
- `0x180007b60`
- `0x180034988`
- `0x180035438`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034a69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034ad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034b67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034a69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034ad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034b67`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x180034aca`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x180034b5d`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x180034aca`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x180034b5d`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x180034a57`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x180034a57`
- `iisutil!PuDbgPrint` at `0x180034be4`
- `iisutil!PuDbgPrint` at `0x180034be4`
- `iisutil!PuDbgPrintError` at `0x180034a28`
- `iisutil!PuDbgPrintError` at `0x180034b1d`
- `iisutil!PuDbgPrintError` at `0x180034a28`
- `iisutil!PuDbgPrintError` at `0x180034b1d`

## string_xrefs

- `0x180034b16`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\work_queue.cxx`
- `0x180034af9`: `Binding a completion port to a job object failed\n`
- `0x180034b05`: `WORK_QUEUE::BindJobToCompletionPort`
- `0x1800349ed`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\job_object.cxx`
- `0x180034a05`: `Could not create a work item for the job object\n`
- `0x180034b30`: `Binding the job object to the completion port failed\n`

## pseudocode

```c
__int64 __fastcall JOB_OBJECT::Initialize(JOB_OBJECT *this, struct APP_POOL *a2, unsigned __int64 a3)
{
  WORK_ITEM **v6; // r14
  signed int BlankWorkItem; // ebx
  HANDLE JobObjectW; // rax
  signed int v9; // eax
  signed int LastError; // eax
  void *v11; // rcx
  signed int v12; // eax
  _QWORD JobObjectInformation[2]; // [rsp+40h] [rbp-28h] BYREF
  int v14; // [rsp+78h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  *((_QWORD *)this + 3) = a2;
  (**(void (__fastcall ***)(struct APP_POOL *))a2)(a2);
  JOB_OBJECT::SetProcessorCount(this, a3);
  v6 = (WORK_ITEM **)((char *)this + 88);
  BlankWorkItem = WORK_QUEUE::GetBlankWorkItem(
                    (WEB_ADMIN_SERVICE *)((char *)g_pWebAdminService + 16),
                    (struct WORK_ITEM **)this + 11);
  if ( BlankWorkItem >= 0 )
  {
    WORK_ITEM::SetWorkDispatchPointer(*v6, this);
    *((_QWORD *)*v6 + 3) = 1;
    *((_DWORD *)*v6 + 18) = 0;
    JobObjectW = CreateJobObjectW(0, 0);
    *((_QWORD *)this + 9) = JobObjectW;
    if ( JobObjectW )
    {
      BlankWorkItem = 0;
      JobObjectInformation[0] = (char *)*v6 + 40;
      JobObjectInformation[1] = *((_QWORD *)g_pWebAdminService + 4);
      if ( !SetInformationJobObject(
              JobObjectW,
              JobObjectAssociateCompletionPortInformation,
              JobObjectInformation,
              0x10u) )
      {
        LastError = GetLastError();
        BlankWorkItem = LastError;
        if ( LastError > 0 )
          BlankWorkItem = (unsigned __int16)LastError | 0x80070000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\work_queue.cxx",
            672,
            "WORK_QUEUE::BindJobToCompletionPort",
            BlankWorkItem,
            "Binding a completion port to a job object failed\n");
      }
      if ( BlankWorkItem >= 0 )
      {
        v11 = (void *)*((_QWORD *)this + 9);
        v14 = 1;
        if ( SetInformationJobObject(v11, JobObjectEndOfJobTimeInformation, &v14, 4u) )
        {
          *((_DWORD *)this + 4) = 1;
        }
        else
        {
          v12 = GetLastError();
          BlankWorkItem = v12;
          if ( v12 > 0 )
            BlankWorkItem = (unsigned __int16)v12 | 0x80070000;
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\job_object.cxx",
              462,
              "JOB_OBJECT::Initialize",
              BlankWorkItem,
              "setting the job action failed\n");
        }
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\job_object.cxx",
          443,
          "JOB_OBJECT::Initialize",
          BlankWorkItem,
          "Binding the job object to the completion port failed\n");
      }
    }
    else
    {
      v9 = GetLastError();
      BlankWorkItem = v9;
      if ( v9 > 0 )
        BlankWorkItem = (unsigned __int16)v9 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\job_object.cxx",
          423,
          "JOB_OBJECT::Initialize",
          BlankWorkItem,
          "Creating the job object for the app pool failed\n");
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\job_object.cxx",
      390,
      "JOB_OBJECT::Initialize",
      BlankWorkItem,
      "Could not create a work item for the job object\n");
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x8000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\job_object.cxx",
      480,
      "JOB_OBJECT::Initialize",
      "Initializing of the job object is returning %08x \nwork_item %08x, job_object %08x\n",
      BlankWorkItem,
      (unsigned int)*v6,
      (_DWORD)this);
  return (unsigned int)BlankWorkItem;
}

```

## disassembly

```asm
0x180034988  mov     [rsp+arg_0], rbx
0x18003498d  mov     [rsp+arg_10], rbp
0x180034992  push    rdi
0x180034993  push    r14
0x180034995  push    r15
0x180034997  sub     rsp, 50h
0x18003499b  mov     rbx, r8
0x18003499e  mov     rdi, rcx
0x1800349a1  test    rdx, rdx
0x1800349a4  jnz     short loc_1800349B0
0x1800349a6  mov     eax, 80070057h
0x1800349ab  jmp     loc_180034BEC
0x1800349b0  mov     [rcx+18h], rdx
0x1800349b4  mov     rcx, rdx
0x1800349b7  mov     rax, [rdx]
0x1800349ba  mov     rax, [rax]
0x1800349bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800349c2  mov     rdx, rbx; unsigned __int64
0x1800349c5  mov     rcx, rdi; this
0x1800349c8  call    ?SetProcessorCount@JOB_OBJECT@@AEAAX_K@Z; JOB_OBJECT::SetProcessorCount(unsigned __int64)
0x1800349cd  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x1800349d4  lea     r14, [rdi+58h]
0x1800349d8  add     rcx, 10h; this
0x1800349dc  mov     rdx, r14; struct WORK_ITEM **
0x1800349df  call    ?GetBlankWorkItem@WORK_QUEUE@@QEAAJPEAPEAVWORK_ITEM@@@Z; WORK_QUEUE::GetBlankWorkItem(WORK_ITEM * *)
0x1800349e4  lea     rbp, aJobObjectIniti; "JOB_OBJECT::Initialize"
0x1800349eb  mov     ebx, eax
0x1800349ed  lea     r15, aServercommonIn_61; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800349f4  test    eax, eax
0x1800349f6  jns     short loc_180034A33
0x1800349f8  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800349ff  jz      loc_180034B9E
0x180034a05  lea     rax, aCouldNotCreate_2; "Could not create a work item for the jo"...
0x180034a0c  mov     r8d, 186h
0x180034a12  mov     rcx, cs:g_pDebug
0x180034a19  mov     r9, rbp
0x180034a1c  mov     [rsp+68h+var_40], rax
0x180034a21  mov     rdx, r15
0x180034a24  mov     dword ptr [rsp+68h+var_48], ebx
0x180034a28  call    cs:__imp_PuDbgPrintError
0x180034a2e  jmp     loc_180034B9E
0x180034a33  mov     rcx, [r14]; this
0x180034a36  mov     rdx, rdi; struct WORK_DISPATCH *
0x180034a39  call    ?SetWorkDispatchPointer@WORK_ITEM@@QEAAXPEAVWORK_DISPATCH@@@Z; WORK_ITEM::SetWorkDispatchPointer(WORK_DISPATCH *)
0x180034a3e  mov     rax, [r14]
0x180034a41  xor     edx, edx; lpName
0x180034a43  xor     ecx, ecx; lpJobAttributes
0x180034a45  mov     qword ptr [rax+18h], 1
0x180034a4d  mov     rax, [r14]
0x180034a50  mov     dword ptr [rax+48h], 0
0x180034a57  call    cs:__imp_CreateJobObjectW
0x180034a5d  mov     [rdi+48h], rax
0x180034a61  mov     r10, rax
0x180034a64  test    rax, rax
0x180034a67  jnz     short loc_180034A9D
0x180034a69  call    cs:__imp_GetLastError
0x180034a6f  mov     ebx, eax
0x180034a71  test    eax, eax
0x180034a73  jle     short loc_180034A7E
0x180034a75  movzx   ebx, ax
0x180034a78  or      ebx, 80070000h
0x180034a7e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180034a85  jz      loc_180034B9E
0x180034a8b  lea     rax, aCreatingTheJob; "Creating the job object for the app poo"...
0x180034a92  mov     r8d, 1A7h
0x180034a98  jmp     loc_180034A12
0x180034a9d  mov     rax, [r14]
0x180034aa0  lea     r8, [rsp+68h+JobObjectInformation]; lpJobObjectInformation
0x180034aa5  add     rax, 28h ; '('
0x180034aa9  xor     ebx, ebx
0x180034aab  mov     [rsp+68h+JobObjectInformation], rax
0x180034ab0  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180034ab7  lea     r9d, [rbx+10h]; cbJobObjectInformationLength
0x180034abb  lea     edx, [rbx+7]; JobObjectInformationClass
0x180034abe  mov     rcx, [rax+20h]
0x180034ac2  mov     [rsp+68h+var_20], rcx
0x180034ac7  mov     rcx, r10; hJob
0x180034aca  call    cs:__imp_SetInformationJobObject
0x180034ad0  test    eax, eax
0x180034ad2  jnz     short loc_180034B23
0x180034ad4  call    cs:__imp_GetLastError
0x180034ada  mov     ebx, eax
0x180034adc  test    eax, eax
0x180034ade  jle     short loc_180034AE9
0x180034ae0  movzx   ebx, ax
0x180034ae3  or      ebx, 80070000h
0x180034ae9  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180034af0  jz      short loc_180034B23
0x180034af2  mov     rcx, cs:g_pDebug
0x180034af9  lea     rax, aBindingAComple; "Binding a completion port to a job obje"...
0x180034b00  mov     [rsp+68h+var_40], rax
0x180034b05  lea     r9, aWorkQueueBindj; "WORK_QUEUE::BindJobToCompletionPort"
0x180034b0c  mov     r8d, 2A0h
0x180034b12  mov     dword ptr [rsp+68h+var_48], ebx
0x180034b16  lea     rdx, aServercommonIn_31; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180034b1d  call    cs:__imp_PuDbgPrintError
0x180034b23  test    ebx, ebx
0x180034b25  jns     short loc_180034B42
0x180034b27  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180034b2e  jz      short loc_180034B9E
0x180034b30  lea     rax, aBindingTheJobO; "Binding the job object to the completio"...
0x180034b37  mov     r8d, 1BBh
0x180034b3d  jmp     loc_180034A12
0x180034b42  mov     rcx, [rdi+48h]; hJob
0x180034b46  lea     r8, [rsp+68h+arg_8]; lpJobObjectInformation
0x180034b4b  mov     r9d, 4; cbJobObjectInformationLength
0x180034b51  mov     [rsp+68h+arg_8], 1
0x180034b59  lea     edx, [r9+2]; JobObjectInformationClass
0x180034b5d  call    cs:__imp_SetInformationJobObject
0x180034b63  test    eax, eax
0x180034b65  jnz     short loc_180034B97
0x180034b67  call    cs:__imp_GetLastError
0x180034b6d  mov     ebx, eax
0x180034b6f  test    eax, eax
0x180034b71  jle     short loc_180034B7C
0x180034b73  movzx   ebx, ax
0x180034b76  or      ebx, 80070000h
0x180034b7c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180034b83  jz      short loc_180034B9E
0x180034b85  lea     rax, aSettingTheJobA; "setting the job action failed\n"
0x180034b8c  mov     r8d, 1CEh
0x180034b92  jmp     loc_180034A12
0x180034b97  mov     dword ptr [rdi+10h], 1
0x180034b9e  mov     eax, cs:g_dwDebugFlags
0x180034ba4  test    al, 3
0x180034ba6  setnz   cl
0x180034ba9  bt      eax, 1Bh
0x180034bad  setb    al
0x180034bb0  test    al, cl
0x180034bb2  jz      short loc_180034BEA
0x180034bb4  mov     rax, [r14]
0x180034bb7  mov     r9, rbp
0x180034bba  mov     rcx, cs:g_pDebug
0x180034bc1  mov     r8d, 1E0h
0x180034bc7  mov     [rsp+68h+var_30], rdi
0x180034bcc  mov     rdx, r15
0x180034bcf  mov     [rsp+68h+var_38], rax
0x180034bd4  lea     rax, aInitializingOf_0; "Initializing of the job object is retur"...
0x180034bdb  mov     dword ptr [rsp+68h+var_40], ebx
0x180034bdf  mov     [rsp+68h+var_48], rax
0x180034be4  call    cs:__imp_PuDbgPrint
0x180034bea  mov     eax, ebx
0x180034bec  lea     r11, [rsp+68h+var_18]
0x180034bf1  mov     rbx, [r11+20h]
0x180034bf5  mov     rbp, [r11+30h]
0x180034bf9  mov     rsp, r11
0x180034bfc  pop     r15
0x180034bfe  pop     r14
0x180034c00  pop     rdi
0x180034c01  retn
```
