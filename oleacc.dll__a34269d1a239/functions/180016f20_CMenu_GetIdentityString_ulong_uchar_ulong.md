# CMenu::GetIdentityString(ulong,uchar * *,ulong *)

- ea: `0x180016f20`
- end: `0x180016fb0`
- name: `?GetIdentityString@CMenu@@UEAAJKPEAPEAEPEAK@Z`
- size: `144`
- prototype: `__int64 __fastcall(CMenu *__hidden this, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180016f20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016f50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016f50`
- `USER32!GetWindowThreadProcessId` at `0x180016f6f`
- `USER32!GetWindowThreadProcessId` at `0x180016f6f`

## pseudocode

```c
__int64 __fastcall CMenu::GetIdentityString(CMenu *this, int a2, unsigned __int8 **a3, unsigned int *a4)
{
  unsigned __int8 *v8; // rbx
  HWND v9; // rcx
  int v10; // ecx
  DWORD v11; // eax
  __int64 result; // rax
  DWORD dwProcessId; // [rsp+50h] [rbp+18h] BYREF

  *a3 = 0;
  *a4 = 0;
  v8 = (unsigned __int8 *)CoTaskMemAlloc(0x10u);
  if ( !v8 )
    return 2147942414LL;
  v9 = (HWND)*((_QWORD *)this + 6);
  dwProcessId = 0;
  GetWindowThreadProcessId(v9, &dwProcessId);
  v10 = *((_DWORD *)this + 24);
  v11 = dwProcessId;
  *(_DWORD *)v8 = -2147483646;
  *((_DWORD *)v8 + 1) = v11;
  result = 0;
  *((_DWORD *)v8 + 2) = v10;
  *((_DWORD *)v8 + 3) = a2;
  *a3 = v8;
  *a4 = 16;
  return result;
}

```

## disassembly

```asm
0x180016f20  mov     [rsp+arg_0], rbx
0x180016f25  mov     [rsp+arg_8], rbp
0x180016f2a  push    rsi
0x180016f2b  push    rdi
0x180016f2c  push    r14
0x180016f2e  sub     rsp, 20h
0x180016f32  mov     rdi, rcx
0x180016f35  mov     qword ptr [r8], 0
0x180016f3c  mov     ecx, 10h; cb
0x180016f41  mov     dword ptr [r9], 0
0x180016f48  mov     rsi, r9
0x180016f4b  mov     r14, r8
0x180016f4e  mov     ebp, edx
0x180016f50  call    cs:__imp_CoTaskMemAlloc
0x180016f56  mov     rbx, rax
0x180016f59  test    rax, rax
0x180016f5c  jz      short loc_180016FA9
0x180016f5e  mov     rcx, [rdi+30h]; hWnd
0x180016f62  lea     rdx, [rsp+38h+dwProcessId]; lpdwProcessId
0x180016f67  mov     [rsp+38h+dwProcessId], 0
0x180016f6f  call    cs:__imp_GetWindowThreadProcessId
0x180016f75  mov     ecx, [rdi+60h]
0x180016f78  mov     eax, [rsp+38h+dwProcessId]
0x180016f7c  mov     dword ptr [rbx], 80000002h
0x180016f82  mov     [rbx+4], eax
0x180016f85  xor     eax, eax
0x180016f87  mov     [rbx+8], ecx
0x180016f8a  mov     [rbx+0Ch], ebp
0x180016f8d  mov     [r14], rbx
0x180016f90  mov     dword ptr [rsi], 10h
0x180016f96  mov     rbx, [rsp+38h+arg_0]
0x180016f9b  mov     rbp, [rsp+38h+arg_8]
0x180016fa0  add     rsp, 20h
0x180016fa4  pop     r14
0x180016fa6  pop     rdi
0x180016fa7  pop     rsi
0x180016fa8  retn
0x180016fa9  mov     eax, 8007000Eh
0x180016fae  jmp     short loc_180016F96
```
