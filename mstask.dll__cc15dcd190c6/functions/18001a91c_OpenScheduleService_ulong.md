# OpenScheduleService(ulong)

- ea: `0x18001a91c`
- end: `0x18001a96c`
- name: `?OpenScheduleService@@YAPEAUSC_HANDLE__@@K@Z`
- size: `80`
- prototype: `struct SC_HANDLE__ *__fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18001a868`

## callees

- `0x18001a91c`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001a92e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001a92e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001a94c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001a94c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001a958`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001a958`

## pseudocode

```c
struct SC_HANDLE__ *__fastcall OpenScheduleService()
{
  struct SC_HANDLE__ *result; // rax
  SC_HANDLE v1; // rdi
  SC_HANDLE v2; // rbx

  result = OpenSCManagerW(0, 0, 1u);
  v1 = result;
  if ( result )
  {
    v2 = OpenServiceW(result, L"Schedule", 4u);
    CloseServiceHandle(v1);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x18001a91c  mov     [rsp+arg_0], rbx
0x18001a921  push    rdi
0x18001a922  sub     rsp, 20h
0x18001a926  xor     edx, edx; lpDatabaseName
0x18001a928  xor     ecx, ecx; lpMachineName
0x18001a92a  lea     r8d, [rdx+1]; dwDesiredAccess
0x18001a92e  call    cs:__imp_OpenSCManagerW
0x18001a934  mov     rdi, rax
0x18001a937  test    rax, rax
0x18001a93a  jz      short loc_18001A961
0x18001a93c  mov     r8d, 4; dwDesiredAccess
0x18001a942  lea     rdx, ServiceName; "Schedule"
0x18001a949  mov     rcx, rdi; hSCManager
0x18001a94c  call    cs:__imp_OpenServiceW
0x18001a952  mov     rcx, rdi; hSCObject
0x18001a955  mov     rbx, rax
0x18001a958  call    cs:__imp_CloseServiceHandle
0x18001a95e  mov     rax, rbx
0x18001a961  mov     rbx, [rsp+28h+arg_0]
0x18001a966  add     rsp, 20h
0x18001a96a  pop     rdi
0x18001a96b  retn
```
