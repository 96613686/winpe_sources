# FreeServiceThreadSecurityInfo(_SERVICE_THREAD_SECURITY_INFO * *)

- ea: `0x18002345c`
- end: `0x1800234a9`
- name: `?FreeServiceThreadSecurityInfo@@YAKPEAPEAU_SERVICE_THREAD_SECURITY_INFO@@@Z`
- size: `77`
- prototype: `__int64 __fastcall(void ***)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180017f30`
- `0x1800234b0`

## callees

- `0x18002345c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002348f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002348f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023481`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023481`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180023474`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180023474`

## pseudocode

```c
__int64 __fastcall FreeServiceThreadSecurityInfo(void ***a1)
{
  void **v1; // rbx
  void *v3; // rcx
  HANDLE ProcessHeap; // rax
  __int64 result; // rax

  v1 = *a1;
  v3 = **a1;
  if ( v3 )
  {
    FreeSid(v3);
    *v1 = 0;
  }
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v1);
  result = 0;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x18002345c  mov     [rsp+arg_0], rbx
0x180023461  push    rdi
0x180023462  sub     rsp, 20h
0x180023466  mov     rbx, [rcx]
0x180023469  mov     rdi, rcx
0x18002346c  mov     rcx, [rbx]; pSid
0x18002346f  test    rcx, rcx
0x180023472  jz      short loc_180023481
0x180023474  call    cs:__imp_FreeSid
0x18002347a  mov     qword ptr [rbx], 0
0x180023481  call    cs:__imp_GetProcessHeap
0x180023487  mov     r8, rbx; lpMem
0x18002348a  xor     edx, edx; dwFlags
0x18002348c  mov     rcx, rax; hHeap
0x18002348f  call    cs:__imp_HeapFree
0x180023495  mov     rbx, [rsp+28h+arg_0]
0x18002349a  xor     eax, eax
0x18002349c  mov     qword ptr [rdi], 0
0x1800234a3  add     rsp, 20h
0x1800234a7  pop     rdi
0x1800234a8  retn
```
