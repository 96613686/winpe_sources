# _resetstkoflw_static

- ea: `0x18001e0e0`
- end: `0x18001e210`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015c4c`

## callees

- `0x18001e0e0`
- `0x18001f1b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18001e16d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18001e16d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001e15e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001e15e`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18001e1ff`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18001e1ff`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001e1e5`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001e1e5`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18001e14b`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18001e14b`

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
0x18001e0e0  push    rbp
0x18001e0e2  push    rbx
0x18001e0e3  push    rsi
0x18001e0e4  push    rdi
0x18001e0e5  push    r14
0x18001e0e7  push    r15
0x18001e0e9  sub     rsp, 98h
0x18001e0f0  lea     rbp, [rsp+20h]
0x18001e0f5  mov     rax, cs:__security_cookie
0x18001e0fc  xor     rax, rbp
0x18001e0ff  mov     [rbp+0A0h+var_38], rax
0x18001e103  mov     eax, [rsp+0C0h+var_C0]
0x18001e106  xorps   xmm0, xmm0
0x18001e109  xorps   xmm1, xmm1
0x18001e10c  mov     [rbp+0A0h+flOldProtect], 0
0x18001e113  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x18001e117  mov     [rbp+0A0h+StackSizeInBytes], 0
0x18001e11e  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x18001e122  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x18001e126  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x18001e12a  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x18001e12e  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x18001e132  sub     rsp, 10h
0x18001e136  lea     r14, [rsp+0D0h+Address]
0x18001e13b  mov     eax, [r14]
0x18001e13e  mov     r8d, 30h ; '0'; dwLength
0x18001e144  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x18001e148  mov     rcx, r14; lpAddress
0x18001e14b  call    cs:__imp_VirtualQuery
0x18001e151  test    rax, rax
0x18001e154  jz      short loc_18001E199
0x18001e156  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x18001e15a  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x18001e15e  call    cs:__imp_GetSystemInfo
0x18001e164  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x18001e167  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x18001e16b  xor     ebx, ebx
0x18001e16d  call    cs:__imp_SetThreadStackGuarantee
0x18001e173  cmp     eax, 1
0x18001e176  jnz     short loc_18001E180
0x18001e178  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x18001e17b  test    eax, eax
0x18001e17d  cmovnz  ebx, eax
0x18001e180  lea     edx, [rdi-1]
0x18001e183  lea     ecx, [rdx+rbx]
0x18001e186  cmp     ecx, ebx
0x18001e188  jb      short loc_18001E199
0x18001e18a  mov     eax, edx
0x18001e18c  not     eax
0x18001e18e  and     eax, ecx
0x18001e190  jz      short loc_18001E1B4
0x18001e192  lea     ecx, [rax+rdi]
0x18001e195  cmp     ecx, eax
0x18001e197  jnb     short loc_18001E1B6
0x18001e199  xor     eax, eax
0x18001e19b  mov     rcx, [rbp+0A0h+var_38]
0x18001e19f  xor     rcx, rbp; StackCookie
0x18001e1a2  call    __security_check_cookie
0x18001e1a7  lea     rsp, [rbp+78h]
0x18001e1ab  pop     r15
0x18001e1ad  pop     r14
0x18001e1af  pop     rdi
0x18001e1b0  pop     rsi
0x18001e1b1  pop     rbx
0x18001e1b2  pop     rbp
0x18001e1b3  retn
0x18001e1b4  mov     ecx, eax
0x18001e1b6  lea     eax, [rdi+rdi*2]
0x18001e1b9  mov     ebx, edx
0x18001e1bb  cmp     ecx, eax
0x18001e1bd  not     rbx
0x18001e1c0  cmovnb  eax, ecx
0x18001e1c3  and     rbx, r14
0x18001e1c6  mov     esi, eax
0x18001e1c8  lea     rax, [r15+rdi]
0x18001e1cc  sub     rbx, rsi
0x18001e1cf  cmp     rbx, rax
0x18001e1d2  jb      short loc_18001E199
0x18001e1d4  mov     r9d, 4; flProtect
0x18001e1da  mov     r8d, 1000h; flAllocationType
0x18001e1e0  mov     edx, esi; dwSize
0x18001e1e2  mov     rcx, rbx; lpAddress
0x18001e1e5  call    cs:__imp_VirtualAlloc
0x18001e1eb  test    rax, rax
0x18001e1ee  jz      short loc_18001E199
0x18001e1f0  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x18001e1f4  mov     r8d, 104h; flNewProtect
0x18001e1fa  mov     edx, esi; dwSize
0x18001e1fc  mov     rcx, rbx; lpAddress
0x18001e1ff  call    cs:__imp_VirtualProtect
0x18001e205  xor     ecx, ecx
0x18001e207  test    eax, eax
0x18001e209  setnz   cl
0x18001e20c  mov     eax, ecx
0x18001e20e  jmp     short loc_18001E19B
```
