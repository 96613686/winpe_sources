# NcaConfigMgrIPUpdate(void *,void *,void *,void *)

- ea: `0x180005180`
- end: `0x180005258`
- name: `?NcaConfigMgrIPUpdate@@YAXPEAX000@Z`
- size: `216`
- prototype: `void __fastcall(void *, void *, void *, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180002310`
- `0x180002e90`
- `0x180004f04`
- `0x180005180`
- `0x180005df8`
- `0x180006544`
- `0x180019100`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800051d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800051d7`

## pseudocode

```c
void __fastcall NcaConfigMgrIPUpdate(void *a1, void *a2, void *a3, void *a4)
{
  PVOID v4; // rcx
  PVOID v5; // rcx

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(v4, ConfigUpdateStart, L"IP");
  AcquireSRWLockExclusive(&SRWLock);
  NcaSrcLnkdTriggerRearm(qword_180028BC0);
  NcaConfigMgrSortDteList((struct NCA_POLICY_ *)&xmmword_180028BC8);
  NcaExcludeShareLockLeave(0, &SRWLock);
  NcaEvCollProbesMultisiteUpdate();
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(v5, ConfigUpdateEnd, L"IP");
}

```

## disassembly

```asm
0x180005180  push    rbx
0x180005182  sub     rsp, 20h
0x180005186  mov     rcx, cs:WPP_GLOBAL_Control
0x18000518d  lea     rbx, WPP_GLOBAL_Control
0x180005194  cmp     rcx, rbx
0x180005197  jz      short loc_1800051B4
0x180005199  test    byte ptr [rcx+1Ch], 8
0x18000519d  jz      short loc_1800051B4
0x18000519f  mov     rcx, [rcx+10h]
0x1800051a3  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x1800051aa  mov     edx, 1Ch
0x1800051af  call    WPP_SF_
0x1800051b4  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x1800051bb  jz      short loc_1800051D0
0x1800051bd  lea     r8, aIp; "IP"
0x1800051c4  lea     rdx, ConfigUpdateStart
0x1800051cb  call    McTemplateU0z_EventWriteTransfer
0x1800051d0  lea     rcx, SRWLock; SRWLock
0x1800051d7  call    cs:__imp_AcquireSRWLockExclusive
0x1800051de  nop     dword ptr [rax+rax+00h]
0x1800051e3  mov     rcx, cs:qword_180028BC0
0x1800051ea  call    NcaSrcLnkdTriggerRearm
0x1800051ef  lea     rcx, xmmword_180028BC8; struct NCA_POLICY_ *
0x1800051f6  call    ?NcaConfigMgrSortDteList@@YAJPEAUNCA_POLICY_@@@Z; NcaConfigMgrSortDteList(NCA_POLICY_ *)
0x1800051fb  lea     rdx, SRWLock
0x180005202  xor     ecx, ecx
0x180005204  call    NcaExcludeShareLockLeave
0x180005209  call    NcaEvCollProbesMultisiteUpdate
0x18000520e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005215  cmp     rcx, rbx
0x180005218  jz      short loc_180005235
0x18000521a  test    byte ptr [rcx+1Ch], 8
0x18000521e  jz      short loc_180005235
0x180005220  mov     rcx, [rcx+10h]
0x180005224  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x18000522b  mov     edx, 1Dh
0x180005230  call    WPP_SF_
0x180005235  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x18000523c  jz      short loc_180005251
0x18000523e  lea     r8, aIp; "IP"
0x180005245  lea     rdx, ConfigUpdateEnd
0x18000524c  call    McTemplateU0z_EventWriteTransfer
0x180005251  add     rsp, 20h
0x180005255  pop     rbx
0x180005256  retn
```
