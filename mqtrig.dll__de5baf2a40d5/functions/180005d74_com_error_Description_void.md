# _com_error::Description(void)

- ea: `0x180005d74`
- end: `0x180005dee`
- name: `?Description@_com_error@@QEBA?AV_bstr_t@@XZ`
- size: `122`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001f159`

## callees

- `0x180005d74`
- `0x180014920`
- `0x180014ae8`
- `0x180022010`

## pseudocode

```c
_QWORD *__fastcall _com_error::Description(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rdi
  __int64 v4; // rcx
  _QWORD *v5; // rax
  struct IErrorInfo *v6; // rdx
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  _QWORD *v9; // [rsp+50h] [rbp+18h]

  v3 = 0;
  v8 = 0;
  v4 = *(_QWORD *)(a1 + 16);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 40LL))(v4, &v8);
    v3 = v8;
  }
  v5 = MmAllocate(0x18u);
  v9 = v5;
  if ( v5 )
  {
    v5[1] = 0;
    *((_DWORD *)v5 + 4) = 1;
    *v5 = v3;
  }
  *a2 = v5;
  if ( !v5 )
    _com_issue_error(-2147024882, v6);
  return a2;
}

```

## disassembly

```asm
0x180005d74  mov     [rsp+arg_8], rbx
0x180005d79  push    rdi
0x180005d7a  sub     rsp, 30h
0x180005d7e  mov     rbx, rdx
0x180005d81  xor     edi, edi
0x180005d83  mov     [rsp+38h+arg_0], rdi
0x180005d88  mov     rcx, [rcx+10h]
0x180005d8c  test    rcx, rcx
0x180005d8f  jz      short loc_180005DA7
0x180005d91  mov     rax, [rcx]
0x180005d94  lea     rdx, [rsp+38h+arg_0]
0x180005d99  mov     rax, [rax+28h]
0x180005d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005da2  mov     rdi, [rsp+38h+arg_0]
0x180005da7  mov     ecx, 18h; unsigned __int64
0x180005dac  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180005db1  mov     [rsp+38h+arg_10], rax
0x180005db6  test    rax, rax
0x180005db9  jz      short loc_180005DCD
0x180005dbb  mov     qword ptr [rax+8], 0
0x180005dc3  mov     dword ptr [rax+10h], 1
0x180005dca  mov     [rax], rdi
0x180005dcd  mov     [rbx], rax
0x180005dd0  test    rax, rax
0x180005dd3  jnz     short loc_180005DE0
0x180005dd5  mov     ecx, 8007000Eh; int
0x180005dda  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180005de0  mov     rax, rbx
0x180005de3  mov     rbx, [rsp+38h+arg_8]
0x180005de8  add     rsp, 30h
0x180005dec  pop     rdi
0x180005ded  retn
```
