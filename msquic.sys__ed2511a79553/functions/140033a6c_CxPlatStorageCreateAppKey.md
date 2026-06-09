# CxPlatStorageCreateAppKey

- ea: `0x140033a6c`
- end: `0x140033bf5`
- name: `CxPlatStorageCreateAppKey`
- size: `393`
- prototype: `__int64 __fastcall(PCCH UTF8StringSource)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140033bfc`

## callees

- `0x140033a6c`
- `0x14003e928`
- `0x14003ed00`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140033b68`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140033b68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033bbf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033bbf`
- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x140033ab4`
- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x140033b8d`
- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x140033ab4`
- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x140033b8d`
- `ntoskrnl!ExAllocatePool2` at `0x140033b0e`
- `ntoskrnl!ExAllocatePool2` at `0x140033b0e`

## pseudocode

```c
__int64 __fastcall CxPlatStorageCreateAppKey(PCCH UTF8StringSource, struct _UNICODE_STRING **a2)
{
  unsigned __int64 UTF8StringByteCount; // rdi
  NTSTATUS v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // ebx
  ULONG v10; // eax
  struct _UNICODE_STRING *Pool2; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  struct _UNICODE_STRING *v14; // rbx
  NTSTATUS v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  unsigned int v18; // edi
  ULONG UnicodeStringActualByteCount; // [rsp+60h] [rbp+18h] BYREF

  UTF8StringByteCount = -1;
  do
    ++UTF8StringByteCount;
  while ( UTF8StringSource[UTF8StringByteCount] );
  if ( UTF8StringByteCount > 0xFFFF )
    return 3221225485LL;
  UnicodeStringActualByteCount = 0;
  v5 = RtlUTF8ToUnicodeN(0, 0, &UnicodeStringActualByteCount, UTF8StringSource, UTF8StringByteCount);
  v8 = v5;
  if ( v5 < 0 )
  {
    if ( (Microsoft_QuicEnableBits & 4) != 0 )
      McTemplateU0qs_EtwWriteTransfer(v7, v6, (unsigned int)v5, "RtlUTF8ToUnicodeN failed");
    return v8;
  }
  v10 = UnicodeStringActualByteCount + 140;
  UnicodeStringActualByteCount = v10;
  if ( v10 > 0xFFFF )
    return 3221225485LL;
  Pool2 = (struct _UNICODE_STRING *)ExAllocatePool2(258, v10 + 16LL, 942826321);
  v14 = Pool2;
  if ( Pool2 )
  {
    Pool2->Buffer = &Pool2[1].Length;
    Pool2->MaximumLength = UnicodeStringActualByteCount;
    Pool2->Length = 0;
    RtlCopyUnicodeString(Pool2, &BaseKeyPath);
    v15 = RtlUTF8ToUnicodeN(
            (PWSTR)((char *)v14->Buffer + v14->Length),
            v14->MaximumLength - v14->Length,
            &UnicodeStringActualByteCount,
            UTF8StringSource,
            UTF8StringByteCount);
    v18 = v15;
    if ( v15 >= 0 )
    {
      v14->Length += UnicodeStringActualByteCount;
      *a2 = v14;
    }
    else
    {
      if ( (Microsoft_QuicEnableBits & 4) != 0 )
        McTemplateU0qs_EtwWriteTransfer(v17, v16, (unsigned int)v15, "RtlUTF8ToUnicodeN failed");
      ExFreePoolWithTag(v14, 0x38326351u);
    }
    return v18;
  }
  else
  {
    if ( (Microsoft_QuicEnableBits & 2) != 0 )
      McTemplateU0sx_EtwWriteTransfer(
        v13,
        v12,
        "UnicodeString for app storage key",
        UnicodeStringActualByteCount + 16LL);
    return 3221225495LL;
  }
}

```

## disassembly

