# ServiceMain(ulong,ushort * *)

- ea: `0x180037730`
- end: `0x180037912`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `482`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callees

- `0x180001008`
- `0x18000bb98`
- `0x18001ad48`
- `0x18001ae3c`
- `0x18003736c`
- `0x180037730`
- `0x180037a5c`
- `0x180038cb8`

## import_xrefs

- `ADVAPI32!RegisterServiceCtrlHandlerW` at `0x1800377ce`
- `ADVAPI32!RegisterServiceCtrlHandlerW` at `0x1800377ce`
- `ADVAPI32!EventUnregister` at `0x180037906`
- `ADVAPI32!UnregisterTraceGuids` at `0x1800378bf`
- `ADVAPI32!UnregisterTraceGuids` at `0x1800378bf`
- `KERNEL32!GetLastError` at `0x180037827`
- `KERNEL32!GetLastError` at `0x180037827`

## string_xrefs

- `0x1800377ad`: `ServiceMain`
- `0x180037890`: `ServiceMain`

## pseudocode

```c
void __fastcall ServiceMain(unsigned int a1, unsigned __int16 **a2)
{
  unsigned int v4; // eax
  unsigned int v5; // edx
  PVOID *v6; // rbx
  TRACEHANDLE v7; // rcx
  REGHANDLE v8; // rcx

  qword_1800E8EB8 = 1;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_lserver;
  qword_1800E8EB0 = 0;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  WPP_MAIN_CB = 0;
  WppInitUm();
  TraceLoggingRegisterEx_EventRegister_EventSetInformation();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids, L"ServiceMain");
  sshStatusHandle = RegisterServiceCtrlHandlerW(L"TermServLicensing", ServiceCtrl);
  if ( sshStatusHandle )
  {
    ssCurrentStatus = 2;
    if ( (unsigned int)ReportStatusToSCMgr(2u, 0, 0xEA60u) )
    {
      v4 = ServiceStart(a1, a2);
      if ( v4 )
        v5 = v4;
      else
        v5 = 0;
      ReportStatusToSCMgr(1u, v5, 0);
    }
  }
  else
  {
    GetLastError();
    CrimsonHelper::RaiseEventInternal((CrimsonHelper *)CrimsonHelper::s_instance, &TLS_E_SC_CONNECT, 0, 0);
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)v6 + 7) & 0x1000) != 0 )
      {
        WPP_SF_S(v6[2], 12, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids, L"ServiceMain");
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control )
      {
        while ( v6 )
        {
          v7 = (TRACEHANDLE)v6[1];
          if ( v7 )
          {
            UnregisterTraceGuids(v7);
            v6[1] = 0;
          }
          v6 = (PVOID *)*v6;
        }
        WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
      }
    }
  }
  v8 = RegHandle;
  RegHandle = 0;
  dword_1800E20E0 = 0;
  EventUnregister(v8);
}

```

## disassembly

