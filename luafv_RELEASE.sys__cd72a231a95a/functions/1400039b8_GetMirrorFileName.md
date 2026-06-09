# GetMirrorFileName

- ea: `0x1400039b8`
- end: `0x140003b63`
- name: `GetMirrorFileName`
- size: `427`
- prototype: `__int64 __fastcall(_QWORD *, __int64, const UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400041e8`
- `0x1400045c0`

## callees

- `0x1400039b8`
- `0x14001b650`
- `0x14001dd40`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400039f6`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400039f6`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140003a98`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140003a98`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003a84`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003b2f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003a84`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003b2f`

## pseudocode

```c
__int64 __fastcall GetMirrorFileName(_QWORD *a1, __int64 a2, const UNICODE_STRING *a3, struct _UNICODE_STRING *a4)
{
  UNICODE_STRING v6; // xmm0
  __int64 v8; // r14
  BOOLEAN v9; // al
  __int64 v10; // r8
  USHORT v11; // dx
  __int64 v12; // rax
  __int64 v13; // rdx
  WCHAR *Pool; // rax
  NTSTATUS appended; // ebx
  UNICODE_STRING *p_Source; // rdx
  __int64 v17; // rdx
  __int64 v19; // rdx
  PWSTR Buffer; // rax
  __int64 v21; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-30h] BYREF
  UNICODE_STRING Source; // [rsp+30h] [rbp-20h] BYREF
  UNICODE_STRING v24; // [rsp+40h] [rbp-10h] BYREF

  v24 = 0;
  v6 = *a3;
  DestinationString = 0;
  v8 = *a1;
  Source = v6;
  v9 = RtlPrefixUnicodeString((PCUNICODE_STRING)(v8 + 152), a3, 1u);
  LOBYTE(v10) = 2;
  if ( v9 )
  {
    Source.Buffer += (unsigned __int64)*(unsigned __int16 *)(v8 + 152) >> 1;
    Source.Length -= *(_WORD *)(v8 + 152);
    v11 = Source.MaximumLength - *(_WORD *)(v8 + 152);
    DestinationString.Length = 0;
    v12 = a1[1];
    Source.MaximumLength = v11;
    v13 = (unsigned __int16)(*(_WORD *)(v12 + 152) + v11);
    DestinationString.MaximumLength = v13;
    Pool = (WCHAR *)LuafvAllocatePool(1, v13, v10);
    DestinationString.Buffer = Pool;
    if ( !Pool )
    {
      appended = -1073741670;
      goto LABEL_11;
    }
    RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(a1[1] + 152LL));
    p_Source = &Source;
  }
  else
  {
    v17 = (unsigned __int16)(a3->MaximumLength + *(_WORD *)(a1[1] + 122LL) - *(_WORD *)(*a1 + 122LL));
    DestinationString.Length = 0;
    DestinationString.MaximumLength = v17;
    DestinationString.Buffer = (PWSTR)LuafvAllocatePool(1, v17, v10);
    if ( !DestinationString.Buffer )
      return 3221225626LL;
    v19 = *a1;
    Buffer = a3->Buffer;
    v24 = *a3;
    v24.Buffer = &Buffer[(unsigned __int64)*(unsigned __int16 *)(v19 + 120) >> 1];
    v24.Length -= *(_WORD *)(v19 + 120);
    LOWORD(Buffer) = *(_WORD *)(v19 + 120);
    v21 = a1[1];
    v24.MaximumLength -= (unsigned __int16)Buffer;
    RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(v21 + 120));
    p_Source = &v24;
  }
  appended = RtlAppendUnicodeStringToString(&DestinationString, p_Source);
  if ( appended < 0 )
  {
    Pool = DestinationString.Buffer;
LABEL_11:
    if ( Pool )
      LuafvFreePool(Pool);
    return (unsigned int)appended;
  }
  *a4 = DestinationString;
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1400039b8  push    rbp
0x1400039ba  push    rbx
0x1400039bb  push    rsi
0x1400039bc  push    rdi
0x1400039bd  push    r14
0x1400039bf  mov     rbp, rsp
0x1400039c2  sub     rsp, 50h
0x1400039c6  xorps   xmm0, xmm0
0x1400039c9  mov     rsi, r8
0x1400039cc  movups  [rbp+var_10], xmm0
0x1400039d0  mov     rbx, rcx
0x1400039d3  mov     rdx, rsi; String2
0x1400039d6  movups  xmm0, xmmword ptr [r8]
0x1400039da  mov     r8b, 1; CaseInSensitive
0x1400039dd  mov     rdi, r9
0x1400039e0  xorps   xmm1, xmm1
0x1400039e3  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x1400039e7  mov     r14, [rcx]
0x1400039ea  movdqu  xmmword ptr [rbp+Source.Length], xmm0
0x1400039ef  lea     rcx, [r14+98h]; String1
0x1400039f6  call    cs:__imp_RtlPrefixUnicodeString
0x1400039fd  nop     dword ptr [rax+rax+00h]
0x140003a02  mov     r8b, 2
0x140003a05  test    al, al
0x140003a07  jz      loc_140003ABB
0x140003a0d  movzx   ecx, word ptr [r14+98h]
0x140003a15  mov     rax, [rbp+Source.Buffer]
0x140003a19  movzx   edx, [rbp+Source.MaximumLength]
0x140003a1d  shr     rcx, 1
0x140003a20  lea     rcx, [rax+rcx*2]
0x140003a24  mov     [rbp+Source.Buffer], rcx
0x140003a28  mov     ecx, 1
0x140003a2d  movzx   eax, word ptr [r14+98h]
0x140003a35  sub     [rbp+Source.Length], ax
0x140003a39  xor     eax, eax
0x140003a3b  sub     dx, [r14+98h]
0x140003a43  mov     [rbp+DestinationString.Length], ax
0x140003a47  mov     rax, [rbx+8]
0x140003a4b  mov     [rbp+Source.MaximumLength], dx
0x140003a4f  add     dx, [rax+98h]
0x140003a56  movzx   edx, dx
0x140003a59  mov     [rbp+DestinationString.MaximumLength], dx
0x140003a5d  call    LuafvAllocatePool
0x140003a62  mov     [rbp+DestinationString.Buffer], rax
0x140003a66  test    rax, rax
0x140003a69  jnz     short loc_140003A75
0x140003a6b  mov     ebx, 0C000009Ah
0x140003a70  jmp     loc_140003B48
0x140003a75  mov     rdx, [rbx+8]
0x140003a79  lea     rcx, [rbp+DestinationString]; DestinationString
0x140003a7d  add     rdx, 98h; SourceString
0x140003a84  call    cs:__imp_RtlCopyUnicodeString
0x140003a8b  nop     dword ptr [rax+rax+00h]
0x140003a90  lea     rdx, [rbp+Source]; Source
0x140003a94  lea     rcx, [rbp+DestinationString]; Destination
0x140003a98  call    cs:__imp_RtlAppendUnicodeStringToString
0x140003a9f  nop     dword ptr [rax+rax+00h]
0x140003aa4  mov     ebx, eax
0x140003aa6  test    eax, eax
0x140003aa8  js      loc_140003B44
0x140003aae  movups  xmm0, xmmword ptr [rbp+DestinationString.Length]
0x140003ab2  movdqu  xmmword ptr [rdi], xmm0
0x140003ab6  jmp     loc_140003B55
0x140003abb  mov     rax, [rbx]
0x140003abe  mov     rdx, [rbx+8]
0x140003ac2  movzx   ecx, word ptr [rax+7Ah]
0x140003ac6  movzx   eax, word ptr [rdx+7Ah]
0x140003aca  sub     ax, cx
0x140003acd  add     ax, [rsi+2]
0x140003ad1  movzx   edx, ax
0x140003ad4  xor     eax, eax
0x140003ad6  mov     [rbp+DestinationString.Length], ax
0x140003ada  mov     [rbp+DestinationString.MaximumLength], dx
0x140003ade  lea     ecx, [rax+1]
0x140003ae1  call    LuafvAllocatePool
0x140003ae6  mov     [rbp+DestinationString.Buffer], rax
0x140003aea  test    rax, rax
0x140003aed  jnz     short loc_140003AF6
0x140003aef  mov     eax, 0C000009Ah
0x140003af4  jmp     short loc_140003B57
0x140003af6  mov     rdx, [rbx]
0x140003af9  mov     rax, [rsi+8]
0x140003afd  movups  xmm0, xmmword ptr [rsi]
0x140003b00  movups  [rbp+var_10], xmm0
0x140003b04  movzx   ecx, word ptr [rdx+78h]
0x140003b08  shr     rcx, 1
0x140003b0b  lea     rcx, [rax+rcx*2]
0x140003b0f  mov     qword ptr [rbp+var_10+8], rcx
0x140003b13  lea     rcx, [rbp+DestinationString]; DestinationString
0x140003b17  movzx   eax, word ptr [rdx+78h]
0x140003b1b  sub     word ptr [rbp+var_10], ax
0x140003b1f  movzx   eax, word ptr [rdx+78h]
0x140003b23  mov     rdx, [rbx+8]
0x140003b27  sub     word ptr [rbp+var_10+2], ax
0x140003b2b  add     rdx, 78h ; 'x'; SourceString
0x140003b2f  call    cs:__imp_RtlCopyUnicodeString
0x140003b36  nop     dword ptr [rax+rax+00h]
0x140003b3b  lea     rdx, [rbp+var_10]
0x140003b3f  jmp     loc_140003A94
0x140003b44  mov     rax, [rbp+DestinationString.Buffer]
0x140003b48  test    rax, rax
0x140003b4b  jz      short loc_140003B55
0x140003b4d  mov     rcx, rax
0x140003b50  call    LuafvFreePool
0x140003b55  mov     eax, ebx
0x140003b57  add     rsp, 50h
0x140003b5b  pop     r14
0x140003b5d  pop     rdi
0x140003b5e  pop     rsi
0x140003b5f  pop     rbx
0x140003b60  pop     rbp
0x140003b61  retn
```
