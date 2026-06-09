# CDirectMusicUMAPort::SetReadNotificationHandle(void *)

- ea: `0x180020d40`
- end: `0x180020d63`
- name: `?SetReadNotificationHandle@CDirectMusicUMAPort@@UEAAJPEAX@Z`
- size: `35`
- prototype: `__int64 __fastcall(CDirectMusicUMAPort *__hidden this, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180020d40`

## pseudocode

```c
__int64 __fastcall CDirectMusicUMAPort::SetReadNotificationHandle(CDirectMusicUMAPort *this, void *a2)
{
  if ( !*((_QWORD *)this + 5) )
    return 2289570100LL;
  if ( *((_DWORD *)this + 12) )
    return 2147500033LL;
  *((_QWORD *)this + 153) = a2;
  return 0;
}

```

## disassembly

```asm
0x180020d40  cmp     qword ptr [rcx+28h], 0
0x180020d45  jnz     short loc_180020D4D
0x180020d47  mov     eax, 88781134h
0x180020d4c  retn
0x180020d4d  cmp     dword ptr [rcx+30h], 0
0x180020d51  jz      short loc_180020D59
0x180020d53  mov     eax, 80004001h
0x180020d58  retn
0x180020d59  mov     [rcx+4C8h], rdx
0x180020d60  xor     eax, eax
0x180020d62  retn
```
