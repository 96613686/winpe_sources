# _resetstkoflw_static

- ea: `0x18001e9ec`
- end: `0x18001eb1c`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ba90`

## callees

- `0x18001e9ec`
- `0x18001ed20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18001ea79`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18001ea79`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001ea6a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001ea6a`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18001eb0b`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18001eb0b`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001eaf1`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001eaf1`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18001ea57`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18001ea57`

## pseudocode

```c
_BOOL8 resetstkoflw_static()
{
  char *AllocationBase; // r15
  __int64 dwPageSize; // rdi
  ULONG v2; // ebx
  unsigned int v3; // edx
  ULONG v4; // ecx
  unsigned int v5; // eax
  unsigned int v6; // ecx
  unsigned int v8; // eax
  unsigned int v9; // esi
  char *v10; // rbx
  _BYTE Address[16]; // [rsp+10h] [rbp-10h] BYREF
  ULONG StackSizeInBytes; // [rsp+20h] [rbp+0h] BYREF
  DWORD flOldProtect; // [rsp+24h] [rbp+4h] BYREF
  _MEMORY_BASIC_INFORMATION Buffer; // [rsp+28h] [rbp+8h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+58h] [rbp+38h] BYREF

  flOldProtect = 0;
  memset(&Buffer, 0, sizeof(Buffer));
  StackSizeInBytes = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  if ( !VirtualQuery(Address, &Buffer, 0x30u) )
    return 0;
  AllocationBase = (char *)Buffer.AllocationBase;
  GetSystemInfo(&SystemInfo);
  dwPageSize = SystemInfo.dwPageSize;
  v2 = 0;
  if ( SetThreadStackGuarantee(&StackSizeInBytes) && StackSizeInBytes )
    v2 = StackSizeInBytes;
  v3 = dwPageSize - 1;
  v4 = dwPageSize - 1 + v2;
  if ( v4 < v2 )
    return 0;
  v5 = v4 & ~v3;
  if ( v5 )
  {
    v6 = v5 + dwPageSize;
    if ( v5 + (unsigned int)dwPageSize < v5 )
      return 0;
  }
  else
  {
    v6 = 0;
  }
  v8 = 3 * dwPageSize;
  if ( v6 >= 3 * (int)dwPageSize )
    v8 = v6;
  v9 = v8;
  v10 = (char *)(((unsigned __int64)Address & ~(unsigned __int64)v3) - v8);
  if ( v10 < &AllocationBase[dwPageSize] || !VirtualAlloc(v10, v8, 0x1000u, 4u) )
    return 0;
  return VirtualProtect(v10, v9, 0x104u, &flOldProtect);
}

```

## disassembly

```asm
0x18001e9ec  push    rbp
0x18001e9ee  push    rbx
0x18001e9ef  push    rsi
0x18001e9f0  push    rdi
0x18001e9f1  push    r14
0x18001e9f3  push    r15
0x18001e9f5  sub     rsp, 98h
0x18001e9fc  lea     rbp, [rsp+20h]
0x18001ea01  mov     rax, cs:__security_cookie
0x18001ea08  xor     rax, rbp
0x18001ea0b  mov     [rbp+0A0h+var_38], rax
0x18001ea0f  mov     eax, [rsp+0C0h+var_C0]
0x18001ea12  xorps   xmm0, xmm0
0x18001ea15  xorps   xmm1, xmm1
0x18001ea18  mov     [rbp+0A0h+flOldProtect], 0
0x18001ea1f  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x18001ea23  mov     [rbp+0A0h+StackSizeInBytes], 0
0x18001ea2a  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x18001ea2e  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x18001ea32  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x18001ea36  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x18001ea3a  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x18001ea3e  sub     rsp, 10h
0x18001ea42  lea     r14, [rsp+0D0h+Address]
0x18001ea47  mov     eax, [r14]
0x18001ea4a  mov     r8d, 30h ; '0'; dwLength
0x18001ea50  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x18001ea54  mov     rcx, r14; lpAddress
0x18001ea57  call    cs:__imp_VirtualQuery
0x18001ea5d  test    rax, rax
0x18001ea60  jz      short loc_18001EAA5
0x18001ea62  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x18001ea66  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x18001ea6a  call    cs:__imp_GetSystemInfo
0x18001ea70  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x18001ea73  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x18001ea77  xor     ebx, ebx
0x18001ea79  call    cs:__imp_SetThreadStackGuarantee
0x18001ea7f  cmp     eax, 1
0x18001ea82  jnz     short loc_18001EA8C
0x18001ea84  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x18001ea87  test    eax, eax
0x18001ea89  cmovnz  ebx, eax
0x18001ea8c  lea     edx, [rdi-1]
0x18001ea8f  lea     ecx, [rdx+rbx]
0x18001ea92  cmp     ecx, ebx
0x18001ea94  jb      short loc_18001EAA5
0x18001ea96  mov     eax, edx
0x18001ea98  not     eax
0x18001ea9a  and     eax, ecx
0x18001ea9c  jz      short loc_18001EAC0
0x18001ea9e  lea     ecx, [rax+rdi]
0x18001eaa1  cmp     ecx, eax
0x18001eaa3  jnb     short loc_18001EAC2
0x18001eaa5  xor     eax, eax
0x18001eaa7  mov     rcx, [rbp+0A0h+var_38]
0x18001eaab  xor     rcx, rbp; StackCookie
0x18001eaae  call    __security_check_cookie
0x18001eab3  lea     rsp, [rbp+78h]
0x18001eab7  pop     r15
0x18001eab9  pop     r14
0x18001eabb  pop     rdi
0x18001eabc  pop     rsi
0x18001eabd  pop     rbx
0x18001eabe  pop     rbp
0x18001eabf  retn
0x18001eac0  mov     ecx, eax
0x18001eac2  lea     eax, [rdi+rdi*2]
0x18001eac5  mov     ebx, edx
0x18001eac7  cmp     ecx, eax
0x18001eac9  not     rbx
0x18001eacc  cmovnb  eax, ecx
0x18001eacf  and     rbx, r14
0x18001ead2  mov     esi, eax
0x18001ead4  lea     rax, [r15+rdi]
0x18001ead8  sub     rbx, rsi
0x18001eadb  cmp     rbx, rax
0x18001eade  jb      short loc_18001EAA5
0x18001eae0  mov     r9d, 4; flProtect
0x18001eae6  mov     r8d, 1000h; flAllocationType
0x18001eaec  mov     edx, esi; dwSize
0x18001eaee  mov     rcx, rbx; lpAddress
0x18001eaf1  call    cs:__imp_VirtualAlloc
0x18001eaf7  test    rax, rax
0x18001eafa  jz      short loc_18001EAA5
0x18001eafc  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x18001eb00  mov     r8d, 104h; flNewProtect
0x18001eb06  mov     edx, esi; dwSize
0x18001eb08  mov     rcx, rbx; lpAddress
0x18001eb0b  call    cs:__imp_VirtualProtect
0x18001eb11  xor     ecx, ecx
0x18001eb13  test    eax, eax
0x18001eb15  setnz   cl
0x18001eb18  mov     eax, ecx
0x18001eb1a  jmp     short loc_18001EAA7
```
