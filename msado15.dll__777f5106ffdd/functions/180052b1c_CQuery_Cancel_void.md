# CQuery::Cancel(void)

- ea: `0x180052b1c`
- end: `0x180052bef`
- name: `?Cancel@CQuery@@QEAAJXZ`
- size: `211`
- prototype: `__int64 __fastcall(CQuery *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180050c20`
- `0x18005c5f0`

## callees

- `0x180052b1c`
- `0x1800cb374`
- `0x1800d0010`

## import_xrefs

- `KERNEL32!Sleep` at `0x180052baf`
- `KERNEL32!Sleep` at `0x180052baf`
- `KERNEL32!CloseHandle` at `0x180052bde`
- `KERNEL32!CloseHandle` at `0x180052bde`
- `KERNEL32!GetCurrentThreadId` at `0x180052b82`
- `KERNEL32!GetCurrentThreadId` at `0x180052bc3`
- `KERNEL32!GetCurrentThreadId` at `0x180052b82`
- `KERNEL32!GetCurrentThreadId` at `0x180052bc3`

## pseudocode

```c
__int64 __fastcall CQuery::Cancel(CQuery *this)
{
  __int64 v2; // rcx
  __int64 v3; // rdi
  void *v4; // rdi
  int v6; // ebx

  v2 = *((_QWORD *)this + 10);
  if ( v2 )
  {
    v3 = *((_QWORD *)this + 17);
    if ( *((_BYTE *)this + 232) )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 24LL))(v2);
    if ( v3 )
    {
      while ( *(_BYTE *)(v3 + 544) == 1
           && (!*((_QWORD *)this + 20) || *((_DWORD *)this + 42) != GetCurrentThreadId())
           && (*(int (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 24LL))(*((_QWORD *)this + 10)) >= 0 )
        Sleep(1u);
    }
  }
  v4 = (void *)_InterlockedExchange64((volatile __int64 *)this + 20, 0);
  if ( v4 )
  {
    v6 = *((_DWORD *)this + 42);
    if ( v6 != GetCurrentThreadId() )
      WaitForMultipleObjectsWithMessageLoop(v4);
    CloseHandle(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x180052b1c  mov     [rsp+arg_0], rbx
0x180052b21  push    rdi
0x180052b22  sub     rsp, 20h
0x180052b26  mov     rbx, rcx
0x180052b29  mov     rcx, [rcx+50h]
0x180052b2d  test    rcx, rcx
0x180052b30  jz      short loc_180052B53
0x180052b32  cmp     byte ptr [rbx+0E8h], 0
0x180052b39  mov     rdi, [rbx+88h]
0x180052b40  jz      short loc_180052B4E
0x180052b42  mov     rax, [rcx]
0x180052b45  mov     rax, [rax+18h]
0x180052b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052b4e  test    rdi, rdi
0x180052b51  jnz     short loc_180052B6F
0x180052b53  xor     edi, edi
0x180052b55  xchg    rdi, [rbx+0A0h]
0x180052b5c  test    rdi, rdi
0x180052b5f  jnz     short loc_180052BBD
0x180052b61  mov     rbx, [rsp+28h+arg_0]
0x180052b66  xor     eax, eax
0x180052b68  add     rsp, 20h
0x180052b6c  pop     rdi
0x180052b6d  retn
0x180052b6f  cmp     byte ptr [rdi+220h], 1
0x180052b76  jnz     short loc_180052B53
0x180052b78  cmp     qword ptr [rbx+0A0h], 0
0x180052b80  jz      short loc_180052B96
0x180052b82  call    cs:__imp_GetCurrentThreadId
0x180052b89  nop     dword ptr [rax+rax+00h]
0x180052b8e  cmp     [rbx+0A8h], eax
0x180052b94  jz      short loc_180052B53
0x180052b96  mov     rcx, [rbx+50h]
0x180052b9a  mov     rax, [rcx]
0x180052b9d  mov     rax, [rax+18h]
0x180052ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ba6  test    eax, eax
0x180052ba8  js      short loc_180052B53
0x180052baa  mov     ecx, 1; dwMilliseconds
0x180052baf  call    cs:__imp_Sleep
0x180052bb6  nop     dword ptr [rax+rax+00h]
0x180052bbb  jmp     short loc_180052B6F
0x180052bbd  mov     ebx, [rbx+0A8h]
0x180052bc3  call    cs:__imp_GetCurrentThreadId
0x180052bca  nop     dword ptr [rax+rax+00h]
0x180052bcf  cmp     ebx, eax
0x180052bd1  jz      short loc_180052BDB
0x180052bd3  mov     rcx, rdi; void *
0x180052bd6  call    ?WaitForMultipleObjectsWithMessageLoop@@YAHPEAX@Z; WaitForMultipleObjectsWithMessageLoop(void *)
0x180052bdb  mov     rcx, rdi; hObject
0x180052bde  call    cs:__imp_CloseHandle
0x180052be5  nop     dword ptr [rax+rax+00h]
0x180052bea  jmp     loc_180052B61
```
