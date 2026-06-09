# DetectedSymlinkOnRemoteDatabaseFile

- ea: `0x14000ba94`
- end: `0x14000bb39`
- name: `DetectedSymlinkOnRemoteDatabaseFile`
- size: `165`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x14000b150`
- `0x140011500`

## callees

- `0x140002d70`
- `0x14000ba94`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000bacc`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000bacc`
- `ntoskrnl!EtwWrite` at `0x14000bb1a`
- `ntoskrnl!EtwWrite` at `0x14000bb1a`

## pseudocode

```c
NTSTATUS DetectedSymlinkOnRemoteDatabaseFile()
{
  NTSTATUS result; // eax
  __int16 v1; // [rsp+30h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-28h] BYREF
  __int16 *v4; // [rsp+58h] [rbp-18h]
  __int64 v5; // [rsp+60h] [rbp-10h]

  result = 0;
  v1 = 0;
  DestinationString = 0;
  if ( gEtwProvRegHandle )
  {
    RtlInitUnicodeString(&DestinationString, L"CVE-2015-1769");
    UserData.Ptr = (ULONGLONG)DestinationString.Buffer;
    UserData.Size = DestinationString.Length;
    v4 = &v1;
    UserData.Reserved = 0;
    v5 = 2;
    return EtwWrite(gEtwProvRegHandle, &MOUNTMGR_CVE_DETECT, 0, 2u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x14000ba94  push    rbp
0x14000ba96  mov     rbp, rsp
0x14000ba99  sub     rsp, 70h
0x14000ba9d  mov     rax, cs:__security_cookie
0x14000baa4  xor     rax, rsp
0x14000baa7  mov     [rbp+var_8], rax
0x14000baab  xor     eax, eax
0x14000baad  xorps   xmm0, xmm0
0x14000bab0  cmp     cs:gEtwProvRegHandle, rax
0x14000bab7  mov     [rbp+var_40], ax
0x14000babb  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000babf  jz      short loc_14000BB26
0x14000bac1  lea     rdx, aCve20151769; "CVE-2015-1769"
0x14000bac8  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000bacc  call    cs:__imp_RtlInitUnicodeString
0x14000bad3  nop     dword ptr [rax+rax+00h]
0x14000bad8  mov     rax, [rbp+DestinationString.Buffer]
0x14000badc  lea     rdx, MOUNTMGR_CVE_DETECT; EventDescriptor
0x14000bae3  mov     rcx, cs:gEtwProvRegHandle; RegHandle
0x14000baea  mov     r9d, 2; UserDataCount
0x14000baf0  mov     [rbp+var_28.Ptr], rax
0x14000baf4  xor     r8d, r8d; ActivityId
0x14000baf7  movzx   eax, [rbp+DestinationString.Length]
0x14000bafb  mov     [rbp+var_28.Size], eax
0x14000bafe  lea     rax, [rbp+var_40]
0x14000bb02  mov     [rbp+var_18], rax
0x14000bb06  lea     rax, [rbp+var_28]
0x14000bb0a  mov     [rsp+70h+UserData], rax; UserData
0x14000bb0f  mov     dword ptr [rbp+var_28.0Ch], 0
0x14000bb16  mov     [rbp+var_10], r9
0x14000bb1a  call    cs:__imp_EtwWrite
0x14000bb21  nop     dword ptr [rax+rax+00h]
0x14000bb26  mov     rcx, [rbp+var_8]
0x14000bb2a  xor     rcx, rsp; StackCookie
0x14000bb2d  call    __security_check_cookie
0x14000bb32  add     rsp, 70h
0x14000bb36  pop     rbp
0x14000bb37  retn
```
