# DiskCreateSymbolicLinks

- ea: `0x140011438`
- end: `0x1400115d9`
- name: `DiskCreateSymbolicLinks`
- size: `417`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x140011820`

## callees

- `0x1400031a0`
- `0x140005990`
- `0x140005bf0`
- `0x140006000`
- `0x1400111d0`
- `0x140011438`

## import_xrefs

- `ntoskrnl!IoCreateSymbolicLink` at `0x140011508`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140011599`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140011508`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140011599`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400114c0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011551`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400114c0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011551`

## pseudocode

```c
__int64 __fastcall DiskCreateSymbolicLinks(__int64 a1)
{
  __int64 v1; // rdi
  _DWORD *v3; // rbx
  int v4; // r8d
  int v5; // r8d
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-59h] BYREF
  wchar_t pszDest[64]; // [rsp+40h] [rbp-49h] BYREF

  v1 = *(_QWORD *)(a1 + 64);
  v3 = *(_DWORD **)(v1 + 96);
  memset(pszDest, 0, sizeof(pszDest));
  DestinationString = 0;
  if ( (*v3 & 1) == 0
    && RtlStringCchPrintfW(
         pszDest,
         0x3Fu,
         L"\\Device\\Harddisk%d\\Partition0",
         *(unsigned int *)(*(_QWORD *)(v1 + 24) + 588LL)) >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, pszDest);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_ZZ(WPP_GLOBAL_Control->AttachedDevice, 21, v4, (unsigned int)&DestinationString, v1 + 112);
    }
    if ( IoCreateSymbolicLink(&DestinationString, (PUNICODE_STRING)(v1 + 112)) >= 0 )
      *v3 |= 1u;
  }
  if ( (*v3 & 2) == 0
    && RtlStringCchPrintfW(
         pszDest,
         0x3Fu,
         L"\\DosDevices\\PhysicalDrive%d",
         *(unsigned int *)(*(_QWORD *)(v1 + 24) + 588LL)) >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, pszDest);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_ZZ(WPP_GLOBAL_Control->AttachedDevice, 22, v5, (unsigned int)&DestinationString, v1 + 112);
    }
    if ( IoCreateSymbolicLink(&DestinationString, (PUNICODE_STRING)(v1 + 112)) >= 0 )
      *v3 |= 2u;
  }
  return DiskCreateGuidSymbolicLink(a1);
}

```

## disassembly