```asm
0x140033a6c  mov     [rsp+arg_0], rbx
0x140033a71  mov     [rsp+arg_8], rbp
0x140033a76  push    rsi
0x140033a77  push    rdi
0x140033a78  push    r14
0x140033a7a  sub     rsp, 30h
0x140033a7e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140033a82  mov     r14, rdx
0x140033a85  xor     ebp, ebp
0x140033a87  mov     rsi, rcx
0x140033a8a  inc     rdi
0x140033a8d  cmp     [rcx+rdi], bpl
0x140033a91  jnz     short loc_140033A8A
0x140033a93  cmp     rdi, 0FFFFh
0x140033a9a  ja      loc_140033BDC
0x140033aa0  mov     r9, rsi; UTF8StringSource
0x140033aa3  mov     [rsp+48h+UnicodeStringActualByteCount], ebp
0x140033aa7  lea     r8, [rsp+48h+UnicodeStringActualByteCount]; UnicodeStringActualByteCount
0x140033aac  mov     [rsp+48h+UTF8StringByteCount], edi; UTF8StringByteCount
0x140033ab0  xor     edx, edx; UnicodeStringMaxByteCount
0x140033ab2  xor     ecx, ecx; UnicodeStringDestination
0x140033ab4  call    cs:__imp_RtlUTF8ToUnicodeN
0x140033abb  nop     dword ptr [rax+rax+00h]
0x140033ac0  mov     ebx, eax
0x140033ac2  test    eax, eax
0x140033ac4  jns     short loc_140033AE5
0x140033ac6  test    cs:Microsoft_QuicEnableBits, 4
0x140033acd  jz      short loc_140033ADE
0x140033acf  lea     r9, aRtlutf8tounico; "RtlUTF8ToUnicodeN failed"
0x140033ad6  mov     r8d, eax
0x140033ad9  call    McTemplateU0qs_EtwWriteTransfer
0x140033ade  mov     eax, ebx
0x140033ae0  jmp     loc_140033BE1
0x140033ae5  mov     eax, [rsp+48h+UnicodeStringActualByteCount]
0x140033ae9  add     eax, 8Ch
0x140033aee  mov     [rsp+48h+UnicodeStringActualByteCount], eax
0x140033af2  cmp     eax, 0FFFFh
0x140033af7  ja      loc_140033BDC
0x140033afd  mov     edx, eax
0x140033aff  mov     ecx, 102h
0x140033b04  add     rdx, 10h
0x140033b08  mov     r8d, 38326351h
0x140033b0e  call    cs:__imp_ExAllocatePool2
0x140033b15  nop     dword ptr [rax+rax+00h]
0x140033b1a  mov     rbx, rax
0x140033b1d  test    rax, rax
0x140033b20  jnz     short loc_140033B4A
0x140033b22  test    cs:Microsoft_QuicEnableBits, 2
0x140033b29  jz      short loc_140033B40
0x140033b2b  mov     r9d, [rsp+48h+UnicodeStringActualByteCount]
0x140033b30  lea     r8, aUnicodestringF_0; "UnicodeString for app storage key"
0x140033b37  add     r9, 10h
0x140033b3b  call    McTemplateU0sx_EtwWriteTransfer
0x140033b40  mov     eax, 0C0000017h
0x140033b45  jmp     loc_140033BE1
0x140033b4a  add     rax, 10h
0x140033b4e  lea     rdx, BaseKeyPath; SourceString
0x140033b55  mov     [rbx+8], rax
0x140033b59  mov     rcx, rbx; DestinationString
0x140033b5c  movzx   eax, word ptr [rsp+48h+UnicodeStringActualByteCount]
0x140033b61  mov     [rbx+2], ax
0x140033b65  mov     [rbx], bp
0x140033b68  call    cs:__imp_RtlCopyUnicodeString
0x140033b6f  nop     dword ptr [rax+rax+00h]
0x140033b74  movzx   ecx, word ptr [rbx]
0x140033b77  lea     r8, [rsp+48h+UnicodeStringActualByteCount]; UnicodeStringActualByteCount
0x140033b7c  movzx   edx, word ptr [rbx+2]
0x140033b80  mov     r9, rsi; UTF8StringSource
0x140033b83  sub     edx, ecx; UnicodeStringMaxByteCount
0x140033b85  mov     [rsp+48h+UTF8StringByteCount], edi; UTF8StringByteCount
0x140033b89  add     rcx, [rbx+8]; UnicodeStringDestination
0x140033b8d  call    cs:__imp_RtlUTF8ToUnicodeN
0x140033b94  nop     dword ptr [rax+rax+00h]
0x140033b99  mov     edi, eax
0x140033b9b  test    eax, eax
0x140033b9d  jns     short loc_140033BCF
0x140033b9f  test    cs:Microsoft_QuicEnableBits, 4
0x140033ba6  jz      short loc_140033BB7
0x140033ba8  lea     r9, aRtlutf8tounico; "RtlUTF8ToUnicodeN failed"
0x140033baf  mov     r8d, eax
0x140033bb2  call    McTemplateU0qs_EtwWriteTransfer
0x140033bb7  mov     edx, 38326351h; Tag
0x140033bbc  mov     rcx, rbx; P
0x140033bbf  call    cs:__imp_ExFreePoolWithTag
0x140033bc6  nop     dword ptr [rax+rax+00h]
0x140033bcb  mov     eax, edi
0x140033bcd  jmp     short loc_140033BE1
0x140033bcf  movzx   eax, word ptr [rsp+48h+UnicodeStringActualByteCount]
0x140033bd4  add     [rbx], ax
0x140033bd7  mov     [r14], rbx
0x140033bda  jmp     short loc_140033BCB
0x140033bdc  mov     eax, 0C000000Dh
0x140033be1  mov     rbx, [rsp+48h+arg_0]
0x140033be6  mov     rbp, [rsp+48h+arg_8]
0x140033beb  add     rsp, 30h
0x140033bef  pop     r14
0x140033bf1  pop     rdi
0x140033bf2  pop     rsi
0x140033bf3  retn
```
