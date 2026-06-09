# CCMLuaUtil::DeleteRegKeysWithoutSubKeys(int,ushort const *,int)

- ea: `0x180003200`
- end: `0x180003232`
- name: `?DeleteRegKeysWithoutSubKeys@CCMLuaUtil@@UEAAJHPEBGH@Z`
- size: `50`
- prototype: `__int64 __fastcall(CCMLuaUtil *this, int, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800026b0`
- `0x180003200`

## pseudocode

```c
__int64 __fastcall CCMLuaUtil::DeleteRegKeysWithoutSubKeys(
        CCMLuaUtil *this,
        int a2,
        const unsigned __int16 *a3,
        int a4)
{
  __int64 result; // rax

  result = CmDeleteRegKeyWithoutSubKeys((HKEY)((a2 != 0) - 0x7FFFFFFFLL), a3, a4);
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180003200  sub     rsp, 28h
0x180003204  neg     edx
0x180003206  mov     rax, r8
0x180003209  mov     r8d, r9d; int
0x18000320c  mov     rdx, rax; unsigned __int16 *
0x18000320f  sbb     rcx, rcx
0x180003212  neg     rcx
0x180003215  add     rcx, 0FFFFFFFF80000001h; hKey
0x18000321c  call    ?CmDeleteRegKeyWithoutSubKeys@@YAJPEAUHKEY__@@PEBGH@Z; CmDeleteRegKeyWithoutSubKeys(HKEY__ *,ushort const *,int)
0x180003221  test    eax, eax
0x180003223  jle     short loc_18000322D
0x180003225  movzx   eax, ax
0x180003228  or      eax, 80070000h
0x18000322d  add     rsp, 28h
0x180003231  retn
```
