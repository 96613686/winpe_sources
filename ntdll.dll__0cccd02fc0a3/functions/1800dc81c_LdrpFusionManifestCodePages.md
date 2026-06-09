# LdrpFusionManifestCodePages

- ea: `0x1800dc81c`
- end: `0x1800dc927`
- name: `LdrpFusionManifestCodePages`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800dc48c`

## callees

- `0x1800dc81c`
- `0x1800dc930`
- `0x18011fe70`
- `0x180120aa8`
- `0x18012c7a0`
- `0x180162000`

## string_xrefs

- `0x1800dc856`: `http://schemas.microsoft.com/SMI/2019/WindowsSettings`

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
0x1800dc81c  mov     r11, rsp
0x1800dc81f  mov     [r11+18h], rbx
0x1800dc823  push    rdi
0x1800dc824  sub     rsp, 70h
0x1800dc828  mov     rax, cs:__security_cookie
0x1800dc82f  xor     rax, rsp
0x1800dc832  mov     [rsp+78h+var_18], rax
0x1800dc837  mov     dword ptr [rcx], 0
0x1800dc83d  lea     rax, [r11-38h]
0x1800dc841  mov     qword ptr [r11-48h], 0
0x1800dc849  lea     r9, aActivecodepage; "activeCodePage"
0x1800dc850  mov     dword ptr [rdx], 0
0x1800dc856  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/SMI/2019/W"...
0x1800dc85d  mov     rdi, rdx
0x1800dc860  mov     qword ptr [r11-50h], 0Fh
0x1800dc868  mov     rbx, rcx
0x1800dc86b  mov     [r11-58h], rax
0x1800dc86f  xor     edx, edx
0x1800dc871  xor     ecx, ecx
0x1800dc873  call    RtlQueryActivationContextApplicationSettings
0x1800dc878  test    eax, eax
0x1800dc87a  jns     short loc_1800DC89E
0x1800dc87c  cmp     dword ptr [rbx], 0
0x1800dc87f  setnz   al
0x1800dc882  mov     rcx, [rsp+78h+var_18]
0x1800dc887  xor     rcx, rsp; StackCookie
0x1800dc88a  call    __security_check_cookie
0x1800dc88f  mov     rbx, [rsp+78h+arg_10]
0x1800dc897  add     rsp, 70h
0x1800dc89b  pop     rdi
0x1800dc89c  retn
0x1800dc89e  lea     rdx, aUtf8; "UTF-8"
0x1800dc8a5  lea     rcx, [rsp+78h+String1]; String1
0x1800dc8aa  call    wcscmp
0x1800dc8af  test    eax, eax
0x1800dc8b1  jz      short loc_1800DC8EA
0x1800dc8b3  lea     rdx, aLegacy; "Legacy"
0x1800dc8ba  lea     rcx, [rsp+78h+String1]; String1
0x1800dc8bf  call    wcscmp
0x1800dc8c4  test    eax, eax
0x1800dc8c6  jz      short loc_1800DC8F8
0x1800dc8c8  lea     rcx, [rsp+78h+String1]
0x1800dc8cd  call    MayBeLocaleName
0x1800dc8d2  test    al, al
0x1800dc8d4  jz      short loc_1800DC87C
0x1800dc8d6  mov     r8, rdi
0x1800dc8d9  lea     rcx, [rsp+78h+String1]
0x1800dc8de  mov     rdx, rbx
0x1800dc8e1  call    RtlpGetProcessCodepagesForLocale
0x1800dc8e6  test    eax, eax
0x1800dc8e8  jns     short loc_1800DC87C
0x1800dc8ea  mov     dword ptr [rbx], 0FDE9h
0x1800dc8f0  mov     dword ptr [rdi], 0FDE9h
0x1800dc8f6  jmp     short loc_1800DC87C
0x1800dc8f8  mov     r8, rdi
0x1800dc8fb  mov     rdx, rbx
0x1800dc8fe  xor     ecx, ecx
0x1800dc900  call    RtlpGetProcessCodepagesForLocale
0x1800dc905  cmp     dword ptr [rbx], 0FDE9h
0x1800dc90b  jz      short loc_1800DC916
0x1800dc90d  cmp     dword ptr [rbx], 0
0x1800dc910  jnz     loc_1800DC87F
0x1800dc916  mov     dword ptr [rbx], 4E4h
0x1800dc91c  mov     dword ptr [rdi], 1B5h
0x1800dc922  jmp     loc_1800DC87C
```
