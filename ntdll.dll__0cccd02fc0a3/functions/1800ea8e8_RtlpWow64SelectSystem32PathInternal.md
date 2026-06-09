# RtlpWow64SelectSystem32PathInternal

- ea: `0x1800ea8e8`
- end: `0x1800eaa42`
- name: `RtlpWow64SelectSystem32PathInternal`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18005c5c0`

## callees

- `0x1800c0420`
- `0x1800ea8e8`
- `0x18012c830`

## string_xrefs

- `0x1800ea968`: `\System32\`
- `0x1800ea9c3`: `System32`

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
0x1800ea8e8  push    rbx
0x1800ea8ea  sub     rsp, 20h
0x1800ea8ee  movzx   r9d, cx
0x1800ea8f2  mov     rbx, r8
0x1800ea8f5  mov     r8b, dl
0x1800ea8f8  sub     r9d, 1
0x1800ea8fc  jz      short loc_1800EA961
0x1800ea8fe  sub     r9d, 14Bh
0x1800ea905  jnz     loc_1800EA9CC
0x1800ea90b  mov     qword ptr [rbx], 0
0x1800ea912  test    dl, dl
0x1800ea914  jz      loc_1800EA99C
0x1800ea91a  lea     rcx, aSyswow64; "\\SysWOW64\\"
0x1800ea921  mov     [rbx+8], rcx
0x1800ea925  call    wcslen
0x1800ea92a  mov     rdx, rax
0x1800ea92d  mov     ecx, 0FFFCh
0x1800ea932  add     rdx, rdx
0x1800ea935  cmp     rdx, 0FFFEh
0x1800ea93c  cmovnb  rdx, rcx
0x1800ea940  movzx   eax, dx
0x1800ea943  mov     ecx, 2
0x1800ea948  mov     [rbx], dx
0x1800ea94b  add     ax, cx
0x1800ea94e  mov     r9d, ecx
0x1800ea951  mov     r8, rbx
0x1800ea954  mov     [rcx+rbx], ax
0x1800ea958  xor     eax, eax
0x1800ea95a  add     rsp, 20h
0x1800ea95e  pop     rbx
0x1800ea95f  retn
0x1800ea961  mov     qword ptr [rbx], 0
0x1800ea968  lea     rcx, aSystem32_2; "\\System32\\"
0x1800ea96f  test    r8b, r8b
0x1800ea972  jz      short loc_1800EA9C3
0x1800ea974  mov     [rbx+8], rcx
0x1800ea978  call    wcslen
0x1800ea97d  add     rax, rax
0x1800ea980  mov     ecx, 0FFFCh
0x1800ea985  cmp     rax, 0FFFEh
0x1800ea98b  cmovnb  rax, rcx
0x1800ea98f  mov     [rbx], ax
0x1800ea992  add     ax, 2
0x1800ea996  mov     [rbx+2], ax
0x1800ea99a  jmp     short loc_1800EA958
0x1800ea99c  lea     rcx, aSyswow64_0; "SysWOW64"
0x1800ea9a3  mov     [rbx+8], rcx
0x1800ea9a7  call    wcslen
0x1800ea9ac  add     rax, rax
0x1800ea9af  mov     ecx, 0FFFCh
0x1800ea9b4  cmp     rax, 0FFFEh
0x1800ea9ba  cmovnb  rax, rcx
0x1800ea9be  movzx   edx, ax
0x1800ea9c1  jmp     short loc_1800EA943
0x1800ea9c3  lea     rcx, aSystem32_0; "System32"
0x1800ea9ca  jmp     short loc_1800EA974
0x1800ea9cc  sub     r9d, 78h ; 'x'
0x1800ea9d0  jz      short loc_1800EA9FF
0x1800ea9d2  sub     r9d, 38A0h
0x1800ea9d9  jz      short loc_1800EAA20
0x1800ea9db  sub     r9d, 4C00h
0x1800ea9e2  jz      loc_1800EA961
0x1800ea9e8  cmp     r9d, 2400h
0x1800ea9ef  jz      loc_1800EA961
0x1800ea9f5  mov     eax, 0C000000Dh
0x1800ea9fa  jmp     loc_1800EA95A
0x1800ea9ff  mov     qword ptr [rbx], 0
0x1800eaa06  test    r8b, r8b
0x1800eaa09  jz      short loc_1800EAA17
0x1800eaa0b  lea     rcx, aSysarm32_0; "\\SysARM32\\"
0x1800eaa12  jmp     loc_1800EA921
0x1800eaa17  lea     rcx, aSysarm32; "SysARM32"
0x1800eaa1e  jmp     short loc_1800EA9A3
0x1800eaa20  test    r8b, r8b
0x1800eaa23  lea     rax, aSychpe32_0; "SyCHPE32"
0x1800eaa2a  lea     rdx, aSychpe32; "\\SyCHPE32\\"
0x1800eaa31  mov     rcx, rbx; DestinationString
0x1800eaa34  cmovz   rdx, rax; SourceString
0x1800eaa38  call    RtlInitUnicodeString
0x1800eaa3d  jmp     loc_1800EA958
```
