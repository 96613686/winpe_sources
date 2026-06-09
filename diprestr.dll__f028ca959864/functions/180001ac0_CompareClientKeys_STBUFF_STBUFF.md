# CompareClientKeys(STBUFF *,STBUFF *)

- ea: `0x180001ac0`
- end: `0x180001aee`
- name: `?CompareClientKeys@@YAHPEAVSTBUFF@@0@Z`
- size: `46`
- prototype: `__int64 __fastcall(struct STBUFF *, struct STBUFF *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001ac0`
- `0x180006776`

## pseudocode

```c
_BOOL8 __fastcall CompareClientKeys(struct STBUFF *a1, struct STBUFF *a2)
{
  return *((_DWORD *)a1 + 4) == *((_DWORD *)a2 + 4)
      && memcmp_0(*((const void **)a1 + 1), *((const void **)a2 + 1), *((unsigned int *)a1 + 4)) == 0;
}

```

## disassembly

```asm
0x180001ac0  sub     rsp, 28h
0x180001ac4  mov     eax, [rcx+10h]
0x180001ac7  cmp     eax, [rdx+10h]
0x180001aca  jz      short loc_180001AD0
0x180001acc  xor     eax, eax
0x180001ace  jmp     short loc_180001AE9
0x180001ad0  mov     rdx, [rdx+8]; Buf2
0x180001ad4  mov     r8, rax; Size
0x180001ad7  mov     rcx, [rcx+8]; Buf1
0x180001adb  call    memcmp_0
0x180001ae0  xor     ecx, ecx
0x180001ae2  test    eax, eax
0x180001ae4  setz    cl
0x180001ae7  mov     eax, ecx
0x180001ae9  add     rsp, 28h
0x180001aed  retn
```
