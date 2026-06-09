# FveBackupMonitor::RegisterStartOfBackupMonitoring(_BACKUP_MONITOR_TYPE)

- ea: `0x18005da88`
- end: `0x18005dba1`
- name: `?RegisterStartOfBackupMonitoring@FveBackupMonitor@@SAJW4_BACKUP_MONITOR_TYPE@@@Z`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800c5324`

## callees

- `0x1800090c0`
- `0x18005da88`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x18005dac9`
- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x18005db4a`
- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x18005dac9`
- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x18005db4a`

## pseudocode

```c
__int64 FveBackupMonitor::RegisterStartOfBackupMonitoring()
{
  LSTATUS v0; // eax
  unsigned int v1; // ebx
  LSTATUS v2; // eax
  int Data; // [rsp+40h] [rbp+8h] BYREF

  Data = 1;
  v0 = RegSetKeyValueW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\BitLocker\\KeyBackupMonitor",
         L"IsKeyBackupMonitorStarted",
         4u,
         &Data,
         4u);
  v1 = v0;
  if ( v0 > 0 )
    v1 = (unsigned __int16)v0 | 0x80070000;
  if ( !v1 )
    goto LABEL_8;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_929186be452536e5252128d48ffaedab_Traceguids, v1);
  if ( (v1 & 0x80000000) == 0 )
  {
LABEL_8:
    v2 = RegSetKeyValueW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Control\\BitLocker\\KeyBackupMonitor",
           L"IsKeyBackupMonitorStartedLocal",
           4u,
           &Data,
           4u);
    v1 = v2;
    if ( v2 > 0 )
      v1 = (unsigned __int16)v2 | 0x80070000;
    if ( v1 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_929186be452536e5252128d48ffaedab_Traceguids, v1);
  }
  return v1;
}

```

## disassembly

```asm
0x18005da88  mov     rax, rsp
0x18005da8b  mov     [rax+10h], rbx
0x18005da8f  mov     [rax+8], ecx
0x18005da92  push    rdi
0x18005da93  sub     rsp, 30h
0x18005da97  mov     dword ptr [rax-10h], 4
0x18005da9e  mov     r9d, 4; dwType
0x18005daa4  mov     dword ptr [rax+8], 1
0x18005daab  lea     rax, [rax+8]
0x18005daaf  lea     r8, aIskeybackupmon; "IsKeyBackupMonitorStarted"
0x18005dab6  mov     [rsp+38h+lpData], rax; lpData
0x18005dabb  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Bit"...
0x18005dac2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005dac9  call    cs:__imp_RegSetKeyValueW
0x18005dad0  nop     dword ptr [rax+rax+00h]
0x18005dad5  mov     ebx, eax
0x18005dad7  test    eax, eax
0x18005dad9  jle     short loc_18005DAE4
0x18005dadb  movzx   ebx, ax
0x18005dade  or      ebx, 80070000h
0x18005dae4  lea     rdi, WPP_GLOBAL_Control
0x18005daeb  test    ebx, ebx
0x18005daed  jz      short loc_18005DB1D
0x18005daef  mov     rcx, cs:WPP_GLOBAL_Control
0x18005daf6  cmp     rcx, rdi
0x18005daf9  jz      short loc_18005DB19
0x18005dafb  test    byte ptr [rcx+1Ch], 40h
0x18005daff  jz      short loc_18005DB19
0x18005db01  mov     rcx, [rcx+10h]
0x18005db05  lea     r8, WPP_929186be452536e5252128d48ffaedab_Traceguids
0x18005db0c  mov     edx, 0Ah
0x18005db11  mov     r9d, ebx
0x18005db14  call    WPP_SF_d
0x18005db19  test    ebx, ebx
0x18005db1b  js      short loc_18005DB93
0x18005db1d  lea     rax, [rsp+38h+Data]
0x18005db22  mov     [rsp+38h+cbData], 4; cbData
0x18005db2a  mov     r9d, 4; dwType
0x18005db30  mov     [rsp+38h+lpData], rax; lpData
0x18005db35  lea     r8, aIskeybackupmon_0; "IsKeyBackupMonitorStartedLocal"
0x18005db3c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005db43  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Bit"...
0x18005db4a  call    cs:__imp_RegSetKeyValueW
0x18005db51  nop     dword ptr [rax+rax+00h]
0x18005db56  mov     ebx, eax
0x18005db58  test    eax, eax
0x18005db5a  jle     short loc_18005DB65
0x18005db5c  movzx   ebx, ax
0x18005db5f  or      ebx, 80070000h
0x18005db65  test    ebx, ebx
0x18005db67  jz      short loc_18005DB93
0x18005db69  mov     rcx, cs:WPP_GLOBAL_Control
0x18005db70  cmp     rcx, rdi
0x18005db73  jz      short loc_18005DB93
0x18005db75  test    byte ptr [rcx+1Ch], 40h
0x18005db79  jz      short loc_18005DB93
0x18005db7b  mov     rcx, [rcx+10h]
0x18005db7f  lea     r8, WPP_929186be452536e5252128d48ffaedab_Traceguids
0x18005db86  mov     edx, 0Bh
0x18005db8b  mov     r9d, ebx
0x18005db8e  call    WPP_SF_d
0x18005db93  mov     eax, ebx
0x18005db95  mov     rbx, [rsp+38h+arg_8]
0x18005db9a  add     rsp, 30h
0x18005db9e  pop     rdi
0x18005db9f  retn
```
