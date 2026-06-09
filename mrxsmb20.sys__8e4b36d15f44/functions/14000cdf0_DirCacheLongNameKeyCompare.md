# DirCacheLongNameKeyCompare

- ea: `0x14000cdf0`
- end: `0x14000cf9a`
- name: `DirCacheLongNameKeyCompare`
- size: `426`
- prototype: `int __cdecl(void *, const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000cdf0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14000cf34`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000cf34`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000ce0a`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000ce0a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000ceba`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000cedd`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000cefa`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000cf19`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000ceba`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000cedd`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000cefa`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000cf19`

## pseudocode

```c
LONG __fastcall DirCacheLongNameKeyCompare(_QWORD *a1, const UNICODE_STRING *a2, unsigned int *a3)
{
  unsigned int v3; // ebx
  CCHAR MostSignificantBit; // al
  __int64 v7; // r8
  unsigned int v8; // r9d
  unsigned int v9; // eax
  __int64 v10; // rdx
  UNICODE_STRING String1; // [rsp+20h] [rbp-18h] BYREF

  v3 = *a3;
  MostSignificantBit = RtlFindMostSignificantBit(*a3);
  v7 = 0;
  if ( MostSignificantBit <= 4 )
  {
    v8 = 0;
  }
  else
  {
    v8 = (unsigned int)(MostSignificantBit - 3) >> 1;
    if ( v8 >= 8 )
      goto LABEL_16;
  }
  _mm_lfence();
  v9 = v3;
  if ( v8 )
    v9 = v3 - (32 << (2 * v8 - 2));
  v10 = a1[v8 + 19];
  if ( v10 && v3 < *((_DWORD *)a1 + 54) )
  {
    v7 = v10 + (v9 << 7);
    goto LABEL_8;
  }
LABEL_16:
  __int2c();
LABEL_8:
  String1 = 0;
  String1.MaximumLength = 2 * (*(_WORD *)(v7 + 86) >> 4);
  String1.Length = String1.MaximumLength;
  String1.Buffer = (PWSTR)(v7 + 2 * ((*(_WORD *)(v7 + 86) & 0xF) + 44LL));
  if ( !RtlEqualUnicodeString(a2, &String2, 0) )
  {
    if ( RtlEqualUnicodeString(&String1, &String2, 0) )
      return 1;
    if ( !RtlEqualUnicodeString(a2, &stru_14003E010, 0) )
    {
      if ( !RtlEqualUnicodeString(&String1, &stru_14003E010, 0) )
        return RtlCompareUnicodeString(a2, &String1, 1u);
      return 1;
    }
  }
  return -1;
}

```

## disassembly

