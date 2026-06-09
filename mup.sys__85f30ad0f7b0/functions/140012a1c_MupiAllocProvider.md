# MupiAllocProvider

- ea: `0x140012a1c`
- end: `0x140012c1f`
- name: `MupiAllocProvider`
- size: `515`
- prototype: `char *__fastcall(PCUNICODE_STRING SourceString, PCUNICODE_STRING, PCUNICODE_STRING, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140012930`

## callees

- `0x140002754`
- `0x140003e44`
- `0x1400059c0`
- `0x14000f644`
- `0x140012a1c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140012aa1`
- `ntoskrnl!ExAllocatePool2` at `0x140012b1b`
- `ntoskrnl!ExAllocatePool2` at `0x140012b81`
- `ntoskrnl!ExAllocatePool2` at `0x140012aa1`
- `ntoskrnl!ExAllocatePool2` at `0x140012b1b`
- `ntoskrnl!ExAllocatePool2` at `0x140012b81`
- `ntoskrnl!KeInitializeEvent` at `0x140012ba1`
- `ntoskrnl!KeInitializeEvent` at `0x140012ba1`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140012af4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140012b40`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140012bca`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140012af4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140012b40`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140012bca`

## pseudocode

```c
char *__fastcall MupiAllocProvider(PCUNICODE_STRING SourceString, PCUNICODE_STRING a2, PCUNICODE_STRING a3, int a4)
{
  USHORT MaximumLength; // bp
  USHORT v9; // r15
  unsigned int v10; // r13d
  char *Pool2; // rax
  char *v12; // rbx
  __int64 v13; // rax
  struct _KEVENT *v14; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_ZD(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)a2, (_DWORD)a3, (_DWORD)SourceString, a4);
  }
  if ( SourceString )
    MaximumLength = SourceString->MaximumLength;
  else
    MaximumLength = 0;
  if ( a3 )
    v9 = a3->MaximumLength;
  else
    v9 = 0;
  v10 = v9 + 176 + MaximumLength;
  Pool2 = (char *)ExAllocatePool2(258, v10, 1851094349);
  v12 = Pool2;
  if ( !Pool2 )
    goto LABEL_20;
  memset(Pool2, 0, v10);
  *((_WORD *)v12 + 1) = v10;
  *((_QWORD *)v12 + 4) = v12 + 176;
  *((_DWORD *)v12 + 1) = 1;
  *(_WORD *)v12 = 28931;
  *((_DWORD *)v12 + 15) = a4;
  *((_WORD *)v12 + 13) = MaximumLength;
  RtlCopyUnicodeString((PUNICODE_STRING)(v12 + 24), SourceString);
  *((_DWORD *)v12 + 17) = 1;
  if ( a2 )
  {
    v13 = ExAllocatePool2(258, a2->MaximumLength, 1313895757);
    *((_QWORD *)v12 + 6) = v13;
    if ( !v13 )
      goto LABEL_14;
    *((_WORD *)v12 + 21) = a2->MaximumLength;
    RtlCopyUnicodeString((PUNICODE_STRING)(v12 + 40), a2);
  }
  else
  {
    *((_QWORD *)v12 + 6) = 0;
    *((_DWORD *)v12 + 10) = 0;
  }
  if ( a3 && a3->Length )
  {
    *((_QWORD *)v12 + 13) = 0;
    v14 = (struct _KEVENT *)ExAllocatePool2(66, 24, 544240973);
    *((_QWORD *)v12 + 17) = v14;
    if ( v14 )
    {
      KeInitializeEvent(v14, NotificationEvent, 0);
      *((_WORD *)v12 + 37) = v9;
      *((_QWORD *)v12 + 10) = &v12[MaximumLength + 176];
      RtlCopyUnicodeString((PUNICODE_STRING)(v12 + 72), a3);
      goto LABEL_20;
    }
LABEL_14:
    MupiFreeProvider(v12);
    return 0;
  }
LABEL_20:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids, v12);
  }
  return v12;
}

```

## disassembly

