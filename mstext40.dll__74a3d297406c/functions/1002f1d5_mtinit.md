# __mtinit

- ea: `0x1002f1d5`
- end: `0x1002f24b`
- name: `__mtinit`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1002e1ef`

## callees

- `0x1002f122`
- `0x1002f1d5`
- `0x1002f24b`
- `0x1003029b`
- `0x100302f7`
- `0x100336b6`
- `0x10033c55`
- `0x10034fa5`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1002f231`
- `KERNEL32!GetCurrentThreadId` at `0x1002f231`

## pseudocode

```c
int _mtinit()
{
  DWORD *v0; // eax
  DWORD *v1; // esi
  DWORD CurrentThreadId; // eax

  _init_pointers();
  if ( _mtinitlocks()
    && (__flsindex = __crtFlsAlloc(_freefls), __flsindex != -1)
    && (v0 = (DWORD *)_calloc_crt(1, 956), (v1 = v0) != 0)
    && __crtFlsSetValue(__flsindex, v0) )
  {
    _initptd(v1, 0);
    CurrentThreadId = GetCurrentThreadId();
    v1[1] = -1;
    *v1 = CurrentThreadId;
    return 1;
  }
  else
  {
    _mtterm();
    return 0;
  }
}

```

## disassembly

```asm
0x1002f1d5  call    __init_pointers
0x1002f1da  call    __mtinitlocks
0x1002f1df  test    eax, eax
0x1002f1e1  jnz     short loc_1002F1EB
0x1002f1e3  call    __mtterm
0x1002f1e8  xor     eax, eax
0x1002f1ea  retn
0x1002f1eb  push    offset __freefls@4
0x1002f1f0  call    ___crtFlsAlloc
0x1002f1f5  mov     ___flsindex, eax
0x1002f1fa  pop     ecx
0x1002f1fb  cmp     eax, 0FFFFFFFFh
0x1002f1fe  jz      short loc_1002F1E3
0x1002f200  push    esi
0x1002f201  push    3BCh
0x1002f206  push    1
0x1002f208  call    __calloc_crt
0x1002f20d  mov     esi, eax
0x1002f20f  pop     ecx
0x1002f210  pop     ecx
0x1002f211  test    esi, esi
0x1002f213  jz      short loc_1002F242
0x1002f215  push    esi; lpTlsValue
0x1002f216  push    ___flsindex; dwTlsIndex
0x1002f21c  call    ___crtFlsSetValue
0x1002f221  pop     ecx
0x1002f222  pop     ecx
0x1002f223  test    eax, eax
0x1002f225  jz      short loc_1002F242
0x1002f227  push    0
0x1002f229  push    esi
0x1002f22a  call    __initptd
0x1002f22f  pop     ecx
0x1002f230  pop     ecx
0x1002f231  call    ds:__imp__GetCurrentThreadId@0
0x1002f237  or      dword ptr [esi+4], 0FFFFFFFFh
0x1002f23b  mov     [esi], eax
0x1002f23d  xor     eax, eax
0x1002f23f  inc     eax
0x1002f240  pop     esi
0x1002f241  retn
0x1002f242  call    __mtterm
0x1002f247  xor     eax, eax
0x1002f249  pop     esi
0x1002f24a  retn
```
