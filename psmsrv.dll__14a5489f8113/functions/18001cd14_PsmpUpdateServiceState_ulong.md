# PsmpUpdateServiceState(ulong)

- ea: `0x18001cd14`
- end: `0x18001cd74`
- name: `?PsmpUpdateServiceState@@YAJK@Z`
- size: `96`
- prototype: `__int64 __fastcall(DWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x18001cd80`

## callees

- `0x18001cd14`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001cd66`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001cd66`

## pseudocode

```c
__int64 __fastcall PsmpUpdateServiceState(DWORD a1)
{
  unsigned int v1; // ebx

  v1 = 0;
  switch ( a1 )
  {
    case 1u:
      goto LABEL_7;
    case 2u:
    case 3u:
      ++PsmpServiceGlobals.dwCheckPoint;
      PsmpServiceGlobals.dwWaitHint = 200;
LABEL_8:
      PsmpServiceGlobals.dwCurrentState = a1;
      SetServiceStatus(hServiceStatus, &PsmpServiceGlobals);
      return v1;
    case 4u:
LABEL_7:
      *(_QWORD *)&PsmpServiceGlobals.dwCheckPoint = 0;
      goto LABEL_8;
  }
  return (unsigned int)-1073741811;
}

```

## disassembly

```asm
0x18001cd14  push    rbx
0x18001cd16  sub     rsp, 20h
0x18001cd1a  mov     eax, ecx
0x18001cd1c  xor     ebx, ebx
0x18001cd1e  sub     eax, 1
0x18001cd21  jz      short loc_18001CD4B
0x18001cd23  sub     eax, 1
0x18001cd26  jz      short loc_18001CD39
0x18001cd28  sub     eax, 1
0x18001cd2b  jz      short loc_18001CD39
0x18001cd2d  cmp     eax, 1
0x18001cd30  jz      short loc_18001CD4B
0x18001cd32  mov     ebx, 0C000000Dh
0x18001cd37  jmp     short loc_18001CD6C
0x18001cd39  inc     cs:?PsmpServiceGlobals@@3U_PSM_SERVICE_GLOBALS@@A.dwCheckPoint; _PSM_SERVICE_GLOBALS PsmpServiceGlobals ...
0x18001cd3f  mov     cs:?PsmpServiceGlobals@@3U_PSM_SERVICE_GLOBALS@@A.dwWaitHint, 0C8h; _PSM_SERVICE_GLOBALS PsmpServiceGlobals ...
0x18001cd49  jmp     short loc_18001CD52
0x18001cd4b  mov     qword ptr cs:?PsmpServiceGlobals@@3U_PSM_SERVICE_GLOBALS@@A.dwCheckPoint, rbx; _PSM_SERVICE_GLOBALS PsmpServiceGlobals ...
0x18001cd52  mov     cs:?PsmpServiceGlobals@@3U_PSM_SERVICE_GLOBALS@@A.dwCurrentState, ecx; _PSM_SERVICE_GLOBALS PsmpServiceGlobals ...
0x18001cd58  lea     rdx, ?PsmpServiceGlobals@@3U_PSM_SERVICE_GLOBALS@@A; lpServiceStatus
0x18001cd5f  mov     rcx, cs:hServiceStatus; hServiceStatus
0x18001cd66  call    cs:__imp_SetServiceStatus
0x18001cd6c  mov     eax, ebx
0x18001cd6e  add     rsp, 20h
0x18001cd72  pop     rbx
0x18001cd73  retn
```
