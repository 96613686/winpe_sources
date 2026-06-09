# BfsAllocateAndConcatenatePath

- ea: `0x140005150`
- end: `0x1400052c2`
- name: `BfsAllocateAndConcatenatePath`
- size: `370`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source, PCUNICODE_STRING)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140009d2c`

## callees

- `0x140001008`
- `0x140005150`
- `0x140013860`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400051ec`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005227`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005240`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400051ec`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005227`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005240`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005193`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005193`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000528f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000528f`
- `ntoskrnl!ExAllocatePool2` at `0x1400051c3`
- `ntoskrnl!ExAllocatePool2` at `0x1400051c3`

## pseudocode

```c
__int64 __fastcall BfsAllocateAndConcatenatePath(
        PCUNICODE_STRING Source,
        PCUNICODE_STRING a2,
        struct _UNICODE_STRING *a3)
{
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  NTSTATUS v9; // ebx
  NTSTATUS appended; // eax
  int v12; // [rsp+20h] [rbp-39h]
  NTSTATUS v13; // [rsp+30h] [rbp-29h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+38h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+58h] [rbp-1h] BYREF
  NTSTATUS *v17; // [rsp+78h] [rbp+1Fh]
  __int64 v18; // [rsp+80h] [rbp+27h]

  Destination = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\");
  Destination.MaximumLength = DestinationString.Length + a2->Length + Source->Length;
  Destination.Length = 0;
  Destination.Buffer = (PWSTR)ExAllocatePool2(256, Destination.MaximumLength, 1316185666);
  if ( Destination.Buffer )
  {
    if ( !Source->Length )
      goto LABEL_8;
    appended = RtlAppendUnicodeStringToString(&Destination, Source);
    v9 = appended;
    if ( appended < 0 )
    {
      v6 = (unsigned int)dword_140019000;
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_12;
      v13 = appended;
      v17 = &v13;
      goto LABEL_11;
    }
    v9 = RtlAppendUnicodeStringToString(&Destination, &DestinationString);
    if ( v9 >= 0 )
    {
LABEL_8:
      v9 = RtlAppendUnicodeStringToString(&Destination, a2);
      if ( v9 >= 0 )
      {
        *a3 = Destination;
        return (unsigned int)v9;
      }
    }
  }
  else
  {
    v9 = -1073741801;
  }
  if ( (unsigned int)dword_140019000 <= 3 )
    goto LABEL_12;
  v17 = &v13;
  v13 = v9;
LABEL_11:
  v18 = 4;
  tlgWriteTransfer_EtwWriteTransfer(v6, (unsigned __int8 *)&byte_140016D91, v7, v8, v12, &v16);
LABEL_12:
  if ( Destination.Buffer )
    RtlFreeUnicodeString(&Destination);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140005150  push    rbp
0x140005152  push    rbx
0x140005153  push    rsi
0x140005154  push    rdi
0x140005155  push    r14
0x140005157  lea     rbp, [rsp-37h]
0x14000515c  sub     rsp, 90h
0x140005163  mov     rax, cs:__security_cookie
0x14000516a  xor     rax, rsp
0x14000516d  mov     [rbp+57h+var_28], rax
0x140005171  mov     rdi, rdx
0x140005174  mov     rbx, rcx
0x140005177  xorps   xmm0, xmm0
0x14000517a  lea     rdx, asc_140016968; "\\"
0x140005181  xorps   xmm1, xmm1
0x140005184  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140005188  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x14000518c  mov     rsi, r8
0x14000518f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x140005193  call    cs:__imp_RtlInitUnicodeString
0x14000519a  nop     dword ptr [rax+rax+00h]
0x14000519f  movzx   ecx, word ptr [rbx]
0x1400051a2  xor     r14d, r14d
0x1400051a5  add     cx, [rdi]
0x1400051a8  mov     r8d, 4E736642h
0x1400051ae  add     cx, [rbp+57h+DestinationString.Length]
0x1400051b2  movzx   edx, cx
0x1400051b5  mov     ecx, 100h
0x1400051ba  mov     [rbp+57h+Destination.MaximumLength], dx
0x1400051be  mov     [rbp+57h+Destination.Length], r14w
0x1400051c3  call    cs:__imp_ExAllocatePool2
0x1400051ca  nop     dword ptr [rax+rax+00h]
0x1400051cf  mov     [rbp+57h+Destination.Buffer], rax
0x1400051d3  test    rax, rax
0x1400051d6  jnz     short loc_1400051DF
0x1400051d8  mov     ebx, 0C0000017h
0x1400051dd  jmp     short loc_140005252
0x1400051df  cmp     [rbx], r14w
0x1400051e3  jbe     short loc_140005239
0x1400051e5  mov     rdx, rbx; Source
0x1400051e8  lea     rcx, [rbp+57h+Destination]; Destination
0x1400051ec  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400051f3  nop     dword ptr [rax+rax+00h]
0x1400051f8  mov     ebx, eax
0x1400051fa  test    eax, eax
0x1400051fc  jns     short loc_14000521F
0x1400051fe  mov     ecx, cs:dword_140019000
0x140005204  cmp     ecx, 3
0x140005207  jbe     short loc_140005285
0x140005209  mov     [rbp+57h+var_80], eax
0x14000520c  lea     rax, [rbp+57h+var_80]
0x140005210  mov     [rbp+57h+var_38], rax
0x140005214  lea     rax, [rbp+57h+var_58]
0x140005218  mov     [rsp+0B0h+var_88], rax
0x14000521d  jmp     short loc_140005271
0x14000521f  lea     rdx, [rbp+57h+DestinationString]; Source
0x140005223  lea     rcx, [rbp+57h+Destination]; Destination
0x140005227  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000522e  nop     dword ptr [rax+rax+00h]
0x140005233  mov     ebx, eax
0x140005235  test    eax, eax
0x140005237  js      short loc_140005252
0x140005239  mov     rdx, rdi; Source
0x14000523c  lea     rcx, [rbp+57h+Destination]; Destination
0x140005240  call    cs:__imp_RtlAppendUnicodeStringToString
0x140005247  nop     dword ptr [rax+rax+00h]
0x14000524c  mov     ebx, eax
0x14000524e  test    eax, eax
0x140005250  jns     short loc_14000529D
0x140005252  mov     eax, cs:dword_140019000
0x140005258  cmp     eax, 3
0x14000525b  jbe     short loc_140005285
0x14000525d  lea     rax, [rbp+57h+var_80]
0x140005261  mov     [rbp+57h+var_38], rax
0x140005265  lea     rax, [rbp+57h+var_58]
0x140005269  mov     [rsp+0B0h+var_88], rax; PEVENT_DATA_DESCRIPTOR
0x14000526e  mov     [rbp+57h+var_80], ebx
0x140005271  lea     rdx, byte_140016D91; int
0x140005278  mov     [rbp+57h+var_30], 4
0x140005280  call    _tlgWriteTransfer_EtwWriteTransfer
0x140005285  cmp     [rbp+57h+Destination.Buffer], r14
0x140005289  jz      short loc_1400052A5
0x14000528b  lea     rcx, [rbp+57h+Destination]; UnicodeString
0x14000528f  call    cs:__imp_RtlFreeUnicodeString
0x140005296  nop     dword ptr [rax+rax+00h]
0x14000529b  jmp     short loc_1400052A5
0x14000529d  movups  xmm0, xmmword ptr [rbp+57h+Destination.Length]
0x1400052a1  movdqu  xmmword ptr [rsi], xmm0
0x1400052a5  mov     eax, ebx
0x1400052a7  mov     rcx, [rbp+57h+var_28]
0x1400052ab  xor     rcx, rsp; StackCookie
0x1400052ae  call    __security_check_cookie
0x1400052b3  add     rsp, 90h
0x1400052ba  pop     r14
0x1400052bc  pop     rdi
0x1400052bd  pop     rsi
0x1400052be  pop     rbx
0x1400052bf  pop     rbp
0x1400052c0  retn
```
