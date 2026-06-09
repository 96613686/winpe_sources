# DxgkDeviceIoctl

- ea: `0x1400724e0`
- end: `0x140072a27`
- name: `DxgkDeviceIoctl`
- size: `1351`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x14001a8d0`
- `0x14001ab20`
- `0x14001b890`
- `0x140045024`
- `0x1400670a4`
- `0x140071dc8`
- `0x1400724e0`
- `0x1400a0100`
- `0x140195620`
- `0x1401e5360`
- `0x140255424`
- `0x140255650`
- `0x140256694`
- `0x14026cb30`
- `0x140323854`
- `0x1403b5c74`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400729da`
- `ntoskrnl!ObfDereferenceObject` at `0x1400729da`
- `ntoskrnl!ProbeForWrite` at `0x140072612`
- `ntoskrnl!ProbeForWrite` at `0x140072612`
- `ntoskrnl!IofCompleteRequest` at `0x1400729f7`
- `ntoskrnl!IofCompleteRequest` at `0x1400729f7`
- `watchdog!WdLogSingleEntry2` at `0x140072532`
- `watchdog!WdLogSingleEntry2` at `0x140072532`
- `watchdog!WdLogSingleEntry0` at `0x14007257e`
- `watchdog!WdLogSingleEntry0` at `0x1400725ad`
- `watchdog!WdLogSingleEntry0` at `0x1400725d7`
- `watchdog!WdLogSingleEntry0` at `0x140072625`
- `watchdog!WdLogSingleEntry0` at `0x14007257e`
- `watchdog!WdLogSingleEntry0` at `0x1400725ad`
- `watchdog!WdLogSingleEntry0` at `0x1400725d7`
- `watchdog!WdLogSingleEntry0` at `0x140072625`
- `watchdog!WdLogSingleEntry1` at `0x140072670`
- `watchdog!WdLogSingleEntry1` at `0x140072700`
- `watchdog!WdLogSingleEntry1` at `0x140072772`
- `watchdog!WdLogSingleEntry1` at `0x1400727ba`
- `watchdog!WdLogSingleEntry1` at `0x14007284d`
- `watchdog!WdLogSingleEntry1` at `0x1400728e4`
- `watchdog!WdLogSingleEntry1` at `0x140072968`
- `watchdog!WdLogSingleEntry1` at `0x1400729ad`
- `watchdog!WdLogSingleEntry1` at `0x140072670`
- `watchdog!WdLogSingleEntry1` at `0x140072700`
- `watchdog!WdLogSingleEntry1` at `0x140072772`
- `watchdog!WdLogSingleEntry1` at `0x1400727ba`
- `watchdog!WdLogSingleEntry1` at `0x14007284d`
- `watchdog!WdLogSingleEntry1` at `0x1400728e4`
- `watchdog!WdLogSingleEntry1` at `0x140072968`
- `watchdog!WdLogSingleEntry1` at `0x1400729ad`

## string_xrefs

- `0x140072716`: `DXGPROCESS::CreateDxgProcess failed: : 0x%I64x`
- `0x14007269f`: `CheckTokenForVMGroupMembership failed: 0x%I64x`

## pseudocode

