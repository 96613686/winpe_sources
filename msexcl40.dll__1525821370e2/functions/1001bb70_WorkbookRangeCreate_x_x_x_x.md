# WorkbookRangeCreate(x,x,x,x)

- ea: `0x1001bb70`
- end: `0x1001bbc3`
- name: `_WorkbookRangeCreate@16`
- size: `83`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x10028701`
- `0x1002db68`
- `0x1002e5d0`

## callees

- `0x1001bb70`
- `0x1001c2b0`
- `0x100203a0`
- `0x1002580a`

## pseudocode

```c
int __fastcall WorkbookRangeCreate(int a1, struct ExcelRange **a2, unsigned int a3, int a4)
{
  void *v5; // eax
  int result; // eax
  unsigned int *v7; // eax
  unsigned int *v8; // edx

  if ( *(_DWORD *)(a1 + 12) )
  {
    v5 = (void *)XLOLERangeCreate(a1, a2, a3, a4);
    return TranslateEXErrorToJETError(v5);
  }
  else
  {
    v7 = (unsigned int *)MemAllocate(8);
    v8 = v7;
    if ( v7 )
    {
      *v7 = a3;
      result = 0;
      v8[1] = a4;
      *a2 = (struct ExcelRange *)v8;
    }
    else
    {
      return -1011;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1001bb70  mov     edi, edi
0x1001bb72  push    ebp
0x1001bb73  mov     ebp, esp
0x1001bb75  cmp     dword ptr [ecx+0Ch], 0
0x1001bb79  push    esi
0x1001bb7a  mov     esi, edx
0x1001bb7c  jz      short loc_1001BB95
0x1001bb7e  push    [ebp+arg_4]
0x1001bb81  push    [ebp+arg_0]
0x1001bb84  call    _XLOLERangeCreate@16; XLOLERangeCreate(x,x,x,x)
0x1001bb89  mov     ecx, eax
0x1001bb8b  call    _TranslateEXErrorToJETError@4; TranslateEXErrorToJETError(x)
0x1001bb90  pop     esi
0x1001bb91  pop     ebp
0x1001bb92  retn    8
0x1001bb95  mov     ecx, 8
0x1001bb9a  call    _MemAllocate@4; MemAllocate(x)
0x1001bb9f  mov     edx, eax
0x1001bba1  test    edx, edx
0x1001bba3  jnz     short loc_1001BBAF
0x1001bba5  mov     eax, 0FFFFFC0Dh
0x1001bbaa  pop     esi
0x1001bbab  pop     ebp
0x1001bbac  retn    8
0x1001bbaf  mov     eax, [ebp+arg_0]
0x1001bbb2  mov     ecx, [ebp+arg_4]
0x1001bbb5  mov     [edx], eax
0x1001bbb7  xor     eax, eax
0x1001bbb9  mov     [edx+4], ecx
0x1001bbbc  mov     [esi], edx
0x1001bbbe  pop     esi
0x1001bbbf  pop     ebp
0x1001bbc0  retn    8
```
