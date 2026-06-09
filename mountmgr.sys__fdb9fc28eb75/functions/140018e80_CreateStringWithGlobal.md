# CreateStringWithGlobal

- ea: `0x140018e80`
- end: `0x1400190d8`
- name: `CreateStringWithGlobal`
- size: `600`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2, UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140018cd0`
- `0x140018da0`

## callees

- `0x140001b30`
- `0x140002f80`
- `0x140018e80`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140018ea7`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140018f82`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140018ea7`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140018f82`
- `ntoskrnl!ExAllocatePool2` at `0x140018ee7`
- `ntoskrnl!ExAllocatePool2` at `0x140018fc2`
- `ntoskrnl!ExAllocatePool2` at `0x140019061`
- `ntoskrnl!ExAllocatePool2` at `0x140018ee7`
- `ntoskrnl!ExAllocatePool2` at `0x140018fc2`
- `ntoskrnl!ExAllocatePool2` at `0x140019061`

## pseudocode

```c
__int64 __fastcall CreateStringWithGlobal(PCUNICODE_STRING String2, UNICODE_STRING *a2)
{
  WCHAR *Pool2; // rax
  WCHAR *v5; // r14
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rdi
  WCHAR *v9; // rax
  WCHAR *v10; // r14
  __int64 v11; // rbx
  WCHAR *v12; // rax
  __int64 result; // rax
  UNICODE_STRING v14; // [rsp+20h] [rbp-38h]

  *(_DWORD *)(&v14.MaximumLength + 1) = 0;
  if ( RtlPrefixUnicodeString(&::String2, String2, 1u) )
  {
    v14.Length = word_140007010 + String2->Length - ::String2.Length;
    v14.MaximumLength = v14.Length + 2;
    Pool2 = (WCHAR *)ExAllocatePool2(258, (unsigned __int16)(v14.Length + 2), 1098149453);
    v14.Buffer = Pool2;
    v5 = Pool2;
    if ( !Pool2 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
        return 3221225626LL;
      v7 = 10;
LABEL_17:
      WPP_SF_(v6->AttachedDevice, v7);
      return 3221225626LL;
    }
    v8 = (unsigned __int16)word_140007010;
    memmove(Pool2, off_140007018, (unsigned __int16)word_140007010);
    memmove(
      (char *)v5 + v8,
      (char *)String2->Buffer + ::String2.Length,
      String2->Length - (unsigned __int64)::String2.Length);
    v5[(unsigned __int64)v14.Length >> 1] = 0;
  }
  else if ( RtlPrefixUnicodeString(&stru_140007048, String2, 1u) )
  {
    v14.Length = word_140007010 + String2->Length - stru_140007048.Length;
    v14.MaximumLength = v14.Length + 2;
    v9 = (WCHAR *)ExAllocatePool2(258, (unsigned __int16)(v14.Length + 2), 1098149453);
    v14.Buffer = v9;
    v10 = v9;
    if ( !v9 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
        return 3221225626LL;
      v7 = 11;
      goto LABEL_17;
    }
    v11 = (unsigned __int16)word_140007010;
    memmove(v9, off_140007018, (unsigned __int16)word_140007010);
    memmove(
      (char *)v10 + v11,
      (char *)String2->Buffer + stru_140007048.Length,
      String2->Length - (unsigned __int64)stru_140007048.Length);
    v10[(unsigned __int64)v14.Length >> 1] = 0;
  }
  else
  {
    v14 = *String2;
    v12 = (WCHAR *)ExAllocatePool2(258, WORD1(*(_QWORD *)&String2->Length), 1098149453);
    v14.Buffer = v12;
    if ( !v12 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
        return 3221225626LL;
      v7 = 12;
      goto LABEL_17;
    }
    memmove(v12, String2->Buffer, String2->MaximumLength);
  }
  result = 0;
  *a2 = v14;
  return result;
}

