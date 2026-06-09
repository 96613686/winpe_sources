# ErrorSetExtendedInfoSz1(x,x,x)

- ea: `0x1000a1f0`
- end: `0x1000a25f`
- name: `_ErrorSetExtendedInfoSz1@12`
- size: `111`
- prototype: `int __stdcall(int, STRSAFE_LPCWSTR pszSrc, int)`
- caller_count: `16`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1000f0e0`
- `0x1000f530`
- `0x1000f8f0`
- `0x1000fa40`
- `0x1000fc70`
- `0x1000ff30`
- `0x10010020`
- `0x10010450`
- `0x100108e0`
- `0x10010f00`
- `0x100113f0`
- `0x10011870`
- `0x10011d90`
- `0x10016d90`
- `0x100178b0`
- `0x10018b90`

## callees

- `0x1000a1f0`
- `0x1000a3e0`
- `0x1000b200`
- `0x10013b00`

## pseudocode

```c
void __stdcall ErrorSetExtendedInfoSz1(int a1, wchar_t *pszSrc, char a3)
{
  wchar_t *v3; // esi
  void (__stdcall *v4)(int, wchar_t *, const wchar_t *, const wchar_t *, int, _DWORD, _DWORD, _DWORD); // eax

  if ( dword_10040F68 )
  {
    if ( (a3 & 1) != 0 )
      v3 = (wchar_t *)HashToDot(pszSrc);
    else
      v3 = pszSrc;
    v4 = *(void (__stdcall **)(int, wchar_t *, const wchar_t *, const wchar_t *, int, _DWORD, _DWORD, _DWORD))(ISAMCurrentTaskCallbacks() + 44);
    if ( v3 )
    {
      v4(dword_10040F68, v3, &dword_100010B4, &dword_100010B4, a1, 0, 0, 0);
      if ( (a3 & 1) != 0 )
        MemFree(v3);
    }
    else
    {
      v4(dword_10040F68, (wchar_t *)&dword_100010B4, &dword_100010B4, &dword_100010B4, a1, 0, 0, 0);
    }
  }
}

```

## disassembly

```asm
0x1000a1f0  cmp     dword_10040F68, 0
0x1000a1f7  jz      short locret_1000A25C
0x1000a1f9  push    esi
0x1000a1fa  push    edi
0x1000a1fb  mov     edi, [esp+8+arg_8]
0x1000a1ff  and     edi, 1
0x1000a202  jz      short loc_1000A211
0x1000a204  push    [esp+8+pszSrc]; pszSrc
0x1000a208  call    HashToDot
0x1000a20d  mov     esi, eax
0x1000a20f  jmp     short loc_1000A215
0x1000a211  mov     esi, [esp+8+pszSrc]
0x1000a215  call    _ISAMCurrentTaskCallbacks@0; ISAMCurrentTaskCallbacks()
0x1000a21a  push    0
0x1000a21c  push    0
0x1000a21e  push    0
0x1000a220  mov     eax, [eax+2Ch]
0x1000a223  push    [esp+14h+arg_0]
0x1000a227  push    offset dword_100010B4
0x1000a22c  push    offset dword_100010B4
0x1000a231  test    esi, esi
0x1000a233  jz      short loc_1000A24D
0x1000a235  push    esi
0x1000a236  push    dword_10040F68
0x1000a23c  call    eax
0x1000a23e  test    edi, edi
0x1000a240  jz      short loc_1000A25A
0x1000a242  push    esi
0x1000a243  call    _MemFree@4; MemFree(x)
0x1000a248  pop     edi
0x1000a249  pop     esi
0x1000a24a  retn    0Ch
0x1000a24d  push    offset dword_100010B4
0x1000a252  push    dword_10040F68
0x1000a258  call    eax
0x1000a25a  pop     edi
0x1000a25b  pop     esi
0x1000a25c  retn    0Ch
```
