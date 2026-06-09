# udk::CopilotPlusDetection::MeetsCopilotPlusMemoryRequirements(void)

- ea: `0x180024e44`
- end: `0x180024f01`
- name: `?MeetsCopilotPlusMemoryRequirements@CopilotPlusDetection@udk@@YA_NXZ`
- size: `189`
- prototype: `bool __fastcall(udk::CopilotPlusDetection *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180074d9c`
- `0x180074fcc`

## callees

- `0x18001a18c`
- `0x180024e44`
- `0x180024fe8`
- `0x18002a3d0`
- `0x18002af50`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180024ea8`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180024ea8`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x180024e68`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x180024e68`

## pseudocode

```c
bool __fastcall udk::CopilotPlusDetection::MeetsCopilotPlusMemoryRequirements(udk::CopilotPlusDetection *this)
{
  const char *v1; // r9
  const char *v2; // r9
  DWORDLONG ullTotalPhys; // rax
  unsigned __int64 TotalMemoryInKilobytes; // [rsp+20h] [rbp-68h] BYREF
  _MEMORYSTATUSEX Buffer; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  TotalMemoryInKilobytes = 0;
  if ( GetPhysicallyInstalledSystemMemory(&TotalMemoryInKilobytes) )
  {
    ullTotalPhys = TotalMemoryInKilobytes << 10;
  }
  else
  {
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x15A,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
      v1);
    memset_0(&Buffer, 0, sizeof(Buffer));
    Buffer.dwLength = 64;
    if ( !GlobalMemoryStatusEx(&Buffer) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x164,
        (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
        v2);
    ullTotalPhys = Buffer.ullTotalPhys;
  }
  return ullTotalPhys >= 0x400000000LL;
}

```

## disassembly

```asm
0x180024e44  sub     rsp, 88h
0x180024e4b  mov     rax, cs:__security_cookie
0x180024e52  xor     rax, rsp
0x180024e55  mov     [rsp+88h+var_18], rax
0x180024e5a  lea     rcx, [rsp+88h+TotalMemoryInKilobytes]; TotalMemoryInKilobytes
0x180024e5f  mov     [rsp+88h+TotalMemoryInKilobytes], 0
0x180024e68  call    cs:__imp_GetPhysicallyInstalledSystemMemory
0x180024e6e  test    eax, eax
0x180024e70  jnz     short loc_180024ED3
0x180024e72  mov     rcx, [rsp+88h]; this
0x180024e7a  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x180024e81  mov     edx, 15Ah; void *
0x180024e86  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180024e8b  xor     edx, edx; Val
0x180024e8d  lea     rcx, [rsp+88h+Buffer]; void *
0x180024e92  lea     r8d, [rdx+40h]; Size
0x180024e96  call    memset_0
0x180024e9b  lea     rcx, [rsp+88h+Buffer]; lpBuffer
0x180024ea0  mov     [rsp+88h+Buffer.dwLength], 40h ; '@'
0x180024ea8  call    cs:__imp_GlobalMemoryStatusEx
0x180024eae  test    eax, eax
0x180024eb0  jnz     short loc_180024ECC
0x180024eb2  mov     rcx, [rsp+88h]; this
0x180024eba  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x180024ec1  mov     edx, 164h; void *
0x180024ec6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180024ecc  mov     rax, [rsp+88h+Buffer.ullTotalPhys]
0x180024ed1  jmp     short loc_180024EDC
0x180024ed3  mov     rax, [rsp+88h+TotalMemoryInKilobytes]
0x180024ed8  shl     rax, 0Ah
0x180024edc  mov     rcx, 400000000h
0x180024ee6  cmp     rax, rcx
0x180024ee9  setnb   al
0x180024eec  mov     rcx, [rsp+88h+var_18]
0x180024ef1  xor     rcx, rsp; StackCookie
0x180024ef4  call    __security_check_cookie
0x180024ef9  add     rsp, 88h
0x180024f00  retn
```