```

## disassembly

```asm
0x140018e80  push    rbx
0x140018e82  push    rbp
0x140018e83  push    rsi
0x140018e84  push    rdi
0x140018e85  push    r14
0x140018e87  sub     rsp, 30h
0x140018e8b  mov     rbp, rdx
0x140018e8e  mov     qword ptr [rsp+58h+var_38.Length], 0
0x140018e97  mov     rdx, rcx; String2
0x140018e9a  mov     rsi, rcx
0x140018e9d  lea     rcx, String2; String1
0x140018ea4  mov     r8b, 1; CaseInSensitive
0x140018ea7  call    cs:__imp_RtlPrefixUnicodeString
0x140018eae  nop     dword ptr [rax+rax+00h]
0x140018eb3  test    al, al
0x140018eb5  jz      loc_140018F75
0x140018ebb  movzx   ebx, word ptr [rsi]
0x140018ebe  mov     ecx, 102h
0x140018ec3  sub     bx, cs:String2.Length
0x140018eca  mov     r8d, 41746E4Dh
0x140018ed0  add     bx, cs:word_140007010
0x140018ed7  mov     [rsp+58h+var_38.Length], bx
0x140018edc  lea     eax, [rbx+2]
0x140018edf  movzx   edx, ax
0x140018ee2  mov     [rsp+58h+var_38.MaximumLength], dx
0x140018ee7  call    cs:__imp_ExAllocatePool2
0x140018eee  nop     dword ptr [rax+rax+00h]
0x140018ef3  mov     [rsp+58h+var_38.Buffer], rax
0x140018ef8  mov     r14, rax
0x140018efb  test    rax, rax
0x140018efe  jnz     short loc_140018F2C
0x140018f00  mov     rcx, cs:WPP_GLOBAL_Control
0x140018f07  lea     rax, WPP_GLOBAL_Control
0x140018f0e  cmp     rcx, rax
0x140018f11  jz      loc_14001909F
0x140018f17  mov     eax, [rcx+2Ch]
0x140018f1a  test    al, 4
0x140018f1c  jz      loc_14001909F
0x140018f22  mov     edx, 0Ah
0x140018f27  jmp     loc_140019096
0x140018f2c  movzx   edi, cs:word_140007010
0x140018f33  mov     rcx, r14; void *
0x140018f36  mov     rdx, cs:off_140007018; Src
0x140018f3d  mov     r8d, edi; Size
0x140018f40  call    memmove
0x140018f45  movzx   ecx, cs:String2.Length
0x140018f4c  movzx   r8d, word ptr [rsi]
0x140018f50  mov     rdx, [rsi+8]
0x140018f54  sub     r8, rcx; Size
0x140018f57  add     rdx, rcx; Src
0x140018f5a  lea     rcx, [rdi+r14]; void *
0x140018f5e  call    memmove
0x140018f63  movzx   ecx, bx
0x140018f66  shr     rcx, 1
0x140018f69  xor     eax, eax
0x140018f6b  mov     [r14+rcx*2], ax
0x140018f70  jmp     loc_1400190C1
0x140018f75  mov     r8b, 1; CaseInSensitive
0x140018f78  lea     rcx, stru_140007048; String1
0x140018f7f  mov     rdx, rsi; String2
0x140018f82  call    cs:__imp_RtlPrefixUnicodeString
0x140018f89  nop     dword ptr [rax+rax+00h]
0x140018f8e  mov     ecx, 102h
0x140018f93  mov     r8d, 41746E4Dh
0x140018f99  test    al, al
0x140018f9b  jz      loc_14001904D
0x140018fa1  movzx   edi, word ptr [rsi]
0x140018fa4  sub     di, cs:stru_140007048.Length
0x140018fab  add     di, cs:word_140007010
0x140018fb2  mov     [rsp+58h+var_38.Length], di
0x140018fb7  lea     eax, [rdi+2]
0x140018fba  movzx   edx, ax
0x140018fbd  mov     [rsp+58h+var_38.MaximumLength], dx
0x140018fc2  call    cs:__imp_ExAllocatePool2
0x140018fc9  nop     dword ptr [rax+rax+00h]
0x140018fce  mov     [rsp+58h+var_38.Buffer], rax
0x140018fd3  mov     r14, rax
0x140018fd6  test    rax, rax
0x140018fd9  jnz     short loc_140019007
0x140018fdb  mov     rcx, cs:WPP_GLOBAL_Control
0x140018fe2  lea     rax, WPP_GLOBAL_Control
0x140018fe9  cmp     rcx, rax
0x140018fec  jz      loc_14001909F
0x140018ff2  mov     eax, [rcx+2Ch]
0x140018ff5  test    al, 4
0x140018ff7  jz      loc_14001909F
0x140018ffd  mov     edx, 0Bh
0x140019002  jmp     loc_140019096
0x140019007  movzx   ebx, cs:word_140007010
0x14001900e  mov     rcx, r14; void *
0x140019011  mov     rdx, cs:off_140007018; Src
0x140019018  mov     r8d, ebx; Size
0x14001901b  call    memmove
0x140019020  movzx   ecx, cs:stru_140007048.Length
0x140019027  movzx   r8d, word ptr [rsi]
0x14001902b  mov     rdx, [rsi+8]
0x14001902f  sub     r8, rcx; Size
0x140019032  add     rdx, rcx; Src
0x140019035  lea     rcx, [rbx+r14]; void *
0x140019039  call    memmove
0x14001903e  movzx   ecx, di
0x140019041  shr     rcx, 1
0x140019044  xor     eax, eax
0x140019046  mov     [r14+rcx*2], ax
0x14001904b  jmp     short loc_1400190C1
0x14001904d  movups  xmm0, xmmword ptr [rsi]
0x140019050  movq    rax, xmm0
0x140019055  shr     rax, 10h
0x140019059  movzx   edx, ax
0x14001905c  movups  xmmword ptr [rsp+58h+var_38.Length], xmm0
0x140019061  call    cs:__imp_ExAllocatePool2
0x140019068  nop     dword ptr [rax+rax+00h]
0x14001906d  mov     [rsp+58h+var_38.Buffer], rax
0x140019072  test    rax, rax
0x140019075  jnz     short loc_1400190B0
0x140019077  mov     rcx, cs:WPP_GLOBAL_Control
0x14001907e  lea     rax, WPP_GLOBAL_Control
0x140019085  cmp     rcx, rax
0x140019088  jz      short loc_14001909F
0x14001908a  mov     eax, [rcx+2Ch]
0x14001908d  test    al, 4
0x14001908f  jz      short loc_14001909F
0x140019091  mov     edx, 0Ch
0x140019096  mov     rcx, [rcx+18h]
0x14001909a  call    WPP_SF_
0x14001909f  mov     eax, 0C000009Ah
0x1400190a4  add     rsp, 30h
0x1400190a8  pop     r14
0x1400190aa  pop     rdi
0x1400190ab  pop     rsi
0x1400190ac  pop     rbp
0x1400190ad  pop     rbx
0x1400190ae  retn
0x1400190b0  movzx   r8d, word ptr [rsi+2]; Size
0x1400190b5  mov     rcx, rax; void *
0x1400190b8  mov     rdx, [rsi+8]; Src
0x1400190bc  call    memmove
0x1400190c1  movups  xmm0, xmmword ptr [rsp+58h+var_38.Length]
0x1400190c6  xor     eax, eax
0x1400190c8  movups  xmmword ptr [rbp+0], xmm0
0x1400190cc  add     rsp, 30h
0x1400190d0  pop     r14
0x1400190d2  pop     rdi
0x1400190d3  pop     rsi
0x1400190d4  pop     rbp
0x1400190d5  pop     rbx
0x1400190d6  retn
```
