# JOB_OBJECT::UpdateJobObjectMonitoring(int,int)

- ea: `0x180035578`
- end: `0x1800358b6`
- name: `?UpdateJobObjectMonitoring@JOB_OBJECT@@QEAAXHH@Z`
- size: `830`
- prototype: `void __fastcall(JOB_OBJECT *__hidden this, int, int)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800174b0`
- `0x1800181ac`
- `0x1800348c0`

## callees

- `0x1800041f4`
- `0x180005878`
- `0x180019140`
- `0x1800347c8`
- `0x180035010`
- `0x180035230`
- `0x180035578`
- `0x18006101a`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356b4`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x1800356a6`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x1800356a6`
- `iisutil!PuDbgPrint` at `0x1800355f0`
- `iisutil!PuDbgPrint` at `0x1800357e1`
- `iisutil!PuDbgPrint` at `0x180035888`
- `iisutil!PuDbgPrint` at `0x1800355f0`
- `iisutil!PuDbgPrint` at `0x1800357e1`
- `iisutil!PuDbgPrint` at `0x180035888`
- `iisutil!PuDbgPrintError` at `0x1800356fd`
- `iisutil!PuDbgPrintError` at `0x1800356fd`

## string_xrefs

- `0x1800355d3`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\job_object.cxx`
- `0x1800356f6`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\job_object.cxx`
- `0x1800357da`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\job_object.cxx`
- `0x180035876`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\job_object.cxx`
- `0x1800355e4`: `UpdateJobObjectMonitoring called, current state = %d\n`
- `0x1800355c5`: `JOB_OBJECT::UpdateJobObjectMonitoring`
- `0x18003586f`: `JOB_OBJECT::UpdateJobObjectMonitoring`

## pseudocode

```c
void __fastcall JOB_OBJECT::UpdateJobObjectMonitoring(JOB_OBJECT *this, int a2, int a3)
{
  _DWORD *v3; // rdi
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rcx
  _BYTE *v10; // rax
  __int64 v11; // rax
  signed int LastError; // eax
  int v13; // edi
  __int64 v14; // rax
  signed int v15; // edx
  WEB_ADMIN_SERVICE *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  unsigned __int16 *v19; // [rsp+30h] [rbp-C8h] BYREF
  unsigned __int16 *v20; // [rsp+38h] [rbp-C0h] BYREF
  _BYTE JobObjectInformation[8]; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+48h] [rbp-B0h]
  int v23; // [rsp+50h] [rbp-A8h]

  v3 = (_DWORD *)((char *)this + 16);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x8000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\job_object.cxx",
      792,
      "JOB_OBJECT::UpdateJobObjectMonitoring",
      "UpdateJobObjectMonitoring called, current state = %d\n",
      *v3);
  JOB_OBJECT::CancelJobObjectTimer(this);
  if ( *v3 == 4 )
  {
    if ( a2 )
    {
      APP_POOL::ProcessStateChangeCommand(*((_QWORD *)this + 3), 1, 0, 0, 0);
      v7 = *((_QWORD *)this + 3);
      if ( *(_DWORD *)(v7 + 20) == 4 )
        *(_DWORD *)(v7 + 444) = 1;
    }
  }
  v8 = *((_DWORD *)this + 8) * *((_DWORD *)this + 9);
  *v3 = 1;
  *((_QWORD *)this + 7) = *((unsigned int *)this + 10) * (unsigned __int64)(unsigned int)(6000 * v8);
  memset_0(JobObjectInformation, 0, 0x90u);
  v9 = 144;
  v10 = JobObjectInformation;
  do
  {
    *v10++ = 0;
    --v9;
  }
  while ( v9 );
  v11 = *((_QWORD *)this + 7);
  if ( v11 > 0 && *((_DWORD *)this + 16) <= 1u )
  {
    v23 = 2052;
    v22 = v11;
  }
  if ( !SetInformationJobObject(*((HANDLE *)this + 9), JobObjectExtendedLimitInformation, JobObjectInformation, 0x90u) )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\job_object.cxx",
        1366,
        "JOB_OBJECT::SetJobObjectExtendedLimitInformation",
        v13,
        "setting the limit on the job object failed\n");
    v14 = *((_QWORD *)this + 3);
    v19 = 0;
    v19 = *(unsigned __int16 **)(v14 + 56);
    WEB_ADMIN_SERVICE::LogEvent(g_pWebAdminService, 0xC00013C4, 1u, (const unsigned __int16 **const)&v19, v13);
    if ( v13 < 0 )
      goto LABEL_29;
  }
  v15 = JOB_OBJECT::SetNotificationLimitInfo(this, 0x200u, *((_QWORD *)this + 6) == 0);
  if ( v15 < 0 )
    goto LABEL_29;
  if ( a3 )
  {
    v15 = JOB_OBJECT::SetJobObjectCpuRateInformation(this);
    if ( v15 < 0 )
      goto LABEL_29;
  }
  v17 = *((_QWORD *)this + 7);
  if ( v17 > 0 || *((_QWORD *)this + 6) )
  {
    *((_DWORD *)this + 4) = 2;
    if ( v17 > 0 && *((_DWORD *)this + 16) <= 1u )
    {
      LOBYTE(v16) = (g_dwDebugFlags & 3) != 0;
      if ( ((unsigned __int8)v16 & ((g_dwDebugFlags & 0x8000000) != 0)) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\job_object.cxx",
          1140,
          "JOB_OBJECT::BeginJobObjectTimer",
          "Beginning job object timer\n");
      v15 = WEB_ADMIN_SERVICE::BeginTimer(
              v16,
              (struct _TP_TIMER **)this + 10,
              JobObjectTimerCallback,
              60000 * *((_DWORD *)this + 8),
              0,
              this);
      if ( v15 < 0 )
      {
        v18 = *((_QWORD *)this + 3);
        v20 = 0;
        v20 = *(unsigned __int16 **)(v18 + 56);
        WEB_ADMIN_SERVICE::LogEvent(g_pWebAdminService, 0xC00013C5, 1u, (const unsigned __int16 **const)&v20, v15);
LABEL_29:
        v15 = 0;
      }
    }
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x8000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\job_object.cxx",
      951,
      "JOB_OBJECT::UpdateJobObjectMonitoring",
      "Updating the job limit is returning %08x\n",
      v15);
}

