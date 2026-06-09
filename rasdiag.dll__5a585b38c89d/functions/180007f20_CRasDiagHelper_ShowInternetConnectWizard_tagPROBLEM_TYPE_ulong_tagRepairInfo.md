# CRasDiagHelper::ShowInternetConnectWizard(tagPROBLEM_TYPE,ulong *,tagRepairInfo * *)

- ea: `0x180007f20`
- end: `0x18000807e`
- name: `?ShowInternetConnectWizard@CRasDiagHelper@@AEAAJW4tagPROBLEM_TYPE@@PEAKPEAPEAUtagRepairInfo@@@Z`
- size: `350`
- prototype: `__int64 __fastcall(CRasDiagHelper *this, __int64, unsigned int *, struct tagRepairInfo **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006fa0`

## callees

- `0x180007f20`
- `0x18000b864`
- `0x18000b928`
- `0x18000cf64`
- `0x18000dd64`

## string_xrefs

- `0x180008040`: `BuildRepairInfos failed with error: 0x%x.`
- `0x180007ffa`: `rundll32.exe`
- `0x180008014`: `xwizards.dll,RunWizard /u /taerosmallfixed {7071ECA0-663B-4BC1-A1FA-B97F3B917C55} /z`

## pseudocode

```c
__int64 __fastcall CRasDiagHelper::ShowInternetConnectWizard(
        CRasDiagHelper *this,
        __int64 a2,
        unsigned int *a3,
        struct tagRepairInfo **a4)
{
  enum tagPROBLEM_TYPE v6; // ebx
  int v8; // ebx
  unsigned int v9; // esi
  __int64 v10; // rcx
  __int64 v11; // rdx
  struct tagRepairInfo *v12; // r15
  unsigned __int64 v13; // rbp
  __int64 v14; // rdx
  __int64 v15; // rdx
  unsigned int v17; // [rsp+20h] [rbp-58h]
  unsigned int *v18; // [rsp+28h] [rbp-50h]

  v6 = (int)a2;
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, 0, a4);
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
  if ( !a3 || !a4 )
  {
    v8 = -2147024809;
    goto LABEL_16;
  }
  v8 = BuildRepairInfos(
         1u,
         (const struct tagRepairInfoMap *)&CRasDiagHelper::m_repairInfos,
         v6,
         (struct _GUID *)&ID_RAS_LOWH_REPAIR_NO_INTERNET_CONNECTIVITY,
         v17,
         a3,
         a4,
         0);
  if ( v8 < 0 )
  {
LABEL_16:
    LODWORD(v18) = v8;
    CRasLogger::Log(
      (_QWORD *)this + 151,
      2u,
      1u,
      (__int64)L"CRasDiagHelper",
      L"BuildRepairInfos failed with error: 0x%x.",
      v18);
    return (unsigned int)v8;
  }
  v9 = 0;
  if ( *a3 )
  {
    v10 = *(_QWORD *)ID_RAS_LOWH_REPAIR_NO_INTERNET_CONNECTIVITY.Data4;
    v11 = *(_QWORD *)&ID_RAS_LOWH_REPAIR_NO_INTERNET_CONNECTIVITY.Data1;
    do
    {
      v12 = *a4;
      v13 = 112LL * v9;
      if ( v11 == *(_QWORD *)&(*a4)[v13 / 0x70].guid.Data1 && v10 == *(_QWORD *)v12[v13 / 0x70].guid.Data4 )
      {
        v12[v13 / 0x70].UiInfo.type = UIT_SHELL_COMMAND;
        AssembleStringsWithAlloc(&(&v12->UiInfo.pwzNull)[v13 / 8], v11, L"open", (unsigned __int16 *)&qword_1800132F0);
        AssembleStringsWithAlloc(
          (unsigned __int16 **)((char *)&v12->UiInfo.pwzDui + v13 + 8),
          v14,
          L"rundll32.exe",
          (unsigned __int16 *)&qword_1800132F0);
        AssembleStringsWithAlloc(
          &(&v12->UiInfo.pwzDui)[v13 / 8 + 1],
          v15,
          L"xwizards.dll,RunWizard /u /taerosmallfixed {7071ECA0-663B-4BC1-A1FA-B97F3B917C55} /z",
          (unsigned __int16 *)&qword_1800132F0);
        v10 = *(_QWORD *)ID_RAS_LOWH_REPAIR_NO_INTERNET_CONNECTIVITY.Data4;
        v11 = *(_QWORD *)&ID_RAS_LOWH_REPAIR_NO_INTERNET_CONNECTIVITY.Data1;
      }
      ++v9;
    }
    while ( v9 < *a3 );
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180007f20  push    rbx
0x180007f22  push    rbp
0x180007f23  push    rsi
0x180007f24  push    rdi
0x180007f25  push    r12
0x180007f27  push    r14
0x180007f29  push    r15
0x180007f2b  sub     rsp, 40h
0x180007f2f  mov     r14, r9
0x180007f32  mov     rdi, r8
0x180007f35  mov     ebx, edx
0x180007f37  mov     rsi, rcx
0x180007f3a  test    r8, r8
0x180007f3d  jnz     short loc_180007F44
0x180007f3f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007f44  test    r14, r14
0x180007f47  jnz     short loc_180007F4E
0x180007f49  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007f4e  mov     r12d, 1
0x180007f54  test    rdi, rdi
0x180007f57  jz      loc_18000803B
0x180007f5d  test    r14, r14
0x180007f60  jz      loc_18000803B
0x180007f66  mov     [rsp+78h+var_40], 0; int
0x180007f6e  lea     r9, ID_RAS_LOWH_REPAIR_NO_INTERNET_CONNECTIVITY; struct _GUID *
0x180007f75  mov     [rsp+78h+var_48], r14; struct tagRepairInfo **
0x180007f7a  lea     rdx, ?m_repairInfos@CRasDiagHelper@@0QBUtagRepairInfoMap@@B; struct tagRepairInfoMap *
0x180007f81  mov     r8d, ebx; enum tagPROBLEM_TYPE
0x180007f84  mov     [rsp+78h+var_50], rdi; unsigned int *
0x180007f89  mov     ecx, r12d; unsigned int
0x180007f8c  call    ?BuildRepairInfos@@YAJKPEBUtagRepairInfoMap@@W4tagPROBLEM_TYPE@@PEAU_GUID@@KPEAKPEAPEAUtagRepairInfo@@H@Z; BuildRepairInfos(ulong,tagRepairInfoMap const *,tagPROBLEM_TYPE,_GUID *,ulong,ulong *,tagRepairInfo * *,int)
0x180007f91  mov     ebx, eax
0x180007f93  test    eax, eax
0x180007f95  js      loc_180008040
0x180007f9b  xor     esi, esi
0x180007f9d  cmp     [rdi], esi
0x180007f9f  jbe     loc_18000806C
0x180007fa5  mov     rcx, qword ptr cs:ID_RAS_LOWH_REPAIR_NO_INTERNET_CONNECTIVITY.Data4
0x180007fac  mov     rdx, qword ptr cs:ID_RAS_LOWH_REPAIR_NO_INTERNET_CONNECTIVITY.Data1; unsigned int
0x180007fb3  mov     r15, [r14]
0x180007fb6  mov     eax, esi
0x180007fb8  imul    rbp, rax, 70h ; 'p'
0x180007fbc  cmp     rdx, [r15+rbp]
0x180007fc0  jnz     short loc_18000802E
0x180007fc2  cmp     rcx, [r15+rbp+8]
0x180007fc7  jnz     short loc_18000802E
0x180007fc9  lea     rcx, [r15+40h]
0x180007fcd  mov     dword ptr [r15+rbp+38h], 2
0x180007fd6  add     rcx, rbp; unsigned __int16 **
0x180007fd9  lea     r9, qword_1800132F0; unsigned __int16 *
0x180007fe0  lea     r8, aOpen; "open"
0x180007fe7  call    ?AssembleStringsWithAlloc@@YAJPEAPEAGIPEBG11@Z; AssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,ushort const *)
0x180007fec  lea     rcx, [r15+48h]
0x180007ff0  add     rcx, rbp; unsigned __int16 **
0x180007ff3  lea     r9, qword_1800132F0; unsigned __int16 *
0x180007ffa  lea     r8, aRundll32Exe; "rundll32.exe"
0x180008001  call    ?AssembleStringsWithAlloc@@YAJPEAPEAGIPEBG11@Z; AssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,ushort const *)
0x180008006  lea     rcx, [r15+50h]
0x18000800a  add     rcx, rbp; unsigned __int16 **
0x18000800d  lea     r9, qword_1800132F0; unsigned __int16 *
0x180008014  lea     r8, aXwizardsDllRun; "xwizards.dll,RunWizard /u /taerosmallfi"...
0x18000801b  call    ?AssembleStringsWithAlloc@@YAJPEAPEAGIPEBG11@Z; AssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,ushort const *)
0x180008020  mov     rcx, qword ptr cs:ID_RAS_LOWH_REPAIR_NO_INTERNET_CONNECTIVITY.Data4
0x180008027  mov     rdx, qword ptr cs:ID_RAS_LOWH_REPAIR_NO_INTERNET_CONNECTIVITY.Data1
0x18000802e  add     esi, r12d
0x180008031  cmp     esi, [rdi]
0x180008033  jb      loc_180007FB3
0x180008039  jmp     short loc_18000806C
0x18000803b  mov     ebx, 80070057h
0x180008040  lea     rax, aBuildrepairinf; "BuildRepairInfos failed with error: 0x%"...
0x180008047  mov     dword ptr [rsp+78h+var_50], ebx
0x18000804b  lea     rcx, [rsi+4B8h]
0x180008052  movsx   r8d, r12w
0x180008056  lea     r9, aCrasdiaghelper; "CRasDiagHelper"
0x18000805d  mov     [rsp+78h+var_58], rax
0x180008062  mov     edx, 2
0x180008067  call    ?Log@CRasLogger@@QEAAJW4tagNDFEventChannel@@FPEBG1ZZ; CRasLogger::Log(tagNDFEventChannel,short,ushort const *,ushort const *,...)
0x18000806c  mov     eax, ebx
0x18000806e  add     rsp, 40h
0x180008072  pop     r15
0x180008074  pop     r14
0x180008076  pop     r12
0x180008078  pop     rdi
0x180008079  pop     rsi
0x18000807a  pop     rbp
0x18000807b  pop     rbx
0x18000807c  retn
```
