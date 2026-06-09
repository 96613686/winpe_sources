# UtilGetTimestampModule(void *,HINSTANCE__ *)

- ea: `0x18003ae98`
- end: `0x18003af66`
- name: `?UtilGetTimestampModule@@YAKPEAXPEAUHINSTANCE__@@@Z`
- size: `206`
- prototype: `__int64 __fastcall(HANDLE hProcess, HINSTANCE lpBaseAddress)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180018800`
- `0x180031050`

## callees

- `0x180002890`
- `0x180003474`
- `0x18003ae98`

## import_xrefs

- `ntdll!RtlImageNtHeaderEx` at `0x18003af19`
- `ntdll!RtlImageNtHeaderEx` at `0x18003af19`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003aef9`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003aef9`

## pseudocode

```c
__int64 __fastcall UtilGetTimestampModule(HANDLE hProcess, HINSTANCE lpBaseAddress)
{
  unsigned int v4; // ebx
  SIZE_T NumberOfBytesRead; // [rsp+38h] [rbp-240h] BYREF
  PIMAGE_NT_HEADERS NtHeader; // [rsp+40h] [rbp-238h] BYREF
  _BYTE Buffer[512]; // [rsp+50h] [rbp-228h] BYREF

  v4 = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  NumberOfBytesRead = 0;
  NtHeader = 0;
  if ( !ReadProcessMemory(hProcess, lpBaseAddress, Buffer, 0x200u, &NumberOfBytesRead) || NumberOfBytesRead != 512 )
    return 0;
  if ( RtlImageNtHeaderEx(0, Buffer, 0x200u, &NtHeader) >= 0 )
  {
    if ( NtHeader )
      return NtHeader->FileHeader.TimeDateStamp;
  }
  return v4;
}

```

## disassembly

```asm
0x18003ae98  mov     [rsp+arg_10], rbx
0x18003ae9d  push    rsi
0x18003ae9e  push    rdi
0x18003ae9f  push    r14
0x18003aea1  sub     rsp, 260h
0x18003aea8  mov     rax, cs:__security_cookie
0x18003aeaf  xor     rax, rsp
0x18003aeb2  mov     [rsp+278h+var_28], rax
0x18003aeba  mov     rsi, rdx
0x18003aebd  mov     rdi, rcx
0x18003aec0  xor     ebx, ebx
0x18003aec2  mov     r14d, 200h
0x18003aec8  mov     r8d, r14d; Size
0x18003aecb  xor     edx, edx; Val
0x18003aecd  lea     rcx, [rsp+278h+Buffer]; void *
0x18003aed2  call    memset_0
0x18003aed7  mov     [rsp+278h+NumberOfBytesRead], rbx
0x18003aedc  mov     [rsp+278h+NtHeader], rbx
0x18003aee1  lea     rax, [rsp+278h+NumberOfBytesRead]
0x18003aee6  mov     [rsp+278h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18003aeeb  mov     r9d, r14d; nSize
0x18003aeee  lea     r8, [rsp+278h+Buffer]; lpBuffer
0x18003aef3  mov     rdx, rsi; lpBaseAddress
0x18003aef6  mov     rcx, rdi; hProcess
0x18003aef9  call    cs:__imp_ReadProcessMemory
0x18003aeff  test    eax, eax
0x18003af01  jz      short loc_18003AF36
0x18003af03  cmp     [rsp+278h+NumberOfBytesRead], r14
0x18003af08  jnz     short loc_18003AF36
0x18003af0a  lea     r9, [rsp+278h+NtHeader]; NtHeader
0x18003af0f  mov     r8d, r14d; Size
0x18003af12  lea     rdx, [rsp+278h+Buffer]; BaseAddress
0x18003af17  xor     ecx, ecx; Flags
0x18003af19  call    cs:__imp_RtlImageNtHeaderEx
0x18003af1f  test    eax, eax
0x18003af21  js      short loc_18003AF34
0x18003af23  mov     rax, [rsp+278h+NtHeader]
0x18003af28  test    rax, rax
0x18003af2b  jz      short loc_18003AF34
0x18003af2d  mov     ebx, [rax+8]
0x18003af30  mov     [rsp+278h+var_248], ebx
0x18003af34  jmp     short loc_18003AF40
0x18003af36  xor     eax, eax
0x18003af38  jmp     short loc_18003AF42
0x18003af3a  xor     ebx, ebx
0x18003af3c  mov     [rsp+278h+var_248], ebx
0x18003af40  mov     eax, ebx
0x18003af42  mov     rcx, [rsp+278h+var_28]
0x18003af4a  xor     rcx, rsp; StackCookie
0x18003af4d  call    __security_check_cookie
0x18003af52  mov     rbx, [rsp+278h+arg_10]
0x18003af5a  add     rsp, 260h
0x18003af61  pop     r14
0x18003af63  pop     rdi
0x18003af64  pop     rsi
0x18003af65  retn
```
