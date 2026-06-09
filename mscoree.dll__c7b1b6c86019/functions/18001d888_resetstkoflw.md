# _resetstkoflw

- ea: `0x18001d888`
- end: `0x18001d9b8`
- name: `_resetstkoflw`
- size: `304`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001abf8`

## callees

- `0x18001d888`
- `0x180041ac0`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x18001d906`
- `KERNEL32!GetSystemInfo` at `0x18001d906`
- `KERNEL32!VirtualProtect` at `0x18001d9a7`
- `KERNEL32!VirtualProtect` at `0x18001d9a7`
- `KERNEL32!VirtualAlloc` at `0x18001d98d`
- `KERNEL32!VirtualAlloc` at `0x18001d98d`
- `KERNEL32!VirtualQuery` at `0x18001d8f3`
- `KERNEL32!VirtualQuery` at `0x18001d8f3`
- `KERNEL32!SetThreadStackGuarantee` at `0x18001d915`
- `KERNEL32!SetThreadStackGuarantee` at `0x18001d915`

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
0x18001d888  push    rbp
0x18001d88a  push    rbx
0x18001d88b  push    rsi
0x18001d88c  push    rdi
0x18001d88d  push    r14
0x18001d88f  push    r15
0x18001d891  sub     rsp, 98h
0x18001d898  lea     rbp, [rsp+20h]
0x18001d89d  mov     rax, cs:__security_cookie
0x18001d8a4  xor     rax, rbp
0x18001d8a7  mov     [rbp+0A0h+var_38], rax
0x18001d8ab  mov     eax, [rsp+0C0h+var_C0]
0x18001d8ae  xorps   xmm0, xmm0
0x18001d8b1  xorps   xmm1, xmm1
0x18001d8b4  mov     [rbp+0A0h+flOldProtect], 0
0x18001d8bb  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x18001d8bf  mov     [rbp+0A0h+StackSizeInBytes], 0
0x18001d8c6  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x18001d8ca  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x18001d8ce  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x18001d8d2  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x18001d8d6  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x18001d8da  sub     rsp, 10h
0x18001d8de  lea     r14, [rsp+0D0h+Address]
0x18001d8e3  mov     eax, [r14]
0x18001d8e6  mov     r8d, 30h ; '0'; dwLength
0x18001d8ec  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x18001d8f0  mov     rcx, r14; lpAddress
0x18001d8f3  call    cs:__imp_VirtualQuery
0x18001d8f9  test    rax, rax
0x18001d8fc  jz      short loc_18001D941
0x18001d8fe  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x18001d902  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x18001d906  call    cs:__imp_GetSystemInfo
0x18001d90c  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x18001d90f  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x18001d913  xor     ebx, ebx
0x18001d915  call    cs:__imp_SetThreadStackGuarantee
0x18001d91b  cmp     eax, 1
0x18001d91e  jnz     short loc_18001D928
0x18001d920  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x18001d923  test    eax, eax
0x18001d925  cmovnz  ebx, eax
0x18001d928  lea     edx, [rdi-1]
0x18001d92b  lea     ecx, [rdx+rbx]
0x18001d92e  cmp     ecx, ebx
0x18001d930  jb      short loc_18001D941
0x18001d932  mov     eax, edx
0x18001d934  not     eax
0x18001d936  and     eax, ecx
0x18001d938  jz      short loc_18001D95C
0x18001d93a  lea     ecx, [rax+rdi]
0x18001d93d  cmp     ecx, eax
0x18001d93f  jnb     short loc_18001D95E
0x18001d941  xor     eax, eax
0x18001d943  mov     rcx, [rbp+0A0h+var_38]
0x18001d947  xor     rcx, rbp; StackCookie
0x18001d94a  call    __security_check_cookie
0x18001d94f  lea     rsp, [rbp+78h]
0x18001d953  pop     r15
0x18001d955  pop     r14
0x18001d957  pop     rdi
0x18001d958  pop     rsi
0x18001d959  pop     rbx
0x18001d95a  pop     rbp
0x18001d95b  retn
0x18001d95c  mov     ecx, eax
0x18001d95e  lea     eax, [rdi+rdi*2]
0x18001d961  mov     ebx, edx
0x18001d963  cmp     ecx, eax
0x18001d965  not     rbx
0x18001d968  cmovnb  eax, ecx
0x18001d96b  and     rbx, r14
0x18001d96e  mov     esi, eax
0x18001d970  lea     rax, [r15+rdi]
0x18001d974  sub     rbx, rsi
0x18001d977  cmp     rbx, rax
0x18001d97a  jb      short loc_18001D941
0x18001d97c  mov     r9d, 4; flProtect
0x18001d982  mov     r8d, 1000h; flAllocationType
0x18001d988  mov     edx, esi; dwSize
0x18001d98a  mov     rcx, rbx; lpAddress
0x18001d98d  call    cs:__imp_VirtualAlloc
0x18001d993  test    rax, rax
0x18001d996  jz      short loc_18001D941
0x18001d998  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x18001d99c  mov     r8d, 104h; flNewProtect
0x18001d9a2  mov     edx, esi; dwSize
0x18001d9a4  mov     rcx, rbx; lpAddress
0x18001d9a7  call    cs:__imp_VirtualProtect
0x18001d9ad  xor     ecx, ecx
0x18001d9af  test    eax, eax
0x18001d9b1  setnz   cl
0x18001d9b4  mov     eax, ecx
0x18001d9b6  jmp     short loc_18001D943
```
