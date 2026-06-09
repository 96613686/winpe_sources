# Migration::SysVolUtil::GetLsaDomainName(FrsStringImpl<ushort,char> &)

- ea: `0x1401fb404`
- end: `0x1401fb5d9`
- name: `?GetLsaDomainName@SysVolUtil@Migration@@SAPEAVFrsStatus@@AEAV?$FrsStringImpl@GD@@@Z`
- size: `469`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1401e7ac0`
- `0x1401f9674`
- `0x1401fc424`
- `0x1401fc690`
- `0x1401fc824`
- `0x140201520`

## callees

- `0x140028eec`
- `0x1401b9494`
- `0x1401be958`
- `0x1401fb404`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401fb473`
- `KERNEL32!GetCurrentThreadId` at `0x1401fb4e3`
- `KERNEL32!GetCurrentThreadId` at `0x1401fb580`
- `KERNEL32!GetCurrentThreadId` at `0x1401fb473`
- `KERNEL32!GetCurrentThreadId` at `0x1401fb4e3`
- `KERNEL32!GetCurrentThreadId` at `0x1401fb580`
- `ntdll!RtlNtStatusToDosError` at `0x1401fb483`
- `ntdll!RtlNtStatusToDosError` at `0x1401fb4f3`
- `ntdll!RtlNtStatusToDosError` at `0x1401fb483`
- `ntdll!RtlNtStatusToDosError` at `0x1401fb4f3`
- `ADVAPI32!LsaClose` at `0x1401fb552`
- `ADVAPI32!LsaClose` at `0x1401fb552`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x1401fb4d1`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x1401fb4d1`
- `ADVAPI32!LsaOpenPolicy` at `0x1401fb453`
- `ADVAPI32!LsaOpenPolicy` at `0x1401fb453`
- `ADVAPI32!LsaFreeMemory` at `0x1401fb56b`
- `ADVAPI32!LsaFreeMemory` at `0x1401fb56b`

## pseudocode

```c
__int64 __fastcall Migration::SysVolUtil::GetLsaDomainName(__int64 a1)
{
  __int64 v1; // rdi
  unsigned int *v2; // rbx
  int v4; // esi
  DWORD v5; // ebx
  ULONG v6; // eax
  __int64 v7; // rcx
  int v8; // esi
  DWORD CurrentThreadId; // ebx
  ULONG v10; // eax
  __int64 v11; // rcx
  DWORD v12; // eax
  __int64 v13; // rcx
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  PVOID PolicyHandle; // [rsp+B8h] [rbp+38h] BYREF
  PVOID Buffer; // [rsp+C0h] [rbp+40h] BYREF

  v1 = 0;
  v2 = 0;
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Buffer = 0;
  FrsStringImpl<unsigned short,char>::SetEmpty(a1);
  v4 = LsaOpenPolicy(0, &ObjectAttributes, 0x801u, &PolicyHandle);
  if ( v4 >= 0
    || (v5 = GetCurrentThreadId(),
        v6 = RtlNtStatusToDosError(v4),
        (v2 = (unsigned int *)FrsStatusList::PushNewError(
                                v7,
                                v6,
                                0,
                                1,
                                "base\\fs\\remotefs\\frs\\src\\ad\\migration.cpp",
                                "Migration::SysVolUtil::GetLsaDomainName",
                                5448,
                                v5,
                                0)) == 0) )
  {
    v8 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
    if ( v8 >= 0
      || (CurrentThreadId = GetCurrentThreadId(),
          v10 = RtlNtStatusToDosError(v8),
          (v2 = (unsigned int *)FrsStatusList::PushNewError(
                                  v11,
                                  v10,
                                  0,
                                  1,
                                  "base\\fs\\remotefs\\frs\\src\\ad\\migration.cpp",
                                  "Migration::SysVolUtil::GetLsaDomainName",
                                  5459,
                                  CurrentThreadId,
                                  0)) == 0) )
    {
      FrsStringImpl<unsigned short,char>::Set(
        a1,
        *((_QWORD *)Buffer + 1),
        (unsigned __int64)*(unsigned __int16 *)Buffer >> 1);
    }
  }
  if ( PolicyHandle )
  {
    LsaClose(PolicyHandle);
    PolicyHandle = 0;
  }
  if ( Buffer )
  {
    LsaFreeMemory(Buffer);
    Buffer = 0;
  }
  if ( v2 )
  {
    v12 = GetCurrentThreadId();
    return FrsStatusList::PushNewError(
             v13,
             v2[1],
             v2[2],
             *v2,
             "base\\fs\\remotefs\\frs\\src\\ad\\migration.cpp",
             "Migration::SysVolUtil::GetLsaDomainName",
             5477,
             v12,
             v2);
  }
  return v1;
}

```

## disassembly

