# _resetstkoflw_static

- ea: `0x18005d4c8`
- end: `0x18005d5f8`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18005d4a0`

## callees

- `0x180042800`
- `0x18005d4c8`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18005d5e7`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18005d5e7`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18005d5cd`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18005d5cd`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18005d533`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18005d533`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18005d555`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18005d555`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18005d546`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18005d546`

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
0x18005d4c8  push    rbp
0x18005d4ca  push    rbx
0x18005d4cb  push    rsi
0x18005d4cc  push    rdi
0x18005d4cd  push    r14
0x18005d4cf  push    r15
0x18005d4d1  sub     rsp, 98h
0x18005d4d8  lea     rbp, [rsp+20h]
0x18005d4dd  mov     rax, cs:__security_cookie
0x18005d4e4  xor     rax, rbp
0x18005d4e7  mov     [rbp+0A0h+var_38], rax
0x18005d4eb  mov     eax, [rsp+0C0h+var_C0]
0x18005d4ee  xorps   xmm0, xmm0
0x18005d4f1  xorps   xmm1, xmm1
0x18005d4f4  mov     [rbp+0A0h+flOldProtect], 0
0x18005d4fb  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x18005d4ff  mov     [rbp+0A0h+StackSizeInBytes], 0
0x18005d506  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x18005d50a  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x18005d50e  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x18005d512  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x18005d516  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x18005d51a  sub     rsp, 10h
0x18005d51e  lea     r14, [rsp+0D0h+Address]
0x18005d523  mov     eax, [r14]
0x18005d526  mov     r8d, 30h ; '0'; dwLength
0x18005d52c  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x18005d530  mov     rcx, r14; lpAddress
0x18005d533  call    cs:__imp_VirtualQuery
0x18005d539  test    rax, rax
0x18005d53c  jz      short loc_18005D581
0x18005d53e  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x18005d542  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x18005d546  call    cs:__imp_GetSystemInfo
0x18005d54c  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x18005d54f  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x18005d553  xor     ebx, ebx
0x18005d555  call    cs:__imp_SetThreadStackGuarantee
0x18005d55b  cmp     eax, 1
0x18005d55e  jnz     short loc_18005D568
0x18005d560  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x18005d563  test    eax, eax
0x18005d565  cmovnz  ebx, eax
0x18005d568  lea     edx, [rdi-1]
0x18005d56b  lea     ecx, [rdx+rbx]
0x18005d56e  cmp     ecx, ebx
0x18005d570  jb      short loc_18005D581
0x18005d572  mov     eax, edx
0x18005d574  not     eax
0x18005d576  and     eax, ecx
0x18005d578  jz      short loc_18005D59C
0x18005d57a  lea     ecx, [rax+rdi]
0x18005d57d  cmp     ecx, eax
0x18005d57f  jnb     short loc_18005D59E
0x18005d581  xor     eax, eax
0x18005d583  mov     rcx, [rbp+0A0h+var_38]
0x18005d587  xor     rcx, rbp; StackCookie
0x18005d58a  call    __security_check_cookie
0x18005d58f  lea     rsp, [rbp+78h]
0x18005d593  pop     r15
0x18005d595  pop     r14
0x18005d597  pop     rdi
0x18005d598  pop     rsi
0x18005d599  pop     rbx
0x18005d59a  pop     rbp
0x18005d59b  retn
0x18005d59c  mov     ecx, eax
0x18005d59e  lea     eax, [rdi+rdi*2]
0x18005d5a1  mov     ebx, edx
0x18005d5a3  cmp     ecx, eax
0x18005d5a5  not     rbx
0x18005d5a8  cmovnb  eax, ecx
0x18005d5ab  and     rbx, r14
0x18005d5ae  mov     esi, eax
0x18005d5b0  lea     rax, [r15+rdi]
0x18005d5b4  sub     rbx, rsi
0x18005d5b7  cmp     rbx, rax
0x18005d5ba  jb      short loc_18005D581
0x18005d5bc  mov     r9d, 4; flProtect
0x18005d5c2  mov     r8d, 1000h; flAllocationType
0x18005d5c8  mov     edx, esi; dwSize
0x18005d5ca  mov     rcx, rbx; lpAddress
0x18005d5cd  call    cs:__imp_VirtualAlloc
0x18005d5d3  test    rax, rax
0x18005d5d6  jz      short loc_18005D581
0x18005d5d8  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x18005d5dc  mov     r8d, 104h; flNewProtect
0x18005d5e2  mov     edx, esi; dwSize
0x18005d5e4  mov     rcx, rbx; lpAddress
0x18005d5e7  call    cs:__imp_VirtualProtect
0x18005d5ed  xor     ecx, ecx
0x18005d5ef  test    eax, eax
0x18005d5f1  setnz   cl
0x18005d5f4  mov     eax, ecx
0x18005d5f6  jmp     short loc_18005D583
```
