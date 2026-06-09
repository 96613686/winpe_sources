# UlpIsServiceContainerEquivalent

- ea: `0x1c013c0d0`
- end: `0x1c013c29f`
- name: `UlpIsServiceContainerEquivalent`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1c013a200`

## callees

- `0x1c013c0d0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1c013c1f7`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1c013c227`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1c013c263`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1c013c1f7`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1c013c227`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1c013c263`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1c013c152`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1c013c1bb`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1c013c152`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1c013c1bb`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1c013c1dd`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1c013c1dd`

## pseudocode

```c
NTSTATUS __fastcall UlpIsServiceContainerEquivalent(__int64 a1, __int64 a2, _BYTE *a3)
{
  char v5; // al
  __int64 v6; // rsi
  __int64 v7; // rbx
  USHORT v8; // ax
  NTSTATUS result; // eax
  char v10; // r12
  __int64 v11; // r15
  __int64 v12; // r13
  USHORT v13; // ax
  NTSTATUS v14; // r12d
  LONG v15; // r12d
  __int64 v16; // rax
  struct _STRING SourceString; // [rsp+20h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-20h] BYREF
  UNICODE_STRING String2; // [rsp+40h] [rbp-10h] BYREF
  char v20; // [rsp+90h] [rbp+40h]

  DestinationString = 0;
  String2 = 0;
  v5 = 0;
  SourceString = 0;
  while ( 1 )
  {
    v6 = 0;
    v20 = v5;
    if ( *(_DWORD *)(a1 + 16) )
      break;
LABEL_21:
    if ( v5 )
    {
      *a3 = 1;
      return 0;
    }
    v16 = a1;
    a1 = a2;
    a2 = v16;
    v5 = 1;
  }
  while ( 1 )
  {
    v7 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v6);
    v8 = *(_WORD *)(v7 + 16);
    if ( *(_DWORD *)v7 == 1 )
    {
      DestinationString.Length = *(_WORD *)(v7 + 16);
      DestinationString.MaximumLength = v8;
      DestinationString.Buffer = *(PWSTR *)(v7 + 8);
    }
    else
    {
      SourceString.Length = *(_WORD *)(v7 + 16);
      SourceString.MaximumLength = v8;
      SourceString.Buffer = *(PCHAR *)(v7 + 8);
      result = RtlAnsiStringToUnicodeString(&DestinationString, &SourceString, 1u);
      if ( result )
        return result;
    }
    v10 = 0;
    v11 = 0;
    if ( *(_DWORD *)(a2 + 16) )
      break;
LABEL_16:
    if ( *(_DWORD *)v7 == 2 )
      RtlFreeUnicodeString(&DestinationString);
    if ( !v10 )
    {
      *a3 = 0;
      return 0;
    }
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= *(_DWORD *)(a1 + 16) )
    {
      v5 = v20;
      goto LABEL_21;
    }
  }
  while ( 1 )
  {
    v12 = *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8 * v11);
    v13 = *(_WORD *)(v12 + 16);
    if ( *(_DWORD *)v12 == 1 )
    {
      String2.Length = *(_WORD *)(v12 + 16);
      String2.MaximumLength = v13;
      String2.Buffer = *(PWSTR *)(v12 + 8);
      goto LABEL_10;
    }
    SourceString.Length = *(_WORD *)(v12 + 16);
    SourceString.MaximumLength = v13;
    SourceString.Buffer = *(PCHAR *)(v12 + 8);
    v14 = RtlAnsiStringToUnicodeString(&String2, &SourceString, 1u);
    if ( v14 )
      break;
LABEL_10:
    v15 = RtlCompareUnicodeString(&DestinationString, &String2, 1u);
    if ( *(_DWORD *)v12 == 2 )
      RtlFreeUnicodeString(&String2);
    if ( !v15 )
    {
      v10 = 1;
      goto LABEL_16;
    }
    v11 = (unsigned int)(v11 + 1);
    if ( (unsigned int)v11 >= *(_DWORD *)(a2 + 16) )
    {
      v10 = 0;
      goto LABEL_16;
    }
  }
  if ( *(_DWORD *)v7 == 2 )
    RtlFreeUnicodeString(&DestinationString);
  return v14;
}

```

