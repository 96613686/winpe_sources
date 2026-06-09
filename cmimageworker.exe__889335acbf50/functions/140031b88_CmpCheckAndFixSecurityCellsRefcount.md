# CmpCheckAndFixSecurityCellsRefcount

- ea: `0x140031b88`
- end: `0x140031c3c`
- name: `CmpCheckAndFixSecurityCellsRefcount`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14002b75c`

## callees

- `0x140027730`
- `0x14002deb4`
- `0x140030f98`
- `0x140031378`
- `0x140031390`
- `0x140031b88`

## pseudocode

```c
__int64 __fastcall CmpCheckAndFixSecurityCellsRefcount(__int64 a1)
{
  unsigned int i; // edi
  __int64 v3; // r14
  unsigned int v4; // ebp
  __int64 CellFlat; // rax
  __int64 result; // rax
  int v7; // edx
  __int64 v8; // rcx
  char v9; // [rsp+40h] [rbp+8h] BYREF

  for ( i = 0; i < *(_DWORD *)(a1 + 1888); ++i )
  {
    v3 = *(_QWORD *)(a1 + 1904);
    v4 = *(_DWORD *)(v3 + 16LL * i);
    if ( (*(_BYTE *)(a1 + 140) & 1) != 0 )
      CellFlat = HvpGetCellFlat(a1, v4, &v9);
    else
      CellFlat = HvpGetCellPaged(a1, v4, &v9);
    if ( *(_DWORD *)(CellFlat + 12) != *(_DWORD *)(*(_QWORD *)(v3 + 16LL * i + 8) + 28LL) )
    {
      result = HvpAdjustHiveFreeDisplay();
      if ( (int)result < 0 )
        return result;
      *(_DWORD *)(v8 + 12) = v7;
    }
    if ( !*(_DWORD *)(*(_QWORD *)(v3 + 16LL * i + 8) + 28LL) )
    {
      result = HvpAdjustHiveFreeDisplay();
      if ( (int)result < 0 )
        return result;
      CmpRemoveSecurityCellList(a1, v4);
      HvFreeCell(a1, v4);
      --i;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140031b88  mov     [rsp+arg_8], rbx
0x140031b8d  mov     [rsp+arg_10], rbp
0x140031b92  push    rsi
0x140031b93  push    rdi
0x140031b94  push    r14
0x140031b96  sub     rsp, 20h
0x140031b9a  xor     edi, edi
0x140031b9c  mov     rbx, rcx
0x140031b9f  cmp     [rcx+760h], edi
0x140031ba5  jbe     short loc_140031C26
0x140031ba7  mov     r14, [rbx+770h]
0x140031bae  lea     r8, [rsp+38h+arg_0]
0x140031bb3  mov     esi, edi
0x140031bb5  mov     rcx, rbx
0x140031bb8  add     rsi, rsi
0x140031bbb  test    byte ptr [rbx+8Ch], 1
0x140031bc2  mov     ebp, [r14+rsi*8]
0x140031bc6  mov     edx, ebp
0x140031bc8  jz      short loc_140031BD1
0x140031bca  call    HvpGetCellFlat
0x140031bcf  jmp     short loc_140031BD6
0x140031bd1  call    HvpGetCellPaged
0x140031bd6  mov     rcx, rax
0x140031bd9  mov     rax, [r14+rsi*8+8]
0x140031bde  mov     edx, [rax+1Ch]
0x140031be1  cmp     [rcx+0Ch], edx
0x140031be4  jz      short loc_140031BF2
0x140031be6  call    HvpAdjustHiveFreeDisplay
0x140031beb  test    eax, eax
0x140031bed  js      short loc_140031C28
0x140031bef  mov     [rcx+0Ch], edx
0x140031bf2  mov     rax, [r14+rsi*8+8]
0x140031bf7  cmp     dword ptr [rax+1Ch], 0
0x140031bfb  jnz     short loc_140031C1C
0x140031bfd  call    HvpAdjustHiveFreeDisplay
0x140031c02  test    eax, eax
0x140031c04  js      short loc_140031C28
0x140031c06  mov     edx, ebp
0x140031c08  mov     rcx, rbx
0x140031c0b  call    CmpRemoveSecurityCellList
0x140031c10  mov     edx, ebp
0x140031c12  mov     rcx, rbx
0x140031c15  call    HvFreeCell
0x140031c1a  dec     edi
0x140031c1c  inc     edi
0x140031c1e  cmp     edi, [rbx+760h]
0x140031c24  jb      short loc_140031BA7
0x140031c26  xor     eax, eax
0x140031c28  mov     rbx, [rsp+38h+arg_8]
0x140031c2d  mov     rbp, [rsp+38h+arg_10]
0x140031c32  add     rsp, 20h
0x140031c36  pop     r14
0x140031c38  pop     rdi
0x140031c39  pop     rsi
0x140031c3a  retn
```
