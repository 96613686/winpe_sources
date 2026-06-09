# CServiceManager::HrOpen(CSLOCK,ulong,ushort const *,ushort const *)

- ea: `0x18003fb94`
- end: `0x18003fbda`
- name: `?HrOpen@CServiceManager@@QEAAJW4CSLOCK@@KPEBG1@Z`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18003fbe0`

## callees

- `0x180034ba0`
- `0x18003fb94`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003fbba`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003fbba`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003fba5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003fba5`

## pseudocode

```c
__int64 __fastcall CServiceManager::HrOpen(SC_HANDLE *a1)
{
  SC_HANDLE v2; // rcx
  SC_HANDLE v3; // rax

  v2 = *a1;
  if ( v2 )
  {
    CloseServiceHandle(v2);
    *a1 = 0;
  }
  v3 = OpenSCManagerW(0, 0, 1u);
  *a1 = v3;
  if ( v3 )
    return 0;
  else
    return HrFromLastWin32Error();
}

```

## disassembly

```asm
0x18003fb94  push    rbx
0x18003fb96  sub     rsp, 20h
0x18003fb9a  mov     rbx, rcx
0x18003fb9d  mov     rcx, [rcx]; hSCObject
0x18003fba0  test    rcx, rcx
0x18003fba3  jz      short loc_18003FBB2
0x18003fba5  call    cs:__imp_CloseServiceHandle
0x18003fbab  mov     qword ptr [rbx], 0
0x18003fbb2  xor     edx, edx; lpDatabaseName
0x18003fbb4  xor     ecx, ecx; lpMachineName
0x18003fbb6  lea     r8d, [rdx+1]; dwDesiredAccess
0x18003fbba  call    cs:__imp_OpenSCManagerW
0x18003fbc0  mov     [rbx], rax
0x18003fbc3  test    rax, rax
0x18003fbc6  jz      short loc_18003FBD0
0x18003fbc8  xor     eax, eax
0x18003fbca  add     rsp, 20h
0x18003fbce  pop     rbx
0x18003fbcf  retn
0x18003fbd0  add     rsp, 20h
0x18003fbd4  pop     rbx
0x18003fbd5  jmp     ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
```
