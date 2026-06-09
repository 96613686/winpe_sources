# _resetstkoflw_static

- ea: `0x180024d64`
- end: `0x180024e94`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009160`

## callees

- `0x180024d64`
- `0x180024ef0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x180024df1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x180024df1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180024de2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180024de2`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180024e69`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180024e69`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180024dcf`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180024dcf`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180024e83`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180024e83`

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
0x180024d64  push    rbp
0x180024d66  push    rbx
0x180024d67  push    rsi
0x180024d68  push    rdi
0x180024d69  push    r14
0x180024d6b  push    r15
0x180024d6d  sub     rsp, 98h
0x180024d74  lea     rbp, [rsp+20h]
0x180024d79  mov     rax, cs:__security_cookie
0x180024d80  xor     rax, rbp
0x180024d83  mov     [rbp+0A0h+var_38], rax
0x180024d87  mov     eax, [rsp+0C0h+var_C0]
0x180024d8a  xorps   xmm0, xmm0
0x180024d8d  xorps   xmm1, xmm1
0x180024d90  mov     [rbp+0A0h+flOldProtect], 0
0x180024d97  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x180024d9b  mov     [rbp+0A0h+StackSizeInBytes], 0
0x180024da2  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x180024da6  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x180024daa  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x180024dae  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x180024db2  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x180024db6  sub     rsp, 10h
0x180024dba  lea     r14, [rsp+0D0h+Address]
0x180024dbf  mov     eax, [r14]
0x180024dc2  mov     r8d, 30h ; '0'; dwLength
0x180024dc8  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x180024dcc  mov     rcx, r14; lpAddress
0x180024dcf  call    cs:__imp_VirtualQuery
0x180024dd5  test    rax, rax
0x180024dd8  jz      short loc_180024E1D
0x180024dda  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x180024dde  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x180024de2  call    cs:__imp_GetSystemInfo
0x180024de8  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x180024deb  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x180024def  xor     ebx, ebx
0x180024df1  call    cs:__imp_SetThreadStackGuarantee
0x180024df7  cmp     eax, 1
0x180024dfa  jnz     short loc_180024E04
0x180024dfc  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x180024dff  test    eax, eax
0x180024e01  cmovnz  ebx, eax
0x180024e04  lea     edx, [rdi-1]
0x180024e07  lea     ecx, [rdx+rbx]
0x180024e0a  cmp     ecx, ebx
0x180024e0c  jb      short loc_180024E1D
0x180024e0e  mov     eax, edx
0x180024e10  not     eax
0x180024e12  and     eax, ecx
0x180024e14  jz      short loc_180024E38
0x180024e16  lea     ecx, [rax+rdi]
0x180024e19  cmp     ecx, eax
0x180024e1b  jnb     short loc_180024E3A
0x180024e1d  xor     eax, eax
0x180024e1f  mov     rcx, [rbp+0A0h+var_38]
0x180024e23  xor     rcx, rbp; StackCookie
0x180024e26  call    __security_check_cookie
0x180024e2b  lea     rsp, [rbp+78h]
0x180024e2f  pop     r15
0x180024e31  pop     r14
0x180024e33  pop     rdi
0x180024e34  pop     rsi
0x180024e35  pop     rbx
0x180024e36  pop     rbp
0x180024e37  retn
0x180024e38  mov     ecx, eax
0x180024e3a  lea     eax, [rdi+rdi*2]
0x180024e3d  mov     ebx, edx
0x180024e3f  cmp     ecx, eax
0x180024e41  not     rbx
0x180024e44  cmovnb  eax, ecx
0x180024e47  and     rbx, r14
0x180024e4a  mov     esi, eax
0x180024e4c  lea     rax, [r15+rdi]
0x180024e50  sub     rbx, rsi
0x180024e53  cmp     rbx, rax
0x180024e56  jb      short loc_180024E1D
0x180024e58  mov     r9d, 4; flProtect
0x180024e5e  mov     r8d, 1000h; flAllocationType
0x180024e64  mov     edx, esi; dwSize
0x180024e66  mov     rcx, rbx; lpAddress
0x180024e69  call    cs:__imp_VirtualAlloc
0x180024e6f  test    rax, rax
0x180024e72  jz      short loc_180024E1D
0x180024e74  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x180024e78  mov     r8d, 104h; flNewProtect
0x180024e7e  mov     edx, esi; dwSize
0x180024e80  mov     rcx, rbx; lpAddress
0x180024e83  call    cs:__imp_VirtualProtect
0x180024e89  xor     ecx, ecx
0x180024e8b  test    eax, eax
0x180024e8d  setnz   cl
0x180024e90  mov     eax, ecx
0x180024e92  jmp     short loc_180024E1F
```
