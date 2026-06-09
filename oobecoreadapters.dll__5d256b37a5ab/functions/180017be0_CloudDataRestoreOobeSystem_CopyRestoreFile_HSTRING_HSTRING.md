# CloudDataRestoreOobeSystem::CopyRestoreFile(HSTRING__ *,HSTRING__ *)

- ea: `0x180017be0`
- end: `0x180017c44`
- name: `?CopyRestoreFile@CloudDataRestoreOobeSystem@@UEAAJPEAUHSTRING__@@0@Z`
- size: `100`
- prototype: `__int64 __fastcall(CloudDataRestoreOobeSystem *this, HSTRING, HSTRING)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180017be0`
- `0x1800194fc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017bf2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017c00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017bf2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017c00`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180017c0f`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180017c0f`

## string_xrefs

- `0x180017c31`: `shellcommon\shell\oobe\core\components\com\clouddatarestoreoobe.cpp`

## pseudocode

```c
__int64 __fastcall CloudDataRestoreOobeSystem::CopyRestoreFile(
        CloudDataRestoreOobeSystem *this,
        HSTRING a2,
        HSTRING a3)
{
  const WCHAR *StringRawBuffer; // rbx
  const WCHAR *v5; // rax
  const char *v6; // r9
  const char *v8; // r9
  __int64 v9; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v11; // [rsp+48h] [rbp+20h]

  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  v5 = WindowsGetStringRawBuffer(a2, 0);
  if ( !CopyFileW(v5, StringRawBuffer, 0) )
  {
    try
    {
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x9C,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\clouddatarestoreoobe.cpp",
        v6);
    }
    catch ( ... )
    {
      *(_DWORD *)(v9 + 72) = wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x9F,
                               (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\clouddatarestoreoobe.cpp",
                               v8);
      return v11;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180017be0  mov     [rsp+arg_0], rbx
0x180017be5  push    rdi
0x180017be6  sub     rsp, 20h
0x180017bea  mov     rdi, rdx
0x180017bed  xor     edx, edx; length
0x180017bef  mov     rcx, r8; string
0x180017bf2  call    cs:__imp_WindowsGetStringRawBuffer
0x180017bf8  mov     rbx, rax
0x180017bfb  xor     edx, edx; length
0x180017bfd  mov     rcx, rdi; string
0x180017c00  call    cs:__imp_WindowsGetStringRawBuffer
0x180017c06  xor     r8d, r8d; bFailIfExists
0x180017c09  mov     rdx, rbx; lpNewFileName
0x180017c0c  mov     rcx, rax; lpExistingFileName
0x180017c0f  call    cs:__imp_CopyFileW
0x180017c15  mov     rcx, [rsp+28h]; this
0x180017c1a  test    eax, eax
0x180017c1c  jz      short loc_180017C31
0x180017c1e  xor     eax, eax
0x180017c20  jmp     short loc_180017C26
0x180017c22  mov     eax, [rsp+28h+arg_18]
0x180017c26  mov     rbx, [rsp+28h+arg_0]
0x180017c2b  add     rsp, 20h
0x180017c2f  pop     rdi
0x180017c30  retn
0x180017c31  lea     r8, aShellcommonShe_17; "shellcommon\\shell\\oobe\\core\\compone"...
0x180017c38  mov     edx, 9Ch; void *
0x180017c3d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
