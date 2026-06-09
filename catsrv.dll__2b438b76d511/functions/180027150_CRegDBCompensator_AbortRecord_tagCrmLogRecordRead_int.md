# CRegDBCompensator::AbortRecord(tagCrmLogRecordRead,int *)

- ea: `0x180027150`
- end: `0x180027250`
- name: `?AbortRecord@CRegDBCompensator@@UEAAJUtagCrmLogRecordRead@@PEAH@Z`
- size: `256`
- prototype: `__int64 __fastcall(CRegDBCompensator *__hidden this, struct tagCrmLogRecordRead *__struct_ptr, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a01c`
- `0x180027150`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800271a2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800271a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002720e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002720e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800271c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800271c2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800271d3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002722d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180027236`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800271d3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002722d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180027236`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180027189`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180027189`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x180027224`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x180027224`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180027202`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180027202`

## pseudocode

```c
__int64 __fastcall CRegDBCompensator::AbortRecord(CRegDBCompensator *this, struct tagCrmLogRecordRead *a2, int *a3)
{
  BYTE *pBlobData; // rbx
  SC_HANDLE v4; // rdi
  unsigned __int64 v5; // r14
  unsigned __int16 *v6; // rax
  WCHAR *v7; // rbp
  const unsigned __int16 *v9; // r8
  SC_HANDLE v10; // rbx
  int v11; // esi

  if ( a2->blobUserData.cbSize >= 4 )
  {
    pBlobData = a2->blobUserData.pBlobData;
    if ( *(_DWORD *)pBlobData != 1 )
      return 0;
    if ( a2->blobUserData.cbSize >= 0x208 )
    {
      v4 = OpenSCManagerW(0, 0, 0x80000000);
      if ( v4 )
      {
        v5 = (unsigned int)(lstrlenW((LPCWSTR)pBlobData + 2) + 1);
        v6 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v5, 2u));
        v7 = v6;
        if ( !v6 )
        {
          CloseServiceHandle(v4);
          return 2147942414LL;
        }
        v9 = (const unsigned __int16 *)(pBlobData + 4);
        v10 = 0;
        v11 = StringCchCopyW(v6, v5, v9);
        if ( v11 >= 0 )
          v10 = OpenServiceW(v4, v7, 0x10000u);
        CoTaskMemFree(v7);
        if ( v11 < 0 )
          return (unsigned int)v11;
        if ( v10 )
        {
          DeleteService(v10);
          CloseServiceHandle(v10);
        }
        CloseServiceHandle(v4);
      }
      return 0;
    }
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x180027150  push    rbx
0x180027152  push    rbp
0x180027153  push    rsi
0x180027154  push    rdi
0x180027155  push    r14
0x180027157  sub     rsp, 20h
0x18002715b  cmp     dword ptr [rdx+8], 4
0x18002715f  jb      loc_180027240
0x180027165  mov     rbx, [rdx+10h]
0x180027169  cmp     dword ptr [rbx], 1
0x18002716c  jnz     loc_18002723C
0x180027172  cmp     dword ptr [rdx+8], 208h
0x180027179  jb      loc_180027240
0x18002717f  xor     edx, edx; lpDatabaseName
0x180027181  xor     ecx, ecx; lpMachineName
0x180027183  mov     r8d, 80000000h; dwDesiredAccess
0x180027189  call    cs:__imp_OpenSCManagerW
0x18002718f  mov     rdi, rax
0x180027192  test    rax, rax
0x180027195  jz      loc_18002723C
0x18002719b  lea     rsi, [rbx+4]
0x18002719f  mov     rcx, rsi; lpString
0x1800271a2  call    cs:__imp_lstrlenW
0x1800271a8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800271af  lea     r14d, [rax+1]
0x1800271b3  mov     eax, 2
0x1800271b8  mul     r14
0x1800271bb  cmovb   rax, rcx
0x1800271bf  mov     rcx, rax; cb
0x1800271c2  call    cs:__imp_CoTaskMemAlloc
0x1800271c8  mov     rbp, rax
0x1800271cb  test    rax, rax
0x1800271ce  jnz     short loc_1800271E0
0x1800271d0  mov     rcx, rdi; hSCObject
0x1800271d3  call    cs:__imp_CloseServiceHandle
0x1800271d9  mov     eax, 8007000Eh
0x1800271de  jmp     short loc_180027245
0x1800271e0  mov     r8, rsi; unsigned __int16 *
0x1800271e3  mov     rdx, r14; unsigned __int64
0x1800271e6  mov     rcx, rbp; unsigned __int16 *
0x1800271e9  xor     ebx, ebx
0x1800271eb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800271f0  mov     esi, eax
0x1800271f2  test    eax, eax
0x1800271f4  js      short loc_18002720B
0x1800271f6  mov     r8d, 10000h; dwDesiredAccess
0x1800271fc  mov     rdx, rbp; lpServiceName
0x1800271ff  mov     rcx, rdi; hSCManager
0x180027202  call    cs:__imp_OpenServiceW
0x180027208  mov     rbx, rax
0x18002720b  mov     rcx, rbp; pv
0x18002720e  call    cs:__imp_CoTaskMemFree
0x180027214  test    esi, esi
0x180027216  jns     short loc_18002721C
0x180027218  mov     eax, esi
0x18002721a  jmp     short loc_180027245
0x18002721c  test    rbx, rbx
0x18002721f  jz      short loc_180027233
0x180027221  mov     rcx, rbx; hService
0x180027224  call    cs:__imp_DeleteService
0x18002722a  mov     rcx, rbx; hSCObject
0x18002722d  call    cs:__imp_CloseServiceHandle
0x180027233  mov     rcx, rdi; hSCObject
0x180027236  call    cs:__imp_CloseServiceHandle
0x18002723c  xor     eax, eax
0x18002723e  jmp     short loc_180027245
0x180027240  mov     eax, 8000FFFFh
0x180027245  add     rsp, 20h
0x180027249  pop     r14
0x18002724b  pop     rdi
0x18002724c  pop     rsi
0x18002724d  pop     rbp
0x18002724e  pop     rbx
0x18002724f  retn
```
