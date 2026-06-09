# IsMicrosoftMediaServer(Windows::Media::Streaming::IBasicDevice *)

- ea: `0x18000ebb4`
- end: `0x18000ec41`
- name: `?IsMicrosoftMediaServer@@YAEPEAUIBasicDevice@Streaming@Media@Windows@@@Z`
- size: `141`
- prototype: `unsigned __int8 __fastcall(struct Windows::Media::Streaming::IBasicDevice *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e9cc`
- `0x180025acc`

## callees

- `0x18000ebb4`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000ec15`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000ec15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ebf0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ebf0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ec2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ec2e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall IsMicrosoftMediaServer(struct Windows::Media::Streaming::IBasicDevice *a1)
{
  bool v1; // bl
  const WCHAR *StringRawBuffer; // rax
  UINT32 length; // [rsp+40h] [rbp+8h] BYREF
  HSTRING string; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  string = 0;
  if ( (*(int (__fastcall **)(struct Windows::Media::Streaming::IBasicDevice *, HSTRING *))(*(_QWORD *)a1 + 64LL))(
         a1,
         &string) >= 0 )
  {
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    if ( length >= 9 )
      v1 = CompareStringOrdinal(StringRawBuffer, 9, L"Microsoft", 9, 1) == 2;
  }
  if ( string )
    WindowsDeleteString(string);
  return v1;
}

```

## disassembly

```asm
0x18000ebb4  mov     [rsp+arg_10], rbx
0x18000ebb9  push    rdi
0x18000ebba  sub     rsp, 30h
0x18000ebbe  xor     bl, bl
0x18000ebc0  mov     [rsp+38h+string], 0
0x18000ebc9  mov     rax, [rcx]
0x18000ebcc  lea     rdx, [rsp+38h+string]
0x18000ebd1  mov     rax, [rax+40h]
0x18000ebd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebda  test    eax, eax
0x18000ebdc  js      short loc_18000EC24
0x18000ebde  mov     [rsp+38h+length], 0
0x18000ebe6  lea     rdx, [rsp+38h+length]; length
0x18000ebeb  mov     rcx, [rsp+38h+string]; string
0x18000ebf0  call    cs:__imp_WindowsGetStringRawBuffer
0x18000ebf6  mov     edx, 9; cchCount1
0x18000ebfb  cmp     [rsp+38h+length], edx
0x18000ebff  jb      short loc_18000EC24
0x18000ec01  lea     edi, [rdx-8]
0x18000ec04  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x18000ec08  mov     r9d, edx; cchCount2
0x18000ec0b  lea     r8, aMicrosoft; "Microsoft"
0x18000ec12  mov     rcx, rax; lpString1
0x18000ec15  call    cs:__imp_CompareStringOrdinal
0x18000ec1b  movzx   ebx, bl
0x18000ec1e  cmp     eax, 2
0x18000ec21  cmovz   ebx, edi
0x18000ec24  mov     rcx, [rsp+38h+string]; string
0x18000ec29  test    rcx, rcx
0x18000ec2c  jz      short loc_18000EC34
0x18000ec2e  call    cs:__imp_WindowsDeleteString
0x18000ec34  mov     al, bl
0x18000ec36  mov     rbx, [rsp+38h+arg_10]
0x18000ec3b  add     rsp, 30h
0x18000ec3f  pop     rdi
0x18000ec40  retn
```
