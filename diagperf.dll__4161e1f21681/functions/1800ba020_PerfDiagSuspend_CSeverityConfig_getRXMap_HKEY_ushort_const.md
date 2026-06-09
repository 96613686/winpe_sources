# PerfDiagSuspend::CSeverityConfig::_getRXMap(HKEY__ * &,ushort const * &)

- ea: `0x1800ba020`
- end: `0x1800ba1cd`
- name: `?_getRXMap@CSeverityConfig@PerfDiagSuspend@@MEAAPEAUtagRXMapEntry@?$RegistryTransferable@VCSeverityConfig@PerfDiagSuspend@@@Performance@@AEAPEAUHKEY__@@AEAPEBG@Z`
- size: `429`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18005759c`
- `0x18005760c`
- `0x1800ba020`
- `0x1800d6010`

## string_xrefs

- `0x1800ba0c3`: `HibernateReadMinorThreshold_Sec`
- `0x1800ba0df`: `HibernateWriteMinorThreshold_Sec`
- `0x1800ba0d1`: `HibernateReadMajorThreshold_Sec`
- `0x1800ba0ed`: `HibernateWriteMajorThreshold_Sec`

## pseudocode

```c
wchar_t **__fastcall PerfDiagSuspend::CSeverityConfig::_getRXMap(__int64 a1)
{
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  if ( __TSS0__1___getRXMap_CSeverityConfig_PerfDiagSuspend__MEAAPEAUtagRXMapEntry___RegistryTransferable_VCSeverityConfig_PerfDiagSuspend___Performance__AEAPEAUHKEY____AEAPEBG_Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
  {
    Init_thread_header(&__TSS0__1___getRXMap_CSeverityConfig_PerfDiagSuspend__MEAAPEAUtagRXMapEntry___RegistryTransferable_VCSeverityConfig_PerfDiagSuspend___Performance__AEAPEAUHKEY____AEAPEBG_Z_4HA);
    if ( __TSS0__1___getRXMap_CSeverityConfig_PerfDiagSuspend__MEAAPEAUtagRXMapEntry___RegistryTransferable_VCSeverityConfig_PerfDiagSuspend___Performance__AEAPEAUHKEY____AEAPEBG_Z_4HA == -1 )
    {
      qword_18010061C = 8;
      dword_180100630 = 0;
      qword_180100628 = (__int64)L"ResumeMajorThreshold_Sec";
      qword_180100634 = 12;
      qword_180100640 = (__int64)L"SuspendMinorThreshold_Sec";
      qword_180100658 = (__int64)L"SuspendMajorThreshold_Sec";
      qword_180100670 = (__int64)L"HibernateReadMinorThreshold_Sec";
      qword_180100688 = (__int64)L"HibernateReadMajorThreshold_Sec";
      qword_1801006A0 = (__int64)L"HibernateWriteMinorThreshold_Sec";
      qword_1801006B8 = (__int64)L"HibernateWriteMajorThreshold_Sec";
      qword_1801006D0 = (__int64)L"S3BiosInitTimeMinorThreshold_MSec";
      qword_1801006E8 = (__int64)L"S3BiosInitTimeMajorThreshold_MSec";
      qword_180100710 = 0;
      dword_180100648 = 0;
      qword_18010064C = 32;
      dword_180100660 = 0;
      qword_180100664 = 36;
      dword_180100678 = 0;
      qword_18010067C = 16;
      dword_180100690 = 0;
      qword_180100694 = 20;
      dword_1801006A8 = 0;
      qword_1801006AC = 40;
      dword_1801006C0 = 0;
      qword_1801006C4 = 44;
      dword_1801006D8 = 0;
      qword_1801006DC = 24;
      dword_1801006F0 = 0;
      qword_1801006F4 = 28;
      qword_180100700 = 0;
      dword_180100708 = 5;
      dword_18010070C = -1;
      Init_thread_footer(&__TSS0__1___getRXMap_CSeverityConfig_PerfDiagSuspend__MEAAPEAUtagRXMapEntry___RegistryTransferable_VCSeverityConfig_PerfDiagSuspend___Performance__AEAPEAUHKEY____AEAPEBG_Z_4HA);
    }
  }
  return &`PerfDiagSuspend::CSeverityConfig::_getRXMap'::`2'::map;
}

```

## disassembly

```asm
0x1800ba020  sub     rsp, 28h
0x1800ba024  mov     rax, [rcx]
0x1800ba027  mov     rax, [rax+8]
0x1800ba02b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba030  mov     ecx, cs:_tls_index
0x1800ba036  mov     rax, gs:58h
0x1800ba03f  mov     edx, 4
0x1800ba044  mov     rax, [rax+rcx*8]
0x1800ba048  mov     eax, [rdx+rax]
0x1800ba04b  cmp     cs:?$TSS0@?1??_getRXMap@CSeverityConfig@PerfDiagSuspend@@MEAAPEAUtagRXMapEntry@?$RegistryTransferable@VCSeverityConfig@PerfDiagSuspend@@@Performance@@AEAPEAUHKEY__@@AEAPEBG@Z@4HA, eax
0x1800ba051  jg      short loc_1800BA05F
0x1800ba053  lea     rax, ?map@?1??_getRXMap@CSeverityConfig@PerfDiagSuspend@@MEAAPEAUtagRXMapEntry@?$RegistryTransferable@VCSeverityConfig@PerfDiagSuspend@@@Performance@@AEAPEAUHKEY__@@AEAPEBG@Z@4PAU456@A; Performance::RegistryTransferable<PerfDiagSuspend::CSeverityConfig>::tagRXMapEntry near * `PerfDiagSuspend::CSeverityConfig::_getRXMap(HKEY__ * &,ushort const * &)'::`2'::map
0x1800ba05a  add     rsp, 28h
0x1800ba05e  retn
0x1800ba05f  lea     rcx, ?$TSS0@?1??_getRXMap@CSeverityConfig@PerfDiagSuspend@@MEAAPEAUtagRXMapEntry@?$RegistryTransferable@VCSeverityConfig@PerfDiagSuspend@@@Performance@@AEAPEAUHKEY__@@AEAPEBG@Z@4HA
0x1800ba066  call    _Init_thread_header
0x1800ba06b  cmp     cs:?$TSS0@?1??_getRXMap@CSeverityConfig@PerfDiagSuspend@@MEAAPEAUtagRXMapEntry@?$RegistryTransferable@VCSeverityConfig@PerfDiagSuspend@@@Performance@@AEAPEAUHKEY__@@AEAPEBG@Z@4HA, 0FFFFFFFFh
0x1800ba072  jnz     short loc_1800BA053
0x1800ba074  xor     edx, edx
0x1800ba076  mov     cs:qword_18010061C, 8
0x1800ba081  lea     rax, aResumemajorthr; "ResumeMajorThreshold_Sec"
0x1800ba088  mov     cs:dword_180100630, edx
0x1800ba08e  mov     cs:qword_180100628, rax
0x1800ba095  lea     rcx, ?$TSS0@?1??_getRXMap@CSeverityConfig@PerfDiagSuspend@@MEAAPEAUtagRXMapEntry@?$RegistryTransferable@VCSeverityConfig@PerfDiagSuspend@@@Performance@@AEAPEAUHKEY__@@AEAPEBG@Z@4HA
0x1800ba09c  lea     rax, aSuspendminorth; "SuspendMinorThreshold_Sec"
0x1800ba0a3  mov     cs:qword_180100634, 0Ch
0x1800ba0ae  mov     cs:qword_180100640, rax
0x1800ba0b5  lea     rax, aSuspendmajorth; "SuspendMajorThreshold_Sec"
0x1800ba0bc  mov     cs:qword_180100658, rax
0x1800ba0c3  lea     rax, aHibernatereadm_0; "HibernateReadMinorThreshold_Sec"
0x1800ba0ca  mov     cs:qword_180100670, rax
0x1800ba0d1  lea     rax, aHibernatereadm; "HibernateReadMajorThreshold_Sec"
0x1800ba0d8  mov     cs:qword_180100688, rax
0x1800ba0df  lea     rax, aHibernatewrite; "HibernateWriteMinorThreshold_Sec"
0x1800ba0e6  mov     cs:qword_1801006A0, rax
0x1800ba0ed  lea     rax, aHibernatewrite_1; "HibernateWriteMajorThreshold_Sec"
0x1800ba0f4  mov     cs:qword_1801006B8, rax
0x1800ba0fb  lea     rax, aS3biosinittime_1; "S3BiosInitTimeMinorThreshold_MSec"
0x1800ba102  mov     cs:qword_1801006D0, rax
0x1800ba109  lea     rax, aS3biosinittime_0; "S3BiosInitTimeMajorThreshold_MSec"
0x1800ba110  mov     cs:qword_1801006E8, rax
0x1800ba117  xor     eax, eax
0x1800ba119  mov     cs:qword_180100710, rax
0x1800ba120  mov     cs:dword_180100648, edx
0x1800ba126  mov     cs:qword_18010064C, 20h ; ' '
0x1800ba131  mov     cs:dword_180100660, edx
0x1800ba137  mov     cs:qword_180100664, 24h ; '$'
0x1800ba142  mov     cs:dword_180100678, edx
0x1800ba148  mov     cs:qword_18010067C, 10h
0x1800ba153  mov     cs:dword_180100690, edx
0x1800ba159  mov     cs:qword_180100694, 14h
0x1800ba164  mov     cs:dword_1801006A8, edx
0x1800ba16a  mov     cs:qword_1801006AC, 28h ; '('
0x1800ba175  mov     cs:dword_1801006C0, edx
0x1800ba17b  mov     cs:qword_1801006C4, 2Ch ; ','
0x1800ba186  mov     cs:dword_1801006D8, edx
0x1800ba18c  mov     cs:qword_1801006DC, 18h
0x1800ba197  mov     cs:dword_1801006F0, edx
0x1800ba19d  mov     cs:qword_1801006F4, 1Ch
0x1800ba1a8  mov     cs:qword_180100700, rdx
0x1800ba1af  mov     cs:dword_180100708, 5
0x1800ba1b9  mov     cs:dword_18010070C, 0FFFFFFFFh
0x1800ba1c3  call    _Init_thread_footer
0x1800ba1c8  jmp     loc_1800BA053
```
