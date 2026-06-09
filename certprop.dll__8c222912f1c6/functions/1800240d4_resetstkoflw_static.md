# _resetstkoflw_static

- ea: `0x1800240d4`
- end: `0x180024204`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a980`

## callees

- `0x180016090`
- `0x1800240d4`

## import_xrefs

- `KERNEL32!VirtualQuery` at `0x18002413f`
- `KERNEL32!VirtualQuery` at `0x18002413f`
- `KERNEL32!VirtualProtect` at `0x1800241f3`
- `KERNEL32!VirtualProtect` at `0x1800241f3`
- `KERNEL32!VirtualAlloc` at `0x1800241d9`
- `KERNEL32!VirtualAlloc` at `0x1800241d9`
- `KERNEL32!GetSystemInfo` at `0x180024152`
- `KERNEL32!GetSystemInfo` at `0x180024152`
- `KERNEL32!SetThreadStackGuarantee` at `0x180024161`
- `KERNEL32!SetThreadStackGuarantee` at `0x180024161`

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
0x1800240d4  push    rbp
0x1800240d6  push    rbx
0x1800240d7  push    rsi
0x1800240d8  push    rdi
0x1800240d9  push    r14
0x1800240db  push    r15
0x1800240dd  sub     rsp, 98h
0x1800240e4  lea     rbp, [rsp+20h]
0x1800240e9  mov     rax, cs:__security_cookie
0x1800240f0  xor     rax, rbp
0x1800240f3  mov     [rbp+0A0h+var_38], rax
0x1800240f7  mov     eax, [rsp+0C0h+var_C0]
0x1800240fa  xorps   xmm0, xmm0
0x1800240fd  xorps   xmm1, xmm1
0x180024100  mov     [rbp+0A0h+flOldProtect], 0
0x180024107  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x18002410b  mov     [rbp+0A0h+StackSizeInBytes], 0
0x180024112  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x180024116  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x18002411a  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x18002411e  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x180024122  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x180024126  sub     rsp, 10h
0x18002412a  lea     r14, [rsp+0D0h+Address]
0x18002412f  mov     eax, [r14]
0x180024132  mov     r8d, 30h ; '0'; dwLength
0x180024138  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x18002413c  mov     rcx, r14; lpAddress
0x18002413f  call    cs:__imp_VirtualQuery
0x180024145  test    rax, rax
0x180024148  jz      short loc_18002418D
0x18002414a  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x18002414e  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x180024152  call    cs:__imp_GetSystemInfo
0x180024158  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x18002415b  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x18002415f  xor     ebx, ebx
0x180024161  call    cs:__imp_SetThreadStackGuarantee
0x180024167  cmp     eax, 1
0x18002416a  jnz     short loc_180024174
0x18002416c  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x18002416f  test    eax, eax
0x180024171  cmovnz  ebx, eax
0x180024174  lea     edx, [rdi-1]
0x180024177  lea     ecx, [rdx+rbx]
0x18002417a  cmp     ecx, ebx
0x18002417c  jb      short loc_18002418D
0x18002417e  mov     eax, edx
0x180024180  not     eax
0x180024182  and     eax, ecx
0x180024184  jz      short loc_1800241A8
0x180024186  lea     ecx, [rax+rdi]
0x180024189  cmp     ecx, eax
0x18002418b  jnb     short loc_1800241AA
0x18002418d  xor     eax, eax
0x18002418f  mov     rcx, [rbp+0A0h+var_38]
0x180024193  xor     rcx, rbp; StackCookie
0x180024196  call    __security_check_cookie
0x18002419b  lea     rsp, [rbp+78h]
0x18002419f  pop     r15
0x1800241a1  pop     r14
0x1800241a3  pop     rdi
0x1800241a4  pop     rsi
0x1800241a5  pop     rbx
0x1800241a6  pop     rbp
0x1800241a7  retn
0x1800241a8  mov     ecx, eax
0x1800241aa  lea     eax, [rdi+rdi*2]
0x1800241ad  mov     ebx, edx
0x1800241af  cmp     ecx, eax
0x1800241b1  not     rbx
0x1800241b4  cmovnb  eax, ecx
0x1800241b7  and     rbx, r14
0x1800241ba  mov     esi, eax
0x1800241bc  lea     rax, [r15+rdi]
0x1800241c0  sub     rbx, rsi
0x1800241c3  cmp     rbx, rax
0x1800241c6  jb      short loc_18002418D
0x1800241c8  mov     r9d, 4; flProtect
0x1800241ce  mov     r8d, 1000h; flAllocationType
0x1800241d4  mov     edx, esi; dwSize
0x1800241d6  mov     rcx, rbx; lpAddress
0x1800241d9  call    cs:__imp_VirtualAlloc
0x1800241df  test    rax, rax
0x1800241e2  jz      short loc_18002418D
0x1800241e4  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x1800241e8  mov     r8d, 104h; flNewProtect
0x1800241ee  mov     edx, esi; dwSize
0x1800241f0  mov     rcx, rbx; lpAddress
0x1800241f3  call    cs:__imp_VirtualProtect
0x1800241f9  xor     ecx, ecx
0x1800241fb  test    eax, eax
0x1800241fd  setnz   cl
0x180024200  mov     eax, ecx
0x180024202  jmp     short loc_18002418F
```
