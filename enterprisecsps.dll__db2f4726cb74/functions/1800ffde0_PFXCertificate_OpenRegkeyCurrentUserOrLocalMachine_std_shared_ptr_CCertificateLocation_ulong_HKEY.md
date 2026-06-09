# PFXCertificate::OpenRegkeyCurrentUserOrLocalMachine(std::shared_ptr<CCertificateLocation>,ulong,HKEY__ * *)

- ea: `0x1800ffde0`
- end: `0x1800ffefb`
- name: `?OpenRegkeyCurrentUserOrLocalMachine@PFXCertificate@@KAJV?$shared_ptr@VCCertificateLocation@@@std@@KPEAPEAUHKEY__@@@Z`
- size: `283`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800fdc8c`
- `0x1800fe538`
- `0x1800fe7f8`
- `0x1800fee04`
- `0x1800fff04`

## callees

- `0x180015804`
- `0x180019fbc`
- `0x1800230c4`
- `0x1800232fc`
- `0x18002344c`
- `0x18002aed0`
- `0x1800ffde0`
- `0x180107010`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800ffe9f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800ffe9f`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800ffe41`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800ffe41`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ffecd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ffecd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PFXCertificate::OpenRegkeyCurrentUserOrLocalMachine(_QWORD *a1, REGSAM a2, HKEY *a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  char IsStateSeparationEnabled; // al
  unsigned int v10; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-38h]
  unsigned int phkResulta; // [rsp+20h] [rbp-38h]
  _BYTE v13[16]; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v14[24]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 24LL))(*a1) != 0x10000 )
  {
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
    v10 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            (LPCWSTR)((unsigned __int64)L"OSData\\" & -(__int64)(IsStateSeparationEnabled != 0)),
            0,
            a2,
            a3);
    if ( v10 )
    {
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x2F,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\certificatecore\\pfxcertificate.cpp",
             (const char *)v10,
             phkResulta);
      goto LABEL_6;
    }
    goto LABEL_5;
  }
  std::_Ptr_base<CCertificateStore>::_Ptr_base<CCertificateStore>(v13);
  std::_Ptr_base<Dynamo::ISettingsPackProcessor>::_Copy_construct_from<Dynamo::ISettingsPackProcessor>(v13, a1);
  AutoDmImpersonate::AutoDmImpersonate(v14, v13);
  v6 = RegOpenCurrentUser(a2, a3);
  if ( !v6 )
  {
    AutoDmImpersonate::~AutoDmImpersonate((AutoDmImpersonate *)v14);
LABEL_5:
    v7 = 0;
    goto LABEL_6;
  }
  v7 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x2B,
         (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\certificatecore\\pfxcertificate.cpp",
         (const char *)v6,
         phkResult);
  AutoDmImpersonate::~AutoDmImpersonate((AutoDmImpersonate *)v14);
LABEL_6:
  std::_Ptr_base<Dynamo::SyncmlPackProcessor>::_Decref(a1);
  return v7;
}

