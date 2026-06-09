# UpdateStatus

- ea: `0x18000eafc`
- end: `0x18000eb74`
- name: `UpdateStatus`
- size: `120`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x18000e930`
- `0x18001c660`
- `0x180021420`
- `0x180023928`
- `0x180025350`

## callees

- `0x18000eafc`
- `0x18004d1a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb48`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000eb29`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000eb29`

## pseudocode

```c
__int64 UpdateStatus()
{
  DWORD v0; // ebx
  DWORD LastError; // eax

  v0 = 0;
  if ( DhcpGlobalServiceStatusHandle )
  {
    if ( DhcpGlobalServiceStatus.dwCurrentState == 4 || DhcpGlobalServiceStatus.dwCurrentState == 1 )
      *(_QWORD *)&DhcpGlobalServiceStatus.dwCheckPoint = 0;
    else
      ++DhcpGlobalServiceStatus.dwCheckPoint;
    if ( !SetServiceStatus(DhcpGlobalServiceStatusHandle, &DhcpGlobalServiceStatus) )
    {
      LastError = GetLastError();
      v0 = LastError;
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_D(1025, 11, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, LastError);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x18000eafc  push    rbx
0x18000eafe  sub     rsp, 20h
0x18000eb02  mov     rcx, cs:DhcpGlobalServiceStatusHandle; hServiceStatus
0x18000eb09  xor     ebx, ebx
0x18000eb0b  test    rcx, rcx
0x18000eb0e  jz      short loc_18000EB33
0x18000eb10  mov     eax, cs:DhcpGlobalServiceStatus.dwCurrentState
0x18000eb16  cmp     eax, 4
0x18000eb19  jnz     short loc_18000EB3B
0x18000eb1b  mov     qword ptr cs:DhcpGlobalServiceStatus.dwCheckPoint, rbx
0x18000eb22  lea     rdx, DhcpGlobalServiceStatus; lpServiceStatus
0x18000eb29  call    cs:__imp_SetServiceStatus
0x18000eb2f  test    eax, eax
0x18000eb31  jz      short loc_18000EB48
0x18000eb33  mov     eax, ebx
0x18000eb35  add     rsp, 20h
0x18000eb39  pop     rbx
0x18000eb3a  retn
0x18000eb3b  cmp     eax, 1
0x18000eb3e  jz      short loc_18000EB1B
0x18000eb40  inc     cs:DhcpGlobalServiceStatus.dwCheckPoint
0x18000eb46  jmp     short loc_18000EB22
0x18000eb48  call    cs:__imp_GetLastError
0x18000eb4e  mov     ebx, eax
0x18000eb50  test    byte ptr cs:xmmword_1800616A0, 2
0x18000eb57  jz      short loc_18000EB33
0x18000eb59  mov     edx, 0Bh
0x18000eb5e  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x18000eb65  mov     ecx, 401h
0x18000eb6a  mov     r9d, eax
0x18000eb6d  call    WPP_SF_D
0x18000eb72  jmp     short loc_18000EB33
```
