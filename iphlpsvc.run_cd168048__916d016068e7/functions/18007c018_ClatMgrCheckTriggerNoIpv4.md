# ClatMgrCheckTriggerNoIpv4

- ea: `0x18007c018`
- end: `0x18007c2b1`
- name: `ClatMgrCheckTriggerNoIpv4`
- size: `665`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18007cafc`

## callees

- `0x18000d7b0`
- `0x18002d2a0`
- `0x18007c018`
- `0x18007d1b8`
- `0x180081718`
- `0x180081838`
- `0x180081960`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007c116`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007c116`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18007c209`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18007c209`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007c261`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007c261`
- `WS2_32!__imp_ntohl` at `0x18007c0e3`
- `WS2_32!__imp_ntohl` at `0x18007c0e3`
- `NSI!NsiFreeTable` at `0x18007c290`
- `NSI!NsiFreeTable` at `0x18007c290`
- `NSI!NsiAllocateAndGetTable` at `0x18007c077`
- `NSI!NsiAllocateAndGetTable` at `0x18007c077`

## string_xrefs

- `0x18007c26f`: `No IPv4 delay timer is already set: Luid=%llu`

## pseudocode

```c
void __fastcall ClatMgrCheckTriggerNoIpv4(__int64 a1)
{
  unsigned int Table; // eax
  __int64 *v3; // rdi
  __int64 v4; // r8
  const wchar_t *v5; // rdx
  unsigned int v6; // r8d
  unsigned int v7; // esi
  __int64 v8; // r9
  ULONGLONG TickCount64; // r14
  unsigned __int64 v10; // rbp
  int IsEnabledDeviceUsageNoInline; // eax
  int v12; // edx
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // rcx
  BOOL v16; // eax
  __int64 v17; // r8
  unsigned int v18; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v19; // [rsp+B0h] [rbp+18h] BYREF
  struct _FILETIME pftDueTime; // [rsp+B8h] [rbp+20h] BYREF

  v19 = 0;
  v18 = 0;
  Table = NsiAllocateAndGetTable(1, &NPI_MS_IPV4_MODULEID, 10, &v19, 16, 0, 0, 0, 0, 0, 0, &v18, 0);
  v3 = (__int64 *)(a1 + 16);
  if ( Table )
  {
    v4 = *v3;
    v5 = L"NsiAllocateAndGetTable failed: Luid=%llu, Status=%d";
    goto LABEL_3;
  }
  v6 = v18;
  v7 = 0;
  if ( !v18 )
  {
LABEL_10:
    if ( *(_BYTE *)(a1 + 27) )
      goto LABEL_25;
    TickCount64 = GetTickCount64();
    v10 = (TickCount64 - *(_QWORD *)(a1 + 32)) & -(__int64)(*(_QWORD *)(a1 + 32) != 0);
    EventWrite0(
      0x4000000,
      L"No IPv4 detected: Luid=%llu, CurrentTick=%llu, TicksElapsedWhileNoIpv4=%llu",
      *v3,
      TickCount64,
      v10);
    if ( v10 < 0x2710 )
    {
      v16 = IsThreadpoolTimerSet(*(PTP_TIMER *)(a1 + 40));
      v17 = *v3;
      if ( v16 )
      {
        EventWrite0(0x4000000, L"No IPv4 delay timer is already set: Luid=%llu", v17);
      }
      else
      {
        pftDueTime = 0;
        EventWrite0(0x4000000, L"Setting No IPv4 delay timer: Luid=%llu", v17);
        *(_QWORD *)(a1 + 32) = TickCount64;
        pftDueTime = (struct _FILETIME)(10000 * (v10 - 10100));
        SetThreadpoolTimer(*(PTP_TIMER *)(a1 + 40), &pftDueTime, 0, 0x7D0u);
      }
      goto LABEL_25;
    }
    EventWrite0(0x4000000, L"Enabling CLAT: Luid=%llu, Trigger=NoIpv4", *v3);
    IsEnabledDeviceUsageNoInline = Feature_CLAT_Preview2_Telemetry__private_IsEnabledDeviceUsageNoInline();
    v15 = *v3;
    if ( IsEnabledDeviceUsageNoInline )
    {
      Table = Enable464xlatRpcClientWithTriggerSource(v15, v12, v13, v14, 3);
      if ( Table )
      {
        v4 = *v3;
        v5 = L"Enable464xlatRpcClientWithTriggerSource failed: Luid=%llu, Status=%d";
        goto LABEL_3;
      }
    }
    else
    {
      Table = Enable464xlatRpcClient(v15);
      if ( Table )
      {
        v4 = *v3;
        v5 = L"Enable464xlatRpcClient failed: Luid=%llu, Status=%d";
LABEL_3:
        EventWrite0(0x4000000, v5, v4, Table);
        goto LABEL_25;
      }
    }
    *(_BYTE *)(a1 + 27) = 1;
    goto LABEL_25;
  }
  while ( 1 )
  {
    if ( *(_QWORD *)(v19 + 16LL * v7) != *v3
      || Ipv4UnicastAddressScope((const UCHAR *)(v19 + 16LL * v7 + 8)) == ScopeLevelLink )
    {
      goto LABEL_9;
    }
    if ( (ntohl(*(_DWORD *)(v8 + 8)) & 0xFFFFFFF8) != 0xC0000000 )
      break;
    v6 = v18;
LABEL_9:
    if ( ++v7 >= v6 )
      goto LABEL_10;
  }
  *(_QWORD *)(a1 + 32) = 0;
  if ( *(_BYTE *)(a1 + 27) )
  {
    EventWrite0(0x4000000, L"Disabling CLAT: Luid=%llu, Trigger=NoIpv4", *(_QWORD *)(a1 + 16));
    Table = Disable464xlatRpcClient(*(_QWORD *)(a1 + 16));
    if ( Table )
    {
      v4 = *(_QWORD *)(a1 + 16);
      v5 = L"Disable464xlatRpcClient failed: Luid=%llu, Status=%d";
      goto LABEL_3;
    }
    *(_BYTE *)(a1 + 27) = 0;
  }
LABEL_25:
  if ( v19 )
    NsiFreeTable(v19, 0, 0, 0);
}

