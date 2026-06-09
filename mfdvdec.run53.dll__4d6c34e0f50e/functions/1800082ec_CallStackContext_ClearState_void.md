# CallStackContext::ClearState(void)

- ea: `0x1800082ec`
- end: `0x180008331`
- name: `?ClearState@CallStackContext@@QEAAXXZ`
- size: `69`
- prototype: `void __fastcall(CallStackContext *__hidden this)`
- caller_count: `22`
- callee_count: `0`
- tags: ``

## callers

- `0x180002370`
- `0x180002540`
- `0x180002810`
- `0x180002ac0`
- `0x180003678`
- `0x1800039e0`
- `0x180003e30`
- `0x180004060`
- `0x1800041dc`
- `0x18000440c`
- `0x180004818`
- `0x180004c54`
- `0x180004fc0`
- `0x180005340`
- `0x1800057a0`
- `0x180005db0`
- `0x180005fbc`
- `0x180006b70`
- `0x180006fd4`
- `0x180007ef0`
- `0x18000854c`
- `0x180008ca0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000831f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000831f`

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
0x1800082ec  push    rbx
0x1800082ee  sub     rsp, 20h
0x1800082f2  xor     eax, eax
0x1800082f4  mov     rbx, rcx
0x1800082f7  mov     [rcx+7C4h], eax
0x1800082fd  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180008304  mov     [rcx+7E0h], rax
0x18000830b  mov     [rcx+7CCh], eax
0x180008311  movdqu  xmmword ptr [rcx+7D0h], xmm0
0x180008319  mov     [rcx+7E8h], eax
0x18000831f  call    cs:__imp_GetCurrentThreadId
0x180008325  mov     [rbx+7C0h], eax
0x18000832b  add     rsp, 20h
0x18000832f  pop     rbx
0x180008330  retn
```