```asm
0x180037730  mov     [rsp+arg_0], rbx
0x180037735  mov     [rsp+arg_8], rbp
0x18003773a  mov     [rsp+arg_10], rsi
0x18003773f  push    rdi
0x180037740  sub     rsp, 20h
0x180037744  mov     rbx, rdx
0x180037747  mov     edi, ecx
0x180037749  lea     rax, WPP_ThisDir_CTLGUID_lserver
0x180037750  mov     cs:qword_1800E8EB8, 1
0x18003775b  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180037762  xor     esi, esi
0x180037764  lea     rax, WPP_MAIN_CB
0x18003776b  mov     cs:qword_1800E8EB0, rsi
0x180037772  mov     cs:WPP_GLOBAL_Control, rax
0x180037779  mov     cs:WPP_MAIN_CB, rsi
0x180037780  call    WppInitUm
0x180037785  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18003778a  mov     rcx, cs:WPP_GLOBAL_Control
0x180037791  lea     rbp, WPP_GLOBAL_Control
0x180037798  cmp     rcx, rbp
0x18003779b  jz      short loc_1800377C0
0x18003779d  test    dword ptr [rcx+1Ch], 1000h
0x1800377a4  jz      short loc_1800377C0
0x1800377a6  mov     rcx, [rcx+10h]
0x1800377aa  lea     edx, [rsi+0Ah]
0x1800377ad  lea     r9, aServicemain_0; "ServiceMain"
0x1800377b4  lea     r8, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids
0x1800377bb  call    WPP_SF_S
0x1800377c0  lea     rdx, ?ServiceCtrl@@YAXK@Z; lpHandlerProc
0x1800377c7  lea     rcx, ServiceName; "TermServLicensing"
0x1800377ce  call    cs:__imp_RegisterServiceCtrlHandlerW
0x1800377d5  nop     dword ptr [rax+rax+00h]
0x1800377da  mov     cs:?sshStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * sshStatusHandle
0x1800377e1  test    rax, rax
0x1800377e4  jz      short loc_180037827
0x1800377e6  mov     ecx, 2; unsigned int
0x1800377eb  xor     edx, edx; unsigned int
0x1800377ed  mov     r8d, 0EA60h; unsigned int
0x1800377f3  mov     cs:?ssCurrentStatus@@3KA, ecx; ulong ssCurrentStatus
0x1800377f9  call    ?ReportStatusToSCMgr@@YAHKKK@Z; ReportStatusToSCMgr(ulong,ulong,ulong)
0x1800377fe  test    eax, eax
0x180037800  jz      short loc_18003784C
0x180037802  xor     r8d, r8d; int
0x180037805  mov     rdx, rbx; unsigned __int16 **
0x180037808  mov     ecx, edi; unsigned int
0x18003780a  call    ?ServiceStart@@YAKKPEAPEAGH@Z; ServiceStart(ulong,ushort * *,int)
0x18003780f  xor     r8d, r8d; unsigned int
0x180037812  lea     ecx, [r8+1]; unsigned int
0x180037816  test    eax, eax
0x180037818  jz      short loc_18003781E
0x18003781a  mov     edx, eax
0x18003781c  jmp     short loc_180037820
0x18003781e  xor     edx, edx; unsigned int
0x180037820  call    ?ReportStatusToSCMgr@@YAHKKK@Z; ReportStatusToSCMgr(ulong,ulong,ulong)
0x180037825  jmp     short loc_18003784C
0x180037827  call    cs:__imp_GetLastError
0x18003782e  nop     dword ptr [rax+rax+00h]
0x180037833  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x180037836  lea     rdx, TLS_E_SC_CONNECT; struct _EVENT_DESCRIPTOR *
0x18003783d  xor     r8d, r8d; unsigned int
0x180037840  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; this
0x180037847  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x18003784c  mov     rbx, cs:WPP_GLOBAL_Control
0x180037853  cmp     rbx, rbp
0x180037856  jz      loc_1800378DE
0x18003785c  test    byte ptr [rbx+1Ch], 20h
0x180037860  jz      short loc_18003787E
0x180037862  mov     rcx, [rbx+10h]
0x180037866  lea     r8, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids
0x18003786d  mov     edx, 0Bh
0x180037872  call    WPP_SF_
0x180037877  mov     rbx, cs:WPP_GLOBAL_Control
0x18003787e  cmp     rbx, rbp
0x180037881  jz      short loc_1800378DE
0x180037883  test    dword ptr [rbx+1Ch], 1000h
0x18003788a  jz      short loc_1800378AF
0x18003788c  mov     rcx, [rbx+10h]
0x180037890  lea     r9, aServicemain_0; "ServiceMain"
0x180037897  mov     edx, 0Ch
0x18003789c  lea     r8, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids
0x1800378a3  call    WPP_SF_S
0x1800378a8  mov     rbx, cs:WPP_GLOBAL_Control
0x1800378af  cmp     rbx, rbp
0x1800378b2  jz      short loc_1800378DE
0x1800378b4  jmp     short loc_1800378D2
0x1800378b6  mov     rcx, [rbx+8]; RegistrationHandle
0x1800378ba  test    rcx, rcx
0x1800378bd  jz      short loc_1800378CF
0x1800378bf  call    cs:__imp_UnregisterTraceGuids
0x1800378c6  nop     dword ptr [rax+rax+00h]
0x1800378cb  mov     [rbx+8], rsi
0x1800378cf  mov     rbx, [rbx]
0x1800378d2  test    rbx, rbx
0x1800378d5  jnz     short loc_1800378B6
0x1800378d7  mov     cs:WPP_GLOBAL_Control, rbp
0x1800378de  mov     rcx, cs:RegHandle
0x1800378e5  mov     cs:RegHandle, rsi
0x1800378ec  mov     cs:dword_1800E20E0, esi
0x1800378f2  mov     rbx, [rsp+28h+arg_0]
0x1800378f7  mov     rbp, [rsp+28h+arg_8]
0x1800378fc  mov     rsi, [rsp+28h+arg_10]
0x180037901  add     rsp, 20h
0x180037905  pop     rdi
0x180037906  jmp     cs:__imp_EventUnregister
```