```asm
0x14000cdf0  mov     [rsp+arg_0], rbx
0x14000cdf5  mov     [rsp+arg_8], rsi
0x14000cdfa  push    rdi
0x14000cdfb  sub     rsp, 30h
0x14000cdff  mov     ebx, [r8]
0x14000ce02  mov     rdi, rcx
0x14000ce05  mov     ecx, ebx; Set
0x14000ce07  mov     rsi, rdx
0x14000ce0a  call    cs:__imp_RtlFindMostSignificantBit
0x14000ce11  nop     dword ptr [rax+rax+00h]
0x14000ce16  xor     r8d, r8d
0x14000ce19  cmp     al, 4
0x14000ce1b  jle     loc_14000CF51
0x14000ce21  movsx   r9d, al
0x14000ce25  sub     r9d, 3
0x14000ce29  shr     r9d, 1
0x14000ce2c  cmp     r9d, 8
0x14000ce30  jnb     loc_14000CF93
0x14000ce36  lfence
0x14000ce39  mov     eax, ebx
0x14000ce3b  test    r9d, r9d
0x14000ce3e  jz      short loc_14000CE51
0x14000ce40  lea     ecx, ds:0FFFFFFFFFFFFFFFEh[r9*2]
0x14000ce48  mov     edx, 20h ; ' '
0x14000ce4d  shl     edx, cl
0x14000ce4f  sub     eax, edx
0x14000ce51  mov     ecx, r9d
0x14000ce54  mov     rdx, [rdi+rcx*8+98h]
0x14000ce5c  test    rdx, rdx
0x14000ce5f  jz      loc_14000CF85
0x14000ce65  cmp     ebx, [rdi+0D8h]
0x14000ce6b  jnb     loc_14000CF8C
0x14000ce71  shl     eax, 7
0x14000ce74  mov     r8d, eax
0x14000ce77  add     r8, rdx
0x14000ce7a  xorps   xmm0, xmm0
0x14000ce7d  lea     rdx, String2; String2
0x14000ce84  movups  xmmword ptr [rsp+38h+String1.Length], xmm0
0x14000ce89  movzx   eax, word ptr [r8+56h]
0x14000ce8e  mov     rcx, rsi; String1
0x14000ce91  shr     ax, 4
0x14000ce95  add     ax, ax
0x14000ce98  mov     [rsp+38h+String1.MaximumLength], ax
0x14000ce9d  mov     [rsp+38h+String1.Length], ax
0x14000cea2  movzx   eax, word ptr [r8+56h]
0x14000cea7  and     eax, 0Fh
0x14000ceaa  add     rax, 2Ch ; ','
0x14000ceae  lea     rax, [r8+rax*2]
0x14000ceb2  xor     r8d, r8d; CaseInSensitive
0x14000ceb5  mov     [rsp+38h+String1.Buffer], rax
0x14000ceba  call    cs:__imp_RtlEqualUnicodeString
0x14000cec1  nop     dword ptr [rax+rax+00h]
0x14000cec6  test    al, al
0x14000cec8  jnz     loc_14000CF6F
0x14000cece  xor     r8d, r8d; CaseInSensitive
0x14000ced1  lea     rdx, String2; String2
0x14000ced8  lea     rcx, [rsp+38h+String1]; String1
0x14000cedd  call    cs:__imp_RtlEqualUnicodeString
0x14000cee4  nop     dword ptr [rax+rax+00h]
0x14000cee9  test    al, al
0x14000ceeb  jnz     short loc_14000CF59
0x14000ceed  xor     r8d, r8d; CaseInSensitive
0x14000cef0  lea     rdx, stru_14003E010; String2
0x14000cef7  mov     rcx, rsi; String1
0x14000cefa  call    cs:__imp_RtlEqualUnicodeString
0x14000cf01  nop     dword ptr [rax+rax+00h]
0x14000cf06  test    al, al
0x14000cf08  jnz     short loc_14000CF6F
0x14000cf0a  xor     r8d, r8d; CaseInSensitive
0x14000cf0d  lea     rdx, stru_14003E010; String2
0x14000cf14  lea     rcx, [rsp+38h+String1]; String1
0x14000cf19  call    cs:__imp_RtlEqualUnicodeString
0x14000cf20  nop     dword ptr [rax+rax+00h]
0x14000cf25  test    al, al
0x14000cf27  jnz     short loc_14000CF59
0x14000cf29  mov     r8b, 1; CaseInSensitive
0x14000cf2c  lea     rdx, [rsp+38h+String1]; String2
0x14000cf31  mov     rcx, rsi; String1
0x14000cf34  call    cs:__imp_RtlCompareUnicodeString
0x14000cf3b  nop     dword ptr [rax+rax+00h]
0x14000cf40  mov     rbx, [rsp+38h+arg_0]
0x14000cf45  mov     rsi, [rsp+38h+arg_8]
0x14000cf4a  add     rsp, 30h
0x14000cf4e  pop     rdi
0x14000cf4f  retn
0x14000cf51  mov     r9d, r8d
0x14000cf54  jmp     loc_14000CE36
0x14000cf59  mov     eax, 1
0x14000cf5e  mov     rbx, [rsp+38h+arg_0]
0x14000cf63  mov     rsi, [rsp+38h+arg_8]
0x14000cf68  add     rsp, 30h
0x14000cf6c  pop     rdi
0x14000cf6d  retn
0x14000cf6f  mov     rbx, [rsp+38h+arg_0]
0x14000cf74  mov     eax, 0FFFFFFFFh
0x14000cf79  mov     rsi, [rsp+38h+arg_8]
0x14000cf7e  add     rsp, 30h
0x14000cf82  pop     rdi
0x14000cf83  retn
0x14000cf85  int     2Ch; Windows NT - assertion failure
0x14000cf87  jmp     loc_14000CE7A
0x14000cf8c  int     2Ch; Windows NT - assertion failure
0x14000cf8e  jmp     loc_14000CE7A
0x14000cf93  int     2Ch; Windows NT - assertion failure
0x14000cf95  jmp     loc_14000CE7A
```
