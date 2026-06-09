# NcaConfigMgrPolUpdateInitialize

- ea: `0x180006940`
- end: `0x180006b04`
- name: `NcaConfigMgrPolUpdateInitialize`
- size: `452`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180004f04`
- `0x180004f34`
- `0x180006544`
- `0x1800065c8`
- `0x180006940`
- `0x180006b10`
- `0x18000b1e8`
- `0x18000b88c`
- `0x18000db28`
- `0x180016678`
- `0x180019100`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006a83`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006a83`

## string_xrefs

- `0x180006984`: `ConfigMgrPolUpdate`
- `0x180006abe`: `ConfigMgrPolUpdate`

## pseudocode

```c
__int64 NcaConfigMgrPolUpdateInitialize()
{
  PVOID v0; // rcx
  unsigned int v1; // eax
  signed int v2; // edi
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // rcx
  int v6; // ebx

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(
      (__int64)v0,
      (const EVENT_DESCRIPTOR *)ModuleInitializeStart,
      L"ConfigMgrPolUpdate");
  v1 = NcaGPTriggerRegisterWait((PTP_WAIT_CALLBACK)NcaConfigMgrUpdate);
  v2 = v1;
  if ( v1 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 14;
LABEL_18:
      WPP_SF_d(v3[2], v4, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids, v1);
    }
  }
  else
  {
    v1 = NcaSrcLnkdTriggerRegisterWait(5, &stru_180028F20, 0, NcaConfigMgrMultisiteUpdate, 0, &qword_180028BB8);
    v2 = v1;
    if ( v1 )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v4 = 15;
        goto LABEL_18;
      }
    }
    else
    {
      v1 = NcaIPTriggerRegisterWait(0, NcaConfigMgrIPUpdate, 0, &qword_180028BC0);
      v2 = v1;
      if ( !v1 )
      {
        v2 = 0;
        AcquireSRWLockExclusive(&SRWLock);
        v6 = xmmword_180028BC8;
        NcaExcludeShareLockLeave(0, &SRWLock);
        NcaDAPEvidenceSnapshotSetGlobalState(21, v6 != 0);
        goto LABEL_22;
      }
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v4 = 16;
        goto LABEL_18;
      }
    }
  }
  NcaConfigMgrPolUpdateShutdown();
  if ( v2 > 0 )
    v2 = (unsigned __int16)v2 | 0x80070000;
