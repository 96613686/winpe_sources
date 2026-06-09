# CscDriverpDereferenceControlHandle

- ea: `0x180003da0`
- end: `0x180003e85`
- name: `CscDriverpDereferenceControlHandle`
- size: `229`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001020`
- `0x1800016b0`
- `0x180002080`
- `0x180003920`

## callees

- `0x180003da0`
- `0x180007bf4`
- `0x180008f90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003dd9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003dd9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003e0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003e0f`
- `ntdll!NtClose` at `0x180003dfb`
- `ntdll!NtClose` at `0x180003dfb`

## pseudocode

```c
void __fastcall CscDriverpDereferenceControlHandle(_QWORD *a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  signed __int32 v6; // ebx
  bool v7; // cc

  v4 = -1;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 7), a2, a3, *a1);
    v5 = WPP_GLOBAL_Control;
  }
  if ( dword_18000E990 )
  {
    EnterCriticalSection(&CriticalSection);
    if ( dword_18000E9C0 > 0 )
    {
      v6 = _InterlockedExchangeAdd(&dword_18000E9C0, 0xFFFFFFFF);
      v7 = v6 <= 1;
      v4 = v6 - 1;
      if ( v7 )
      {
        NtClose(FileHandle);
        FileHandle = 0;
      }
    }
    LeaveCriticalSection(&CriticalSection);
    v5 = WPP_GLOBAL_Control;
  }
  *a1 = 0;
  if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 17) & 0x200) != 0 && *((_BYTE *)v5 + 65) >= 4u )
    WPP_SF_d(v5[7], 43, WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids, v4);
}

```

## disassembly

```asm
0x180003da0  push    rbx
0x180003da2  push    rbp
0x180003da3  push    rsi
0x180003da4  push    rdi
0x180003da5  sub     rsp, 38h
0x180003da9  mov     rdi, rcx
0x180003dac  mov     ebx, 0FFFFFFFFh
0x180003db1  mov     rcx, cs:WPP_GLOBAL_Control
0x180003db8  lea     rbp, WPP_GLOBAL_Control
0x180003dbf  cmp     rcx, rbp
0x180003dc2  jnz     loc_180003E56
0x180003dc8  xor     esi, esi
0x180003dca  cmp     cs:dword_18000E990, esi
0x180003dd0  jz      short loc_180003E1C
0x180003dd2  lea     rcx, CriticalSection; lpCriticalSection
0x180003dd9  call    cs:__imp_EnterCriticalSection
0x180003ddf  cmp     cs:dword_18000E9C0, esi
0x180003de5  jle     short loc_180003E08
0x180003de7  lock xadd cs:dword_18000E9C0, ebx
0x180003def  sub     ebx, 1
0x180003df2  jg      short loc_180003E08
0x180003df4  mov     rcx, cs:FileHandle; Handle
0x180003dfb  call    cs:__imp_NtClose
0x180003e01  mov     cs:FileHandle, rsi
0x180003e08  lea     rcx, CriticalSection; lpCriticalSection
0x180003e0f  call    cs:__imp_LeaveCriticalSection
0x180003e15  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e1c  mov     [rdi], rsi
0x180003e1f  cmp     rcx, rbp
0x180003e22  jnz     short loc_180003E2D
0x180003e24  add     rsp, 38h
0x180003e28  pop     rdi
0x180003e29  pop     rsi
0x180003e2a  pop     rbp
0x180003e2b  pop     rbx
0x180003e2c  retn
0x180003e2d  test    dword ptr [rcx+44h], 200h
0x180003e34  jz      short loc_180003E24
0x180003e36  cmp     byte ptr [rcx+41h], 4
0x180003e3a  jb      short loc_180003E24
0x180003e3c  mov     rcx, [rcx+38h]
0x180003e40  lea     r8, WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids
0x180003e47  mov     edx, 2Bh ; '+'
0x180003e4c  mov     r9d, ebx
0x180003e4f  call    WPP_SF_d
0x180003e54  jmp     short loc_180003E24
0x180003e56  test    dword ptr [rcx+44h], 200h
0x180003e5d  jz      loc_180003DC8
0x180003e63  cmp     byte ptr [rcx+41h], 4
0x180003e67  jb      loc_180003DC8
0x180003e6d  mov     r9, [rdi]
0x180003e70  mov     rcx, [rcx+38h]
0x180003e74  call    WPP_SF_qq
0x180003e79  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e80  jmp     loc_180003DC8
```
