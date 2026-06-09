# CipAllocateValidationContext

- ea: `0x180099e48`
- end: `0x18009a002`
- name: `CipAllocateValidationContext`
- size: `442`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18009acb8`
- `0x1800e5a50`

## callees

- `0x18005bec0`
- `0x180099118`
- `0x180099e48`
- `0x18009a008`
- `0x18009a168`

## import_xrefs

- `ntoskrnl!RtlImageNtHeaderEx` at `0x180099f10`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x180099f10`

## pseudocode

```c
__int64 __fastcall CipAllocateValidationContext(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        void *a4,
        unsigned int Size,
        __int64 a6,
        _DWORD *a7,
        __int64 a8,
        PVOID *a9)
{
  unsigned int v11; // r15d
  NTSTATUS v12; // esi
  _BYTE *v13; // r14
  char ShouldImageBeForwardedToHvci; // al
  char v15; // bl
  WORD Machine; // cx
  bool v18; // al
  PVOID Entry; // [rsp+38h] [rbp-50h] BYREF
  PIMAGE_NT_HEADERS NtHeader; // [rsp+40h] [rbp-48h] BYREF

  v11 = a1;
  Entry = 0;
  NtHeader = 0;
  if ( !g_HvciSupported )
    return CipAllocateLocalValidationContext(a1, a6, a8, a3, a9);
  v12 = CipAllocateLocalValidationContext(a1, a6, a8, a3, &Entry);
  if ( v12 >= 0 )
  {
    v13 = Entry;
    ShouldImageBeForwardedToHvci = CipShouldImageBeForwardedToHvci(v11, a2, (char *)Entry + 3304);
    v15 = ShouldImageBeForwardedToHvci;
    if ( !ShouldImageBeForwardedToHvci && !v13[3304] )
      goto LABEL_5;
    if ( ShouldImageBeForwardedToHvci && a7 && (*a7 & 2) == 0 )
    {
      v12 = -1073741755;
      goto LABEL_6;
    }
    v12 = RtlImageNtHeaderEx(0, a4, Size, &NtHeader);
    if ( v12 >= 0 )
    {
      Machine = NtHeader->FileHeader.Machine;
      v18 = Machine != 0x8664u;
      if ( v15 && Machine == 332 )
        v18 = 0;
      if ( v18 )
      {
        v13[3304] = 0;
      }
      else if ( v15 )
      {
        v12 = CiHvciSetValidationContextForHvci(Entry, v11, a4, Size);
        if ( v12 < 0 )
          goto LABEL_6;
      }
LABEL_5:
      *a9 = Entry;
      Entry = 0;
    }
  }
LABEL_6:
  if ( Entry )
    CiFreeValidationContext((void (***)(void))Entry);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180099e48  mov     r11, rsp
0x180099e4b  push    rbx
0x180099e4c  push    rsi
0x180099e4d  push    rdi
0x180099e4e  push    r12
0x180099e50  push    r14
0x180099e52  push    r15
0x180099e54  sub     rsp, 58h
0x180099e58  mov     r12, r9
0x180099e5b  mov     ebx, edx
0x180099e5d  mov     r15d, ecx
0x180099e60  xor     edi, edi
0x180099e62  mov     [r11-50h], rdi
0x180099e66  mov     [r11-48h], rdi
0x180099e6a  mov     r9, r8
0x180099e6d  mov     rdx, [rsp+88h+arg_28]
0x180099e75  mov     r8, [rsp+88h+arg_38]
0x180099e7d  cmp     cs:g_HvciSupported, dil
0x180099e84  jz      loc_180099FA3
0x180099e8a  lea     rax, [r11-50h]
0x180099e8e  mov     [r11-68h], rax
0x180099e92  call    CipAllocateLocalValidationContext
0x180099e97  mov     esi, eax
0x180099e99  test    eax, eax
0x180099e9b  js      short loc_180099ED7
0x180099e9d  mov     r14, [rsp+88h+Entry]
0x180099ea2  lea     r8, [r14+0CE8h]
0x180099ea9  mov     edx, ebx
0x180099eab  mov     ecx, r15d
0x180099eae  call    CipShouldImageBeForwardedToHvci
0x180099eb3  mov     bl, al
0x180099eb5  test    al, al
0x180099eb7  jnz     short loc_180099EF6
0x180099eb9  cmp     [r14+0CE8h], dil
0x180099ec0  jnz     short loc_180099EF6
0x180099ec2  mov     rcx, [rsp+88h+arg_40]
0x180099eca  mov     rax, [rsp+88h+Entry]
0x180099ecf  mov     [rcx], rax
0x180099ed2  mov     [rsp+88h+Entry], rdi
0x180099ed7  mov     rcx, [rsp+88h+Entry]; Entry
0x180099edc  test    rcx, rcx
0x180099edf  jnz     loc_180099FF8
0x180099ee5  mov     eax, esi
0x180099ee7  add     rsp, 58h
0x180099eeb  pop     r15
0x180099eed  pop     r14
0x180099eef  pop     r12
0x180099ef1  pop     rdi
0x180099ef2  pop     rsi
0x180099ef3  pop     rbx
0x180099ef4  retn
0x180099ef6  test    bl, bl
0x180099ef8  jnz     loc_180099FC6
0x180099efe  mov     r8d, dword ptr [rsp+88h+Size]; Size
0x180099f06  lea     r9, [rsp+88h+NtHeader]; NtHeader
0x180099f0b  mov     rdx, r12; BaseAddress
0x180099f0e  xor     ecx, ecx; Flags
0x180099f10  call    cs:__imp_RtlImageNtHeaderEx
0x180099f17  nop     dword ptr [rax+rax+00h]
0x180099f1c  mov     esi, eax
0x180099f1e  mov     [rsp+88h+var_54], eax
0x180099f22  test    eax, eax
0x180099f24  js      short loc_180099ED7
0x180099f26  mov     rax, [rsp+88h+NtHeader]
0x180099f2b  movzx   ecx, word ptr [rax+4]
0x180099f2f  movzx   eax, dil
0x180099f33  mov     edx, 8664h
0x180099f38  mov     r9d, 1
0x180099f3e  cmp     cx, dx
0x180099f41  cmovnz  eax, r9d
0x180099f45  mov     [rsp+88h+var_58], al
0x180099f49  movzx   edx, dil
0x180099f4d  mov     r8d, 14Ch
0x180099f53  cmp     cx, r8w
0x180099f57  cmovz   edx, r9d
0x180099f5b  mov     [rsp+88h+var_57], dl
0x180099f5f  jmp     short loc_180099F6C
0x180099f61  mov     esi, eax
0x180099f63  mov     [rsp+88h+var_54], eax
0x180099f67  jmp     loc_180099ED7
0x180099f6c  test    bl, bl
0x180099f6e  jnz     short loc_180099FEB
0x180099f70  test    al, al
0x180099f72  jnz     short loc_180099FBA
0x180099f74  test    bl, bl
0x180099f76  jz      loc_180099EC2
0x180099f7c  mov     r9d, dword ptr [rsp+88h+Size]
0x180099f84  mov     r8, r12
0x180099f87  mov     edx, r15d
0x180099f8a  mov     rcx, [rsp+88h+Entry]
0x180099f8f  call    CiHvciSetValidationContextForHvci
0x180099f94  mov     esi, eax
0x180099f96  test    eax, eax
0x180099f98  jns     loc_180099EC2
0x180099f9e  jmp     loc_180099ED7
0x180099fa3  mov     rax, [rsp+88h+arg_40]
0x180099fab  mov     [rsp+88h+var_68], rax
0x180099fb0  call    CipAllocateLocalValidationContext
0x180099fb5  jmp     loc_180099EE7
0x180099fba  mov     [r14+0CE8h], dil
0x180099fc1  jmp     loc_180099EC2
0x180099fc6  mov     rax, [rsp+88h+arg_30]
0x180099fce  test    rax, rax
0x180099fd1  jz      loc_180099EFE
0x180099fd7  mov     eax, [rax]
0x180099fd9  test    al, 2
0x180099fdb  jnz     loc_180099EFE
0x180099fe1  mov     esi, 0C0000045h
0x180099fe6  jmp     loc_180099ED7
0x180099feb  movzx   eax, al
0x180099fee  test    dl, dl
0x180099ff0  cmovnz  eax, edi
0x180099ff3  jmp     loc_180099F70
0x180099ff8  call    CiFreeValidationContext
0x180099ffd  jmp     loc_180099EE5
```