## disassembly

```asm
0x1c013c0d0  mov     [rsp-38h+arg_8], rbx
0x1c013c0d5  mov     [rsp-38h+arg_10], r8
0x1c013c0da  push    rbp
0x1c013c0db  push    rsi
0x1c013c0dc  push    rdi
0x1c013c0dd  push    r12
0x1c013c0df  push    r13
0x1c013c0e1  push    r14
0x1c013c0e3  push    r15
0x1c013c0e5  mov     rbp, rsp
0x1c013c0e8  sub     rsp, 50h
0x1c013c0ec  xorps   xmm0, xmm0
0x1c013c0ef  xorps   xmm1, xmm1
0x1c013c0f2  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1c013c0f6  mov     r14, rdx
0x1c013c0f9  mov     rdi, rcx
0x1c013c0fc  movups  xmmword ptr [rbp+String2.Length], xmm1
0x1c013c100  xor     al, al
0x1c013c102  movups  xmmword ptr [rbp+SourceString.Length], xmm0
0x1c013c106  xor     esi, esi
0x1c013c108  mov     [rbp+arg_0], al
0x1c013c10b  cmp     [rdi+10h], esi
0x1c013c10e  jbe     loc_1C013C246
0x1c013c114  mov     rax, [rdi+8]
0x1c013c118  mov     rbx, [rax+rsi*8]
0x1c013c11c  cmp     dword ptr [rbx], 1
0x1c013c11f  movzx   eax, word ptr [rbx+10h]
0x1c013c123  jnz     short loc_1C013C137
0x1c013c125  mov     [rbp+DestinationString.Length], ax
0x1c013c129  mov     [rbp+DestinationString.MaximumLength], ax
0x1c013c12d  mov     rax, [rbx+8]
0x1c013c131  mov     [rbp+DestinationString.Buffer], rax
0x1c013c135  jmp     short loc_1C013C166
0x1c013c137  mov     [rbp+SourceString.Length], ax
0x1c013c13b  lea     rdx, [rbp+SourceString]; SourceString
0x1c013c13f  mov     [rbp+SourceString.MaximumLength], ax
0x1c013c143  lea     rcx, [rbp+DestinationString]; DestinationString
0x1c013c147  mov     rax, [rbx+8]
0x1c013c14b  mov     r8b, 1; AllocateDestinationString
0x1c013c14e  mov     [rbp+SourceString.Buffer], rax
0x1c013c152  call    cs:__imp_RtlAnsiStringToUnicodeString
0x1c013c159  nop     dword ptr [rax+rax+00h]
0x1c013c15e  test    eax, eax
0x1c013c160  jnz     loc_1C013C286
0x1c013c166  xor     r12b, r12b
0x1c013c169  xor     r15d, r15d
0x1c013c16c  mov     [rbp+arg_18], r12b
0x1c013c170  cmp     [r14+10h], r15d
0x1c013c174  jbe     loc_1C013C21E
0x1c013c17a  mov     rax, [r14+8]
0x1c013c17e  mov     r13, [rax+r15*8]
0x1c013c182  cmp     dword ptr [r13+0], 1
0x1c013c187  movzx   eax, word ptr [r13+10h]
0x1c013c18c  jnz     short loc_1C013C1A0
0x1c013c18e  mov     [rbp+String2.Length], ax
0x1c013c192  mov     [rbp+String2.MaximumLength], ax
0x1c013c196  mov     rax, [r13+8]
0x1c013c19a  mov     [rbp+String2.Buffer], rax
0x1c013c19e  jmp     short loc_1C013C1D2
0x1c013c1a0  mov     [rbp+SourceString.Length], ax
0x1c013c1a4  lea     rdx, [rbp+SourceString]; SourceString
0x1c013c1a8  mov     [rbp+SourceString.MaximumLength], ax
0x1c013c1ac  lea     rcx, [rbp+String2]; DestinationString
0x1c013c1b0  mov     rax, [r13+8]
0x1c013c1b4  mov     r8b, 1; AllocateDestinationString
0x1c013c1b7  mov     [rbp+SourceString.Buffer], rax
0x1c013c1bb  call    cs:__imp_RtlAnsiStringToUnicodeString
0x1c013c1c2  nop     dword ptr [rax+rax+00h]
0x1c013c1c7  mov     r12d, eax
0x1c013c1ca  test    eax, eax
0x1c013c1cc  jnz     loc_1C013C25A
0x1c013c1d2  mov     r8b, 1; CaseInSensitive
0x1c013c1d5  lea     rdx, [rbp+String2]; String2
0x1c013c1d9  lea     rcx, [rbp+DestinationString]; String1
0x1c013c1dd  call    cs:__imp_RtlCompareUnicodeString
0x1c013c1e4  nop     dword ptr [rax+rax+00h]
0x1c013c1e9  cmp     dword ptr [r13+0], 2
0x1c013c1ee  mov     r12d, eax
0x1c013c1f1  jnz     short loc_1C013C203
0x1c013c1f3  lea     rcx, [rbp+String2]; UnicodeString
0x1c013c1f7  call    cs:__imp_RtlFreeUnicodeString
0x1c013c1fe  nop     dword ptr [rax+rax+00h]
0x1c013c203  test    r12d, r12d
0x1c013c206  jz      short loc_1C013C21B
0x1c013c208  inc     r15d
0x1c013c20b  cmp     r15d, [r14+10h]
0x1c013c20f  jb      loc_1C013C17A
0x1c013c215  mov     r12b, [rbp+arg_18]
0x1c013c219  jmp     short loc_1C013C21E
0x1c013c21b  mov     r12b, 1
0x1c013c21e  cmp     dword ptr [rbx], 2
0x1c013c221  jnz     short loc_1C013C233
0x1c013c223  lea     rcx, [rbp+DestinationString]; UnicodeString
0x1c013c227  call    cs:__imp_RtlFreeUnicodeString
0x1c013c22e  nop     dword ptr [rax+rax+00h]
0x1c013c233  test    r12b, r12b
0x1c013c236  jz      short loc_1C013C274
0x1c013c238  inc     esi
0x1c013c23a  cmp     esi, [rdi+10h]
0x1c013c23d  jb      loc_1C013C114
0x1c013c243  mov     al, [rbp+arg_0]
0x1c013c246  test    al, al
0x1c013c248  jnz     short loc_1C013C27D
0x1c013c24a  mov     rax, rdi
0x1c013c24d  mov     rdi, r14
0x1c013c250  mov     r14, rax
0x1c013c253  mov     al, 1
0x1c013c255  jmp     loc_1C013C106
0x1c013c25a  cmp     dword ptr [rbx], 2
0x1c013c25d  jnz     short loc_1C013C26F
0x1c013c25f  lea     rcx, [rbp+DestinationString]; UnicodeString
0x1c013c263  call    cs:__imp_RtlFreeUnicodeString
0x1c013c26a  nop     dword ptr [rax+rax+00h]
0x1c013c26f  mov     eax, r12d
0x1c013c272  jmp     short loc_1C013C286
0x1c013c274  mov     rax, [rbp+arg_10]
0x1c013c278  mov     byte ptr [rax], 0
0x1c013c27b  jmp     short loc_1C013C284
0x1c013c27d  mov     rax, [rbp+arg_10]
0x1c013c281  mov     byte ptr [rax], 1
0x1c013c284  xor     eax, eax
0x1c013c286  mov     rbx, [rsp+50h+arg_8]
0x1c013c28e  add     rsp, 50h
0x1c013c292  pop     r15
0x1c013c294  pop     r14
0x1c013c296  pop     r13
0x1c013c298  pop     r12
0x1c013c29a  pop     rdi
0x1c013c29b  pop     rsi
0x1c013c29c  pop     rbp
0x1c013c29d  retn
```
