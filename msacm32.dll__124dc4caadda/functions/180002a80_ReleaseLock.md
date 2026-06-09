# ReleaseLock

- ea: `0x180002a80`
- end: `0x180002af5`
- name: `ReleaseLock`
- size: `117`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x180002540`
- `0x180002900`
- `0x180002b00`
- `0x180002e70`
- `0x180007ef0`
- `0x180008160`
- `0x1800089c0`
- `0x180008c00`
- `0x180008d00`
- `0x18000ad3c`
- `0x18000b8d0`
- `0x18000bca0`
- `0x18000c130`
- `0x18000cfe0`
- `0x18000d7b0`
- `0x18000da50`

## callees

- `0x180002a80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002aac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a89`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002ad7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002aed`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002ad7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002aed`

## pseudocode

```c
void __fastcall ReleaseLock(__int64 a1)
{
  int v2; // eax
  int v3; // eax
  bool v4; // zf
  void *v5; // rcx
  void *v6; // rcx

  EnterCriticalSection((LPCRITICAL_SECTION)a1);
  v2 = *(_DWORD *)(a1 + 68);
  if ( v2 < 0 )
  {
    v4 = v2 == -1;
    v3 = v2 + 1;
    *(_DWORD *)(a1 + 68) = v3;
    if ( v4 )
    {
      v4 = *(_DWORD *)(a1 + 48) == 0;
      *(_DWORD *)(a1 + 72) = 0;
      if ( v4 )
      {
        v5 = *(void **)(a1 + 40);
        *(_DWORD *)(a1 + 48) = 1;
        SetEvent(v5);
        v3 = *(_DWORD *)(a1 + 68);
      }
      else
      {
        v3 = 0;
      }
    }
  }
  else
  {
    v3 = v2 - 1;
    *(_DWORD *)(a1 + 68) = v3;
  }
  if ( !v3 && !*(_DWORD *)(a1 + 64) )
  {
    v6 = *(void **)(a1 + 56);
    *(_DWORD *)(a1 + 64) = 1;
    SetEvent(v6);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)a1);
}

```

## disassembly

```asm
0x180002a80  push    rbx
0x180002a82  sub     rsp, 20h
0x180002a86  mov     rbx, rcx
0x180002a89  call    cs:__imp_EnterCriticalSection
0x180002a8f  mov     eax, [rbx+44h]
0x180002a92  test    eax, eax
0x180002a94  js      short loc_180002AB3
0x180002a96  dec     eax
0x180002a98  mov     [rbx+44h], eax
0x180002a9b  test    eax, eax
0x180002a9d  jnz     short loc_180002AA4
0x180002a9f  cmp     [rbx+40h], eax
0x180002aa2  jz      short loc_180002AE2
0x180002aa4  mov     rcx, rbx
0x180002aa7  add     rsp, 20h
0x180002aab  pop     rbx
0x180002aac  jmp     cs:__imp_LeaveCriticalSection
0x180002ab3  add     eax, 1
0x180002ab6  mov     [rbx+44h], eax
0x180002ab9  jnz     short loc_180002A9B
0x180002abb  cmp     dword ptr [rbx+30h], 0
0x180002abf  mov     dword ptr [rbx+48h], 0
0x180002ac6  jz      short loc_180002ACC
0x180002ac8  xor     eax, eax
0x180002aca  jmp     short loc_180002A9B
0x180002acc  mov     rcx, [rbx+28h]; hEvent
0x180002ad0  mov     dword ptr [rbx+30h], 1
0x180002ad7  call    cs:__imp_SetEvent
0x180002add  mov     eax, [rbx+44h]
0x180002ae0  jmp     short loc_180002A9B
0x180002ae2  mov     rcx, [rbx+38h]; hEvent
0x180002ae6  mov     dword ptr [rbx+40h], 1
0x180002aed  call    cs:__imp_SetEvent
0x180002af3  jmp     short loc_180002AA4
```
