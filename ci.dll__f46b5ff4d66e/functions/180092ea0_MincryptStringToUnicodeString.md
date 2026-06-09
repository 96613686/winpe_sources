# MincryptStringToUnicodeString

- ea: `0x180092ea0`
- end: `0x18009304c`
- name: `MincryptStringToUnicodeString`
- size: `428`
- prototype: `__int64 __fastcall(PUNICODE_STRING DestinationString)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180064e80`
- `0x1800653ac`
- `0x18006cca8`
- `0x1800712f0`
- `0x180092344`
- `0x1800941c8`
- `0x180094950`

## callees

- `0x180092ea0`
- `0x180093054`
- `0x1800a61ac`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18009303b`
- `ntoskrnl!RtlInitUnicodeString` at `0x18009303b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180093017`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180093017`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x180092fb6`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x180092fb6`
- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x180092f5e`
- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x180092f5e`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x180092efc`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x180092efc`

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
0x180092ea0  push    rbp
0x180092ea2  push    rbx
0x180092ea3  push    rsi
0x180092ea4  push    rdi
0x180092ea5  push    r14
0x180092ea7  push    r15
0x180092ea9  mov     rbp, rsp
0x180092eac  sub     rsp, 58h
0x180092eb0  mov     r15, rdx
0x180092eb3  mov     [rbp+UnicodeStringActualByteCount], 0
0x180092eba  mov     dl, [rdx+0Ah]
0x180092ebd  xorps   xmm0, xmm0
0x180092ec0  xorps   xmm1, xmm1
0x180092ec3  mov     r14b, r8b
0x180092ec6  mov     rbx, rcx
0x180092ec9  lea     rdi, [r15+8]
0x180092ecd  movups  xmmword ptr [rbp+SourceString.Length], xmm0
0x180092ed1  movups  xmmword ptr [rbp+StringIn.Length], xmm1
0x180092ed5  cmp     dl, 0Ch
0x180092ed8  jz      short loc_180092F1A
0x180092eda  movzx   eax, word ptr [rdi]
0x180092edd  mov     rcx, [r15]
0x180092ee0  cmp     dl, 1Eh
0x180092ee3  jz      loc_180092F99
0x180092ee9  mov     [rbp+SourceString.Buffer], rcx
0x180092eed  lea     rdx, [rbp+SourceString]; SourceString
0x180092ef1  mov     rcx, rbx; DestinationString
0x180092ef4  mov     [rbp+SourceString.Length], ax
0x180092ef8  mov     [rbp+SourceString.MaximumLength], ax
0x180092efc  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180092f03  nop     dword ptr [rax+rax+00h]
0x180092f08  mov     edi, eax
0x180092f0a  mov     eax, edi
0x180092f0c  add     rsp, 58h
0x180092f10  pop     r15
0x180092f12  pop     r14
0x180092f14  pop     rdi
0x180092f15  pop     rsi
0x180092f16  pop     rbx
0x180092f17  pop     rbp
0x180092f18  retn
0x180092f1a  lea     rsi, [rcx+8]
0x180092f1e  test    r14b, r14b
0x180092f21  jz      short loc_180092F49
0x180092f23  movzx   ecx, word ptr [rdi]
0x180092f26  lea     rcx, ds:2[rcx*2]
0x180092f2e  call    MincryptAlloc
0x180092f33  mov     [rsi], rax
0x180092f36  test    rax, rax
0x180092f39  jz      loc_180092FF4
0x180092f3f  movzx   eax, word ptr [rdi]
0x180092f42  add     ax, ax
0x180092f45  mov     [rbx+2], ax
0x180092f49  movzx   eax, word ptr [rdi]
0x180092f4c  lea     r8, [rbp+UnicodeStringActualByteCount]; UnicodeStringActualByteCount
0x180092f50  movzx   edx, word ptr [rbx+2]; UnicodeStringMaxByteCount
0x180092f54  mov     r9, [r15]; UTF8StringSource
0x180092f57  mov     rcx, [rsi]; UnicodeStringDestination
0x180092f5a  mov     [rsp+58h+UTF8StringByteCount], eax; UTF8StringByteCount
0x180092f5e  call    cs:__imp_RtlUTF8ToUnicodeN
0x180092f65  nop     dword ptr [rax+rax+00h]
0x180092f6a  mov     edi, eax
0x180092f6c  test    eax, eax
0x180092f6e  js      loc_180093025
0x180092f74  movzx   edx, word ptr [rbp+UnicodeStringActualByteCount]
0x180092f78  movzx   eax, word ptr [rbx+2]
0x180092f7c  mov     [rbx], dx
0x180092f7f  lea     rcx, [rdx+2]
0x180092f83  cmp     rcx, rax
0x180092f86  ja      short loc_180092F0A
0x180092f88  mov     rcx, [rsi]
0x180092f8b  shr     rdx, 1
0x180092f8e  xor     eax, eax
0x180092f90  mov     [rcx+rdx*2], ax
0x180092f94  jmp     loc_180092F0A
0x180092f99  mov     [rbp+StringIn.Length], ax
0x180092f9d  mov     [rbp+StringIn.MaximumLength], ax
0x180092fa1  mov     [rbp+StringIn.Buffer], rcx
0x180092fa5  test    r14b, r14b
0x180092fa8  jz      short loc_180092FFE
0x180092faa  mov     r8, rbx; StringOut
0x180092fad  lea     rdx, [rbp+StringIn]; StringIn
0x180092fb1  mov     ecx, 3; Flags
0x180092fb6  call    cs:__imp_RtlDuplicateUnicodeString
0x180092fbd  nop     dword ptr [rax+rax+00h]
0x180092fc2  mov     edi, eax
0x180092fc4  test    eax, eax
0x180092fc6  js      loc_180092F0A
0x180092fcc  movzx   eax, word ptr [rbx]
0x180092fcf  mov     rcx, [rbx+8]
0x180092fd3  shr     rax, 1
0x180092fd6  lea     rdx, [rcx+rax*2]
0x180092fda  jmp     short loc_180092FEA
0x180092fdc  movzx   eax, word ptr [rcx]
0x180092fdf  ror     ax, 8
0x180092fe3  mov     [rcx], ax
0x180092fe6  add     rcx, 2
0x180092fea  cmp     rcx, rdx
0x180092fed  jb      short loc_180092FDC
0x180092fef  jmp     loc_180092F0A
0x180092ff4  mov     edi, 0C0000017h
0x180092ff9  jmp     loc_180092F0A
0x180092ffe  cmp     [rbx+2], ax
0x180093002  jnb     short loc_18009300E
0x180093004  mov     edi, 0C0000023h
0x180093009  jmp     loc_180092F0A
0x18009300e  xor     edi, edi
0x180093010  lea     rdx, [rbp+StringIn]; SourceString
0x180093014  mov     rcx, rbx; DestinationString
0x180093017  call    cs:__imp_RtlCopyUnicodeString
0x18009301e  nop     dword ptr [rax+rax+00h]
0x180093023  jmp     short loc_180092FCC
0x180093025  test    r14b, r14b
0x180093028  jz      loc_180092F0A
0x18009302e  mov     rcx, [rsi]
0x180093031  call    MincryptFree
0x180093036  xor     edx, edx; SourceString
0x180093038  mov     rcx, rbx; DestinationString
0x18009303b  call    cs:__imp_RtlInitUnicodeString
0x180093042  nop     dword ptr [rax+rax+00h]
0x180093047  jmp     loc_180092F0A
```