```

## disassembly

```asm
0x180035578  mov     [rsp+arg_8], rbx
0x18003557d  mov     [rsp+arg_10], rbp
0x180035582  push    rsi
0x180035583  push    rdi
0x180035584  push    r15
0x180035586  sub     rsp, 0E0h
0x18003558d  mov     rax, cs:__security_cookie
0x180035594  xor     rax, rsp
0x180035597  mov     [rsp+0F8h+var_28], rax
0x18003559f  mov     eax, cs:g_dwDebugFlags
0x1800355a5  lea     rdi, [rcx+10h]
0x1800355a9  test    al, 3
0x1800355ab  mov     ebp, r8d
0x1800355ae  mov     esi, edx
0x1800355b0  mov     rbx, rcx
0x1800355b3  setnz   r9b
0x1800355b7  bt      eax, 1Bh
0x1800355bb  setb    al
0x1800355be  test    al, r9b
0x1800355c1  jz      short loc_1800355F6
0x1800355c3  mov     eax, [rdi]
0x1800355c5  lea     r9, aJobObjectUpdat; "JOB_OBJECT::UpdateJobObjectMonitoring"
0x1800355cc  mov     rcx, cs:g_pDebug
0x1800355d3  lea     rdx, aServercommonIn_61; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800355da  mov     dword ptr [rsp+0F8h+var_D0], eax
0x1800355de  mov     r8d, 318h
0x1800355e4  lea     rax, aUpdatejobobjec; "UpdateJobObjectMonitoring called, curre"...
0x1800355eb  mov     qword ptr [rsp+0F8h+var_D8], rax
0x1800355f0  call    cs:__imp_PuDbgPrint
0x1800355f6  mov     rcx, rbx; this
0x1800355f9  call    ?CancelJobObjectTimer@JOB_OBJECT@@AEAAJXZ; JOB_OBJECT::CancelJobObjectTimer(void)
0x1800355fe  cmp     dword ptr [rdi], 4
0x180035601  mov     r15d, 1
0x180035607  jnz     short loc_180035638
0x180035609  test    esi, esi
0x18003560b  jz      short loc_180035638
0x18003560d  mov     rcx, [rbx+18h]
0x180035611  xor     r9d, r9d
0x180035614  xor     r8d, r8d
0x180035617  mov     [rsp+0F8h+var_D8], 0
0x18003561f  mov     edx, r15d
0x180035622  call    ?ProcessStateChangeCommand@APP_POOL@@QEAAJKHW4HTTP_WRAPPER_PROTOCOL_APPPOOL_STATE_REASON@@J@Z; APP_POOL::ProcessStateChangeCommand(ulong,int,HTTP_WRAPPER_PROTOCOL_APPPOOL_STATE_REASON,long)
0x180035627  mov     rax, [rbx+18h]
0x18003562b  cmp     dword ptr [rax+14h], 4
0x18003562f  jnz     short loc_180035638
0x180035631  mov     [rax+1BCh], r15d
0x180035638  mov     eax, [rbx+24h]
0x18003563b  xor     edx, edx; Val
0x18003563d  imul    eax, [rbx+20h]
0x180035641  mov     [rdi], r15d
0x180035644  mov     edi, 90h
0x180035649  mov     r8d, edi; Size
0x18003564c  imul    ecx, eax, 1770h
0x180035652  mov     eax, [rbx+28h]
0x180035655  imul    rcx, rax
0x180035659  mov     [rbx+38h], rcx
0x18003565d  lea     rcx, [rsp+0F8h+JobObjectInformation]; void *
0x180035662  call    memset_0
0x180035667  mov     ecx, edi
0x180035669  lea     rax, [rsp+0F8h+JobObjectInformation]
0x18003566e  mov     byte ptr [rax], 0
0x180035671  add     rax, r15
0x180035674  sub     rcx, r15
0x180035677  jnz     short loc_18003566E
0x180035679  mov     rax, [rbx+38h]
0x18003567d  test    rax, rax
0x180035680  jle     short loc_180035695
0x180035682  cmp     [rbx+40h], r15d
0x180035686  ja      short loc_180035695
0x180035688  mov     [rsp+0F8h+var_A8], 804h
0x180035690  mov     [rsp+0F8h+var_B0], rax
0x180035695  mov     rcx, [rbx+48h]; hJob
0x180035699  lea     r8, [rsp+0F8h+JobObjectInformation]; lpJobObjectInformation
0x18003569e  mov     r9d, edi; cbJobObjectInformationLength
0x1800356a1  mov     edx, 9; JobObjectInformationClass
0x1800356a6  call    cs:__imp_SetInformationJobObject
0x1800356ac  test    eax, eax
0x1800356ae  jnz     loc_18003573E
0x1800356b4  call    cs:__imp_GetLastError
0x1800356ba  mov     edi, eax
0x1800356bc  test    eax, eax
0x1800356be  jle     short loc_1800356C9
0x1800356c0  movzx   edi, ax
0x1800356c3  or      edi, 80070000h
0x1800356c9  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800356d0  jz      short loc_180035703
0x1800356d2  mov     rcx, cs:g_pDebug
0x1800356d9  lea     rax, aSettingTheLimi; "setting the limit on the job object fai"...
0x1800356e0  mov     [rsp+0F8h+var_D0], rax
0x1800356e5  lea     r9, aJobObjectSetjo; "JOB_OBJECT::SetJobObjectExtendedLimitIn"...
0x1800356ec  mov     r8d, 556h
0x1800356f2  mov     [rsp+0F8h+var_D8], edi
0x1800356f6  lea     rdx, aServercommonIn_61; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800356fd  call    cs:__imp_PuDbgPrintError
0x180035703  mov     rax, [rbx+18h]
0x180035707  lea     r9, [rsp+0F8h+var_C8]; unsigned __int16 **
0x18003570c  mov     [rsp+0F8h+var_C8], 0
0x180035715  mov     r8d, r15d; unsigned __int16
0x180035718  mov     edx, 0C00013C4h; unsigned int
0x18003571d  mov     [rsp+0F8h+var_D8], edi; unsigned int
0x180035721  mov     rcx, [rax+38h]
0x180035725  mov     [rsp+0F8h+var_C8], rcx
0x18003572a  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x180035731  call    ?LogEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180035736  test    edi, edi
0x180035738  js      loc_180035845
0x18003573e  xor     r8d, r8d
0x180035741  mov     edx, 200h; unsigned int
0x180035746  cmp     [rbx+30h], r8
0x18003574a  mov     rcx, rbx; this
0x18003574d  setbe   r8b; int
0x180035751  call    ?SetNotificationLimitInfo@JOB_OBJECT@@QEAAJKH@Z; JOB_OBJECT::SetNotificationLimitInfo(ulong,int)
0x180035756  mov     edx, eax
0x180035758  test    eax, eax
0x18003575a  js      loc_180035845
0x180035760  test    ebp, ebp
0x180035762  jz      short loc_180035776
0x180035764  mov     rcx, rbx; this
0x180035767  call    ?SetJobObjectCpuRateInformation@JOB_OBJECT@@AEAAJXZ; JOB_OBJECT::SetJobObjectCpuRateInformation(void)
0x18003576c  mov     edx, eax
0x18003576e  test    eax, eax
0x180035770  js      loc_180035845
0x180035776  mov     rax, [rbx+38h]
0x18003577a  test    rax, rax
0x18003577d  jg      short loc_18003578A
0x18003577f  cmp     qword ptr [rbx+30h], 0
0x180035784  jbe     loc_180035847
0x18003578a  mov     dword ptr [rbx+10h], 2
0x180035791  test    rax, rax
0x180035794  jle     loc_180035847
0x18003579a  cmp     [rbx+40h], r15d
0x18003579e  ja      loc_180035847
0x1800357a4  mov     eax, cs:g_dwDebugFlags
0x1800357aa  test    al, 3
0x1800357ac  setnz   cl
0x1800357af  bt      eax, 1Bh
0x1800357b3  setb    al
0x1800357b6  test    al, cl
0x1800357b8  jz      short loc_1800357E7
0x1800357ba  mov     rcx, cs:g_pDebug
0x1800357c1  lea     rax, aBeginningJobOb; "Beginning job object timer\n"
0x1800357c8  lea     r9, aJobObjectBegin; "JOB_OBJECT::BeginJobObjectTimer"
0x1800357cf  mov     qword ptr [rsp+0F8h+var_D8], rax
0x1800357d4  mov     r8d, 474h
0x1800357da  lea     rdx, aServercommonIn_61; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800357e1  call    cs:__imp_PuDbgPrint
0x1800357e7  imul    r9d, [rbx+20h], 0EA60h; unsigned int
0x1800357ef  lea     rdx, [rbx+50h]; struct _TP_TIMER **
0x1800357f3  mov     [rsp+0F8h+var_D0], rbx; void *
0x1800357f8  lea     r8, ?JobObjectTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *)
0x1800357ff  mov     [rsp+0F8h+var_D8], 0; int
0x180035807  call    ?BeginTimer@WEB_ADMIN_SERVICE@@QEAAJPEAPEAU_TP_TIMER@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU2@@ZKH2@Z; WEB_ADMIN_SERVICE::BeginTimer(_TP_TIMER * *,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *),ulong,int,void *)
0x18003580c  mov     edx, eax
0x18003580e  test    eax, eax
0x180035810  jns     short loc_180035847
0x180035812  mov     rax, [rbx+18h]
0x180035816  lea     r9, [rsp+0F8h+var_C0]; unsigned __int16 **
0x18003581b  mov     [rsp+0F8h+var_C0], 0
0x180035824  mov     r8d, r15d; unsigned __int16
0x180035827  mov     [rsp+0F8h+var_D8], edx; unsigned int
0x18003582b  mov     edx, 0C00013C5h; unsigned int
0x180035830  mov     rcx, [rax+38h]
0x180035834  mov     [rsp+0F8h+var_C0], rcx
0x180035839  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x180035840  call    ?LogEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180035845  xor     edx, edx
0x180035847  mov     eax, cs:g_dwDebugFlags
0x18003584d  test    al, 3
0x18003584f  setnz   cl
0x180035852  bt      eax, 1Bh
0x180035856  setb    al
0x180035859  test    al, cl
0x18003585b  jz      short loc_18003588E
0x18003585d  mov     rcx, cs:g_pDebug
0x180035864  lea     rax, aUpdatingTheJob; "Updating the job limit is returning %08"...
0x18003586b  mov     dword ptr [rsp+0F8h+var_D0], edx
0x18003586f  lea     r9, aJobObjectUpdat; "JOB_OBJECT::UpdateJobObjectMonitoring"
0x180035876  lea     rdx, aServercommonIn_61; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18003587d  mov     qword ptr [rsp+0F8h+var_D8], rax
0x180035882  mov     r8d, 3B7h
0x180035888  call    cs:__imp_PuDbgPrint
0x18003588e  mov     rcx, [rsp+0F8h+var_28]
0x180035896  xor     rcx, rsp; StackCookie
0x180035899  call    __security_check_cookie
0x18003589e  lea     r11, [rsp+0F8h+var_18]
0x1800358a6  mov     rbx, [r11+28h]
0x1800358aa  mov     rbp, [r11+30h]
0x1800358ae  mov     rsp, r11
0x1800358b1  pop     r15
0x1800358b3  pop     rdi
0x1800358b4  pop     rsi
0x1800358b5  retn
```
