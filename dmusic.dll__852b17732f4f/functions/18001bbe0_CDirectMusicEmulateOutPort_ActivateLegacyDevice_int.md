# CDirectMusicEmulateOutPort::ActivateLegacyDevice(int)

- ea: `0x18001bbe0`
- end: `0x18001bc75`
- name: `?ActivateLegacyDevice@CDirectMusicEmulateOutPort@@UEAAJH@Z`
- size: `149`
- prototype: `__int64 __fastcall(DWORD_PTR dwInstance, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001b808`
- `0x18001bbe0`

## import_xrefs

- `api-ms-win-mm-time-l1-1-0!timeEndPeriod` at `0x18001bc5e`
- `api-ms-win-mm-time-l1-1-0!timeEndPeriod` at `0x18001bc5e`
- `api-ms-win-mm-time-l1-1-0!timeBeginPeriod` at `0x18001bc1d`
- `api-ms-win-mm-time-l1-1-0!timeBeginPeriod` at `0x18001bc1d`
- `api-ms-win-mm-mme-l1-1-0!midiOutClose` at `0x18001bc46`
- `api-ms-win-mm-mme-l1-1-0!midiOutClose` at `0x18001bc46`
- `api-ms-win-mm-mme-l1-1-0!midiOutOpen` at `0x18001bc10`
- `api-ms-win-mm-mme-l1-1-0!midiOutOpen` at `0x18001bc10`
- `api-ms-win-mm-misc-l2-1-0!timeKillEvent` at `0x18001bc2f`
- `api-ms-win-mm-misc-l2-1-0!timeKillEvent` at `0x18001bc2f`

## pseudocode

```c
__int64 __fastcall CDirectMusicEmulateOutPort::ActivateLegacyDevice(DWORD_PTR dwInstance, int a2)
{
  MMRESULT v3; // edi
  UINT v5; // ecx
  MMRESULT v6; // eax
  unsigned int v7; // edi

  if ( a2 )
  {
    v3 = midiOutOpen(
           (LPHMIDIOUT)(dwInstance + 392),
           *(_DWORD *)(dwInstance + 376),
           (DWORD_PTR)&midiOutProc,
           dwInstance,
           0x30000u);
    timeBeginPeriod(5u);
    return MMRESULTToHRESULT(v3);
  }
  else
  {
    v5 = *(_DWORD *)(dwInstance + 480);
    if ( v5 )
    {
      timeKillEvent(v5);
      *(_DWORD *)(dwInstance + 480) = 0;
    }
    v6 = midiOutClose(*(HMIDIOUT *)(dwInstance + 392));
    *(_QWORD *)(dwInstance + 392) = 0;
    v7 = v6;
    timeEndPeriod(5u);
    return MMRESULTToHRESULT(v7);
  }
}

```

## disassembly

```asm
0x18001bbe0  mov     [rsp+arg_0], rbx
0x18001bbe5  push    rdi
0x18001bbe6  sub     rsp, 30h
0x18001bbea  mov     rbx, rcx
0x18001bbed  test    edx, edx
0x18001bbef  jz      short loc_18001BC25
0x18001bbf1  mov     edx, [rbx+178h]; uDeviceID
0x18001bbf7  lea     r8, midiOutProc; dwCallback
0x18001bbfe  add     rcx, 188h; phmo
0x18001bc05  mov     [rsp+38h+fdwOpen], 30000h; fdwOpen
0x18001bc0d  mov     r9, rbx; dwInstance
0x18001bc10  call    cs:__imp_midiOutOpen
0x18001bc16  mov     ecx, 5; uPeriod
0x18001bc1b  mov     edi, eax
0x18001bc1d  call    cs:__imp_timeBeginPeriod
0x18001bc23  jmp     short loc_18001BC64
0x18001bc25  mov     ecx, [rcx+1E0h]; uTimerID
0x18001bc2b  test    ecx, ecx
0x18001bc2d  jz      short loc_18001BC3F
0x18001bc2f  call    cs:__imp_timeKillEvent
0x18001bc35  mov     dword ptr [rbx+1E0h], 0
0x18001bc3f  mov     rcx, [rbx+188h]; hmo
0x18001bc46  call    cs:__imp_midiOutClose
0x18001bc4c  mov     ecx, 5; uPeriod
0x18001bc51  mov     qword ptr [rbx+188h], 0
0x18001bc5c  mov     edi, eax
0x18001bc5e  call    cs:__imp_timeEndPeriod
0x18001bc64  mov     ecx, edi; unsigned int
0x18001bc66  mov     rbx, [rsp+38h+arg_0]
0x18001bc6b  add     rsp, 30h
0x18001bc6f  pop     rdi
0x18001bc70  jmp     ?MMRESULTToHRESULT@@YAJI@Z; MMRESULTToHRESULT(uint)
```
