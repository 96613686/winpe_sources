# GetProcessPath(ulong,ushort * *)

- ea: `0x1800d6e00`
- end: `0x1800d6f2b`
- name: `?GetProcessPath@@YAKKPEAPEAG@Z`
- size: `299`
- prototype: `unsigned int __fastcall(DWORD dwProcessId, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800d68b0`

## callees

- `0x180012920`
- `0x180012de0`
- `0x1800d6e00`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800d6eeb`
- `ntdll!RtlNtStatusToDosError` at `0x1800d6eeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6e50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6ea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6e50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6ea2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d6efe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d6efe`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800d6e42`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800d6e42`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800d6e98`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800d6e98`

## string_xrefs

- `0x1800d6e56`: `Failed to get open the process [%d] for PID [%d]`
- `0x1800d6ea8`: `Failed to get the image path [%d] for PID [%d]`
- `0x1800d6e6b`: `GetProcessPath`
- `0x1800d6ebd`: `GetProcessPath`

## pseudocode

```c
__int64 __fastcall GetProcessPath(DWORD dwProcessId, unsigned __int16 **a2)
{
  HANDLE v3; // rax
  void *v4; // rsi
  ULONG LastError; // ebx
  NTSTATUS v6; // eax
  NTSTATUS v7; // edi
  DWORD dwSize[4]; // [rsp+30h] [rbp-238h] BYREF
  WCHAR ExeName[264]; // [rsp+40h] [rbp-228h] BYREF

  *a2 = 0;
  dwSize[0] = 0;
  v3 = OpenProcess(0x1000u, 0, dwProcessId);
  v4 = v3;
  if ( v3 )
  {
    dwSize[0] = 260;
    if ( QueryFullProcessImageNameW(v3, 0, ExeName, dwSize) )
    {
      v6 = AslStringDuplicate(a2, ExeName);
      v7 = v6;
      if ( v6 < 0 )
      {
        LastError = RtlNtStatusToDosError(v6);
        if ( LastError == 317 )
          LastError = v7;
      }
      else
      {
        LastError = 0;
      }
    }
    else
    {
      LastError = GetLastError();
      AslLogCallPrintf(
        1,
        (unsigned int)"GetProcessPath",
        631,
        (unsigned int)"Failed to get the image path [%d] for PID [%d]");
    }
    CloseHandle(v4);
  }
  else
  {
    LastError = GetLastError();
    AslLogCallPrintf(
      1,
      (unsigned int)"GetProcessPath",
      621,
      (unsigned int)"Failed to get open the process [%d] for PID [%d]");
  }
  return LastError;
}

```

## disassembly

```asm
0x1800d6e00  mov     [rsp+arg_10], rbx
0x1800d6e05  mov     [rsp+arg_18], rsi
0x1800d6e0a  push    rdi
0x1800d6e0b  sub     rsp, 260h
0x1800d6e12  mov     rax, cs:__security_cookie
0x1800d6e19  xor     rax, rsp
0x1800d6e1c  mov     [rsp+268h+var_18], rax
0x1800d6e24  mov     rbx, rdx
0x1800d6e27  mov     qword ptr [rdx], 0
0x1800d6e2e  mov     edi, ecx
0x1800d6e30  mov     [rsp+268h+dwSize], 0
0x1800d6e38  mov     r8d, ecx; dwProcessId
0x1800d6e3b  xor     edx, edx; bInheritHandle
0x1800d6e3d  mov     ecx, 1000h; dwDesiredAccess
0x1800d6e42  call    cs:__imp_OpenProcess
0x1800d6e48  mov     rsi, rax
0x1800d6e4b  test    rax, rax
0x1800d6e4e  jnz     short loc_1800D6E81
0x1800d6e50  call    cs:__imp_GetLastError
0x1800d6e56  lea     r9, aFailedToGetOpe; "Failed to get open the process [%d] for"...
0x1800d6e5d  mov     [rsp+268h+var_240], edi
0x1800d6e61  mov     r8d, 26Dh
0x1800d6e67  mov     [rsp+268h+var_248], eax
0x1800d6e6b  lea     rdx, aGetprocesspath; "GetProcessPath"
0x1800d6e72  mov     ebx, eax
0x1800d6e74  lea     ecx, [rsi+1]
0x1800d6e77  call    AslLogCallPrintf
0x1800d6e7c  jmp     loc_1800D6F04
0x1800d6e81  lea     r9, [rsp+268h+dwSize]; lpdwSize
0x1800d6e86  mov     [rsp+268h+dwSize], 104h
0x1800d6e8e  lea     r8, [rsp+268h+ExeName]; lpExeName
0x1800d6e93  xor     edx, edx; dwFlags
0x1800d6e95  mov     rcx, rsi; hProcess
0x1800d6e98  call    cs:__imp_QueryFullProcessImageNameW
0x1800d6e9e  test    eax, eax
0x1800d6ea0  jnz     short loc_1800D6ED2
0x1800d6ea2  call    cs:__imp_GetLastError
0x1800d6ea8  lea     r9, aFailedToGetThe_38; "Failed to get the image path [%d] for P"...
0x1800d6eaf  mov     [rsp+268h+var_240], edi
0x1800d6eb3  mov     r8d, 277h
0x1800d6eb9  mov     [rsp+268h+var_248], eax
0x1800d6ebd  lea     rdx, aGetprocesspath; "GetProcessPath"
0x1800d6ec4  mov     ecx, 1
0x1800d6ec9  mov     ebx, eax
0x1800d6ecb  call    AslLogCallPrintf
0x1800d6ed0  jmp     short loc_1800D6EFB
0x1800d6ed2  lea     rdx, [rsp+268h+ExeName]
0x1800d6ed7  mov     rcx, rbx
0x1800d6eda  call    AslStringDuplicate
0x1800d6edf  mov     edi, eax
0x1800d6ee1  test    eax, eax
0x1800d6ee3  js      short loc_1800D6EE9
0x1800d6ee5  xor     ebx, ebx
0x1800d6ee7  jmp     short loc_1800D6EFB
0x1800d6ee9  mov     ecx, edi; Status
0x1800d6eeb  call    cs:__imp_RtlNtStatusToDosError
0x1800d6ef1  cmp     eax, 13Dh
0x1800d6ef6  mov     ebx, eax
0x1800d6ef8  cmovz   ebx, edi
0x1800d6efb  mov     rcx, rsi; hObject
0x1800d6efe  call    cs:__imp_CloseHandle
0x1800d6f04  mov     eax, ebx
0x1800d6f06  mov     rcx, [rsp+268h+var_18]
0x1800d6f0e  xor     rcx, rsp; StackCookie
0x1800d6f11  call    __security_check_cookie
0x1800d6f16  lea     r11, [rsp+268h+var_8]
0x1800d6f1e  mov     rbx, [r11+20h]
0x1800d6f22  mov     rsi, [r11+28h]
0x1800d6f26  mov     rsp, r11
0x1800d6f29  pop     rdi
0x1800d6f2a  retn
```
