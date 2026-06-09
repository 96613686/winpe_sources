# CTimer::ThreadCallback(void *)

- ea: `0x140009770`
- end: `0x140009775`
- name: `?ThreadCallback@CTimer@@KAKPEAX@Z`
- size: `5`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140008064`

## pseudocode

```c
// attributes: thunk
DWORD __fastcall CTimer::ThreadCallback(CTimer *lpThreadParameter)
{
  return CTimer::RunTimer(lpThreadParameter);
}

```

## disassembly

```asm
0x140009770  jmp     ?RunTimer@CTimer@@IEAAKXZ; CTimer::RunTimer(void)
```
