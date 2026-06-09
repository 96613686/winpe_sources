# NcaConfigMgrMultisiteUpdate(void *,void *,void *,void *)

- ea: `0x180005c20`
- end: `0x180005cfd`
- name: `?NcaConfigMgrMultisiteUpdate@@YAXPEAX000@Z`
- size: `221`
- prototype: `void __fastcall(void *, void *, void *, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180002310`
- `0x180002e90`
- `0x180004f04`
- `0x180005c20`
- `0x180005df8`
- `0x180006544`
- `0x180006c28`
- `0x180019100`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005c7c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005c7c`

## pseudocode

```c
void __fastcall NcaConfigMgrMultisiteUpdate(void *a1, void *a2, void *a3, void *a4)
{
  PVOID v4; // rcx
  __int64 v5; // rcx
  PVOID v6; // rcx

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids);
  NcaConfigMgrSendConfigChangedNotification(v4, a2, a3, a4);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(v5, ConfigUpdateStart, L"Multisite");
  AcquireSRWLockExclusive(&SRWLock);
  NcaSrcLnkdTriggerRearm(qword_180028BB8);
  NcaConfigMgrSortDteList((struct NCA_POLICY_ *)&xmmword_180028BC8);
  NcaExcludeShareLockLeave(0, &SRWLock);
  NcaEvCollProbesMultisiteUpdate();
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(v6, ConfigUpdateEnd, L"Multisite");
}

```

## disassembly

```asm
0x180005c20  push    rbx
0x180005c22  sub     rsp, 20h
0x180005c26  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c2d  lea     rbx, WPP_GLOBAL_Control
0x180005c34  cmp     rcx, rbx
0x180005c37  jz      short loc_180005C54
0x180005c39  test    byte ptr [rcx+1Ch], 8
0x180005c3d  jz      short loc_180005C54
0x180005c3f  mov     rcx, [rcx+10h]
0x180005c43  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x180005c4a  mov     edx, 1Ah
0x180005c4f  call    WPP_SF_
0x180005c54  call    NcaConfigMgrSendConfigChangedNotification
0x180005c59  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180005c60  jz      short loc_180005C75
0x180005c62  lea     r8, aMultisite; "Multisite"
0x180005c69  lea     rdx, ConfigUpdateStart
0x180005c70  call    McTemplateU0z_EventWriteTransfer
0x180005c75  lea     rcx, SRWLock; SRWLock
0x180005c7c  call    cs:__imp_AcquireSRWLockExclusive
0x180005c83  nop     dword ptr [rax+rax+00h]
0x180005c88  mov     rcx, cs:qword_180028BB8
0x180005c8f  call    NcaSrcLnkdTriggerRearm
0x180005c94  lea     rcx, xmmword_180028BC8; struct NCA_POLICY_ *
0x180005c9b  call    ?NcaConfigMgrSortDteList@@YAJPEAUNCA_POLICY_@@@Z; NcaConfigMgrSortDteList(NCA_POLICY_ *)
0x180005ca0  lea     rdx, SRWLock
0x180005ca7  xor     ecx, ecx
0x180005ca9  call    NcaExcludeShareLockLeave
0x180005cae  call    NcaEvCollProbesMultisiteUpdate
0x180005cb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180005cba  cmp     rcx, rbx
0x180005cbd  jz      short loc_180005CDA
0x180005cbf  test    byte ptr [rcx+1Ch], 8
0x180005cc3  jz      short loc_180005CDA
0x180005cc5  mov     rcx, [rcx+10h]
0x180005cc9  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x180005cd0  mov     edx, 1Bh
0x180005cd5  call    WPP_SF_
0x180005cda  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180005ce1  jz      short loc_180005CF6
0x180005ce3  lea     r8, aMultisite; "Multisite"
0x180005cea  lea     rdx, ConfigUpdateEnd
0x180005cf1  call    McTemplateU0z_EventWriteTransfer
0x180005cf6  add     rsp, 20h
0x180005cfa  pop     rbx
0x180005cfb  retn
```
