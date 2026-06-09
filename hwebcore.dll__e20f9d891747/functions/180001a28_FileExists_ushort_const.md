# FileExists(ushort const *)

- ea: `0x180001a28`
- end: `0x180001a81`
- name: `?FileExists@@YAHPEBG@Z`
- size: `89`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001a90`

## callees

- `0x180001a28`
- `0x180002be0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180001a55`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180001a55`

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
0x180001a28  sub     rsp, 58h
0x180001a2c  mov     rax, cs:__security_cookie
0x180001a33  xor     rax, rsp
0x180001a36  mov     [rsp+58h+var_10], rax
0x180001a3b  xorps   xmm0, xmm0
0x180001a3e  lea     r8, [rsp+58h+FileInformation]; lpFileInformation
0x180001a43  xor     eax, eax
0x180001a45  xor     edx, edx; fInfoLevelId
0x180001a47  movups  [rsp+58h+FileInformation], xmm0
0x180001a4c  mov     [rsp+58h+var_18], eax
0x180001a50  movups  [rsp+58h+var_28], xmm0
0x180001a55  call    cs:__imp_GetFileAttributesExW
0x180001a5b  test    eax, eax
0x180001a5d  jz      short loc_180001A6D
0x180001a5f  mov     eax, dword ptr [rsp+58h+FileInformation]
0x180001a63  shr     eax, 4
0x180001a66  not     eax
0x180001a68  and     eax, 1
0x180001a6b  jmp     short loc_180001A6F
0x180001a6d  xor     eax, eax
0x180001a6f  mov     rcx, [rsp+58h+var_10]
0x180001a74  xor     rcx, rsp; StackCookie
0x180001a77  call    __security_check_cookie
0x180001a7c  add     rsp, 58h
0x180001a80  retn
```
