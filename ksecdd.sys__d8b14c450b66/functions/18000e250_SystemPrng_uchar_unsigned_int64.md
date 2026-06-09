# SystemPrng(uchar *,unsigned __int64)

- ea: `0x18000e250`
- end: `0x18000e27b`
- name: `?SystemPrng@@YAHPEAE_K@Z`
- size: `43`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000e250`
- `0x180010920`

## pseudocode

```c
__int64 __fastcall SystemPrng(unsigned __int8 *a1)
{
  __int64 (__fastcall *v1)(unsigned __int8 *); // rax

  if ( *(_QWORD *)&WPP_MAIN_CB.SectorSize
    && (v1 = *(__int64 (__fastcall **)(unsigned __int8 *))(*(_QWORD *)&WPP_MAIN_CB.SectorSize + 320LL)) != 0 )
  {
    return v1(a1);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x18000e250  sub     rsp, 28h
0x18000e254  mov     rax, qword ptr cs:WPP_MAIN_CB.SectorSize
0x18000e25b  test    rax, rax
0x18000e25e  jz      short loc_18000E273
0x18000e260  mov     rax, [rax+140h]
0x18000e267  test    rax, rax
0x18000e26a  jz      short loc_18000E273
0x18000e26c  call    _guard_dispatch_icall
0x18000e271  jmp     short loc_18000E275
0x18000e273  xor     eax, eax
0x18000e275  add     rsp, 28h
0x18000e279  retn
```
