# PopAdaptiveStandbyTraceBatteryUpdate

- ea: `0x14079f358`
- end: `0x14079f67e`
- name: `PopAdaptiveStandbyTraceBatteryUpdate`
- size: `806`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x140b0cd74`

## callees

- `0x140309b10`
- `0x14040bd00`
- `0x1404729c0`
- `0x1404e0f5c`
- `0x1406d9d70`
- `0x14079f358`
- `0x14079f684`
- `0x140bae410`
- `0x140bae8e0`

## string_xrefs

- `0x14079f5e7`: `Settings.Hibernate.Battery Updates.Update %d.Hibernate Reject Reason (Budget)`
- `0x14079f5fb`: `Settings.Hibernate.Battery Updates.Update %d.Hibernate Reject Reason (Reserve)`
- `0x14079f5a2`: `Settings.Hibernate.Battery Updates.Update %d.Hibernate Reject Reason`
- `0x14079f5b6`: `Settings.Hibernate.Battery Updates.Update %d.Battery Region`
- `0x14079f49c`: `Settings.Hibernate.Battery Updates.Update %d.Battery Percent`
- `0x14079f428`: `Settings.Hibernate.Battery Updates.Update %d.Timestamp`
- `0x14079f50c`: `Settings.Hibernate.Battery Updates.Update %d.Remaining Charge Capacity`
- `0x14079f54a`: `Settings.Hibernate.Battery Updates.Update %d.RS Reject Reason`
- `0x14079f4d4`: `Settings.Hibernate.Battery Updates.Update %d.Full Charge Capacity`

## pseudocode

```c
void __fastcall PopAdaptiveStandbyTraceBatteryUpdate(__int64 a1, unsigned int *a2, int a3, int a4, int a5)
{
  __int64 v5; // r12
  __int64 v8; // r14
  __int64 Pool2; // rbx
  __int64 v10; // rsi
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v12; // r9
  wchar_t *v13; // rcx
  wchar_t *v14; // rcx
  TIME_FIELDS TimeFields; // [rsp+50h] [rbp-B0h] BYREF
  LARGE_INTEGER LocalTime; // [rsp+60h] [rbp-A0h] BYREF
  LARGE_INTEGER SystemTime; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v18[608]; // [rsp+70h] [rbp-90h] BYREF

  v5 = a3;
  v8 = a4;
  LocalTime.QuadPart = 0;
  TimeFields = 0;
  Pool2 = ExAllocatePool2(256, 1680, 1682009936);
  if ( Pool2 )
  {
    if ( *(_DWORD *)(a1 + 248) == 1 )
    {
      v10 = *(_QWORD *)(a1 + 240);
    }
    else
    {
      if ( *(_DWORD *)(a1 + 248) != 2 )
      {
LABEL_13:
        ExFreePoolWithTag((PVOID)Pool2, 0x64416F50u);
        return;
      }
      v10 = *(_QWORD *)(a1 + 240) - 1LL;
    }
    SystemTime.QuadPart = MEMORY[0xFFFFF78000000014];
    ExSystemTimeToLocalTime(&SystemTime, &LocalTime);
    RtlTimeToTimeFields(&LocalTime, &TimeFields);
    RtlStringCchPrintfW(
      (NTSTRSAFE_PWSTR)(Pool2 + 12),
      0x48u,
      L"Settings.Hibernate.Battery Updates.Update %d.Timestamp",
      *(unsigned int *)(a1 + 236));
    RtlStringCchPrintfW(
      (NTSTRSAFE_PWSTR)(Pool2 + 172),
      0x20u,
      L"%04d-%02d-%02dT%02d:%02d:%02d",
      (unsigned int)TimeFields.Year,
      TimeFields.Month,
      TimeFields.Day,
      TimeFields.Hour,
      TimeFields.Minute,
      TimeFields.Second);
    RtlStringCchPrintfW(
      (NTSTRSAFE_PWSTR)(Pool2 + 252),
      0x48u,
      L"Settings.Hibernate.Battery Updates.Update %d.Battery Percent",
      *(unsigned int *)(a1 + 236));
    RtlStringCchPrintfW((NTSTRSAFE_PWSTR)(Pool2 + 412), 0x20u, L"%d%%", a2[4]);
    RtlStringCchPrintfW(
      (NTSTRSAFE_PWSTR)(Pool2 + 492),
      0x48u,
      L"Settings.Hibernate.Battery Updates.Update %d.Full Charge Capacity",
      *(unsigned int *)(a1 + 236));
    RtlStringCchPrintfW((NTSTRSAFE_PWSTR)(Pool2 + 652), 0x20u, L"%d", a2[2]);
    RtlStringCchPrintfW(
      (NTSTRSAFE_PWSTR)(Pool2 + 732),
      0x48u,
      L"Settings.Hibernate.Battery Updates.Update %d.Remaining Charge Capacity",
      *(unsigned int *)(a1 + 236));
    RtlStringCchPrintfW((NTSTRSAFE_PWSTR)(Pool2 + 892), 0x20u, L"%d", a2[3]);
    RtlStringCchPrintfW(
      (NTSTRSAFE_PWSTR)(Pool2 + 972),
      0x48u,
      L"Settings.Hibernate.Battery Updates.Update %d.RS Reject Reason",
      *(unsigned int *)(a1 + 236));
    *(_QWORD *)(Pool2 + 1120) = PopAdaptiveStandbyRejectReasonStrings[v5];
    if ( (Feature_AdaptiveHibernateEnhancements__private_featureState & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = Feature_AdaptiveHibernateEnhancements__private_featureState & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_AdaptiveHibernateEnhancements__private_IsEnabledDeviceUsageNoInline();
    v12 = *(unsigned int *)(a1 + 236);
    v13 = (wchar_t *)(Pool2 + 1212);
    if ( IsEnabledDeviceUsageNoInline )
    {
      RtlStringCchPrintfW(v13, 0x48u, L"Settings.Hibernate.Battery Updates.Update %d.Hibernate Reject Reason", v12);
      *(_QWORD *)(Pool2 + 1360) = PopAdaptiveStandbyRejectReasonStrings[v8];
      RtlStringCchPrintfW(
        (NTSTRSAFE_PWSTR)(Pool2 + 1452),
        0x48u,
        L"Settings.Hibernate.Battery Updates.Update %d.Battery Region",
        *(unsigned int *)(a1 + 236));
      v14 = PopAdaptiveStandbyRegionStrings[*(int *)(a1 + 216)];
    }
    else
    {
      RtlStringCchPrintfW(
        v13,
        0x48u,
        L"Settings.Hibernate.Battery Updates.Update %d.Hibernate Reject Reason (Budget)",
        v12);
      *(_QWORD *)(Pool2 + 1360) = PopAdaptiveStandbyRejectReasonStrings[v8];
      RtlStringCchPrintfW(
        (NTSTRSAFE_PWSTR)(Pool2 + 1452),
        0x48u,
        L"Settings.Hibernate.Battery Updates.Update %d.Hibernate Reject Reason (Reserve)",
        *(unsigned int *)(a1 + 236));
      v14 = PopAdaptiveStandbyRejectReasonStrings[a5];
    }
    *(_QWORD *)(Pool2 + 1600) = v14;
    PopAdaptiveStandbyTraceSessionMetadata(v10, 7, Pool2, v18);
    goto LABEL_13;
  }
}

```

## disassembly

```asm
0x14079f358  mov     [rsp-8+arg_10], rbx
0x14079f35d  push    rbp
0x14079f35e  push    rsi
0x14079f35f  push    rdi
0x14079f360  push    r12
0x14079f362  push    r13
0x14079f364  push    r14
0x14079f366  push    r15
0x14079f368  lea     rbp, [rsp-1E0h]
0x14079f370  sub     rsp, 2E0h
0x14079f377  mov     rax, cs:__security_cookie
0x14079f37e  xor     rax, rsp
0x14079f381  mov     [rbp+210h+var_40], rax
0x14079f388  movsxd  r12, r8d
0x14079f38b  mov     r15, rdx
0x14079f38e  mov     rdi, rcx
0x14079f391  movsxd  r14, r9d
0x14079f394  xorps   xmm0, xmm0
0x14079f397  mov     qword ptr [rsp+310h+LocalTime], 0
0x14079f3a0  mov     edx, 690h
0x14079f3a5  mov     ecx, 100h
0x14079f3aa  mov     r8d, 64416F50h
0x14079f3b0  movups  xmmword ptr [rsp+310h+TimeFields.Year], xmm0
0x14079f3b5  call    ExAllocatePool2
0x14079f3ba  mov     rbx, rax
0x14079f3bd  test    rax, rax
0x14079f3c0  jz      loc_14079F653
0x14079f3c6  mov     eax, [rdi+0F8h]
0x14079f3cc  sub     eax, 1
0x14079f3cf  jz      short loc_14079F3E6
0x14079f3d1  cmp     eax, 1
0x14079f3d4  jnz     loc_14079F646
0x14079f3da  mov     rsi, [rdi+0F0h]
0x14079f3e1  dec     rsi
0x14079f3e4  jmp     short loc_14079F3ED
0x14079f3e6  mov     rsi, [rdi+0F0h]
0x14079f3ed  mov     rax, 0FFFFF78000000014h
0x14079f3f7  lea     rdx, [rsp+310h+LocalTime]; LocalTime
0x14079f3fc  lea     rcx, [rsp+310h+SystemTime]; SystemTime
0x14079f401  mov     rax, [rax]
0x14079f404  mov     qword ptr [rsp+310h+SystemTime], rax
0x14079f409  call    ExSystemTimeToLocalTime
0x14079f40e  lea     rdx, [rsp+310h+TimeFields]; TimeFields
0x14079f413  lea     rcx, [rsp+310h+LocalTime]; Time
0x14079f418  call    RtlTimeToTimeFields
0x14079f41d  mov     r9d, [rdi+0ECh]
0x14079f424  lea     rcx, [rbx+0Ch]; pszDest
0x14079f428  lea     r8, aSettingsHibern_18; "Settings.Hibernate.Battery Updates.Upda"...
0x14079f42f  mov     edx, 48h ; 'H'; cchDest
0x14079f434  call    RtlStringCchPrintfW
0x14079f439  movsx   eax, [rsp+310h+TimeFields.Second]
0x14079f43e  lea     rcx, [rbx+0ACh]; pszDest
0x14079f445  movsx   edx, [rsp+310h+TimeFields.Minute]
0x14079f44a  mov     r13d, 20h ; ' '
0x14079f450  movsx   r8d, [rsp+310h+TimeFields.Hour]
0x14079f456  movsx   r10d, [rsp+310h+TimeFields.Day]
0x14079f45c  movsx   r11d, [rsp+310h+TimeFields.Month]
0x14079f462  movsx   r9d, [rsp+310h+TimeFields.Year]
0x14079f468  mov     [rsp+310h+var_2D0], eax
0x14079f46c  mov     [rsp+310h+var_2D8], edx
0x14079f470  mov     edx, r13d; cchDest
0x14079f473  mov     [rsp+310h+var_2E0], r8d
0x14079f478  lea     r8, a04d02d02dt02d0; "%04d-%02d-%02dT%02d:%02d:%02d"
0x14079f47f  mov     [rsp+310h+var_2E8], r10d
0x14079f484  mov     [rsp+310h+var_2F0], r11d
0x14079f489  call    RtlStringCchPrintfW
0x14079f48e  mov     r9d, [rdi+0ECh]
0x14079f495  lea     rcx, [rbx+0FCh]; pszDest
0x14079f49c  lea     r8, aSettingsHibern_8; "Settings.Hibernate.Battery Updates.Upda"...
0x14079f4a3  lea     edx, [r13+28h]; cchDest
0x14079f4a7  call    RtlStringCchPrintfW
0x14079f4ac  mov     r9d, [r15+10h]
0x14079f4b0  lea     rcx, [rbx+19Ch]; pszDest
0x14079f4b7  lea     r8, aD_0; "%d%%"
0x14079f4be  mov     edx, r13d; cchDest
0x14079f4c1  call    RtlStringCchPrintfW
0x14079f4c6  mov     r9d, [rdi+0ECh]
0x14079f4cd  lea     rcx, [rbx+1ECh]; pszDest
0x14079f4d4  lea     r8, aSettingsHibern_13; "Settings.Hibernate.Battery Updates.Upda"...
0x14079f4db  lea     edx, [r13+28h]; cchDest
0x14079f4df  call    RtlStringCchPrintfW
0x14079f4e4  mov     r9d, [r15+8]
0x14079f4e8  lea     rcx, [rbx+28Ch]; pszDest
0x14079f4ef  lea     r8, aD_5; "%d"
0x14079f4f6  mov     edx, r13d; cchDest
0x14079f4f9  call    RtlStringCchPrintfW
0x14079f4fe  mov     r9d, [rdi+0ECh]
0x14079f505  lea     rcx, [rbx+2DCh]; pszDest
0x14079f50c  lea     r8, aSettingsHibern_2; "Settings.Hibernate.Battery Updates.Upda"...
0x14079f513  lea     edx, [r13+28h]; cchDest
0x14079f517  call    RtlStringCchPrintfW
0x14079f51c  mov     r9d, [r15+0Ch]
0x14079f520  lea     rcx, [rbx+37Ch]; pszDest
0x14079f527  lea     r8, aD_5; "%d"
0x14079f52e  mov     edx, r13d; cchDest
0x14079f531  call    RtlStringCchPrintfW
0x14079f536  mov     r9d, [rdi+0ECh]
0x14079f53d  lea     rcx, [rbx+3CCh]; pszDest
0x14079f544  mov     r13d, 48h ; 'H'
0x14079f54a  lea     r8, aSettingsHibern_9; "Settings.Hibernate.Battery Updates.Upda"...
0x14079f551  mov     edx, r13d; cchDest
0x14079f554  call    RtlStringCchPrintfW
0x14079f559  mov     rax, r12
0x14079f55c  lea     r12, cs:140000000h
0x14079f563  mov     rax, ds:rva PopAdaptiveStandbyRejectReasonStrings[r12+rax*8]
0x14079f56b  mov     [rbx+460h], rax
0x14079f572  mov     eax, cs:Feature_AdaptiveHibernateEnhancements__private_featureState
0x14079f578  test    al, 10h
0x14079f57a  jz      short loc_14079F581
0x14079f57c  and     eax, 1
0x14079f57f  jmp     short loc_14079F586
0x14079f581  call    Feature_AdaptiveHibernateEnhancements__private_IsEnabledDeviceUsageNoInline
0x14079f586  mov     r9d, [rdi+0ECh]
0x14079f58d  lea     rcx, [rbx+4BCh]; pszDest
0x14079f594  lea     r15, [rbx+5ACh]
0x14079f59b  mov     rdx, r13; cchDest
0x14079f59e  test    eax, eax
0x14079f5a0  jz      short loc_14079F5E7
0x14079f5a2  lea     r8, aSettingsHibern_11; "Settings.Hibernate.Battery Updates.Upda"...
0x14079f5a9  call    RtlStringCchPrintfW
0x14079f5ae  mov     rax, ds:rva PopAdaptiveStandbyRejectReasonStrings[r12+r14*8]
0x14079f5b6  lea     r8, aSettingsHibern_7; "Settings.Hibernate.Battery Updates.Upda"...
0x14079f5bd  mov     [rbx+550h], rax
0x14079f5c4  mov     rdx, r13; cchDest
0x14079f5c7  mov     r9d, [rdi+0ECh]
0x14079f5ce  mov     rcx, r15; pszDest
0x14079f5d1  call    RtlStringCchPrintfW
0x14079f5d6  movsxd  rax, dword ptr [rdi+0D8h]
0x14079f5dd  mov     rcx, ds:rva PopAdaptiveStandbyRegionStrings[r12+rax*8]
0x14079f5e5  jmp     short loc_14079F62A
0x14079f5e7  lea     r8, aSettingsHibern; "Settings.Hibernate.Battery Updates.Upda"...
0x14079f5ee  call    RtlStringCchPrintfW
0x14079f5f3  mov     rax, ds:rva PopAdaptiveStandbyRejectReasonStrings[r12+r14*8]
0x14079f5fb  lea     r8, aSettingsHibern_6; "Settings.Hibernate.Battery Updates.Upda"...
0x14079f602  mov     [rbx+550h], rax
0x14079f609  mov     rdx, r13; cchDest
0x14079f60c  mov     r9d, [rdi+0ECh]
0x14079f613  mov     rcx, r15; pszDest
0x14079f616  call    RtlStringCchPrintfW
0x14079f61b  movsxd  rax, [rbp+210h+arg_20]
0x14079f622  mov     rcx, ds:rva PopAdaptiveStandbyRejectReasonStrings[r12+rax*8]
0x14079f62a  mov     [rbx+640h], rcx
0x14079f631  lea     r9, [rsp+310h+var_2A0]
0x14079f636  mov     rcx, rsi
0x14079f639  mov     r8, rbx
0x14079f63c  mov     edx, 7
0x14079f641  call    PopAdaptiveStandbyTraceSessionMetadata
0x14079f646  mov     edx, 64416F50h; Tag
0x14079f64b  mov     rcx, rbx; P
0x14079f64e  call    ExFreePoolWithTag
0x14079f653  mov     rcx, [rbp+210h+var_40]
0x14079f65a  xor     rcx, rsp; StackCookie
0x14079f65d  call    __security_check_cookie
0x14079f662  mov     rbx, [rsp+310h+arg_10]
0x14079f66a  add     rsp, 2E0h
0x14079f671  pop     r15
0x14079f673  pop     r14
0x14079f675  pop     r13
0x14079f677  pop     r12
0x14079f679  pop     rdi
0x14079f67a  pop     rsi
0x14079f67b  pop     rbp
0x14079f67c  retn
```