```c
__int64 __fastcall DxgkDeviceIoctl(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  DWORD LowPart; // ecx
  __int64 v5; // rsi
  PVOID UserBuffer; // r12
  ULONG Length; // esi
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // r14
  ULONG Options; // ebx
  DXGVIRTUALMACHINE **v10; // r14
  NTSTATUS v11; // eax
  DXGVIRTUALMACHINE ***Current; // rax
  int v13; // eax
  const wchar_t *v14; // r9
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // edx
  DXGVIRTUALMACHINE *v19; // rbx
  bool v20; // r8
  DXGVIRTUALMACHINE *v22; // [rsp+50h] [rbp-98h] BYREF
  unsigned int v23; // [rsp+58h] [rbp-90h]
  void *Src; // [rsp+60h] [rbp-88h] BYREF
  void *v25; // [rsp+68h] [rbp-80h]
  PVOID v26; // [rsp+70h] [rbp-78h]
  IRP *v27; // [rsp+78h] [rbp-70h]
  _BYTE v28[24]; // [rsp+80h] [rbp-68h] BYREF
  struct _GUID v29; // [rsp+98h] [rbp-50h] BYREF

  v27 = a2;
  v23 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart != 2310147 )
  {
    LODWORD(v5) = -1073741808;
    WdLogSingleEntry2(3, LowPart);
    WdLogGlobalForLineNumber = 1085;
    goto LABEL_43;
  }
  UserBuffer = a2->UserBuffer;
  v25 = UserBuffer;
  Length = CurrentStackLocation->Parameters.Read.Length;
  Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
  Options = CurrentStackLocation->Parameters.Create.Options;
  Src = 0;
  v29 = 0;
  if ( !DXGVAILOBJECT::IsFeatureEnabled() )
  {
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 942;
    LODWORD(v5) = -1073741637;
    goto LABEL_43;
  }
  if ( Options != 16 )
  {
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 949;
LABEL_7:
    LODWORD(v5) = -1073741306;
    goto LABEL_43;
  }
  if ( Length != 8 )
  {
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 956;
    goto LABEL_7;
  }
  v26 = UserBuffer;
  RtlCopyFromUser(&v29, Parameters, 0x10u);
  ProbeForWrite(UserBuffer, 8u, 1u);
  v10 = 0;
  v11 = CheckTokenForVMGroupMembership();
  v5 = v11;
  if ( v11 < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 980;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"CheckTokenForVMGroupMembership failed: 0x%I64x",
      v5,
      0,
      0,
      0,
      0);
  }
  if ( (int)v5 >= 0 )
  {
    Current = (DXGVIRTUALMACHINE ***)DXGPROCESS::GetCurrent();
    v22 = (DXGVIRTUALMACHINE *)Current;
    if ( Current )
    {
      v18 = *((_DWORD *)Current + 102);
      if ( (v18 & 0x80) != 0 )
      {
        if ( (v18 & 0x100) != 0 )
          v10 = Current[75];
        else
          v10 = (DXGVIRTUALMACHINE **)((unsigned __int64)Current & -(__int64)((v18 & 0x80) != 0));
        LODWORD(v5) = 0;
        goto LABEL_33;
      }
      v5 = -1073741811;
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 1028;
      v14 = L"Process is belonging to VM group, but not VMWP or VMMEM : 0x%I64x";
      goto LABEL_31;
    }
    v13 = DXGPROCESS::CreateDxgProcess(&v22, 0, 0, 1u, 0);
    v5 = v13;
    if ( v13 < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 993;
      v14 = L"DXGPROCESS::CreateDxgProcess failed: : 0x%I64x";
LABEL_31:
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v14, v5, 0, 0, 0, 0);
      goto LABEL_32;
    }
    v15 = *((_DWORD *)v22 + 102);
    if ( (v15 & 0x100) != 0 )
      v10 = (DXGVIRTUALMACHINE **)*((_QWORD *)v22 + 75);
    else
      v10 = (DXGVIRTUALMACHINE **)((unsigned __int64)v22 & -(__int64)((v15 & 0x80u) != 0));
    v16 = DXGPROCESSVMWP::InitializeVmwpProcess((DXGPROCESSVMWP *)v10, 0, 0, 0, 0, 0, 0);
    v5 = v16;
    if ( v16 < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 1003;
      v14 = L"DXGPROCESS::InitializeVmwpProcess failed: : 0x%I64x";
      goto LABEL_31;
    }
    v22 = v10[75];
    v17 = DXGVIRTUALMACHINE::InitializeVirtualMachine(v22, 0, 1u);
    v5 = v17;
    if ( v17 < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 1013;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Failed to initalize virtual machine : 0x%I64x",
        v5,
        0,
        0,
        0,
        0);
    }
    DXGVIRTUALMACHINE::SetVmGuid(v22, &v29);
  }
LABEL_32:
  v19 = 0;
  v22 = 0;
  if ( (int)v5 >= 0 )
  {
LABEL_33:
    DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
      (DXGAUTOPUSHLOCKEXCLUSIVE *)v28,
      (DXGVIRTUALMACHINE *)((char *)v10[75] + 64));
    v19 = DXGVIRTUALMACHINE::ReferenceVailObject(v10[75]);
    v22 = v19;
    if ( !v19 )
    {
      LODWORD(v5) = -1073741275;
      WdLogSingleEntry1(1);
      WdLogGlobalForLineNumber = 1040;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"Failed to find Vail object: 0xI64x",
        -1073741275,
        0,
        0,
        0,
        0);
    }
    DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v28);
    if ( (int)v5 >= 0 )
    {
      LODWORD(v5) = DxgkCompositionObject::CreateHandle(v19, 0xC0060000, v20, 1, &Src);
      if ( (int)v5 >= 0 )
      {
        v23 = 8;
      }
      else
      {
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 1052;
      }
      if ( (int)v5 >= 0 )
        RtlCopyToUser(v25, &Src, 8u);
    }
  }
  if ( v19 )
    ObfDereferenceObject(v19);
LABEL_43:
  a2->IoStatus.Information = v23;
  a2->IoStatus.Status = v5;
  IofCompleteRequest(a2, 0);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400724e0  push    rbx
0x1400724e2  push    rsi
0x1400724e3  push    rdi
0x1400724e4  push    r12
0x1400724e6  push    r14
0x1400724e8  push    r15
0x1400724ea  sub     rsp, 0B8h
0x1400724f1  mov     rax, cs:__security_cookie
0x1400724f8  xor     rax, rsp
0x1400724fb  mov     [rsp+0E8h+var_40], rax
0x140072503  mov     r15, rdx
0x140072506  mov     [rsp+0E8h+var_70], rdx
0x14007250b  xor     edi, edi
0x14007250d  mov     [rsp+0E8h+var_90], edi
0x140072511  mov     rax, [rdx+0B8h]
0x140072518  mov     ecx, [rax+18h]
0x14007251b  cmp     ecx, 234003h
0x140072521  jz      short loc_14007254D
0x140072523  mov     edx, ecx
0x140072525  mov     rsi, 0FFFFFFFFC0000010h
0x14007252c  mov     r8, rsi
0x14007252f  lea     ecx, [rdi+3]
0x140072532  call    cs:__imp_WdLogSingleEntry2
0x140072539  nop     dword ptr [rax+rax+00h]
0x14007253e  mov     cs:WdLogGlobalForLineNumber, 43Dh
0x140072548  jmp     loc_1400729E6
0x14007254d  mov     r12, [rdx+70h]
0x140072551  mov     [rsp+0E8h+var_80], r12
0x140072556  mov     esi, [rax+8]
0x140072559  mov     r14, [rax+20h]
0x14007255d  mov     ebx, [rax+10h]
0x140072560  mov     [rsp+0E8h+Src], rdi
0x140072565  xorps   xmm0, xmm0
0x140072568  movups  xmmword ptr [rsp+0E8h+var_50.Data1], xmm0
0x140072570  call    ?IsFeatureEnabled@DXGVAILOBJECT@@SAEXZ; DXGVAILOBJECT::IsFeatureEnabled(void)
0x140072575  test    al, al
0x140072577  jnz     short loc_14007259E
0x140072579  mov     ecx, 3
0x14007257e  call    cs:__imp_WdLogSingleEntry0
0x140072585  nop     dword ptr [rax+rax+00h]
0x14007258a  mov     cs:WdLogGlobalForLineNumber, 3AEh
0x140072594  mov     esi, 0C00000BBh
0x140072599  jmp     loc_1400729E6
0x14007259e  mov     r8d, 10h; Size
0x1400725a4  cmp     ebx, r8d
0x1400725a7  jz      short loc_1400725CD
0x1400725a9  lea     ecx, [r8-0Dh]
0x1400725ad  call    cs:__imp_WdLogSingleEntry0
0x1400725b4  nop     dword ptr [rax+rax+00h]
0x1400725b9  mov     cs:WdLogGlobalForLineNumber, 3B5h
0x1400725c3  mov     esi, 0C0000206h
0x1400725c8  jmp     loc_1400729E6
0x1400725cd  cmp     esi, 8
0x1400725d0  jz      short loc_1400725EF
0x1400725d2  mov     ecx, 3
0x1400725d7  call    cs:__imp_WdLogSingleEntry0
0x1400725de  nop     dword ptr [rax+rax+00h]
0x1400725e3  mov     cs:WdLogGlobalForLineNumber, 3BCh
0x1400725ed  jmp     short loc_1400725C3
0x1400725ef  mov     esi, edi
0x1400725f1  mov     [rsp+0E8h+var_78], r12
0x1400725f6  mov     rdx, r14; Src
0x1400725f9  lea     rcx, [rsp+0E8h+var_50]; void *
0x140072601  call    RtlCopyFromUser
0x140072606  mov     edx, 8; Length
0x14007260b  lea     r8d, [rdx-7]; Alignment
0x14007260f  mov     rcx, r12; Address
0x140072612  call    cs:__imp_ProbeForWrite
0x140072619  nop     dword ptr [rax+rax+00h]
0x14007261e  jmp     short loc_140072651
0x140072620  mov     ecx, 3
0x140072625  call    cs:__imp_WdLogSingleEntry0
0x14007262c  nop     dword ptr [rax+rax+00h]
0x140072631  mov     cs:WdLogGlobalForLineNumber, 3CAh
0x14007263b  mov     esi, 0C000000Dh
0x140072640  xor     edi, edi
0x140072642  mov     rax, [rsp+0E8h+var_78]
0x140072647  mov     [rsp+0E8h+var_80], rax
0x14007264c  mov     r15, [rsp+0E8h+var_70]
0x140072651  mov     r14, rdi
0x140072654  test    esi, esi
0x140072656  js      short loc_1400726B8
0x140072658  call    ?CheckTokenForVMGroupMembership@@YAJXZ; CheckTokenForVMGroupMembership(void)
0x14007265d  movsxd  rsi, eax
0x140072660  test    eax, eax
0x140072662  jns     short loc_1400726B8
0x140072664  mov     rdx, rsi
0x140072667  mov     r12d, 2
0x14007266d  mov     ecx, r12d
0x140072670  call    cs:__imp_WdLogSingleEntry1
0x140072677  nop     dword ptr [rax+rax+00h]
0x14007267c  mov     cs:WdLogGlobalForLineNumber, 3D4h
0x140072686  mov     [rsp+0E8h+var_A8], rdi
0x14007268b  mov     [rsp+0E8h+var_B0], rdi
0x140072690  mov     [rsp+0E8h+var_B8], rdi
0x140072695  mov     qword ptr [rsp+0E8h+var_C0], rdi
0x14007269a  mov     [rsp+0E8h+var_C8], rsi
0x14007269f  lea     r9, aChecktokenforv; "CheckTokenForVMGroupMembership failed: "...
0x1400726a6  or      r8d, 0FFFFFFFFh
0x1400726aa  mov     edx, 40000h
0x1400726af  xor     ecx, ecx
0x1400726b1  call    DxgkLogInternalTriageEvent
0x1400726b6  jmp     short loc_1400726BE
0x1400726b8  mov     r12d, 2
0x1400726be  test    esi, esi
0x1400726c0  js      loc_140072893
0x1400726c6  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x1400726cb  mov     rcx, rax
0x1400726ce  mov     [rsp+0E8h+var_98], rax
0x1400726d3  test    rax, rax
0x1400726d6  jnz     loc_140072814
0x1400726dc  mov     [rsp+0E8h+var_C8], rdi; struct _EPROCESS *
0x1400726e1  mov     r9b, 1; unsigned __int8
0x1400726e4  xor     r8d, r8d; struct DXGPROCESS *
0x1400726e7  xor     edx, edx; struct DXGPROCESS *
0x1400726e9  lea     rcx, [rsp+0E8h+var_98]; struct DXGPROCESS **
0x1400726ee  call    ?CreateDxgProcess@DXGPROCESS@@SAJPEAPEAV1@PEAV1@1EPEAU_EPROCESS@@@Z; DXGPROCESS::CreateDxgProcess(DXGPROCESS * *,DXGPROCESS *,DXGPROCESS *,uchar,_EPROCESS *)
0x1400726f3  movsxd  rsi, eax
0x1400726f6  test    eax, eax
0x1400726f8  jns     short loc_140072722
0x1400726fa  mov     rdx, rsi
0x1400726fd  mov     ecx, r12d
0x140072700  call    cs:__imp_WdLogSingleEntry1
0x140072707  nop     dword ptr [rax+rax+00h]
0x14007270c  mov     cs:WdLogGlobalForLineNumber, 3E1h
0x140072716  lea     r9, aDxgprocessCrea; "DXGPROCESS::CreateDxgProcess failed: : "...
0x14007271d  jmp     loc_14007286A
0x140072722  mov     rcx, [rsp+0E8h+var_98]
0x140072727  mov     eax, [rcx+198h]
0x14007272d  bt      eax, 8
0x140072731  jnb     short loc_14007273C
0x140072733  mov     r14, [rcx+258h]
0x14007273a  jmp     short loc_140072746
0x14007273c  and     al, 80h
0x14007273e  neg     al
0x140072740  sbb     r14, r14
0x140072743  and     r14, rcx
0x140072746  mov     [rsp+0E8h+var_B8], rdi; struct DXGVIRTUALMACHINE *
0x14007274b  mov     [rsp+0E8h+var_C0], dil; unsigned __int8
0x140072750  mov     [rsp+0E8h+var_C8], rdi; struct _EPROCESS *
0x140072755  xor     r9d, r9d; struct _EPROCESS *
0x140072758  xor     r8d, r8d; struct DXGPROCESS *
0x14007275b  xor     edx, edx; void *
0x14007275d  mov     rcx, r14; this
0x140072760  call    ?InitializeVmwpProcess@DXGPROCESSVMWP@@QEAAJPEAXPEAVDXGPROCESS@@PEAU_EPROCESS@@2EPEAVDXGVIRTUALMACHINE@@@Z; DXGPROCESSVMWP::InitializeVmwpProcess(void *,DXGPROCESS *,_EPROCESS *,_EPROCESS *,uchar,DXGVIRTUALMACHINE *)
0x140072765  movsxd  rsi, eax
0x140072768  test    eax, eax
0x14007276a  jns     short loc_140072794
0x14007276c  mov     rdx, rsi
0x14007276f  mov     ecx, r12d
0x140072772  call    cs:__imp_WdLogSingleEntry1
0x140072779  nop     dword ptr [rax+rax+00h]
0x14007277e  mov     cs:WdLogGlobalForLineNumber, 3EBh
0x140072788  lea     r9, aDxgprocessInit; "DXGPROCESS::InitializeVmwpProcess faile"...
0x14007278f  jmp     loc_14007286A
0x140072794  mov     rax, [r14+258h]
0x14007279b  mov     [rsp+0E8h+var_98], rax
0x1400727a0  mov     r8b, 1; unsigned __int8
0x1400727a3  xor     edx, edx; void *
0x1400727a5  mov     rcx, rax; this
0x1400727a8  call    ?InitializeVirtualMachine@DXGVIRTUALMACHINE@@QEAAJPEAXE@Z; DXGVIRTUALMACHINE::InitializeVirtualMachine(void *,uchar)
0x1400727ad  movsxd  rsi, eax
0x1400727b0  test    eax, eax
0x1400727b2  jns     short loc_140072800
0x1400727b4  mov     rdx, rsi
0x1400727b7  mov     ecx, r12d
0x1400727ba  call    cs:__imp_WdLogSingleEntry1
0x1400727c1  nop     dword ptr [rax+rax+00h]
0x1400727c6  mov     cs:WdLogGlobalForLineNumber, 3F5h
0x1400727d0  mov     [rsp+0E8h+var_A8], rdi
0x1400727d5  mov     [rsp+0E8h+var_B0], rdi
0x1400727da  mov     [rsp+0E8h+var_B8], rdi
0x1400727df  mov     qword ptr [rsp+0E8h+var_C0], rdi
0x1400727e4  mov     [rsp+0E8h+var_C8], rsi
0x1400727e9  lea     r9, aFailedToInital_0; "Failed to initalize virtual machine : 0"...
0x1400727f0  or      r8d, 0FFFFFFFFh
0x1400727f4  mov     edx, 40000h
0x1400727f9  xor     ecx, ecx
0x1400727fb  call    DxgkLogInternalTriageEvent
0x140072800  lea     rdx, [rsp+0E8h+var_50]; struct _GUID *
0x140072808  mov     rcx, [rsp+0E8h+var_98]; this
0x14007280d  call    ?SetVmGuid@DXGVIRTUALMACHINE@@QEAAXPEBU_GUID@@@Z; DXGVIRTUALMACHINE::SetVmGuid(_GUID const *)
0x140072812  jmp     short loc_140072893
0x140072814  mov     edx, [rax+198h]
0x14007281a  mov     eax, edx
0x14007281c  shr     eax, 7
0x14007281f  test    al, 1
0x140072821  jz      short loc_140072840
0x140072823  bt      edx, 8
0x140072827  jnb     short loc_140072832
0x140072829  mov     r14, [rcx+258h]
0x140072830  jmp     short loc_14007283C
0x140072832  and     al, 1
0x140072834  neg     al
0x140072836  sbb     r14, r14
0x140072839  and     r14, rcx
0x14007283c  mov     esi, edi
0x14007283e  jmp     short loc_1400728A3
0x140072840  mov     rsi, 0FFFFFFFFC000000Dh
0x140072847  mov     rdx, rsi
0x14007284a  mov     ecx, r12d
0x14007284d  call    cs:__imp_WdLogSingleEntry1
0x140072854  nop     dword ptr [rax+rax+00h]
0x140072859  mov     cs:WdLogGlobalForLineNumber, 404h
0x140072863  lea     r9, aProcessIsBelon; "Process is belonging to VM group, but n"...
0x14007286a  mov     [rsp+0E8h+var_A8], rdi
0x14007286f  mov     [rsp+0E8h+var_B0], rdi
0x140072874  mov     [rsp+0E8h+var_B8], rdi
0x140072879  mov     qword ptr [rsp+0E8h+var_C0], rdi
0x14007287e  mov     [rsp+0E8h+var_C8], rsi
0x140072883  or      r8d, 0FFFFFFFFh
0x140072887  mov     edx, 40000h
0x14007288c  xor     ecx, ecx
0x14007288e  call    DxgkLogInternalTriageEvent
0x140072893  mov     rbx, rdi
0x140072896  mov     [rsp+0E8h+var_98], rbx
0x14007289b  test    esi, esi
0x14007289d  js      loc_1400729D2
0x1400728a3  mov     rdx, [r14+258h]
0x1400728aa  add     rdx, 40h ; '@'; struct DXGPUSHLOCK *
0x1400728ae  lea     rcx, [rsp+0E8h+var_68]; this
0x1400728b6  call    ??0DXGAUTOPUSHLOCKEXCLUSIVE@@QEAA@QEAVDXGPUSHLOCK@@@Z; DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(DXGPUSHLOCK * const)
0x1400728bb  mov     rcx, [r14+258h]; this
0x1400728c2  call    ?ReferenceVailObject@DXGVIRTUALMACHINE@@QEAAPEAVDXGVAILOBJECT@@XZ; DXGVIRTUALMACHINE::ReferenceVailObject(void)
0x1400728c7  mov     rbx, rax
0x1400728ca  mov     [rsp+0E8h+var_98], rax
0x1400728cf  test    rax, rax
0x1400728d2  jnz     short loc_14007292A
0x1400728d4  mov     r14, 0FFFFFFFFC0000225h
0x1400728db  mov     esi, r14d
0x1400728de  mov     rdx, r14
0x1400728e1  lea     ecx, [rax+1]
0x1400728e4  call    cs:__imp_WdLogSingleEntry1
0x1400728eb  nop     dword ptr [rax+rax+00h]
0x1400728f0  mov     cs:WdLogGlobalForLineNumber, 410h
0x1400728fa  mov     [rsp+0E8h+var_A8], rdi
0x1400728ff  mov     [rsp+0E8h+var_B0], rdi
0x140072904  mov     [rsp+0E8h+var_B8], rdi
0x140072909  mov     qword ptr [rsp+0E8h+var_C0], rdi
0x14007290e  mov     [rsp+0E8h+var_C8], r14
0x140072913  lea     r9, aFailedToFindVa; "Failed to find Vail object: 0xI64x"
0x14007291a  or      r8d, 0FFFFFFFFh
0x14007291e  mov     edx, 40002h
0x140072923  xor     ecx, ecx
0x140072925  call    DxgkLogInternalTriageEvent
0x14007292a  lea     rcx, [rsp+0E8h+var_68]; this
0x140072932  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x140072937  test    esi, esi
0x140072939  js      loc_1400729D2
0x14007293f  lea     rax, [rsp+0E8h+Src]
0x140072944  mov     [rsp+0E8h+var_C8], rax; void **
0x140072949  mov     r9b, 1; char
0x14007294c  mov     edx, 0C0060000h; unsigned int
0x140072951  mov     rcx, rbx; this
0x140072954  call    ?CreateHandle@DxgkCompositionObject@@QEBAJK_NDPEAPEAX@Z; DxgkCompositionObject::CreateHandle(ulong,bool,char,void * *)
0x140072959  movsxd  rsi, eax
0x14007295c  test    eax, eax
0x14007295e  jns     short loc_140072980
0x140072960  mov     rdx, rsi
0x140072963  mov     ecx, 3
0x140072968  call    cs:__imp_WdLogSingleEntry1
0x14007296f  nop     dword ptr [rax+rax+00h]
0x140072974  mov     cs:WdLogGlobalForLineNumber, 41Ch
0x14007297e  jmp     short loc_140072988
0x140072980  mov     [rsp+0E8h+var_90], 8
0x140072988  test    esi, esi
0x14007298a  js      short loc_1400729D2
0x14007298c  mov     r8d, 8; Size
0x140072992  lea     rdx, [rsp+0E8h+Src]; Src
0x140072997  mov     rcx, [rsp+0E8h+var_80]; void *
0x14007299c  call    RtlCopyToUser
0x1400729a1  jmp     short loc_1400729D2
0x1400729a3  mov     rdx, [rsp+0E8h+var_78]
0x1400729a8  mov     ecx, 3
0x1400729ad  call    cs:__imp_WdLogSingleEntry1
0x1400729b4  nop     dword ptr [rax+rax+00h]
0x1400729b9  mov     cs:WdLogGlobalForLineNumber, 42Ch
0x1400729c3  mov     esi, 0C000000Dh
0x1400729c8  mov     rbx, [rsp+0E8h+var_98]
0x1400729cd  mov     r15, [rsp+0E8h+var_70]
0x1400729d2  test    rbx, rbx
0x1400729d5  jz      short loc_1400729E6
0x1400729d7  mov     rcx, rbx; Object
0x1400729da  call    cs:__imp_ObfDereferenceObject
0x1400729e1  nop     dword ptr [rax+rax+00h]
0x1400729e6  mov     eax, [rsp+0E8h+var_90]
0x1400729ea  mov     [r15+38h], rax
0x1400729ee  mov     [r15+30h], esi
0x1400729f2  xor     edx, edx; PriorityBoost
0x1400729f4  mov     rcx, r15; Irp
0x1400729f7  call    cs:__imp_IofCompleteRequest
0x1400729fe  nop     dword ptr [rax+rax+00h]
0x140072a03  mov     eax, esi
0x140072a05  mov     rcx, [rsp+0E8h+var_40]
0x140072a0d  xor     rcx, rsp; StackCookie
0x140072a10  call    __security_check_cookie
0x140072a15  add     rsp, 0B8h
0x140072a1c  pop     r15
0x140072a1e  pop     r14
0x140072a20  pop     r12
  ... truncated ...
```
