# DhcpCreateSecurityObjects

- ea: `0x180002318`
- end: `0x18000259e`
- name: `DhcpCreateSecurityObjects`
- size: `646`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180025144`

## callees

- `0x1800021b4`
- `0x180002318`
- `0x18000282c`
- `0x1800250e8`
- `0x18008f2a0`
- `0x18009069c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180002574`
- `ntdll!RtlNtStatusToDosError` at `0x180002574`
- `ADVAPI32!ConvertStringSidToSidW` at `0x1800024b7`
- `ADVAPI32!ConvertStringSidToSidW` at `0x1800024b7`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800024eb`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000252f`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800024eb`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000252f`
- `KERNEL32!GetLastError` at `0x1800024c7`
- `KERNEL32!GetLastError` at `0x1800024c7`

## pseudocode

```c
ULONG DhcpCreateSecurityObjects()
{
  int v0; // ebx
  __int64 v1; // r8
  unsigned int v2; // eax
  void *v3; // rcx
  unsigned int v4; // eax
  void *v5; // rcx
  __int64 v7; // rdx
  __int16 *v8; // rcx
  NTSTATUS SecurityObject; // eax
  __int16 v10; // [rsp+48h] [rbp-19h] BYREF
  char v11; // [rsp+4Ah] [rbp-17h]
  int v12; // [rsp+4Ch] [rbp-15h]
  void *v13; // [rsp+50h] [rbp-11h]
  _QWORD v14[2]; // [rsp+58h] [rbp-9h] BYREF
  _QWORD v15[2]; // [rsp+68h] [rbp+7h] BYREF
  __int16 v16; // [rsp+78h] [rbp+17h] BYREF
  char v17; // [rsp+7Ah] [rbp+19h]
  int v18; // [rsp+7Ch] [rbp+1Bh]
  void *v19; // [rsp+80h] [rbp+1Fh]
  __int16 v20; // [rsp+88h] [rbp+27h]
  char v21; // [rsp+8Ah] [rbp+29h]
  int v22; // [rsp+8Ch] [rbp+2Bh]
  LPVOID *v23; // [rsp+90h] [rbp+2Fh]
  __int16 v24; // [rsp+98h] [rbp+37h]
  char v25; // [rsp+9Ah] [rbp+39h]
  unsigned int v26; // [rsp+9Ch] [rbp+3Bh]
  LPVOID *v27; // [rsp+A0h] [rbp+3Fh]
  unsigned int v28; // [rsp+C8h] [rbp+67h] BYREF

  v22 = -1610612736;
  v16 = 0;
  v18 = 0x10000000;
  v12 = 0x10000000;
  v17 = 0;
  v19 = &AliasAdminsSid;
  v0 = 0;
  v20 = 0;
  v21 = 0;
  v23 = &DhcpAdminSid;
  v24 = 0;
  v25 = 0;
  v26 = 0x80000000;
  v27 = &DhcpSid;
  v10 = 0;
  v11 = 0;
  v13 = &AliasAdminsSid;
  v14[0] = GetString(1126);
  v14[1] = GetString(1127);
  v15[0] = GetString(1128);
  v15[1] = GetString(1129);
  v2 = DhcpCreateAndLookupSid(v1, v14);
  v28 = v2;
  if ( v2 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_96c1c8f0f5ee380f4a6130aeff8779e4_Traceguids, v2);
    DhcpReportEventW(v3, 1035, 1, 0, 4, 0, &v28);
    v28 = 0;
    v0 = 1;
  }
  v4 = DhcpCreateAndLookupSid(&DhcpAdminSid, v15);
  v28 = v4;
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_96c1c8f0f5ee380f4a6130aeff8779e4_Traceguids, v4);
    DhcpReportEventW(v5, 1036, 1, 0, 4, 0, &v28);
    v28 = 0;
    v0 = 1;
  }
  if ( !ConvertStringSidToSidW(L"S-1-5-80-3273805168-4048181553-3172130058-210131473-390205191", &DhcpServiceSid) )
    return GetLastError();
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:S-1-5-80-3273805168-4048181553-3172130058-210131473-390205191G:S-1-5-80-3273805168-4048181553-3172130058-210"
           "131473-390205191D:(A;OICI;FA;;;S-1-5-80-3273805168-4048181553-3172130058-210131473-390205191)(A;OICI;FA;;;BA)"
           "(A;OICI;FR;;;IU)(A;OICI;FR;;;SU)",
          1u,
          &DhcpGlobalDirSecurityDescriptor,
          0) )
    return GetLastError();
  DhcpGlobalDirSecurityAttr.lpSecurityDescriptor = DhcpGlobalDirSecurityDescriptor;
  DhcpGlobalDirSecurityAttr.nLength = 24;
  DhcpGlobalDirSecurityAttr.bInheritHandle = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;KA;;;S-1-5-80-3273805168-4048181553-3172130058-210131473-390205191)(A;CI;KA;;;BA)(A;CI;KA;;;SY)(A;CI;KR;;;BU)",
          1u,
          &DhcpGlobalRegSecurityDescriptor,
          0) )
    return GetLastError();
  qword_180157588 = (__int64)DhcpGlobalRegSecurityDescriptor;
  DhcpGlobalRegSecurityAttr = 24;
  dword_180157590 = 0;
  if ( v0 )
  {
    v7 = 1;
    v8 = &v10;
  }
  else
  {
    v7 = 3;
    v8 = &v16;
  }
  SecurityObject = NetpCreateSecurityObject(v8, v7);
  return RtlNtStatusToDosError(SecurityObject);
}

