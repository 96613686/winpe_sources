# MincryptStringToUnicodeString

- ea: `0x180099e30`
- end: `0x180099fdc`
- name: `MincryptStringToUnicodeString`
- size: `428`
- prototype: `__int64 __fastcall(PUNICODE_STRING DestinationString)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1800658e4`
- `0x180065e10`
- `0x18006dd5c`
- `0x180072880`
- `0x1800992d4`
- `0x18009b158`
- `0x18009b8e0`

## callees

- `0x180099e30`
- `0x180099fe4`
- `0x1800a6f1c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180099fcb`
- `ntoskrnl!RtlInitUnicodeString` at `0x180099fcb`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180099fa7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180099fa7`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x180099f46`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x180099f46`
- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x180099eee`
- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x180099eee`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x180099e8c`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x180099e8c`

## pseudocode

```c
__int64 __fastcall MincryptStringToUnicodeString(PUNICODE_STRING DestinationString, __int64 a2, BOOLEAN a3)
{
  char v4; // dl
  USHORT *v7; // rdi
  USHORT v8; // ax
  CHAR *v9; // rcx
  NTSTATUS v10; // edi
  PWSTR *p_Buffer; // rsi
  __int64 v13; // rax
  unsigned __int64 v14; // rdx
  unsigned __int64 MaximumLength; // rax
  PWSTR Buffer; // rcx
  WCHAR *v17; // rdx
  UNICODE_STRING StringIn; // [rsp+30h] [rbp-28h] BYREF
  struct _STRING SourceString; // [rsp+40h] [rbp-18h] BYREF
  ULONG UnicodeStringActualByteCount; // [rsp+98h] [rbp+40h] BYREF

  UnicodeStringActualByteCount = 0;
  v4 = *(_BYTE *)(a2 + 10);
  v7 = (USHORT *)(a2 + 8);
  SourceString = 0;
  StringIn = 0;
  if ( v4 == 12 )
  {
    p_Buffer = &DestinationString->Buffer;
    if ( a3 )
    {
      v13 = MincryptAlloc(2LL * *v7 + 2);
      *p_Buffer = (PWSTR)v13;
      if ( !v13 )
        return (unsigned int)-1073741801;
      DestinationString->MaximumLength = 2 * *v7;
    }
    v10 = RtlUTF8ToUnicodeN(
            *p_Buffer,
            DestinationString->MaximumLength,
            &UnicodeStringActualByteCount,
            *(PCCH *)a2,
            *v7);
    if ( v10 < 0 )
    {
      if ( a3 )
      {
        MincryptFree(*p_Buffer);
        RtlInitUnicodeString(DestinationString, 0);
      }
    }
    else
    {
      v14 = (unsigned __int16)UnicodeStringActualByteCount;
      MaximumLength = DestinationString->MaximumLength;
      DestinationString->Length = UnicodeStringActualByteCount;
      if ( v14 + 2 <= MaximumLength )
        (*p_Buffer)[v14 >> 1] = 0;
    }
  }
  else
  {
    v8 = *v7;
    v9 = *(CHAR **)a2;
    if ( v4 == 30 )
    {
      StringIn.Length = *v7;
      StringIn.MaximumLength = v8;
      StringIn.Buffer = (PWSTR)v9;
      if ( a3 )
      {
        v10 = RtlDuplicateUnicodeString(3u, &StringIn, DestinationString);
        if ( v10 < 0 )
          return (unsigned int)v10;
      }
      else
      {
        if ( DestinationString->MaximumLength < v8 )
          return (unsigned int)-1073741789;
        v10 = 0;
        RtlCopyUnicodeString(DestinationString, &StringIn);
      }
      Buffer = DestinationString->Buffer;
      v17 = &Buffer[(unsigned __int64)DestinationString->Length >> 1];
      while ( Buffer < v17 )
      {
        *Buffer = __ROR2__(*Buffer, 8);
        ++Buffer;
      }
    }
    else
    {
      SourceString.Buffer = *(PCHAR *)a2;
      SourceString.Length = v8;
      SourceString.MaximumLength = v8;
      return (unsigned int)RtlAnsiStringToUnicodeString(DestinationString, &SourceString, a3);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180099e30  push    rbp
0x180099e32  push    rbx
0x180099e33  push    rsi
0x180099e34  push    rdi
0x180099e35  push    r14
0x180099e37  push    r15
0x180099e39  mov     rbp, rsp
0x180099e3c  sub     rsp, 58h
0x180099e40  mov     r15, rdx
0x180099e43  mov     [rbp+UnicodeStringActualByteCount], 0
0x180099e4a  mov     dl, [rdx+0Ah]
0x180099e4d  xorps   xmm0, xmm0
0x180099e50  xorps   xmm1, xmm1
0x180099e53  mov     r14b, r8b
0x180099e56  mov     rbx, rcx
0x180099e59  lea     rdi, [r15+8]
0x180099e5d  movups  xmmword ptr [rbp+SourceString.Length], xmm0
0x180099e61  movups  xmmword ptr [rbp+StringIn.Length], xmm1
0x180099e65  cmp     dl, 0Ch
0x180099e68  jz      short loc_180099EAA
0x180099e6a  movzx   eax, word ptr [rdi]
0x180099e6d  mov     rcx, [r15]
0x180099e70  cmp     dl, 1Eh
0x180099e73  jz      loc_180099F29
0x180099e79  mov     [rbp+SourceString.Buffer], rcx
0x180099e7d  lea     rdx, [rbp+SourceString]; SourceString
0x180099e81  mov     rcx, rbx; DestinationString
0x180099e84  mov     [rbp+SourceString.Length], ax
0x180099e88  mov     [rbp+SourceString.MaximumLength], ax
0x180099e8c  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180099e93  nop     dword ptr [rax+rax+00h]
0x180099e98  mov     edi, eax
0x180099e9a  mov     eax, edi
0x180099e9c  add     rsp, 58h
0x180099ea0  pop     r15
0x180099ea2  pop     r14
0x180099ea4  pop     rdi
0x180099ea5  pop     rsi
0x180099ea6  pop     rbx
0x180099ea7  pop     rbp
0x180099ea8  retn
0x180099eaa  lea     rsi, [rcx+8]
0x180099eae  test    r14b, r14b
0x180099eb1  jz      short loc_180099ED9
0x180099eb3  movzx   ecx, word ptr [rdi]
0x180099eb6  lea     rcx, ds:2[rcx*2]
0x180099ebe  call    MincryptAlloc
0x180099ec3  mov     [rsi], rax
0x180099ec6  test    rax, rax
0x180099ec9  jz      loc_180099F84
0x180099ecf  movzx   eax, word ptr [rdi]
0x180099ed2  add     ax, ax
0x180099ed5  mov     [rbx+2], ax
0x180099ed9  movzx   eax, word ptr [rdi]
0x180099edc  lea     r8, [rbp+UnicodeStringActualByteCount]; UnicodeStringActualByteCount
0x180099ee0  movzx   edx, word ptr [rbx+2]; UnicodeStringMaxByteCount
0x180099ee4  mov     r9, [r15]; UTF8StringSource
0x180099ee7  mov     rcx, [rsi]; UnicodeStringDestination
0x180099eea  mov     [rsp+58h+UTF8StringByteCount], eax; UTF8StringByteCount
0x180099eee  call    cs:__imp_RtlUTF8ToUnicodeN
0x180099ef5  nop     dword ptr [rax+rax+00h]
0x180099efa  mov     edi, eax
0x180099efc  test    eax, eax
0x180099efe  js      loc_180099FB5
0x180099f04  movzx   edx, word ptr [rbp+UnicodeStringActualByteCount]
0x180099f08  movzx   eax, word ptr [rbx+2]
0x180099f0c  mov     [rbx], dx
0x180099f0f  lea     rcx, [rdx+2]
0x180099f13  cmp     rcx, rax
0x180099f16  ja      short loc_180099E9A
0x180099f18  mov     rcx, [rsi]
0x180099f1b  shr     rdx, 1
0x180099f1e  xor     eax, eax
0x180099f20  mov     [rcx+rdx*2], ax
0x180099f24  jmp     loc_180099E9A
0x180099f29  mov     [rbp+StringIn.Length], ax
0x180099f2d  mov     [rbp+StringIn.MaximumLength], ax
0x180099f31  mov     [rbp+StringIn.Buffer], rcx
0x180099f35  test    r14b, r14b
0x180099f38  jz      short loc_180099F8E
0x180099f3a  mov     r8, rbx; StringOut
0x180099f3d  lea     rdx, [rbp+StringIn]; StringIn
0x180099f41  mov     ecx, 3; Flags
0x180099f46  call    cs:__imp_RtlDuplicateUnicodeString
0x180099f4d  nop     dword ptr [rax+rax+00h]
0x180099f52  mov     edi, eax
0x180099f54  test    eax, eax
0x180099f56  js      loc_180099E9A
0x180099f5c  movzx   eax, word ptr [rbx]
0x180099f5f  mov     rcx, [rbx+8]
0x180099f63  shr     rax, 1
0x180099f66  lea     rdx, [rcx+rax*2]
0x180099f6a  jmp     short loc_180099F7A
0x180099f6c  movzx   eax, word ptr [rcx]
0x180099f6f  ror     ax, 8
0x180099f73  mov     [rcx], ax
0x180099f76  add     rcx, 2
0x180099f7a  cmp     rcx, rdx
0x180099f7d  jb      short loc_180099F6C
0x180099f7f  jmp     loc_180099E9A
0x180099f84  mov     edi, 0C0000017h
0x180099f89  jmp     loc_180099E9A
0x180099f8e  cmp     [rbx+2], ax
0x180099f92  jnb     short loc_180099F9E
0x180099f94  mov     edi, 0C0000023h
0x180099f99  jmp     loc_180099E9A
0x180099f9e  xor     edi, edi
0x180099fa0  lea     rdx, [rbp+StringIn]; SourceString
0x180099fa4  mov     rcx, rbx; DestinationString
0x180099fa7  call    cs:__imp_RtlCopyUnicodeString
0x180099fae  nop     dword ptr [rax+rax+00h]
0x180099fb3  jmp     short loc_180099F5C
0x180099fb5  test    r14b, r14b
0x180099fb8  jz      loc_180099E9A
0x180099fbe  mov     rcx, [rsi]
0x180099fc1  call    MincryptFree
0x180099fc6  xor     edx, edx; SourceString
0x180099fc8  mov     rcx, rbx; DestinationString
0x180099fcb  call    cs:__imp_RtlInitUnicodeString
0x180099fd2  nop     dword ptr [rax+rax+00h]
0x180099fd7  jmp     loc_180099E9A
```
