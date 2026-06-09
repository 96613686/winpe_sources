# _resetstkoflw_static

- ea: `0x180044b74`
- end: `0x180044ca4`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018c80`

## callees

- `0x1800210f0`
- `0x180044b74`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x180044c01`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x180044c01`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180044bf2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180044bf2`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180044bdf`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180044bdf`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180044c79`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180044c79`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180044c93`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180044c93`

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
0x180044b74  push    rbp
0x180044b76  push    rbx
0x180044b77  push    rsi
0x180044b78  push    rdi
0x180044b79  push    r14
0x180044b7b  push    r15
0x180044b7d  sub     rsp, 98h
0x180044b84  lea     rbp, [rsp+20h]
0x180044b89  mov     rax, cs:__security_cookie
0x180044b90  xor     rax, rbp
0x180044b93  mov     [rbp+0A0h+var_38], rax
0x180044b97  mov     eax, [rsp+0C0h+var_C0]
0x180044b9a  xorps   xmm0, xmm0
0x180044b9d  xorps   xmm1, xmm1
0x180044ba0  mov     [rbp+0A0h+flOldProtect], 0
0x180044ba7  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x180044bab  mov     [rbp+0A0h+StackSizeInBytes], 0
0x180044bb2  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x180044bb6  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x180044bba  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x180044bbe  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x180044bc2  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x180044bc6  sub     rsp, 10h
0x180044bca  lea     r14, [rsp+0D0h+Address]
0x180044bcf  mov     eax, [r14]
0x180044bd2  mov     r8d, 30h ; '0'; dwLength
0x180044bd8  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x180044bdc  mov     rcx, r14; lpAddress
0x180044bdf  call    cs:__imp_VirtualQuery
0x180044be5  test    rax, rax
0x180044be8  jz      short loc_180044C2D
0x180044bea  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x180044bee  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x180044bf2  call    cs:__imp_GetSystemInfo
0x180044bf8  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x180044bfb  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x180044bff  xor     ebx, ebx
0x180044c01  call    cs:__imp_SetThreadStackGuarantee
0x180044c07  cmp     eax, 1
0x180044c0a  jnz     short loc_180044C14
0x180044c0c  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x180044c0f  test    eax, eax
0x180044c11  cmovnz  ebx, eax
0x180044c14  lea     edx, [rdi-1]
0x180044c17  lea     ecx, [rdx+rbx]
0x180044c1a  cmp     ecx, ebx
0x180044c1c  jb      short loc_180044C2D
0x180044c1e  mov     eax, edx
0x180044c20  not     eax
0x180044c22  and     eax, ecx
0x180044c24  jz      short loc_180044C48
0x180044c26  lea     ecx, [rax+rdi]
0x180044c29  cmp     ecx, eax
0x180044c2b  jnb     short loc_180044C4A
0x180044c2d  xor     eax, eax
0x180044c2f  mov     rcx, [rbp+0A0h+var_38]
0x180044c33  xor     rcx, rbp; StackCookie
0x180044c36  call    __security_check_cookie
0x180044c3b  lea     rsp, [rbp+78h]
0x180044c3f  pop     r15
0x180044c41  pop     r14
0x180044c43  pop     rdi
0x180044c44  pop     rsi
0x180044c45  pop     rbx
0x180044c46  pop     rbp
0x180044c47  retn
0x180044c48  mov     ecx, eax
0x180044c4a  lea     eax, [rdi+rdi*2]
0x180044c4d  mov     ebx, edx
0x180044c4f  cmp     ecx, eax
0x180044c51  not     rbx
0x180044c54  cmovnb  eax, ecx
0x180044c57  and     rbx, r14
0x180044c5a  mov     esi, eax
0x180044c5c  lea     rax, [r15+rdi]
0x180044c60  sub     rbx, rsi
0x180044c63  cmp     rbx, rax
0x180044c66  jb      short loc_180044C2D
0x180044c68  mov     r9d, 4; flProtect
0x180044c6e  mov     r8d, 1000h; flAllocationType
0x180044c74  mov     edx, esi; dwSize
0x180044c76  mov     rcx, rbx; lpAddress
0x180044c79  call    cs:__imp_VirtualAlloc
0x180044c7f  test    rax, rax
0x180044c82  jz      short loc_180044C2D
0x180044c84  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x180044c88  mov     r8d, 104h; flNewProtect
0x180044c8e  mov     edx, esi; dwSize
0x180044c90  mov     rcx, rbx; lpAddress
0x180044c93  call    cs:__imp_VirtualProtect
0x180044c99  xor     ecx, ecx
0x180044c9b  test    eax, eax
0x180044c9d  setnz   cl
0x180044ca0  mov     eax, ecx
0x180044ca2  jmp     short loc_180044C2F
```
