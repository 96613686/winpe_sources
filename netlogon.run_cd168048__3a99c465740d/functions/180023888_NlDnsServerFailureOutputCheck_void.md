# NlDnsServerFailureOutputCheck(void)

- ea: `0x180023888`
- end: `0x180023965`
- name: `?NlDnsServerFailureOutputCheck@@YAXXZ`
- size: `221`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180022a8c`

## callees

- `0x180007518`
- `0x18000d324`
- `0x180023888`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800238bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023910`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800238bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023910`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800238a7`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800238a7`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800238ed`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800238ed`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800238ff`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180023928`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800238ff`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180023928`

## string_xrefs

- `0x1800238c7`: `NlDnsServerFailureOutputCheck: OpenSCManager failed: 0x%lx\n`

## pseudocode

```c
void NlDnsServerFailureOutputCheck(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rbx
  DWORD LastError; // eax
  SC_HANDLE v3; // rdi

  if ( !NlDnsWriteServerFailureEventLog )
  {
    v0 = OpenSCManagerW(0, 0, 1u);
    v1 = v0;
    if ( v0 )
    {
      v3 = OpenServiceW(v0, L"DNS", 5u);
      CloseServiceHandle(v1);
      if ( v3 )
      {
        CloseServiceHandle(v3);
      }
      else if ( GetLastError() == 1060 )
      {
LABEL_10:
        NlDnsWriteServerFailureEventLog = 1;
        return;
      }
    }
    else
    {
      LastError = GetLastError();
      NlPrintRoutine(0x100u, L"NlDnsServerFailureOutputCheck: OpenSCManager failed: 0x%lx\n", LastError);
    }
    if ( NlDnsInitCount > 1 || NetpDcElapsedTime(NlGlobalDnsStartTime) > 0x1D4C0 )
      goto LABEL_10;
  }
}

```

## disassembly

```asm
0x180023888  mov     [rsp+arg_0], rbx
0x18002388d  push    rdi
0x18002388e  sub     rsp, 20h
0x180023892  cmp     cs:?NlDnsWriteServerFailureEventLog@@3HA, 0; int NlDnsWriteServerFailureEventLog
0x180023899  jnz     loc_180023959
0x18002389f  xor     edx, edx; lpDatabaseName
0x1800238a1  xor     ecx, ecx; lpMachineName
0x1800238a3  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800238a7  call    cs:__imp_OpenSCManagerW
0x1800238ae  nop     dword ptr [rax+rax+00h]
0x1800238b3  mov     rbx, rax
0x1800238b6  test    rax, rax
0x1800238b9  jnz     short loc_1800238DD
0x1800238bb  call    cs:__imp_GetLastError
0x1800238c2  nop     dword ptr [rax+rax+00h]
0x1800238c7  lea     rdx, aNldnsserverfai; "NlDnsServerFailureOutputCheck: OpenSCMa"...
0x1800238ce  mov     ecx, 100h; unsigned int
0x1800238d3  mov     r8d, eax
0x1800238d6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800238db  jmp     short loc_180023934
0x1800238dd  mov     r8d, 5; dwDesiredAccess
0x1800238e3  lea     rdx, ServiceName; "DNS"
0x1800238ea  mov     rcx, rbx; hSCManager
0x1800238ed  call    cs:__imp_OpenServiceW
0x1800238f4  nop     dword ptr [rax+rax+00h]
0x1800238f9  mov     rcx, rbx; hSCObject
0x1800238fc  mov     rdi, rax
0x1800238ff  call    cs:__imp_CloseServiceHandle
0x180023906  nop     dword ptr [rax+rax+00h]
0x18002390b  test    rdi, rdi
0x18002390e  jnz     short loc_180023925
0x180023910  call    cs:__imp_GetLastError
0x180023917  nop     dword ptr [rax+rax+00h]
0x18002391c  cmp     eax, 424h
0x180023921  jz      short loc_18002394F
0x180023923  jmp     short loc_180023934
0x180023925  mov     rcx, rdi; hSCObject
0x180023928  call    cs:__imp_CloseServiceHandle
0x18002392f  nop     dword ptr [rax+rax+00h]
0x180023934  cmp     cs:?NlDnsInitCount@@3KA, 1; ulong NlDnsInitCount
0x18002393b  ja      short loc_18002394F
0x18002393d  mov     ecx, cs:?NlGlobalDnsStartTime@@3KA; unsigned int
0x180023943  call    ?NetpDcElapsedTime@@YAKK@Z; NetpDcElapsedTime(ulong)
0x180023948  cmp     eax, 1D4C0h
0x18002394d  jbe     short loc_180023959
0x18002394f  mov     cs:?NlDnsWriteServerFailureEventLog@@3HA, 1; int NlDnsWriteServerFailureEventLog
0x180023959  mov     rbx, [rsp+28h+arg_0]
0x18002395e  add     rsp, 20h
0x180023962  pop     rdi
0x180023963  retn
```
