# CheckForRpcRetry(long)

- ea: `0x180001ae0`
- end: `0x180001b14`
- name: `?CheckForRpcRetry@@YAHJ@Z`
- size: `52`
- prototype: `_BOOL8 __fastcall(int)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015a0`
- `0x180001810`
- `0x180002060`
- `0x18000313c`
- `0x1800031d0`
- `0x1800032a0`
- `0x180003380`
- `0x180003460`

## callees

- `0x180001ae0`

## pseudocode

```c
_BOOL8 __fastcall CheckForRpcRetry(int a1)
{
  unsigned __int64 v1; // rax
  __int64 v2; // rdx
  _BOOL8 result; // rax

  v1 = (unsigned int)(a1 + 2147023194);
  result = (unsigned int)v1 <= 0x33 && (v2 = 0x8200003308001LL, _bittest64(&v2, v1))
        || a1 == -2147023121
        || a1 == -2147023071;
  return result;
}

```

## disassembly

```asm
0x180001ae0  lea     eax, [rcx+7FF8F95Ah]
0x180001ae6  cmp     eax, 33h ; '3'
0x180001ae9  ja      short loc_180001AFB
0x180001aeb  mov     rdx, 8200003308001h
0x180001af5  bt      rdx, rax
0x180001af9  jb      short loc_180001B0E
0x180001afb  cmp     ecx, 800706EFh
0x180001b01  jz      short loc_180001B0E
0x180001b03  cmp     ecx, 80070721h
0x180001b09  jz      short loc_180001B0E
0x180001b0b  xor     eax, eax
0x180001b0d  retn
0x180001b0e  mov     eax, 1
0x180001b13  retn
```
