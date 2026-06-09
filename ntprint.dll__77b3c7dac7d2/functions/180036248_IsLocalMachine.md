# IsLocalMachine

- ea: `0x180036248`
- end: `0x1800362db`
- name: `IsLocalMachine`
- size: `147`
- prototype: `__int64 __fastcall(LPCWSTR lpString1)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009724`
- `0x18000b7ec`
- `0x180012424`
- `0x18001c680`
- `0x180027e90`
- `0x1800288a0`

## callees

- `0x180036248`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x1800362ba`
- `KERNEL32!lstrcmpiW` at `0x1800362ba`
- `KERNEL32!GetComputerNameW` at `0x18003629c`
- `KERNEL32!GetComputerNameW` at `0x18003629c`

## pseudocode

```c
__int64 __fastcall IsLocalMachine(LPCWSTR lpString1)
{
  unsigned int v2; // edi
  DWORD nSize; // [rsp+30h] [rbp+8h] BYREF

  if ( !lpString1 || !*lpString1 )
    return 1;
  v2 = 0;
  if ( *lpString1 == 92 && lpString1[1] == 92 )
  {
    if ( !dword_180055EAC )
    {
      *(_DWORD *)&szLocalMachineName = 6029404;
      nSize = 16;
      dword_180055EAC = GetComputerNameW(&Buffer, &nSize);
    }
    if ( !lstrcmpiW(lpString1, &szLocalMachineName) )
      return 1;
  }
  return v2;
}

```

## disassembly

```asm
0x180036248  mov     [rsp+arg_8], rbx
0x18003624d  mov     [rsp+arg_10], rsi
0x180036252  push    rdi
0x180036253  sub     rsp, 20h
0x180036257  xor     esi, esi
0x180036259  mov     rbx, rcx
0x18003625c  test    rcx, rcx
0x18003625f  jz      short loc_1800362C4
0x180036261  cmp     [rcx], si
0x180036264  jz      short loc_1800362C4
0x180036266  lea     eax, [rsi+5Ch]
0x180036269  mov     edi, esi
0x18003626b  cmp     [rcx], ax
0x18003626e  jnz     short loc_1800362C9
0x180036270  cmp     [rcx+2], ax
0x180036274  jnz     short loc_1800362C9
0x180036276  cmp     cs:dword_180055EAC, esi
0x18003627c  jnz     short loc_1800362B0
0x18003627e  lea     rdx, [rsp+28h+nSize]; nSize
0x180036283  mov     cs:?szLocalMachineName@@3PAGA, 5C005Ch; ushort near * szLocalMachineName
0x18003628d  lea     rcx, Buffer; lpBuffer
0x180036294  mov     [rsp+28h+nSize], 10h
0x18003629c  call    cs:__imp_GetComputerNameW
0x1800362a2  test    eax, eax
0x1800362a4  jz      short loc_1800362B0
0x1800362a6  mov     cs:dword_180055EAC, 1
0x1800362b0  lea     rdx, ?szLocalMachineName@@3PAGA; lpString2
0x1800362b7  mov     rcx, rbx; lpString1
0x1800362ba  call    cs:__imp_lstrcmpiW
0x1800362c0  test    eax, eax
0x1800362c2  jnz     short loc_1800362C9
0x1800362c4  mov     edi, 1
0x1800362c9  mov     rbx, [rsp+28h+arg_8]
0x1800362ce  mov     eax, edi
0x1800362d0  mov     rsi, [rsp+28h+arg_10]
0x1800362d5  add     rsp, 20h
0x1800362d9  pop     rdi
0x1800362da  retn
```
