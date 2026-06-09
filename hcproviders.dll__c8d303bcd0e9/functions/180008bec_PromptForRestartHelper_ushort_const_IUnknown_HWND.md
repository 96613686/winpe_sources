# PromptForRestartHelper(ushort const *,IUnknown *,HWND__ *)

- ea: `0x180008bec`
- end: `0x180008c82`
- name: `?PromptForRestartHelper@@YAJPEBGPEAUIUnknown@@PEAUHWND__@@@Z`
- size: `150`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IUnknown *, HWND)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180008c90`
- `0x180008cb0`

## callees

- `0x180004a4c`
- `0x180004fbc`
- `0x180004fc8`
- `0x180008bec`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180008c27`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180008c27`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180008c3e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180008c3e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180008c4d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180008c4d`

## pseudocode

```c
__int64 __fastcall PromptForRestartHelper(const unsigned __int16 *a1, struct IUnknown *a2, HWND a3)
{
  _QWORD *v5; // rax
  void *v6; // rbx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v8; // rdi

  v5 = operator new(0x10u);
  v6 = v5;
  if ( !v5 )
    return 2147942414LL;
  *v5 = a3;
  v5[1] = a1;
  ThreadpoolWork = CreateThreadpoolWork(PromptForRestartCB, v5, 0);
  v8 = ThreadpoolWork;
  if ( ThreadpoolWork )
  {
    SubmitThreadpoolWork(ThreadpoolWork);
    CloseThreadpoolWork(v8);
    return 0;
  }
  else
  {
    operator delete(v6);
    return ResultFromKnownLastError();
  }
}

```

## disassembly

```asm
0x180008bec  mov     [rsp+arg_0], rbx
0x180008bf1  mov     [rsp+arg_8], rsi
0x180008bf6  push    rdi
0x180008bf7  sub     rsp, 20h
0x180008bfb  mov     rsi, rcx
0x180008bfe  mov     rdi, r8
0x180008c01  mov     ecx, 10h; Size
0x180008c06  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008c0b  mov     rbx, rax
0x180008c0e  test    rax, rax
0x180008c11  jz      short loc_180008C6C
0x180008c13  xor     r8d, r8d; pcbe
0x180008c16  mov     [rax], rdi
0x180008c19  mov     rdx, rax; pv
0x180008c1c  mov     [rax+8], rsi
0x180008c20  lea     rcx, ?PromptForRestartCB@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180008c27  call    cs:__imp_CreateThreadpoolWork
0x180008c2e  nop     dword ptr [rax+rax+00h]
0x180008c33  mov     rdi, rax
0x180008c36  test    rax, rax
0x180008c39  jz      short loc_180008C5D
0x180008c3b  mov     rcx, rax; pwk
0x180008c3e  call    cs:__imp_SubmitThreadpoolWork
0x180008c45  nop     dword ptr [rax+rax+00h]
0x180008c4a  mov     rcx, rdi; pwk
0x180008c4d  call    cs:__imp_CloseThreadpoolWork
0x180008c54  nop     dword ptr [rax+rax+00h]
0x180008c59  xor     eax, eax
0x180008c5b  jmp     short loc_180008C71
0x180008c5d  mov     rcx, rbx; Block
0x180008c60  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008c65  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180008c6a  jmp     short loc_180008C71
0x180008c6c  mov     eax, 8007000Eh
0x180008c71  mov     rbx, [rsp+28h+arg_0]
0x180008c76  mov     rsi, [rsp+28h+arg_8]
0x180008c7b  add     rsp, 20h
0x180008c7f  pop     rdi
0x180008c80  retn
```
