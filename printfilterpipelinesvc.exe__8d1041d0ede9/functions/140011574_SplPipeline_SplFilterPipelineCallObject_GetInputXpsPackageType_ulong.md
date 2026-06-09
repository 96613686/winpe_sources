# SplPipeline::SplFilterPipelineCallObject::GetInputXpsPackageType(ulong)

- ea: `0x140011574`
- end: `0x140011720`
- name: `?GetInputXpsPackageType@SplFilterPipelineCallObject@SplPipeline@@AEAA?AW4PFPM_XPS_TYPE@@K@Z`
- size: `428`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x140012404`

## callees

- `0x1400086f8`
- `0x140011134`
- `0x140011574`
- `0x140011754`
- `0x1400117e0`
- `0x140013214`
- `0x140016740`
- `0x140016934`
- `0x14004650c`
- `0x14005d3c4`

## import_xrefs

- `KERNEL32!Sleep` at `0x140011639`
- `KERNEL32!Sleep` at `0x140011639`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400115db`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400115db`
- `WINSPOOL!GetJobNamedPropertyValue` at `0x14001161d`
- `WINSPOOL!GetJobNamedPropertyValue` at `0x1400116a3`
- `WINSPOOL!GetJobNamedPropertyValue` at `0x14001161d`
- `WINSPOOL!GetJobNamedPropertyValue` at `0x1400116a3`
- `WINSPOOL!FreePrintPropertyValue` at `0x1400116c8`
- `WINSPOOL!FreePrintPropertyValue` at `0x1400116c8`

## string_xrefs

- `0x1400116b1`: `TYPE_XPS_OPEN`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SplPipeline::SplFilterPipelineCallObject::GetInputXpsPackageType(__int64 a1, unsigned int a2)
{
  void *v4; // rdx
  int ModernPrinterType; // esi
  struct _DRIVER_INFO_8W **v6; // r8
  void *v7; // rdx
  int DriverInfo; // edi
  unsigned int v9; // r8d
  void *v10; // rbx
  unsigned int v11; // ebx
  unsigned int v12; // edi
  unsigned int MaxNumberOfRetries; // esi
  signed int JobNamedPropertyValue; // eax
  int v15; // edx
  const char *v16; // r8
  unsigned int v17; // r9d
  bool v18; // sf
  signed int v19; // eax
  int v20; // edx
  const char *v21; // r8
  unsigned int v22; // r9d
  bool v24; // sf
  wchar_t *String2[2]; // [rsp+20h] [rbp-20h] BYREF
  __int64 v26; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  void *Block; // [rsp+70h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp+40h] BYREF

  *(_OWORD *)String2 = 0;
  v26 = 0;
  v4 = *(void **)(a1 + 80);
  if ( v4 == (void *)-1LL )
    v4 = 0;
  PrnExcept::ImpersonateTokenThroughScope::ImpersonateTokenThroughScope(&TokenHandle, v4);
  ModernPrinterType = 0;
  Block = 0;
  DriverInfo = PrintCore::GetDriverInfo(*(HANDLE *)(a1 + 40), &Block, v6);
  if ( DriverInfo < 0 )
  {
    wil::details::in1diag3::_Log_Hr(retaddr, v7, v9, (const char *)(unsigned int)DriverInfo, (int)String2[0]);
  }
  else
  {
    v10 = Block;
    ModernPrinterType = PrintCore::IppSelection::GetModernPrinterType(*((_QWORD *)Block + 15));
    free(v10);
  }
  v11 = 2;
  if ( ModernPrinterType )
  {
    v12 = 0;
    MaxNumberOfRetries = GetMaxNumberOfRetries();
    if ( !MaxNumberOfRetries )
    {
LABEL_15:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_a2cda53fd4003733db4e66a2523c8202_Traceguids);
      }
      goto LABEL_22;
    }
    while ( 1 )
    {
      JobNamedPropertyValue = GetJobNamedPropertyValue(*(_QWORD *)(a1 + 40), a2, L"Spool File Contents", String2);
      if ( !JobNamedPropertyValue )
        goto LABEL_20;
      if ( JobNamedPropertyValue == 1168 )
      {
        ++v12;
        Sleep(0x14u);
      }
      else
      {
        v18 = JobNamedPropertyValue < 0;
        if ( JobNamedPropertyValue > 0 )
        {
          JobNamedPropertyValue = (unsigned __int16)JobNamedPropertyValue | 0x80070000;
          v18 = JobNamedPropertyValue < 0;
        }
        if ( v18 )
          SplException::RealThrowFromHR((SplException *)(unsigned int)JobNamedPropertyValue, v15, v16, v17);
      }
      if ( v12 >= MaxNumberOfRetries )
        goto LABEL_15;
    }
  }
  v19 = GetJobNamedPropertyValue(*(_QWORD *)(a1 + 40), a2, L"Spool File Contents", String2);
  if ( !v19 )
  {
LABEL_20:
    v11 = wcscmp_0(L"TYPE_XPS_OPEN", String2[1]) == 0;
    FreePrintPropertyValue(String2);
LABEL_22:
    PrnExcept::ImpersonateTokenThroughScope::~ImpersonateTokenThroughScope(&TokenHandle);
    return v11;
  }
  if ( v19 == 1168 )
    goto LABEL_22;
  v24 = v19 < 0;
  if ( v19 > 0 )
  {
    v19 = (unsigned __int16)v19 | 0x80070000;
    v24 = v19 < 0;
  }
  if ( v24 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v19, v20, v21, v22);
  PrnExcept::ImpersonateTokenThroughScope::~ImpersonateTokenThroughScope(&TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x140011574  mov     [rsp-28h+arg_8], rbx
0x140011579  push    rbp
0x14001157a  push    rsi
0x14001157b  push    rdi
0x14001157c  push    r14
0x14001157e  push    r15
0x140011580  mov     rbp, rsp
0x140011583  sub     rsp, 40h
0x140011587  mov     r15d, edx
0x14001158a  mov     r14, rcx
0x14001158d  xorps   xmm0, xmm0
0x140011590  xor     eax, eax
0x140011592  movups  xmmword ptr [rbp+String2], xmm0
0x140011596  mov     [rbp+var_10], rax
0x14001159a  mov     rdx, [rcx+50h]
0x14001159e  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1400115a2  cmovz   rdx, rax; Token
0x1400115a6  lea     rcx, [rbp+TokenHandle]; TokenHandle
0x1400115aa  call    ??0ImpersonateTokenThroughScope@PrnExcept@@QEAA@PEAX@Z; PrnExcept::ImpersonateTokenThroughScope::ImpersonateTokenThroughScope(void *)
0x1400115af  nop
0x1400115b0  xor     esi, esi
0x1400115b2  mov     [rbp+Block], rsi
0x1400115b6  lea     rdx, [rbp+Block]; void *
0x1400115ba  mov     rcx, [r14+28h]; hPrinter
0x1400115be  call    ?GetDriverInfo@PrintCore@@YAJPEAXPEAPEAU_DRIVER_INFO_8W@@@Z; PrintCore::GetDriverInfo(void *,_DRIVER_INFO_8W * *)
0x1400115c3  mov     edi, eax
0x1400115c5  test    eax, eax
0x1400115c7  js      short loc_1400115E1
0x1400115c9  mov     rbx, [rbp+Block]
0x1400115cd  mov     rcx, [rbx+78h]
0x1400115d1  call    ?GetModernPrinterType@IppSelection@PrintCore@@SA?AW4ModernPrinterType@2@PEB_W@Z; PrintCore::IppSelection::GetModernPrinterType(wchar_t const *)
0x1400115d6  mov     esi, eax
0x1400115d8  mov     rcx, rbx; Block
0x1400115db  call    cs:__imp_free
0x1400115e1  mov     rcx, [rbp+28h]; this
0x1400115e5  test    edi, edi
0x1400115e7  jns     short loc_1400115F1
0x1400115e9  mov     r9d, edi; char *
0x1400115ec  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400115f1  mov     ebx, 2
0x1400115f6  test    esi, esi
0x1400115f8  jz      loc_140011691
0x1400115fe  xor     edi, edi
0x140011600  call    ?GetMaxNumberOfRetries@@YAIXZ; GetMaxNumberOfRetries(void)
0x140011605  mov     esi, eax
0x140011607  test    eax, eax
0x140011609  jz      short loc_140011659
0x14001160b  lea     r9, [rbp+String2]
0x14001160f  lea     r8, aSpoolFileConte; "Spool File Contents"
0x140011616  mov     edx, r15d
0x140011619  mov     rcx, [r14+28h]
0x14001161d  call    cs:__imp_GetJobNamedPropertyValue
0x140011623  test    eax, eax
0x140011625  jz      loc_1400116AD
0x14001162b  cmp     eax, 490h
0x140011630  jnz     short loc_140011641
0x140011632  inc     edi
0x140011634  mov     ecx, 14h; dwMilliseconds
0x140011639  call    cs:__imp_Sleep
0x14001163f  jmp     short loc_140011655
0x140011641  test    eax, eax
0x140011643  jle     short loc_14001164F
0x140011645  movzx   eax, ax
0x140011648  or      eax, 80070000h
0x14001164d  test    eax, eax
0x14001164f  js      loc_140011718
0x140011655  cmp     edi, esi
0x140011657  jb      short loc_14001160B
0x140011659  lea     rax, WPP_GLOBAL_Control
0x140011660  mov     rcx, cs:WPP_GLOBAL_Control
0x140011667  cmp     rcx, rax
0x14001166a  jz      short loc_1400116D7
0x14001166c  test    dword ptr [rcx+1Ch], 100h
0x140011673  jz      short loc_1400116D7
0x140011675  cmp     [rcx+19h], bl
0x140011678  jb      short loc_1400116D7
0x14001167a  mov     edx, 17h
0x14001167f  lea     r8, WPP_a2cda53fd4003733db4e66a2523c8202_Traceguids
0x140011686  mov     rcx, [rcx+10h]
0x14001168a  call    WPP_SF_
0x14001168f  jmp     short loc_1400116D7
0x140011691  lea     r9, [rbp+String2]
0x140011695  lea     r8, aSpoolFileConte; "Spool File Contents"
0x14001169c  mov     edx, r15d
0x14001169f  mov     rcx, [r14+28h]
0x1400116a3  call    cs:__imp_GetJobNamedPropertyValue
0x1400116a9  test    eax, eax
0x1400116ab  jnz     short loc_1400116D0
0x1400116ad  mov     rdx, [rbp+String2+8]; String2
0x1400116b1  lea     rcx, aTypeXpsOpen; "TYPE_XPS_OPEN"
0x1400116b8  call    wcscmp_0
0x1400116bd  xor     ebx, ebx
0x1400116bf  test    eax, eax
0x1400116c1  setz    bl
0x1400116c4  lea     rcx, [rbp+String2]
0x1400116c8  call    cs:__imp_FreePrintPropertyValue
0x1400116ce  jmp     short loc_1400116D7
0x1400116d0  cmp     eax, 490h
0x1400116d5  jnz     short loc_1400116E4
0x1400116d7  lea     rcx, [rbp+TokenHandle]; this
0x1400116db  call    ??1ImpersonateTokenThroughScope@PrnExcept@@QEAA@XZ; PrnExcept::ImpersonateTokenThroughScope::~ImpersonateTokenThroughScope(void)
0x1400116e0  mov     eax, ebx
0x1400116e2  jmp     short loc_1400116FF
0x1400116e4  test    eax, eax
0x1400116e6  jle     short loc_1400116F2
0x1400116e8  movzx   eax, ax
0x1400116eb  or      eax, 80070000h
0x1400116f0  test    eax, eax
0x1400116f2  js      short loc_140011710
0x1400116f4  lea     rcx, [rbp+TokenHandle]; this
0x1400116f8  call    ??1ImpersonateTokenThroughScope@PrnExcept@@QEAA@XZ; PrnExcept::ImpersonateTokenThroughScope::~ImpersonateTokenThroughScope(void)
0x1400116fd  xor     eax, eax
0x1400116ff  mov     rbx, [rsp+40h+arg_8]
0x140011704  add     rsp, 40h
0x140011708  pop     r15
0x14001170a  pop     r14
0x14001170c  pop     rdi
0x14001170d  pop     rsi
0x14001170e  pop     rbp
0x14001170f  retn
0x140011710  mov     ecx, eax; this
0x140011712  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140011718  mov     ecx, eax; this
0x14001171a  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
```
