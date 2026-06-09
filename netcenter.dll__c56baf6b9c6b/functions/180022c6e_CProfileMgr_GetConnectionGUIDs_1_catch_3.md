# _CProfileMgr::GetConnectionGUIDs_::_1_::catch$3

- ea: `0x180022c6e`
- end: `0x180022cb7`
- name: `_CProfileMgr::GetConnectionGUIDs_::_1_::catch$3`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180022c6e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022c95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022c95`

## pseudocode

```c
__int64 __fastcall CProfileMgr::GetConnectionGUIDs_::_1_::catch_3(__int64 a1, __int64 a2)
{
  unsigned int i; // ebx

  *(_DWORD *)(a2 + 48) = -2147024882;
  for ( i = *(_DWORD *)(a2 + 152); i < *(_DWORD *)(a2 + 136); ++i )
    CoTaskMemFree(*(LPVOID *)(*(_QWORD *)(a2 + 56) + 8LL * i));
  return 0;
}

```

## disassembly

```asm
0x180022c6e  mov     [rsp+arg_8], rdx
0x180022c73  push    rbx
0x180022c74  push    rbp
0x180022c75  sub     rsp, 38h
0x180022c79  mov     rbp, rdx
0x180022c7c  mov     dword ptr [rbp+30h], 8007000Eh
0x180022c83  mov     ebx, [rbp+98h]
0x180022c89  jmp     short loc_180022C9D
0x180022c8b  mov     eax, ebx
0x180022c8d  mov     rcx, [rbp+38h]
0x180022c91  mov     rcx, [rcx+rax*8]; pv
0x180022c95  call    cs:__imp_CoTaskMemFree
0x180022c9b  inc     ebx
0x180022c9d  cmp     ebx, [rbp+88h]
0x180022ca3  jb      short loc_180022C8B
0x180022ca5  mov     rax, 0
0x180022caf  add     rsp, 38h
0x180022cb3  pop     rbp
0x180022cb4  pop     rbx
0x180022cb5  retn
```
