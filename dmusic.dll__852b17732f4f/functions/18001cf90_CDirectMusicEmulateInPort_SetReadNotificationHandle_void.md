# CDirectMusicEmulateInPort::SetReadNotificationHandle(void *)

- ea: `0x18001cf90`
- end: `0x18001cfa9`
- name: `?SetReadNotificationHandle@CDirectMusicEmulateInPort@@UEAAJPEAX@Z`
- size: `25`
- prototype: `__int64 __fastcall(CDirectMusicEmulateInPort *__hidden this, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001cf90`

## pseudocode

```c
__int64 __fastcall CDirectMusicEmulateInPort::SetReadNotificationHandle(CDirectMusicEmulateInPort *this, void *a2)
{
  __int64 result; // rax

  result = 0;
  if ( !*((_QWORD *)this + 46) )
    return 2289570100LL;
  *((_QWORD *)this + 49) = a2;
  return result;
}

```

## disassembly

```asm
0x18001cf90  xor     eax, eax
0x18001cf92  cmp     [rcx+170h], rax
0x18001cf99  jnz     short loc_18001CFA1
0x18001cf9b  mov     eax, 88781134h
0x18001cfa0  retn
0x18001cfa1  mov     [rcx+188h], rdx
0x18001cfa8  retn
```
