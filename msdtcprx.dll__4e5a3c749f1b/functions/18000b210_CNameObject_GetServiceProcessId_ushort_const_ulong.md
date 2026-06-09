# CNameObject::GetServiceProcessId(ushort const *,ulong *)

- ea: `0x18000b210`
- end: `0x18000b335`
- name: `?GetServiceProcessId@CNameObject@@AEAAJPEBGPEAK@Z`
- size: `293`
- prototype: `int(CNameObject *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800158d8`
- `0x18004f9f0`

## callees

- `0x18000b210`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b262`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b29a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b262`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b29a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2d5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000b306`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000b30f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000b306`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000b30f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000b28c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000b28c`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x18000b254`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x18000b254`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18000b2cb`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18000b2cb`

## pseudocode

```c
__int64 __fastcall CNameObject::GetServiceProcessId(CNameObject *this, const unsigned __int16 *a2, unsigned int *a3)
{
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rsi
  signed int v7; // eax
  unsigned int v8; // ebx
  SC_HANDLE v9; // rdi
  signed int v10; // eax
  signed int LastError; // eax
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-58h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-50h] BYREF
  __int128 v15; // [rsp+48h] [rbp-40h]
  int v16; // [rsp+58h] [rbp-30h]

  *a3 = 0;
  v16 = 0;
  pcbBytesNeeded = 0;
  *(_OWORD *)Buffer = 0;
  v15 = 0;
  v5 = OpenSCManagerA(0, 0, 1u);
  v6 = v5;
  if ( v5 )
  {
    v9 = OpenServiceW(v5, a2, 4u);
    if ( v9 )
    {
      if ( QueryServiceStatusEx(v9, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
      {
        v8 = 0;
        if ( ((*(_DWORD *)&Buffer[4] - 2) & 0xFFFFFFFD) == 0 )
          *a3 = HIDWORD(v15);
      }
      else
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
      }
      CloseServiceHandle(v9);
    }
    else
    {
      v10 = GetLastError();
      v8 = v10;
      if ( v10 > 0 )
        v8 = (unsigned __int16)v10 | 0x80070000;
    }
    CloseServiceHandle(v6);
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
  }
  return v8;
}

```

## disassembly

```asm
0x18000b210  mov     [rsp+arg_0], rbx
0x18000b215  push    rsi
0x18000b216  push    rdi
0x18000b217  push    r14
0x18000b219  sub     rsp, 70h
0x18000b21d  mov     rax, cs:__security_cookie
0x18000b224  xor     rax, rsp
0x18000b227  mov     [rsp+88h+var_28], rax
0x18000b22c  xor     eax, eax
0x18000b22e  xorps   xmm0, xmm0
0x18000b231  mov     r14, r8
0x18000b234  mov     [r8], eax
0x18000b237  mov     rbx, rdx
0x18000b23a  mov     [rsp+88h+var_30], eax
0x18000b23e  xor     edx, edx; lpDatabaseName
0x18000b240  mov     [rsp+88h+var_58], eax
0x18000b244  lea     r8d, [rax+1]; dwDesiredAccess
0x18000b248  xor     ecx, ecx; lpMachineName
0x18000b24a  movups  xmmword ptr [rsp+88h+Buffer], xmm0
0x18000b24f  movups  [rsp+88h+var_40], xmm0
0x18000b254  call    cs:__imp_OpenSCManagerA
0x18000b25a  mov     rsi, rax
0x18000b25d  test    rax, rax
0x18000b260  jnz     short loc_18000B280
0x18000b262  call    cs:__imp_GetLastError
0x18000b268  mov     ebx, eax
0x18000b26a  test    eax, eax
0x18000b26c  jle     loc_18000B315
0x18000b272  movzx   ebx, ax
0x18000b275  or      ebx, 80070000h
0x18000b27b  jmp     loc_18000B315
0x18000b280  mov     r8d, 4; dwDesiredAccess
0x18000b286  mov     rdx, rbx; lpServiceName
0x18000b289  mov     rcx, rsi; hSCManager
0x18000b28c  call    cs:__imp_OpenServiceW
0x18000b292  mov     rdi, rax
0x18000b295  test    rax, rax
0x18000b298  jnz     short loc_18000B2B1
0x18000b29a  call    cs:__imp_GetLastError
0x18000b2a0  mov     ebx, eax
0x18000b2a2  test    eax, eax
0x18000b2a4  jle     short loc_18000B30C
0x18000b2a6  movzx   ebx, ax
0x18000b2a9  or      ebx, 80070000h
0x18000b2af  jmp     short loc_18000B30C
0x18000b2b1  lea     rax, [rsp+88h+var_58]
0x18000b2b6  mov     r9d, 24h ; '$'; cbBufSize
0x18000b2bc  lea     r8, [rsp+88h+Buffer]; lpBuffer
0x18000b2c1  mov     [rsp+88h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18000b2c6  xor     edx, edx; InfoLevel
0x18000b2c8  mov     rcx, rdi; hService
0x18000b2cb  call    cs:__imp_QueryServiceStatusEx
0x18000b2d1  test    eax, eax
0x18000b2d3  jnz     short loc_18000B2EC
0x18000b2d5  call    cs:__imp_GetLastError
0x18000b2db  mov     ebx, eax
0x18000b2dd  test    eax, eax
0x18000b2df  jle     short loc_18000B303
0x18000b2e1  movzx   ebx, ax
0x18000b2e4  or      ebx, 80070000h
0x18000b2ea  jmp     short loc_18000B303
0x18000b2ec  mov     eax, dword ptr [rsp+88h+Buffer+4]
0x18000b2f0  xor     ebx, ebx
0x18000b2f2  add     eax, 0FFFFFFFEh
0x18000b2f5  test    eax, 0FFFFFFFDh
0x18000b2fa  jnz     short loc_18000B303
0x18000b2fc  mov     ecx, dword ptr [rsp+88h+var_40+0Ch]
0x18000b300  mov     [r14], ecx
0x18000b303  mov     rcx, rdi; hSCObject
0x18000b306  call    cs:__imp_CloseServiceHandle
0x18000b30c  mov     rcx, rsi; hSCObject
0x18000b30f  call    cs:__imp_CloseServiceHandle
0x18000b315  mov     eax, ebx
0x18000b317  mov     rcx, [rsp+88h+var_28]
0x18000b31c  xor     rcx, rsp; StackCookie
0x18000b31f  call    __security_check_cookie
0x18000b324  mov     rbx, [rsp+88h+arg_0]
0x18000b32c  add     rsp, 70h
0x18000b330  pop     r14
0x18000b332  pop     rdi
0x18000b333  pop     rsi
0x18000b334  retn
```
