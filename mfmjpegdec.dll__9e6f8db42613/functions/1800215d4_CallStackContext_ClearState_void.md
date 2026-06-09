# CallStackContext::ClearState(void)

- ea: `0x1800215d4`
- end: `0x180021619`
- name: `?ClearState@CallStackContext@@QEAAXXZ`
- size: `69`
- prototype: `void __fastcall(CallStackContext *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180021584`
- `0x180056638`
- `0x18006e358`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021607`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021607`

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
0x1800215d4  push    rbx
0x1800215d6  sub     rsp, 20h
0x1800215da  xor     eax, eax
0x1800215dc  mov     rbx, rcx
0x1800215df  mov     [rcx+7C4h], eax
0x1800215e5  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800215ec  mov     [rcx+7E0h], rax
0x1800215f3  mov     [rcx+7CCh], eax
0x1800215f9  movdqu  xmmword ptr [rcx+7D0h], xmm0
0x180021601  mov     [rcx+7E8h], eax
0x180021607  call    cs:__imp_GetCurrentThreadId
0x18002160d  mov     [rbx+7C0h], eax
0x180021613  add     rsp, 20h
0x180021617  pop     rbx
0x180021618  retn
```
