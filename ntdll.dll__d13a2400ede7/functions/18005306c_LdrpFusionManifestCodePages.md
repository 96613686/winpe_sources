# LdrpFusionManifestCodePages

- ea: `0x18005306c`
- end: `0x180053177`
- name: `LdrpFusionManifestCodePages`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180052ce4`

## callees

- `0x18005306c`
- `0x180053180`
- `0x180120960`
- `0x180121598`
- `0x18012d290`
- `0x180162810`

## string_xrefs

- `0x1800530a6`: `http://schemas.microsoft.com/SMI/2019/WindowsSettings`

## pseudocode

```c
bool __fastcall LdrpFusionManifestCodePages(_DWORD *a1, _DWORD *a2)
{
  bool v4; // zf
  wchar_t String1[16]; // [rsp+40h] [rbp-38h] BYREF

  *a1 = 0;
  *a2 = 0;
  if ( (int)RtlQueryActivationContextApplicationSettings(
              0,
              0,
              L"http://schemas.microsoft.com/SMI/2019/WindowsSettings",
              L"activeCodePage",
              String1,
              15,
              0) < 0 )
    goto LABEL_2;
  if ( !wcscmp(String1, L"UTF-8") )
  {
LABEL_8:
    *a1 = 65001;
    *a2 = 65001;
LABEL_2:
    v4 = *a1 == 0;
    return !v4;
  }
  if ( wcscmp(String1, L"Legacy") )
  {
    if ( !(unsigned __int8)MayBeLocaleName(String1) || (int)RtlpGetProcessCodepagesForLocale(String1, a1, a2) >= 0 )
      goto LABEL_2;
    goto LABEL_8;
  }
  RtlpGetProcessCodepagesForLocale(0, a1, a2);
  if ( *a1 == 65001 || (v4 = *a1 == 0, !*a1) )
  {
    *a1 = 1252;
    *a2 = 437;
    goto LABEL_2;
  }
  return !v4;
}

```

## disassembly

```asm
0x18005306c  mov     r11, rsp
0x18005306f  mov     [r11+18h], rbx
0x180053073  push    rdi
0x180053074  sub     rsp, 70h
0x180053078  mov     rax, cs:__security_cookie
0x18005307f  xor     rax, rsp
0x180053082  mov     [rsp+78h+var_18], rax
0x180053087  mov     dword ptr [rcx], 0
0x18005308d  lea     rax, [r11-38h]
0x180053091  mov     qword ptr [r11-48h], 0
0x180053099  lea     r9, aActivecodepage; "activeCodePage"
0x1800530a0  mov     dword ptr [rdx], 0
0x1800530a6  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/SMI/2019/W"...
0x1800530ad  mov     rdi, rdx
0x1800530b0  mov     qword ptr [r11-50h], 0Fh
0x1800530b8  mov     rbx, rcx
0x1800530bb  mov     [r11-58h], rax
0x1800530bf  xor     edx, edx
0x1800530c1  xor     ecx, ecx
0x1800530c3  call    RtlQueryActivationContextApplicationSettings
0x1800530c8  test    eax, eax
0x1800530ca  jns     short loc_1800530EE
0x1800530cc  cmp     dword ptr [rbx], 0
0x1800530cf  setnz   al
0x1800530d2  mov     rcx, [rsp+78h+var_18]
0x1800530d7  xor     rcx, rsp; StackCookie
0x1800530da  call    __security_check_cookie
0x1800530df  mov     rbx, [rsp+78h+arg_10]
0x1800530e7  add     rsp, 70h
0x1800530eb  pop     rdi
0x1800530ec  retn
0x1800530ee  lea     rdx, aUtf8; "UTF-8"
0x1800530f5  lea     rcx, [rsp+78h+String1]; String1
0x1800530fa  call    wcscmp
0x1800530ff  test    eax, eax
0x180053101  jz      short loc_18005313A
0x180053103  lea     rdx, aLegacy; "Legacy"
0x18005310a  lea     rcx, [rsp+78h+String1]; String1
0x18005310f  call    wcscmp
0x180053114  test    eax, eax
0x180053116  jz      short loc_180053148
0x180053118  lea     rcx, [rsp+78h+String1]
0x18005311d  call    MayBeLocaleName
0x180053122  test    al, al
0x180053124  jz      short loc_1800530CC
0x180053126  mov     r8, rdi
0x180053129  lea     rcx, [rsp+78h+String1]
0x18005312e  mov     rdx, rbx
0x180053131  call    RtlpGetProcessCodepagesForLocale
0x180053136  test    eax, eax
0x180053138  jns     short loc_1800530CC
0x18005313a  mov     dword ptr [rbx], 0FDE9h
0x180053140  mov     dword ptr [rdi], 0FDE9h
0x180053146  jmp     short loc_1800530CC
0x180053148  mov     r8, rdi
0x18005314b  mov     rdx, rbx
0x18005314e  xor     ecx, ecx
0x180053150  call    RtlpGetProcessCodepagesForLocale
0x180053155  cmp     dword ptr [rbx], 0FDE9h
0x18005315b  jz      short loc_180053166
0x18005315d  cmp     dword ptr [rbx], 0
0x180053160  jnz     loc_1800530CF
0x180053166  mov     dword ptr [rbx], 4E4h
0x18005316c  mov     dword ptr [rdi], 1B5h
0x180053172  jmp     loc_1800530CC
```
