# TranslateLogonMethod(ulong *)

- ea: `0x180011d4c`
- end: `0x180011d88`
- name: `?TranslateLogonMethod@@YAJPEAK@Z`
- size: `60`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d340`
- `0x18000d5b8`

## callees

- `0x180011d4c`

## pseudocode

```c
__int64 __fastcall TranslateLogonMethod(unsigned int *a1)
{
  if ( *a1 )
  {
    switch ( *a1 )
    {
      case 1u:
        *a1 = 4;
        break;
      case 2u:
        *a1 = 3;
        break;
      case 3u:
        *a1 = 8;
        break;
      default:
        return 2147942487LL;
    }
  }
  else
  {
    *a1 = 2;
  }
  return 0;
}

```

## disassembly

```asm
0x180011d4c  mov     edx, [rcx]
0x180011d4e  test    edx, edx
0x180011d50  jz      short loc_180011D7F
0x180011d52  sub     edx, 1
0x180011d55  jz      short loc_180011D77
0x180011d57  sub     edx, 1
0x180011d5a  jz      short loc_180011D6F
0x180011d5c  cmp     edx, 1
0x180011d5f  jz      short loc_180011D67
0x180011d61  mov     eax, 80070057h
0x180011d66  retn
0x180011d67  mov     dword ptr [rcx], 8
0x180011d6d  jmp     short loc_180011D85
0x180011d6f  mov     dword ptr [rcx], 3
0x180011d75  jmp     short loc_180011D85
0x180011d77  mov     dword ptr [rcx], 4
0x180011d7d  jmp     short loc_180011D85
0x180011d7f  mov     dword ptr [rcx], 2
0x180011d85  xor     eax, eax
0x180011d87  retn
```
