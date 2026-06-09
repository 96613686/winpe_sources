# RtlpWow64SelectSystem32PathInternal

- ea: `0x1800eaf48`
- end: `0x1800eb0a2`
- name: `RtlpWow64SelectSystem32PathInternal`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180078fa0`

## callees

- `0x1800c4700`
- `0x1800eaf48`
- `0x18012d320`

## string_xrefs

- `0x1800eafc8`: `\System32\`
- `0x1800eb023`: `System32`

## pseudocode

```c
__int64 __fastcall RtlpWow64SelectSystem32PathInternal(unsigned __int16 a1, char a2, UNICODE_STRING *a3)
{
  const wchar_t *v5; // rcx
  size_t v6; // rax
  __int16 v7; // dx
  size_t v8; // rax
  const wchar_t *v10; // rcx
  size_t v11; // rax
  const wchar_t *v12; // rcx
  const WCHAR *v13; // rdx

  switch ( a1 )
  {
    case 1u:
      goto LABEL_10;
    case 0x14Cu:
      *(_QWORD *)&a3->Length = 0;
      if ( a2 )
      {
        v5 = L"\\SysWOW64\\";
LABEL_5:
        a3->Buffer = (wchar_t *)v5;
        v6 = wcslen(v5);
        v7 = 2 * v6;
        if ( 2 * v6 >= 0xFFFE )
          v7 = -4;
        LOWORD(v8) = v7;
LABEL_8:
        a3->Length = v7;
        a3->MaximumLength = v8 + 2;
        return 0;
      }
      v12 = L"SysWOW64";
      goto LABEL_16;
    case 0x1C4u:
      *(_QWORD *)&a3->Length = 0;
      if ( a2 )
      {
        v5 = L"\\SysARM32\\";
        goto LABEL_5;
      }
      v12 = L"SysARM32";
LABEL_16:
      a3->Buffer = (wchar_t *)v12;
      v8 = 2 * wcslen(v12);
      if ( v8 >= 0xFFFE )
        LOWORD(v8) = -4;
      v7 = v8;
      goto LABEL_8;
    case 0x3A64u:
      v13 = L"\\SyCHPE32\\";
      if ( !a2 )
        v13 = L"SyCHPE32";
      RtlInitUnicodeString(a3, v13);
      return 0;
    case 0x8664u:
    case 0xAA64u:
LABEL_10:
      *(_QWORD *)&a3->Length = 0;
      v10 = L"\\System32\\";
      if ( !a2 )
        v10 = L"System32";
      a3->Buffer = (wchar_t *)v10;
      v11 = 2 * wcslen(v10);
      if ( v11 >= 0xFFFE )
        LOWORD(v11) = -4;
      a3->Length = v11;
      a3->MaximumLength = v11 + 2;
      return 0;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x1800eaf48  push    rbx
0x1800eaf4a  sub     rsp, 20h
0x1800eaf4e  movzx   r9d, cx
0x1800eaf52  mov     rbx, r8
0x1800eaf55  mov     r8b, dl
0x1800eaf58  sub     r9d, 1
0x1800eaf5c  jz      short loc_1800EAFC1
0x1800eaf5e  sub     r9d, 14Bh
0x1800eaf65  jnz     loc_1800EB02C
0x1800eaf6b  mov     qword ptr [rbx], 0
0x1800eaf72  test    dl, dl
0x1800eaf74  jz      loc_1800EAFFC
0x1800eaf7a  lea     rcx, aSyswow64; "\\SysWOW64\\"
0x1800eaf81  mov     [rbx+8], rcx
0x1800eaf85  call    wcslen
0x1800eaf8a  mov     rdx, rax
0x1800eaf8d  mov     ecx, 0FFFCh
0x1800eaf92  add     rdx, rdx
0x1800eaf95  cmp     rdx, 0FFFEh
0x1800eaf9c  cmovnb  rdx, rcx
0x1800eafa0  movzx   eax, dx
0x1800eafa3  mov     ecx, 2
0x1800eafa8  mov     [rbx], dx
0x1800eafab  add     ax, cx
0x1800eafae  mov     r9d, ecx
0x1800eafb1  mov     r8, rbx
0x1800eafb4  mov     [rcx+rbx], ax
0x1800eafb8  xor     eax, eax
0x1800eafba  add     rsp, 20h
0x1800eafbe  pop     rbx
0x1800eafbf  retn
0x1800eafc1  mov     qword ptr [rbx], 0
0x1800eafc8  lea     rcx, aSystem32_2; "\\System32\\"
0x1800eafcf  test    r8b, r8b
0x1800eafd2  jz      short loc_1800EB023
0x1800eafd4  mov     [rbx+8], rcx
0x1800eafd8  call    wcslen
0x1800eafdd  add     rax, rax
0x1800eafe0  mov     ecx, 0FFFCh
0x1800eafe5  cmp     rax, 0FFFEh
0x1800eafeb  cmovnb  rax, rcx
0x1800eafef  mov     [rbx], ax
0x1800eaff2  add     ax, 2
0x1800eaff6  mov     [rbx+2], ax
0x1800eaffa  jmp     short loc_1800EAFB8
0x1800eaffc  lea     rcx, aSyswow64_0; "SysWOW64"
0x1800eb003  mov     [rbx+8], rcx
0x1800eb007  call    wcslen
0x1800eb00c  add     rax, rax
0x1800eb00f  mov     ecx, 0FFFCh
0x1800eb014  cmp     rax, 0FFFEh
0x1800eb01a  cmovnb  rax, rcx
0x1800eb01e  movzx   edx, ax
0x1800eb021  jmp     short loc_1800EAFA3
0x1800eb023  lea     rcx, aSystem32_0; "System32"
0x1800eb02a  jmp     short loc_1800EAFD4
0x1800eb02c  sub     r9d, 78h ; 'x'
0x1800eb030  jz      short loc_1800EB05F
0x1800eb032  sub     r9d, 38A0h
0x1800eb039  jz      short loc_1800EB080
0x1800eb03b  sub     r9d, 4C00h
0x1800eb042  jz      loc_1800EAFC1
0x1800eb048  cmp     r9d, 2400h
0x1800eb04f  jz      loc_1800EAFC1
0x1800eb055  mov     eax, 0C000000Dh
0x1800eb05a  jmp     loc_1800EAFBA
0x1800eb05f  mov     qword ptr [rbx], 0
0x1800eb066  test    r8b, r8b
0x1800eb069  jz      short loc_1800EB077
0x1800eb06b  lea     rcx, aSysarm32_0; "\\SysARM32\\"
0x1800eb072  jmp     loc_1800EAF81
0x1800eb077  lea     rcx, aSysarm32; "SysARM32"
0x1800eb07e  jmp     short loc_1800EB003
0x1800eb080  test    r8b, r8b
0x1800eb083  lea     rax, aSychpe32_0; "SyCHPE32"
0x1800eb08a  lea     rdx, aSychpe32; "\\SyCHPE32\\"
0x1800eb091  mov     rcx, rbx; DestinationString
0x1800eb094  cmovz   rdx, rax; SourceString
0x1800eb098  call    RtlInitUnicodeString
0x1800eb09d  jmp     loc_1800EAFB8
```
