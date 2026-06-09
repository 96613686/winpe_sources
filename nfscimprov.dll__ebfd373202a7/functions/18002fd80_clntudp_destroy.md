# clntudp_destroy

- ea: `0x18002fd80`
- end: `0x18002fe02`
- name: `clntudp_destroy`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002fd80`
- `0x180037010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18002fd99`
- `KERNEL32!EnterCriticalSection` at `0x18002fd99`
- `KERNEL32!LeaveCriticalSection` at `0x18002fdda`
- `KERNEL32!LeaveCriticalSection` at `0x18002fdda`
- `KERNEL32!DeleteCriticalSection` at `0x18002fde3`
- `KERNEL32!DeleteCriticalSection` at `0x18002fde3`
- `KERNEL32!GlobalFree` at `0x18002fdd1`
- `KERNEL32!GlobalFree` at `0x18002fdd1`
- `KERNEL32!GlobalFree` at `0x18002fdfb`
- `WS2_32!__imp_closesocket` at `0x18002fdac`
- `WS2_32!__imp_closesocket` at `0x18002fdac`

## pseudocode

```c
HGLOBAL __fastcall clntudp_destroy(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  SOCKET *v3; // rbx
  void (__fastcall *v4)(SOCKET *); // rax

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  v3 = *(SOCKET **)(a1 + 16);
  if ( *v3 != -1 )
    closesocket(*v3);
  v4 = *(void (__fastcall **)(SOCKET *))(v3[23] + 56);
  if ( v4 )
    v4(v3 + 22);
  GlobalFree(v3);
  LeaveCriticalSection(v1);
  DeleteCriticalSection(v1);
  return GlobalFree((HGLOBAL)a1);
}

```

## disassembly

```asm
0x18002fd80  mov     [rsp+arg_0], rbx
0x18002fd85  mov     [rsp+arg_8], rsi
0x18002fd8a  push    rdi
0x18002fd8b  sub     rsp, 20h
0x18002fd8f  lea     rsi, [rcx+18h]
0x18002fd93  mov     rdi, rcx
0x18002fd96  mov     rcx, rsi; lpCriticalSection
0x18002fd99  call    cs:__imp_EnterCriticalSection
0x18002fd9f  mov     rbx, [rdi+10h]
0x18002fda3  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18002fda7  jz      short loc_18002FDB2
0x18002fda9  mov     rcx, [rbx]; s
0x18002fdac  call    cs:__imp_closesocket
0x18002fdb2  mov     rax, [rbx+0B8h]
0x18002fdb9  mov     rax, [rax+38h]
0x18002fdbd  test    rax, rax
0x18002fdc0  jz      short loc_18002FDCE
0x18002fdc2  lea     rcx, [rbx+0B0h]
0x18002fdc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fdce  mov     rcx, rbx; hMem
0x18002fdd1  call    cs:__imp_GlobalFree
0x18002fdd7  mov     rcx, rsi; lpCriticalSection
0x18002fdda  call    cs:__imp_LeaveCriticalSection
0x18002fde0  mov     rcx, rsi; lpCriticalSection
0x18002fde3  call    cs:__imp_DeleteCriticalSection
0x18002fde9  mov     rcx, rdi
0x18002fdec  mov     rbx, [rsp+28h+arg_0]
0x18002fdf1  mov     rsi, [rsp+28h+arg_8]
0x18002fdf6  add     rsp, 20h
0x18002fdfa  pop     rdi
0x18002fdfb  jmp     cs:__imp_GlobalFree
```
