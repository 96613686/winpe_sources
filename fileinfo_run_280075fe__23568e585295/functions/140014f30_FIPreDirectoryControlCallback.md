# FIPreDirectoryControlCallback

- ea: `0x140014f30`
- end: `0x140015115`
- name: `FIPreDirectoryControlCallback`
- size: `485`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140003920`
- `0x140003a00`
- `0x140014f30`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x140014fd0`
- `ntoskrnl!PsGetThreadId` at `0x140014fd0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400150c0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400150e5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400150c0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400150e5`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140015072`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140015072`

## pseudocode

```c
_BOOL8 __fastcall FIPreDirectoryControlCallback(unsigned __int64 a1, __int64 a2)
{
  void (__fastcall *v4)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *); // rbx
  struct _KTHREAD *v6; // rcx
  unsigned int ThreadId; // eax
  __int64 v8; // rax
  char v9; // cl
  struct _UNICODE_STRING *v10; // rax
  _DWORD *v11; // rcx
  __int16 v12; // si
  int ActivityIdCallbackData; // eax
  __int128 *v14; // rdx
  __int64 v15; // rcx
  __int16 v16; // [rsp+40h] [rbp-59h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-51h] BYREF
  __int128 v18; // [rsp+58h] [rbp-41h] BYREF
  _OWORD v19[2]; // [rsp+68h] [rbp-31h] BYREF
  __int128 v20; // [rsp+88h] [rbp-11h] BYREF
  _QWORD v21[3]; // [rsp+98h] [rbp-1h] BYREF
  int Length; // [rsp+B0h] [rbp+17h]
  int v23; // [rsp+B4h] [rbp+1Bh]
  __int16 *v24; // [rsp+B8h] [rbp+1Fh]
  __int64 v25; // [rsp+C0h] [rbp+27h]

  v18 = 0;
  v16 = 0;
  memset(v19, 0, sizeof(v19));
  DestinationString = 0;
  v20 = 0;
  v4 = *(void (__fastcall **)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *))(qword_140009A00 + 16);
  if ( v4 )
  {
    v6 = *(struct _KTHREAD **)(a1 + 8);
    memset(v19, 0, sizeof(v19));
    v18 = a1;
    if ( v6 )
      ThreadId = (unsigned int)PsGetThreadId(v6);
    else
      ThreadId = -1;
    DWORD2(v19[0]) = ThreadId;
    *((_QWORD *)&v18 + 1) = *(_QWORD *)(a2 + 32);
    *(_QWORD *)&v19[0] = *(_QWORD *)(*((_QWORD *)&v18 + 1) + 24LL);
    v8 = *(_QWORD *)(a1 + 16);
    v9 = *(_BYTE *)(v8 + 5);
    if ( v9 == 1 )
    {
      v10 = *(struct _UNICODE_STRING **)(v8 + 32);
      if ( v10 )
        DestinationString = *v10;
      else
        RtlInitUnicodeString(&DestinationString, &word_1400061B0);
      v11 = *(_DWORD **)(a1 + 16);
      v12 = 1096;
      HIDWORD(v19[0]) = v11[6];
      LODWORD(v19[1]) = v11[10];
      DWORD1(v19[1]) = v11[12];
    }
    else
    {
      if ( v9 != 2 )
        return *(_QWORD *)(qword_140009A00 + 24) == 0;
      RtlInitUnicodeString(&DestinationString, &word_1400061B0);
      v15 = *(_QWORD *)(a1 + 16);
      v12 = 1101;
      HIDWORD(v19[0]) = *(_DWORD *)(v15 + 24);
      LODWORD(v19[1]) = *(_DWORD *)(v15 + 32);
    }
    v21[1] = 40;
    v21[0] = &v18;
    v21[2] = DestinationString.Buffer;
    Length = DestinationString.Length;
    v16 = 0;
    v24 = &v16;
    v23 = 0;
    v25 = 2;
    ActivityIdCallbackData = FltGetActivityIdCallbackData(a1, &v20);
    v14 = &v20;
    if ( ActivityIdCallbackData < 0 )
      v14 = 0;
    v4(*(_QWORD *)(a1 + 8), v21, 3, 0x4000000, v12, v14);
  }
  return *(_QWORD *)(qword_140009A00 + 24) == 0;
}

```

## disassembly

