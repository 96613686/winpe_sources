# RasAuthAttributeGet

- ea: `0x18001ae70`
- end: `0x18001ae93`
- name: `RasAuthAttributeGet`
- size: `35`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18000380c`
- `0x180012d54`
- `0x180012e38`
- `0x18001427c`
- `0x1800181b0`
- `0x18001a254`
- `0x18001b3d0`
- `0x18001c310`
- `0x18002787c`

## callees

- `0x18001ae70`

## pseudocode

```c
_DWORD *__fastcall RasAuthAttributeGet(int a1, __int64 a2)
{
  unsigned int i; // r8d
  _DWORD *result; // rax

  if ( a2 )
  {
    for ( i = 0; ; ++i )
    {
      result = (_DWORD *)(a2 + 16LL * i);
      if ( !*result )
        break;
      if ( *result == a1 )
        return result;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001ae70  test    rdx, rdx
0x18001ae73  jz      short loc_18001AE90
0x18001ae75  xor     r8d, r8d
0x18001ae78  mov     eax, r8d
0x18001ae7b  shl     rax, 4
0x18001ae7f  add     rax, rdx
0x18001ae82  cmp     dword ptr [rax], 0
0x18001ae85  jz      short loc_18001AE90
0x18001ae87  cmp     [rax], ecx
0x18001ae89  jz      short locret_18001AE92
0x18001ae8b  inc     r8d
0x18001ae8e  jmp     short loc_18001AE78
0x18001ae90  xor     eax, eax
0x18001ae92  retn
```
