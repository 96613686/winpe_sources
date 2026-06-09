# FreeWDMHandle(void *)

- ea: `0x18001ed80`
- end: `0x18001ed90`
- name: `?FreeWDMHandle@@YAKPEAX@Z`
- size: `16`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001ed98`

## pseudocode

```c
__int64 __fastcall FreeWDMHandle(CDirectMusicUMAPort *lpThreadParameter)
{
  CDirectMusicUMAPort::FreeWDMHandle(lpThreadParameter);
  return 0;
}

```

## disassembly

```asm
0x18001ed80  sub     rsp, 28h
0x18001ed84  call    ?FreeWDMHandle@CDirectMusicUMAPort@@AEAAXXZ; CDirectMusicUMAPort::FreeWDMHandle(void)
0x18001ed89  xor     eax, eax
0x18001ed8b  add     rsp, 28h
0x18001ed8f  retn
```
