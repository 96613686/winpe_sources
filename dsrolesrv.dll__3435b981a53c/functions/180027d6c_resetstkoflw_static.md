# _resetstkoflw_static

- ea: `0x180027d6c`
- end: `0x180027e9c`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180027d44`

## callees

- `0x180027d6c`
- `0x18002c050`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x180027e8b`
- `KERNEL32!VirtualProtect` at `0x180027e8b`
- `KERNEL32!VirtualAlloc` at `0x180027e71`
- `KERNEL32!VirtualAlloc` at `0x180027e71`
- `KERNEL32!GetSystemInfo` at `0x180027dea`
- `KERNEL32!GetSystemInfo` at `0x180027dea`
- `KERNEL32!SetThreadStackGuarantee` at `0x180027df9`
- `KERNEL32!SetThreadStackGuarantee` at `0x180027df9`
- `KERNEL32!VirtualQuery` at `0x180027dd7`
- `KERNEL32!VirtualQuery` at `0x180027dd7`

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
0x180027d6c  push    rbp
0x180027d6e  push    rbx
0x180027d6f  push    rsi
0x180027d70  push    rdi
0x180027d71  push    r14
0x180027d73  push    r15
0x180027d75  sub     rsp, 98h
0x180027d7c  lea     rbp, [rsp+20h]
0x180027d81  mov     rax, cs:__security_cookie
0x180027d88  xor     rax, rbp
0x180027d8b  mov     [rbp+0A0h+var_38], rax
0x180027d8f  mov     eax, [rsp+0C0h+var_C0]
0x180027d92  xorps   xmm0, xmm0
0x180027d95  xorps   xmm1, xmm1
0x180027d98  mov     [rbp+0A0h+flOldProtect], 0
0x180027d9f  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x180027da3  mov     [rbp+0A0h+StackSizeInBytes], 0
0x180027daa  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x180027dae  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x180027db2  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x180027db6  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x180027dba  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x180027dbe  sub     rsp, 10h
0x180027dc2  lea     r14, [rsp+0D0h+Address]
0x180027dc7  mov     eax, [r14]
0x180027dca  mov     r8d, 30h ; '0'; dwLength
0x180027dd0  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x180027dd4  mov     rcx, r14; lpAddress
0x180027dd7  call    cs:__imp_VirtualQuery
0x180027ddd  test    rax, rax
0x180027de0  jz      short loc_180027E25
0x180027de2  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x180027de6  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x180027dea  call    cs:__imp_GetSystemInfo
0x180027df0  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x180027df3  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x180027df7  xor     ebx, ebx
0x180027df9  call    cs:__imp_SetThreadStackGuarantee
0x180027dff  cmp     eax, 1
0x180027e02  jnz     short loc_180027E0C
0x180027e04  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x180027e07  test    eax, eax
0x180027e09  cmovnz  ebx, eax
0x180027e0c  lea     edx, [rdi-1]
0x180027e0f  lea     ecx, [rdx+rbx]
0x180027e12  cmp     ecx, ebx
0x180027e14  jb      short loc_180027E25
0x180027e16  mov     eax, edx
0x180027e18  not     eax
0x180027e1a  and     eax, ecx
0x180027e1c  jz      short loc_180027E40
0x180027e1e  lea     ecx, [rax+rdi]
0x180027e21  cmp     ecx, eax
0x180027e23  jnb     short loc_180027E42
0x180027e25  xor     eax, eax
0x180027e27  mov     rcx, [rbp+0A0h+var_38]
0x180027e2b  xor     rcx, rbp; StackCookie
0x180027e2e  call    __security_check_cookie
0x180027e33  lea     rsp, [rbp+78h]
0x180027e37  pop     r15
0x180027e39  pop     r14
0x180027e3b  pop     rdi
0x180027e3c  pop     rsi
0x180027e3d  pop     rbx
0x180027e3e  pop     rbp
0x180027e3f  retn
0x180027e40  mov     ecx, eax
0x180027e42  lea     eax, [rdi+rdi*2]
0x180027e45  mov     ebx, edx
0x180027e47  cmp     ecx, eax
0x180027e49  not     rbx
0x180027e4c  cmovnb  eax, ecx
0x180027e4f  and     rbx, r14
0x180027e52  mov     esi, eax
0x180027e54  lea     rax, [r15+rdi]
0x180027e58  sub     rbx, rsi
0x180027e5b  cmp     rbx, rax
0x180027e5e  jb      short loc_180027E25
0x180027e60  mov     r9d, 4; flProtect
0x180027e66  mov     r8d, 1000h; flAllocationType
0x180027e6c  mov     edx, esi; dwSize
0x180027e6e  mov     rcx, rbx; lpAddress
0x180027e71  call    cs:__imp_VirtualAlloc
0x180027e77  test    rax, rax
0x180027e7a  jz      short loc_180027E25
0x180027e7c  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x180027e80  mov     r8d, 104h; flNewProtect
0x180027e86  mov     edx, esi; dwSize
0x180027e88  mov     rcx, rbx; lpAddress
0x180027e8b  call    cs:__imp_VirtualProtect
0x180027e91  xor     ecx, ecx
0x180027e93  test    eax, eax
0x180027e95  setnz   cl
0x180027e98  mov     eax, ecx
0x180027e9a  jmp     short loc_180027E27
```
