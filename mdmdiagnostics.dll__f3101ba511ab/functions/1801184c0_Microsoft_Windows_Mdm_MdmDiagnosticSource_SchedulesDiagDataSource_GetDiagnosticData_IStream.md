# Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x1801184c0`
- end: `0x18011854e`
- name: `?GetDiagnosticData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `142`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800ed46c`
- `0x1801184c0`
- `0x180118e40`
- `0x1801193d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1801184df`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1801184df`

## string_xrefs

- `0x1801184fb`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\schedulesdiagdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::GetDiagnosticData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource *this,
        struct IStream **a2)
{
  int StreamOnHGlobal; // ebx
  __int64 v5; // rdx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, a2);
  if ( StreamOnHGlobal < 0 )
  {
    v5 = 359;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\schedulesdiagdata.cpp",
      (const char *)(unsigned int)StreamOnHGlobal,
      v7);
    return (unsigned int)StreamOnHGlobal;
  }
  StreamOnHGlobal = Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::InitiatializeDataGathering(
                      this,
                      a2);
  if ( StreamOnHGlobal < 0 )
  {
    v5 = 360;
    goto LABEL_3;
  }
  StreamOnHGlobal = Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::GetScheduleData(this);
  if ( StreamOnHGlobal < 0 )
  {
    v5 = 361;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1801184c0  mov     [rsp+arg_0], rbx
0x1801184c5  mov     [rsp+arg_8], rsi
0x1801184ca  push    rdi; int
0x1801184cb  sub     rsp, 20h
0x1801184cf  mov     rsi, rdx
0x1801184d2  mov     rdi, rcx
0x1801184d5  mov     r8, rdx; ppstm
0x1801184d8  xor     ecx, ecx; hGlobal
0x1801184da  mov     edx, 1; fDeleteOnRelease
0x1801184df  call    cs:__imp_CreateStreamOnHGlobal
0x1801184e6  nop     dword ptr [rax+rax+00h]
0x1801184eb  mov     ebx, eax
0x1801184ed  test    eax, eax
0x1801184ef  jns     short loc_18011850E
0x1801184f1  mov     edx, 167h; void *
0x1801184f6  mov     rcx, [rsp+28h]; this
0x1801184fb  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180118502  mov     r9d, ebx; char *
0x180118505  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011850a  mov     eax, ebx
0x18011850c  jmp     short loc_18011853D
0x18011850e  mov     rdx, rsi; struct IStream **
0x180118511  mov     rcx, rdi; this
0x180118514  call    ?InitiatializeDataGathering@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAPEAUIStream@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::InitiatializeDataGathering(IStream * *)
0x180118519  mov     ebx, eax
0x18011851b  test    eax, eax
0x18011851d  jns     short loc_180118526
0x18011851f  mov     edx, 168h
0x180118524  jmp     short loc_1801184F6
0x180118526  mov     rcx, rdi; this
0x180118529  call    ?GetScheduleData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::GetScheduleData(void)
0x18011852e  mov     ebx, eax
0x180118530  test    eax, eax
0x180118532  jns     short loc_18011853B
0x180118534  mov     edx, 169h
0x180118539  jmp     short loc_1801184F6
0x18011853b  xor     eax, eax
0x18011853d  mov     rbx, [rsp+28h+arg_0]
0x180118542  mov     rsi, [rsp+28h+arg_8]
0x180118547  add     rsp, 20h
0x18011854b  pop     rdi
0x18011854c  retn
```
