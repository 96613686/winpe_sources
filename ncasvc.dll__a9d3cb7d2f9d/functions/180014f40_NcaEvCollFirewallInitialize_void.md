# NcaEvCollFirewallInitialize(void)

- ea: `0x180014f40`
- end: `0x180015138`
- name: `?NcaEvCollFirewallInitialize@@YAJXZ`
- size: `504`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180004f04`
- `0x180004f34`
- `0x180006544`
- `0x1800065c8`
- `0x180014f40`
- `0x180015140`
- `0x180015430`
- `0x180018ffc`
- `0x18001cc3e`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015000`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015000`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015048`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015097`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015097`
- `KERNEL32!RegisterWaitForSingleObject` at `0x180015087`
- `KERNEL32!RegisterWaitForSingleObject` at `0x180015087`
- `FirewallAPI!FWChangeNotificationCreate` at `0x180015026`
- `FirewallAPI!FWChangeNotificationCreate` at `0x180015026`

## pseudocode

```c
__int64 NcaEvCollFirewallInitialize(void)
{
  PVOID v0; // rcx
  int v1; // eax
  __int64 v2; // rbx
  HANDLE EventW; // rax
  HANDLE v4; // rdx
  DWORD LastError; // eax
  PVOID *v6; // rcx

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_0a37ec5daa873b49bf48ef714ea038f6_Traceguids);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(v0, ModuleInitializeStart, L"EvCollFirewall");
  memset_0(&gNcaEvCollFirewall, 0, 0x50u);
  v1 = NcaCriticalSectionCreate(&stru_180029278);
  v2 = v1;
  if ( v1 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_0a37ec5daa873b49bf48ef714ea038f6_Traceguids,
        (unsigned int)v1);
    NcaEvCollFirewallShutdown();
    goto LABEL_20;
  }
  NcaEvCollOnFirewallChange(0, 0);
  EventW = CreateEventW(0, 0, 0, 0);
  qword_180029268 = EventW;
  if ( !EventW )
  {
    qword_180029270 = 0;
    goto LABEL_20;
  }
  if ( (unsigned int)FWChangeNotificationCreate(EventW, &qword_180029270) )
  {
    qword_180029270 = 0;
    CloseHandle(qword_180029268);
    v4 = 0;
    qword_180029268 = 0;
  }
  else
  {
    v4 = qword_180029268;
  }
  if ( RegisterWaitForSingleObject(&gNcaEvCollFirewall, v4, NcaEvCollOnFirewallChange, 0, 0xFFFFFFFF, 0x80u) )
    goto LABEL_20;
  LastError = GetLastError();
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_0a37ec5daa873b49bf48ef714ea038f6_Traceguids, LastError);
LABEL_20:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
  {
    McTemplateU0zx_EventWriteTransfer(v6, ModuleInitializeEnd, L"EvCollFirewall", v2);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    WPP_SF_d(v6[2], 20, WPP_0a37ec5daa873b49bf48ef714ea038f6_Traceguids, (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180014f40  mov     [rsp+arg_0], rbx
0x180014f45  push    rsi
0x180014f46  sub     rsp, 30h
0x180014f4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f51  lea     rsi, WPP_GLOBAL_Control
0x180014f58  cmp     rcx, rsi
0x180014f5b  jz      short loc_180014F78
0x180014f5d  test    byte ptr [rcx+1Ch], 8
0x180014f61  jz      short loc_180014F78
0x180014f63  mov     rcx, [rcx+10h]
0x180014f67  lea     r8, WPP_0a37ec5daa873b49bf48ef714ea038f6_Traceguids
0x180014f6e  mov     edx, 11h
0x180014f73  call    WPP_SF_
0x180014f78  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180014f7f  jz      short loc_180014F94
0x180014f81  lea     r8, aEvcollfirewall; "EvCollFirewall"
0x180014f88  lea     rdx, ModuleInitializeStart
0x180014f8f  call    McTemplateU0z_EventWriteTransfer
0x180014f94  xor     edx, edx; Val
0x180014f96  lea     rcx, ?gNcaEvCollFirewall@@3UNCA_EVCOLL_FIREWALL_COMPONENT_@@A; void *
0x180014f9d  lea     r8d, [rdx+50h]; Size
0x180014fa1  call    memset_0
0x180014fa6  lea     rcx, stru_180029278; lpCriticalSection
0x180014fad  call    NcaCriticalSectionCreate
0x180014fb2  movsxd  rbx, eax
0x180014fb5  test    eax, eax
0x180014fb7  jns     short loc_180014FED
0x180014fb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fc0  cmp     rcx, rsi
0x180014fc3  jz      short loc_180014FE3
0x180014fc5  test    byte ptr [rcx+1Ch], 1
0x180014fc9  jz      short loc_180014FE3
0x180014fcb  mov     rcx, [rcx+10h]
0x180014fcf  lea     r8, WPP_0a37ec5daa873b49bf48ef714ea038f6_Traceguids
0x180014fd6  mov     edx, 12h
0x180014fdb  mov     r9d, ebx
0x180014fde  call    WPP_SF_d
0x180014fe3  call    ?NcaEvCollFirewallShutdown@@YAXXZ; NcaEvCollFirewallShutdown(void)
0x180014fe8  jmp     loc_1800150DA
0x180014fed  xor     edx, edx; BOOLEAN
0x180014fef  xor     ecx, ecx; PVOID
0x180014ff1  call    NcaEvCollOnFirewallChange
0x180014ff6  xor     r9d, r9d; lpName
0x180014ff9  xor     r8d, r8d; bInitialState
0x180014ffc  xor     edx, edx; bManualReset
0x180014ffe  xor     ecx, ecx; lpEventAttributes
0x180015000  call    cs:__imp_CreateEventW
0x180015007  nop     dword ptr [rax+rax+00h]
0x18001500c  mov     cs:qword_180029268, rax
0x180015013  test    rax, rax
0x180015016  jz      loc_1800150CF
0x18001501c  lea     rdx, qword_180029270
0x180015023  mov     rcx, rax
0x180015026  call    cs:__imp_FWChangeNotificationCreate
0x18001502d  nop     dword ptr [rax+rax+00h]
0x180015032  test    eax, eax
0x180015034  jz      short loc_18001505F
0x180015036  mov     rcx, cs:qword_180029268; hObject
0x18001503d  mov     cs:qword_180029270, 0
0x180015048  call    cs:__imp_CloseHandle
0x18001504f  nop     dword ptr [rax+rax+00h]
0x180015054  xor     edx, edx
0x180015056  mov     cs:qword_180029268, rdx
0x18001505d  jmp     short loc_180015066
0x18001505f  mov     rdx, cs:qword_180029268; hObject
0x180015066  mov     [rsp+38h+dwFlags], 80h; dwFlags
0x18001506e  lea     r8, NcaEvCollOnFirewallChange; Callback
0x180015075  xor     r9d, r9d; Context
0x180015078  mov     [rsp+38h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x180015080  lea     rcx, ?gNcaEvCollFirewall@@3UNCA_EVCOLL_FIREWALL_COMPONENT_@@A; phNewWaitObject
0x180015087  call    cs:__imp_RegisterWaitForSingleObject
0x18001508e  nop     dword ptr [rax+rax+00h]
0x180015093  test    eax, eax
0x180015095  jnz     short loc_1800150DA
0x180015097  call    cs:__imp_GetLastError
0x18001509e  nop     dword ptr [rax+rax+00h]
0x1800150a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150aa  cmp     rcx, rsi
0x1800150ad  jz      short loc_1800150E1
0x1800150af  test    byte ptr [rcx+1Ch], 1
0x1800150b3  jz      short loc_1800150E1
0x1800150b5  mov     rcx, [rcx+10h]
0x1800150b9  lea     r8, WPP_0a37ec5daa873b49bf48ef714ea038f6_Traceguids
0x1800150c0  mov     edx, 13h
0x1800150c5  mov     r9d, eax
0x1800150c8  call    WPP_SF_d
0x1800150cd  jmp     short loc_1800150DA
0x1800150cf  mov     cs:qword_180029270, 0
0x1800150da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150e1  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x1800150e8  jz      short loc_180015107
0x1800150ea  mov     r9, rbx
0x1800150ed  lea     r8, aEvcollfirewall; "EvCollFirewall"
0x1800150f4  lea     rdx, ModuleInitializeEnd
0x1800150fb  call    McTemplateU0zx_EventWriteTransfer
0x180015100  mov     rcx, cs:WPP_GLOBAL_Control
0x180015107  cmp     rcx, rsi
0x18001510a  jz      short loc_18001512A
0x18001510c  test    byte ptr [rcx+1Ch], 8
0x180015110  jz      short loc_18001512A
0x180015112  mov     rcx, [rcx+10h]
0x180015116  lea     r8, WPP_0a37ec5daa873b49bf48ef714ea038f6_Traceguids
0x18001511d  mov     edx, 14h
0x180015122  mov     r9d, ebx
0x180015125  call    WPP_SF_d
0x18001512a  mov     eax, ebx
0x18001512c  mov     rbx, [rsp+38h+arg_0]
0x180015131  add     rsp, 30h
0x180015135  pop     rsi
0x180015136  retn
```
