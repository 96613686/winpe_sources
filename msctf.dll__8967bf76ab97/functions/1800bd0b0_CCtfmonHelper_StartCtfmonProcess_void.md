# CCtfmonHelper::StartCtfmonProcess(void)

- ea: `0x1800bd0b0`
- end: `0x1800bd147`
- name: `?StartCtfmonProcess@CCtfmonHelper@@SA_NXZ`
- size: `151`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800bd150`

## callees

- `0x1800bd0b0`
- `0x1800bd464`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd111`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd111`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800bd102`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800bd102`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800bd0ec`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800bd0ec`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800bd0ce`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800bd0ce`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800bd125`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800bd12e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800bd125`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800bd12e`

## string_xrefs

- `0x1800bd0e3`: `TextInputManagementService`

## pseudocode

```c
char __fastcall CCtfmonHelper::StartCtfmonProcess(const unsigned __int16 *a1)
{
  char v1; // di
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  bool v4; // bl
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rbp

  v1 = 1;
  if ( !CCtfmonHelper::_SetSessionEvent(a1) )
  {
    v2 = OpenSCManagerW(0, 0, 1u);
    v3 = v2;
    if ( !v2 )
      return 0;
    v4 = 0;
    v5 = OpenServiceW(v2, L"TextInputManagementService", 0x10u);
    v6 = v5;
    if ( v5 )
    {
      v4 = StartServiceW(v5, 0, 0) || GetLastError() == 1056;
      CloseServiceHandle(v6);
    }
    CloseServiceHandle(v3);
    if ( !v4 )
      return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x1800bd0b0  push    rbx
0x1800bd0b2  push    rbp
0x1800bd0b3  push    rsi
0x1800bd0b4  push    rdi
0x1800bd0b5  sub     rsp, 28h
0x1800bd0b9  call    ?_SetSessionEvent@CCtfmonHelper@@CA_NPEBG@Z; CCtfmonHelper::_SetSessionEvent(ushort const *)
0x1800bd0be  mov     edi, 1
0x1800bd0c3  test    al, al
0x1800bd0c5  jnz     short loc_1800BD13B
0x1800bd0c7  mov     r8d, edi; dwDesiredAccess
0x1800bd0ca  xor     edx, edx; lpDatabaseName
0x1800bd0cc  xor     ecx, ecx; lpMachineName
0x1800bd0ce  call    cs:__imp_OpenSCManagerW
0x1800bd0d4  mov     rsi, rax
0x1800bd0d7  test    rax, rax
0x1800bd0da  jz      short loc_1800BD138
0x1800bd0dc  lea     r8d, [rdi+0Fh]; dwDesiredAccess
0x1800bd0e0  mov     rcx, rax; hSCManager
0x1800bd0e3  lea     rdx, ServiceName; "TextInputManagementService"
0x1800bd0ea  xor     bl, bl
0x1800bd0ec  call    cs:__imp_OpenServiceW
0x1800bd0f2  mov     rbp, rax
0x1800bd0f5  test    rax, rax
0x1800bd0f8  jz      short loc_1800BD12B
0x1800bd0fa  xor     r8d, r8d; lpServiceArgVectors
0x1800bd0fd  xor     edx, edx; dwNumServiceArgs
0x1800bd0ff  mov     rcx, rax; hService
0x1800bd102  call    cs:__imp_StartServiceW
0x1800bd108  test    eax, eax
0x1800bd10a  jz      short loc_1800BD111
0x1800bd10c  mov     bl, dil
0x1800bd10f  jmp     short loc_1800BD122
0x1800bd111  call    cs:__imp_GetLastError
0x1800bd117  cmp     eax, 420h
0x1800bd11c  movzx   ebx, bl
0x1800bd11f  cmovz   ebx, edi
0x1800bd122  mov     rcx, rbp; hSCObject
0x1800bd125  call    cs:__imp_CloseServiceHandle
0x1800bd12b  mov     rcx, rsi; hSCObject
0x1800bd12e  call    cs:__imp_CloseServiceHandle
0x1800bd134  test    bl, bl
0x1800bd136  jnz     short loc_1800BD13B
0x1800bd138  xor     dil, dil
0x1800bd13b  mov     al, dil
0x1800bd13e  add     rsp, 28h
0x1800bd142  pop     rdi
0x1800bd143  pop     rsi
0x1800bd144  pop     rbp
0x1800bd145  pop     rbx
0x1800bd146  retn
```
