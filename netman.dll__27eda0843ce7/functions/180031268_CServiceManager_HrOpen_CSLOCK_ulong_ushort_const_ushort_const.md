# CServiceManager::HrOpen(CSLOCK,ulong,ushort const *,ushort const *)

- ea: `0x180031268`
- end: `0x1800312ae`
- name: `?HrOpen@CServiceManager@@QEAAJW4CSLOCK@@KPEBG1@Z`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800312b4`

## callees

- `0x18003060c`
- `0x180031268`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x180031279`
- `ADVAPI32!CloseServiceHandle` at `0x180031279`
- `ADVAPI32!OpenSCManagerW` at `0x18003128e`
- `ADVAPI32!OpenSCManagerW` at `0x18003128e`

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
0x180031268  push    rbx
0x18003126a  sub     rsp, 20h
0x18003126e  mov     rbx, rcx
0x180031271  mov     rcx, [rcx]; hSCObject
0x180031274  test    rcx, rcx
0x180031277  jz      short loc_180031286
0x180031279  call    cs:__imp_CloseServiceHandle
0x18003127f  mov     qword ptr [rbx], 0
0x180031286  xor     edx, edx; lpDatabaseName
0x180031288  xor     ecx, ecx; lpMachineName
0x18003128a  lea     r8d, [rdx+1]; dwDesiredAccess
0x18003128e  call    cs:__imp_OpenSCManagerW
0x180031294  mov     [rbx], rax
0x180031297  test    rax, rax
0x18003129a  jz      short loc_1800312A4
0x18003129c  xor     eax, eax
0x18003129e  add     rsp, 20h
0x1800312a2  pop     rbx
0x1800312a3  retn
0x1800312a4  add     rsp, 20h
0x1800312a8  pop     rbx
0x1800312a9  jmp     ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
```
