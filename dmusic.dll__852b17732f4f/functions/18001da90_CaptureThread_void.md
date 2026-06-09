# CaptureThread(void *)

- ea: `0x18001da90`
- end: `0x18001daa0`
- name: `?CaptureThread@@YAKPEAX@Z`
- size: `16`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001daa8`

## pseudocode

```c
__int64 __fastcall CaptureThread(CDirectMusicUMAPort *lpThreadParameter)
{
  CDirectMusicUMAPort::CaptureThread(lpThreadParameter);
  return 0;
}

```

## disassembly

```asm
0x18001da90  sub     rsp, 28h
0x18001da94  call    ?CaptureThread@CDirectMusicUMAPort@@AEAAXXZ; CDirectMusicUMAPort::CaptureThread(void)
0x18001da99  xor     eax, eax
0x18001da9b  add     rsp, 28h
0x18001da9f  retn
```