```

## disassembly

```asm
0x18007c018  mov     r11, rsp
0x18007c01b  mov     [r11+8], rbx
0x18007c01f  push    rbp
0x18007c020  push    rsi
0x18007c021  push    rdi
0x18007c022  push    r14
0x18007c024  push    r15
0x18007c026  sub     rsp, 70h
0x18007c02a  xor     r15d, r15d
0x18007c02d  lea     rax, [r11+10h]
0x18007c031  mov     [r11-38h], r15b
0x18007c035  lea     r9, [r11+18h]
0x18007c039  mov     [r11-40h], rax
0x18007c03d  lea     rdx, NPI_MS_IPV4_MODULEID
0x18007c044  mov     [r11-48h], r15d
0x18007c048  mov     rbx, rcx
0x18007c04b  mov     [r11-50h], r15
0x18007c04f  lea     r8d, [r15+0Ah]
0x18007c053  mov     [r11-58h], r15d
0x18007c057  lea     ecx, [r15+1]
0x18007c05b  mov     [r11-60h], r15
0x18007c05f  mov     [r11-68h], r15d
0x18007c063  mov     [r11-70h], r15
0x18007c067  mov     dword ptr [rsp+98h+var_78], 10h
0x18007c06f  mov     [r11+18h], r15
0x18007c073  mov     [r11+10h], r15d
0x18007c077  call    cs:__imp_NsiAllocateAndGetTable
0x18007c07e  nop     dword ptr [rax+rax+00h]
0x18007c083  lea     rdi, [rbx+10h]
0x18007c087  test    eax, eax
0x18007c089  jz      short loc_18007C0A7
0x18007c08b  mov     r8, [rdi]
0x18007c08e  lea     rdx, aNsiallocateand_0; "NsiAllocateAndGetTable failed: Luid=%ll"...
0x18007c095  mov     ecx, 4000000h
0x18007c09a  mov     r9d, eax
0x18007c09d  call    EventWrite0
0x18007c0a2  jmp     loc_18007C27B
0x18007c0a7  mov     r8d, [rsp+98h+arg_8]
0x18007c0af  mov     esi, r15d
0x18007c0b2  test    r8d, r8d
0x18007c0b5  jz      short loc_18007C10C
0x18007c0b7  mov     rdx, [rsp+98h+arg_10]
0x18007c0bf  mov     rax, [rdi]
0x18007c0c2  mov     ecx, esi
0x18007c0c4  add     rcx, rcx
0x18007c0c7  cmp     [rdx+rcx*8], rax
0x18007c0cb  jnz     short loc_18007C105
0x18007c0cd  lea     r9, [rdx+rcx*8]
0x18007c0d1  lea     rcx, [r9+8]; Address
0x18007c0d5  call    Ipv4UnicastAddressScope
0x18007c0da  cmp     eax, 2
0x18007c0dd  jz      short loc_18007C105
0x18007c0df  mov     ecx, [r9+8]; netlong
0x18007c0e3  call    cs:__imp_ntohl
0x18007c0ea  nop     dword ptr [rax+rax+00h]
0x18007c0ef  and     eax, 0FFFFFFF8h
0x18007c0f2  cmp     eax, 0C0000000h
0x18007c0f7  jnz     loc_18007C19D
0x18007c0fd  mov     r8d, [rsp+98h+arg_8]
0x18007c105  inc     esi
0x18007c107  cmp     esi, r8d
0x18007c10a  jb      short loc_18007C0B7
0x18007c10c  cmp     [rbx+1Bh], r15b
0x18007c110  jnz     loc_18007C27B
0x18007c116  call    cs:__imp_GetTickCount64
0x18007c11d  nop     dword ptr [rax+rax+00h]
0x18007c122  mov     rcx, [rbx+20h]
0x18007c126  mov     esi, 4000000h
0x18007c12b  mov     r8, [rdi]
0x18007c12e  mov     rdx, rax
0x18007c131  sub     rdx, rcx
0x18007c134  mov     r9, rax
0x18007c137  neg     rcx
0x18007c13a  mov     r14, rax
0x18007c13d  mov     ecx, esi
0x18007c13f  sbb     rbp, rbp
0x18007c142  and     rbp, rdx
0x18007c145  lea     rdx, aNoIpv4Detected; "No IPv4 detected: Luid=%llu, CurrentTic"...
0x18007c14c  mov     [rsp+98h+var_78], rbp
0x18007c151  call    EventWrite0
0x18007c156  cmp     rbp, 2710h
0x18007c15d  jb      loc_18007C205
0x18007c163  mov     r8, [rdi]
0x18007c166  lea     rdx, aEnablingClatLu; "Enabling CLAT: Luid=%llu, Trigger=NoIpv"...
0x18007c16d  mov     ecx, esi
0x18007c16f  call    EventWrite0
0x18007c174  call    Feature_CLAT_Preview2_Telemetry__private_IsEnabledDeviceUsageNoInline
0x18007c179  mov     rcx, [rdi]
0x18007c17c  test    eax, eax
0x18007c17e  jz      short loc_18007C1EA
0x18007c180  mov     dword ptr [rsp+98h+var_78], 3
0x18007c188  call    Enable464xlatRpcClientWithTriggerSource
0x18007c18d  test    eax, eax
0x18007c18f  jz      short loc_18007C1FF
0x18007c191  mov     r8, [rdi]
0x18007c194  lea     rdx, aEnable464xlatr_0; "Enable464xlatRpcClientWithTriggerSource"...
0x18007c19b  jmp     short loc_18007C1DA
0x18007c19d  mov     [rbx+20h], r15
0x18007c1a1  cmp     [rbx+1Bh], r15b
0x18007c1a5  jz      loc_18007C27B
0x18007c1ab  mov     r8, [rbx+10h]
0x18007c1af  lea     rdx, aDisablingClatL_1; "Disabling CLAT: Luid=%llu, Trigger=NoIp"...
0x18007c1b6  mov     esi, 4000000h
0x18007c1bb  mov     ecx, esi
0x18007c1bd  call    EventWrite0
0x18007c1c2  mov     rcx, [rbx+10h]
0x18007c1c6  call    Disable464xlatRpcClient
0x18007c1cb  test    eax, eax
0x18007c1cd  jz      short loc_18007C1E1
0x18007c1cf  mov     r8, [rbx+10h]
0x18007c1d3  lea     rdx, aDisable464xlat; "Disable464xlatRpcClient failed: Luid=%l"...
0x18007c1da  mov     ecx, esi
0x18007c1dc  jmp     loc_18007C09A
0x18007c1e1  mov     [rbx+1Bh], r15b
0x18007c1e5  jmp     loc_18007C27B
0x18007c1ea  call    Enable464xlatRpcClient
0x18007c1ef  test    eax, eax
0x18007c1f1  jz      short loc_18007C1FF
0x18007c1f3  mov     r8, [rdi]
0x18007c1f6  lea     rdx, aEnable464xlatr; "Enable464xlatRpcClient failed: Luid=%ll"...
0x18007c1fd  jmp     short loc_18007C1DA
0x18007c1ff  mov     byte ptr [rbx+1Bh], 1
0x18007c203  jmp     short loc_18007C27B
0x18007c205  mov     rcx, [rbx+28h]; pti
0x18007c209  call    cs:__imp_IsThreadpoolTimerSet
0x18007c210  nop     dword ptr [rax+rax+00h]
0x18007c215  mov     r8, [rdi]
0x18007c218  mov     ecx, esi
0x18007c21a  test    eax, eax
0x18007c21c  jnz     short loc_18007C26F
0x18007c21e  lea     rdx, aSettingNoIpv4D; "Setting No IPv4 delay timer: Luid=%llu"
0x18007c225  mov     qword ptr [rsp+98h+pftDueTime.dwLowDateTime], r15
0x18007c22d  call    EventWrite0
0x18007c232  lea     rax, [rbp-2774h]
0x18007c239  mov     [rbx+20h], r14
0x18007c23d  imul    rcx, rax, 2710h
0x18007c244  mov     r9d, 7D0h; msWindowLength
0x18007c24a  lea     rdx, [rsp+98h+pftDueTime]; pftDueTime
0x18007c252  mov     qword ptr [rsp+98h+pftDueTime.dwLowDateTime], rcx
0x18007c25a  xor     r8d, r8d; msPeriod
0x18007c25d  mov     rcx, [rbx+28h]; pti
0x18007c261  call    cs:__imp_SetThreadpoolTimer
0x18007c268  nop     dword ptr [rax+rax+00h]
0x18007c26d  jmp     short loc_18007C27B
0x18007c26f  lea     rdx, aNoIpv4DelayTim; "No IPv4 delay timer is already set: Lui"...
0x18007c276  call    EventWrite0
0x18007c27b  mov     rcx, [rsp+98h+arg_10]
0x18007c283  test    rcx, rcx
0x18007c286  jz      short loc_18007C29C
0x18007c288  xor     r9d, r9d
0x18007c28b  xor     r8d, r8d
0x18007c28e  xor     edx, edx
0x18007c290  call    cs:__imp_NsiFreeTable
0x18007c297  nop     dword ptr [rax+rax+00h]
0x18007c29c  mov     rbx, [rsp+98h+arg_0]
0x18007c2a4  add     rsp, 70h
0x18007c2a8  pop     r15
0x18007c2aa  pop     r14
0x18007c2ac  pop     rdi
0x18007c2ad  pop     rsi
0x18007c2ae  pop     rbp
0x18007c2af  retn
```
