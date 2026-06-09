# DBOpenFormat

- ea: `0x1001a940`
- end: `0x1001aa31`
- name: `DBOpenFormat`
- size: `241`
- prototype: `int __stdcall(_WORD *, unsigned int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x10006400`
- `0x1001a940`
- `0x1002580a`
- `0x1002ee43`

## pseudocode

```c
int __stdcall DBOpenFormat(_WORD *a1, unsigned int a2, int a3)
{
  int v3; // esi
  wchar_t *v4; // edx
  int v5; // eax
  int result; // eax
  int *v7; // eax

  if ( !*(_DWORD *)(dword_1003A9BC + 76) )
    dword_1003A9B0 = 0;
  v3 = MemAllocate(20);
  if ( !v3 )
    return -2;
  if ( *(_DWORD *)(dword_1003A9BC + 4) == 4 )
  {
    if ( dword_1003A9B0 == 22 )
    {
      v4 = L"h:mm am/pm";
      if ( dword_1003B918 )
        v4 = L"hh:mm am/pm";
    }
    else
    {
      if ( dword_1003A9B0 != 23 )
        goto LABEL_13;
      v4 = L"h:mm:ss am/pm";
      if ( dword_1003B918 )
        v4 = L"hh:mm:ss am/pm";
    }
    WCSCPY2(a1, v4, a2);
  }
LABEL_13:
  v5 = FMTStoreFormat(a1, (_DWORD *)(v3 + 8));
  if ( v5 )
    return 8 * (v5 == -2) - 10;
  ++dword_1003A9B0;
  *(_DWORD *)(v3 + 4) = a3;
  if ( *(_DWORD *)(dword_1003A9BC + 76) )
  {
    v7 = (int *)dword_1003A9B4;
    dword_1003A9B4 = v3;
    *v7 = v3;
    return 0;
  }
  else
  {
    *(_DWORD *)(dword_1003A9BC + 76) = v3;
    result = 0;
    dword_1003A9B4 = v3;
  }
  return result;
}

```

## disassembly

```asm
0x1001a940  mov     edi, edi
0x1001a942  push    ebp
0x1001a943  mov     ebp, esp
0x1001a945  mov     eax, dword_1003A9BC
0x1001a94a  cmp     dword ptr [eax+4Ch], 0
0x1001a94e  jnz     short loc_1001A95A
0x1001a950  mov     dword_1003A9B0, 0
0x1001a95a  push    esi
0x1001a95b  mov     ecx, 14h
0x1001a960  call    _MemAllocate@4; MemAllocate(x)
0x1001a965  mov     esi, eax
0x1001a967  test    esi, esi
0x1001a969  jz      loc_1001AA27
0x1001a96f  mov     ecx, dword_1003A9BC
0x1001a975  push    edi
0x1001a976  mov     edi, [ebp+arg_0]
0x1001a979  cmp     dword ptr [ecx+4], 4
0x1001a97d  jnz     short loc_1001A9C1
0x1001a97f  mov     eax, dword_1003A9B0
0x1001a984  cmp     eax, 16h
0x1001a987  jnz     short loc_1001A99F
0x1001a989  cmp     dword_1003B918, 0
0x1001a990  mov     edx, offset aHMmAmPm_0; "h:mm am/pm"
0x1001a995  mov     eax, offset aHhMmAmPm; "hh:mm am/pm"
0x1001a99a  cmovnz  edx, eax
0x1001a99d  jmp     short loc_1001A9B7
0x1001a99f  cmp     eax, 17h
0x1001a9a2  jnz     short loc_1001A9C1
0x1001a9a4  cmp     dword_1003B918, 0
0x1001a9ab  mov     edx, offset aHMmSsAmPm; "h:mm:ss am/pm"
0x1001a9b0  jz      short loc_1001A9B7
0x1001a9b2  mov     edx, offset aHhMmSsAmPm; "hh:mm:ss am/pm"
0x1001a9b7  push    [ebp+arg_4]
0x1001a9ba  mov     ecx, edi
0x1001a9bc  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001a9c1  lea     eax, [esi+8]
0x1001a9c4  mov     edx, offset _ControlPanelSettings
0x1001a9c9  push    eax
0x1001a9ca  mov     ecx, edi
0x1001a9cc  call    _FMTStoreFormat@12; FMTStoreFormat(x,x,x)
0x1001a9d1  mov     ecx, eax
0x1001a9d3  pop     edi
0x1001a9d4  test    ecx, ecx
0x1001a9d6  jz      short loc_1001A9EC
0x1001a9d8  xor     eax, eax
0x1001a9da  cmp     ecx, 0FFFFFFFEh
0x1001a9dd  pop     esi
0x1001a9de  setz    al
0x1001a9e1  lea     eax, ds:0FFFFFFF6h[eax*8]
0x1001a9e8  pop     ebp
0x1001a9e9  retn    0Ch
0x1001a9ec  mov     eax, [ebp+arg_8]
0x1001a9ef  inc     dword_1003A9B0
0x1001a9f5  mov     [esi+4], eax
0x1001a9f8  mov     eax, dword_1003A9BC
0x1001a9fd  cmp     dword ptr [eax+4Ch], 0
0x1001aa01  jnz     short loc_1001AA13
0x1001aa03  mov     [eax+4Ch], esi
0x1001aa06  xor     eax, eax
0x1001aa08  mov     dword_1003A9B4, esi
0x1001aa0e  pop     esi
0x1001aa0f  pop     ebp
0x1001aa10  retn    0Ch
0x1001aa13  mov     eax, dword_1003A9B4
0x1001aa18  mov     dword_1003A9B4, esi
0x1001aa1e  mov     [eax], esi
0x1001aa20  xor     eax, eax
0x1001aa22  pop     esi
0x1001aa23  pop     ebp
0x1001aa24  retn    0Ch
0x1001aa27  mov     eax, 0FFFFFFFEh
0x1001aa2c  pop     esi
0x1001aa2d  pop     ebp
0x1001aa2e  retn    0Ch
```
