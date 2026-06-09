# RxSmbdGetSMBDirectServicePath

- ea: `0x14008c990`
- end: `0x14008caf5`
- name: `RxSmbdGetSMBDirectServicePath`
- size: `357`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x14008cb80`

## callees

- `0x140039fd8`
- `0x14004cbb8`
- `0x140053404`
- `0x140059dc0`
- `0x140086014`
- `0x14008c990`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14008ca40`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14008ca40`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14008ca53`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14008ca53`

## string_xrefs

- `0x14008c9d5`: `SMBDirectServiceName`

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
0x14008c990  mov     [rsp-8+arg_8], rbx
0x14008c995  mov     [rsp-8+arg_10], rdi
0x14008c99a  push    rbp
0x14008c99b  lea     rbp, [rsp-57h]
0x14008c9a0  sub     rsp, 0E0h
0x14008c9a7  mov     rax, cs:__security_cookie
0x14008c9ae  xor     rax, rsp
0x14008c9b1  mov     [rbp+57h+var_10], rax
0x14008c9b5  xorps   xmm0, xmm0
0x14008c9b8  mov     [rbp+57h+var_98], 0
0x14008c9c0  xor     eax, eax
0x14008c9c2  lea     r9, [rbp+57h+var_B0]
0x14008c9c6  mov     edi, 80h
0x14008c9cb  mov     [rcx], ax
0x14008c9ce  lea     r8, [rbp+57h+pszDest]
0x14008c9d2  mov     [rbp+57h+var_B0], edi
0x14008c9d5  lea     rdx, aSmbdirectservi; "SMBDirectServiceName"
0x14008c9dc  mov     rbx, rcx
0x14008c9df  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x14008c9e3  call    RfsRegGetString
0x14008c9e8  test    eax, eax
0x14008c9ea  jns     short loc_14008CA04
0x14008c9ec  lea     r8, aSmbdirect; "SMBDirect"
0x14008c9f3  mov     edx, edi; cbDest
0x14008c9f5  lea     rcx, [rbp+57h+pszDest]; pszDest
0x14008c9f9  call    RtlStringCbCopyW
0x14008c9fe  lea     r11d, [rdi-6Eh]
0x14008ca02  jmp     short loc_14008CA08
0x14008ca04  mov     r11d, [rbp+57h+var_B0]
0x14008ca08  cmp     r11d, 0FFFEh
0x14008ca0f  jnb     loc_14008CACE
0x14008ca15  mov     [rbp+57h+Source.Length], r11w
0x14008ca1a  lea     rax, [rbp+57h+pszDest]
0x14008ca1e  add     r11w, 2
0x14008ca23  mov     [rbp+57h+Source.Buffer], rax
0x14008ca27  mov     [rbp+57h+Source.MaximumLength], r11w
0x14008ca2c  cmp     r11w, di
0x14008ca30  ja      loc_14008CACE
0x14008ca36  lea     rdx, stru_140061F40; SourceString
0x14008ca3d  mov     rcx, rbx; DestinationString
0x14008ca40  call    cs:__imp_RtlCopyUnicodeString
0x14008ca47  nop     dword ptr [rax+rax+00h]
0x14008ca4c  lea     rdx, [rbp+57h+Source]; Source
0x14008ca50  mov     rcx, rbx; Destination
0x14008ca53  call    cs:__imp_RtlAppendUnicodeStringToString
0x14008ca5a  nop     dword ptr [rax+rax+00h]
0x14008ca5f  test    eax, eax
0x14008ca61  js      short loc_14008CACE
0x14008ca63  movzx   edx, [rbp+57h+Source.Length]
0x14008ca67  lea     r8, [rbp+57h+var_98]
0x14008ca6b  mov     rcx, [rbp+57h+Source.Buffer]
0x14008ca6f  shr     edx, 1
0x14008ca71  call    RfsRegIsValidSubkeyName
0x14008ca76  test    al, al
0x14008ca78  jnz     short loc_14008CACA
0x14008ca7a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008ca81  lea     rax, WPP_GLOBAL_Control
0x14008ca88  cmp     rcx, rax
0x14008ca8b  jz      short loc_14008CAC3
0x14008ca8d  mov     eax, [rcx+2Ch]
0x14008ca90  test    al, 4
0x14008ca92  jz      short loc_14008CAC3
0x14008ca94  cmp     byte ptr [rcx+29h], 4
0x14008ca98  jb      short loc_14008CAC3
0x14008ca9a  mov     rax, [rbp+57h+var_98]
0x14008ca9e  mov     edx, 21h ; '!'
0x14008caa3  mov     rcx, [rcx+18h]
0x14008caa7  mov     r8d, eax
0x14008caaa  sub     r8d, dword ptr [rbp+57h+Source.Buffer]
0x14008caae  mov     [rsp+0E0h+var_C0], r8d
0x14008cab3  lea     r8, WPP_fe1ce53ca48c31d5aa52f121b5564b01_Traceguids
0x14008caba  movzx   r9d, word ptr [rax]
0x14008cabe  call    WPP_SF_Dd
0x14008cac3  mov     eax, 0C0000033h
0x14008cac8  jmp     short loc_14008CAD3
0x14008caca  xor     eax, eax
0x14008cacc  jmp     short loc_14008CAD3
0x14008cace  mov     eax, 0C0000106h
0x14008cad3  mov     rcx, [rbp+57h+var_10]
0x14008cad7  xor     rcx, rsp; StackCookie
0x14008cada  call    __security_check_cookie
0x14008cadf  lea     r11, [rsp+0E0h+var_s0]
0x14008cae7  mov     rbx, [r11+18h]
0x14008caeb  mov     rdi, [r11+20h]
0x14008caef  mov     rsp, r11
0x14008caf2  pop     rbp
0x14008caf3  retn
```
