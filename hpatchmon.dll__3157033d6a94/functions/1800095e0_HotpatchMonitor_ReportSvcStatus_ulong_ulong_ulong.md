# HotpatchMonitor::ReportSvcStatus(ulong,ulong,ulong)

- ea: `0x1800095e0`
- end: `0x180009669`
- name: `?ReportSvcStatus@HotpatchMonitor@@MEAAJKKK@Z`
- size: `137`
- prototype: `__int64 __fastcall(HotpatchMonitor *this, DWORD, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update`

## callees

- `0x1800095e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000964c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000964c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180009642`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180009642`

## pseudocode

```c
__int64 __fastcall HotpatchMonitor::ReportSvcStatus(HotpatchMonitor *this, DWORD a2, int a3, int a4)
{
  unsigned int v4; // ebx
  int v6; // eax
  int v7; // edx
  struct _SERVICE_STATUS *v8; // rdx
  SERVICE_STATUS_HANDLE v9; // rcx
  signed int LastError; // eax

  v4 = 0;
  if ( a2 == 1 )
  {
    v6 = 0;
    *((_DWORD *)this + 6) = 1;
    v7 = 0;
    goto LABEL_10;
  }
  if ( a2 == 2 || a2 == 3 )
  {
    *((_DWORD *)this + 6) = 0;
    goto LABEL_7;
  }
  if ( a2 != 4 )
  {
LABEL_7:
    v6 = dword_18001E638;
    goto LABEL_8;
  }
  *((_DWORD *)this + 6) = 1029;
  v6 = 0;
LABEL_8:
  v7 = v6 + 1;
LABEL_10:
  dword_18001E638 = v7;
  v8 = (struct _SERVICE_STATUS *)((char *)this + 16);
  *((_DWORD *)this + 9) = v6;
  *((_DWORD *)this + 7) = a3;
  *((_DWORD *)this + 10) = a4;
  v9 = (SERVICE_STATUS_HANDLE)*((_QWORD *)this + 1);
  v8->dwCurrentState = a2;
  if ( !SetServiceStatus(v9, v8) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v4;
}

```

## disassembly

```asm
0x1800095e0  push    rbx
0x1800095e2  sub     rsp, 20h
0x1800095e6  xor     ebx, ebx
0x1800095e8  mov     eax, edx
0x1800095ea  mov     r10d, edx
0x1800095ed  sub     eax, 1
0x1800095f0  jz      short loc_18000961A
0x1800095f2  sub     eax, 1
0x1800095f5  jz      short loc_18000960C
0x1800095f7  sub     eax, 1
0x1800095fa  jz      short loc_18000960C
0x1800095fc  cmp     eax, 1
0x1800095ff  jnz     short loc_18000960F
0x180009601  mov     dword ptr [rcx+18h], 405h
0x180009608  xor     eax, eax
0x18000960a  jmp     short loc_180009615
0x18000960c  mov     [rcx+18h], ebx
0x18000960f  mov     eax, cs:dword_18001E638
0x180009615  lea     edx, [rax+1]
0x180009618  jmp     short loc_180009625
0x18000961a  xor     eax, eax
0x18000961c  mov     dword ptr [rcx+18h], 1
0x180009623  xor     edx, edx
0x180009625  mov     cs:dword_18001E638, edx
0x18000962b  lea     rdx, [rcx+10h]; lpServiceStatus
0x18000962f  mov     [rcx+24h], eax
0x180009632  mov     [rcx+1Ch], r8d
0x180009636  mov     [rcx+28h], r9d
0x18000963a  mov     rcx, [rcx+8]; hServiceStatus
0x18000963e  mov     [rdx+4], r10d
0x180009642  call    cs:__imp_SetServiceStatus
0x180009648  test    eax, eax
0x18000964a  jnz     short loc_180009661
0x18000964c  call    cs:__imp_GetLastError
0x180009652  mov     ebx, eax
0x180009654  test    eax, eax
0x180009656  jle     short loc_180009661
0x180009658  movzx   ebx, ax
0x18000965b  or      ebx, 80070000h
0x180009661  mov     eax, ebx
0x180009663  add     rsp, 20h
0x180009667  pop     rbx
0x180009668  retn
```
