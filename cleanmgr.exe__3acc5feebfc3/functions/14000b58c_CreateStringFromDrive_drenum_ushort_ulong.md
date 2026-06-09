# CreateStringFromDrive(drenum,ushort *,ulong)

- ea: `0x14000b58c`
- end: `0x14000b5b5`
- name: `?CreateStringFromDrive@@YAHW4drenum@@PEAGK@Z`
- size: `41`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b5bc`
- `0x14000b6dc`
- `0x14000b780`
- `0x140016f84`

## callees

- `0x14000b58c`

## pseudocode

```c
__int64 __fastcall CreateStringFromDrive(int a1, __int64 a2)
{
  if ( !a2 || a1 == 26 )
    return 0;
  *(_DWORD *)(a2 + 2) = 6029370;
  *(_WORD *)a2 = (char)(a1 + 65);
  *(_WORD *)(a2 + 6) = 0;
  return 1;
}

```

## disassembly

```asm
0x14000b58c  test    rdx, rdx
0x14000b58f  jz      short loc_14000B5B2
0x14000b591  cmp     ecx, 1Ah
0x14000b594  jz      short loc_14000B5B2
0x14000b596  add     cl, 41h ; 'A'
0x14000b599  mov     dword ptr [rdx+2], 5C003Ah
0x14000b5a0  movsx   eax, cl
0x14000b5a3  mov     [rdx], ax
0x14000b5a6  xor     eax, eax
0x14000b5a8  mov     [rdx+6], ax
0x14000b5ac  mov     eax, 1
0x14000b5b1  retn
0x14000b5b2  xor     eax, eax
0x14000b5b4  retn
```
