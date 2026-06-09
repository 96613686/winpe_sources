# LanIDsMgr::ManageLLDPDriver(bool)

- ea: `0x18001003c`
- end: `0x1800102b4`
- name: `?ManageLLDPDriver@LanIDsMgr@@AEAAX_N@Z`
- size: `632`
- prototype: `void __fastcall(LanIDsMgr *__hidden this, bool)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, service_task`

## callers

- `0x18000f688`
- `0x1800fee54`

## callees

- `0x18000fab0`
- `0x18001003c`
- `0x180010968`
- `0x1800111cc`
- `0x180032758`
- `0x18005f308`
- `0x1800a88a0`
- `0x1800a8d70`
- `0x1800a8dac`
- `0x1800fd7c4`
- `0x1800fe3f8`
- `0x1800feb40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001007f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001007f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800100ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800100ea`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001026f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001026f`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180010265`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180010265`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LanIDsMgr::ManageLLDPDriver(LanIDsMgr *this, unsigned __int8 a2, __int64 a3)
{
  char v5; // bp
  PVOID *v6; // rcx
  __int64 v7; // r9
  LanIDsMgr *v8; // rcx
  __int64 v9; // rcx
  void *v10; // rbx
  LldpSvc *v11; // [rsp+20h] [rbp-58h]
  _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-50h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_l(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, a3, a2);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( a2 || !LanIDsMgr::ShouldStartLLDP(this) )
  {
    v5 = 0;
    if ( a2 && *((_QWORD *)this + 12) )
    {
      v9 = *((_QWORD *)this + 13);
      if ( v9 )
      {
        LldpSvc::Operation(v9, 2);
        v10 = (void *)*((_QWORD *)this + 13);
        if ( v10 )
        {
          LldpSvc::~LldpSvc(*((LldpSvc **)this + 13));
          operator delete(v10);
        }
        *((_QWORD *)this + 13) = 0;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_a7d930b269293553628841c7763b54c1_Traceguids);
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      ControlService(*((SC_HANDLE *)this + 12), 1u, &ServiceStatus);
      CloseServiceHandle(*((SC_HANDLE *)this + 12));
      *((_QWORD *)this + 12) = 0;
    }
    goto LABEL_5;
  }
  v5 = 1;
  v7 = *((_QWORD *)this + 12);
  if ( !v7 )
  {
    v8 = (LanIDsMgr *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_a7d930b269293553628841c7763b54c1_Traceguids);
    *((_QWORD *)this + 12) = LanIDsMgr::StartKernelDriver(v8);
    goto LABEL_5;
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_a7d930b269293553628841c7763b54c1_Traceguids, v7);
LABEL_5:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*((_QWORD *)this + 12) )
    goto LABEL_7;
  if ( !*((_QWORD *)this + 13) )
  {
    v11 = (LldpSvc *)operator new(8u);
    *(_QWORD *)v11 = -1;
    LldpSvc::OpenLldpDriver(v11);
    *((_QWORD *)this + 13) = v11;
    v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_7:
    if ( !*((_QWORD *)this + 13) )
      goto LABEL_8;
  }
  if ( v5 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
      WPP_SF_(v6[2], 59, &WPP_a7d930b269293553628841c7763b54c1_Traceguids);
    LldpSvc::Operation(*((_QWORD *)this + 13), 1);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_8:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
    WPP_SF_(v6[2], 60, &WPP_a7d930b269293553628841c7763b54c1_Traceguids);
  if ( this != (LanIDsMgr *)-8LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18001003c  mov     [rsp+arg_10], rbx
0x180010041  push    rbp
0x180010042  push    rsi
0x180010043  push    rdi
0x180010044  push    r12
0x180010046  push    r13
0x180010048  sub     rsp, 50h
0x18001004c  mov     rax, cs:__security_cookie
0x180010053  xor     rax, rsp
0x180010056  mov     [rsp+78h+var_30], rax
0x18001005b  movzx   ebx, dl
0x18001005e  mov     rdi, rcx
0x180010061  lea     r12, WPP_GLOBAL_Control
0x180010068  mov     rcx, cs:WPP_GLOBAL_Control
0x18001006f  cmp     rcx, r12
0x180010072  jnz     loc_180010111
0x180010078  lea     rsi, [rdi+8]
0x18001007c  mov     rcx, rsi; lpCriticalSection
0x18001007f  call    cs:__imp_EnterCriticalSection
0x180010085  mov     [rsp+78h+var_58], rsi
0x18001008a  lea     r13, WPP_a7d930b269293553628841c7763b54c1_Traceguids
0x180010091  test    bl, bl
0x180010093  jnz     short loc_1800100A5
0x180010095  mov     rcx, rdi; this
0x180010098  call    ?ShouldStartLLDP@LanIDsMgr@@QEAA_NXZ; LanIDsMgr::ShouldStartLLDP(void)
0x18001009d  test    al, al
0x18001009f  jnz     loc_180010177
0x1800100a5  xor     bpl, bpl
0x1800100a8  test    bl, bl
0x1800100aa  jnz     loc_1800101E3
0x1800100b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100b7  cmp     qword ptr [rdi+60h], 0
0x1800100bc  jnz     short loc_180010131
0x1800100be  cmp     qword ptr [rdi+68h], 0
0x1800100c3  jnz     short loc_18001013C
0x1800100c5  cmp     rcx, r12
0x1800100c8  jz      short loc_1800100E2
0x1800100ca  test    byte ptr [rcx+1Ch], 4
0x1800100ce  jz      short loc_1800100E2
0x1800100d0  mov     edx, 3Ch ; '<'
0x1800100d5  mov     r8, r13
0x1800100d8  mov     rcx, [rcx+10h]
0x1800100dc  call    WPP_SF_
0x1800100e1  nop
0x1800100e2  test    rsi, rsi
0x1800100e5  jz      short loc_1800100F0
0x1800100e7  mov     rcx, rsi; lpCriticalSection
0x1800100ea  call    cs:__imp_LeaveCriticalSection
0x1800100f0  mov     rcx, [rsp+78h+var_30]
0x1800100f5  xor     rcx, rsp; StackCookie
0x1800100f8  call    __security_check_cookie
0x1800100fd  mov     rbx, [rsp+78h+arg_10]
0x180010105  add     rsp, 50h
0x180010109  pop     r13
0x18001010b  pop     r12
0x18001010d  pop     rdi
0x18001010e  pop     rsi
0x18001010f  pop     rbp
0x180010110  retn
0x180010111  test    byte ptr [rcx+1Ch], 4
0x180010115  jz      loc_180010078
0x18001011b  mov     r9d, ebx
0x18001011e  mov     edx, 37h ; '7'
0x180010123  mov     rcx, [rcx+10h]
0x180010127  call    WPP_SF_l
0x18001012c  jmp     loc_180010078
0x180010131  cmp     qword ptr [rdi+68h], 0
0x180010136  jz      loc_180010282
0x18001013c  test    bpl, bpl
0x18001013f  jz      short loc_1800100C5
0x180010141  cmp     rcx, r12
0x180010144  jz      short loc_18001015D
0x180010146  test    byte ptr [rcx+1Ch], 4
0x18001014a  jz      short loc_18001015D
0x18001014c  mov     edx, 3Bh ; ';'
0x180010151  mov     r8, r13
0x180010154  mov     rcx, [rcx+10h]
0x180010158  call    WPP_SF_
0x18001015d  mov     edx, 1
0x180010162  mov     rcx, [rdi+68h]
0x180010166  call    ?Operation@LldpSvc@@QEAAHW4_OperationType@@@Z; LldpSvc::Operation(_OperationType)
0x18001016b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010172  jmp     loc_1800100C5
0x180010177  mov     bpl, 1
0x18001017a  mov     r9, [rdi+60h]
0x18001017e  test    r9, r9
0x180010181  jnz     short loc_1800101B3
0x180010183  mov     rcx, cs:WPP_GLOBAL_Control
0x18001018a  cmp     rcx, r12
0x18001018d  jz      short loc_1800101A5
0x18001018f  test    byte ptr [rcx+1Ch], 4
0x180010193  jz      short loc_1800101A5
0x180010195  lea     edx, [r9+38h]
0x180010199  mov     r8, r13
0x18001019c  mov     rcx, [rcx+10h]
0x1800101a0  call    WPP_SF_
0x1800101a5  call    ?StartKernelDriver@LanIDsMgr@@AEAAPEAUSC_HANDLE__@@XZ; LanIDsMgr::StartKernelDriver(void)
0x1800101aa  mov     [rdi+60h], rax
0x1800101ae  jmp     loc_1800100B0
0x1800101b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101ba  cmp     rcx, r12
0x1800101bd  jz      loc_1800100B7
0x1800101c3  test    byte ptr [rcx+1Ch], 4
0x1800101c7  jz      loc_1800100B7
0x1800101cd  mov     edx, 39h ; '9'
0x1800101d2  mov     r8, r13
0x1800101d5  mov     rcx, [rcx+10h]
0x1800101d9  call    WPP_SF_q
0x1800101de  jmp     loc_1800100B0
0x1800101e3  cmp     qword ptr [rdi+60h], 0
0x1800101e8  jz      loc_1800100B0
0x1800101ee  mov     rcx, [rdi+68h]
0x1800101f2  test    rcx, rcx
0x1800101f5  jz      short loc_180010227
0x1800101f7  mov     edx, 2
0x1800101fc  call    ?Operation@LldpSvc@@QEAAHW4_OperationType@@@Z; LldpSvc::Operation(_OperationType)
0x180010201  mov     rbx, [rdi+68h]
0x180010205  test    rbx, rbx
0x180010208  jz      short loc_18001021F
0x18001020a  mov     rcx, rbx; this
0x18001020d  call    ??1LldpSvc@@QEAA@XZ; LldpSvc::~LldpSvc(void)
0x180010212  mov     edx, 8
0x180010217  mov     rcx, rbx; Block
0x18001021a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001021f  mov     qword ptr [rdi+68h], 0
0x180010227  mov     rcx, cs:WPP_GLOBAL_Control
0x18001022e  cmp     rcx, r12
0x180010231  jz      short loc_18001024A
0x180010233  test    byte ptr [rcx+1Ch], 4
0x180010237  jz      short loc_18001024A
0x180010239  mov     edx, 3Ah ; ':'
0x18001023e  mov     r8, r13
0x180010241  mov     rcx, [rcx+10h]
0x180010245  call    WPP_SF_
0x18001024a  xorps   xmm0, xmm0
0x18001024d  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x180010252  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x180010257  lea     r8, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18001025c  mov     edx, 1; dwControl
0x180010261  mov     rcx, [rdi+60h]; hService
0x180010265  call    cs:__imp_ControlService
0x18001026b  mov     rcx, [rdi+60h]; hSCObject
0x18001026f  call    cs:__imp_CloseServiceHandle
0x180010275  mov     qword ptr [rdi+60h], 0
0x18001027d  jmp     loc_1800100B0
0x180010282  mov     ecx, 8; Size
0x180010287  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001028c  mov     rbx, rax
0x18001028f  mov     [rsp+78h+var_58], rax
0x180010294  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x18001029b  mov     rcx, rax; this
0x18001029e  call    ?OpenLldpDriver@LldpSvc@@AEAA_NXZ; LldpSvc::OpenLldpDriver(void)
0x1800102a3  mov     [rdi+68h], rbx
0x1800102a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102ae  jmp     loc_1800100BE
```
