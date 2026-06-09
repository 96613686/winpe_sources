# DiskReadSmartLog

- ea: `0x140010f3c`
- end: `0x140011002`
- name: `DiskReadSmartLog`
- size: `198`
- prototype: `__int64 __fastcall(__int64, unsigned __int8, char, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140010490`

## callees

- `0x140005d00`
- `0x140010f3c`
- `0x140012810`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140010fdf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010fdf`
- `ntoskrnl!ExAllocatePool2` at `0x140010f83`
- `ntoskrnl!ExAllocatePool2` at `0x140010f83`

## pseudocode

```c
__int64 __fastcall DiskReadSmartLog(__int64 a1, unsigned __int8 a2, char a3, void *a4)
{
  unsigned int v7; // esi
  unsigned __int64 v8; // rax
  char *Buffer; // rdi
  NTSTATUS v11; // ebx
  __int64 v13; // [rsp+88h] [rbp+10h] BYREF

  v7 = a2 << 9;
  v8 = v7 + 16LL;
  if ( v8 < 0x21 )
    LODWORD(v8) = 33;
  LODWORD(v13) = v8 + 28;
  Buffer = (char *)ExAllocatePool2(64, (unsigned int)(v8 + 28), 1631871827);
  if ( Buffer )
  {
    v11 = DiskPerformSmartCommand(a1, 1770763, 176, 213, a2, a3, Buffer, (int *)&v13);
    if ( v11 >= 0 )
      memmove(a4, Buffer + 44, v7);
    ExFreePoolWithTag(Buffer, 0);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140010f3c  push    rbx
0x140010f3e  push    rbp
0x140010f3f  push    rsi
0x140010f40  push    rdi
0x140010f41  push    r14
0x140010f43  push    r15
0x140010f45  sub     rsp, 48h
0x140010f49  movzx   ebx, dl
0x140010f4c  mov     r15, rcx
0x140010f4f  mov     ecx, 21h ; '!'
0x140010f54  mov     eax, ebx
0x140010f56  shl     eax, 9
0x140010f59  mov     r14b, r8b
0x140010f5c  mov     esi, eax
0x140010f5e  mov     r8d, 61446353h
0x140010f64  add     rax, 10h
0x140010f68  mov     rbp, r9
0x140010f6b  cmp     rax, rcx
0x140010f6e  cmovb   rax, rcx
0x140010f72  mov     ecx, 40h ; '@'
0x140010f77  add     eax, 1Ch
0x140010f7a  mov     edx, eax
0x140010f7c  mov     dword ptr [rsp+78h+arg_8], eax
0x140010f83  call    cs:__imp_ExAllocatePool2
0x140010f8a  nop     dword ptr [rax+rax+00h]
0x140010f8f  mov     rdi, rax
0x140010f92  test    rax, rax
0x140010f95  jz      short loc_140010FED
0x140010f97  lea     rax, [rsp+78h+arg_8]
0x140010f9f  mov     r9b, 0D5h; int
0x140010fa2  mov     [rsp+78h+var_40], rax; __int64
0x140010fa7  mov     r8b, 0B0h; int
0x140010faa  mov     [rsp+78h+Buffer], rdi; Buffer
0x140010faf  mov     edx, 1B050Bh; int
0x140010fb4  mov     [rsp+78h+var_50], r14b; char
0x140010fb9  mov     rcx, r15; int
0x140010fbc  mov     [rsp+78h+var_58], bl; char
0x140010fc0  call    DiskPerformSmartCommand
0x140010fc5  mov     ebx, eax
0x140010fc7  test    eax, eax
0x140010fc9  js      short loc_140010FDA
0x140010fcb  lea     rdx, [rdi+2Ch]; Src
0x140010fcf  mov     r8d, esi; Size
0x140010fd2  mov     rcx, rbp; void *
0x140010fd5  call    memmove
0x140010fda  xor     edx, edx; Tag
0x140010fdc  mov     rcx, rdi; P
0x140010fdf  call    cs:__imp_ExFreePoolWithTag
0x140010fe6  nop     dword ptr [rax+rax+00h]
0x140010feb  jmp     short loc_140010FF2
0x140010fed  mov     ebx, 0C000009Ah
0x140010ff2  mov     eax, ebx
0x140010ff4  add     rsp, 48h
0x140010ff8  pop     r15
0x140010ffa  pop     r14
0x140010ffc  pop     rdi
0x140010ffd  pop     rsi
0x140010ffe  pop     rbp
0x140010fff  pop     rbx
0x140011000  retn
```