```asm
0x140014f30  push    rbp
0x140014f32  push    rbx
0x140014f33  push    rsi
0x140014f34  push    rdi
0x140014f35  lea     rbp, [rsp-3Fh]
0x140014f3a  sub     rsp, 0D8h
0x140014f41  mov     rax, cs:__security_cookie
0x140014f48  xor     rax, rsp
0x140014f4b  mov     [rbp+57h+var_28], rax
0x140014f4f  mov     rbx, cs:qword_140009A00
0x140014f56  xorps   xmm0, xmm0
0x140014f59  xor     eax, eax
0x140014f5b  mov     rsi, rdx
0x140014f5e  movups  [rbp+57h+var_98], xmm0
0x140014f62  mov     [rbp+57h+var_B0], ax
0x140014f66  mov     rdi, rcx
0x140014f69  movups  [rbp+57h+var_88], xmm0
0x140014f6d  movups  [rbp+57h+var_78], xmm0
0x140014f71  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140014f75  movups  [rbp+57h+var_68], xmm0
0x140014f79  mov     rbx, [rbx+10h]
0x140014f7d  test    rbx, rbx
0x140014f80  jnz     short loc_140014FAE
0x140014f82  mov     rax, cs:qword_140009A00
0x140014f89  mov     rcx, [rax+18h]
0x140014f8d  xor     eax, eax
0x140014f8f  test    rcx, rcx
0x140014f92  setz    al
0x140014f95  mov     rcx, [rbp+57h+var_28]
0x140014f99  xor     rcx, rsp; StackCookie
0x140014f9c  call    __security_check_cookie
0x140014fa1  add     rsp, 0D8h
0x140014fa8  pop     rdi
0x140014fa9  pop     rsi
0x140014faa  pop     rbx
0x140014fab  pop     rbp
0x140014fac  retn
0x140014fae  mov     rcx, [rcx+8]; Thread
0x140014fb2  mov     qword ptr [rbp+57h+var_98+8], rax
0x140014fb6  mov     qword ptr [rbp+57h+var_88], rax
0x140014fba  mov     qword ptr [rbp+57h+var_78+8], rax
0x140014fbe  mov     qword ptr [rbp+57h+var_98], rdi
0x140014fc2  movdqu  [rbp+57h+var_88+8], xmm0
0x140014fc7  test    rcx, rcx
0x140014fca  jz      loc_14001510B
0x140014fd0  call    cs:__imp_PsGetThreadId
0x140014fd7  nop     dword ptr [rax+rax+00h]
0x140014fdc  mov     dword ptr [rbp+57h+var_88+8], eax
0x140014fdf  mov     rax, [rsi+20h]
0x140014fe3  mov     qword ptr [rbp+57h+var_98+8], rax
0x140014fe7  mov     rax, [rax+18h]
0x140014feb  mov     qword ptr [rbp+57h+var_88], rax
0x140014fef  mov     rax, [rdi+10h]
0x140014ff3  movzx   ecx, byte ptr [rax+5]
0x140014ff7  cmp     cl, 1
0x140014ffa  jnz     loc_1400150D1
0x140015000  mov     rax, [rax+20h]
0x140015004  test    rax, rax
0x140015007  jz      loc_1400150B5
0x14001500d  movups  xmm0, xmmword ptr [rax]
0x140015010  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140015014  mov     rcx, [rdi+10h]
0x140015018  mov     esi, 448h
0x14001501d  mov     eax, [rcx+18h]
0x140015020  mov     dword ptr [rbp+57h+var_88+0Ch], eax
0x140015023  mov     eax, [rcx+28h]
0x140015026  mov     dword ptr [rbp+57h+var_78], eax
0x140015029  mov     eax, [rcx+30h]
0x14001502c  mov     dword ptr [rbp+57h+var_78+4], eax
0x14001502f  lea     rax, [rbp+57h+var_98]
0x140015033  mov     [rbp+57h+var_50], 28h ; '('
0x14001503b  mov     [rbp+57h+var_58], rax
0x14001503f  lea     rdx, [rbp+57h+var_68]
0x140015043  mov     rax, [rbp+57h+DestinationString.Buffer]
0x140015047  mov     rcx, rdi
0x14001504a  mov     [rbp+57h+var_48], rax
0x14001504e  movzx   eax, [rbp+57h+DestinationString.Length]
0x140015052  mov     [rbp+57h+var_40], eax
0x140015055  xor     eax, eax
0x140015057  mov     [rbp+57h+var_B0], ax
0x14001505b  lea     rax, [rbp+57h+var_B0]
0x14001505f  mov     [rbp+57h+var_38], rax
0x140015063  mov     [rbp+57h+var_3C], 0
0x14001506a  mov     [rbp+57h+var_30], 2
0x140015072  call    cs:__imp_FltGetActivityIdCallbackData
0x140015079  nop     dword ptr [rax+rax+00h]
0x14001507e  xor     ecx, ecx
0x140015080  lea     rdx, [rbp+57h+var_68]
0x140015084  test    eax, eax
0x140015086  mov     r9d, 4000000h
0x14001508c  mov     r8d, 3
0x140015092  mov     rax, rbx
0x140015095  cmovs   rdx, rcx
0x140015099  mov     rcx, [rdi+8]
0x14001509d  mov     [rsp+0F0h+var_C8], rdx
0x1400150a2  lea     rdx, [rbp+57h+var_58]
0x1400150a6  mov     [rsp+0F0h+var_D0], si
0x1400150ab  call    _guard_dispatch_icall
0x1400150b0  jmp     loc_140014F82
0x1400150b5  lea     rdx, word_1400061B0; SourceString
0x1400150bc  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400150c0  call    cs:__imp_RtlInitUnicodeString
0x1400150c7  nop     dword ptr [rax+rax+00h]
0x1400150cc  jmp     loc_140015014
0x1400150d1  cmp     cl, 2
0x1400150d4  jnz     loc_140014F82
0x1400150da  lea     rdx, word_1400061B0; SourceString
0x1400150e1  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400150e5  call    cs:__imp_RtlInitUnicodeString
0x1400150ec  nop     dword ptr [rax+rax+00h]
0x1400150f1  mov     rcx, [rdi+10h]
0x1400150f5  mov     esi, 44Dh
0x1400150fa  mov     eax, [rcx+18h]
0x1400150fd  mov     dword ptr [rbp+57h+var_88+0Ch], eax
0x140015100  mov     eax, [rcx+20h]
0x140015103  mov     dword ptr [rbp+57h+var_78], eax
0x140015106  jmp     loc_14001502F
0x14001510b  mov     eax, 0FFFFFFFFh
0x140015110  jmp     loc_140014FDC
```