```

## disassembly

```asm
0x1800ffde0  mov     [rsp+arg_8], rbx
0x1800ffde5  mov     [rsp+arg_10], rsi
0x1800ffdea  mov     [rsp+arg_0], rcx
0x1800ffdef  push    rdi
0x1800ffdf0  sub     rsp, 50h
0x1800ffdf4  mov     rbx, r8
0x1800ffdf7  mov     esi, edx
0x1800ffdf9  mov     rdi, rcx
0x1800ffdfc  mov     rcx, [rcx]
0x1800ffdff  mov     rax, [rcx]
0x1800ffe02  mov     rax, [rax+18h]
0x1800ffe06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffe0b  cmp     eax, 10000h
0x1800ffe10  jnz     loc_1800FFE9F
0x1800ffe16  lea     rcx, [rsp+58h+var_28]
0x1800ffe1b  call    ??0?$_Ptr_base@VCCertificateStore@@@std@@IEAA@XZ; std::_Ptr_base<CCertificateStore>::_Ptr_base<CCertificateStore>(void)
0x1800ffe20  mov     rdx, rdi
0x1800ffe23  lea     rcx, [rsp+58h+var_28]
0x1800ffe28  call    ??$_Copy_construct_from@VISettingsPackProcessor@Dynamo@@@?$_Ptr_base@VISettingsPackProcessor@Dynamo@@@std@@IEAAXAEBV?$shared_ptr@VISettingsPackProcessor@Dynamo@@@1@@Z; std::_Ptr_base<Dynamo::ISettingsPackProcessor>::_Copy_construct_from<Dynamo::ISettingsPackProcessor>(std::shared_ptr<Dynamo::ISettingsPackProcessor> const &)
0x1800ffe2d  lea     rdx, [rsp+58h+var_28]
0x1800ffe32  lea     rcx, [rsp+58h+var_18]
0x1800ffe37  call    ??0AutoDmImpersonate@@QEAA@V?$shared_ptr@VCCertificateLocation@@@std@@@Z; AutoDmImpersonate::AutoDmImpersonate(std::shared_ptr<CCertificateLocation>)
0x1800ffe3c  mov     rdx, rbx; phkResult
0x1800ffe3f  mov     ecx, esi; samDesired
0x1800ffe41  call    cs:__imp_RegOpenCurrentUser
0x1800ffe48  nop     dword ptr [rax+rax+00h]
0x1800ffe4d  test    eax, eax
0x1800ffe4f  jz      short loc_1800FFE78
0x1800ffe51  mov     rcx, [rsp+58h]; this
0x1800ffe56  mov     r9d, eax; char *
0x1800ffe59  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800ffe60  mov     edx, 2Bh ; '+'; void *
0x1800ffe65  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800ffe6a  mov     ebx, eax
0x1800ffe6c  lea     rcx, [rsp+58h+var_18]; this
0x1800ffe71  call    ??1AutoDmImpersonate@@QEAA@XZ; AutoDmImpersonate::~AutoDmImpersonate(void)
0x1800ffe76  jmp     short loc_1800FFE84
0x1800ffe78  lea     rcx, [rsp+58h+var_18]; this
0x1800ffe7d  call    ??1AutoDmImpersonate@@QEAA@XZ; AutoDmImpersonate::~AutoDmImpersonate(void)
0x1800ffe82  xor     ebx, ebx
0x1800ffe84  mov     rcx, rdi
0x1800ffe87  call    ?_Decref@?$_Ptr_base@VSyncmlPackProcessor@Dynamo@@@std@@IEAAXXZ; std::_Ptr_base<Dynamo::SyncmlPackProcessor>::_Decref(void)
0x1800ffe8c  mov     eax, ebx
0x1800ffe8e  mov     rbx, [rsp+58h+arg_8]
0x1800ffe93  mov     rsi, [rsp+58h+arg_10]
0x1800ffe98  add     rsp, 50h
0x1800ffe9c  pop     rdi
0x1800ffe9d  retn
0x1800ffe9f  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800ffea6  nop     dword ptr [rax+rax+00h]
0x1800ffeab  nop
0x1800ffeac  lea     rcx, aOsdata_1; "OSData\\"
0x1800ffeb3  neg     al
0x1800ffeb5  sbb     rdx, rdx
0x1800ffeb8  and     rdx, rcx; lpSubKey
0x1800ffebb  mov     qword ptr [rsp+58h+phkResult], rbx; unsigned int
0x1800ffec0  mov     r9d, esi; samDesired
0x1800ffec3  xor     r8d, r8d; ulOptions
0x1800ffec6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ffecd  call    cs:__imp_RegOpenKeyExW
0x1800ffed4  nop     dword ptr [rax+rax+00h]
0x1800ffed9  test    eax, eax
0x1800ffedb  jz      short loc_1800FFE82
0x1800ffedd  mov     rcx, [rsp+58h]; this
0x1800ffee2  mov     r9d, eax; char *
0x1800ffee5  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800ffeec  mov     edx, 2Fh ; '/'; void *
0x1800ffef1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800ffef6  mov     ebx, eax
0x1800ffef8  jmp     short loc_1800FFE84
```
