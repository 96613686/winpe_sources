# PopulateAndInsertRecvCtxtInGlobalList

- ea: `0x18000fb90`
- end: `0x18000fc0b`
- name: `PopulateAndInsertRecvCtxtInGlobalList`
- size: `123`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180016d60`
- `0x180026494`
- `0x180030e74`
- `0x180033480`

## callees

- `0x18000fb90`
- `0x18000fc14`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000fbba`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000fbba`
- `WS2_32!WSACreateEvent` at `0x18000fbd5`
- `WS2_32!WSACreateEvent` at `0x18000fbd5`
- `WS2_32!__imp_WSAGetLastError` at `0x18000fbeb`
- `WS2_32!__imp_WSAGetLastError` at `0x18000fbeb`

## pseudocode

```c
int __fastcall PopulateAndInsertRecvCtxtInGlobalList(
        __int64 a1,
        __int64 a2,
        _DWORD *a3,
        int a4,
        unsigned int a5,
        _DWORD *a6)
{
  ULONGLONG TickCount64; // rax
  ULONGLONG v8; // rcx
  HANDLE v9; // rax
  __int64 v10; // rdx

  *a6 = 0;
  *(_QWORD *)(a1 + 16) = a2;
  *(_DWORD *)(a1 + 24) = *a3;
  *(_QWORD *)(a1 + 32) = a3;
  *(_DWORD *)(a1 + 40) = a4;
  TickCount64 = GetTickCount64();
  v8 = 0;
  if ( TickCount64 + a5 >= TickCount64 )
    v8 = TickCount64 + a5;
  *(_QWORD *)(a1 + 48) = v8;
  v9 = WSACreateEvent();
  *(_QWORD *)(a1 + 56) = v9;
  *(_DWORD *)(a1 + 64) = 0;
  if ( !v9 )
    return WSAGetLastError();
  InsertInPriorityList(a1, v10, a6);
  return 0;
}

```

## disassembly

```asm
0x18000fb90  mov     [rsp+arg_0], rbx
0x18000fb95  push    rdi
0x18000fb96  sub     rsp, 20h
0x18000fb9a  mov     rdi, [rsp+28h+arg_28]
0x18000fb9f  mov     rbx, rcx
0x18000fba2  mov     dword ptr [rdi], 0
0x18000fba8  mov     [rcx+10h], rdx
0x18000fbac  mov     eax, [r8]
0x18000fbaf  mov     [rcx+18h], eax
0x18000fbb2  mov     [rcx+20h], r8
0x18000fbb6  mov     [rcx+28h], r9d
0x18000fbba  call    cs:__imp_GetTickCount64
0x18000fbc0  mov     r8d, [rsp+28h+arg_20]
0x18000fbc5  xor     ecx, ecx
0x18000fbc7  add     r8, rax
0x18000fbca  cmp     r8, rax
0x18000fbcd  cmovnb  rcx, r8
0x18000fbd1  mov     [rbx+30h], rcx
0x18000fbd5  call    cs:__imp_WSACreateEvent
0x18000fbdb  mov     [rbx+38h], rax
0x18000fbdf  mov     dword ptr [rbx+40h], 0
0x18000fbe6  test    rax, rax
0x18000fbe9  jnz     short loc_18000FBFC
0x18000fbeb  call    cs:__imp_WSAGetLastError
0x18000fbf1  mov     rbx, [rsp+28h+arg_0]
0x18000fbf6  add     rsp, 20h
0x18000fbfa  pop     rdi
0x18000fbfb  retn
0x18000fbfc  mov     r8, rdi
0x18000fbff  mov     rcx, rbx
0x18000fc02  call    InsertInPriorityList
0x18000fc07  xor     eax, eax
0x18000fc09  jmp     short loc_18000FBF1
```
