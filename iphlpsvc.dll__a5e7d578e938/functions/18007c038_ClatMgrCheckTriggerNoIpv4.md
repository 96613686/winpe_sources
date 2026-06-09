# ClatMgrCheckTriggerNoIpv4

- ea: `0x18007c038`
- end: `0x18007c2d1`
- name: `ClatMgrCheckTriggerNoIpv4`
- size: `665`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18007cc0c`

## callees

- `0x18000d7c0`
- `0x18002d2b0`
- `0x18007c038`
- `0x18007d398`
- `0x180081908`
- `0x180081a28`
- `0x180081b50`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007c136`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007c136`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18007c229`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18007c229`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007c281`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007c281`
- `WS2_32!__imp_ntohl` at `0x18007c103`
- `WS2_32!__imp_ntohl` at `0x18007c103`
- `NSI!NsiFreeTable` at `0x18007c2b0`
- `NSI!NsiFreeTable` at `0x18007c2b0`
- `NSI!NsiAllocateAndGetTable` at `0x18007c097`
- `NSI!NsiAllocateAndGetTable` at `0x18007c097`

## string_xrefs

- `0x18007c28f`: `No IPv4 delay timer is already set: Luid=%llu`

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
0x18007c038  mov     r11, rsp
0x18007c03b  mov     [r11+8], rbx
0x18007c03f  push    rbp
0x18007c040  push    rsi
0x18007c041  push    rdi
0x18007c042  push    r14
0x18007c044  push    r15
0x18007c046  sub     rsp, 70h
0x18007c04a  xor     r15d, r15d
0x18007c04d  lea     rax, [r11+10h]
0x18007c051  mov     [r11-38h], r15b
0x18007c055  lea     r9, [r11+18h]
0x18007c059  mov     [r11-40h], rax
0x18007c05d  lea     rdx, NPI_MS_IPV4_MODULEID
0x18007c064  mov     [r11-48h], r15d
0x18007c068  mov     rbx, rcx
0x18007c06b  mov     [r11-50h], r15
0x18007c06f  lea     r8d, [r15+0Ah]
0x18007c073  mov     [r11-58h], r15d
0x18007c077  lea     ecx, [r15+1]
0x18007c07b  mov     [r11-60h], r15
0x18007c07f  mov     [r11-68h], r15d
0x18007c083  mov     [r11-70h], r15
0x18007c087  mov     dword ptr [rsp+98h+var_78], 10h
0x18007c08f  mov     [r11+18h], r15
0x18007c093  mov     [r11+10h], r15d
0x18007c097  call    cs:__imp_NsiAllocateAndGetTable
0x18007c09e  nop     dword ptr [rax+rax+00h]
0x18007c0a3  lea     rdi, [rbx+10h]
0x18007c0a7  test    eax, eax
0x18007c0a9  jz      short loc_18007C0C7
0x18007c0ab  mov     r8, [rdi]
0x18007c0ae  lea     rdx, aNsiallocateand_0; "NsiAllocateAndGetTable failed: Luid=%ll"...
0x18007c0b5  mov     ecx, 4000000h
0x18007c0ba  mov     r9d, eax
0x18007c0bd  call    EventWrite0
0x18007c0c2  jmp     loc_18007C29B
0x18007c0c7  mov     r8d, [rsp+98h+arg_8]
0x18007c0cf  mov     esi, r15d
0x18007c0d2  test    r8d, r8d
0x18007c0d5  jz      short loc_18007C12C
0x18007c0d7  mov     rdx, [rsp+98h+arg_10]
0x18007c0df  mov     rax, [rdi]
0x18007c0e2  mov     ecx, esi
0x18007c0e4  add     rcx, rcx
0x18007c0e7  cmp     [rdx+rcx*8], rax
0x18007c0eb  jnz     short loc_18007C125
0x18007c0ed  lea     r9, [rdx+rcx*8]
0x18007c0f1  lea     rcx, [r9+8]; Address
0x18007c0f5  call    Ipv4UnicastAddressScope
0x18007c0fa  cmp     eax, 2
0x18007c0fd  jz      short loc_18007C125
0x18007c0ff  mov     ecx, [r9+8]; netlong
0x18007c103  call    cs:__imp_ntohl
0x18007c10a  nop     dword ptr [rax+rax+00h]
0x18007c10f  and     eax, 0FFFFFFF8h
0x18007c112  cmp     eax, 0C0000000h
0x18007c117  jnz     loc_18007C1BD
0x18007c11d  mov     r8d, [rsp+98h+arg_8]
0x18007c125  inc     esi
0x18007c127  cmp     esi, r8d
0x18007c12a  jb      short loc_18007C0D7
0x18007c12c  cmp     [rbx+1Bh], r15b
0x18007c130  jnz     loc_18007C29B
0x18007c136  call    cs:__imp_GetTickCount64
0x18007c13d  nop     dword ptr [rax+rax+00h]
0x18007c142  mov     rcx, [rbx+20h]
0x18007c146  mov     esi, 4000000h
0x18007c14b  mov     r8, [rdi]
0x18007c14e  mov     rdx, rax
0x18007c151  sub     rdx, rcx
0x18007c154  mov     r9, rax
0x18007c157  neg     rcx
0x18007c15a  mov     r14, rax
0x18007c15d  mov     ecx, esi
0x18007c15f  sbb     rbp, rbp
0x18007c162  and     rbp, rdx
0x18007c165  lea     rdx, aNoIpv4Detected; "No IPv4 detected: Luid=%llu, CurrentTic"...
0x18007c16c  mov     [rsp+98h+var_78], rbp
0x18007c171  call    EventWrite0
0x18007c176  cmp     rbp, 2710h
0x18007c17d  jb      loc_18007C225
0x18007c183  mov     r8, [rdi]
0x18007c186  lea     rdx, aEnablingClatLu; "Enabling CLAT: Luid=%llu, Trigger=NoIpv"...
0x18007c18d  mov     ecx, esi
0x18007c18f  call    EventWrite0
0x18007c194  call    Feature_CLAT_Preview2_Telemetry__private_IsEnabledDeviceUsageNoInline
0x18007c199  mov     rcx, [rdi]
0x18007c19c  test    eax, eax
0x18007c19e  jz      short loc_18007C20A
0x18007c1a0  mov     dword ptr [rsp+98h+var_78], 3
0x18007c1a8  call    Enable464xlatRpcClientWithTriggerSource
0x18007c1ad  test    eax, eax
0x18007c1af  jz      short loc_18007C21F
0x18007c1b1  mov     r8, [rdi]
0x18007c1b4  lea     rdx, aEnable464xlatr_0; "Enable464xlatRpcClientWithTriggerSource"...
0x18007c1bb  jmp     short loc_18007C1FA
0x18007c1bd  mov     [rbx+20h], r15
0x18007c1c1  cmp     [rbx+1Bh], r15b
0x18007c1c5  jz      loc_18007C29B
0x18007c1cb  mov     r8, [rbx+10h]
0x18007c1cf  lea     rdx, aDisablingClatL_1; "Disabling CLAT: Luid=%llu, Trigger=NoIp"...
0x18007c1d6  mov     esi, 4000000h
0x18007c1db  mov     ecx, esi
0x18007c1dd  call    EventWrite0
0x18007c1e2  mov     rcx, [rbx+10h]
0x18007c1e6  call    Disable464xlatRpcClient
0x18007c1eb  test    eax, eax
0x18007c1ed  jz      short loc_18007C201
0x18007c1ef  mov     r8, [rbx+10h]
0x18007c1f3  lea     rdx, aDisable464xlat; "Disable464xlatRpcClient failed: Luid=%l"...
0x18007c1fa  mov     ecx, esi
0x18007c1fc  jmp     loc_18007C0BA
0x18007c201  mov     [rbx+1Bh], r15b
0x18007c205  jmp     loc_18007C29B
0x18007c20a  call    Enable464xlatRpcClient
0x18007c20f  test    eax, eax
0x18007c211  jz      short loc_18007C21F
0x18007c213  mov     r8, [rdi]
0x18007c216  lea     rdx, aEnable464xlatr; "Enable464xlatRpcClient failed: Luid=%ll"...
0x18007c21d  jmp     short loc_18007C1FA
0x18007c21f  mov     byte ptr [rbx+1Bh], 1
0x18007c223  jmp     short loc_18007C29B
0x18007c225  mov     rcx, [rbx+28h]; pti
0x18007c229  call    cs:__imp_IsThreadpoolTimerSet
0x18007c230  nop     dword ptr [rax+rax+00h]
0x18007c235  mov     r8, [rdi]
0x18007c238  mov     ecx, esi
0x18007c23a  test    eax, eax
0x18007c23c  jnz     short loc_18007C28F
0x18007c23e  lea     rdx, aSettingNoIpv4D; "Setting No IPv4 delay timer: Luid=%llu"
0x18007c245  mov     qword ptr [rsp+98h+pftDueTime.dwLowDateTime], r15
0x18007c24d  call    EventWrite0
0x18007c252  lea     rax, [rbp-2774h]
0x18007c259  mov     [rbx+20h], r14
0x18007c25d  imul    rcx, rax, 2710h
0x18007c264  mov     r9d, 7D0h; msWindowLength
0x18007c26a  lea     rdx, [rsp+98h+pftDueTime]; pftDueTime
0x18007c272  mov     qword ptr [rsp+98h+pftDueTime.dwLowDateTime], rcx
0x18007c27a  xor     r8d, r8d; msPeriod
0x18007c27d  mov     rcx, [rbx+28h]; pti
0x18007c281  call    cs:__imp_SetThreadpoolTimer
0x18007c288  nop     dword ptr [rax+rax+00h]
0x18007c28d  jmp     short loc_18007C29B
0x18007c28f  lea     rdx, aNoIpv4DelayTim; "No IPv4 delay timer is already set: Lui"...
0x18007c296  call    EventWrite0
0x18007c29b  mov     rcx, [rsp+98h+arg_10]
0x18007c2a3  test    rcx, rcx
0x18007c2a6  jz      short loc_18007C2BC
0x18007c2a8  xor     r9d, r9d
0x18007c2ab  xor     r8d, r8d
0x18007c2ae  xor     edx, edx
0x18007c2b0  call    cs:__imp_NsiFreeTable
0x18007c2b7  nop     dword ptr [rax+rax+00h]
0x18007c2bc  mov     rbx, [rsp+98h+arg_0]
0x18007c2c4  add     rsp, 70h
0x18007c2c8  pop     r15
0x18007c2ca  pop     r14
0x18007c2cc  pop     rdi
0x18007c2cd  pop     rsi
0x18007c2ce  pop     rbp
0x18007c2cf  retn
```
