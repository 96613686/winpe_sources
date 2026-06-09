# netDbCleanup

- ea: `0x180036ec8`
- end: `0x180036fb5`
- name: `netDbCleanup`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180036fbc`
- `0x180037a14`

## callees

- `0x180033a84`
- `0x1800348f0`
- `0x180036ec8`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036f3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036f53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036f69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036f3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036f53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036f69`

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
0x180036ec8  push    rbx
0x180036eca  push    rbp
0x180036ecb  push    rsi
0x180036ecc  push    rdi
0x180036ecd  push    r14
0x180036ecf  sub     rsp, 20h
0x180036ed3  lea     rbx, [rcx+18h]
0x180036ed7  mov     r14, rcx
0x180036eda  cmp     qword ptr [rbx], 0
0x180036ede  lea     rdi, [rcx+10h]
0x180036ee2  jz      loc_180036F98
0x180036ee8  xor     ebp, ebp
0x180036eea  cmp     [rdi], ebp
0x180036eec  jbe     loc_180036F8B
0x180036ef2  mov     rax, [rbx]
0x180036ef5  mov     rcx, [rax+rbp*8]
0x180036ef9  test    rcx, rcx
0x180036efc  jz      short loc_180036F7B
0x180036efe  mov     rcx, [rcx+28h]
0x180036f02  test    rcx, rcx
0x180036f05  jz      short loc_180036F2D
0x180036f07  mov     rax, [rcx]
0x180036f0a  mov     rax, [rax+10h]
0x180036f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f13  mov     rcx, [rbx]
0x180036f16  mov     r8d, eax
0x180036f19  mov     rdx, [rcx+rbp*8]
0x180036f1d  lea     rcx, aNetdbcleanupLs; "netDbCleanup: %ls ref=%x"
0x180036f24  mov     rdx, [rdx+18h]
0x180036f28  call    DbgOutputTrace
0x180036f2d  mov     rax, [rbx]
0x180036f30  mov     rcx, [rax+rbp*8]
0x180036f34  mov     rcx, [rcx+8]; pv
0x180036f38  test    rcx, rcx
0x180036f3b  jz      short loc_180036F43
0x180036f3d  call    cs:__imp_CoTaskMemFree
0x180036f43  mov     rax, [rbx]
0x180036f46  mov     rcx, [rax+rbp*8]
0x180036f4a  mov     rcx, [rcx+10h]; pv
0x180036f4e  test    rcx, rcx
0x180036f51  jz      short loc_180036F59
0x180036f53  call    cs:__imp_CoTaskMemFree
0x180036f59  mov     rax, [rbx]
0x180036f5c  mov     rcx, [rax+rbp*8]
0x180036f60  mov     rcx, [rcx+18h]; pv
0x180036f64  test    rcx, rcx
0x180036f67  jz      short loc_180036F6F
0x180036f69  call    cs:__imp_CoTaskMemFree
0x180036f6f  mov     rcx, [rbx]
0x180036f72  mov     rcx, [rcx+rbp*8]; lpMem
0x180036f76  call    RassrvFree
0x180036f7b  inc     ebp
0x180036f7d  cmp     ebp, [rdi]
0x180036f7f  jb      loc_180036EF2
0x180036f85  lea     rsi, [r14+18h]
0x180036f89  jmp     short loc_180036F8E
0x180036f8b  mov     rsi, rbx
0x180036f8e  mov     rcx, [rbx]; lpMem
0x180036f91  call    RassrvFree
0x180036f96  jmp     short loc_180036F9B
0x180036f98  mov     rsi, rbx
0x180036f9b  mov     dword ptr [rdi], 0
0x180036fa1  xor     eax, eax
0x180036fa3  mov     qword ptr [rsi], 0
0x180036faa  add     rsp, 20h
0x180036fae  pop     r14
0x180036fb0  pop     rdi
0x180036fb1  pop     rsi
0x180036fb2  pop     rbp
0x180036fb3  pop     rbx
0x180036fb4  retn
```
