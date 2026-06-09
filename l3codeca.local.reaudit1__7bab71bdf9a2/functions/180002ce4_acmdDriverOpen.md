# acmdDriverOpen

- ea: `0x180002ce4`
- end: `0x180002d9b`
- name: `acmdDriverOpen`
- size: `183`
- prototype: `__int64 __fastcall(HDRVR hDriver)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800036c0`

## callees

- `0x180002ce4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002d09`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002d09`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002d3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002d3f`
- `api-ms-win-mm-misc-l1-1-0!GetDriverModuleHandle` at `0x180002d2e`
- `api-ms-win-mm-misc-l1-1-0!GetDriverModuleHandle` at `0x180002d2e`

## pseudocode

```c
_QWORD *__fastcall acmdDriverOpen(HDRVR hDriver, _DWORD *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  HMODULE DriverModuleHandle; // rax

  if ( a2 && a2[1] != 1667528033 )
    return 0;
  v4 = LocalAlloc(0x40u, 0x48u);
  v5 = v4;
  if ( !v4 )
  {
    if ( a2 )
      a2[5] = 7;
    return 0;
  }
  v4[2] = hDriver;
  DriverModuleHandle = GetDriverModuleHandle(hDriver);
  v5[3] = DriverModuleHandle;
  if ( !DriverModuleHandle )
    v5[3] = GetModuleHandleW(0);
  *(_QWORD *)((char *)v5 + 52) = 0;
  *((_DWORD *)v5 + 15) = 0;
  *((_DWORD *)v5 + 16) = _InterlockedIncrement(&dword_18001A148);
  if ( a2 )
  {
    v5[1] = 0;
    *(_DWORD *)v5 = a2[1];
    *((_DWORD *)v5 + 8) = a2[3];
    *((_DWORD *)v5 + 9) = a2[4];
    a2[5] = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180002ce4  push    rbx
0x180002ce6  push    rbp
0x180002ce7  push    rsi
0x180002ce8  push    rdi
0x180002ce9  sub     rsp, 28h
0x180002ced  mov     rdi, rdx
0x180002cf0  mov     rbp, rcx
0x180002cf3  test    rdx, rdx
0x180002cf6  jz      short loc_180002D01
0x180002cf8  cmp     dword ptr [rdx+4], 63647561h
0x180002cff  jnz     short loc_180002D23
0x180002d01  mov     edx, 48h ; 'H'; uBytes
0x180002d06  lea     ecx, [rdx-8]; uFlags
0x180002d09  call    cs:__imp_LocalAlloc
0x180002d0f  mov     rbx, rax
0x180002d12  test    rax, rax
0x180002d15  jnz     short loc_180002D27
0x180002d17  test    rdi, rdi
0x180002d1a  jz      short loc_180002D23
0x180002d1c  mov     dword ptr [rdi+14h], 7
0x180002d23  xor     eax, eax
0x180002d25  jmp     short loc_180002D92
0x180002d27  mov     rcx, rbp; hDriver
0x180002d2a  mov     [rax+10h], rbp
0x180002d2e  call    cs:__imp_GetDriverModuleHandle
0x180002d34  mov     [rbx+18h], rax
0x180002d38  test    rax, rax
0x180002d3b  jnz     short loc_180002D49
0x180002d3d  xor     ecx, ecx; lpModuleName
0x180002d3f  call    cs:__imp_GetModuleHandleW
0x180002d45  mov     [rbx+18h], rax
0x180002d49  mov     qword ptr [rbx+34h], 0
0x180002d51  mov     eax, 1
0x180002d56  mov     dword ptr [rbx+3Ch], 0
0x180002d5d  lock xadd cs:dword_18001A148, eax
0x180002d65  inc     eax
0x180002d67  mov     [rbx+40h], eax
0x180002d6a  test    rdi, rdi
0x180002d6d  jz      short loc_180002D8F
0x180002d6f  mov     qword ptr [rbx+8], 0
0x180002d77  mov     eax, [rdi+4]
0x180002d7a  mov     [rbx], eax
0x180002d7c  mov     eax, [rdi+0Ch]
0x180002d7f  mov     [rbx+20h], eax
0x180002d82  mov     eax, [rdi+10h]
0x180002d85  mov     [rbx+24h], eax
0x180002d88  mov     dword ptr [rdi+14h], 0
0x180002d8f  mov     rax, rbx
0x180002d92  add     rsp, 28h
0x180002d96  pop     rdi
0x180002d97  pop     rsi
0x180002d98  pop     rbp
0x180002d99  pop     rbx
0x180002d9a  retn
```
