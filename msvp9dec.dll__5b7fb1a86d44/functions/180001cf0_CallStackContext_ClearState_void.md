# CallStackContext::ClearState(void)

- ea: `0x180001cf0`
- end: `0x180001d34`
- name: `?ClearState@CallStackContext@@QEAAXXZ`
- size: `68`
- prototype: `void __fastcall(CallStackContext *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001b50`
- `0x180001c60`
- `0x180002580`
- `0x180004e90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001d22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001d22`

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
0x180001cf0  push    rbx
0x180001cf2  sub     rsp, 20h
0x180001cf6  xor     eax, eax
0x180001cf8  mov     rbx, rcx
0x180001cfb  mov     [rcx+7C4h], eax
0x180001d01  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180001d08  mov     [rcx+7E0h], rax
0x180001d0f  mov     [rcx+7CCh], eax
0x180001d15  movups  xmmword ptr [rcx+7D0h], xmm0
0x180001d1c  mov     [rcx+7E8h], eax
0x180001d22  call    cs:__imp_GetCurrentThreadId
0x180001d28  mov     [rbx+7C0h], eax
0x180001d2e  add     rsp, 20h
0x180001d32  pop     rbx
0x180001d33  retn
```
