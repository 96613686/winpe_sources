# netDbCleanup

- ea: `0x180028dc8`
- end: `0x180028eb5`
- name: `netDbCleanup`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180028ebc`
- `0x18002990c`

## callees

- `0x180021470`
- `0x180026710`
- `0x180028dc8`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e69`

## pseudocode

```c
__int64 __fastcall netDbCleanup(__int64 a1)
{
  LPVOID *v1; // rbx
  _DWORD *v3; // rdi
  __int64 v4; // rbp
  __int64 v5; // rcx
  __int64 v6; // rcx
  int v7; // eax
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  _QWORD *v11; // rsi
  __int64 result; // rax

  v1 = (LPVOID *)(a1 + 24);
  v3 = (_DWORD *)(a1 + 16);
  if ( *(_QWORD *)(a1 + 24) )
  {
    v4 = 0;
    if ( *v3 )
    {
      do
      {
        v5 = *((_QWORD *)*v1 + v4);
        if ( v5 )
        {
          v6 = *(_QWORD *)(v5 + 40);
          if ( v6 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
            DbgOutputTrace("netDbCleanup: %ls ref=%x", *(const wchar_t **)(*((_QWORD *)*v1 + v4) + 24LL), v7);
          }
          v8 = *(void **)(*((_QWORD *)*v1 + v4) + 8LL);
          if ( v8 )
            CoTaskMemFree(v8);
          v9 = *(void **)(*((_QWORD *)*v1 + v4) + 16LL);
          if ( v9 )
            CoTaskMemFree(v9);
          v10 = *(void **)(*((_QWORD *)*v1 + v4) + 24LL);
          if ( v10 )
            CoTaskMemFree(v10);
          RassrvFree(*((LPVOID *)*v1 + v4));
        }
        v4 = (unsigned int)(v4 + 1);
      }
      while ( (unsigned int)v4 < *v3 );
      v11 = (_QWORD *)(a1 + 24);
    }
    else
    {
      v11 = (_QWORD *)(a1 + 24);
    }
    RassrvFree(*v1);
  }
  else
  {
    v11 = (_QWORD *)(a1 + 24);
  }
  *v3 = 0;
  result = 0;
  *v11 = 0;
  return result;
}

```

## disassembly

```asm
0x180028dc8  push    rbx
0x180028dca  push    rbp
0x180028dcb  push    rsi
0x180028dcc  push    rdi
0x180028dcd  push    r14
0x180028dcf  sub     rsp, 20h
0x180028dd3  lea     rbx, [rcx+18h]
0x180028dd7  mov     r14, rcx
0x180028dda  cmp     qword ptr [rbx], 0
0x180028dde  lea     rdi, [rcx+10h]
0x180028de2  jz      loc_180028E98
0x180028de8  xor     ebp, ebp
0x180028dea  cmp     [rdi], ebp
0x180028dec  jbe     loc_180028E8B
0x180028df2  mov     rax, [rbx]
0x180028df5  mov     rcx, [rax+rbp*8]
0x180028df9  test    rcx, rcx
0x180028dfc  jz      short loc_180028E7B
0x180028dfe  mov     rcx, [rcx+28h]
0x180028e02  test    rcx, rcx
0x180028e05  jz      short loc_180028E2D
0x180028e07  mov     rax, [rcx]
0x180028e0a  mov     rax, [rax+10h]
0x180028e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e13  mov     rcx, [rbx]
0x180028e16  mov     r8d, eax
0x180028e19  mov     rdx, [rcx+rbp*8]
0x180028e1d  lea     rcx, aNetdbcleanupLs; "netDbCleanup: %ls ref=%x"
0x180028e24  mov     rdx, [rdx+18h]
0x180028e28  call    DbgOutputTrace
0x180028e2d  mov     rax, [rbx]
0x180028e30  mov     rcx, [rax+rbp*8]
0x180028e34  mov     rcx, [rcx+8]; pv
0x180028e38  test    rcx, rcx
0x180028e3b  jz      short loc_180028E43
0x180028e3d  call    cs:__imp_CoTaskMemFree
0x180028e43  mov     rax, [rbx]
0x180028e46  mov     rcx, [rax+rbp*8]
0x180028e4a  mov     rcx, [rcx+10h]; pv
0x180028e4e  test    rcx, rcx
0x180028e51  jz      short loc_180028E59
0x180028e53  call    cs:__imp_CoTaskMemFree
0x180028e59  mov     rax, [rbx]
0x180028e5c  mov     rcx, [rax+rbp*8]
0x180028e60  mov     rcx, [rcx+18h]; pv
0x180028e64  test    rcx, rcx
0x180028e67  jz      short loc_180028E6F
0x180028e69  call    cs:__imp_CoTaskMemFree
0x180028e6f  mov     rcx, [rbx]
0x180028e72  mov     rcx, [rcx+rbp*8]; lpMem
0x180028e76  call    RassrvFree
0x180028e7b  inc     ebp
0x180028e7d  cmp     ebp, [rdi]
0x180028e7f  jb      loc_180028DF2
0x180028e85  lea     rsi, [r14+18h]
0x180028e89  jmp     short loc_180028E8E
0x180028e8b  mov     rsi, rbx
0x180028e8e  mov     rcx, [rbx]; lpMem
0x180028e91  call    RassrvFree
0x180028e96  jmp     short loc_180028E9B
0x180028e98  mov     rsi, rbx
0x180028e9b  mov     dword ptr [rdi], 0
0x180028ea1  xor     eax, eax
0x180028ea3  mov     qword ptr [rsi], 0
0x180028eaa  add     rsp, 20h
0x180028eae  pop     r14
0x180028eb0  pop     rdi
0x180028eb1  pop     rsi
0x180028eb2  pop     rbp
0x180028eb3  pop     rbx
0x180028eb4  retn
```
