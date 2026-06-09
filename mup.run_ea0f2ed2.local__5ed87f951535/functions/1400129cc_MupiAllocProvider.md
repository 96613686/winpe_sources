# MupiAllocProvider

- ea: `0x1400129cc`
- end: `0x140012bcf`
- name: `MupiAllocProvider`
- size: `515`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, PCUNICODE_STRING, PCUNICODE_STRING)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400128e0`

## callees

- `0x140002754`
- `0x140003e44`
- `0x1400059c0`
- `0x14000f644`
- `0x1400129cc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140012a51`
- `ntoskrnl!ExAllocatePool2` at `0x140012acb`
- `ntoskrnl!ExAllocatePool2` at `0x140012b31`
- `ntoskrnl!ExAllocatePool2` at `0x140012a51`
- `ntoskrnl!ExAllocatePool2` at `0x140012acb`
- `ntoskrnl!ExAllocatePool2` at `0x140012b31`
- `ntoskrnl!KeInitializeEvent` at `0x140012b51`
- `ntoskrnl!KeInitializeEvent` at `0x140012b51`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140012aa4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140012af0`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140012b7a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140012aa4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140012af0`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140012b7a`

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
0x1400129cc  push    rbx
0x1400129ce  push    rbp
0x1400129cf  push    rsi
0x1400129d0  push    rdi
0x1400129d1  push    r12
0x1400129d3  push    r13
0x1400129d5  push    r14
0x1400129d7  push    r15
0x1400129d9  sub     rsp, 38h
0x1400129dd  mov     r12d, r9d
0x1400129e0  mov     rdi, r8
0x1400129e3  mov     r14, rdx
0x1400129e6  mov     rsi, rcx
0x1400129e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400129f0  lea     rax, WPP_GLOBAL_Control
0x1400129f7  cmp     rcx, rax
0x1400129fa  jz      short loc_140012A16
0x1400129fc  test    dword ptr [rcx+2Ch], 4000000h
0x140012a03  jz      short loc_140012A16
0x140012a05  mov     rcx, [rcx+18h]
0x140012a09  mov     [rsp+78h+var_58], r9d
0x140012a0e  mov     r9, rsi
0x140012a11  call    WPP_SF_ZD
0x140012a16  test    rsi, rsi
0x140012a19  jz      short loc_140012A21
0x140012a1b  movzx   ebp, word ptr [rsi+2]
0x140012a1f  jmp     short loc_140012A23
0x140012a21  xor     ebp, ebp
0x140012a23  test    rdi, rdi
0x140012a26  jz      short loc_140012A2F
0x140012a28  movzx   r15d, word ptr [rdi+2]
0x140012a2d  jmp     short loc_140012A32
0x140012a2f  xor     r15d, r15d
0x140012a32  movzx   ecx, r15w
0x140012a36  mov     r8d, 6E55754Dh
0x140012a3c  add     ecx, 0B0h
0x140012a42  movzx   r13d, bp
0x140012a46  add     r13d, ecx
0x140012a49  mov     ecx, 102h
0x140012a4e  mov     edx, r13d
0x140012a51  call    cs:__imp_ExAllocatePool2
0x140012a58  nop     dword ptr [rax+rax+00h]
0x140012a5d  mov     rbx, rax
0x140012a60  test    rax, rax
0x140012a63  jz      loc_140012B86
0x140012a69  mov     r8d, r13d; Size
0x140012a6c  xor     edx, edx; Val
0x140012a6e  mov     rcx, rax; void *
0x140012a71  call    memset
0x140012a76  mov     [rbx+2], r13w
0x140012a7b  lea     rax, [rbx+0B0h]
0x140012a82  mov     r13d, 1
0x140012a88  mov     [rbx+20h], rax
0x140012a8c  lea     rcx, [rbx+18h]; DestinationString
0x140012a90  mov     [rbx+4], r13d
0x140012a94  mov     rdx, rsi; SourceString
0x140012a97  mov     word ptr [rbx], 7103h
0x140012a9c  mov     [rbx+3Ch], r12d
0x140012aa0  mov     [rbx+1Ah], bp
0x140012aa4  call    cs:__imp_RtlCopyUnicodeString
0x140012aab  nop     dword ptr [rax+rax+00h]
0x140012ab0  xor     esi, esi
0x140012ab2  mov     [rbx+44h], r13d
0x140012ab6  test    r14, r14
0x140012ab9  jz      short loc_140012B0E
0x140012abb  movzx   edx, word ptr [r14+2]
0x140012ac0  mov     ecx, 102h
0x140012ac5  mov     r8d, 4E50754Dh
0x140012acb  call    cs:__imp_ExAllocatePool2
0x140012ad2  nop     dword ptr [rax+rax+00h]
0x140012ad7  mov     [rbx+30h], rax
0x140012adb  test    rax, rax
0x140012ade  jz      short loc_140012AFE
0x140012ae0  movzx   eax, word ptr [r14+2]
0x140012ae5  lea     rcx, [rbx+28h]; DestinationString
0x140012ae9  mov     rdx, r14; SourceString
0x140012aec  mov     [rbx+2Ah], ax
0x140012af0  call    cs:__imp_RtlCopyUnicodeString
0x140012af7  nop     dword ptr [rax+rax+00h]
0x140012afc  jmp     short loc_140012B15
0x140012afe  mov     rcx, rbx; P
0x140012b01  call    MupiFreeProvider
0x140012b06  mov     rbx, rsi
0x140012b09  jmp     loc_140012BBA
0x140012b0e  mov     [rbx+30h], rsi
0x140012b12  mov     [rbx+28h], esi
0x140012b15  test    rdi, rdi
0x140012b18  jz      short loc_140012B86
0x140012b1a  cmp     [rdi], si
0x140012b1d  jbe     short loc_140012B86
0x140012b1f  mov     edx, 18h
0x140012b24  mov     [rbx+68h], rsi
0x140012b28  mov     r8d, 2070754Dh
0x140012b2e  lea     ecx, [rdx+2Ah]
0x140012b31  call    cs:__imp_ExAllocatePool2
0x140012b38  nop     dword ptr [rax+rax+00h]
0x140012b3d  mov     [rbx+88h], rax
0x140012b44  test    rax, rax
0x140012b47  jz      short loc_140012AFE
0x140012b49  xor     r8d, r8d; State
0x140012b4c  xor     edx, edx; Type
0x140012b4e  mov     rcx, rax; Event
0x140012b51  call    cs:__imp_KeInitializeEvent
0x140012b58  nop     dword ptr [rax+rax+00h]
0x140012b5d  movzx   ecx, bp
0x140012b60  mov     rdx, rdi; SourceString
0x140012b63  add     rcx, 0B0h
0x140012b6a  mov     [rbx+4Ah], r15w
0x140012b6f  add     rcx, rbx
0x140012b72  mov     [rbx+50h], rcx
0x140012b76  lea     rcx, [rbx+48h]; DestinationString
0x140012b7a  call    cs:__imp_RtlCopyUnicodeString
0x140012b81  nop     dword ptr [rax+rax+00h]
0x140012b86  mov     rcx, cs:WPP_GLOBAL_Control
0x140012b8d  lea     rax, WPP_GLOBAL_Control
0x140012b94  cmp     rcx, rax
0x140012b97  jz      short loc_140012BBA
0x140012b99  test    dword ptr [rcx+2Ch], 4000000h
0x140012ba0  jz      short loc_140012BBA
0x140012ba2  mov     rcx, [rcx+18h]
0x140012ba6  lea     r8, WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids
0x140012bad  mov     edx, 13h
0x140012bb2  mov     r9, rbx
0x140012bb5  call    WPP_SF_q
0x140012bba  mov     rax, rbx
0x140012bbd  add     rsp, 38h
0x140012bc1  pop     r15
0x140012bc3  pop     r14
0x140012bc5  pop     r13
0x140012bc7  pop     r12
0x140012bc9  pop     rdi
0x140012bca  pop     rsi
0x140012bcb  pop     rbp
0x140012bcc  pop     rbx
0x140012bcd  retn
```
