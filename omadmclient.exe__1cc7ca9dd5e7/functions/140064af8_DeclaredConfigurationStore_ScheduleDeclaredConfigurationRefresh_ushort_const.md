# DeclaredConfigurationStore_ScheduleDeclaredConfigurationRefresh(ushort const *)

- ea: `0x140064af8`
- end: `0x140064c72`
- name: `?DeclaredConfigurationStore_ScheduleDeclaredConfigurationRefresh@@YAJPEBG@Z`
- size: `378`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14004b5a0`

## callees

- `0x140003450`
- `0x14000b0f4`
- `0x14000bf50`
- `0x14001173c`
- `0x1400146d8`
- `0x140029118`
- `0x140039c7c`
- `0x140064698`
- `0x140064af8`
- `0x140064c78`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x140064b67`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140064b67`

## string_xrefs

- `0x140064b4c`: `DeclaredConfigurationStore_ScheduleDeclaredConfigurationRefresh`
- `0x140064b7a`: `OSData\Software\Microsoft\DeclaredConfiguration\ManagementServiceConfiguration\%s`
- `0x140064b45`: `RefreshTask needs enrollmentId`
- `0x140064b73`: `Software\Microsoft\DeclaredConfiguration\ManagementServiceConfiguration\%s`
- `0x140064bfb`: `/c /DeclaredConfigurationRefresh /o `

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeclaredConfigurationStore_ScheduleDeclaredConfigurationRefresh(unsigned __int16 *a1)
{
  unsigned int v2; // ebx
  char IsStateSeparationEnabled; // al
  const unsigned __int16 *v5; // r8
  int v6; // eax
  HKEY v7; // rcx
  const unsigned __int16 *v8; // r8
  int RegistryDWORD; // eax
  unsigned int v10; // ebx
  __int64 v11; // rcx
  __int64 v12; // r8
  int v13; // [rsp+20h] [rbp-E0h]
  unsigned int v14; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v15; // [rsp+58h] [rbp-A8h]
  _OWORD Src[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v17[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v15 = 0;
  if ( !a1 )
  {
    v2 = -2147024809;
    if ( byte_140084F41 < 0 )
      McTemplateU0zzd_EventWriteTransfer(
        0,
        (unsigned int)OrchestratorGenericFailure,
        (unsigned int)L"DeclaredConfigurationStore_ScheduleDeclaredConfigurationRefresh",
        (unsigned int)L"RefreshTask needs enrollmentId",
        87);
    return v2;
  }
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1);
  v5 = L"OSData\\Software\\Microsoft\\DeclaredConfiguration\\ManagementServiceConfiguration\\%s";
  if ( !IsStateSeparationEnabled )
    v5 = L"Software\\Microsoft\\DeclaredConfiguration\\ManagementServiceConfiguration\\%s";
  v6 = StringCchPrintfW(v17, 0x104u, v5, a1);
  v2 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
      (const char *)(unsigned int)v6,
      v13);
    return v2;
  }
  v14 = 0;
  RegistryDWORD = DCCDNUtil_GetRegistryDWORD(v7, v17, v8, &v14);
  v10 = v14;
  if ( RegistryDWORD < 0 )
    v10 = 240;
  if ( v10 )
  {
    memset(Src, 0, sizeof(Src));
    std::wstring::_Construct<1,unsigned short const *>(Src, L"/c /DeclaredConfigurationRefresh /o ", 36);
    std::wstring::append(Src, a1);
    ScheduleDeclaredConfigurationMaintenanceCycle(v11, a1, v12, v10, v10);
    std::wstring::~wstring(Src);
  }
  return 0;
}

```

## disassembly

