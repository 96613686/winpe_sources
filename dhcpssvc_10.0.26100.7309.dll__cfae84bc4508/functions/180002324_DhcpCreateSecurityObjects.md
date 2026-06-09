# DhcpCreateSecurityObjects

- ea: `0x180002324`
- end: `0x1800025c4`
- name: `DhcpCreateSecurityObjects`
- size: `672`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180025bf4`

## callees

- `0x1800021c0`
- `0x180002324`
- `0x180002854`
- `0x180025b98`
- `0x18008f124`
- `0x1800904f8`
- `0x1800cc9e0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000258e`
- `ntdll!RtlNtStatusToDosError` at `0x18000258e`
- `ADVAPI32!ConvertStringSidToSidW` at `0x1800024d1`
- `ADVAPI32!ConvertStringSidToSidW` at `0x1800024d1`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180002505`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180002549`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180002505`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180002549`
- `KERNEL32!GetLastError` at `0x1800024e1`
- `KERNEL32!GetLastError` at `0x1800024e1`

## pseudocode

```c
ULONG __fastcall DhcpCreateSecurityObjects(__int64 a1, __int64 a2)
{
  int v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r8
  unsigned int v10; // eax
  void *v11; // rcx
  unsigned int v12; // eax
  void *v13; // rcx
  __int64 v15; // rdx
  __int16 *v16; // rcx
  NTSTATUS SecurityObject; // eax
  __int16 v18; // [rsp+50h] [rbp-21h] BYREF
  char v19; // [rsp+52h] [rbp-1Fh]
  int v20; // [rsp+54h] [rbp-1Dh]
  void *v21; // [rsp+58h] [rbp-19h]
  _QWORD v22[2]; // [rsp+60h] [rbp-11h] BYREF
  _QWORD v23[2]; // [rsp+70h] [rbp-1h] BYREF
  __int16 v24; // [rsp+80h] [rbp+Fh] BYREF
  char v25; // [rsp+82h] [rbp+11h]
  int v26; // [rsp+84h] [rbp+13h]
  void *v27; // [rsp+88h] [rbp+17h]
  __int16 v28; // [rsp+90h] [rbp+1Fh]
  char v29; // [rsp+92h] [rbp+21h]
  int v30; // [rsp+94h] [rbp+23h]
  LPVOID *v31; // [rsp+98h] [rbp+27h]
  __int16 v32; // [rsp+A0h] [rbp+2Fh]
  char v33; // [rsp+A2h] [rbp+31h]
  unsigned int v34; // [rsp+A4h] [rbp+33h]
  LPVOID *v35; // [rsp+A8h] [rbp+37h]

  v30 = -1610612736;
  v24 = 0;
  v26 = 0x10000000;
  v20 = 0x10000000;
  v25 = 0;
  v27 = &AliasAdminsSid;
  v2 = 0;
  v28 = 0;
  v29 = 0;
  v31 = &DhcpAdminSid;
  v32 = 0;
  v33 = 0;
  v34 = 0x80000000;
  v35 = &DhcpSid;
  v18 = 0;
  v19 = 0;
  v21 = &AliasAdminsSid;
  v22[0] = GetString(1126, a2, &DhcpSid);
  v22[1] = GetString(1127, v3, v4);
  v23[0] = GetString(1128, v5, v6);
  v23[1] = GetString(1129, v7, v8);
  v10 = DhcpCreateAndLookupSid(v9, v22);
  if ( v10 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_96c1c8f0f5ee380f4a6130aeff8779e4_Traceguids, v10);
    DhcpReportEventW(v11, 1035, 1);
    v2 = 1;
  }
  v12 = DhcpCreateAndLookupSid(&DhcpAdminSid, v23);
  if ( v12 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_96c1c8f0f5ee380f4a6130aeff8779e4_Traceguids, v12);
    DhcpReportEventW(v13, 1036, 1);
    v2 = 1;
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
  qword_1801555E8 = (__int64)DhcpGlobalRegSecurityDescriptor;
  DhcpGlobalRegSecurityAttr = 24;
  dword_1801555F0 = 0;
  if ( v2 )
  {
    v15 = 1;
    v16 = &v18;
  }
  else
  {
    v15 = 3;
    v16 = &v24;
  }
  SecurityObject = NetpCreateSecurityObject(v16, v15);
  return RtlNtStatusToDosError(SecurityObject);
}

