# _resetstkoflw_static

- ea: `0x18002df6c`
- end: `0x18002e09c`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002df44`

## callees

- `0x18002df6c`
- `0x18002e230`

## import_xrefs

- `KERNEL32!SetThreadStackGuarantee` at `0x18002dff9`
- `KERNEL32!SetThreadStackGuarantee` at `0x18002dff9`
- `KERNEL32!VirtualProtect` at `0x18002e08b`
- `KERNEL32!VirtualProtect` at `0x18002e08b`
- `KERNEL32!VirtualAlloc` at `0x18002e071`
- `KERNEL32!VirtualAlloc` at `0x18002e071`
- `KERNEL32!GetSystemInfo` at `0x18002dfea`
- `KERNEL32!GetSystemInfo` at `0x18002dfea`
- `KERNEL32!VirtualQuery` at `0x18002dfd7`
- `KERNEL32!VirtualQuery` at `0x18002dfd7`

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
  struct _MEMORY_BASIC_INFORMATION Buffer; // [rsp+28h] [rbp+8h] BYREF
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
0x18002df6c  push    rbp
0x18002df6e  push    rbx
0x18002df6f  push    rsi
0x18002df70  push    rdi
0x18002df71  push    r14
0x18002df73  push    r15
0x18002df75  sub     rsp, 98h
0x18002df7c  lea     rbp, [rsp+20h]
0x18002df81  mov     rax, cs:__security_cookie
0x18002df88  xor     rax, rbp
0x18002df8b  mov     [rbp+0A0h+var_38], rax
0x18002df8f  mov     eax, [rsp+0C0h+var_C0]
0x18002df92  xorps   xmm0, xmm0
0x18002df95  xorps   xmm1, xmm1
0x18002df98  mov     [rbp+0A0h+flOldProtect], 0
0x18002df9f  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x18002dfa3  mov     [rbp+0A0h+StackSizeInBytes], 0
0x18002dfaa  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x18002dfae  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x18002dfb2  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x18002dfb6  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x18002dfba  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x18002dfbe  sub     rsp, 10h
0x18002dfc2  lea     r14, [rsp+0D0h+Address]
0x18002dfc7  mov     eax, [r14]
0x18002dfca  mov     r8d, 30h ; '0'; dwLength
0x18002dfd0  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x18002dfd4  mov     rcx, r14; lpAddress
0x18002dfd7  call    cs:__imp_VirtualQuery
0x18002dfdd  test    rax, rax
0x18002dfe0  jz      short loc_18002E025
0x18002dfe2  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x18002dfe6  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x18002dfea  call    cs:__imp_GetSystemInfo
0x18002dff0  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x18002dff3  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x18002dff7  xor     ebx, ebx
0x18002dff9  call    cs:__imp_SetThreadStackGuarantee
0x18002dfff  cmp     eax, 1
0x18002e002  jnz     short loc_18002E00C
0x18002e004  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x18002e007  test    eax, eax
0x18002e009  cmovnz  ebx, eax
0x18002e00c  lea     edx, [rdi-1]
0x18002e00f  lea     ecx, [rdx+rbx]
0x18002e012  cmp     ecx, ebx
0x18002e014  jb      short loc_18002E025
0x18002e016  mov     eax, edx
0x18002e018  not     eax
0x18002e01a  and     eax, ecx
0x18002e01c  jz      short loc_18002E040
0x18002e01e  lea     ecx, [rax+rdi]
0x18002e021  cmp     ecx, eax
0x18002e023  jnb     short loc_18002E042
0x18002e025  xor     eax, eax
0x18002e027  mov     rcx, [rbp+0A0h+var_38]
0x18002e02b  xor     rcx, rbp; StackCookie
0x18002e02e  call    __security_check_cookie
0x18002e033  lea     rsp, [rbp+78h]
0x18002e037  pop     r15
0x18002e039  pop     r14
0x18002e03b  pop     rdi
0x18002e03c  pop     rsi
0x18002e03d  pop     rbx
0x18002e03e  pop     rbp
0x18002e03f  retn
0x18002e040  mov     ecx, eax
0x18002e042  lea     eax, [rdi+rdi*2]
0x18002e045  mov     ebx, edx
0x18002e047  cmp     ecx, eax
0x18002e049  not     rbx
0x18002e04c  cmovnb  eax, ecx
0x18002e04f  and     rbx, r14
0x18002e052  mov     esi, eax
0x18002e054  lea     rax, [r15+rdi]
0x18002e058  sub     rbx, rsi
0x18002e05b  cmp     rbx, rax
0x18002e05e  jb      short loc_18002E025
0x18002e060  mov     r9d, 4; flProtect
0x18002e066  mov     r8d, 1000h; flAllocationType
0x18002e06c  mov     edx, esi; dwSize
0x18002e06e  mov     rcx, rbx; lpAddress
0x18002e071  call    cs:__imp_VirtualAlloc
0x18002e077  test    rax, rax
0x18002e07a  jz      short loc_18002E025
0x18002e07c  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x18002e080  mov     r8d, 104h; flNewProtect
0x18002e086  mov     edx, esi; dwSize
0x18002e088  mov     rcx, rbx; lpAddress
0x18002e08b  call    cs:__imp_VirtualProtect
0x18002e091  xor     ecx, ecx
0x18002e093  test    eax, eax
0x18002e095  setnz   cl
0x18002e098  mov     eax, ecx
0x18002e09a  jmp     short loc_18002E027
```
