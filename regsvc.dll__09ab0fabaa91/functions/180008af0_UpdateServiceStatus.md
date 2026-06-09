# UpdateServiceStatus

- ea: `0x180008af0`
- end: `0x180008b50`
- name: `UpdateServiceStatus`
- size: `96`
- prototype: `BOOL __fastcall(int, int, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x180008830`
- `0x180008870`
- `0x180008a60`

## callees

- `0x180008af0`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008b49`

## pseudocode

```c
BOOL __fastcall UpdateServiceStatus(int a1, int a2, int a3)
{
  LODWORD(xmmword_18002BFA4) = a1;
  DWORD2(xmmword_18002BFA4) = a2;
  HIDWORD(qword_18002BFB4) = a3;
  DWORD1(xmmword_18002BFA4) = a1 != 2;
  if ( a1 == 4 || a1 == 1 )
    LODWORD(qword_18002BFB4) = 0;
  else
    LODWORD(qword_18002BFB4) = dword_18002B1B4++;
  return SetServiceStatus((SERVICE_STATUS_HANDLE)g_hStatus, (LPSERVICE_STATUS)&g_status);
}

```

## disassembly

```asm
0x180008af0  xor     eax, eax
0x180008af2  mov     dword ptr cs:xmmword_18002BFA4, ecx
0x180008af8  cmp     ecx, 2
0x180008afb  mov     dword ptr cs:xmmword_18002BFA4+8, edx
0x180008b01  mov     dword ptr cs:qword_18002BFB4+4, r8d
0x180008b08  setnz   al
0x180008b0b  mov     dword ptr cs:xmmword_18002BFA4+4, eax
0x180008b11  cmp     ecx, 4
0x180008b14  jz      short loc_180008B31
0x180008b16  cmp     ecx, 1
0x180008b19  jz      short loc_180008B31
0x180008b1b  mov     eax, cs:dword_18002B1B4
0x180008b21  mov     dword ptr cs:qword_18002BFB4, eax
0x180008b27  inc     eax
0x180008b29  mov     cs:dword_18002B1B4, eax
0x180008b2f  jmp     short loc_180008B3B
0x180008b31  mov     dword ptr cs:qword_18002BFB4, 0
0x180008b3b  mov     rcx, cs:g_hStatus
0x180008b42  lea     rdx, g_status
0x180008b49  jmp     cs:__imp_SetServiceStatus
```
