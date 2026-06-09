# MincryptStringToUnicodeString

- ea: `0x1800944d0`
- end: `0x18009467c`
- name: `MincryptStringToUnicodeString`
- size: `428`
- prototype: `__int64 __fastcall(PUNICODE_STRING DestinationString)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180065774`
- `0x180065ca0`
- `0x18006da7c`
- `0x1800725a0`
- `0x180093974`
- `0x1800957f8`
- `0x180095f80`

## callees

- `0x1800944d0`
- `0x180094684`
- `0x1800a737c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18009466b`
- `ntoskrnl!RtlInitUnicodeString` at `0x18009466b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180094647`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180094647`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800945e6`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800945e6`
- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x18009458e`
- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x18009458e`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x18009452c`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x18009452c`

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
0x1800944d0  push    rbp
0x1800944d2  push    rbx
0x1800944d3  push    rsi
0x1800944d4  push    rdi
0x1800944d5  push    r14
0x1800944d7  push    r15
0x1800944d9  mov     rbp, rsp
0x1800944dc  sub     rsp, 58h
0x1800944e0  mov     r15, rdx
0x1800944e3  mov     [rbp+UnicodeStringActualByteCount], 0
0x1800944ea  mov     dl, [rdx+0Ah]
0x1800944ed  xorps   xmm0, xmm0
0x1800944f0  xorps   xmm1, xmm1
0x1800944f3  mov     r14b, r8b
0x1800944f6  mov     rbx, rcx
0x1800944f9  lea     rdi, [r15+8]
0x1800944fd  movups  xmmword ptr [rbp+SourceString.Length], xmm0
0x180094501  movups  xmmword ptr [rbp+StringIn.Length], xmm1
0x180094505  cmp     dl, 0Ch
0x180094508  jz      short loc_18009454A
0x18009450a  movzx   eax, word ptr [rdi]
0x18009450d  mov     rcx, [r15]
0x180094510  cmp     dl, 1Eh
0x180094513  jz      loc_1800945C9
0x180094519  mov     [rbp+SourceString.Buffer], rcx
0x18009451d  lea     rdx, [rbp+SourceString]; SourceString
0x180094521  mov     rcx, rbx; DestinationString
0x180094524  mov     [rbp+SourceString.Length], ax
0x180094528  mov     [rbp+SourceString.MaximumLength], ax
0x18009452c  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180094533  nop     dword ptr [rax+rax+00h]
0x180094538  mov     edi, eax
0x18009453a  mov     eax, edi
0x18009453c  add     rsp, 58h
0x180094540  pop     r15
0x180094542  pop     r14
0x180094544  pop     rdi
0x180094545  pop     rsi
0x180094546  pop     rbx
0x180094547  pop     rbp
0x180094548  retn
0x18009454a  lea     rsi, [rcx+8]
0x18009454e  test    r14b, r14b
0x180094551  jz      short loc_180094579
0x180094553  movzx   ecx, word ptr [rdi]
0x180094556  lea     rcx, ds:2[rcx*2]
0x18009455e  call    MincryptAlloc
0x180094563  mov     [rsi], rax
0x180094566  test    rax, rax
0x180094569  jz      loc_180094624
0x18009456f  movzx   eax, word ptr [rdi]
0x180094572  add     ax, ax
0x180094575  mov     [rbx+2], ax
0x180094579  movzx   eax, word ptr [rdi]
0x18009457c  lea     r8, [rbp+UnicodeStringActualByteCount]; UnicodeStringActualByteCount
0x180094580  movzx   edx, word ptr [rbx+2]; UnicodeStringMaxByteCount
0x180094584  mov     r9, [r15]; UTF8StringSource
0x180094587  mov     rcx, [rsi]; UnicodeStringDestination
0x18009458a  mov     [rsp+58h+UTF8StringByteCount], eax; UTF8StringByteCount
0x18009458e  call    cs:__imp_RtlUTF8ToUnicodeN
0x180094595  nop     dword ptr [rax+rax+00h]
0x18009459a  mov     edi, eax
0x18009459c  test    eax, eax
0x18009459e  js      loc_180094655
0x1800945a4  movzx   edx, word ptr [rbp+UnicodeStringActualByteCount]
0x1800945a8  movzx   eax, word ptr [rbx+2]
0x1800945ac  mov     [rbx], dx
0x1800945af  lea     rcx, [rdx+2]
0x1800945b3  cmp     rcx, rax
0x1800945b6  ja      short loc_18009453A
0x1800945b8  mov     rcx, [rsi]
0x1800945bb  shr     rdx, 1
0x1800945be  xor     eax, eax
0x1800945c0  mov     [rcx+rdx*2], ax
0x1800945c4  jmp     loc_18009453A
0x1800945c9  mov     [rbp+StringIn.Length], ax
0x1800945cd  mov     [rbp+StringIn.MaximumLength], ax
0x1800945d1  mov     [rbp+StringIn.Buffer], rcx
0x1800945d5  test    r14b, r14b
0x1800945d8  jz      short loc_18009462E
0x1800945da  mov     r8, rbx; StringOut
0x1800945dd  lea     rdx, [rbp+StringIn]; StringIn
0x1800945e1  mov     ecx, 3; Flags
0x1800945e6  call    cs:__imp_RtlDuplicateUnicodeString
0x1800945ed  nop     dword ptr [rax+rax+00h]
0x1800945f2  mov     edi, eax
0x1800945f4  test    eax, eax
0x1800945f6  js      loc_18009453A
0x1800945fc  movzx   eax, word ptr [rbx]
0x1800945ff  mov     rcx, [rbx+8]
0x180094603  shr     rax, 1
0x180094606  lea     rdx, [rcx+rax*2]
0x18009460a  jmp     short loc_18009461A
0x18009460c  movzx   eax, word ptr [rcx]
0x18009460f  ror     ax, 8
0x180094613  mov     [rcx], ax
0x180094616  add     rcx, 2
0x18009461a  cmp     rcx, rdx
0x18009461d  jb      short loc_18009460C
0x18009461f  jmp     loc_18009453A
0x180094624  mov     edi, 0C0000017h
0x180094629  jmp     loc_18009453A
0x18009462e  cmp     [rbx+2], ax
0x180094632  jnb     short loc_18009463E
0x180094634  mov     edi, 0C0000023h
0x180094639  jmp     loc_18009453A
0x18009463e  xor     edi, edi
0x180094640  lea     rdx, [rbp+StringIn]; SourceString
0x180094644  mov     rcx, rbx; DestinationString
0x180094647  call    cs:__imp_RtlCopyUnicodeString
0x18009464e  nop     dword ptr [rax+rax+00h]
0x180094653  jmp     short loc_1800945FC
0x180094655  test    r14b, r14b
0x180094658  jz      loc_18009453A
0x18009465e  mov     rcx, [rsi]
0x180094661  call    MincryptFree
0x180094666  xor     edx, edx; SourceString
0x180094668  mov     rcx, rbx; DestinationString
0x18009466b  call    cs:__imp_RtlInitUnicodeString
0x180094672  nop     dword ptr [rax+rax+00h]
0x180094677  jmp     loc_18009453A
```
