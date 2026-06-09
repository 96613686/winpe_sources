# LmpMapFile

- ea: `0x14004e8bc`
- end: `0x14004ea41`
- name: `LmpMapFile`
- size: `389`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14004de44`

## callees

- `0x140030f40`
- `0x1400400a4`
- `0x14004e8bc`

## import_xrefs

- `ntoskrnl!ZwQueryInformationFile` at `0x14004e914`
- `ntoskrnl!ZwQueryInformationFile` at `0x14004e914`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e9c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e9c3`
- `ntoskrnl!ZwReadFile` at `0x14004e999`
- `ntoskrnl!ZwReadFile` at `0x14004e999`
- `ntoskrnl!ExAllocatePool2` at `0x14004e954`
- `ntoskrnl!ExAllocatePool2` at `0x14004e954`

## pseudocode

```c
void *__fastcall LmpMapFile(HANDLE FileHandle, ULONG *a2)
{
  unsigned int v4; // eax
  ULONG Length; // ebx
  void *Buffer; // rdi
  unsigned int v7; // eax
  unsigned int v8; // esi
  union _LARGE_INTEGER ByteOffset; // [rsp+50h] [rbp-58h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-50h] BYREF
  ULONG v12[4]; // [rsp+68h] [rbp-40h] BYREF
  __int64 v13; // [rsp+78h] [rbp-30h]

  ByteOffset.QuadPart = 0;
  *(_OWORD *)v12 = 0;
  v13 = 0;
  IoStatusBlock = 0;
  v4 = ZwQueryInformationFile(FileHandle, &IoStatusBlock, v12, 0x18u, FileStandardInformation);
  if ( v4 )
  {
    if ( SBYTE1(xmmword_140038420) < 0 )
      WPP_SF_d(1039, 11, WPP_1dea4ad0a30639a494f955885f716115_Traceguids, v4);
  }
  else
  {
    Length = v12[2];
    if ( (unsigned __int64)(v12[2] + 2) >= *(_QWORD *)&v12[2] )
    {
      Buffer = (void *)ExAllocatePool2(64, v12[2] + 2, 942760526);
      if ( !Buffer )
        return Buffer;
      v7 = ZwReadFile(FileHandle, 0, 0, 0, &IoStatusBlock, Buffer, Length, &ByteOffset, 0);
      v8 = v7;
      if ( v7 && SBYTE1(xmmword_140038420) < 0 )
        WPP_SF_d(1039, 12, WPP_1dea4ad0a30639a494f955885f716115_Traceguids, v7);
      if ( !IoStatusBlock.Status && !v8 )
      {
        *a2 = Length;
        return Buffer;
      }
      ExFreePoolWithTag(Buffer, 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14004e8bc  mov     r11, rsp
0x14004e8bf  mov     [r11+18h], rbx
0x14004e8c3  push    rsi
0x14004e8c4  push    rdi
0x14004e8c5  push    r14
0x14004e8c7  sub     rsp, 90h
0x14004e8ce  mov     rax, cs:__security_cookie
0x14004e8d5  xor     rax, rsp
0x14004e8d8  mov     [rsp+0A8h+var_28], rax
0x14004e8e0  xor     eax, eax
0x14004e8e2  mov     [rsp+0A8h+FileInformationClass], 5; FileInformationClass
0x14004e8ea  xorps   xmm1, xmm1
0x14004e8ed  mov     [r11-58h], rax
0x14004e8f1  mov     r14, rdx
0x14004e8f4  lea     r8, [r11-40h]; FileInformation
0x14004e8f8  xorps   xmm0, xmm0
0x14004e8fb  lea     rdx, [r11-50h]; IoStatusBlock
0x14004e8ff  movups  xmmword ptr [rsp+0A8h+var_40], xmm1
0x14004e904  lea     r9d, [rax+18h]; Length
0x14004e908  mov     [r11-30h], rax
0x14004e90c  mov     rsi, rcx
0x14004e90f  movups  xmmword ptr [rsp+0A8h+IoStatusBlock], xmm0
0x14004e914  call    cs:__imp_ZwQueryInformationFile
0x14004e91b  nop     dword ptr [rax+rax+00h]
0x14004e920  test    eax, eax
0x14004e922  jnz     loc_14004E9F6
0x14004e928  mov     rbx, qword ptr [rsp+0A8h+var_40+8]
0x14004e92d  mov     rax, rbx
0x14004e930  shr     rax, 20h
0x14004e934  test    eax, eax
0x14004e936  jnz     loc_14004E9CF
0x14004e93c  lea     eax, [rbx+2]
0x14004e93f  cmp     eax, ebx
0x14004e941  jb      loc_14004E9CF
0x14004e947  mov     edx, eax
0x14004e949  mov     ecx, 40h ; '@'
0x14004e94e  mov     r8d, 3831624Eh
0x14004e954  call    cs:__imp_ExAllocatePool2
0x14004e95b  nop     dword ptr [rax+rax+00h]
0x14004e960  mov     rdi, rax
0x14004e963  test    rax, rax
0x14004e966  jz      short loc_14004E9B9
0x14004e968  mov     [rsp+0A8h+Key], 0; Key
0x14004e971  lea     rax, [rsp+0A8h+var_58]
0x14004e976  mov     [rsp+0A8h+ByteOffset], rax; ByteOffset
0x14004e97b  xor     r9d, r9d; ApcContext
0x14004e97e  mov     [rsp+0A8h+Length], ebx; Length
0x14004e982  lea     rax, [rsp+0A8h+IoStatusBlock]
0x14004e987  mov     [rsp+0A8h+Buffer], rdi; Buffer
0x14004e98c  xor     r8d, r8d; ApcRoutine
0x14004e98f  xor     edx, edx; Event
0x14004e991  mov     qword ptr [rsp+0A8h+FileInformationClass], rax; IoStatusBlock
0x14004e996  mov     rcx, rsi; FileHandle
0x14004e999  call    cs:__imp_ZwReadFile
0x14004e9a0  nop     dword ptr [rax+rax+00h]
0x14004e9a5  mov     esi, eax
0x14004e9a7  test    eax, eax
0x14004e9a9  jnz     short loc_14004EA1A
0x14004e9ab  cmp     dword ptr [rsp+0A8h+IoStatusBlock], 0
0x14004e9b0  jnz     short loc_14004E9BE
0x14004e9b2  test    esi, esi
0x14004e9b4  jnz     short loc_14004E9BE
0x14004e9b6  mov     [r14], ebx
0x14004e9b9  mov     rax, rdi
0x14004e9bc  jmp     short loc_14004E9D1
0x14004e9be  xor     edx, edx; Tag
0x14004e9c0  mov     rcx, rdi; P
0x14004e9c3  call    cs:__imp_ExFreePoolWithTag
0x14004e9ca  nop     dword ptr [rax+rax+00h]
0x14004e9cf  xor     eax, eax
0x14004e9d1  mov     rcx, [rsp+0A8h+var_28]
0x14004e9d9  xor     rcx, rsp; StackCookie
0x14004e9dc  call    __security_check_cookie
0x14004e9e1  mov     rbx, [rsp+0A8h+arg_10]
0x14004e9e9  add     rsp, 90h
0x14004e9f0  pop     r14
0x14004e9f2  pop     rdi
0x14004e9f3  pop     rsi
0x14004e9f4  retn
0x14004e9f6  cmp     byte ptr cs:xmmword_140038420+1, 0
0x14004e9fd  jge     short loc_14004E9CF
0x14004e9ff  mov     edx, 0Bh
0x14004ea04  lea     r8, WPP_1dea4ad0a30639a494f955885f716115_Traceguids
0x14004ea0b  mov     ecx, 40Fh
0x14004ea10  mov     r9d, eax
0x14004ea13  call    WPP_SF_d
0x14004ea18  jmp     short loc_14004E9CF
0x14004ea1a  cmp     byte ptr cs:xmmword_140038420+1, 0
0x14004ea21  jge     short loc_14004E9AB
0x14004ea23  mov     edx, 0Ch
0x14004ea28  lea     r8, WPP_1dea4ad0a30639a494f955885f716115_Traceguids
0x14004ea2f  mov     ecx, 40Fh
0x14004ea34  mov     r9d, esi
0x14004ea37  call    WPP_SF_d
0x14004ea3c  jmp     loc_14004E9AB
```
