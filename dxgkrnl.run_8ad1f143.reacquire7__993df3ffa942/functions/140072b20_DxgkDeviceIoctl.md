# DxgkDeviceIoctl

- ea: `0x140072b20`
- end: `0x140073067`
- name: `DxgkDeviceIoctl`
- size: `1351`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x14001aa04`
- `0x14001ac50`
- `0x14001b9c0`
- `0x140045284`
- `0x1400674c4`
- `0x140072408`
- `0x140072b20`
- `0x1400a0bd0`
- `0x140199620`
- `0x1401e76e0`
- `0x140259a74`
- `0x140259ca0`
- `0x14025ace4`
- `0x1402720f0`
- `0x14032a5c4`
- `0x1403b6104`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14007301a`
- `ntoskrnl!ObfDereferenceObject` at `0x14007301a`
- `ntoskrnl!ProbeForWrite` at `0x140072c52`
- `ntoskrnl!ProbeForWrite` at `0x140072c52`
- `ntoskrnl!IofCompleteRequest` at `0x140073037`
- `ntoskrnl!IofCompleteRequest` at `0x140073037`
- `watchdog!WdLogSingleEntry2` at `0x140072b72`
- `watchdog!WdLogSingleEntry2` at `0x140072b72`
- `watchdog!WdLogSingleEntry0` at `0x140072bbe`
- `watchdog!WdLogSingleEntry0` at `0x140072bed`
- `watchdog!WdLogSingleEntry0` at `0x140072c17`
- `watchdog!WdLogSingleEntry0` at `0x140072c65`
- `watchdog!WdLogSingleEntry0` at `0x140072bbe`
- `watchdog!WdLogSingleEntry0` at `0x140072bed`
- `watchdog!WdLogSingleEntry0` at `0x140072c17`
- `watchdog!WdLogSingleEntry0` at `0x140072c65`
- `watchdog!WdLogSingleEntry1` at `0x140072cb0`
- `watchdog!WdLogSingleEntry1` at `0x140072d40`
- `watchdog!WdLogSingleEntry1` at `0x140072db2`
- `watchdog!WdLogSingleEntry1` at `0x140072dfa`
- `watchdog!WdLogSingleEntry1` at `0x140072e8d`
- `watchdog!WdLogSingleEntry1` at `0x140072f24`
- `watchdog!WdLogSingleEntry1` at `0x140072fa8`
- `watchdog!WdLogSingleEntry1` at `0x140072fed`
- `watchdog!WdLogSingleEntry1` at `0x140072cb0`
- `watchdog!WdLogSingleEntry1` at `0x140072d40`
- `watchdog!WdLogSingleEntry1` at `0x140072db2`
- `watchdog!WdLogSingleEntry1` at `0x140072dfa`
- `watchdog!WdLogSingleEntry1` at `0x140072e8d`
- `watchdog!WdLogSingleEntry1` at `0x140072f24`
- `watchdog!WdLogSingleEntry1` at `0x140072fa8`
- `watchdog!WdLogSingleEntry1` at `0x140072fed`

## string_xrefs

