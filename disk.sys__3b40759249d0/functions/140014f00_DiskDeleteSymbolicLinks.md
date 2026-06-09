# DiskDeleteSymbolicLinks

- ea: `0x140014f00`
- end: `0x140015021`
- name: `DiskDeleteSymbolicLinks`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x140014df0`

## callees

- `0x1400031a0`
- `0x140005bf0`
- `0x140006000`
- `0x14000e170`
- `0x140014f00`

## import_xrefs

- `ntoskrnl!IoDeleteSymbolicLink` at `0x140014f8f`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140014fe4`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140014f8f`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140014fe4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140014f7e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140014fd3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140014f7e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140014fd3`

## pseudocode

```c
__int64 __fastcall DiskDeleteSymbolicLinks(__int64 a1)
{
  __int64 v1; // rsi
  int *v3; // rdi
  int v4; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-A8h] BYREF
  wchar_t pszDest[64]; // [rsp+30h] [rbp-98h] BYREF

  v1 = *(_QWORD *)(a1 + 64);
  v3 = *(int **)(v1 + 96);
  memset(pszDest, 0, sizeof(pszDest));
  DestinationString = 0;
  v4 = *v3;
  if ( (*v3 & 1) != 0 )
  {
    if ( RtlStringCchPrintfW(
           pszDest,
           0x3Fu,
           L"\\Device\\Harddisk%d\\Partition0",
           *(unsigned int *)(*(_QWORD *)(v1 + 24) + 588LL),
           *(_QWORD *)&DestinationString.Length,
           DestinationString.Buffer) >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, pszDest);
      IoDeleteSymbolicLink(&DestinationString);
    }
    *v3 &= ~1u;
    v4 = *v3;
  }
  if ( (v4 & 2) != 0 )
  {
    if ( RtlStringCchPrintfW(
           pszDest,
           0x3Fu,
           L"\\DosDevices\\PhysicalDrive%d",
           *(unsigned int *)(*(_QWORD *)(v1 + 24) + 588LL)) >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, pszDest);
      IoDeleteSymbolicLink(&DestinationString);
    }
    *v3 &= ~2u;
  }
  return DiskDeleteGuidSymbolicLink(a1);
}

```

## disassembly

```asm
0x140014f00  mov     [rsp+arg_8], rbx
0x140014f05  mov     [rsp+arg_10], rsi
0x140014f0a  push    rdi
0x140014f0b  sub     rsp, 0C0h
0x140014f12  mov     rax, cs:__security_cookie
0x140014f19  xor     rax, rsp
0x140014f1c  mov     [rsp+0C8h+var_18], rax
0x140014f24  mov     rsi, [rcx+40h]
0x140014f28  mov     rbx, rcx
0x140014f2b  xor     edx, edx; Val
0x140014f2d  lea     rcx, [rsp+0C8h+pszDest]; void *
0x140014f32  mov     r8d, 80h; Size
0x140014f38  mov     rdi, [rsi+60h]
0x140014f3c  call    memset
0x140014f41  xorps   xmm0, xmm0
0x140014f44  movups  xmmword ptr [rsp+0C8h+DestinationString.Length], xmm0
0x140014f49  mov     eax, [rdi]
0x140014f4b  test    al, 1
0x140014f4d  jz      short loc_140014FA0
0x140014f4f  mov     r9, [rsi+18h]
0x140014f53  lea     r8, aDeviceHarddisk_1; "\\Device\\Harddisk%d\\Partition0"
0x140014f5a  mov     edx, 3Fh ; '?'; cchDest
0x140014f5f  lea     rcx, [rsp+0C8h+pszDest]; pszDest
0x140014f64  mov     r9d, [r9+24Ch]
0x140014f6b  call    RtlStringCchPrintfW
0x140014f70  test    eax, eax
0x140014f72  js      short loc_140014F9B
0x140014f74  lea     rdx, [rsp+0C8h+pszDest]; SourceString
0x140014f79  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x140014f7e  call    cs:__imp_RtlInitUnicodeString
0x140014f85  nop     dword ptr [rax+rax+00h]
0x140014f8a  lea     rcx, [rsp+0C8h+DestinationString]; SymbolicLinkName
0x140014f8f  call    cs:__imp_IoDeleteSymbolicLink
0x140014f96  nop     dword ptr [rax+rax+00h]
0x140014f9b  and     dword ptr [rdi], 0FFFFFFFEh
0x140014f9e  mov     eax, [rdi]
0x140014fa0  test    al, 2
0x140014fa2  jz      short loc_140014FF3
0x140014fa4  mov     r9, [rsi+18h]
0x140014fa8  lea     r8, aDosdevicesPhys; "\\DosDevices\\PhysicalDrive%d"
0x140014faf  mov     edx, 3Fh ; '?'; cchDest
0x140014fb4  lea     rcx, [rsp+0C8h+pszDest]; pszDest
0x140014fb9  mov     r9d, [r9+24Ch]
0x140014fc0  call    RtlStringCchPrintfW
0x140014fc5  test    eax, eax
0x140014fc7  js      short loc_140014FF0
0x140014fc9  lea     rdx, [rsp+0C8h+pszDest]; SourceString
0x140014fce  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x140014fd3  call    cs:__imp_RtlInitUnicodeString
0x140014fda  nop     dword ptr [rax+rax+00h]
0x140014fdf  lea     rcx, [rsp+0C8h+DestinationString]; SymbolicLinkName
0x140014fe4  call    cs:__imp_IoDeleteSymbolicLink
0x140014feb  nop     dword ptr [rax+rax+00h]
0x140014ff0  and     dword ptr [rdi], 0FFFFFFFDh
0x140014ff3  mov     rcx, rbx
0x140014ff6  call    DiskDeleteGuidSymbolicLink
0x140014ffb  mov     rcx, [rsp+0C8h+var_18]
0x140015003  xor     rcx, rsp; StackCookie
0x140015006  call    __security_check_cookie
0x14001500b  lea     r11, [rsp+0C8h+var_8]
0x140015013  mov     rbx, [r11+18h]
0x140015017  mov     rsi, [r11+20h]
0x14001501b  mov     rsp, r11
0x14001501e  pop     rdi
0x14001501f  retn
```
