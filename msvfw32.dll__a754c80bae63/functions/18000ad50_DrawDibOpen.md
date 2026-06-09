# DrawDibOpen

- ea: `0x18000ad50`
- end: `0x18000adb0`
- name: `DrawDibOpen`
- size: `96`
- prototype: `HDRAWDIB __stdcall()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800047f0`

## callees

- `0x18000ab84`
- `0x18000ad50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ada1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ada1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ad7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ad7b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ad60`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ad60`

## pseudocode

```c
HDRAWDIB __stdcall DrawDibOpen()
{
  HDRAWDIB result; // rax
  HDRAWDIB v1; // rbx

  result = LocalAlloc(0x40u, 0xAE8u);
  v1 = result;
  if ( result )
  {
    *(_DWORD *)result = 2792;
    EnterCriticalSection(&DCISerialize);
    if ( !dword_180023D6C++ )
      DrawDibInit();
    LeaveCriticalSection(&DCISerialize);
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x18000ad50  push    rbx
0x18000ad52  sub     rsp, 20h
0x18000ad56  mov     edx, 0AE8h; uBytes
0x18000ad5b  mov     ecx, 40h ; '@'; uFlags
0x18000ad60  call    cs:__imp_LocalAlloc
0x18000ad66  mov     rbx, rax
0x18000ad69  test    rax, rax
0x18000ad6c  jz      short loc_18000ADAA
0x18000ad6e  lea     rcx, DCISerialize; lpCriticalSection
0x18000ad75  mov     dword ptr [rax], 0AE8h
0x18000ad7b  call    cs:__imp_EnterCriticalSection
0x18000ad81  mov     eax, cs:dword_180023D6C
0x18000ad87  mov     edx, eax
0x18000ad89  inc     eax
0x18000ad8b  mov     cs:dword_180023D6C, eax
0x18000ad91  test    edx, edx
0x18000ad93  jnz     short loc_18000AD9A
0x18000ad95  call    DrawDibInit
0x18000ad9a  lea     rcx, DCISerialize; lpCriticalSection
0x18000ada1  call    cs:__imp_LeaveCriticalSection
0x18000ada7  mov     rax, rbx
0x18000adaa  add     rsp, 20h
0x18000adae  pop     rbx
0x18000adaf  retn
```
