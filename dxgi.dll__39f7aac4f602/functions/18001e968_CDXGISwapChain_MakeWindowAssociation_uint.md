# CDXGISwapChain::MakeWindowAssociation(uint)

- ea: `0x18001e968`
- end: `0x18001ea41`
- name: `?MakeWindowAssociation@CDXGISwapChain@@QEAAXI@Z`
- size: `217`
- prototype: `void __fastcall(CDXGISwapChain *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18001d9b0`
- `0x18002bd04`
- `0x18004794c`

## callees

- `0x18001e968`
- `0x18001ea48`
- `0x1800cb010`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18001e9cc`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18001e9cc`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowsHookExW` at `0x18001e9e3`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowsHookExW` at `0x18001e9e3`
- `ext-ms-win-ntuser-window-l1-1-0!UnhookWindowsHookEx` at `0x18001ea2d`
- `ext-ms-win-ntuser-window-l1-1-0!UnhookWindowsHookEx` at `0x18001ea2d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CDXGISwapChain::MakeWindowAssociation(CDXGISwapChain *this, int a2)
{
  unsigned __int64 v4; // rdi
  __int64 v5; // rax
  DWORD WindowThreadProcessId; // eax

  if ( *((_DWORD *)this + 82) == 2 )
  {
    v4 = ((unsigned __int64)this + 136) & -(__int64)(this != 0);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v4 + 8) + 24LL))(*(_QWORD *)(v4 + 8));
    v5 = *((_QWORD *)this + 57);
    if ( (a2 & 1) != 0 )
    {
      if ( v5 )
      {
        UnhookWindowsHookEx(*((HHOOK *)this + 57));
        *((_QWORD *)this + 57) = 0;
      }
    }
    else if ( !v5 )
    {
      WindowThreadProcessId = GetWindowThreadProcessId(*((HWND *)this + 42), 0);
      *((_QWORD *)this + 57) = SetWindowsHookExW(3, SwapChainWindowEventHook, 0, WindowThreadProcessId);
    }
    *((_DWORD *)this + 116) = a2;
    CDXGISwapChain::UpdatePrintScreenHandling(this);
    if ( v4 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v4 + 8) + 32LL))(*(_QWORD *)(v4 + 8));
  }
}

```

## disassembly

```asm
0x18001e968  mov     [rsp+arg_8], rbx
0x18001e96d  mov     [rsp+arg_10], rsi
0x18001e972  push    rdi
0x18001e973  sub     rsp, 20h
0x18001e977  mov     esi, edx
0x18001e979  mov     rbx, rcx
0x18001e97c  cmp     dword ptr [rcx+148h], 2
0x18001e983  jnz     loc_18001EA15
0x18001e989  mov     rax, rcx
0x18001e98c  lea     r8, [rcx+88h]
0x18001e993  neg     rax
0x18001e996  sbb     rdi, rdi
0x18001e999  and     rdi, r8
0x18001e99c  mov     rcx, [rdi+8]
0x18001e9a0  mov     rax, [rcx]
0x18001e9a3  mov     rax, [rax+18h]
0x18001e9a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9ac  mov     [rsp+28h+arg_0], rdi
0x18001e9b1  mov     rax, [rbx+1C8h]
0x18001e9b8  test    sil, 1
0x18001e9bc  jnz     short loc_18001EA25
0x18001e9be  test    rax, rax
0x18001e9c1  jnz     short loc_18001E9F0
0x18001e9c3  xor     edx, edx; lpdwProcessId
0x18001e9c5  mov     rcx, [rbx+150h]; hWnd
0x18001e9cc  call    cs:__imp_GetWindowThreadProcessId
0x18001e9d2  mov     r9d, eax; dwThreadId
0x18001e9d5  xor     r8d, r8d; hmod
0x18001e9d8  lea     rdx, ?SwapChainWindowEventHook@@YA_JH_K_J@Z; lpfn
0x18001e9df  lea     ecx, [r8+3]; idHook
0x18001e9e3  call    cs:__imp_SetWindowsHookExW
0x18001e9e9  mov     [rbx+1C8h], rax
0x18001e9f0  mov     [rbx+1D0h], esi
0x18001e9f6  mov     rcx, rbx; this
0x18001e9f9  call    ?UpdatePrintScreenHandling@CDXGISwapChain@@IEAAXXZ; CDXGISwapChain::UpdatePrintScreenHandling(void)
0x18001e9fe  nop
0x18001e9ff  test    rdi, rdi
0x18001ea02  jz      short loc_18001EA15
0x18001ea04  mov     rcx, [rdi+8]
0x18001ea08  mov     rax, [rcx]
0x18001ea0b  mov     rax, [rax+20h]
0x18001ea0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea14  nop
0x18001ea15  mov     rbx, [rsp+28h+arg_8]
0x18001ea1a  mov     rsi, [rsp+28h+arg_10]
0x18001ea1f  add     rsp, 20h
0x18001ea23  pop     rdi
0x18001ea24  retn
0x18001ea25  test    rax, rax
0x18001ea28  jz      short loc_18001E9F0
0x18001ea2a  mov     rcx, rax; hhk
0x18001ea2d  call    cs:__imp_UnhookWindowsHookEx
0x18001ea33  mov     qword ptr [rbx+1C8h], 0
0x18001ea3e  jmp     short loc_18001E9F0
```