```asm
0x140064af8  mov     [rsp-8+arg_8], rbx
0x140064afd  mov     [rsp-8+arg_10], rdi
0x140064b02  push    rbp
0x140064b03  lea     rbp, [rsp-1A0h]
0x140064b0b  sub     rsp, 2A0h
0x140064b12  mov     rax, cs:__security_cookie
0x140064b19  xor     rax, rsp
0x140064b1c  mov     [rbp+1A0h+var_10], rax
0x140064b23  mov     rdi, rcx
0x140064b26  mov     [rsp+2A0h+var_248], 0
0x140064b2f  test    rcx, rcx
0x140064b32  jnz     short loc_140064B67
0x140064b34  mov     ebx, 80070057h
0x140064b39  cmp     cs:byte_140084F41, cl
0x140064b3f  jge     short loc_140064B60
0x140064b41  mov     [rsp+2A0h+var_280], ebx
0x140064b45  lea     r9, aRefreshtaskNee; "RefreshTask needs enrollmentId"
0x140064b4c  lea     r8, aDeclaredconfig; "DeclaredConfigurationStore_ScheduleDecl"...
0x140064b53  lea     rdx, OrchestratorGenericFailure
0x140064b5a  call    McTemplateU0zzd_EventWriteTransfer
0x140064b5f  nop
0x140064b60  mov     eax, ebx
0x140064b62  jmp     loc_140064C4D
0x140064b67  call    cs:__imp_RtlIsStateSeparationEnabled
0x140064b6e  nop     dword ptr [rax+rax+00h]
0x140064b73  lea     rcx, aSoftwareMicros_19; "Software\\Microsoft\\DeclaredConfigurat"...
0x140064b7a  lea     r8, aOsdataSoftware_13; "OSData\\Software\\Microsoft\\DeclaredCo"...
0x140064b81  test    al, al
0x140064b83  cmovz   r8, rcx; unsigned __int16 *
0x140064b87  mov     r9, rdi
0x140064b8a  mov     edx, 104h; unsigned __int64
0x140064b8f  lea     rcx, [rbp+1A0h+var_220]; unsigned __int16 *
0x140064b93  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140064b98  mov     ebx, eax
0x140064b9a  test    eax, eax
0x140064b9c  jns     short loc_140064BBC
0x140064b9e  mov     rcx, [rbp+1A8h]; this
0x140064ba5  mov     r9d, eax; char *
0x140064ba8  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x140064baf  mov     edx, 0C4Eh; void *
0x140064bb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140064bb9  nop
0x140064bba  jmp     short loc_140064B60
0x140064bbc  mov     [rsp+2A0h+var_250], 0
0x140064bc4  lea     r9, [rsp+2A0h+var_250]; unsigned int *
0x140064bc9  lea     rdx, [rbp+1A0h+var_220]; unsigned __int16 *
0x140064bcd  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140064bd2  mov     ebx, [rsp+2A0h+var_250]
0x140064bd6  mov     ecx, 0F0h
0x140064bdb  test    eax, eax
0x140064bdd  cmovs   ebx, ecx
0x140064be0  test    ebx, ebx
0x140064be2  jz      short loc_140064C4B
0x140064be4  xorps   xmm0, xmm0
0x140064be7  movups  [rsp+2A0h+Src], xmm0
0x140064bec  xorps   xmm1, xmm1
0x140064bef  movdqu  [rsp+2A0h+var_230], xmm1
0x140064bf5  mov     r8d, 24h ; '$'
0x140064bfb  lea     rdx, aCDeclaredconfi; "/c /DeclaredConfigurationRefresh /o "
0x140064c02  lea     rcx, [rsp+2A0h+Src]
0x140064c07  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140064c0c  nop
0x140064c0d  mov     rdx, rdi; void *
0x140064c10  lea     rcx, [rsp+2A0h+Src]; Src
0x140064c15  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x140064c1a  lea     rax, [rsp+2A0h+Src]
0x140064c1f  cmp     qword ptr [rsp+2A0h+var_230+8], 7
0x140064c25  cmova   rax, qword ptr [rsp+2A0h+Src]
0x140064c2b  mov     [rsp+2A0h+var_270], rax
0x140064c30  mov     [rsp+2A0h+var_280], ebx
0x140064c34  mov     r9d, ebx
0x140064c37  mov     rdx, rdi
0x140064c3a  call    ScheduleDeclaredConfigurationMaintenanceCycle
0x140064c3f  nop
0x140064c40  lea     rcx, [rsp+2A0h+Src]
0x140064c45  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140064c4a  nop
0x140064c4b  xor     eax, eax
0x140064c4d  mov     rcx, [rbp+1A0h+var_10]
0x140064c54  xor     rcx, rsp; StackCookie
0x140064c57  call    __security_check_cookie
0x140064c5c  lea     r11, [rsp+2A0h+var_s0]
0x140064c64  mov     rbx, [r11+18h]
0x140064c68  mov     rdi, [r11+20h]
0x140064c6c  mov     rsp, r11
0x140064c6f  pop     rbp
0x140064c70  retn
```
