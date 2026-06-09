# DiskWriteSmartLog

- ea: `0x140011118`
- end: `0x1400111c9`
- name: `DiskWriteSmartLog`
- size: `177`
- prototype: `__int64 __fastcall(__int64, unsigned __int8, char, const void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140010490`

## callees

- `0x140005d00`
- `0x140011118`
- `0x140012810`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400111a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400111a6`
- `ntoskrnl!ExAllocatePool2` at `0x14001114d`
- `ntoskrnl!ExAllocatePool2` at `0x14001114d`

## pseudocode

```c
__int64 __fastcall DiskWriteSmartLog(__int64 a1, unsigned __int8 a2, char a3, const void *a4)
{
  unsigned int v7; // ebx
  __int64 Pool2; // rax
  char *Buffer; // rdi
  unsigned int v11; // ebx
  __int64 v13; // [rsp+88h] [rbp+10h] BYREF

  v7 = a2 << 9;
  LODWORD(v13) = v7 + 60;
  Pool2 = ExAllocatePool2(64, v7 + 60, 1631871827);
  Buffer = (char *)Pool2;
  if ( Pool2 )
  {
    memmove((void *)(Pool2 + 60), a4, v7);
    v11 = DiskPerformSmartCommand(a1, 1770764, 176, 214, a2, a3, Buffer, (int *)&v13);
    ExFreePoolWithTag(Buffer, 0);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v11;
}

```

## disassembly

```asm
0x140011118  push    rbx
0x14001111a  push    rbp
0x14001111b  push    rsi
0x14001111c  push    rdi
0x14001111d  push    r14
0x14001111f  push    r15
0x140011121  sub     rsp, 48h
0x140011125  movzx   esi, dl
0x140011128  mov     r14b, r8b
0x14001112b  mov     r15, rcx
0x14001112e  mov     ebx, esi
0x140011130  shl     ebx, 9
0x140011133  mov     ecx, 40h ; '@'
0x140011138  mov     r8d, 61446353h
0x14001113e  mov     rbp, r9
0x140011141  lea     eax, [rbx+3Ch]
0x140011144  mov     edx, eax
0x140011146  mov     dword ptr [rsp+78h+arg_8], eax
0x14001114d  call    cs:__imp_ExAllocatePool2
0x140011154  nop     dword ptr [rax+rax+00h]
0x140011159  mov     rdi, rax
0x14001115c  test    rax, rax
0x14001115f  jz      short loc_1400111B4
0x140011161  mov     r8d, ebx; Size
0x140011164  lea     rcx, [rax+3Ch]; void *
0x140011168  mov     rdx, rbp; Src
0x14001116b  call    memmove
0x140011170  lea     rax, [rsp+78h+arg_8]
0x140011178  mov     r9b, 0D6h; int
0x14001117b  mov     [rsp+78h+var_40], rax; __int64
0x140011180  mov     r8b, 0B0h; int
0x140011183  mov     [rsp+78h+Buffer], rdi; Buffer
0x140011188  mov     edx, 1B050Ch; int
0x14001118d  mov     [rsp+78h+var_50], r14b; char
0x140011192  mov     rcx, r15; int
0x140011195  mov     [rsp+78h+var_58], sil; char
0x14001119a  call    DiskPerformSmartCommand
0x14001119f  xor     edx, edx; Tag
0x1400111a1  mov     rcx, rdi; P
0x1400111a4  mov     ebx, eax
0x1400111a6  call    cs:__imp_ExFreePoolWithTag
0x1400111ad  nop     dword ptr [rax+rax+00h]
0x1400111b2  jmp     short loc_1400111B9
0x1400111b4  mov     ebx, 0C000009Ah
0x1400111b9  mov     eax, ebx
0x1400111bb  add     rsp, 48h
0x1400111bf  pop     r15
0x1400111c1  pop     r14
0x1400111c3  pop     rdi
0x1400111c4  pop     rsi
0x1400111c5  pop     rbp
0x1400111c6  pop     rbx
0x1400111c7  retn
```
