# NcaWfpTriggerInitialize

- ea: `0x18000e250`
- end: `0x18000e5c9`
- name: `NcaWfpTriggerInitialize`
- size: `889`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003cb8`
- `0x180003d28`
- `0x180004f04`
- `0x180004f34`
- `0x180006544`
- `0x1800065c8`
- `0x18000b488`
- `0x18000e250`
- `0x18000e5d0`
- `0x18001cc3e`
- `0x18001cc70`

## import_xrefs

- `fwpuclnt!FwpmEngineOpen0` at `0x18000e421`
- `fwpuclnt!FwpmEngineOpen0` at `0x18000e421`
- `fwpuclnt!FwpmNetEventSubscribe4` at `0x18000e4c3`
- `fwpuclnt!FwpmNetEventSubscribe4` at `0x18000e516`
- `fwpuclnt!FwpmNetEventSubscribe4` at `0x18000e4c3`
- `fwpuclnt!FwpmNetEventSubscribe4` at `0x18000e516`

## pseudocode

```c
__int64 NcaWfpTriggerInitialize()
{
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v1; // rax
  PVOID v2; // rcx
  int v3; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  DWORD v8; // eax
  int v9; // edi
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  _QWORD v13[4]; // [rsp+30h] [rbp-69h] BYREF
  _OWORD v14[2]; // [rsp+50h] [rbp-49h] BYREF
  unsigned int Data1; // [rsp+70h] [rbp-29h] BYREF
  __int128 v16; // [rsp+74h] [rbp-25h]
  __int128 v17; // [rsp+84h] [rbp-15h]
  int v18; // [rsp+94h] [rbp-5h]
  _OWORD v19[2]; // [rsp+98h] [rbp-1h] BYREF

  Data1 = 0;
  v18 = 0;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  memset(v14, 0, sizeof(v14));
  v1 = ThreadLocalStoragePointer[tls_index];
  memset(v13, 0, sizeof(v13));
  LODWORD(v1) = *(_DWORD *)(v1 + 4);
  v16 = 0;
  v17 = 0;
  v19[0] = *(_OWORD *)L"Nca Bfe Session";
  v19[1] = *(_OWORD *)L"Session";
  if ( dword_180029B14 > (int)v1 )
  {
    Init_thread_header(&dword_180029B14);
    if ( dword_180029B14 == -1 )
    {
      session.displayData.description = 0;
      session.displayData.name = (wchar_t *)v19;
      *(_OWORD *)&session.sid = 0;
      session.flags = 1;
      *(_QWORD *)&session.txnWaitTimeoutInMSec = 18000000;
      session.kernelMode = 0;
      Init_thread_footer(&dword_180029B14);
    }
  }
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_121ff5a4cd6831df1eb545e67fe1632a_Traceguids);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer((__int64)v2, (const EVENT_DESCRIPTOR *)ModuleInitializeStart, L"WfpTrigger");
  memset_0(&gNcaWfpTriggerComp, 0, 0x98u);
  v3 = NcaSyncedListCreate((__int64)&stru_180028D88);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_18;
    v6 = 11;
LABEL_17:
    WPP_SF_d(v5[2], v6, WPP_121ff5a4cd6831df1eb545e67fe1632a_Traceguids, (unsigned int)v3);
LABEL_18:
    NcaWfpTriggerShutdown();
    goto LABEL_35;
  }
  v3 = NcaSyncedListCreate((__int64)qword_180028DC8);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_18;
    v6 = 12;
    goto LABEL_17;
  }
  v8 = FwpmEngineOpen0(0, 0xAu, 0, &session, &gNcaWfpTriggerComp);
  v9 = v8;
  if ( v8 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_32;
    v11 = 13;
    goto LABEL_31;
  }
  *(_QWORD *)&v14[0] = v13;
  LODWORD(v13[2]) = 1;
  v13[3] = &Data1;
  Data1 = FWPM_CONDITION_NET_EVENT_TYPE.Data1;
  *((_QWORD *)&v16 + 1) = *(unsigned int *)&FWPM_CONDITION_NET_EVENT_TYPE.Data4[4];
  *(_QWORD *)&v16 = *(_QWORD *)&FWPM_CONDITION_NET_EVENT_TYPE.Data2;
  DWORD1(v17) = 3;
  HIDWORD(v17) = 2;
  v8 = FwpmNetEventSubscribe4(gNcaWfpTriggerComp, v14, NcaWfpNetEventCallback, 0, &qword_180028D80);
  v9 = v8;
  if ( v8 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_32;
    v11 = 14;
    goto LABEL_31;
  }
  HIDWORD(v17) = 0;
  v8 = FwpmNetEventSubscribe4(gNcaWfpTriggerComp, v14, NcaWfpNetEventCallback, 0, &eventsHandle);
  v9 = v8;
  if ( !v8 )
    goto LABEL_35;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 15;
