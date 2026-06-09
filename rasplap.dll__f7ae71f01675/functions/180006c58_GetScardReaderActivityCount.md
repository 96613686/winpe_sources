# GetScardReaderActivityCount

- ea: `0x180006c58`
- end: `0x180006d52`
- name: `GetScardReaderActivityCount`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001ee0`

## callees

- `0x180006c58`
- `0x18000b0ce`
- `0x18000b100`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180006cb1`
- `KERNEL32!WaitForSingleObject` at `0x180006cb1`
- `WinSCard!SCardReleaseStartedEvent` at `0x180006d18`
- `WinSCard!SCardReleaseStartedEvent` at `0x180006d18`
- `WinSCard!SCardReleaseContext` at `0x180006d28`
- `WinSCard!SCardReleaseContext` at `0x180006d28`
- `WinSCard!SCardEstablishContext` at `0x180006ccf`
- `WinSCard!SCardEstablishContext` at `0x180006ccf`
- `WinSCard!SCardGetStatusChangeW` at `0x180006d00`
- `WinSCard!SCardGetStatusChangeW` at `0x180006d00`
- `WinSCard!SCardAccessStartedEvent` at `0x180006c97`
- `WinSCard!SCardAccessStartedEvent` at `0x180006c97`

## pseudocode

```c
__int64 __fastcall GetScardReaderActivityCount(const WCHAR *a1, DWORD *a2)
{
  HANDLE v4; // rax
  unsigned int v5; // ebx
  SCARDCONTEXT phContext[2]; // [rsp+20h] [rbp-68h] BYREF
  struct $B80B7D01E79FADDB4AAC58DE22BC823F rgReaderStates; // [rsp+30h] [rbp-58h] BYREF

  phContext[0] = 0;
  memset_0(&rgReaderStates, 0, sizeof(rgReaderStates));
  v4 = SCardAccessStartedEvent();
  if ( v4 )
  {
    if ( WaitForSingleObject(v4, 0x3E8u) )
    {
      v5 = -2146435043;
    }
    else
    {
      v5 = SCardEstablishContext(2u, 0, 0, phContext);
      if ( !v5 )
      {
        memset_0(&rgReaderStates, 0, sizeof(rgReaderStates));
        rgReaderStates.szReader = a1;
        v5 = SCardGetStatusChangeW(phContext[0], 0, &rgReaderStates, 1u);
        if ( !v5 )
          *a2 = rgReaderStates.dwEventState & 0xFFFF0000;
      }
    }
    SCardReleaseStartedEvent();
  }
  else
  {
    v5 = -2146435043;
  }
  if ( phContext[0] )
    SCardReleaseContext(phContext[0]);
  return v5;
}

```

## disassembly

```asm
0x180006c58  mov     r11, rsp
0x180006c5b  mov     [r11+18h], rbx
0x180006c5f  mov     [r11+20h], rsi
0x180006c63  push    rdi
0x180006c64  sub     rsp, 80h
0x180006c6b  mov     rax, cs:__security_cookie
0x180006c72  xor     rax, rsp
0x180006c75  mov     [rsp+88h+var_18], rax
0x180006c7a  mov     rdi, rdx
0x180006c7d  mov     qword ptr [r11-68h], 0
0x180006c85  xor     edx, edx; Val
0x180006c87  mov     rsi, rcx
0x180006c8a  lea     rcx, [r11-58h]; void *
0x180006c8e  lea     r8d, [rdx+40h]; Size
0x180006c92  call    memset_0
0x180006c97  call    cs:__imp_SCardAccessStartedEvent
0x180006c9d  test    rax, rax
0x180006ca0  jnz     short loc_180006CA9
0x180006ca2  mov     ebx, 8010001Dh
0x180006ca7  jmp     short loc_180006D1E
0x180006ca9  mov     edx, 3E8h; dwMilliseconds
0x180006cae  mov     rcx, rax; hHandle
0x180006cb1  call    cs:__imp_WaitForSingleObject
0x180006cb7  test    eax, eax
0x180006cb9  jz      short loc_180006CC2
0x180006cbb  mov     ebx, 8010001Dh
0x180006cc0  jmp     short loc_180006D18
0x180006cc2  xor     edx, edx; pvReserved1
0x180006cc4  lea     r9, [rsp+88h+phContext]; phContext
0x180006cc9  xor     r8d, r8d; pvReserved2
0x180006ccc  lea     ecx, [rdx+2]; dwScope
0x180006ccf  call    cs:__imp_SCardEstablishContext
0x180006cd5  mov     ebx, eax
0x180006cd7  test    eax, eax
0x180006cd9  jnz     short loc_180006D18
0x180006cdb  xor     edx, edx; Val
0x180006cdd  lea     r8d, [rax+40h]; Size
0x180006ce1  lea     rcx, [rsp+88h+rgReaderStates]; void *
0x180006ce6  call    memset_0
0x180006ceb  mov     rcx, [rsp+88h+phContext]; hContext
0x180006cf0  lea     r9d, [rbx+1]; cReaders
0x180006cf4  lea     r8, [rsp+88h+rgReaderStates]; rgReaderStates
0x180006cf9  mov     [rsp+88h+rgReaderStates.szReader], rsi
0x180006cfe  xor     edx, edx; dwTimeout
0x180006d00  call    cs:__imp_SCardGetStatusChangeW
0x180006d06  mov     ebx, eax
0x180006d08  test    eax, eax
0x180006d0a  jnz     short loc_180006D18
0x180006d0c  mov     ecx, [rsp+88h+rgReaderStates.dwEventState]
0x180006d10  and     ecx, 0FFFF0000h
0x180006d16  mov     [rdi], ecx
0x180006d18  call    cs:__imp_SCardReleaseStartedEvent
0x180006d1e  mov     rcx, [rsp+88h+phContext]; hContext
0x180006d23  test    rcx, rcx
0x180006d26  jz      short loc_180006D2E
0x180006d28  call    cs:__imp_SCardReleaseContext
0x180006d2e  mov     eax, ebx
0x180006d30  mov     rcx, [rsp+88h+var_18]
0x180006d35  xor     rcx, rsp; StackCookie
0x180006d38  call    __security_check_cookie
0x180006d3d  lea     r11, [rsp+88h+var_8]
0x180006d45  mov     rbx, [r11+20h]
0x180006d49  mov     rsi, [r11+28h]
0x180006d4d  mov     rsp, r11
0x180006d50  pop     rdi
0x180006d51  retn
```
