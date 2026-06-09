# NTGetLmHostPath

- ea: `0x14004b55c`
- end: `0x14004b6fd`
- name: `NTGetLmHostPath`
- size: `417`
- prototype: `__int64 __fastcall(PCHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14004b48c`

## callees

- `0x140030e76`
- `0x140031140`
- `0x140048958`
- `0x14004b55c`

## import_xrefs

- `ntoskrnl!RtlInitString` at `0x14004b652`
- `ntoskrnl!RtlInitString` at `0x14004b652`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14004b60c`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14004b60c`
- `ntoskrnl!RtlAppendStringToString` at `0x14004b666`
- `ntoskrnl!RtlAppendStringToString` at `0x14004b666`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b620`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b636`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b6e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b620`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b636`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b6e5`
- `ntoskrnl!ExAllocatePool2` at `0x14004b5da`
- `ntoskrnl!ExAllocatePool2` at `0x14004b5da`

## pseudocode

```c
__int64 __fastcall NTGetLmHostPath(PCHAR *a1)
{
  CHAR *Pool2; // rax
  NTSTATUS v4; // ebx
  NTSTATUS appended; // edi
  PCHAR Buffer; // rbx
  struct _STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF
  UNICODE_STRING SourceString; // [rsp+30h] [rbp-28h] BYREF
  STRING Source; // [rsp+40h] [rbp-18h] BYREF

  *a1 = 0;
  SourceString = 0;
  DestinationString = 0;
  Source = 0;
  if ( (int)ReadStringRelative(&stru_1400394D0, L"TcpIp\\Parameters") < 0
    && (int)ReadStringRelative(&stru_1400394D0, L"Tcp\\Parameters") < 0 )
  {
    return 3221225473LL;
  }
  Pool2 = (CHAR *)ExAllocatePool2(64, (SourceString.Length >> 1) + 9, 926114382);
  if ( !Pool2 )
    return 3221225626LL;
  DestinationString.Buffer = Pool2;
  DestinationString.MaximumLength = (SourceString.Length >> 1) + 9;
  DestinationString.Length = DestinationString.MaximumLength;
  v4 = RtlUnicodeStringToAnsiString(&DestinationString, &SourceString, 0);
  ExFreePoolWithTag(SourceString.Buffer, 0);
  if ( v4 < 0 )
  {
    ExFreePoolWithTag(DestinationString.Buffer, 0);
    return 3221225473LL;
  }
  RtlInitString(&Source, "\\lmhosts");
  appended = RtlAppendStringToString(&DestinationString, &Source);
  if ( appended < 0 )
  {
    ExFreePoolWithTag(DestinationString.Buffer, 0);
  }
  else
  {
    Buffer = DestinationString.Buffer;
    if ( !strncmp_0(DestinationString.Buffer, "%SystemRoot%", 0xCu) )
    {
      *Buffer = 92;
      DestinationString.Buffer[11] = 92;
      Buffer = DestinationString.Buffer;
      if ( DestinationString.Buffer[12] == 92 && DestinationString.Length > 0xDu )
      {
        memmove(
          DestinationString.Buffer + 12,
          DestinationString.Buffer + 13,
          (unsigned int)DestinationString.Length - 13);
        DestinationString.Buffer[DestinationString.Length - 1] = 0;
        Buffer = DestinationString.Buffer;
      }
    }
    *a1 = Buffer;
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14004b55c  push    rbp
0x14004b55e  push    rbx
0x14004b55f  push    rsi
0x14004b560  push    rdi
0x14004b561  mov     rbp, rsp
0x14004b564  sub     rsp, 58h
0x14004b568  xorps   xmm0, xmm0
0x14004b56b  mov     qword ptr [rcx], 0
0x14004b572  mov     rsi, rcx
0x14004b575  lea     r9, [rbp+SourceString]
0x14004b579  xorps   xmm1, xmm1
0x14004b57c  lea     rcx, stru_1400394D0; SourceString
0x14004b583  lea     rdx, aTcpipParameter; "TcpIp\\Parameters"
0x14004b58a  movups  xmmword ptr [rbp+SourceString.Length], xmm0
0x14004b58e  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x14004b592  movups  xmmword ptr [rbp+Source.Length], xmm0
0x14004b596  call    ReadStringRelative
0x14004b59b  test    eax, eax
0x14004b59d  jns     short loc_14004B5C4
0x14004b59f  lea     r9, [rbp+SourceString]
0x14004b5a3  lea     rdx, aTcpParameters; "Tcp\\Parameters"
0x14004b5aa  lea     rcx, stru_1400394D0; SourceString
0x14004b5b1  call    ReadStringRelative
0x14004b5b6  test    eax, eax
0x14004b5b8  jns     short loc_14004B5C4
0x14004b5ba  mov     eax, 0C0000001h
0x14004b5bf  jmp     loc_14004B6F3
0x14004b5c4  movzx   ebx, [rbp+SourceString.Length]
0x14004b5c8  mov     ecx, 40h ; '@'
0x14004b5cd  shr     ebx, 1
0x14004b5cf  mov     r8d, 3733624Eh
0x14004b5d5  add     ebx, 9
0x14004b5d8  mov     edx, ebx
0x14004b5da  call    cs:__imp_ExAllocatePool2
0x14004b5e1  nop     dword ptr [rax+rax+00h]
0x14004b5e6  test    rax, rax
0x14004b5e9  jnz     short loc_14004B5F5
0x14004b5eb  mov     eax, 0C000009Ah
0x14004b5f0  jmp     loc_14004B6F3
0x14004b5f5  xor     r8d, r8d; AllocateDestinationString
0x14004b5f8  mov     [rbp+DestinationString.Buffer], rax
0x14004b5fc  lea     rdx, [rbp+SourceString]; SourceString
0x14004b600  mov     [rbp+DestinationString.MaximumLength], bx
0x14004b604  lea     rcx, [rbp+DestinationString]; DestinationString
0x14004b608  mov     [rbp+DestinationString.Length], bx
0x14004b60c  call    cs:__imp_RtlUnicodeStringToAnsiString
0x14004b613  nop     dword ptr [rax+rax+00h]
0x14004b618  mov     rcx, [rbp+SourceString.Buffer]; P
0x14004b61c  xor     edx, edx; Tag
0x14004b61e  mov     ebx, eax
0x14004b620  call    cs:__imp_ExFreePoolWithTag
0x14004b627  nop     dword ptr [rax+rax+00h]
0x14004b62c  test    ebx, ebx
0x14004b62e  jns     short loc_14004B647
0x14004b630  mov     rcx, [rbp+DestinationString.Buffer]; P
0x14004b634  xor     edx, edx; Tag
0x14004b636  call    cs:__imp_ExFreePoolWithTag
0x14004b63d  nop     dword ptr [rax+rax+00h]
0x14004b642  jmp     loc_14004B5BA
0x14004b647  lea     rdx, aLmhosts; "\\lmhosts"
0x14004b64e  lea     rcx, [rbp+Source]; DestinationString
0x14004b652  call    cs:__imp_RtlInitString
0x14004b659  nop     dword ptr [rax+rax+00h]
0x14004b65e  lea     rdx, [rbp+Source]; Source
0x14004b662  lea     rcx, [rbp+DestinationString]; Destination
0x14004b666  call    cs:__imp_RtlAppendStringToString
0x14004b66d  nop     dword ptr [rax+rax+00h]
0x14004b672  mov     edi, eax
0x14004b674  test    eax, eax
0x14004b676  js      short loc_14004B6DF
0x14004b678  mov     rbx, [rbp+DestinationString.Buffer]
0x14004b67c  lea     rdx, aSystemroot; "%SystemRoot%"
0x14004b683  mov     rcx, rbx; Str1
0x14004b686  mov     r8d, 0Ch; MaxCount
0x14004b68c  call    strncmp_0
0x14004b691  test    eax, eax
0x14004b693  jnz     short loc_14004B6DA
0x14004b695  mov     byte ptr [rbx], 5Ch ; '\'
0x14004b698  mov     rax, [rbp+DestinationString.Buffer]
0x14004b69c  mov     byte ptr [rax+0Bh], 5Ch ; '\'
0x14004b6a0  mov     rbx, [rbp+DestinationString.Buffer]
0x14004b6a4  lea     rcx, [rbx+0Ch]; void *
0x14004b6a8  cmp     byte ptr [rcx], 5Ch ; '\'
0x14004b6ab  jnz     short loc_14004B6DA
0x14004b6ad  mov     edx, 0Dh
0x14004b6b2  cmp     [rbp+DestinationString.Length], dx
0x14004b6b6  jbe     short loc_14004B6DA
0x14004b6b8  movzx   r8d, [rbp+DestinationString.Length]
0x14004b6bd  sub     r8d, edx; Size
0x14004b6c0  lea     rdx, [rbx+0Dh]; Src
0x14004b6c4  call    memmove
0x14004b6c9  movzx   ecx, [rbp+DestinationString.Length]
0x14004b6cd  mov     rax, [rbp+DestinationString.Buffer]
0x14004b6d1  mov     byte ptr [rcx+rax-1], 0
0x14004b6d6  mov     rbx, [rbp+DestinationString.Buffer]
0x14004b6da  mov     [rsi], rbx
0x14004b6dd  jmp     short loc_14004B6F1
0x14004b6df  mov     rcx, [rbp+DestinationString.Buffer]; P
0x14004b6e3  xor     edx, edx; Tag
0x14004b6e5  call    cs:__imp_ExFreePoolWithTag
0x14004b6ec  nop     dword ptr [rax+rax+00h]
0x14004b6f1  mov     eax, edi
0x14004b6f3  add     rsp, 58h
0x14004b6f7  pop     rdi
0x14004b6f8  pop     rsi
0x14004b6f9  pop     rbx
0x14004b6fa  pop     rbp
0x14004b6fb  retn
```
