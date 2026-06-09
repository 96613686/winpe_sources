# ReadStringRelative

- ea: `0x140048958`
- end: `0x140048aba`
- name: `ReadStringRelative`
- size: `354`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, PCWSTR, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14004b55c`

## callees

- `0x140048958`
- `0x140048db4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140048a1d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140048a1d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140048a31`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140048a31`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400489d7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400489d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048a56`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048a56`
- `ntoskrnl!ExAllocatePool2` at `0x1400489b0`
- `ntoskrnl!ExAllocatePool2` at `0x1400489b0`

## pseudocode

```c
__int64 __fastcall ReadStringRelative(PCUNICODE_STRING SourceString, PCWSTR a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  __int64 v5; // r8
  unsigned int v9; // esi
  wchar_t *Pool2; // rax
  wchar_t *v11; // rdi
  int i; // edx
  unsigned __int16 v13; // r8
  wchar_t *v14; // rdx
  __int64 v15; // rdx
  NTSTATUS appended; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-28h] BYREF
  UNICODE_STRING Source; // [rsp+30h] [rbp-18h] BYREF

  v4 = -1;
  v5 = -1;
  DestinationString = 0;
  Source = 0;
  do
    ++v5;
  while ( a2[v5] );
  v9 = SourceString->MaximumLength + 2 * (v5 + 1);
  Pool2 = (wchar_t *)ExAllocatePool2(64, v9, 942891598);
  v11 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  DestinationString.MaximumLength = v9;
  DestinationString.Buffer = Pool2;
  RtlCopyUnicodeString(&DestinationString, SourceString);
  do
    ++v4;
  while ( DestinationString.Buffer[v4] );
  for ( i = v4 - 1; ; --i )
  {
    if ( i < 0 )
      goto LABEL_8;
    if ( DestinationString.Buffer[i] == asc_140033C74[0] )
      break;
  }
  if ( i == DestinationString.Length - 1 )
  {
LABEL_8:
    v13 = 0;
    v14 = 0;
    goto LABEL_9;
  }
  v13 = 2 * i + 2;
  v14 = &DestinationString.Buffer[i + 1];
LABEL_9:
  DestinationString.Length = v13;
  if ( v14 )
  {
    *v14 = 0;
    RtlInitUnicodeString(&Source, a2);
    appended = RtlAppendUnicodeStringToString(&DestinationString, &Source);
    if ( appended >= 0 )
      appended = OpenAndReadElement(&DestinationString, v15, a4);
  }
  else
  {
    appended = -1073741823;
  }
  ExFreePoolWithTag(v11, 0);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140048958  push    rbp
0x14004895a  push    rbx
0x14004895b  push    rsi
0x14004895c  push    rdi
0x14004895d  push    r12
0x14004895f  push    r13
0x140048961  push    r14
0x140048963  push    r15
0x140048965  mov     rbp, rsp
0x140048968  sub     rsp, 48h
0x14004896c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140048970  xorps   xmm0, xmm0
0x140048973  xorps   xmm1, xmm1
0x140048976  mov     r8, rbx
0x140048979  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14004897d  xor     r13d, r13d
0x140048980  mov     r12, r9
0x140048983  movups  xmmword ptr [rbp+Source.Length], xmm1
0x140048987  mov     r15, rdx
0x14004898a  mov     r14, rcx
0x14004898d  inc     r8
0x140048990  cmp     [rdx+r8*2], r13w
0x140048995  jnz     short loc_14004898D
0x140048997  movzx   eax, word ptr [rcx+2]
0x14004899b  lea     r8d, [r8+1]
0x14004899f  mov     ecx, 40h ; '@'
0x1400489a4  lea     esi, [rax+r8*2]
0x1400489a8  mov     r8d, 3833624Eh
0x1400489ae  mov     edx, esi
0x1400489b0  call    cs:__imp_ExAllocatePool2
0x1400489b7  nop     dword ptr [rax+rax+00h]
0x1400489bc  mov     rdi, rax
0x1400489bf  test    rax, rax
0x1400489c2  jz      loc_140048A76
0x1400489c8  mov     rdx, r14; SourceString
0x1400489cb  mov     [rbp+DestinationString.MaximumLength], si
0x1400489cf  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400489d3  mov     [rbp+DestinationString.Buffer], rax
0x1400489d7  call    cs:__imp_RtlCopyUnicodeString
0x1400489de  nop     dword ptr [rax+rax+00h]
0x1400489e3  mov     r9, [rbp+DestinationString.Buffer]
0x1400489e7  inc     rbx
0x1400489ea  cmp     [r9+rbx*2], r13w
0x1400489ef  jnz     short loc_1400489E7
0x1400489f1  mov     eax, dword ptr cs:asc_140033C74; "\\"
0x1400489f7  lea     edx, [rbx-1]
0x1400489fa  test    edx, edx
0x1400489fc  jns     short loc_140048A7D
0x1400489fe  mov     r8d, r13d
0x140048a01  mov     rdx, r13
0x140048a04  mov     [rbp+DestinationString.Length], r8w
0x140048a09  test    rdx, rdx
0x140048a0c  jz      loc_140048AB3
0x140048a12  mov     [rdx], r13w
0x140048a16  lea     rcx, [rbp+Source]; DestinationString
0x140048a1a  mov     rdx, r15; SourceString
0x140048a1d  call    cs:__imp_RtlInitUnicodeString
0x140048a24  nop     dword ptr [rax+rax+00h]
0x140048a29  lea     rdx, [rbp+Source]; Source
0x140048a2d  lea     rcx, [rbp+DestinationString]; Destination
0x140048a31  call    cs:__imp_RtlAppendUnicodeStringToString
0x140048a38  nop     dword ptr [rax+rax+00h]
0x140048a3d  mov     ebx, eax
0x140048a3f  test    eax, eax
0x140048a41  js      short loc_140048A51
0x140048a43  mov     r8, r12
0x140048a46  lea     rcx, [rbp+DestinationString]
0x140048a4a  call    OpenAndReadElement
0x140048a4f  mov     ebx, eax
0x140048a51  xor     edx, edx; Tag
0x140048a53  mov     rcx, rdi; P
0x140048a56  call    cs:__imp_ExFreePoolWithTag
0x140048a5d  nop     dword ptr [rax+rax+00h]
0x140048a62  mov     eax, ebx
0x140048a64  add     rsp, 48h
0x140048a68  pop     r15
0x140048a6a  pop     r14
0x140048a6c  pop     r13
0x140048a6e  pop     r12
0x140048a70  pop     rdi
0x140048a71  pop     rsi
0x140048a72  pop     rbx
0x140048a73  pop     rbp
0x140048a74  retn
0x140048a76  mov     eax, 0C000009Ah
0x140048a7b  jmp     short loc_140048A64
0x140048a7d  movsxd  rcx, edx
0x140048a80  cmp     [r9+rcx*2], ax
0x140048a85  jz      short loc_140048A8E
0x140048a87  dec     edx
0x140048a89  jmp     loc_1400489FA
0x140048a8e  movzx   eax, [rbp+DestinationString.Length]
0x140048a92  dec     eax
0x140048a94  cmp     edx, eax
0x140048a96  jz      loc_1400489FE
0x140048a9c  lea     eax, [rdx+1]
0x140048a9f  movsxd  rcx, eax
0x140048aa2  lea     r8d, ds:2[rdx*2]
0x140048aaa  lea     rdx, [r9+rcx*2]
0x140048aae  jmp     loc_140048A04
0x140048ab3  mov     ebx, 0C0000001h
0x140048ab8  jmp     short loc_140048A51
```