```

## disassembly

```asm
0x180002324  mov     rax, rsp
0x180002327  mov     [rax+8], rbx
0x18000232b  mov     [rax+10h], rsi
0x18000232f  mov     [rax+18h], rdi
0x180002333  push    rbp
0x180002334  push    r12
0x180002336  push    r14
0x180002338  lea     rbp, [rax-5Fh]
0x18000233c  sub     rsp, 0B0h
0x180002343  mov     rax, cs:__security_cookie
0x18000234a  xor     rax, rsp
0x18000234d  mov     [rbp+57h+var_18], rax
0x180002351  xor     edi, edi
0x180002353  mov     [rbp+57h+var_34], 0A0000000h
0x18000235a  mov     ecx, 10000000h
0x18000235f  mov     [rbp+57h+var_48], di
0x180002363  lea     rax, AliasAdminsSid
0x18000236a  mov     [rbp+57h+var_44], ecx
0x18000236d  mov     [rbp+57h+var_74], ecx
0x180002370  lea     r12, DhcpAdminSid
0x180002377  lea     r8, DhcpSid
0x18000237e  mov     [rbp+57h+var_46], dil
0x180002382  mov     ecx, 466h
0x180002387  mov     [rbp+57h+var_40], rax
0x18000238b  mov     ebx, edi
0x18000238d  mov     [rbp+57h+var_38], di
0x180002391  mov     [rbp+57h+var_36], dil
0x180002395  mov     [rbp+57h+var_30], r12
0x180002399  mov     [rbp+57h+var_28], di
0x18000239d  mov     [rbp+57h+var_26], dil
0x1800023a1  mov     [rbp+57h+var_24], 80000000h
0x1800023a8  mov     [rbp+57h+var_20], r8
0x1800023ac  mov     [rbp+57h+var_78], di
0x1800023b0  mov     [rbp+57h+var_76], dil
0x1800023b4  mov     [rbp+57h+var_70], rax
0x1800023b8  call    GetString
0x1800023bd  mov     ecx, 467h
0x1800023c2  mov     [rbp+57h+var_68], rax
0x1800023c6  call    GetString
0x1800023cb  mov     ecx, 468h
0x1800023d0  mov     [rbp+57h+var_60], rax
0x1800023d4  call    GetString
0x1800023d9  mov     ecx, 469h
0x1800023de  mov     [rbp+57h+var_58], rax
0x1800023e2  call    GetString
0x1800023e7  mov     rcx, r8
0x1800023ea  mov     [rbp+57h+var_50], rax
0x1800023ee  lea     rdx, [rbp+57h+var_68]
0x1800023f2  call    DhcpCreateAndLookupSid
0x1800023f7  mov     [rbp+57h+var_80], eax
0x1800023fa  lea     r14, WPP_GLOBAL_Control
0x180002401  lea     esi, [rdi+1]
0x180002404  test    eax, eax
0x180002406  jz      short loc_18000245B
0x180002408  mov     rcx, cs:WPP_GLOBAL_Control
0x18000240f  cmp     rcx, r14
0x180002412  jz      short loc_180002430
0x180002414  test    byte ptr [rcx+1Ch], 10h
0x180002418  jz      short loc_180002430
0x18000241a  mov     rcx, [rcx+10h]
0x18000241e  lea     edx, [rdi+0Ah]
0x180002421  mov     r9d, eax
0x180002424  lea     r8, WPP_96c1c8f0f5ee380f4a6130aeff8779e4_Traceguids
0x18000242b  call    WPP_SF_D
0x180002430  lea     rax, [rbp+57h+var_80]
0x180002434  xor     r9d, r9d
0x180002437  mov     [rsp+0C0h+var_90], rax
0x18000243c  mov     r8d, esi
0x18000243f  mov     [rsp+0C0h+var_98], rdi
0x180002444  mov     edx, 40Bh
0x180002449  mov     dword ptr [rsp+0C0h+var_A0], 4
0x180002451  call    DhcpReportEventW
0x180002456  mov     [rbp+57h+var_80], edi
0x180002459  mov     ebx, esi
0x18000245b  lea     rdx, [rbp+57h+var_58]
0x18000245f  mov     rcx, r12
0x180002462  call    DhcpCreateAndLookupSid
0x180002467  mov     [rbp+57h+var_80], eax
0x18000246a  test    eax, eax
0x18000246c  jz      short loc_1800024C3
0x18000246e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002475  cmp     rcx, r14
0x180002478  jz      short loc_180002498
0x18000247a  test    byte ptr [rcx+1Ch], 10h
0x18000247e  jz      short loc_180002498
0x180002480  mov     rcx, [rcx+10h]
0x180002484  lea     r8, WPP_96c1c8f0f5ee380f4a6130aeff8779e4_Traceguids
0x18000248b  mov     edx, 0Bh
0x180002490  mov     r9d, eax
0x180002493  call    WPP_SF_D
0x180002498  lea     rax, [rbp+57h+var_80]
0x18000249c  xor     r9d, r9d
0x18000249f  mov     [rsp+0C0h+var_90], rax
0x1800024a4  mov     r8d, esi
0x1800024a7  mov     [rsp+0C0h+var_98], rdi
0x1800024ac  mov     edx, 40Ch
0x1800024b1  mov     dword ptr [rsp+0C0h+var_A0], 4
0x1800024b9  call    DhcpReportEventW
0x1800024be  mov     [rbp+57h+var_80], edi
0x1800024c1  mov     ebx, esi
0x1800024c3  lea     rdx, DhcpServiceSid; Sid
0x1800024ca  lea     rcx, StringSid; "S-1-5-80-3273805168-4048181553-31721300"...
0x1800024d1  call    cs:__imp_ConvertStringSidToSidW
0x1800024d8  nop     dword ptr [rax+rax+00h]
0x1800024dd  test    eax, eax
0x1800024df  jnz     short loc_1800024F2
0x1800024e1  call    cs:__imp_GetLastError
0x1800024e8  nop     dword ptr [rax+rax+00h]
0x1800024ed  jmp     loc_18000259A
0x1800024f2  xor     r9d, r9d; SecurityDescriptorSize
0x1800024f5  lea     r8, DhcpGlobalDirSecurityDescriptor; SecurityDescriptor
0x1800024fc  mov     edx, esi; StringSDRevision
0x1800024fe  lea     rcx, StringSecurityDescriptor; "O:S-1-5-80-3273805168-4048181553-317213"...
0x180002505  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000250c  nop     dword ptr [rax+rax+00h]
0x180002511  test    eax, eax
0x180002513  jz      short loc_1800024E1
0x180002515  mov     rax, cs:DhcpGlobalDirSecurityDescriptor
0x18000251c  lea     r8, DhcpGlobalRegSecurityDescriptor; SecurityDescriptor
0x180002523  mov     r14d, 18h
0x180002529  mov     cs:DhcpGlobalDirSecurityAttr.lpSecurityDescriptor, rax
0x180002530  xor     r9d, r9d; SecurityDescriptorSize
0x180002533  mov     cs:DhcpGlobalDirSecurityAttr.nLength, r14d
0x18000253a  mov     edx, esi; StringSDRevision
0x18000253c  mov     cs:DhcpGlobalDirSecurityAttr.bInheritHandle, edi
0x180002542  lea     rcx, aDAKaS158032738; "D:(A;;KA;;;S-1-5-80-3273805168-40481815"...
0x180002549  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180002550  nop     dword ptr [rax+rax+00h]
0x180002555  test    eax, eax
0x180002557  jz      short loc_1800024E1
0x180002559  mov     rax, cs:DhcpGlobalRegSecurityDescriptor
0x180002560  mov     cs:qword_1801555E8, rax
0x180002567  mov     cs:DhcpGlobalRegSecurityAttr, r14d
0x18000256e  mov     cs:dword_1801555F0, edi
0x180002574  test    ebx, ebx
0x180002576  jnz     short loc_180002581
0x180002578  lea     edx, [rbx+3]
0x18000257b  lea     rcx, [rbp+57h+var_48]
0x18000257f  jmp     short loc_180002587
0x180002581  mov     edx, esi
0x180002583  lea     rcx, [rbp+57h+var_78]
0x180002587  call    NetpCreateSecurityObject
0x18000258c  mov     ecx, eax; Status
0x18000258e  call    cs:__imp_RtlNtStatusToDosError
0x180002595  nop     dword ptr [rax+rax+00h]
0x18000259a  mov     rcx, [rbp+57h+var_18]
0x18000259e  xor     rcx, rsp; StackCookie
0x1800025a1  call    __security_check_cookie
0x1800025a6  lea     r11, [rsp+0C0h+var_10]
0x1800025ae  mov     rbx, [r11+20h]
0x1800025b2  mov     rsi, [r11+28h]
0x1800025b6  mov     rdi, [r11+30h]
0x1800025ba  mov     rsp, r11
0x1800025bd  pop     r14
0x1800025bf  pop     r12
0x1800025c1  pop     rbp
0x1800025c2  retn
```
