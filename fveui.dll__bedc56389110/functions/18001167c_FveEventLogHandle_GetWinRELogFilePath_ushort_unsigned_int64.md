# FveEventLogHandle::GetWinRELogFilePath(ushort *,unsigned __int64)

- ea: `0x18001167c`
- end: `0x1800116ed`
- name: `?GetWinRELogFilePath@FveEventLogHandle@@SAJPEAG_K@Z`
- size: `113`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180011978`

## callees

- `0x1800022d8`
- `0x18000b9f8`
- `0x18001167c`
- `0x1800128ac`

## pseudocode

```c
__int64 __fastcall FveEventLogHandle::GetWinRELogFilePath(unsigned __int16 *a1, unsigned __int16 **a2)
{
  int AssociatedOsInfo; // ebx
  void *Block; // [rsp+48h] [rbp+10h] BYREF

  Block = 0;
  AssociatedOsInfo = FveBcdUtil::GetAssociatedOsInfo((struct _BCDE_DEVICE **)&Block, a2);
  if ( AssociatedOsInfo >= 0 )
    AssociatedOsInfo = StringCchPrintfW(
                         a1,
                         0x104u,
                         L"\\\\?\\GLOBALROOT%s\\%s",
                         (char *)Block + 20,
                         L"BitLockerWinRELog.etl");
  if ( Block )
    operator delete(Block);
  return (unsigned int)AssociatedOsInfo;
}

```

## disassembly

```asm
0x18001167c  mov     rax, rsp
0x18001167f  mov     [rax+8], rbx
0x180011683  mov     [rax+10h], rdx
0x180011687  push    rdi
0x180011688  sub     rsp, 30h
0x18001168c  mov     rdi, rcx
0x18001168f  mov     qword ptr [rax+10h], 0
0x180011697  lea     rcx, [rax+10h]; struct _BCDE_DEVICE **
0x18001169b  call    ?GetAssociatedOsInfo@FveBcdUtil@@SAJPEAPEAU_BCDE_DEVICE@@PEAPEAG@Z; FveBcdUtil::GetAssociatedOsInfo(_BCDE_DEVICE * *,ushort * *)
0x1800116a0  mov     ebx, eax
0x1800116a2  test    eax, eax
0x1800116a4  js      short loc_1800116D1
0x1800116a6  mov     r9, [rsp+38h+Block]
0x1800116ab  add     r9, 14h
0x1800116af  lea     rax, aBitlockerwinre_0; "BitLockerWinRELog.etl"
0x1800116b6  mov     [rsp+38h+var_18], rax
0x1800116bb  lea     r8, aGlobalrootSS; "\\\\?\\GLOBALROOT%s\\%s"
0x1800116c2  mov     edx, 104h; unsigned __int64
0x1800116c7  mov     rcx, rdi; unsigned __int16 *
0x1800116ca  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800116cf  mov     ebx, eax
0x1800116d1  mov     rcx, [rsp+38h+Block]; Block
0x1800116d6  test    rcx, rcx
0x1800116d9  jz      short loc_1800116E0
0x1800116db  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800116e0  mov     eax, ebx
0x1800116e2  mov     rbx, [rsp+38h+arg_0]
0x1800116e7  add     rsp, 30h
0x1800116eb  pop     rdi
0x1800116ec  retn
0x18002c7ac  push    rbp
0x18002c7ae  sub     rsp, 30h
0x18002c7b2  mov     rbp, rdx
0x18002c7b5  mov     rcx, [rbp+48h]; Block
0x18002c7b9  test    rcx, rcx
0x18002c7bc  jz      short loc_18002C7C4
0x18002c7be  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c7c3  nop
0x18002c7c4  add     rsp, 30h
0x18002c7c8  pop     rbp
0x18002c7c9  retn
```
