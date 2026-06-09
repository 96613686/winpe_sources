# Migration::SysVolUtil::GetLsaDnsDomainName(FrsStringImpl<ushort,char> &)

- ea: `0x1401fb1dc`
- end: `0x1401fb3fe`
- name: `?GetLsaDnsDomainName@SysVolUtil@Migration@@SAPEAVFrsStatus@@AEAV?$FrsStringImpl@GD@@@Z`
- size: `546`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1401f7400`
- `0x1401fc134`

## callees

- `0x140028eec`
- `0x1401b9494`
- `0x1401be958`
- `0x1401fb1dc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401fb24b`
- `KERNEL32!GetCurrentThreadId` at `0x1401fb2bb`
- `KERNEL32!GetCurrentThreadId` at `0x1401fb314`
- `KERNEL32!GetCurrentThreadId` at `0x1401fb3a5`
- `KERNEL32!GetCurrentThreadId` at `0x1401fb24b`
- `KERNEL32!GetCurrentThreadId` at `0x1401fb2bb`
- `KERNEL32!GetCurrentThreadId` at `0x1401fb314`
- `KERNEL32!GetCurrentThreadId` at `0x1401fb3a5`
- `ntdll!RtlNtStatusToDosError` at `0x1401fb25b`
- `ntdll!RtlNtStatusToDosError` at `0x1401fb2cb`
- `ntdll!RtlNtStatusToDosError` at `0x1401fb25b`
- `ntdll!RtlNtStatusToDosError` at `0x1401fb2cb`
- `ADVAPI32!LsaClose` at `0x1401fb377`
- `ADVAPI32!LsaClose` at `0x1401fb377`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x1401fb2a9`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x1401fb2a9`
- `ADVAPI32!LsaOpenPolicy` at `0x1401fb22b`
- `ADVAPI32!LsaOpenPolicy` at `0x1401fb22b`
- `ADVAPI32!LsaFreeMemory` at `0x1401fb390`
- `ADVAPI32!LsaFreeMemory` at `0x1401fb390`

## pseudocode

```c
__int64 __fastcall Migration::SysVolUtil::GetLsaDnsDomainName(__int64 a1)
{
  __int64 v1; // rdi
  unsigned int *v2; // rbx
  int v4; // esi
  DWORD v5; // ebx
  ULONG v6; // eax
  __int64 v7; // rcx
  int v8; // esi
  DWORD v9; // ebx
  ULONG v10; // eax
  __int64 v11; // rcx
  _QWORD *v12; // rdx
  DWORD CurrentThreadId; // eax
  __int64 v14; // rcx
  DWORD v15; // eax
  __int64 v16; // rcx
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  PVOID Buffer; // [rsp+B8h] [rbp+38h] BYREF
  PVOID PolicyHandle; // [rsp+C0h] [rbp+40h] BYREF

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
                                "Migration::SysVolUtil::GetLsaDnsDomainName",
                                5379,
                                v5,
                                0)) == 0) )
  {
    v8 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer);
    if ( v8 >= 0
      || (v9 = GetCurrentThreadId(),
          v10 = RtlNtStatusToDosError(v8),
          (v2 = (unsigned int *)FrsStatusList::PushNewError(
                                  v11,
                                  v10,
                                  0,
                                  1,
                                  "base\\fs\\remotefs\\frs\\src\\ad\\migration.cpp",
                                  "Migration::SysVolUtil::GetLsaDnsDomainName",
                                  5390,
                                  v9,
                                  0)) == 0) )
    {
      v12 = Buffer;
      if ( !*((_QWORD *)Buffer + 8) )
      {
        CurrentThreadId = GetCurrentThreadId();
        v2 = (unsigned int *)FrsStatusList::PushNewError(
                               v14,
                               9551,
                               0,
                               3,
                               "base\\fs\\remotefs\\frs\\src\\ad\\migration.cpp",
                               "Migration::SysVolUtil::GetLsaDnsDomainName",
                               5398,
                               CurrentThreadId,
                               0);
        if ( v2 )
          goto LABEL_9;
        v12 = Buffer;
      }
      FrsStringImpl<unsigned short,char>::Set(a1, v12[3], (unsigned __int64)*((unsigned __int16 *)v12 + 8) >> 1);
    }
  }
