# CreateSystemEvent(SystemEventInfo const *)

- ea: `0x140007b80`
- end: `0x140007c12`
- name: `?CreateSystemEvent@@YAPEAXPEBUSystemEventInfo@@@Z`
- size: `146`
- prototype: `HANDLE __fastcall(const struct SystemEventInfo *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140006bb0`
- `0x140007af4`

## callees

- `0x140007b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140007beb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140007beb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140007bf9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140007bf9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140007baa`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140007baa`

## pseudocode

```c
HANDLE __fastcall CreateSystemEvent(const struct SystemEventInfo *a1)
{
  const WCHAR *v2; // rcx
  const WCHAR *v4; // r9
  HANDLE v5; // rbx
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+20h] [rbp-28h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp+8h] BYREF

  v2 = (const WCHAR *)*((_QWORD *)a1 + 1);
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v2, 1u, &SecurityDescriptor, 0) )
    return 0;
  v4 = *(const WCHAR **)a1;
  EventAttributes.lpSecurityDescriptor = SecurityDescriptor;
  *(_QWORD *)&EventAttributes.nLength = 24;
  *(_QWORD *)&EventAttributes.bInheritHandle = 0;
  v5 = CreateEventW(&EventAttributes, 0, 0, v4);
  LocalFree(SecurityDescriptor);
  return v5;
}

```

## disassembly

```asm
0x140007b80  mov     [rsp+arg_8], rbx
0x140007b85  mov     [rsp+arg_10], rsi
0x140007b8a  push    rdi
0x140007b8b  sub     rsp, 40h
0x140007b8f  mov     rdi, rcx
0x140007b92  lea     r8, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x140007b97  mov     rcx, [rcx+8]; StringSecurityDescriptor
0x140007b9b  xor     esi, esi
0x140007b9d  xor     r9d, r9d; SecurityDescriptorSize
0x140007ba0  mov     [rsp+48h+SecurityDescriptor], rsi
0x140007ba5  mov     edx, 1; StringSDRevision
0x140007baa  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140007bb0  test    eax, eax
0x140007bb2  jnz     short loc_140007BC6
0x140007bb4  mov     eax, esi
0x140007bb6  mov     rbx, [rsp+48h+arg_8]
0x140007bbb  mov     rsi, [rsp+48h+arg_10]
0x140007bc0  add     rsp, 40h
0x140007bc4  pop     rdi
0x140007bc5  retn
0x140007bc6  mov     rax, [rsp+48h+SecurityDescriptor]
0x140007bcb  lea     rcx, [rsp+48h+EventAttributes]; lpEventAttributes
0x140007bd0  mov     r9, [rdi]; lpName
0x140007bd3  xor     r8d, r8d; bInitialState
0x140007bd6  xor     edx, edx; bManualReset
0x140007bd8  mov     [rsp+48h+EventAttributes.lpSecurityDescriptor], rax
0x140007bdd  mov     qword ptr [rsp+48h+EventAttributes.nLength], 18h
0x140007be6  mov     qword ptr [rsp+48h+EventAttributes.bInheritHandle], rsi
0x140007beb  call    cs:__imp_CreateEventW
0x140007bf1  mov     rcx, [rsp+48h+SecurityDescriptor]; hMem
0x140007bf6  mov     rbx, rax
0x140007bf9  call    cs:__imp_LocalFree
0x140007bff  mov     rsi, [rsp+48h+arg_10]
0x140007c04  mov     rax, rbx
0x140007c07  mov     rbx, [rsp+48h+arg_8]
0x140007c0c  add     rsp, 40h
0x140007c10  pop     rdi
0x140007c11  retn
```
