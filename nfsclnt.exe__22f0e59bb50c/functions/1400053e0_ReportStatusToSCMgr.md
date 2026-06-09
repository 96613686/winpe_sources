# ReportStatusToSCMgr

- ea: `0x1400053e0`
- end: `0x14000546e`
- name: `ReportStatusToSCMgr`
- size: `142`
- prototype: `__int64 __fastcall(DWORD, DWORD, DWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140005850`
- `0x140005890`
- `0x14000664c`
- `0x140007124`

## callees

- `0x140005180`
- `0x1400053e0`

## import_xrefs

- `ADVAPI32!SetServiceStatus` at `0x14000543f`
- `ADVAPI32!SetServiceStatus` at `0x14000543f`

## string_xrefs

- `0x140005451`: `base\fs\remotefs\nfs4\client\nfsclient\daccess.c`

## pseudocode

```c
__int64 __fastcall ReportStatusToSCMgr(DWORD a1, DWORD a2, DWORD a3)
{
  unsigned int v3; // ebx

  ssStatus.dwCurrentState = a1;
  ssStatus.dwWin32ExitCode = a2;
  ssStatus.dwWaitHint = a3;
  ssStatus.dwControlsAccepted = a1 != 2;
  if ( a1 == 4 || a1 == 1 )
    ssStatus.dwCheckPoint = 0;
  else
    ssStatus.dwCheckPoint = dword_140020314++;
  v3 = SetServiceStatus(sshStatusHandle, &ssStatus);
  if ( !v3 )
    LOG_ERROR_EVENT_WIN32(
      (int)&EVENT_ERROR_SETSERVICESTATUS,
      0,
      (int)L"base\\fs\\remotefs\\nfs4\\client\\nfsclient\\daccess.c",
      351);
  return v3;
}

```

## disassembly

```asm
0x1400053e0  push    rbx
0x1400053e2  sub     rsp, 20h
0x1400053e6  xor     eax, eax
0x1400053e8  mov     cs:ssStatus.dwCurrentState, ecx
0x1400053ee  cmp     ecx, 2
0x1400053f1  mov     cs:ssStatus.dwWin32ExitCode, edx
0x1400053f7  mov     cs:ssStatus.dwWaitHint, r8d
0x1400053fe  setnz   al
0x140005401  mov     cs:ssStatus.dwControlsAccepted, eax
0x140005407  cmp     ecx, 4
0x14000540a  jz      short loc_140005427
0x14000540c  cmp     ecx, 1
0x14000540f  jz      short loc_140005427
0x140005411  mov     eax, cs:dword_140020314
0x140005417  mov     cs:ssStatus.dwCheckPoint, eax
0x14000541d  inc     eax
0x14000541f  mov     cs:dword_140020314, eax
0x140005425  jmp     short loc_140005431
0x140005427  mov     cs:ssStatus.dwCheckPoint, 0
0x140005431  mov     rcx, cs:sshStatusHandle; hServiceStatus
0x140005438  lea     rdx, ssStatus; lpServiceStatus
0x14000543f  call    cs:__imp_SetServiceStatus
0x140005445  mov     ebx, eax
0x140005447  test    eax, eax
0x140005449  jnz     short loc_140005466
0x14000544b  mov     r9d, 15Fh; int
0x140005451  lea     r8, aBaseFsRemotefs_0; "base\\fs\\remotefs\\nfs4\\client\\nfscl"...
0x140005458  xor     edx, edx; int
0x14000545a  lea     rcx, EVENT_ERROR_SETSERVICESTATUS; int
0x140005461  call    LOG_ERROR_EVENT_WIN32
0x140005466  mov     eax, ebx
0x140005468  add     rsp, 20h
0x14000546c  pop     rbx
0x14000546d  retn
```
