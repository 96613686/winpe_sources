# PsmpUpdateApplicationCounters

- ea: `0x180003504`
- end: `0x180003657`
- name: `PsmpUpdateApplicationCounters`
- size: `339`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180002550`
- `0x1800114d0`

## callees

- `0x180003504`
- `0x18000bdc0`
- `0x180012cf0`
- `0x18001465c`
- `0x18001b7e0`
- `0x18001c10c`

## import_xrefs

- `ntdll!NtQueryInformationJobObject` at `0x180003554`
- `ntdll!NtQueryInformationJobObject` at `0x180003554`

## pseudocode

```c
__int64 __fastcall PsmpUpdateApplicationCounters(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // rcx
  bool v6; // zf
  unsigned int NetQuota; // eax
  _BYTE JobInformation[144]; // [rsp+30h] [rbp-1C8h] BYREF
  __int64 v10; // [rsp+C0h] [rbp-138h]

  memset_0(JobInformation, 0, 0x1B0u);
  NtQueryInformationJobObject(*(HANDLE *)(a1 + 184), JobObjectBasicProcessIdList|0x10, JobInformation, 0x1B0u, 0);
  v2 = MEMORY[0x7FFE03B0];
  v3 = MEMORY[0x7FFE0008];
  while ( v2 != MEMORY[0x7FFE03B0] )
  {
    _mm_pause();
    v2 = MEMORY[0x7FFE03B0];
    v3 = MEMORY[0x7FFE0008];
  }
  v4 = v3 - v2;
  *(_QWORD *)(352LL * *(int *)(a1 + 344) + a1 + 720) += v10 - *(_QWORD *)(a1 + 368);
  *(_QWORD *)(a1 + 368) = v10;
  v5 = 352 * (*(int *)(a1 + 344) + 2LL);
  *(_QWORD *)(v5 + a1) += v4 - *(_QWORD *)(a1 + 352);
  v6 = *(_QWORD *)(a1 + 232) == 0;
  *(_QWORD *)(a1 + 352) = v4;
  if ( !v6 )
  {
    NetQuota = PsmpQueryNetQuota(a1);
    *(_QWORD *)(352LL * *(int *)(a1 + 344) + a1 + 712) += NetQuota - *(_QWORD *)(a1 + 360);
    *(_QWORD *)(a1 + 360) = NetQuota;
  }
  PsmpUpdateApplicationCountersForJob(a1, 6);
  PsmpUpdateApplicationCountersForJob(a1, 8);
  return PsmpUpdateAppUsageInfo(a1);
}

```

## disassembly

```asm
0x180003504  push    rbx
0x180003506  sub     rsp, 1F0h
0x18000350d  mov     rax, cs:__security_cookie
0x180003514  xor     rax, rsp
0x180003517  mov     [rsp+1F8h+var_18], rax
0x18000351f  mov     rbx, rcx
0x180003522  xor     edx, edx; Val
0x180003524  lea     rcx, [rsp+1F8h+JobInformation]; void *
0x180003529  mov     r8d, 1B0h; Size
0x18000352f  call    memset_0
0x180003534  mov     rcx, [rbx+0B8h]; JobHandle
0x18000353b  lea     r8, [rsp+1F8h+JobInformation]; JobInformation
0x180003540  mov     r9d, 1B0h; JobInformationLength
0x180003546  mov     [rsp+1F8h+ReturnLength], 0; ReturnLength
0x18000354f  mov     edx, 13h; JobInformationClass
0x180003554  call    cs:__imp_NtQueryInformationJobObject
0x18000355a  mov     r8d, 7FFE03B0h
0x180003560  mov     rcx, [r8]
0x180003563  mov     rdx, ds:7FFE0008h
0x18000356b  jmp     short loc_18000357A
0x18000356d  pause
0x18000356f  mov     rcx, [r8]
0x180003572  mov     edx, 7FFE0008h
0x180003577  mov     rdx, [rdx]
0x18000357a  mov     rax, [r8]
0x18000357d  cmp     rcx, rax
0x180003580  jnz     short loc_18000356D
0x180003582  movsxd  rax, dword ptr [rbx+158h]
0x180003589  sub     rdx, rcx
0x18000358c  imul    rcx, rax, 160h
0x180003593  mov     rax, [rsp+1F8h+var_138]
0x18000359b  sub     rax, [rbx+170h]
0x1800035a2  add     [rcx+rbx+2D0h], rax
0x1800035aa  mov     rax, [rsp+1F8h+var_138]
0x1800035b2  mov     [rbx+170h], rax
0x1800035b9  movsxd  rax, dword ptr [rbx+158h]
0x1800035c0  add     rax, 2
0x1800035c4  imul    rcx, rax, 160h
0x1800035cb  mov     rax, rdx
0x1800035ce  sub     rax, [rbx+160h]
0x1800035d5  add     [rcx+rbx], rax
0x1800035d9  cmp     qword ptr [rbx+0E8h], 0
0x1800035e1  mov     [rbx+160h], rdx
0x1800035e8  jz      short loc_18000361C
0x1800035ea  mov     rcx, rbx
0x1800035ed  call    PsmpQueryNetQuota
0x1800035f2  mov     r8d, eax
0x1800035f5  movsxd  rax, dword ptr [rbx+158h]
0x1800035fc  imul    rdx, rax, 160h
0x180003603  mov     eax, r8d
0x180003606  sub     rax, [rbx+168h]
0x18000360d  add     [rdx+rbx+2C8h], rax
0x180003615  mov     [rbx+168h], r8
0x18000361c  mov     edx, 6
0x180003621  mov     rcx, rbx
0x180003624  call    PsmpUpdateApplicationCountersForJob
0x180003629  mov     edx, 8
0x18000362e  mov     rcx, rbx
0x180003631  call    PsmpUpdateApplicationCountersForJob
0x180003636  mov     rcx, rbx
0x180003639  call    PsmpUpdateAppUsageInfo
0x18000363e  mov     rcx, [rsp+1F8h+var_18]
0x180003646  xor     rcx, rsp; StackCookie
0x180003649  call    __security_check_cookie
0x18000364e  add     rsp, 1F0h
0x180003655  pop     rbx
0x180003656  retn
```