LABEL_9:
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
    v15 = GetCurrentThreadId();
    return FrsStatusList::PushNewError(
             v16,
             v2[1],
             v2[2],
             *v2,
             "base\\fs\\remotefs\\frs\\src\\ad\\migration.cpp",
             "Migration::SysVolUtil::GetLsaDnsDomainName",
             5416,
             v15,
             v2);
  }
  return v1;
}

```

## disassembly

```asm
0x1401fb1dc  mov     [rsp-28h+arg_0], rbx
0x1401fb1e1  mov     [rsp-28h+arg_18], rsi
0x1401fb1e6  push    rbp
0x1401fb1e7  push    rdi
0x1401fb1e8  push    r12
0x1401fb1ea  push    r14
0x1401fb1ec  push    r15
0x1401fb1ee  mov     rbp, rsp
0x1401fb1f1  sub     rsp, 80h
0x1401fb1f8  xorps   xmm0, xmm0
0x1401fb1fb  xor     edi, edi
0x1401fb1fd  mov     ebx, edi
0x1401fb1ff  mov     [rbp+PolicyHandle], rdi
0x1401fb203  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1401fb207  mov     [rbp+Buffer], rdi
0x1401fb20b  mov     r14, rcx
0x1401fb20e  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1401fb212  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1401fb216  call    ?SetEmpty@?$FrsStringImpl@GD@@QEAAXXZ; FrsStringImpl<ushort,char>::SetEmpty(void)
0x1401fb21b  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x1401fb21f  mov     r8d, 801h; DesiredAccess
0x1401fb225  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x1401fb229  xor     ecx, ecx; SystemName
0x1401fb22b  call    cs:__imp_LsaOpenPolicy
0x1401fb232  nop     dword ptr [rax+rax+00h]
0x1401fb237  lea     r15, aMigrationSysvo_35; "Migration::SysVolUtil::GetLsaDnsDomainN"...
0x1401fb23e  mov     esi, eax
0x1401fb240  lea     r12, aBaseFsRemotefs_99; "base\\fs\\remotefs\\frs\\src\\ad\\migra"...
0x1401fb247  test    eax, eax
0x1401fb249  jns     short loc_1401FB29C
0x1401fb24b  call    cs:__imp_GetCurrentThreadId
0x1401fb252  nop     dword ptr [rax+rax+00h]
0x1401fb257  mov     ecx, esi; Status
0x1401fb259  mov     ebx, eax
0x1401fb25b  call    cs:__imp_RtlNtStatusToDosError
0x1401fb262  nop     dword ptr [rax+rax+00h]
0x1401fb267  mov     [rsp+80h+var_40], rdi
0x1401fb26c  lea     r9d, [rdi+1]
0x1401fb270  mov     [rsp+80h+var_48], ebx
0x1401fb274  xor     r8d, r8d
0x1401fb277  mov     [rsp+80h+var_50], 1503h
0x1401fb27f  mov     edx, eax
0x1401fb281  mov     [rsp+80h+var_58], r15
0x1401fb286  mov     [rsp+80h+var_60], r12
0x1401fb28b  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401fb290  mov     rbx, rax
0x1401fb293  test    rax, rax
0x1401fb296  jnz     loc_1401FB36E
0x1401fb29c  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1401fb2a0  lea     r8, [rbp+Buffer]; Buffer
0x1401fb2a4  mov     edx, 0Ch; InformationClass
0x1401fb2a9  call    cs:__imp_LsaQueryInformationPolicy
0x1401fb2b0  nop     dword ptr [rax+rax+00h]
0x1401fb2b5  mov     esi, eax
0x1401fb2b7  test    eax, eax
0x1401fb2b9  jns     short loc_1401FB30A
0x1401fb2bb  call    cs:__imp_GetCurrentThreadId
0x1401fb2c2  nop     dword ptr [rax+rax+00h]
0x1401fb2c7  mov     ecx, esi; Status
0x1401fb2c9  mov     ebx, eax
0x1401fb2cb  call    cs:__imp_RtlNtStatusToDosError
0x1401fb2d2  nop     dword ptr [rax+rax+00h]
0x1401fb2d7  mov     [rsp+80h+var_40], rdi
0x1401fb2dc  mov     r9d, 1
0x1401fb2e2  mov     [rsp+80h+var_48], ebx
0x1401fb2e6  xor     r8d, r8d
0x1401fb2e9  mov     [rsp+80h+var_50], 150Eh
0x1401fb2f1  mov     edx, eax
0x1401fb2f3  mov     [rsp+80h+var_58], r15
0x1401fb2f8  mov     [rsp+80h+var_60], r12
0x1401fb2fd  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401fb302  mov     rbx, rax
0x1401fb305  test    rax, rax
0x1401fb308  jnz     short loc_1401FB36E
0x1401fb30a  mov     rdx, [rbp+Buffer]
0x1401fb30e  cmp     [rdx+40h], rdi
0x1401fb312  jnz     short loc_1401FB35A
0x1401fb314  call    cs:__imp_GetCurrentThreadId
0x1401fb31b  nop     dword ptr [rax+rax+00h]
0x1401fb320  mov     [rsp+80h+var_40], rdi
0x1401fb325  mov     r9d, 3
0x1401fb32b  mov     [rsp+80h+var_48], eax
0x1401fb32f  xor     r8d, r8d
0x1401fb332  mov     [rsp+80h+var_50], 1516h
0x1401fb33a  mov     edx, 254Fh
0x1401fb33f  mov     [rsp+80h+var_58], r15
0x1401fb344  mov     [rsp+80h+var_60], r12
0x1401fb349  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401fb34e  mov     rbx, rax
0x1401fb351  test    rax, rax
0x1401fb354  jnz     short loc_1401FB36E
0x1401fb356  mov     rdx, [rbp+Buffer]
0x1401fb35a  movzx   r8d, word ptr [rdx+10h]
0x1401fb35f  mov     rcx, r14
0x1401fb362  mov     rdx, [rdx+18h]
0x1401fb366  shr     r8, 1
0x1401fb369  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG_K@Z; FrsStringImpl<ushort,char>::Set(ushort const *,unsigned __int64)
0x1401fb36e  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x1401fb372  test    rcx, rcx
0x1401fb375  jz      short loc_1401FB387
0x1401fb377  call    cs:__imp_LsaClose
0x1401fb37e  nop     dword ptr [rax+rax+00h]
0x1401fb383  mov     [rbp+PolicyHandle], rdi
0x1401fb387  mov     rcx, [rbp+Buffer]; Buffer
0x1401fb38b  test    rcx, rcx
0x1401fb38e  jz      short loc_1401FB3A0
0x1401fb390  call    cs:__imp_LsaFreeMemory
0x1401fb397  nop     dword ptr [rax+rax+00h]
0x1401fb39c  mov     [rbp+Buffer], rdi
0x1401fb3a0  test    rbx, rbx
0x1401fb3a3  jz      short loc_1401FB3DE
0x1401fb3a5  call    cs:__imp_GetCurrentThreadId
0x1401fb3ac  nop     dword ptr [rax+rax+00h]
0x1401fb3b1  mov     r9d, [rbx]
0x1401fb3b4  mov     r8d, [rbx+8]
0x1401fb3b8  mov     edx, [rbx+4]
0x1401fb3bb  mov     [rsp+80h+var_40], rbx
0x1401fb3c0  mov     [rsp+80h+var_48], eax
0x1401fb3c4  mov     [rsp+80h+var_50], 1528h
0x1401fb3cc  mov     [rsp+80h+var_58], r15
0x1401fb3d1  mov     [rsp+80h+var_60], r12
0x1401fb3d6  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401fb3db  mov     rdi, rax
0x1401fb3de  lea     r11, [rsp+80h+var_s0]
0x1401fb3e6  mov     rax, rdi
0x1401fb3e9  mov     rbx, [r11+30h]
0x1401fb3ed  mov     rsi, [r11+48h]
0x1401fb3f1  mov     rsp, r11
0x1401fb3f4  pop     r15
0x1401fb3f6  pop     r14
0x1401fb3f8  pop     r12
0x1401fb3fa  pop     rdi
0x1401fb3fb  pop     rbp
0x1401fb3fc  retn
```
