# KpsStartTimeoutTimer(_KPS_IO *)

- ea: `0x180022d38`
- end: `0x180022d7d`
- name: `?KpsStartTimeoutTimer@@YAXPEAU_KPS_IO@@@Z`
- size: `69`
- prototype: `void __fastcall(struct _KPS_IO *)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x18001e728`
- `0x18001e8e8`
- `0x18001eb40`
- `0x18001edec`
- `0x18001f048`
- `0x18001f390`
- `0x18001f5ec`
- `0x18001fd08`
- `0x180020038`
- `0x1800208d8`
- `0x180020d0c`
- `0x1800210f4`
- `0x180022708`
- `0x180022a5c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180022d6b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180022d6b`

## pseudocode

```c
void __fastcall KpsStartTimeoutTimer(struct _KPS_IO *a1)
{
  struct _TP_WAIT *v1; // rcx
  struct _FILETIME pftTimeout; // [rsp+30h] [rbp+8h] BYREF

  v1 = (struct _TP_WAIT *)*((_QWORD *)a1 + 41);
  pftTimeout = (struct _FILETIME)(-10000LL * (unsigned int)dword_18003A9CC);
  SetThreadpoolWait(v1, h, &pftTimeout);
}

```

## disassembly

```asm
0x180022d38  sub     rsp, 28h
0x180022d3c  mov     eax, cs:dword_18003A9CC
0x180022d42  lea     r8, [rsp+28h+pftTimeout]; pftTimeout
0x180022d47  mov     rcx, [rcx+148h]; pwa
0x180022d4e  imul    rdx, rax, 0FFFFFFFFFFFFD8F0h
0x180022d55  mov     rax, rdx
0x180022d58  mov     [rsp+28h+pftTimeout.dwLowDateTime], edx
0x180022d5c  mov     rdx, cs:h; h
0x180022d63  shr     rax, 20h
0x180022d67  mov     [rsp+28h+pftTimeout.dwHighDateTime], eax
0x180022d6b  call    cs:__imp_SetThreadpoolWait
0x180022d72  nop     dword ptr [rax+rax+00h]
0x180022d77  add     rsp, 28h
0x180022d7b  retn
```
