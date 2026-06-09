# _resetstkoflw_static

- ea: `0x18006b57c`
- end: `0x18006b6ac`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010b14`

## callees

- `0x18002fb50`
- `0x18006b57c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18006b609`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18006b609`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18006b5fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18006b5fa`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18006b681`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18006b681`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18006b69b`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18006b69b`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18006b5e7`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18006b5e7`

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
  struct _SYSTEM_INFO SystemInfo; // [rsp+58h] [rbp+38h] BYREF

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
0x18006b57c  push    rbp
0x18006b57e  push    rbx
0x18006b57f  push    rsi
0x18006b580  push    rdi
0x18006b581  push    r14
0x18006b583  push    r15
0x18006b585  sub     rsp, 98h
0x18006b58c  lea     rbp, [rsp+20h]
0x18006b591  mov     rax, cs:__security_cookie
0x18006b598  xor     rax, rbp
0x18006b59b  mov     [rbp+0A0h+var_38], rax
0x18006b59f  mov     eax, [rsp+0C0h+var_C0]
0x18006b5a2  xorps   xmm0, xmm0
0x18006b5a5  xorps   xmm1, xmm1
0x18006b5a8  mov     [rbp+0A0h+flOldProtect], 0
0x18006b5af  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x18006b5b3  mov     [rbp+0A0h+StackSizeInBytes], 0
0x18006b5ba  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x18006b5be  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x18006b5c2  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x18006b5c6  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x18006b5ca  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x18006b5ce  sub     rsp, 10h
0x18006b5d2  lea     r14, [rsp+0D0h+Address]
0x18006b5d7  mov     eax, [r14]
0x18006b5da  mov     r8d, 30h ; '0'; dwLength
0x18006b5e0  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x18006b5e4  mov     rcx, r14; lpAddress
0x18006b5e7  call    cs:__imp_VirtualQuery
0x18006b5ed  test    rax, rax
0x18006b5f0  jz      short loc_18006B635
0x18006b5f2  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x18006b5f6  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x18006b5fa  call    cs:__imp_GetSystemInfo
0x18006b600  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x18006b603  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x18006b607  xor     ebx, ebx
0x18006b609  call    cs:__imp_SetThreadStackGuarantee
0x18006b60f  cmp     eax, 1
0x18006b612  jnz     short loc_18006B61C
0x18006b614  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x18006b617  test    eax, eax
0x18006b619  cmovnz  ebx, eax
0x18006b61c  lea     edx, [rdi-1]
0x18006b61f  lea     ecx, [rdx+rbx]
0x18006b622  cmp     ecx, ebx
0x18006b624  jb      short loc_18006B635
0x18006b626  mov     eax, edx
0x18006b628  not     eax
0x18006b62a  and     eax, ecx
0x18006b62c  jz      short loc_18006B650
0x18006b62e  lea     ecx, [rax+rdi]
0x18006b631  cmp     ecx, eax
0x18006b633  jnb     short loc_18006B652
0x18006b635  xor     eax, eax
0x18006b637  mov     rcx, [rbp+0A0h+var_38]
0x18006b63b  xor     rcx, rbp; StackCookie
0x18006b63e  call    __security_check_cookie
0x18006b643  lea     rsp, [rbp+78h]
0x18006b647  pop     r15
0x18006b649  pop     r14
0x18006b64b  pop     rdi
0x18006b64c  pop     rsi
0x18006b64d  pop     rbx
0x18006b64e  pop     rbp
0x18006b64f  retn
0x18006b650  mov     ecx, eax
0x18006b652  lea     eax, [rdi+rdi*2]
0x18006b655  mov     ebx, edx
0x18006b657  cmp     ecx, eax
0x18006b659  not     rbx
0x18006b65c  cmovnb  eax, ecx
0x18006b65f  and     rbx, r14
0x18006b662  mov     esi, eax
0x18006b664  lea     rax, [r15+rdi]
0x18006b668  sub     rbx, rsi
0x18006b66b  cmp     rbx, rax
0x18006b66e  jb      short loc_18006B635
0x18006b670  mov     r9d, 4; flProtect
0x18006b676  mov     r8d, 1000h; flAllocationType
0x18006b67c  mov     edx, esi; dwSize
0x18006b67e  mov     rcx, rbx; lpAddress
0x18006b681  call    cs:__imp_VirtualAlloc
0x18006b687  test    rax, rax
0x18006b68a  jz      short loc_18006B635
0x18006b68c  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x18006b690  mov     r8d, 104h; flNewProtect
0x18006b696  mov     edx, esi; dwSize
0x18006b698  mov     rcx, rbx; lpAddress
0x18006b69b  call    cs:__imp_VirtualProtect
0x18006b6a1  xor     ecx, ecx
0x18006b6a3  test    eax, eax
0x18006b6a5  setnz   cl
0x18006b6a8  mov     eax, ecx
0x18006b6aa  jmp     short loc_18006B637
```
