# RxSmbdGetSMBDirectServicePath

- ea: `0x14008c940`
- end: `0x14008caa5`
- name: `RxSmbdGetSMBDirectServicePath`
- size: `357`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x14008cb30`

## callees

- `0x140039fd8`
- `0x14004cbb8`
- `0x140053404`
- `0x140059dc0`
- `0x140085fc4`
- `0x14008c940`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14008c9f0`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14008c9f0`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14008ca03`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14008ca03`

## string_xrefs

- `0x14008c985`: `SMBDirectServiceName`

## pseudocode

```c
__int64 __fastcall RxSmbdGetSMBDirectServicePath(PUNICODE_STRING Destination)
{
  unsigned int v2; // r11d
  int v4; // [rsp+30h] [rbp-59h] BYREF
  UNICODE_STRING Source; // [rsp+38h] [rbp-51h] BYREF
  unsigned __int16 *v6; // [rsp+48h] [rbp-41h] BYREF
  wchar_t pszDest[64]; // [rsp+50h] [rbp-39h] BYREF

  v6 = 0;
  Destination->Length = 0;
  v4 = 128;
  Source = 0;
  if ( (int)RfsRegGetString(Destination, L"SMBDirectServiceName", pszDest, &v4) >= 0 )
  {
    v2 = v4;
  }
  else
  {
    RtlStringCbCopyW(pszDest, 0x80u, L"SMBDirect");
    v2 = 18;
  }
  if ( v2 >= 0xFFFE )
    return 3221225734LL;
  Source.Length = v2;
  Source.Buffer = pszDest;
  Source.MaximumLength = v2 + 2;
  if ( (unsigned __int16)(v2 + 2) > 0x80u )
    return 3221225734LL;
  RtlCopyUnicodeString(Destination, &stru_140061F40);
  if ( RtlAppendUnicodeStringToString(Destination, &Source) < 0 )
    return 3221225734LL;
  if ( (unsigned __int8)RfsRegIsValidSubkeyName(Source.Buffer, Source.Length >> 1, &v6) )
    return 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      33,
      WPP_fe1ce53ca48c31d5aa52f121b5564b01_Traceguids,
      *v6,
      (_DWORD)v6 - LODWORD(Source.Buffer));
  }
  return 3221225523LL;
}

```

## disassembly

```asm
0x14008c940  mov     [rsp-8+arg_8], rbx
0x14008c945  mov     [rsp-8+arg_10], rdi
0x14008c94a  push    rbp
0x14008c94b  lea     rbp, [rsp-57h]
0x14008c950  sub     rsp, 0E0h
0x14008c957  mov     rax, cs:__security_cookie
0x14008c95e  xor     rax, rsp
0x14008c961  mov     [rbp+57h+var_10], rax
0x14008c965  xorps   xmm0, xmm0
0x14008c968  mov     [rbp+57h+var_98], 0
0x14008c970  xor     eax, eax
0x14008c972  lea     r9, [rbp+57h+var_B0]
0x14008c976  mov     edi, 80h
0x14008c97b  mov     [rcx], ax
0x14008c97e  lea     r8, [rbp+57h+pszDest]
0x14008c982  mov     [rbp+57h+var_B0], edi
0x14008c985  lea     rdx, aSmbdirectservi; "SMBDirectServiceName"
0x14008c98c  mov     rbx, rcx
0x14008c98f  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x14008c993  call    RfsRegGetString
0x14008c998  test    eax, eax
0x14008c99a  jns     short loc_14008C9B4
0x14008c99c  lea     r8, aSmbdirect; "SMBDirect"
0x14008c9a3  mov     edx, edi; cbDest
0x14008c9a5  lea     rcx, [rbp+57h+pszDest]; pszDest
0x14008c9a9  call    RtlStringCbCopyW
0x14008c9ae  lea     r11d, [rdi-6Eh]
0x14008c9b2  jmp     short loc_14008C9B8
0x14008c9b4  mov     r11d, [rbp+57h+var_B0]
0x14008c9b8  cmp     r11d, 0FFFEh
0x14008c9bf  jnb     loc_14008CA7E
0x14008c9c5  mov     [rbp+57h+Source.Length], r11w
0x14008c9ca  lea     rax, [rbp+57h+pszDest]
0x14008c9ce  add     r11w, 2
0x14008c9d3  mov     [rbp+57h+Source.Buffer], rax
0x14008c9d7  mov     [rbp+57h+Source.MaximumLength], r11w
0x14008c9dc  cmp     r11w, di
0x14008c9e0  ja      loc_14008CA7E
0x14008c9e6  lea     rdx, stru_140061F40; SourceString
0x14008c9ed  mov     rcx, rbx; DestinationString
0x14008c9f0  call    cs:__imp_RtlCopyUnicodeString
0x14008c9f7  nop     dword ptr [rax+rax+00h]
0x14008c9fc  lea     rdx, [rbp+57h+Source]; Source
0x14008ca00  mov     rcx, rbx; Destination
0x14008ca03  call    cs:__imp_RtlAppendUnicodeStringToString
0x14008ca0a  nop     dword ptr [rax+rax+00h]
0x14008ca0f  test    eax, eax
0x14008ca11  js      short loc_14008CA7E
0x14008ca13  movzx   edx, [rbp+57h+Source.Length]
0x14008ca17  lea     r8, [rbp+57h+var_98]
0x14008ca1b  mov     rcx, [rbp+57h+Source.Buffer]
0x14008ca1f  shr     edx, 1
0x14008ca21  call    RfsRegIsValidSubkeyName
0x14008ca26  test    al, al
0x14008ca28  jnz     short loc_14008CA7A
0x14008ca2a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008ca31  lea     rax, WPP_GLOBAL_Control
0x14008ca38  cmp     rcx, rax
0x14008ca3b  jz      short loc_14008CA73
0x14008ca3d  mov     eax, [rcx+2Ch]
0x14008ca40  test    al, 4
0x14008ca42  jz      short loc_14008CA73
0x14008ca44  cmp     byte ptr [rcx+29h], 4
0x14008ca48  jb      short loc_14008CA73
0x14008ca4a  mov     rax, [rbp+57h+var_98]
0x14008ca4e  mov     edx, 21h ; '!'
0x14008ca53  mov     rcx, [rcx+18h]
0x14008ca57  mov     r8d, eax
0x14008ca5a  sub     r8d, dword ptr [rbp+57h+Source.Buffer]
0x14008ca5e  mov     [rsp+0E0h+var_C0], r8d
0x14008ca63  lea     r8, WPP_fe1ce53ca48c31d5aa52f121b5564b01_Traceguids
0x14008ca6a  movzx   r9d, word ptr [rax]
0x14008ca6e  call    WPP_SF_Dd
0x14008ca73  mov     eax, 0C0000033h
0x14008ca78  jmp     short loc_14008CA83
0x14008ca7a  xor     eax, eax
0x14008ca7c  jmp     short loc_14008CA83
0x14008ca7e  mov     eax, 0C0000106h
0x14008ca83  mov     rcx, [rbp+57h+var_10]
0x14008ca87  xor     rcx, rsp; StackCookie
0x14008ca8a  call    __security_check_cookie
0x14008ca8f  lea     r11, [rsp+0E0h+var_s0]
0x14008ca97  mov     rbx, [r11+18h]
0x14008ca9b  mov     rdi, [r11+20h]
0x14008ca9f  mov     rsp, r11
0x14008caa2  pop     rbp
0x14008caa3  retn
```
