# DfsThreadpoolWrapper::SubmitWork(_TP_CALLBACK_ENVIRON_V3 *,void *,ulong (*)(void *),ulong (*)(void *))

- ea: `0x14003b7b4`
- end: `0x14003b854`
- name: `?SubmitWork@DfsThreadpoolWrapper@@QEAAKPEAU_TP_CALLBACK_ENVIRON_V3@@PEAXP6AK1@Z2@Z`
- size: `160`
- prototype: `unsigned int(DfsThreadpoolWrapper *__hidden this, struct _TP_CALLBACK_ENVIRON_V3 *, void *, unsigned int (*)(void *), unsigned int (*)(void *))`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000a6cc`
- `0x140021460`
- `0x1400448ec`

## callees

- `0x1400011d0`
- `0x140007880`
- `0x14003b7b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b81c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b81c`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x14003b808`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x14003b808`

## pseudocode

```c
__int64 __fastcall DfsThreadpoolWrapper::SubmitWork(
        DfsThreadpoolWrapper *this,
        struct _TP_CALLBACK_ENVIRON_V3 *a2,
        void *a3,
        unsigned int (*a4)(void *))
{
  struct _DFS_THREADPOOL_CALLBACK_CONTEXT *v6; // rax
  struct _DFS_THREADPOOL_CALLBACK_CONTEXT *v7; // rbx
  struct _DFS_THREADPOOL_CALLBACK_CONTEXT *v8; // rsi
  DWORD LastError; // edi

  v6 = (struct _DFS_THREADPOOL_CALLBACK_CONTEXT *)operator new(0x18u);
  v7 = 0;
  v8 = v6;
  if ( v6 )
  {
    *(_QWORD *)v6 = a3;
    *((_QWORD *)v6 + 1) = DfsUpdateLinkSimpleCallback;
    *((_QWORD *)v6 + 2) = DfsUpdateLinkSimpleCancellationCallback;
    if ( TrySubmitThreadpoolCallback(DfsThreadpoolSimpleWorkCallback, v6, a2) )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      v7 = v8;
    }
    DfsThreadpoolDeleteCallbackContext(v7);
  }
  else
  {
    return 14;
  }
  return LastError;
}

```

## disassembly

```asm
0x14003b7b4  mov     [rsp+arg_0], rbx
0x14003b7b9  mov     [rsp+arg_8], rbp
0x14003b7be  mov     [rsp+arg_10], rsi
0x14003b7c3  push    rdi
0x14003b7c4  sub     rsp, 20h
0x14003b7c8  mov     ecx, 18h; Size
0x14003b7cd  mov     rdi, r8
0x14003b7d0  mov     rbp, rdx
0x14003b7d3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003b7d8  xor     ebx, ebx
0x14003b7da  mov     rsi, rax
0x14003b7dd  test    rax, rax
0x14003b7e0  jz      short loc_14003B837
0x14003b7e2  mov     [rax], rdi
0x14003b7e5  lea     rcx, ?DfsThreadpoolSimpleWorkCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x14003b7ec  lea     rax, ?DfsUpdateLinkSimpleCallback@@YAKPEAX@Z; DfsUpdateLinkSimpleCallback(void *)
0x14003b7f3  mov     r8, rbp; pcbe
0x14003b7f6  mov     [rsi+8], rax
0x14003b7fa  mov     rdx, rsi; pv
0x14003b7fd  lea     rax, ?DfsUpdateLinkSimpleCancellationCallback@@YAKPEAX@Z; DfsUpdateLinkSimpleCancellationCallback(void *)
0x14003b804  mov     [rsi+10h], rax
0x14003b808  call    cs:__imp_TrySubmitThreadpoolCallback
0x14003b80f  nop     dword ptr [rax+rax+00h]
0x14003b814  test    eax, eax
0x14003b816  jz      short loc_14003B81C
0x14003b818  mov     edi, ebx
0x14003b81a  jmp     short loc_14003B82D
0x14003b81c  call    cs:__imp_GetLastError
0x14003b823  nop     dword ptr [rax+rax+00h]
0x14003b828  mov     edi, eax
0x14003b82a  mov     rbx, rsi
0x14003b82d  mov     rcx, rbx; struct _DFS_THREADPOOL_CALLBACK_CONTEXT *
0x14003b830  call    ?DfsThreadpoolDeleteCallbackContext@@YAXPEAU_DFS_THREADPOOL_CALLBACK_CONTEXT@@@Z; DfsThreadpoolDeleteCallbackContext(_DFS_THREADPOOL_CALLBACK_CONTEXT *)
0x14003b835  jmp     short loc_14003B83C
0x14003b837  mov     edi, 0Eh
0x14003b83c  mov     rbx, [rsp+28h+arg_0]
0x14003b841  mov     eax, edi
0x14003b843  mov     rbp, [rsp+28h+arg_8]
0x14003b848  mov     rsi, [rsp+28h+arg_10]
0x14003b84d  add     rsp, 20h
0x14003b851  pop     rdi
0x14003b852  retn
```
