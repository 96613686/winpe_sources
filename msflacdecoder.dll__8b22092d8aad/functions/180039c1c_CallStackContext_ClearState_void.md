# CallStackContext::ClearState(void)

- ea: `0x180039c1c`
- end: `0x180039c61`
- name: `?ClearState@CallStackContext@@QEAAXXZ`
- size: `69`
- prototype: `void __fastcall(CallStackContext *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18002fff0`
- `0x180039dc8`
- `0x18003a784`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039c4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039c4f`

## pseudocode

```c
void __fastcall CallStackContext::ClearState(GUID *this)
{
  *(_DWORD *)&this[124].Data2 = 0;
  *(_QWORD *)&this[126].Data1 = 0;
  *(_DWORD *)&this[124].Data4[4] = 0;
  this[125] = GUID_00000000_0000_0000_0000_000000000000;
  *(_DWORD *)this[126].Data4 = 0;
  this[124].Data1 = GetCurrentThreadId();
}

```

## disassembly

```asm
0x180039c1c  push    rbx
0x180039c1e  sub     rsp, 20h
0x180039c22  xor     eax, eax
0x180039c24  mov     rbx, rcx
0x180039c27  mov     [rcx+7C4h], eax
0x180039c2d  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180039c34  mov     [rcx+7E0h], rax
0x180039c3b  mov     [rcx+7CCh], eax
0x180039c41  movdqu  xmmword ptr [rcx+7D0h], xmm0
0x180039c49  mov     [rcx+7E8h], eax
0x180039c4f  call    cs:__imp_GetCurrentThreadId
0x180039c55  mov     [rbx+7C0h], eax
0x180039c5b  add     rsp, 20h
0x180039c5f  pop     rbx
0x180039c60  retn
```