LABEL_22:
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0zx_EventWriteTransfer(v5, (const EVENT_DESCRIPTOR *)ModuleInitializeEnd, L"ConfigMgrPolUpdate", v2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids, (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180006940  push    rbx
0x180006942  push    rbp
0x180006943  push    rdi
0x180006944  push    r14
0x180006946  sub     rsp, 38h
0x18000694a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006951  lea     rbp, WPP_GLOBAL_Control
0x180006958  lea     r14, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x18000695f  cmp     rcx, rbp
0x180006962  jz      short loc_18000697B
0x180006964  test    byte ptr [rcx+1Ch], 8
0x180006968  jz      short loc_18000697B
0x18000696a  mov     rcx, [rcx+10h]
0x18000696e  mov     edx, 0Dh
0x180006973  mov     r8, r14
0x180006976  call    WPP_SF_
0x18000697b  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180006982  jz      short loc_180006997
0x180006984  lea     r8, aConfigmgrpolup; "ConfigMgrPolUpdate"
0x18000698b  lea     rdx, ModuleInitializeStart
0x180006992  call    McTemplateU0z_EventWriteTransfer
0x180006997  lea     r8, ?gNcaConfigMgr@@3UNCA_CONFIG_MGR_COMPONENT_@@A; NCA_CONFIG_MGR_COMPONENT_ gNcaConfigMgr
0x18000699e  lea     rcx, ?NcaConfigMgrUpdate@@YAXPEAX000@Z; pfnwa
0x1800069a5  call    NcaGPTriggerRegisterWait
0x1800069aa  mov     edi, eax
0x1800069ac  test    eax, eax
0x1800069ae  jz      short loc_1800069D4
0x1800069b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069b7  cmp     rcx, rbp
0x1800069ba  jz      loc_180006A66
0x1800069c0  test    byte ptr [rcx+1Ch], 1
0x1800069c4  jz      loc_180006A66
0x1800069ca  mov     edx, 0Eh
0x1800069cf  jmp     loc_180006A57
0x1800069d4  xor     r8d, r8d
0x1800069d7  lea     rax, qword_180028BB8
0x1800069de  mov     [rsp+58h+var_30], rax
0x1800069e3  lea     r9, ?NcaConfigMgrMultisiteUpdate@@YAXPEAX000@Z; NcaConfigMgrMultisiteUpdate(void *,void *,void *,void *)
0x1800069ea  lea     rdx, stru_180028F20
0x1800069f1  mov     [rsp+58h+var_38], 0
0x1800069fa  lea     ecx, [r8+5]
0x1800069fe  call    NcaSrcLnkdTriggerRegisterWait
0x180006a03  mov     edi, eax
0x180006a05  test    eax, eax
0x180006a07  jz      short loc_180006A22
0x180006a09  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a10  cmp     rcx, rbp
0x180006a13  jz      short loc_180006A66
0x180006a15  test    byte ptr [rcx+1Ch], 1
0x180006a19  jz      short loc_180006A66
0x180006a1b  mov     edx, 0Fh
0x180006a20  jmp     short loc_180006A57
0x180006a22  lea     r9, qword_180028BC0
0x180006a29  xor     r8d, r8d
0x180006a2c  lea     rdx, ?NcaConfigMgrIPUpdate@@YAXPEAX000@Z; NcaConfigMgrIPUpdate(void *,void *,void *,void *)
0x180006a33  xor     ecx, ecx
0x180006a35  call    NcaIPTriggerRegisterWait
0x180006a3a  mov     edi, eax
0x180006a3c  test    eax, eax
0x180006a3e  jz      short loc_180006A7A
0x180006a40  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a47  cmp     rcx, rbp
0x180006a4a  jz      short loc_180006A66
0x180006a4c  test    byte ptr [rcx+1Ch], 1
0x180006a50  jz      short loc_180006A66
0x180006a52  mov     edx, 10h
0x180006a57  mov     rcx, [rcx+10h]
0x180006a5b  mov     r9d, eax
0x180006a5e  mov     r8, r14
0x180006a61  call    WPP_SF_d
0x180006a66  call    NcaConfigMgrPolUpdateShutdown
0x180006a6b  test    edi, edi
0x180006a6d  jle     short loc_180006AB2
0x180006a6f  movzx   edi, di
0x180006a72  or      edi, 80070000h
0x180006a78  jmp     short loc_180006AB2
0x180006a7a  lea     rcx, SRWLock; SRWLock
0x180006a81  xor     edi, edi
0x180006a83  call    cs:__imp_AcquireSRWLockExclusive
0x180006a8a  nop     dword ptr [rax+rax+00h]
0x180006a8f  mov     ebx, dword ptr cs:xmmword_180028BC8
0x180006a95  lea     rdx, SRWLock
0x180006a9c  xor     ecx, ecx
0x180006a9e  call    NcaExcludeShareLockLeave
0x180006aa3  xor     edx, edx
0x180006aa5  lea     ecx, [rdi+15h]
0x180006aa8  test    ebx, ebx
0x180006aaa  setnz   dl
0x180006aad  call    NcaDAPEvidenceSnapshotSetGlobalState
0x180006ab2  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180006ab9  jz      short loc_180006AD1
0x180006abb  movsxd  r9, edi
0x180006abe  lea     r8, aConfigmgrpolup; "ConfigMgrPolUpdate"
0x180006ac5  lea     rdx, ModuleInitializeEnd
0x180006acc  call    McTemplateU0zx_EventWriteTransfer
0x180006ad1  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ad8  cmp     rcx, rbp
0x180006adb  jz      short loc_180006AF7
0x180006add  test    byte ptr [rcx+1Ch], 8
0x180006ae1  jz      short loc_180006AF7
0x180006ae3  mov     rcx, [rcx+10h]
0x180006ae7  mov     edx, 12h
0x180006aec  mov     r9d, edi
0x180006aef  mov     r8, r14
0x180006af2  call    WPP_SF_d
0x180006af7  mov     eax, edi
0x180006af9  add     rsp, 38h
0x180006afd  pop     r14
0x180006aff  pop     rdi
0x180006b00  pop     rbp
0x180006b01  pop     rbx
0x180006b02  retn
```