- `0x140072cdf`: `CheckTokenForVMGroupMembership failed: 0x%I64x`
- `0x140072d56`: `DXGPROCESS::CreateDxgProcess failed: : 0x%I64x`

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
  int v11; // eax
  DXGVIRTUALMACHINE ***Current; // rax
  int v13; // eax
  const wchar_t *v14; // r9
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // edx
  DXGVIRTUALMACHINE *v19; // rbx
  bool v20; // r8
  int v21; // eax
  DXGVIRTUALMACHINE *v23; // [rsp+50h] [rbp-98h] BYREF
  unsigned int v24; // [rsp+58h] [rbp-90h]
  void *Src; // [rsp+60h] [rbp-88h] BYREF
  void *v26; // [rsp+68h] [rbp-80h]
  PVOID v27; // [rsp+70h] [rbp-78h]
  IRP *v28; // [rsp+78h] [rbp-70h]
  _BYTE v29[24]; // [rsp+80h] [rbp-68h] BYREF
  struct _GUID v30; // [rsp+98h] [rbp-50h] BYREF

  v28 = a2;
  v24 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart != 2310147 )
  {
    LODWORD(v5) = -1073741808;
    WdLogSingleEntry2(3, LowPart, -1073741808);
    WdLogGlobalForLineNumber = 1085;
    goto LABEL_43;
  }
  UserBuffer = a2->UserBuffer;
  v26 = UserBuffer;
  Length = CurrentStackLocation->Parameters.Read.Length;
  Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
  Options = CurrentStackLocation->Parameters.Create.Options;
  Src = 0;
  v30 = 0;
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
  v27 = UserBuffer;
  RtlCopyFromUser(&v30, Parameters, 0x10u);
  ProbeForWrite(UserBuffer, 8u, 1u);
  v10 = 0;
  v11 = CheckTokenForVMGroupMembership();
  v5 = v11;
  if ( v11 < 0 )
  {
    WdLogSingleEntry1(2, v11);
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
    v23 = (DXGVIRTUALMACHINE *)Current;
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
      WdLogSingleEntry1(2, -1073741811);
      WdLogGlobalForLineNumber = 1028;
      v14 = L"Process is belonging to VM group, but not VMWP or VMMEM : 0x%I64x";
      goto LABEL_31;
    }
    v13 = DXGPROCESS::CreateDxgProcess(&v23, 0, 0, 1u, 0);
    v5 = v13;
    if ( v13 < 0 )
    {
      WdLogSingleEntry1(2, v13);
      WdLogGlobalForLineNumber = 993;
      v14 = L"DXGPROCESS::CreateDxgProcess failed: : 0x%I64x";
LABEL_31:
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v14, v5, 0, 0, 0, 0);
      goto LABEL_32;
    }
    v15 = *((_DWORD *)v23 + 102);
    if ( (v15 & 0x100) != 0 )
      v10 = (DXGVIRTUALMACHINE **)*((_QWORD *)v23 + 75);
    else
      v10 = (DXGVIRTUALMACHINE **)((unsigned __int64)v23 & -(__int64)((v15 & 0x80u) != 0));
    v16 = DXGPROCESSVMWP::InitializeVmwpProcess((DXGPROCESSVMWP *)v10, 0, 0, 0, 0, 0, 0);
    v5 = v16;
    if ( v16 < 0 )
    {
      WdLogSingleEntry1(2, v16);
      WdLogGlobalForLineNumber = 1003;
      v14 = L"DXGPROCESS::InitializeVmwpProcess failed: : 0x%I64x";
      goto LABEL_31;
    }
    v23 = v10[75];
    v17 = DXGVIRTUALMACHINE::InitializeVirtualMachine(v23, 0, 1u);
    v5 = v17;
    if ( v17 < 0 )
    {
      WdLogSingleEntry1(2, v17);
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
    DXGVIRTUALMACHINE::SetVmGuid(v23, &v30);
  }
LABEL_32:
  v19 = 0;
  v23 = 0;
  if ( (int)v5 >= 0 )
  {
LABEL_33:
    DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
      (DXGAUTOPUSHLOCKEXCLUSIVE *)v29,
      (DXGVIRTUALMACHINE *)((char *)v10[75] + 64));
    v19 = DXGVIRTUALMACHINE::ReferenceVailObject(v10[75]);
    v23 = v19;
    if ( !v19 )
    {
      LODWORD(v5) = -1073741275;
      WdLogSingleEntry1(1, -1073741275);
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
    DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v29);
    if ( (int)v5 >= 0 )
    {
      v21 = DxgkCompositionObject::CreateHandle(v19, 0xC0060000, v20, 1, &Src);
      LODWORD(v5) = v21;
      if ( v21 >= 0 )
      {
        v24 = 8;
      }
      else
      {
        WdLogSingleEntry1(3, v21);
        WdLogGlobalForLineNumber = 1052;
      }
      if ( (int)v5 >= 0 )
        RtlCopyToUser(v26, &Src, 8u);
    }
  }
  if ( v19 )
    ObfDereferenceObject(v19);