```

## disassembly

```asm
0x180002318  mov     rax, rsp
0x18000231b  mov     [rax+10h], rbx
0x18000231f  mov     [rax+18h], rsi
0x180002323  mov     [rax+20h], rdi
0x180002327  push    rbp
0x180002328  push    r12
0x18000232a  push    r14
0x18000232c  lea     rbp, [rax-5Fh]
0x180002330  sub     rsp, 0A0h
0x180002337  xor     edi, edi
0x180002339  mov     [rbp+57h+var_2C], 0A0000000h
0x180002340  mov     ecx, 10000000h
0x180002345  mov     [rbp+57h+var_40], di
0x180002349  lea     rax, AliasAdminsSid
0x180002350  mov     [rbp+57h+var_3C], ecx
0x180002353  mov     [rbp+57h+var_6C], ecx
0x180002356  lea     r12, DhcpAdminSid
0x18000235d  lea     r8, DhcpSid
0x180002364  mov     [rbp+57h+var_3E], dil
0x180002368  mov     ecx, 466h
0x18000236d  mov     [rbp+57h+var_38], rax
0x180002371  mov     ebx, edi
0x180002373  mov     [rbp+57h+var_30], di
0x180002377  mov     [rbp+57h+var_2E], dil
0x18000237b  mov     [rbp+57h+var_28], r12
0x18000237f  mov     [rbp+57h+var_20], di
0x180002383  mov     [rbp+57h+var_1E], dil
0x180002387  mov     [rbp+57h+var_1C], 80000000h
0x18000238e  mov     [rbp+57h+var_18], r8
0x180002392  mov     [rbp+57h+var_70], di
0x180002396  mov     [rbp+57h+var_6E], dil
0x18000239a  mov     [rbp+57h+var_68], rax
0x18000239e  call    GetString
0x1800023a3  mov     ecx, 467h
0x1800023a8  mov     [rbp+57h+var_60], rax
0x1800023ac  call    GetString
0x1800023b1  mov     ecx, 468h
0x1800023b6  mov     [rbp+57h+var_58], rax
0x1800023ba  call    GetString
0x1800023bf  mov     ecx, 469h
0x1800023c4  mov     [rbp+57h+var_50], rax
0x1800023c8  call    GetString
0x1800023cd  mov     rcx, r8
0x1800023d0  mov     [rbp+57h+var_48], rax
0x1800023d4  lea     rdx, [rbp+57h+var_60]
0x1800023d8  call    DhcpCreateAndLookupSid
0x1800023dd  mov     [rbp+57h+arg_0], eax
0x1800023e0  lea     r14, WPP_GLOBAL_Control
0x1800023e7  lea     esi, [rdi+1]
0x1800023ea  test    eax, eax
0x1800023ec  jz      short loc_180002441
0x1800023ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023f5  cmp     rcx, r14
0x1800023f8  jz      short loc_180002416
0x1800023fa  test    byte ptr [rcx+1Ch], 10h
0x1800023fe  jz      short loc_180002416
0x180002400  mov     rcx, [rcx+10h]
0x180002404  lea     edx, [rdi+0Ah]
0x180002407  mov     r9d, eax
0x18000240a  lea     r8, WPP_96c1c8f0f5ee380f4a6130aeff8779e4_Traceguids
0x180002411  call    WPP_SF_D
0x180002416  lea     rax, [rbp+57h+arg_0]
0x18000241a  xor     r9d, r9d
0x18000241d  mov     [rsp+0B0h+var_80], rax
0x180002422  mov     r8d, esi
0x180002425  mov     [rsp+0B0h+var_88], rdi
0x18000242a  mov     edx, 40Bh
0x18000242f  mov     dword ptr [rsp+0B0h+var_90], 4
0x180002437  call    DhcpReportEventW
0x18000243c  mov     [rbp+57h+arg_0], edi
0x18000243f  mov     ebx, esi
0x180002441  lea     rdx, [rbp+57h+var_50]
0x180002445  mov     rcx, r12
0x180002448  call    DhcpCreateAndLookupSid
0x18000244d  mov     [rbp+57h+arg_0], eax
0x180002450  test    eax, eax
0x180002452  jz      short loc_1800024A9
0x180002454  mov     rcx, cs:WPP_GLOBAL_Control
0x18000245b  cmp     rcx, r14
0x18000245e  jz      short loc_18000247E
0x180002460  test    byte ptr [rcx+1Ch], 10h
0x180002464  jz      short loc_18000247E
0x180002466  mov     rcx, [rcx+10h]
0x18000246a  lea     r8, WPP_96c1c8f0f5ee380f4a6130aeff8779e4_Traceguids
0x180002471  mov     edx, 0Bh
0x180002476  mov     r9d, eax
0x180002479  call    WPP_SF_D
0x18000247e  lea     rax, [rbp+57h+arg_0]
0x180002482  xor     r9d, r9d
0x180002485  mov     [rsp+0B0h+var_80], rax
0x18000248a  mov     r8d, esi
0x18000248d  mov     [rsp+0B0h+var_88], rdi
0x180002492  mov     edx, 40Ch
0x180002497  mov     dword ptr [rsp+0B0h+var_90], 4
0x18000249f  call    DhcpReportEventW
0x1800024a4  mov     [rbp+57h+arg_0], edi
0x1800024a7  mov     ebx, esi
0x1800024a9  lea     rdx, DhcpServiceSid; Sid
0x1800024b0  lea     rcx, StringSid; "S-1-5-80-3273805168-4048181553-31721300"...
0x1800024b7  call    cs:__imp_ConvertStringSidToSidW
0x1800024be  nop     dword ptr [rax+rax+00h]
0x1800024c3  test    eax, eax
0x1800024c5  jnz     short loc_1800024D8
0x1800024c7  call    cs:__imp_GetLastError
0x1800024ce  nop     dword ptr [rax+rax+00h]
0x1800024d3  jmp     loc_180002580
0x1800024d8  xor     r9d, r9d; SecurityDescriptorSize
0x1800024db  lea     r8, DhcpGlobalDirSecurityDescriptor; SecurityDescriptor
0x1800024e2  mov     edx, esi; StringSDRevision
0x1800024e4  lea     rcx, StringSecurityDescriptor; "O:S-1-5-80-3273805168-4048181553-317213"...
0x1800024eb  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800024f2  nop     dword ptr [rax+rax+00h]
0x1800024f7  test    eax, eax
0x1800024f9  jz      short loc_1800024C7
0x1800024fb  mov     rax, cs:DhcpGlobalDirSecurityDescriptor
0x180002502  lea     r8, DhcpGlobalRegSecurityDescriptor; SecurityDescriptor
0x180002509  mov     r14d, 18h
0x18000250f  mov     cs:DhcpGlobalDirSecurityAttr.lpSecurityDescriptor, rax
0x180002516  xor     r9d, r9d; SecurityDescriptorSize
0x180002519  mov     cs:DhcpGlobalDirSecurityAttr.nLength, r14d
0x180002520  mov     edx, esi; StringSDRevision
0x180002522  mov     cs:DhcpGlobalDirSecurityAttr.bInheritHandle, edi
0x180002528  lea     rcx, aDAKaS158032738; "D:(A;;KA;;;S-1-5-80-3273805168-40481815"...
0x18000252f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180002536  nop     dword ptr [rax+rax+00h]
0x18000253b  test    eax, eax
0x18000253d  jz      short loc_1800024C7
0x18000253f  mov     rax, cs:DhcpGlobalRegSecurityDescriptor
0x180002546  mov     cs:qword_180157588, rax
0x18000254d  mov     cs:DhcpGlobalRegSecurityAttr, r14d
0x180002554  mov     cs:dword_180157590, edi
0x18000255a  test    ebx, ebx
0x18000255c  jnz     short loc_180002567
0x18000255e  lea     edx, [rbx+3]
0x180002561  lea     rcx, [rbp+57h+var_40]
0x180002565  jmp     short loc_18000256D
0x180002567  mov     edx, esi
0x180002569  lea     rcx, [rbp+57h+var_70]
0x18000256d  call    NetpCreateSecurityObject
0x180002572  mov     ecx, eax; Status
0x180002574  call    cs:__imp_RtlNtStatusToDosError
0x18000257b  nop     dword ptr [rax+rax+00h]
0x180002580  lea     r11, [rsp+0B0h+var_10]
0x180002588  mov     rbx, [r11+28h]
0x18000258c  mov     rsi, [r11+30h]
0x180002590  mov     rdi, [r11+38h]
0x180002594  mov     rsp, r11
0x180002597  pop     r14
0x180002599  pop     r12
0x18000259b  pop     rbp
0x18000259c  retn
```
