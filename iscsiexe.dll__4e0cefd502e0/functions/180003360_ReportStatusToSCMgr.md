# ReportStatusToSCMgr

- ea: `0x180003360`
- end: `0x1800033c2`
- name: `ReportStatusToSCMgr`
- size: `98`
- prototype: `BOOL __fastcall(int, int, int)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800032d0`
- `0x1800033d0`
- `0x180013ae0`
- `0x180013b24`

## callees

- `0x180003360`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800033bb`

## pseudocode

```c
BOOL __fastcall ReportStatusToSCMgr(int a1, int a2, int a3)
{
  dword_180027544 = a1;
  dword_18002754C = a2;
  dword_180027558 = a3;
  dword_180027548 = a1 != 2 ? 5 : 0;
  if ( a1 == 4 || a1 == 1 )
    dword_180027554 = 0;
  else
    dword_180027554 = dword_1800270F4++;
  return SetServiceStatus((SERVICE_STATUS_HANDLE)DiscpStatusHandle, (LPSERVICE_STATUS)&DiscpServiceStatus);
}

```

## disassembly

```asm
0x180003360  lea     eax, [rcx-2]
0x180003363  mov     cs:dword_180027544, ecx
0x180003369  neg     eax
0x18000336b  mov     cs:dword_18002754C, edx
0x180003371  mov     cs:dword_180027558, r8d
0x180003378  sbb     eax, eax
0x18000337a  and     eax, 5
0x18000337d  mov     cs:dword_180027548, eax
0x180003383  cmp     ecx, 4
0x180003386  jz      short loc_1800033A3
0x180003388  cmp     ecx, 1
0x18000338b  jz      short loc_1800033A3
0x18000338d  mov     eax, cs:dword_1800270F4
0x180003393  mov     cs:dword_180027554, eax
0x180003399  inc     eax
0x18000339b  mov     cs:dword_1800270F4, eax
0x1800033a1  jmp     short loc_1800033AD
0x1800033a3  mov     cs:dword_180027554, 0
0x1800033ad  mov     rcx, cs:DiscpStatusHandle
0x1800033b4  lea     rdx, DiscpServiceStatus
0x1800033bb  jmp     cs:__imp_SetServiceStatus
```
