# DiskGetGuidSymbolicLinkName

- ea: `0x1400159c0`
- end: `0x140015a87`
- name: `DiskGetGuidSymbolicLinkName`
- size: `199`
- prototype: `NTSTATUS __fastcall(const GUID *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x14000e170`
- `0x1400111d0`

## callees

- `0x14000572c`
- `0x1400159c0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x140015a68`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140015a68`
- `ntoskrnl!RtlStringFromGUID` at `0x1400159d6`
- `ntoskrnl!RtlStringFromGUID` at `0x1400159d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015a57`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015a57`
- `ntoskrnl!ExAllocatePool2` at `0x140015a04`
- `ntoskrnl!ExAllocatePool2` at `0x140015a04`
- `ntoskrnl!RtlInitUnicodeString` at `0x140015a44`
- `ntoskrnl!RtlInitUnicodeString` at `0x140015a44`

## pseudocode

```c
NTSTATUS __fastcall DiskGetGuidSymbolicLinkName(const GUID *a1, struct _UNICODE_STRING *a2)
{
  NTSTATUS result; // eax
  wchar_t *Pool2; // rax
  wchar_t *v5; // rdi
  NTSTATUS v6; // esi
  struct _UNICODE_STRING GuidString; // [rsp+20h] [rbp-18h] BYREF

  GuidString = 0;
  result = RtlStringFromGUID(a1, &GuidString);
  if ( result >= 0 )
  {
    Pool2 = (wchar_t *)ExAllocatePool2(64, 106, 541352787);
    v5 = Pool2;
    if ( Pool2 )
    {
      v6 = RtlStringCbPrintfW(Pool2, 0x6Au, L"\\Global??\\Disk%s", GuidString.Buffer);
      if ( v6 < 0 )
        ExFreePoolWithTag(v5, 0);
      else
        RtlInitUnicodeString(a2, v5);
    }
    else
    {
      v6 = -1073741670;
    }
    RtlFreeUnicodeString(&GuidString);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x1400159c0  push    rbx
0x1400159c2  sub     rsp, 30h
0x1400159c6  mov     rbx, rdx
0x1400159c9  xorps   xmm0, xmm0
0x1400159cc  lea     rdx, [rsp+38h+GuidString]; GuidString
0x1400159d1  movups  xmmword ptr [rsp+38h+GuidString.Length], xmm0
0x1400159d6  call    cs:__imp_RtlStringFromGUID
0x1400159dd  nop     dword ptr [rax+rax+00h]
0x1400159e2  test    eax, eax
0x1400159e4  js      loc_140015A80
0x1400159ea  mov     [rsp+38h+arg_0], rsi
0x1400159ef  mov     edx, 6Ah ; 'j'
0x1400159f4  mov     ecx, 40h ; '@'
0x1400159f9  mov     [rsp+38h+arg_8], rdi
0x1400159fe  mov     r8d, 20446353h
0x140015a04  call    cs:__imp_ExAllocatePool2
0x140015a0b  nop     dword ptr [rax+rax+00h]
0x140015a10  mov     rdi, rax
0x140015a13  test    rax, rax
0x140015a16  jnz     short loc_140015A1F
0x140015a18  mov     esi, 0C000009Ah
0x140015a1d  jmp     short loc_140015A63
0x140015a1f  mov     r9, [rsp+38h+GuidString.Buffer]
0x140015a24  lea     r8, aGlobalDiskS; "\\Global??\\Disk%s"
0x140015a2b  mov     edx, 6Ah ; 'j'; cbDest
0x140015a30  mov     rcx, rdi; pszDest
0x140015a33  call    RtlStringCbPrintfW
0x140015a38  mov     esi, eax
0x140015a3a  test    eax, eax
0x140015a3c  js      short loc_140015A52
0x140015a3e  mov     rdx, rdi; SourceString
0x140015a41  mov     rcx, rbx; DestinationString
0x140015a44  call    cs:__imp_RtlInitUnicodeString
0x140015a4b  nop     dword ptr [rax+rax+00h]
0x140015a50  jmp     short loc_140015A63
0x140015a52  xor     edx, edx; Tag
0x140015a54  mov     rcx, rdi; P
0x140015a57  call    cs:__imp_ExFreePoolWithTag
0x140015a5e  nop     dword ptr [rax+rax+00h]
0x140015a63  lea     rcx, [rsp+38h+GuidString]; UnicodeString
0x140015a68  call    cs:__imp_RtlFreeUnicodeString
0x140015a6f  nop     dword ptr [rax+rax+00h]
0x140015a74  mov     rdi, [rsp+38h+arg_8]
0x140015a79  mov     eax, esi
0x140015a7b  mov     rsi, [rsp+38h+arg_0]
0x140015a80  add     rsp, 30h
0x140015a84  pop     rbx
0x140015a85  retn
```