```asm
0x140012a1c  push    rbx
0x140012a1e  push    rbp
0x140012a1f  push    rsi
0x140012a20  push    rdi
0x140012a21  push    r12
0x140012a23  push    r13
0x140012a25  push    r14
0x140012a27  push    r15
0x140012a29  sub     rsp, 38h
0x140012a2d  mov     r12d, r9d
0x140012a30  mov     rdi, r8
0x140012a33  mov     r14, rdx
0x140012a36  mov     rsi, rcx
0x140012a39  mov     rcx, cs:WPP_GLOBAL_Control
0x140012a40  lea     rax, WPP_GLOBAL_Control
0x140012a47  cmp     rcx, rax
0x140012a4a  jz      short loc_140012A66
0x140012a4c  test    dword ptr [rcx+2Ch], 4000000h
0x140012a53  jz      short loc_140012A66
0x140012a55  mov     rcx, [rcx+18h]
0x140012a59  mov     [rsp+78h+var_58], r9d
0x140012a5e  mov     r9, rsi
0x140012a61  call    WPP_SF_ZD
0x140012a66  test    rsi, rsi
0x140012a69  jz      short loc_140012A71
0x140012a6b  movzx   ebp, word ptr [rsi+2]
0x140012a6f  jmp     short loc_140012A73
0x140012a71  xor     ebp, ebp
0x140012a73  test    rdi, rdi
0x140012a76  jz      short loc_140012A7F
0x140012a78  movzx   r15d, word ptr [rdi+2]
0x140012a7d  jmp     short loc_140012A82
0x140012a7f  xor     r15d, r15d
0x140012a82  movzx   ecx, r15w
0x140012a86  mov     r8d, 6E55754Dh
0x140012a8c  add     ecx, 0B0h
0x140012a92  movzx   r13d, bp
0x140012a96  add     r13d, ecx
0x140012a99  mov     ecx, 102h
0x140012a9e  mov     edx, r13d
0x140012aa1  call    cs:__imp_ExAllocatePool2
0x140012aa8  nop     dword ptr [rax+rax+00h]
0x140012aad  mov     rbx, rax
0x140012ab0  test    rax, rax
0x140012ab3  jz      loc_140012BD6
0x140012ab9  mov     r8d, r13d; Size
0x140012abc  xor     edx, edx; Val
0x140012abe  mov     rcx, rax; void *
0x140012ac1  call    memset
0x140012ac6  mov     [rbx+2], r13w
0x140012acb  lea     rax, [rbx+0B0h]
0x140012ad2  mov     r13d, 1
0x140012ad8  mov     [rbx+20h], rax
0x140012adc  lea     rcx, [rbx+18h]; DestinationString
0x140012ae0  mov     [rbx+4], r13d
0x140012ae4  mov     rdx, rsi; SourceString
0x140012ae7  mov     word ptr [rbx], 7103h
0x140012aec  mov     [rbx+3Ch], r12d
0x140012af0  mov     [rbx+1Ah], bp
0x140012af4  call    cs:__imp_RtlCopyUnicodeString
0x140012afb  nop     dword ptr [rax+rax+00h]
0x140012b00  xor     esi, esi
0x140012b02  mov     [rbx+44h], r13d
0x140012b06  test    r14, r14
0x140012b09  jz      short loc_140012B5E
0x140012b0b  movzx   edx, word ptr [r14+2]
0x140012b10  mov     ecx, 102h
0x140012b15  mov     r8d, 4E50754Dh
0x140012b1b  call    cs:__imp_ExAllocatePool2
0x140012b22  nop     dword ptr [rax+rax+00h]
0x140012b27  mov     [rbx+30h], rax
0x140012b2b  test    rax, rax
0x140012b2e  jz      short loc_140012B4E
0x140012b30  movzx   eax, word ptr [r14+2]
0x140012b35  lea     rcx, [rbx+28h]; DestinationString
0x140012b39  mov     rdx, r14; SourceString
0x140012b3c  mov     [rbx+2Ah], ax
0x140012b40  call    cs:__imp_RtlCopyUnicodeString
0x140012b47  nop     dword ptr [rax+rax+00h]
0x140012b4c  jmp     short loc_140012B65
0x140012b4e  mov     rcx, rbx; P
0x140012b51  call    MupiFreeProvider
0x140012b56  mov     rbx, rsi
0x140012b59  jmp     loc_140012C0A
0x140012b5e  mov     [rbx+30h], rsi
0x140012b62  mov     [rbx+28h], esi
0x140012b65  test    rdi, rdi
0x140012b68  jz      short loc_140012BD6
0x140012b6a  cmp     [rdi], si
0x140012b6d  jbe     short loc_140012BD6
0x140012b6f  mov     edx, 18h
0x140012b74  mov     [rbx+68h], rsi
0x140012b78  mov     r8d, 2070754Dh
0x140012b7e  lea     ecx, [rdx+2Ah]
0x140012b81  call    cs:__imp_ExAllocatePool2
0x140012b88  nop     dword ptr [rax+rax+00h]
0x140012b8d  mov     [rbx+88h], rax
0x140012b94  test    rax, rax
0x140012b97  jz      short loc_140012B4E
0x140012b99  xor     r8d, r8d; State
0x140012b9c  xor     edx, edx; Type
0x140012b9e  mov     rcx, rax; Event
0x140012ba1  call    cs:__imp_KeInitializeEvent
0x140012ba8  nop     dword ptr [rax+rax+00h]
0x140012bad  movzx   ecx, bp
0x140012bb0  mov     rdx, rdi; SourceString
0x140012bb3  add     rcx, 0B0h
0x140012bba  mov     [rbx+4Ah], r15w
0x140012bbf  add     rcx, rbx
0x140012bc2  mov     [rbx+50h], rcx
0x140012bc6  lea     rcx, [rbx+48h]; DestinationString
0x140012bca  call    cs:__imp_RtlCopyUnicodeString
0x140012bd1  nop     dword ptr [rax+rax+00h]
0x140012bd6  mov     rcx, cs:WPP_GLOBAL_Control
0x140012bdd  lea     rax, WPP_GLOBAL_Control
0x140012be4  cmp     rcx, rax
0x140012be7  jz      short loc_140012C0A
0x140012be9  test    dword ptr [rcx+2Ch], 4000000h
0x140012bf0  jz      short loc_140012C0A
0x140012bf2  mov     rcx, [rcx+18h]
0x140012bf6  lea     r8, WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids
0x140012bfd  mov     edx, 13h
0x140012c02  mov     r9, rbx
0x140012c05  call    WPP_SF_q
0x140012c0a  mov     rax, rbx
0x140012c0d  add     rsp, 38h
0x140012c11  pop     r15
0x140012c13  pop     r14
0x140012c15  pop     r13
0x140012c17  pop     r12
0x140012c19  pop     rdi
0x140012c1a  pop     rsi
0x140012c1b  pop     rbp
0x140012c1c  pop     rbx
0x140012c1d  retn
```
