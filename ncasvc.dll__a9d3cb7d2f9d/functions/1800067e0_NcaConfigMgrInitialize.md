# NcaConfigMgrInitialize

- ea: `0x1800067e0`
- end: `0x180006936`
- name: `NcaConfigMgrInitialize`
- size: `342`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004f04`
- `0x180004f34`
- `0x180005770`
- `0x180006544`
- `0x1800065c8`
- `0x1800067e0`
- `0x180006c60`
- `0x18001cc3e`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180006887`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180006887`

## string_xrefs

- `0x180006828`: `ConfigMgr`
- `0x1800068eb`: `ConfigMgr`

## pseudocode

```c
__int64 __fastcall NcaConfigMgrInitialize(__int64 a1)
{
  PVOID *v1; // rbx
  int Policy; // eax
  __int64 v3; // rcx
  __int64 v4; // rbx

  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(a1, ModuleInitializeStart, L"ConfigMgr");
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  memset_0(&gNcaConfigMgr, 0, 0x90u);
  if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 8) != 0 )
    WPP_SF_(v1[2], 37, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids);
  dword_180028C38 = 0;
  InitializeSRWLock(&SRWLock);
  dword_180028C38 = 1;
  Policy = NcaConfigMgrLoadPolicy((struct NCA_POLICY_ *)&xmmword_180028BC8);
  v4 = Policy;
  if ( Policy < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids,
        (unsigned int)Policy);
    NcaConfigMgrShutdown();
  }
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0zx_EventWriteTransfer(v3, ModuleInitializeEnd, L"ConfigMgr", v4);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids, (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800067e0  mov     [rsp+arg_0], rbx
0x1800067e5  push    rdi
0x1800067e6  sub     rsp, 20h
0x1800067ea  mov     rbx, cs:WPP_GLOBAL_Control
0x1800067f1  lea     rdi, WPP_GLOBAL_Control
0x1800067f8  cmp     rbx, rdi
0x1800067fb  jz      short loc_18000681F
0x1800067fd  test    byte ptr [rbx+1Ch], 8
0x180006801  jz      short loc_18000681F
0x180006803  mov     rcx, [rbx+10h]
0x180006807  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x18000680e  mov     edx, 0Ah
0x180006813  call    WPP_SF_
0x180006818  mov     rbx, cs:WPP_GLOBAL_Control
0x18000681f  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180006826  jz      short loc_180006842
0x180006828  lea     r8, aConfigmgr; "ConfigMgr"
0x18000682f  lea     rdx, ModuleInitializeStart
0x180006836  call    McTemplateU0z_EventWriteTransfer
0x18000683b  mov     rbx, cs:WPP_GLOBAL_Control
0x180006842  xor     edx, edx; Val
0x180006844  lea     rcx, ?gNcaConfigMgr@@3UNCA_CONFIG_MGR_COMPONENT_@@A; void *
0x18000684b  mov     r8d, 90h; Size
0x180006851  call    memset_0
0x180006856  cmp     rbx, rdi
0x180006859  jz      short loc_180006876
0x18000685b  test    byte ptr [rbx+1Ch], 8
0x18000685f  jz      short loc_180006876
0x180006861  mov     rcx, [rbx+10h]
0x180006865  lea     r8, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids
0x18000686c  mov     edx, 25h ; '%'
0x180006871  call    WPP_SF_
0x180006876  lea     rcx, SRWLock; SRWLock
0x18000687d  mov     cs:dword_180028C38, 0
0x180006887  call    cs:__imp_InitializeSRWLock
0x18000688e  nop     dword ptr [rax+rax+00h]
0x180006893  lea     rcx, xmmword_180028BC8; struct NCA_POLICY_ *
0x18000689a  mov     cs:dword_180028C38, 1
0x1800068a4  call    ?NcaConfigMgrLoadPolicy@@YAJPEAUNCA_POLICY_@@@Z; NcaConfigMgrLoadPolicy(NCA_POLICY_ *)
0x1800068a9  movsxd  rbx, eax
0x1800068ac  test    eax, eax
0x1800068ae  jns     short loc_1800068DF
0x1800068b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068b7  cmp     rcx, rdi
0x1800068ba  jz      short loc_1800068DA
0x1800068bc  test    byte ptr [rcx+1Ch], 1
0x1800068c0  jz      short loc_1800068DA
0x1800068c2  mov     rcx, [rcx+10h]
0x1800068c6  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x1800068cd  mov     edx, 0Bh
0x1800068d2  mov     r9d, ebx
0x1800068d5  call    WPP_SF_d
0x1800068da  call    NcaConfigMgrShutdown
0x1800068df  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x1800068e6  jz      short loc_1800068FE
0x1800068e8  mov     r9, rbx
0x1800068eb  lea     r8, aConfigmgr; "ConfigMgr"
0x1800068f2  lea     rdx, ModuleInitializeEnd
0x1800068f9  call    McTemplateU0zx_EventWriteTransfer
0x1800068fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180006905  cmp     rcx, rdi
0x180006908  jz      short loc_180006928
0x18000690a  test    byte ptr [rcx+1Ch], 8
0x18000690e  jz      short loc_180006928
0x180006910  mov     rcx, [rcx+10h]
0x180006914  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x18000691b  mov     edx, 0Ch
0x180006920  mov     r9d, ebx
0x180006923  call    WPP_SF_d
0x180006928  mov     eax, ebx
0x18000692a  mov     rbx, [rsp+28h+arg_0]
0x18000692f  add     rsp, 20h
0x180006933  pop     rdi
0x180006934  retn
```