```asm
0x140011438  mov     [rsp-8+arg_8], rbx
0x14001143d  mov     [rsp-8+arg_10], rsi
0x140011442  push    rbp
0x140011443  push    rdi
0x140011444  push    r14
0x140011446  lea     rbp, [rsp-47h]
0x14001144b  sub     rsp, 0D0h
0x140011452  mov     rax, cs:__security_cookie
0x140011459  xor     rax, rsp
0x14001145c  mov     [rbp+57h+var_20], rax
0x140011460  mov     rdi, [rcx+40h]
0x140011464  mov     rsi, rcx
0x140011467  xor     edx, edx; Val
0x140011469  lea     rcx, [rbp+57h+pszDest]; void *
0x14001146d  mov     r8d, 80h; Size
0x140011473  mov     rbx, [rdi+60h]
0x140011477  call    memset
0x14001147c  xorps   xmm0, xmm0
0x14001147f  lea     r14, WPP_GLOBAL_Control
0x140011486  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14001148a  mov     eax, [rbx]
0x14001148c  test    al, 1
0x14001148e  jnz     loc_14001151B
0x140011494  mov     r9, [rdi+18h]
0x140011498  lea     r8, aDeviceHarddisk_1; "\\Device\\Harddisk%d\\Partition0"
0x14001149f  mov     edx, 3Fh ; '?'; cchDest
0x1400114a4  lea     rcx, [rbp+57h+pszDest]; pszDest
0x1400114a8  mov     r9d, [r9+24Ch]
0x1400114af  call    RtlStringCchPrintfW
0x1400114b4  test    eax, eax
0x1400114b6  js      short loc_14001151B
0x1400114b8  lea     rdx, [rbp+57h+pszDest]; SourceString
0x1400114bc  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400114c0  call    cs:__imp_RtlInitUnicodeString
0x1400114c7  nop     dword ptr [rax+rax+00h]
0x1400114cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400114d3  cmp     rcx, r14
0x1400114d6  jz      short loc_140011500
0x1400114d8  mov     eax, [rcx+2Ch]
0x1400114db  test    al, 2
0x1400114dd  jz      short loc_140011500
0x1400114df  cmp     byte ptr [rcx+29h], 4
0x1400114e3  jb      short loc_140011500
0x1400114e5  mov     rcx, [rcx+18h]
0x1400114e9  lea     rax, [rdi+70h]
0x1400114ed  mov     edx, 15h
0x1400114f2  mov     [rsp+0E0h+var_C0], rax
0x1400114f7  lea     r9, [rbp+57h+DestinationString]
0x1400114fb  call    WPP_SF_ZZ
0x140011500  lea     rdx, [rdi+70h]; DeviceName
0x140011504  lea     rcx, [rbp+57h+DestinationString]; SymbolicLinkName
0x140011508  call    cs:__imp_IoCreateSymbolicLink
0x14001150f  nop     dword ptr [rax+rax+00h]
0x140011514  test    eax, eax
0x140011516  js      short loc_14001151B
0x140011518  or      dword ptr [rbx], 1
0x14001151b  mov     eax, [rbx]
0x14001151d  test    al, 2
0x14001151f  jnz     loc_1400115AC
0x140011525  mov     r9, [rdi+18h]
0x140011529  lea     r8, aDosdevicesPhys; "\\DosDevices\\PhysicalDrive%d"
0x140011530  mov     edx, 3Fh ; '?'; cchDest
0x140011535  lea     rcx, [rbp+57h+pszDest]; pszDest
0x140011539  mov     r9d, [r9+24Ch]
0x140011540  call    RtlStringCchPrintfW
0x140011545  test    eax, eax
0x140011547  js      short loc_1400115AC
0x140011549  lea     rdx, [rbp+57h+pszDest]; SourceString
0x14001154d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140011551  call    cs:__imp_RtlInitUnicodeString
0x140011558  nop     dword ptr [rax+rax+00h]
0x14001155d  mov     rcx, cs:WPP_GLOBAL_Control
0x140011564  cmp     rcx, r14
0x140011567  jz      short loc_140011591
0x140011569  mov     eax, [rcx+2Ch]
0x14001156c  test    al, 2
0x14001156e  jz      short loc_140011591
0x140011570  cmp     byte ptr [rcx+29h], 4
0x140011574  jb      short loc_140011591
0x140011576  mov     rcx, [rcx+18h]
0x14001157a  lea     rax, [rdi+70h]
0x14001157e  mov     edx, 16h
0x140011583  mov     [rsp+0E0h+var_C0], rax
0x140011588  lea     r9, [rbp+57h+DestinationString]
0x14001158c  call    WPP_SF_ZZ
0x140011591  lea     rdx, [rdi+70h]; DeviceName
0x140011595  lea     rcx, [rbp+57h+DestinationString]; SymbolicLinkName
0x140011599  call    cs:__imp_IoCreateSymbolicLink
0x1400115a0  nop     dword ptr [rax+rax+00h]
0x1400115a5  test    eax, eax
0x1400115a7  js      short loc_1400115AC
0x1400115a9  or      dword ptr [rbx], 2
0x1400115ac  mov     rcx, rsi
0x1400115af  call    DiskCreateGuidSymbolicLink
0x1400115b4  mov     rcx, [rbp+57h+var_20]
0x1400115b8  xor     rcx, rsp; StackCookie
0x1400115bb  call    __security_check_cookie
0x1400115c0  lea     r11, [rsp+0E0h+var_10]
0x1400115c8  mov     rbx, [r11+28h]
0x1400115cc  mov     rsi, [r11+30h]
0x1400115d0  mov     rsp, r11
0x1400115d3  pop     r14
0x1400115d5  pop     rdi
0x1400115d6  pop     rbp
0x1400115d7  retn
```
