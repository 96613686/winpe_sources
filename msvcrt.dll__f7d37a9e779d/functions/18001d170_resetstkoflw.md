# _resetstkoflw

- ea: `0x18001d170`
- end: `0x18001d2a0`
- name: `_resetstkoflw`
- size: `304`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002d80c`

## callees

- `0x18001d170`
- `0x180079760`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18001d1db`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18001d1db`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18001d28f`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18001d28f`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001d275`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001d275`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18001d1fd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18001d1fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001d1ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001d1ee`

## pseudocode

```c
int __cdecl resetstkoflw()
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
0x18001d170  push    rbp
0x18001d172  push    rbx
0x18001d173  push    rsi
0x18001d174  push    rdi
0x18001d175  push    r14
0x18001d177  push    r15
0x18001d179  sub     rsp, 98h
0x18001d180  lea     rbp, [rsp+20h]
0x18001d185  mov     rax, cs:__security_cookie
0x18001d18c  xor     rax, rbp
0x18001d18f  mov     [rbp+0A0h+var_38], rax
0x18001d193  mov     eax, [rsp+0C0h+var_C0]
0x18001d196  xorps   xmm0, xmm0
0x18001d199  xorps   xmm1, xmm1
0x18001d19c  mov     [rbp+0A0h+flOldProtect], 0
0x18001d1a3  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x18001d1a7  mov     [rbp+0A0h+StackSizeInBytes], 0
0x18001d1ae  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x18001d1b2  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x18001d1b6  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x18001d1ba  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x18001d1be  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x18001d1c2  sub     rsp, 10h
0x18001d1c6  lea     r14, [rsp+0D0h+Address]
0x18001d1cb  mov     eax, [r14]
0x18001d1ce  mov     r8d, 30h ; '0'; dwLength
0x18001d1d4  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x18001d1d8  mov     rcx, r14; lpAddress
0x18001d1db  call    cs:__imp_VirtualQuery
0x18001d1e1  test    rax, rax
0x18001d1e4  jz      short loc_18001D229
0x18001d1e6  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x18001d1ea  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x18001d1ee  call    cs:__imp_GetSystemInfo
0x18001d1f4  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x18001d1f7  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x18001d1fb  xor     ebx, ebx
0x18001d1fd  call    cs:__imp_SetThreadStackGuarantee
0x18001d203  cmp     eax, 1
0x18001d206  jnz     short loc_18001D210
0x18001d208  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x18001d20b  test    eax, eax
0x18001d20d  cmovnz  ebx, eax
0x18001d210  lea     edx, [rdi-1]
0x18001d213  lea     ecx, [rdx+rbx]
0x18001d216  cmp     ecx, ebx
0x18001d218  jb      short loc_18001D229
0x18001d21a  mov     eax, edx
0x18001d21c  not     eax
0x18001d21e  and     eax, ecx
0x18001d220  jz      short loc_18001D244
0x18001d222  lea     ecx, [rax+rdi]
0x18001d225  cmp     ecx, eax
0x18001d227  jnb     short loc_18001D246
0x18001d229  xor     eax, eax
0x18001d22b  mov     rcx, [rbp+0A0h+var_38]
0x18001d22f  xor     rcx, rbp; StackCookie
0x18001d232  call    __security_check_cookie
0x18001d237  lea     rsp, [rbp+78h]
0x18001d23b  pop     r15
0x18001d23d  pop     r14
0x18001d23f  pop     rdi
0x18001d240  pop     rsi
0x18001d241  pop     rbx
0x18001d242  pop     rbp
0x18001d243  retn
0x18001d244  mov     ecx, eax
0x18001d246  lea     eax, [rdi+rdi*2]
0x18001d249  mov     ebx, edx
0x18001d24b  cmp     ecx, eax
0x18001d24d  not     rbx
0x18001d250  cmovnb  eax, ecx
0x18001d253  and     rbx, r14
0x18001d256  mov     esi, eax
0x18001d258  lea     rax, [r15+rdi]
0x18001d25c  sub     rbx, rsi
0x18001d25f  cmp     rbx, rax
0x18001d262  jb      short loc_18001D229
0x18001d264  mov     r9d, 4; flProtect
0x18001d26a  mov     r8d, 1000h; flAllocationType
0x18001d270  mov     edx, esi; dwSize
0x18001d272  mov     rcx, rbx; lpAddress
0x18001d275  call    cs:__imp_VirtualAlloc
0x18001d27b  test    rax, rax
0x18001d27e  jz      short loc_18001D229
0x18001d280  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x18001d284  mov     r8d, 104h; flNewProtect
0x18001d28a  mov     edx, esi; dwSize
0x18001d28c  mov     rcx, rbx; lpAddress
0x18001d28f  call    cs:__imp_VirtualProtect
0x18001d295  xor     ecx, ecx
0x18001d297  test    eax, eax
0x18001d299  setnz   cl
0x18001d29c  mov     eax, ecx
0x18001d29e  jmp     short loc_18001D22B
```
