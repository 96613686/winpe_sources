# clnttcp_destroy

- ea: `0x18002f0a0`
- end: `0x18002f122`
- name: `clnttcp_destroy`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002f0a0`
- `0x180037010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18002f0b9`
- `KERNEL32!EnterCriticalSection` at `0x18002f0b9`
- `KERNEL32!LeaveCriticalSection` at `0x18002f0fa`
- `KERNEL32!LeaveCriticalSection` at `0x18002f0fa`
- `KERNEL32!DeleteCriticalSection` at `0x18002f103`
- `KERNEL32!DeleteCriticalSection` at `0x18002f103`
- `KERNEL32!GlobalFree` at `0x18002f0f1`
- `KERNEL32!GlobalFree` at `0x18002f0f1`
- `KERNEL32!GlobalFree` at `0x18002f11b`
- `WS2_32!__imp_closesocket` at `0x18002f0cc`
- `WS2_32!__imp_closesocket` at `0x18002f0cc`

## pseudocode

```c
HGLOBAL __fastcall clnttcp_destroy(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  SOCKET *v3; // rbx
  void (__fastcall *v4)(SOCKET *); // rax

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  v3 = *(SOCKET **)(a1 + 16);
  if ( *v3 != -1 )
    closesocket(*v3);
  v4 = *(void (__fastcall **)(SOCKET *))(v3[26] + 56);
  if ( v4 )
    v4(v3 + 25);
  GlobalFree(v3);
  LeaveCriticalSection(v1);
  DeleteCriticalSection(v1);
  return GlobalFree((HGLOBAL)a1);
}

```

## disassembly

```asm
0x18002f0a0  mov     [rsp+arg_0], rbx
0x18002f0a5  mov     [rsp+arg_8], rsi
0x18002f0aa  push    rdi
0x18002f0ab  sub     rsp, 20h
0x18002f0af  lea     rsi, [rcx+18h]
0x18002f0b3  mov     rdi, rcx
0x18002f0b6  mov     rcx, rsi; lpCriticalSection
0x18002f0b9  call    cs:__imp_EnterCriticalSection
0x18002f0bf  mov     rbx, [rdi+10h]
0x18002f0c3  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18002f0c7  jz      short loc_18002F0D2
0x18002f0c9  mov     rcx, [rbx]; s
0x18002f0cc  call    cs:__imp_closesocket
0x18002f0d2  mov     rax, [rbx+0D0h]
0x18002f0d9  mov     rax, [rax+38h]
0x18002f0dd  test    rax, rax
0x18002f0e0  jz      short loc_18002F0EE
0x18002f0e2  lea     rcx, [rbx+0C8h]
0x18002f0e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0ee  mov     rcx, rbx; hMem
0x18002f0f1  call    cs:__imp_GlobalFree
0x18002f0f7  mov     rcx, rsi; lpCriticalSection
0x18002f0fa  call    cs:__imp_LeaveCriticalSection
0x18002f100  mov     rcx, rsi; lpCriticalSection
0x18002f103  call    cs:__imp_DeleteCriticalSection
0x18002f109  mov     rcx, rdi
0x18002f10c  mov     rbx, [rsp+28h+arg_0]
0x18002f111  mov     rsi, [rsp+28h+arg_8]
0x18002f116  add     rsp, 20h
0x18002f11a  pop     rdi
0x18002f11b  jmp     cs:__imp_GlobalFree
```
