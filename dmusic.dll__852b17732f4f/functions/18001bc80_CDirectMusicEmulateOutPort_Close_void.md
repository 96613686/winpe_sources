# CDirectMusicEmulateOutPort::Close(void)

- ea: `0x18001bc80`
- end: `0x18001bcc7`
- name: `?Close@CDirectMusicEmulateOutPort@@UEAAJXZ`
- size: `71`
- prototype: `__int64 __fastcall(CDirectMusicEmulateOutPort *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001bb44`

## callees

- `0x18001ada0`
- `0x18001bc80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001bcb4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001bcb4`
- `api-ms-win-mm-misc-l2-1-0!timeKillEvent` at `0x18001bc9d`
- `api-ms-win-mm-misc-l2-1-0!timeKillEvent` at `0x18001bc9d`

## pseudocode

```c
__int64 __fastcall CDirectMusicEmulateOutPort::Close(CDirectMusicEmulateOutPort *this)
{
  UINT v2; // ecx

  *((_DWORD *)this + 117) = 1;
  v2 = *((_DWORD *)this + 116);
  if ( v2 )
  {
    timeKillEvent(v2);
    *((_DWORD *)this + 116) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
  return CDirectMusicEmulatePort::Close(this);
}

```

## disassembly

```asm
0x18001bc80  push    rbx
0x18001bc82  sub     rsp, 20h
0x18001bc86  mov     rbx, rcx
0x18001bc89  mov     dword ptr [rcx+1D4h], 1
0x18001bc93  mov     ecx, [rcx+1D0h]; uTimerID
0x18001bc99  test    ecx, ecx
0x18001bc9b  jz      short loc_18001BCAD
0x18001bc9d  call    cs:__imp_timeKillEvent
0x18001bca3  mov     dword ptr [rbx+1D0h], 0
0x18001bcad  lea     rcx, [rbx+180h]; lpCriticalSection
0x18001bcb4  call    cs:__imp_DeleteCriticalSection
0x18001bcba  mov     rcx, rbx; this
0x18001bcbd  add     rsp, 20h
0x18001bcc1  pop     rbx
0x18001bcc2  jmp     ?Close@CDirectMusicEmulatePort@@UEAAJXZ; CDirectMusicEmulatePort::Close(void)
```
