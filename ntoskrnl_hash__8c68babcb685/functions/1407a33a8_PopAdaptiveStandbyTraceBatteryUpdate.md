# PopAdaptiveStandbyTraceBatteryUpdate

- ea: `0x1407a33a8`
- end: `0x1407a36ce`
- name: `PopAdaptiveStandbyTraceBatteryUpdate`
- size: `806`
- prototype: `void __fastcall(__int64, unsigned int *, int, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x140b137d4`

## callees

- `0x1403729b0`
- `0x140423550`
- `0x140481fa0`
- `0x1404f07ac`
- `0x1406dc8c0`
- `0x1407a33a8`
- `0x1407a36d4`
- `0x140bb1410`
- `0x140bb19f0`

## string_xrefs

- `0x1407a3478`: `Settings.Hibernate.Battery Updates.Update %d.Timestamp`
- `0x1407a34ec`: `Settings.Hibernate.Battery Updates.Update %d.Battery Percent`
- `0x1407a3524`: `Settings.Hibernate.Battery Updates.Update %d.Full Charge Capacity`
- `0x1407a359a`: `Settings.Hibernate.Battery Updates.Update %d.RS Reject Reason`
- `0x1407a355c`: `Settings.Hibernate.Battery Updates.Update %d.Remaining Charge Capacity`
- `0x1407a3606`: `Settings.Hibernate.Battery Updates.Update %d.Battery Region`
- `0x1407a35f2`: `Settings.Hibernate.Battery Updates.Update %d.Hibernate Reject Reason`
- `0x1407a364b`: `Settings.Hibernate.Battery Updates.Update %d.Hibernate Reject Reason (Reserve)`
- `0x1407a3637`: `Settings.Hibernate.Battery Updates.Update %d.Hibernate Reject Reason (Budget)`

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
0x1407a33a8  mov     [rsp-8+arg_10], rbx
0x1407a33ad  push    rbp
0x1407a33ae  push    rsi
0x1407a33af  push    rdi
0x1407a33b0  push    r12
0x1407a33b2  push    r13
0x1407a33b4  push    r14
0x1407a33b6  push    r15
0x1407a33b8  lea     rbp, [rsp-1E0h]
0x1407a33c0  sub     rsp, 2E0h
0x1407a33c7  mov     rax, cs:__security_cookie
0x1407a33ce  xor     rax, rsp
0x1407a33d1  mov     [rbp+210h+var_40], rax
0x1407a33d8  movsxd  r12, r8d
0x1407a33db  mov     r15, rdx
0x1407a33de  mov     rdi, rcx
0x1407a33e1  movsxd  r14, r9d
0x1407a33e4  xorps   xmm0, xmm0
0x1407a33e7  mov     qword ptr [rsp+310h+LocalTime], 0
0x1407a33f0  mov     edx, 690h
0x1407a33f5  mov     ecx, 100h
0x1407a33fa  mov     r8d, 64416F50h
0x1407a3400  movups  xmmword ptr [rsp+310h+TimeFields.Year], xmm0
0x1407a3405  call    ExAllocatePool2
0x1407a340a  mov     rbx, rax
0x1407a340d  test    rax, rax
0x1407a3410  jz      loc_1407A36A3
0x1407a3416  mov     eax, [rdi+0F8h]
0x1407a341c  sub     eax, 1
0x1407a341f  jz      short loc_1407A3436
0x1407a3421  cmp     eax, 1
0x1407a3424  jnz     loc_1407A3696
0x1407a342a  mov     rsi, [rdi+0F0h]
0x1407a3431  dec     rsi
0x1407a3434  jmp     short loc_1407A343D
0x1407a3436  mov     rsi, [rdi+0F0h]
0x1407a343d  mov     rax, 0FFFFF78000000014h
0x1407a3447  lea     rdx, [rsp+310h+LocalTime]; LocalTime
0x1407a344c  lea     rcx, [rsp+310h+SystemTime]; SystemTime
0x1407a3451  mov     rax, [rax]
0x1407a3454  mov     qword ptr [rsp+310h+SystemTime], rax
0x1407a3459  call    ExSystemTimeToLocalTime
0x1407a345e  lea     rdx, [rsp+310h+TimeFields]; TimeFields
0x1407a3463  lea     rcx, [rsp+310h+LocalTime]; Time
0x1407a3468  call    RtlTimeToTimeFields
0x1407a346d  mov     r9d, [rdi+0ECh]
0x1407a3474  lea     rcx, [rbx+0Ch]; pszDest
0x1407a3478  lea     r8, aSettingsHibern_18; "Settings.Hibernate.Battery Updates.Upda"...
0x1407a347f  mov     edx, 48h ; 'H'; cchDest
0x1407a3484  call    RtlStringCchPrintfW
0x1407a3489  movsx   eax, [rsp+310h+TimeFields.Second]
0x1407a348e  lea     rcx, [rbx+0ACh]; pszDest
0x1407a3495  movsx   edx, [rsp+310h+TimeFields.Minute]
0x1407a349a  mov     r13d, 20h ; ' '
0x1407a34a0  movsx   r8d, [rsp+310h+TimeFields.Hour]
0x1407a34a6  movsx   r10d, [rsp+310h+TimeFields.Day]
0x1407a34ac  movsx   r11d, [rsp+310h+TimeFields.Month]
0x1407a34b2  movsx   r9d, [rsp+310h+TimeFields.Year]
0x1407a34b8  mov     [rsp+310h+var_2D0], eax
0x1407a34bc  mov     [rsp+310h+var_2D8], edx
0x1407a34c0  mov     edx, r13d; cchDest
0x1407a34c3  mov     [rsp+310h+var_2E0], r8d
0x1407a34c8  lea     r8, a04d02d02dt02d0; "%04d-%02d-%02dT%02d:%02d:%02d"
0x1407a34cf  mov     [rsp+310h+var_2E8], r10d
0x1407a34d4  mov     [rsp+310h+var_2F0], r11d
0x1407a34d9  call    RtlStringCchPrintfW
0x1407a34de  mov     r9d, [rdi+0ECh]
0x1407a34e5  lea     rcx, [rbx+0FCh]; pszDest
0x1407a34ec  lea     r8, aSettingsHibern_8; "Settings.Hibernate.Battery Updates.Upda"...
0x1407a34f3  lea     edx, [r13+28h]; cchDest
0x1407a34f7  call    RtlStringCchPrintfW
0x1407a34fc  mov     r9d, [r15+10h]
0x1407a3500  lea     rcx, [rbx+19Ch]; pszDest
0x1407a3507  lea     r8, aD_0; "%d%%"
0x1407a350e  mov     edx, r13d; cchDest
0x1407a3511  call    RtlStringCchPrintfW
0x1407a3516  mov     r9d, [rdi+0ECh]
0x1407a351d  lea     rcx, [rbx+1ECh]; pszDest
0x1407a3524  lea     r8, aSettingsHibern_13; "Settings.Hibernate.Battery Updates.Upda"...
0x1407a352b  lea     edx, [r13+28h]; cchDest
0x1407a352f  call    RtlStringCchPrintfW
0x1407a3534  mov     r9d, [r15+8]
0x1407a3538  lea     rcx, [rbx+28Ch]; pszDest
0x1407a353f  lea     r8, aD_5; "%d"
0x1407a3546  mov     edx, r13d; cchDest
0x1407a3549  call    RtlStringCchPrintfW
0x1407a354e  mov     r9d, [rdi+0ECh]
0x1407a3555  lea     rcx, [rbx+2DCh]; pszDest
0x1407a355c  lea     r8, aSettingsHibern_2; "Settings.Hibernate.Battery Updates.Upda"...
0x1407a3563  lea     edx, [r13+28h]; cchDest
0x1407a3567  call    RtlStringCchPrintfW
0x1407a356c  mov     r9d, [r15+0Ch]
0x1407a3570  lea     rcx, [rbx+37Ch]; pszDest
0x1407a3577  lea     r8, aD_5; "%d"
0x1407a357e  mov     edx, r13d; cchDest
0x1407a3581  call    RtlStringCchPrintfW
0x1407a3586  mov     r9d, [rdi+0ECh]
0x1407a358d  lea     rcx, [rbx+3CCh]; pszDest
0x1407a3594  mov     r13d, 48h ; 'H'
0x1407a359a  lea     r8, aSettingsHibern_9; "Settings.Hibernate.Battery Updates.Upda"...
0x1407a35a1  mov     edx, r13d; cchDest
0x1407a35a4  call    RtlStringCchPrintfW
0x1407a35a9  mov     rax, r12
0x1407a35ac  lea     r12, cs:140000000h
0x1407a35b3  mov     rax, ds:rva PopAdaptiveStandbyRejectReasonStrings[r12+rax*8]
0x1407a35bb  mov     [rbx+460h], rax
0x1407a35c2  mov     eax, cs:Feature_AdaptiveHibernateEnhancements__private_featureState
0x1407a35c8  test    al, 10h
0x1407a35ca  jz      short loc_1407A35D1
0x1407a35cc  and     eax, 1
0x1407a35cf  jmp     short loc_1407A35D6
0x1407a35d1  call    Feature_AdaptiveHibernateEnhancements__private_IsEnabledDeviceUsageNoInline
0x1407a35d6  mov     r9d, [rdi+0ECh]
0x1407a35dd  lea     rcx, [rbx+4BCh]; pszDest
0x1407a35e4  lea     r15, [rbx+5ACh]
0x1407a35eb  mov     rdx, r13; cchDest
0x1407a35ee  test    eax, eax
0x1407a35f0  jz      short loc_1407A3637
0x1407a35f2  lea     r8, aSettingsHibern_11; "Settings.Hibernate.Battery Updates.Upda"...
0x1407a35f9  call    RtlStringCchPrintfW
0x1407a35fe  mov     rax, ds:rva PopAdaptiveStandbyRejectReasonStrings[r12+r14*8]
0x1407a3606  lea     r8, aSettingsHibern_7; "Settings.Hibernate.Battery Updates.Upda"...
0x1407a360d  mov     [rbx+550h], rax
0x1407a3614  mov     rdx, r13; cchDest
0x1407a3617  mov     r9d, [rdi+0ECh]
0x1407a361e  mov     rcx, r15; pszDest
0x1407a3621  call    RtlStringCchPrintfW
0x1407a3626  movsxd  rax, dword ptr [rdi+0D8h]
0x1407a362d  mov     rcx, ds:rva PopAdaptiveStandbyRegionStrings[r12+rax*8]
0x1407a3635  jmp     short loc_1407A367A
0x1407a3637  lea     r8, aSettingsHibern; "Settings.Hibernate.Battery Updates.Upda"...
0x1407a363e  call    RtlStringCchPrintfW
0x1407a3643  mov     rax, ds:rva PopAdaptiveStandbyRejectReasonStrings[r12+r14*8]
0x1407a364b  lea     r8, aSettingsHibern_6; "Settings.Hibernate.Battery Updates.Upda"...
0x1407a3652  mov     [rbx+550h], rax
0x1407a3659  mov     rdx, r13; cchDest
0x1407a365c  mov     r9d, [rdi+0ECh]
0x1407a3663  mov     rcx, r15; pszDest
0x1407a3666  call    RtlStringCchPrintfW
0x1407a366b  movsxd  rax, [rbp+210h+arg_20]
0x1407a3672  mov     rcx, ds:rva PopAdaptiveStandbyRejectReasonStrings[r12+rax*8]
0x1407a367a  mov     [rbx+640h], rcx
0x1407a3681  lea     r9, [rsp+310h+var_2A0]
0x1407a3686  mov     rcx, rsi
0x1407a3689  mov     r8, rbx
0x1407a368c  mov     edx, 7
0x1407a3691  call    PopAdaptiveStandbyTraceSessionMetadata
0x1407a3696  mov     edx, 64416F50h; Tag
0x1407a369b  mov     rcx, rbx; P
0x1407a369e  call    ExFreePoolWithTag
0x1407a36a3  mov     rcx, [rbp+210h+var_40]
0x1407a36aa  xor     rcx, rsp; StackCookie
0x1407a36ad  call    __security_check_cookie
0x1407a36b2  mov     rbx, [rsp+310h+arg_10]
0x1407a36ba  add     rsp, 2E0h
0x1407a36c1  pop     r15
0x1407a36c3  pop     r14
0x1407a36c5  pop     r13
0x1407a36c7  pop     r12
0x1407a36c9  pop     rdi
0x1407a36ca  pop     rsi
0x1407a36cb  pop     rbp
0x1407a36cc  retn
```
