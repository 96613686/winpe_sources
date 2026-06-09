# NlDnsServerFailureOutputCheck(void)

- ea: `0x180022784`
- end: `0x18002283c`
- name: `?NlDnsServerFailureOutputCheck@@YAXXZ`
- size: `184`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180021a28`

## callees

- `0x180007278`
- `0x18000cbe0`
- `0x180022784`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227f4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800227a3`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800227a3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800227dd`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800227dd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800227e9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180022806`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800227e9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180022806`

## string_xrefs

- `0x1800227b7`: `NlDnsServerFailureOutputCheck: OpenSCManager failed: 0x%lx\n`

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
0x180022784  mov     [rsp+arg_0], rbx
0x180022789  push    rdi
0x18002278a  sub     rsp, 20h
0x18002278e  cmp     cs:?NlDnsWriteServerFailureEventLog@@3HA, 0; int NlDnsWriteServerFailureEventLog
0x180022795  jnz     loc_180022831
0x18002279b  xor     edx, edx; lpDatabaseName
0x18002279d  xor     ecx, ecx; lpMachineName
0x18002279f  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800227a3  call    cs:__imp_OpenSCManagerW
0x1800227a9  mov     rbx, rax
0x1800227ac  test    rax, rax
0x1800227af  jnz     short loc_1800227CD
0x1800227b1  call    cs:__imp_GetLastError
0x1800227b7  lea     rdx, aNldnsserverfai; "NlDnsServerFailureOutputCheck: OpenSCMa"...
0x1800227be  mov     ecx, 100h; unsigned int
0x1800227c3  mov     r8d, eax
0x1800227c6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800227cb  jmp     short loc_18002280C
0x1800227cd  mov     r8d, 5; dwDesiredAccess
0x1800227d3  lea     rdx, ServiceName; "DNS"
0x1800227da  mov     rcx, rbx; hSCManager
0x1800227dd  call    cs:__imp_OpenServiceW
0x1800227e3  mov     rcx, rbx; hSCObject
0x1800227e6  mov     rdi, rax
0x1800227e9  call    cs:__imp_CloseServiceHandle
0x1800227ef  test    rdi, rdi
0x1800227f2  jnz     short loc_180022803
0x1800227f4  call    cs:__imp_GetLastError
0x1800227fa  cmp     eax, 424h
0x1800227ff  jz      short loc_180022827
0x180022801  jmp     short loc_18002280C
0x180022803  mov     rcx, rdi; hSCObject
0x180022806  call    cs:__imp_CloseServiceHandle
0x18002280c  cmp     cs:?NlDnsInitCount@@3KA, 1; ulong NlDnsInitCount
0x180022813  ja      short loc_180022827
0x180022815  mov     ecx, cs:?NlGlobalDnsStartTime@@3KA; unsigned int
0x18002281b  call    ?NetpDcElapsedTime@@YAKK@Z; NetpDcElapsedTime(ulong)
0x180022820  cmp     eax, 1D4C0h
0x180022825  jbe     short loc_180022831
0x180022827  mov     cs:?NlDnsWriteServerFailureEventLog@@3HA, 1; int NlDnsWriteServerFailureEventLog
0x180022831  mov     rbx, [rsp+28h+arg_0]
0x180022836  add     rsp, 20h
0x18002283a  pop     rdi
0x18002283b  retn
```