```asm
0x1401fb404  mov     [rsp-28h+arg_0], rbx
0x1401fb409  mov     [rsp-28h+arg_18], rsi
0x1401fb40e  push    rbp
0x1401fb40f  push    rdi
0x1401fb410  push    r12
0x1401fb412  push    r14
0x1401fb414  push    r15
0x1401fb416  mov     rbp, rsp
0x1401fb419  sub     rsp, 80h
0x1401fb420  xorps   xmm0, xmm0
0x1401fb423  xor     edi, edi
0x1401fb425  mov     ebx, edi
0x1401fb427  mov     [rbp+PolicyHandle], rdi
0x1401fb42b  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1401fb42f  mov     [rbp+Buffer], rdi
0x1401fb433  mov     r14, rcx
0x1401fb436  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1401fb43a  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1401fb43e  call    ?SetEmpty@?$FrsStringImpl@GD@@QEAAXXZ; FrsStringImpl<ushort,char>::SetEmpty(void)
0x1401fb443  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x1401fb447  mov     r8d, 801h; DesiredAccess
0x1401fb44d  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x1401fb451  xor     ecx, ecx; SystemName
0x1401fb453  call    cs:__imp_LsaOpenPolicy
0x1401fb45a  nop     dword ptr [rax+rax+00h]
0x1401fb45f  lea     r15, aMigrationSysvo_88; "Migration::SysVolUtil::GetLsaDomainName"
0x1401fb466  mov     esi, eax
0x1401fb468  lea     r12, aBaseFsRemotefs_99; "base\\fs\\remotefs\\frs\\src\\ad\\migra"...
0x1401fb46f  test    eax, eax
0x1401fb471  jns     short loc_1401FB4C4
0x1401fb473  call    cs:__imp_GetCurrentThreadId
0x1401fb47a  nop     dword ptr [rax+rax+00h]
0x1401fb47f  mov     ecx, esi; Status
0x1401fb481  mov     ebx, eax
0x1401fb483  call    cs:__imp_RtlNtStatusToDosError
0x1401fb48a  nop     dword ptr [rax+rax+00h]
0x1401fb48f  mov     [rsp+80h+var_40], rdi
0x1401fb494  lea     r9d, [rdi+1]
0x1401fb498  mov     [rsp+80h+var_48], ebx
0x1401fb49c  xor     r8d, r8d
0x1401fb49f  mov     [rsp+80h+var_50], 1548h
0x1401fb4a7  mov     edx, eax
0x1401fb4a9  mov     [rsp+80h+var_58], r15
0x1401fb4ae  mov     [rsp+80h+var_60], r12
0x1401fb4b3  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401fb4b8  mov     rbx, rax
0x1401fb4bb  test    rax, rax
0x1401fb4be  jnz     loc_1401FB549
0x1401fb4c4  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1401fb4c8  lea     r8, [rbp+Buffer]; Buffer
0x1401fb4cc  mov     edx, 5; InformationClass
0x1401fb4d1  call    cs:__imp_LsaQueryInformationPolicy
0x1401fb4d8  nop     dword ptr [rax+rax+00h]
0x1401fb4dd  mov     esi, eax
0x1401fb4df  test    eax, eax
0x1401fb4e1  jns     short loc_1401FB532
0x1401fb4e3  call    cs:__imp_GetCurrentThreadId
0x1401fb4ea  nop     dword ptr [rax+rax+00h]
0x1401fb4ef  mov     ecx, esi; Status
0x1401fb4f1  mov     ebx, eax
0x1401fb4f3  call    cs:__imp_RtlNtStatusToDosError
0x1401fb4fa  nop     dword ptr [rax+rax+00h]
0x1401fb4ff  mov     [rsp+80h+var_40], rdi
0x1401fb504  mov     r9d, 1
0x1401fb50a  mov     [rsp+80h+var_48], ebx
0x1401fb50e  xor     r8d, r8d
0x1401fb511  mov     [rsp+80h+var_50], 1553h
0x1401fb519  mov     edx, eax
0x1401fb51b  mov     [rsp+80h+var_58], r15
0x1401fb520  mov     [rsp+80h+var_60], r12
0x1401fb525  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401fb52a  mov     rbx, rax
0x1401fb52d  test    rax, rax
0x1401fb530  jnz     short loc_1401FB549
0x1401fb532  mov     rdx, [rbp+Buffer]
0x1401fb536  mov     rcx, r14
0x1401fb539  movzx   r8d, word ptr [rdx]
0x1401fb53d  mov     rdx, [rdx+8]
0x1401fb541  shr     r8, 1
0x1401fb544  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG_K@Z; FrsStringImpl<ushort,char>::Set(ushort const *,unsigned __int64)
0x1401fb549  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x1401fb54d  test    rcx, rcx
0x1401fb550  jz      short loc_1401FB562
0x1401fb552  call    cs:__imp_LsaClose
0x1401fb559  nop     dword ptr [rax+rax+00h]
0x1401fb55e  mov     [rbp+PolicyHandle], rdi
0x1401fb562  mov     rcx, [rbp+Buffer]; Buffer
0x1401fb566  test    rcx, rcx
0x1401fb569  jz      short loc_1401FB57B
0x1401fb56b  call    cs:__imp_LsaFreeMemory
0x1401fb572  nop     dword ptr [rax+rax+00h]
0x1401fb577  mov     [rbp+Buffer], rdi
0x1401fb57b  test    rbx, rbx
0x1401fb57e  jz      short loc_1401FB5B9
0x1401fb580  call    cs:__imp_GetCurrentThreadId
0x1401fb587  nop     dword ptr [rax+rax+00h]
0x1401fb58c  mov     r9d, [rbx]
0x1401fb58f  mov     r8d, [rbx+8]
0x1401fb593  mov     edx, [rbx+4]
0x1401fb596  mov     [rsp+80h+var_40], rbx
0x1401fb59b  mov     [rsp+80h+var_48], eax
0x1401fb59f  mov     [rsp+80h+var_50], 1565h
0x1401fb5a7  mov     [rsp+80h+var_58], r15
0x1401fb5ac  mov     [rsp+80h+var_60], r12
0x1401fb5b1  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401fb5b6  mov     rdi, rax
0x1401fb5b9  lea     r11, [rsp+80h+var_s0]
0x1401fb5c1  mov     rax, rdi
0x1401fb5c4  mov     rbx, [r11+30h]
0x1401fb5c8  mov     rsi, [r11+48h]
0x1401fb5cc  mov     rsp, r11
0x1401fb5cf  pop     r15
0x1401fb5d1  pop     r14
0x1401fb5d3  pop     r12
0x1401fb5d5  pop     rdi
0x1401fb5d6  pop     rbp
0x1401fb5d7  retn
```