LABEL_43:
  a2->IoStatus.Information = v24;
  a2->IoStatus.Status = v5;
  IofCompleteRequest(a2, 0);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140072b20  push    rbx
0x140072b22  push    rsi
0x140072b23  push    rdi
0x140072b24  push    r12
0x140072b26  push    r14
0x140072b28  push    r15
0x140072b2a  sub     rsp, 0B8h
0x140072b31  mov     rax, cs:__security_cookie
0x140072b38  xor     rax, rsp
0x140072b3b  mov     [rsp+0E8h+var_40], rax
0x140072b43  mov     r15, rdx
0x140072b46  mov     [rsp+0E8h+var_70], rdx
0x140072b4b  xor     edi, edi
0x140072b4d  mov     [rsp+0E8h+var_90], edi
0x140072b51  mov     rax, [rdx+0B8h]
0x140072b58  mov     ecx, [rax+18h]
0x140072b5b  cmp     ecx, 234003h
0x140072b61  jz      short loc_140072B8D
0x140072b63  mov     edx, ecx
0x140072b65  mov     rsi, 0FFFFFFFFC0000010h
0x140072b6c  mov     r8, rsi
0x140072b6f  lea     ecx, [rdi+3]
0x140072b72  call    cs:__imp_WdLogSingleEntry2
0x140072b79  nop     dword ptr [rax+rax+00h]
0x140072b7e  mov     cs:WdLogGlobalForLineNumber, 43Dh
0x140072b88  jmp     loc_140073026
0x140072b8d  mov     r12, [rdx+70h]
0x140072b91  mov     [rsp+0E8h+var_80], r12
0x140072b96  mov     esi, [rax+8]
0x140072b99  mov     r14, [rax+20h]
0x140072b9d  mov     ebx, [rax+10h]
0x140072ba0  mov     [rsp+0E8h+Src], rdi
0x140072ba5  xorps   xmm0, xmm0
0x140072ba8  movups  xmmword ptr [rsp+0E8h+var_50.Data1], xmm0
0x140072bb0  call    ?IsFeatureEnabled@DXGVAILOBJECT@@SAEXZ; DXGVAILOBJECT::IsFeatureEnabled(void)
0x140072bb5  test    al, al
0x140072bb7  jnz     short loc_140072BDE
0x140072bb9  mov     ecx, 3
0x140072bbe  call    cs:__imp_WdLogSingleEntry0
0x140072bc5  nop     dword ptr [rax+rax+00h]
0x140072bca  mov     cs:WdLogGlobalForLineNumber, 3AEh
0x140072bd4  mov     esi, 0C00000BBh
0x140072bd9  jmp     loc_140073026
0x140072bde  mov     r8d, 10h; Size
0x140072be4  cmp     ebx, r8d
0x140072be7  jz      short loc_140072C0D
0x140072be9  lea     ecx, [r8-0Dh]
0x140072bed  call    cs:__imp_WdLogSingleEntry0
0x140072bf4  nop     dword ptr [rax+rax+00h]
0x140072bf9  mov     cs:WdLogGlobalForLineNumber, 3B5h
0x140072c03  mov     esi, 0C0000206h
0x140072c08  jmp     loc_140073026
0x140072c0d  cmp     esi, 8
0x140072c10  jz      short loc_140072C2F
0x140072c12  mov     ecx, 3
0x140072c17  call    cs:__imp_WdLogSingleEntry0
0x140072c1e  nop     dword ptr [rax+rax+00h]
0x140072c23  mov     cs:WdLogGlobalForLineNumber, 3BCh
0x140072c2d  jmp     short loc_140072C03
0x140072c2f  mov     esi, edi
0x140072c31  mov     [rsp+0E8h+var_78], r12
0x140072c36  mov     rdx, r14; Src
0x140072c39  lea     rcx, [rsp+0E8h+var_50]; void *
0x140072c41  call    RtlCopyFromUser
0x140072c46  mov     edx, 8; Length
0x140072c4b  lea     r8d, [rdx-7]; Alignment
0x140072c4f  mov     rcx, r12; Address
0x140072c52  call    cs:__imp_ProbeForWrite
0x140072c59  nop     dword ptr [rax+rax+00h]
0x140072c5e  jmp     short loc_140072C91
0x140072c60  mov     ecx, 3
0x140072c65  call    cs:__imp_WdLogSingleEntry0
0x140072c6c  nop     dword ptr [rax+rax+00h]
0x140072c71  mov     cs:WdLogGlobalForLineNumber, 3CAh
0x140072c7b  mov     esi, 0C000000Dh
0x140072c80  xor     edi, edi
0x140072c82  mov     rax, [rsp+0E8h+var_78]
0x140072c87  mov     [rsp+0E8h+var_80], rax
0x140072c8c  mov     r15, [rsp+0E8h+var_70]
0x140072c91  mov     r14, rdi
0x140072c94  test    esi, esi
0x140072c96  js      short loc_140072CF8
0x140072c98  call    ?CheckTokenForVMGroupMembership@@YAJXZ; CheckTokenForVMGroupMembership(void)
0x140072c9d  movsxd  rsi, eax
0x140072ca0  test    eax, eax
0x140072ca2  jns     short loc_140072CF8
0x140072ca4  mov     rdx, rsi
0x140072ca7  mov     r12d, 2
0x140072cad  mov     ecx, r12d
0x140072cb0  call    cs:__imp_WdLogSingleEntry1
0x140072cb7  nop     dword ptr [rax+rax+00h]
0x140072cbc  mov     cs:WdLogGlobalForLineNumber, 3D4h
0x140072cc6  mov     [rsp+0E8h+var_A8], rdi
0x140072ccb  mov     [rsp+0E8h+var_B0], rdi
0x140072cd0  mov     [rsp+0E8h+var_B8], rdi
0x140072cd5  mov     qword ptr [rsp+0E8h+var_C0], rdi
0x140072cda  mov     [rsp+0E8h+var_C8], rsi
0x140072cdf  lea     r9, aChecktokenforv; "CheckTokenForVMGroupMembership failed: "...
0x140072ce6  or      r8d, 0FFFFFFFFh
0x140072cea  mov     edx, 40000h
0x140072cef  xor     ecx, ecx
0x140072cf1  call    DxgkLogInternalTriageEvent
0x140072cf6  jmp     short loc_140072CFE
0x140072cf8  mov     r12d, 2
0x140072cfe  test    esi, esi
0x140072d00  js      loc_140072ED3
0x140072d06  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x140072d0b  mov     rcx, rax
0x140072d0e  mov     [rsp+0E8h+var_98], rax
0x140072d13  test    rax, rax
0x140072d16  jnz     loc_140072E54
0x140072d1c  mov     [rsp+0E8h+var_C8], rdi; struct _EPROCESS *
0x140072d21  mov     r9b, 1; unsigned __int8
0x140072d24  xor     r8d, r8d; struct DXGPROCESS *
0x140072d27  xor     edx, edx; struct DXGPROCESS *
0x140072d29  lea     rcx, [rsp+0E8h+var_98]; struct DXGPROCESS **
0x140072d2e  call    ?CreateDxgProcess@DXGPROCESS@@SAJPEAPEAV1@PEAV1@1EPEAU_EPROCESS@@@Z; DXGPROCESS::CreateDxgProcess(DXGPROCESS * *,DXGPROCESS *,DXGPROCESS *,uchar,_EPROCESS *)
0x140072d33  movsxd  rsi, eax
0x140072d36  test    eax, eax
0x140072d38  jns     short loc_140072D62
0x140072d3a  mov     rdx, rsi
0x140072d3d  mov     ecx, r12d
0x140072d40  call    cs:__imp_WdLogSingleEntry1
0x140072d47  nop     dword ptr [rax+rax+00h]
0x140072d4c  mov     cs:WdLogGlobalForLineNumber, 3E1h
0x140072d56  lea     r9, aDxgprocessCrea; "DXGPROCESS::CreateDxgProcess failed: : "...
0x140072d5d  jmp     loc_140072EAA
0x140072d62  mov     rcx, [rsp+0E8h+var_98]
0x140072d67  mov     eax, [rcx+198h]
0x140072d6d  bt      eax, 8
0x140072d71  jnb     short loc_140072D7C
0x140072d73  mov     r14, [rcx+258h]
0x140072d7a  jmp     short loc_140072D86
0x140072d7c  and     al, 80h
0x140072d7e  neg     al
0x140072d80  sbb     r14, r14
0x140072d83  and     r14, rcx
0x140072d86  mov     [rsp+0E8h+var_B8], rdi; struct DXGVIRTUALMACHINE *
0x140072d8b  mov     [rsp+0E8h+var_C0], dil; unsigned __int8
0x140072d90  mov     [rsp+0E8h+var_C8], rdi; struct _EPROCESS *
0x140072d95  xor     r9d, r9d; struct _EPROCESS *
0x140072d98  xor     r8d, r8d; struct DXGPROCESS *
0x140072d9b  xor     edx, edx; void *
0x140072d9d  mov     rcx, r14; this
0x140072da0  call    ?InitializeVmwpProcess@DXGPROCESSVMWP@@QEAAJPEAXPEAVDXGPROCESS@@PEAU_EPROCESS@@2EPEAVDXGVIRTUALMACHINE@@@Z; DXGPROCESSVMWP::InitializeVmwpProcess(void *,DXGPROCESS *,_EPROCESS *,_EPROCESS *,uchar,DXGVIRTUALMACHINE *)
0x140072da5  movsxd  rsi, eax
0x140072da8  test    eax, eax
0x140072daa  jns     short loc_140072DD4
0x140072dac  mov     rdx, rsi
0x140072daf  mov     ecx, r12d
0x140072db2  call    cs:__imp_WdLogSingleEntry1
0x140072db9  nop     dword ptr [rax+rax+00h]
0x140072dbe  mov     cs:WdLogGlobalForLineNumber, 3EBh
0x140072dc8  lea     r9, aDxgprocessInit; "DXGPROCESS::InitializeVmwpProcess faile"...
0x140072dcf  jmp     loc_140072EAA
0x140072dd4  mov     rax, [r14+258h]
0x140072ddb  mov     [rsp+0E8h+var_98], rax
0x140072de0  mov     r8b, 1; unsigned __int8
0x140072de3  xor     edx, edx; void *
0x140072de5  mov     rcx, rax; this
0x140072de8  call    ?InitializeVirtualMachine@DXGVIRTUALMACHINE@@QEAAJPEAXE@Z; DXGVIRTUALMACHINE::InitializeVirtualMachine(void *,uchar)
0x140072ded  movsxd  rsi, eax
0x140072df0  test    eax, eax
0x140072df2  jns     short loc_140072E40
0x140072df4  mov     rdx, rsi
0x140072df7  mov     ecx, r12d
0x140072dfa  call    cs:__imp_WdLogSingleEntry1
0x140072e01  nop     dword ptr [rax+rax+00h]
0x140072e06  mov     cs:WdLogGlobalForLineNumber, 3F5h
0x140072e10  mov     [rsp+0E8h+var_A8], rdi
0x140072e15  mov     [rsp+0E8h+var_B0], rdi
0x140072e1a  mov     [rsp+0E8h+var_B8], rdi
0x140072e1f  mov     qword ptr [rsp+0E8h+var_C0], rdi
0x140072e24  mov     [rsp+0E8h+var_C8], rsi
0x140072e29  lea     r9, aFailedToInital_0; "Failed to initalize virtual machine : 0"...
0x140072e30  or      r8d, 0FFFFFFFFh
0x140072e34  mov     edx, 40000h
0x140072e39  xor     ecx, ecx
0x140072e3b  call    DxgkLogInternalTriageEvent
0x140072e40  lea     rdx, [rsp+0E8h+var_50]; struct _GUID *
0x140072e48  mov     rcx, [rsp+0E8h+var_98]; this
0x140072e4d  call    ?SetVmGuid@DXGVIRTUALMACHINE@@QEAAXPEBU_GUID@@@Z; DXGVIRTUALMACHINE::SetVmGuid(_GUID const *)
0x140072e52  jmp     short loc_140072ED3
0x140072e54  mov     edx, [rax+198h]
0x140072e5a  mov     eax, edx
0x140072e5c  shr     eax, 7
0x140072e5f  test    al, 1
0x140072e61  jz      short loc_140072E80
0x140072e63  bt      edx, 8
0x140072e67  jnb     short loc_140072E72
0x140072e69  mov     r14, [rcx+258h]
0x140072e70  jmp     short loc_140072E7C
0x140072e72  and     al, 1
0x140072e74  neg     al
0x140072e76  sbb     r14, r14
0x140072e79  and     r14, rcx
0x140072e7c  mov     esi, edi
0x140072e7e  jmp     short loc_140072EE3
0x140072e80  mov     rsi, 0FFFFFFFFC000000Dh
0x140072e87  mov     rdx, rsi
0x140072e8a  mov     ecx, r12d
0x140072e8d  call    cs:__imp_WdLogSingleEntry1
0x140072e94  nop     dword ptr [rax+rax+00h]
0x140072e99  mov     cs:WdLogGlobalForLineNumber, 404h
0x140072ea3  lea     r9, aProcessIsBelon; "Process is belonging to VM group, but n"...
0x140072eaa  mov     [rsp+0E8h+var_A8], rdi
0x140072eaf  mov     [rsp+0E8h+var_B0], rdi
0x140072eb4  mov     [rsp+0E8h+var_B8], rdi
0x140072eb9  mov     qword ptr [rsp+0E8h+var_C0], rdi
0x140072ebe  mov     [rsp+0E8h+var_C8], rsi
0x140072ec3  or      r8d, 0FFFFFFFFh
0x140072ec7  mov     edx, 40000h
0x140072ecc  xor     ecx, ecx
0x140072ece  call    DxgkLogInternalTriageEvent
0x140072ed3  mov     rbx, rdi
0x140072ed6  mov     [rsp+0E8h+var_98], rbx
0x140072edb  test    esi, esi
0x140072edd  js      loc_140073012
0x140072ee3  mov     rdx, [r14+258h]
0x140072eea  add     rdx, 40h ; '@'; struct DXGPUSHLOCK *
0x140072eee  lea     rcx, [rsp+0E8h+var_68]; this
0x140072ef6  call    ??0DXGAUTOPUSHLOCKEXCLUSIVE@@QEAA@QEAVDXGPUSHLOCK@@@Z; DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(DXGPUSHLOCK * const)
0x140072efb  mov     rcx, [r14+258h]; this
0x140072f02  call    ?ReferenceVailObject@DXGVIRTUALMACHINE@@QEAAPEAVDXGVAILOBJECT@@XZ; DXGVIRTUALMACHINE::ReferenceVailObject(void)
0x140072f07  mov     rbx, rax
0x140072f0a  mov     [rsp+0E8h+var_98], rax
0x140072f0f  test    rax, rax
0x140072f12  jnz     short loc_140072F6A
0x140072f14  mov     r14, 0FFFFFFFFC0000225h
0x140072f1b  mov     esi, r14d
0x140072f1e  mov     rdx, r14
0x140072f21  lea     ecx, [rax+1]
0x140072f24  call    cs:__imp_WdLogSingleEntry1
0x140072f2b  nop     dword ptr [rax+rax+00h]
0x140072f30  mov     cs:WdLogGlobalForLineNumber, 410h
0x140072f3a  mov     [rsp+0E8h+var_A8], rdi
0x140072f3f  mov     [rsp+0E8h+var_B0], rdi
0x140072f44  mov     [rsp+0E8h+var_B8], rdi
0x140072f49  mov     qword ptr [rsp+0E8h+var_C0], rdi
0x140072f4e  mov     [rsp+0E8h+var_C8], r14
0x140072f53  lea     r9, aFailedToFindVa; "Failed to find Vail object: 0xI64x"
0x140072f5a  or      r8d, 0FFFFFFFFh
0x140072f5e  mov     edx, 40002h
0x140072f63  xor     ecx, ecx
0x140072f65  call    DxgkLogInternalTriageEvent
0x140072f6a  lea     rcx, [rsp+0E8h+var_68]; this
0x140072f72  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x140072f77  test    esi, esi
0x140072f79  js      loc_140073012
0x140072f7f  lea     rax, [rsp+0E8h+Src]
0x140072f84  mov     [rsp+0E8h+var_C8], rax; void **
0x140072f89  mov     r9b, 1; char
0x140072f8c  mov     edx, 0C0060000h; unsigned int
0x140072f91  mov     rcx, rbx; this
0x140072f94  call    ?CreateHandle@DxgkCompositionObject@@QEBAJK_NDPEAPEAX@Z; DxgkCompositionObject::CreateHandle(ulong,bool,char,void * *)
0x140072f99  movsxd  rsi, eax
0x140072f9c  test    eax, eax
0x140072f9e  jns     short loc_140072FC0
0x140072fa0  mov     rdx, rsi
0x140072fa3  mov     ecx, 3
0x140072fa8  call    cs:__imp_WdLogSingleEntry1
0x140072faf  nop     dword ptr [rax+rax+00h]
0x140072fb4  mov     cs:WdLogGlobalForLineNumber, 41Ch
0x140072fbe  jmp     short loc_140072FC8
0x140072fc0  mov     [rsp+0E8h+var_90], 8
0x140072fc8  test    esi, esi
0x140072fca  js      short loc_140073012
0x140072fcc  mov     r8d, 8; Size
0x140072fd2  lea     rdx, [rsp+0E8h+Src]; Src
0x140072fd7  mov     rcx, [rsp+0E8h+var_80]; void *
0x140072fdc  call    RtlCopyToUser
0x140072fe1  jmp     short loc_140073012
0x140072fe3  mov     rdx, [rsp+0E8h+var_78]
0x140072fe8  mov     ecx, 3
0x140072fed  call    cs:__imp_WdLogSingleEntry1
0x140072ff4  nop     dword ptr [rax+rax+00h]
0x140072ff9  mov     cs:WdLogGlobalForLineNumber, 42Ch
0x140073003  mov     esi, 0C000000Dh
0x140073008  mov     rbx, [rsp+0E8h+var_98]
0x14007300d  mov     r15, [rsp+0E8h+var_70]
0x140073012  test    rbx, rbx
0x140073015  jz      short loc_140073026
0x140073017  mov     rcx, rbx; Object
0x14007301a  call    cs:__imp_ObfDereferenceObject
0x140073021  nop     dword ptr [rax+rax+00h]
0x140073026  mov     eax, [rsp+0E8h+var_90]
0x14007302a  mov     [r15+38h], rax
0x14007302e  mov     [r15+30h], esi
0x140073032  xor     edx, edx; PriorityBoost
0x140073034  mov     rcx, r15; Irp
0x140073037  call    cs:__imp_IofCompleteRequest
0x14007303e  nop     dword ptr [rax+rax+00h]
0x140073043  mov     eax, esi
0x140073045  mov     rcx, [rsp+0E8h+var_40]
0x14007304d  xor     rcx, rsp; StackCookie
0x140073050  call    __security_check_cookie
0x140073055  add     rsp, 0B8h
0x14007305c  pop     r15
0x14007305e  pop     r14
0x140073060  pop     r12
  ... truncated ...
```
