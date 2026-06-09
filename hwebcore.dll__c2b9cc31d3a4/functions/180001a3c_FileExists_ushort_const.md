# FileExists(ushort const *)

- ea: `0x180001a3c`
- end: `0x180001a9c`
- name: `?FileExists@@YAHPEBG@Z`
- size: `96`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001ab0`

## callees

- `0x180001a3c`
- `0x180002de0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180001a69`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180001a69`

## pseudocode

```c
_BOOL8 __fastcall FileExists(const unsigned __int16 *a1)
{
  _OWORD FileInformation[2]; // [rsp+20h] [rbp-38h] BYREF
  int v3; // [rsp+40h] [rbp-18h]

  memset(FileInformation, 0, sizeof(FileInformation));
  v3 = 0;
  return GetFileAttributesExW(a1, GetFileExInfoStandard, FileInformation) && (FileInformation[0] & 0x10) == 0;
}

```

## disassembly

```asm
0x180001a3c  sub     rsp, 58h
0x180001a40  mov     rax, cs:__security_cookie
0x180001a47  xor     rax, rsp
0x180001a4a  mov     [rsp+58h+var_10], rax
0x180001a4f  xorps   xmm0, xmm0
0x180001a52  lea     r8, [rsp+58h+FileInformation]; lpFileInformation
0x180001a57  xor     eax, eax
0x180001a59  xor     edx, edx; fInfoLevelId
0x180001a5b  movups  [rsp+58h+FileInformation], xmm0
0x180001a60  mov     [rsp+58h+var_18], eax
0x180001a64  movups  [rsp+58h+var_28], xmm0
0x180001a69  call    cs:__imp_GetFileAttributesExW
0x180001a70  nop     dword ptr [rax+rax+00h]
0x180001a75  test    eax, eax
0x180001a77  jz      short loc_180001A87
0x180001a79  mov     eax, dword ptr [rsp+58h+FileInformation]
0x180001a7d  shr     eax, 4
0x180001a80  not     eax
0x180001a82  and     eax, 1
0x180001a85  jmp     short loc_180001A89
0x180001a87  xor     eax, eax
0x180001a89  mov     rcx, [rsp+58h+var_10]
0x180001a8e  xor     rcx, rsp; StackCookie
0x180001a91  call    __security_check_cookie
0x180001a96  add     rsp, 58h
0x180001a9a  retn
```