LABEL_31:
    WPP_SF_d(v10[2], v11, WPP_121ff5a4cd6831df1eb545e67fe1632a_Traceguids, v8);
  }
LABEL_32:
  NcaWfpTriggerShutdown();
  if ( v9 > 0 )
    v4 = (unsigned __int16)v9 | 0x80070000;
  else
    v4 = v9;
LABEL_35:
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0zx_EventWriteTransfer(v7, (const EVENT_DESCRIPTOR *)ModuleInitializeEnd, L"WfpTrigger", (int)v4);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_121ff5a4cd6831df1eb545e67fe1632a_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18000e250  push    rbp
0x18000e252  push    rbx
0x18000e253  push    rdi
0x18000e254  push    r12
0x18000e256  push    r13
0x18000e258  push    r15
0x18000e25a  lea     rbp, [rsp-2Fh]
0x18000e25f  sub     rsp, 0C8h
0x18000e266  mov     rax, cs:__security_cookie
0x18000e26d  xor     rax, rsp
0x18000e270  mov     [rbp+57h+var_38], rax
0x18000e274  mov     ecx, cs:_tls_index
0x18000e27a  xor     eax, eax
0x18000e27c  xorps   xmm0, xmm0
0x18000e27f  mov     [rbp+57h+var_80], eax
0x18000e282  mov     [rbp+57h+var_5C], eax
0x18000e285  xorps   xmm1, xmm1
0x18000e288  mov     rax, gs:58h
0x18000e291  movups  [rbp+57h+var_BC], xmm0
0x18000e295  mov     edx, 4
0x18000e29a  movups  [rbp+57h+var_A0], xmm0
0x18000e29e  mov     rax, [rax+rcx*8]
0x18000e2a2  movups  [rbp+57h+var_90], xmm0
0x18000e2a6  mov     [rbp+57h+var_C0], 0
0x18000e2ad  movups  [rbp+57h+var_BC+0Ch], xmm0
0x18000e2b1  mov     eax, [rdx+rax]
0x18000e2b4  cmp     cs:dword_180029B14, eax
0x18000e2ba  movups  xmm0, xmmword ptr cs:aNcaBfeSession; "Nca Bfe Session"
0x18000e2c1  movups  [rbp+57h+var_7C], xmm1
0x18000e2c5  movups  [rbp+57h+var_6C], xmm1
0x18000e2c9  movups  xmm1, xmmword ptr cs:aNcaBfeSession+10h; "Session"
0x18000e2d0  movups  [rbp+57h+var_58], xmm0
0x18000e2d4  movups  [rbp+57h+var_48], xmm1
0x18000e2d8  jle     short loc_18000E33B
0x18000e2da  lea     rcx, dword_180029B14
0x18000e2e1  call    _Init_thread_header
0x18000e2e6  cmp     cs:dword_180029B14, 0FFFFFFFFh
0x18000e2ed  jnz     short loc_18000E33B
0x18000e2ef  lea     rax, [rbp+57h+var_58]
0x18000e2f3  mov     cs:session.displayData.description, 0
0x18000e2fe  xorps   xmm0, xmm0
0x18000e301  mov     cs:session.displayData.name, rax
0x18000e308  lea     rcx, dword_180029B14
0x18000e30f  movdqa  xmmword ptr cs:session.sid, xmm0
0x18000e317  mov     cs:session.flags, 1
0x18000e321  mov     qword ptr cs:session.txnWaitTimeoutInMSec, 112A880h
0x18000e32c  mov     cs:session.kernelMode, 0
0x18000e336  call    _Init_thread_footer
0x18000e33b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e342  lea     r15, WPP_GLOBAL_Control
0x18000e349  lea     r12, WPP_121ff5a4cd6831df1eb545e67fe1632a_Traceguids
0x18000e350  mov     edi, 0Ah
0x18000e355  cmp     rcx, r15
0x18000e358  jz      short loc_18000E36E
0x18000e35a  test    byte ptr [rcx+1Ch], 8
0x18000e35e  jz      short loc_18000E36E
0x18000e360  mov     rcx, [rcx+10h]
0x18000e364  mov     edx, edi
0x18000e366  mov     r8, r12
0x18000e369  call    WPP_SF_
0x18000e36e  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x18000e375  jz      short loc_18000E38A
0x18000e377  lea     r8, aWfptrigger; "WfpTrigger"
0x18000e37e  lea     rdx, ModuleInitializeStart
0x18000e385  call    McTemplateU0z_EventWriteTransfer
0x18000e38a  lea     r13, ?gNcaWfpTriggerComp@@3UNCA_WFP_TRIGGER_COMP_@@A; NCA_WFP_TRIGGER_COMP_ gNcaWfpTriggerComp
0x18000e391  xor     edx, edx; Val
0x18000e393  mov     rcx, r13; void *
0x18000e396  mov     r8d, 98h; Size
0x18000e39c  call    memset_0
0x18000e3a1  lea     rcx, stru_180028D88
0x18000e3a8  call    NcaSyncedListCreate
0x18000e3ad  mov     ebx, eax
0x18000e3af  test    eax, eax
0x18000e3b1  jns     short loc_18000E3CC
0x18000e3b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3ba  cmp     rcx, r15
0x18000e3bd  jz      short loc_18000E404
0x18000e3bf  test    byte ptr [rcx+1Ch], 1
0x18000e3c3  jz      short loc_18000E404
0x18000e3c5  mov     edx, 0Bh
0x18000e3ca  jmp     short loc_18000E3F5
0x18000e3cc  lea     rcx, qword_180028DC8
0x18000e3d3  call    NcaSyncedListCreate
0x18000e3d8  mov     ebx, eax
0x18000e3da  test    eax, eax
0x18000e3dc  jns     short loc_18000E40E
0x18000e3de  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3e5  cmp     rcx, r15
0x18000e3e8  jz      short loc_18000E404
0x18000e3ea  test    byte ptr [rcx+1Ch], 1
0x18000e3ee  jz      short loc_18000E404
0x18000e3f0  mov     edx, 0Ch
0x18000e3f5  mov     rcx, [rcx+10h]
0x18000e3f9  mov     r9d, eax
0x18000e3fc  mov     r8, r12
0x18000e3ff  call    WPP_SF_d
0x18000e404  call    NcaWfpTriggerShutdown
0x18000e409  jmp     loc_18000E564
0x18000e40e  lea     r9, session; session
0x18000e415  mov     [rsp+0F0h+engineHandle], r13; engineHandle
0x18000e41a  xor     r8d, r8d; authIdentity
0x18000e41d  mov     edx, edi; authnService
0x18000e41f  xor     ecx, ecx; serverName
0x18000e421  call    cs:__imp_FwpmEngineOpen0
0x18000e428  nop     dword ptr [rax+rax+00h]
0x18000e42d  mov     edi, eax
0x18000e42f  test    eax, eax
0x18000e431  jz      short loc_18000E457
0x18000e433  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e43a  cmp     rcx, r15
0x18000e43d  jz      loc_18000E54E
0x18000e443  test    byte ptr [rcx+1Ch], 1
0x18000e447  jz      loc_18000E54E
0x18000e44d  mov     edx, 0Dh
0x18000e452  jmp     loc_18000E53F
0x18000e457  movsd   xmm0, qword ptr cs:FWPM_CONDITION_NET_EVENT_TYPE.Data2
0x18000e45f  lea     rax, [rbp+57h+var_C0]
0x18000e463  mov     rcx, cs:?gNcaWfpTriggerComp@@3UNCA_WFP_TRIGGER_COMP_@@A; NCA_WFP_TRIGGER_COMP_ gNcaWfpTriggerComp
0x18000e46a  lea     r8, ?NcaWfpNetEventCallback@@YAXPEAXPEBUFWPM_NET_EVENT5_@@@Z; NcaWfpNetEventCallback(void *,FWPM_NET_EVENT5_ const *)
0x18000e471  mov     qword ptr [rbp+57h+var_A0], rax
0x18000e475  lea     rdx, [rbp+57h+var_A0]
0x18000e479  lea     rax, [rbp+57h+var_80]
0x18000e47d  mov     dword ptr [rbp+57h+var_BC+0Ch], 1
0x18000e484  mov     [rbp+57h+var_A8], rax
0x18000e488  xor     r9d, r9d
0x18000e48b  mov     eax, cs:FWPM_CONDITION_NET_EVENT_TYPE.Data1
0x18000e491  mov     [rbp+57h+var_80], eax
0x18000e494  mov     eax, dword ptr cs:FWPM_CONDITION_NET_EVENT_TYPE.Data4+4
0x18000e49a  mov     dword ptr [rbp+57h+var_7C+8], eax
0x18000e49d  lea     rax, qword_180028D80
0x18000e4a4  mov     [rsp+0F0h+engineHandle], rax
0x18000e4a9  movsd   qword ptr [rbp+57h+var_7C], xmm0
0x18000e4ae  mov     dword ptr [rbp+57h+var_7C+0Ch], 0
0x18000e4b5  mov     dword ptr [rbp+57h+var_6C+4], 3
0x18000e4bc  mov     dword ptr [rbp+57h+var_6C+0Ch], 2
0x18000e4c3  call    cs:__imp_FwpmNetEventSubscribe4
0x18000e4ca  nop     dword ptr [rax+rax+00h]
0x18000e4cf  mov     edi, eax
0x18000e4d1  test    eax, eax
0x18000e4d3  jz      short loc_18000E4EE
0x18000e4d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4dc  cmp     rcx, r15
0x18000e4df  jz      short loc_18000E54E
0x18000e4e1  test    byte ptr [rcx+1Ch], 1
0x18000e4e5  jz      short loc_18000E54E
0x18000e4e7  mov     edx, 0Eh
0x18000e4ec  jmp     short loc_18000E53F
0x18000e4ee  mov     rcx, cs:?gNcaWfpTriggerComp@@3UNCA_WFP_TRIGGER_COMP_@@A; NCA_WFP_TRIGGER_COMP_ gNcaWfpTriggerComp
0x18000e4f5  lea     rax, eventsHandle
0x18000e4fc  xor     r9d, r9d
0x18000e4ff  mov     [rsp+0F0h+engineHandle], rax
0x18000e504  lea     r8, ?NcaWfpNetEventCallback@@YAXPEAXPEBUFWPM_NET_EVENT5_@@@Z; NcaWfpNetEventCallback(void *,FWPM_NET_EVENT5_ const *)
0x18000e50b  mov     dword ptr [rbp+57h+var_6C+0Ch], 0
0x18000e512  lea     rdx, [rbp+57h+var_A0]
0x18000e516  call    cs:__imp_FwpmNetEventSubscribe4
0x18000e51d  nop     dword ptr [rax+rax+00h]
0x18000e522  mov     edi, eax
0x18000e524  test    eax, eax
0x18000e526  jz      short loc_18000E564
0x18000e528  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e52f  cmp     rcx, r15
0x18000e532  jz      short loc_18000E54E
0x18000e534  test    byte ptr [rcx+1Ch], 1
0x18000e538  jz      short loc_18000E54E
0x18000e53a  mov     edx, 0Fh
0x18000e53f  mov     rcx, [rcx+10h]
0x18000e543  mov     r9d, eax
0x18000e546  mov     r8, r12
0x18000e549  call    WPP_SF_d
0x18000e54e  call    NcaWfpTriggerShutdown
0x18000e553  test    edi, edi
0x18000e555  jg      short loc_18000E55B
0x18000e557  mov     ebx, edi
0x18000e559  jmp     short loc_18000E564
0x18000e55b  movzx   ebx, di
0x18000e55e  or      ebx, 80070000h
0x18000e564  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x18000e56b  jz      short loc_18000E583
0x18000e56d  movsxd  r9, ebx
0x18000e570  lea     r8, aWfptrigger; "WfpTrigger"
0x18000e577  lea     rdx, ModuleInitializeEnd
0x18000e57e  call    McTemplateU0zx_EventWriteTransfer
0x18000e583  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e58a  cmp     rcx, r15
0x18000e58d  jz      short loc_18000E5A9
0x18000e58f  test    byte ptr [rcx+1Ch], 8
0x18000e593  jz      short loc_18000E5A9
0x18000e595  mov     rcx, [rcx+10h]
0x18000e599  mov     edx, 10h
0x18000e59e  mov     r9d, ebx
0x18000e5a1  mov     r8, r12
0x18000e5a4  call    WPP_SF_d
0x18000e5a9  mov     eax, ebx
0x18000e5ab  mov     rcx, [rbp+57h+var_38]
0x18000e5af  xor     rcx, rsp; StackCookie
0x18000e5b2  call    __security_check_cookie
0x18000e5b7  add     rsp, 0C8h
0x18000e5be  pop     r15
0x18000e5c0  pop     r13
0x18000e5c2  pop     r12
0x18000e5c4  pop     rdi
0x18000e5c5  pop     rbx
0x18000e5c6  pop     rbp
0x18000e5c7  retn
```
