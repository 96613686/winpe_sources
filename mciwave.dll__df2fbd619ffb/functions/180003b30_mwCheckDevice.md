# mwCheckDevice

- ea: `0x180003b30`
- end: `0x180003bb9`
- name: `mwCheckDevice`
- size: `137`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004028`
- `0x180004318`
- `0x1800046f0`

## callees

- `0x180003b30`

## import_xrefs

- `WINMM!waveInOpen` at `0x180003b90`
- `WINMM!waveInOpen` at `0x180003b90`
- `WINMM!waveOutOpen` at `0x180003b75`
- `WINMM!waveOutOpen` at `0x180003b75`

## pseudocode

```c
__int64 __fastcall mwCheckDevice(__int64 a1, int a2)
{
  const WAVEFORMATEX *v2; // r8
  bool v5; // zf
  UINT v6; // edx
  unsigned int v7; // ebx

  v2 = *(const WAVEFORMATEX **)(a1 + 168);
  if ( !v2->nBlockAlign )
    return 282;
  v5 = a2 == 1;
  v6 = *(_DWORD *)(a1 + 36);
  v7 = 0;
  if ( v5 )
  {
    if ( waveOutOpen(0, v6, v2, 0, 0, 1u) )
    {
      LOBYTE(v7) = *(_DWORD *)(a1 + 36) != -1;
      v7 += 326;
    }
  }
  else if ( waveInOpen(0, v6, v2, 0, 0, 1u) )
  {
    LOBYTE(v7) = *(_DWORD *)(a1 + 36) != -1;
    v7 += 328;
  }
  return v7;
}

```

## disassembly

```asm
0x180003b30  mov     [rsp+arg_0], rbx
0x180003b35  mov     [rsp+arg_8], rsi
0x180003b3a  push    rdi
0x180003b3b  sub     rsp, 30h
0x180003b3f  mov     r8, [rcx+0A8h]; pwfx
0x180003b46  xor     esi, esi
0x180003b48  mov     rdi, rcx
0x180003b4b  cmp     [r8+0Ch], si
0x180003b50  jnz     short loc_180003B59
0x180003b52  mov     eax, 11Ah
0x180003b57  jmp     short loc_180003BA9
0x180003b59  mov     eax, 1
0x180003b5e  xor     r9d, r9d; dwCallback
0x180003b61  mov     [rsp+38h+fdwOpen], eax; fdwOpen
0x180003b65  cmp     edx, eax
0x180003b67  mov     edx, [rcx+24h]; uDeviceID
0x180003b6a  mov     ebx, esi
0x180003b6c  mov     [rsp+38h+dwInstance], rsi; dwInstance
0x180003b71  jnz     short loc_180003B8E
0x180003b73  xor     ecx, ecx; phwo
0x180003b75  call    cs:__imp_waveOutOpen
0x180003b7b  test    eax, eax
0x180003b7d  jz      short loc_180003BA7
0x180003b7f  cmp     dword ptr [rdi+24h], 0FFFFFFFFh
0x180003b83  setnz   bl
0x180003b86  add     ebx, 146h
0x180003b8c  jmp     short loc_180003BA7
0x180003b8e  xor     ecx, ecx; phwi
0x180003b90  call    cs:__imp_waveInOpen
0x180003b96  test    eax, eax
0x180003b98  jz      short loc_180003BA7
0x180003b9a  cmp     dword ptr [rdi+24h], 0FFFFFFFFh
0x180003b9e  setnz   bl
0x180003ba1  add     ebx, 148h
0x180003ba7  mov     eax, ebx
0x180003ba9  mov     rbx, [rsp+38h+arg_0]
0x180003bae  mov     rsi, [rsp+38h+arg_8]
0x180003bb3  add     rsp, 30h
0x180003bb7  pop     rdi
0x180003bb8  retn
```
