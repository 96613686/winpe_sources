# _resetstkoflw_static

- ea: `0x18002528c`
- end: `0x1800253bc`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025264`

## callees

- `0x18002528c`
- `0x18002b4a0`

## import_xrefs

- `KERNEL32!SetThreadStackGuarantee` at `0x180025319`
- `KERNEL32!SetThreadStackGuarantee` at `0x180025319`
- `KERNEL32!GetSystemInfo` at `0x18002530a`
- `KERNEL32!GetSystemInfo` at `0x18002530a`
- `KERNEL32!VirtualAlloc` at `0x180025391`
- `KERNEL32!VirtualAlloc` at `0x180025391`
- `KERNEL32!VirtualProtect` at `0x1800253ab`
- `KERNEL32!VirtualProtect` at `0x1800253ab`
- `KERNEL32!VirtualQuery` at `0x1800252f7`
- `KERNEL32!VirtualQuery` at `0x1800252f7`

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
0x18002528c  push    rbp
0x18002528e  push    rbx
0x18002528f  push    rsi
0x180025290  push    rdi
0x180025291  push    r14
0x180025293  push    r15
0x180025295  sub     rsp, 98h
0x18002529c  lea     rbp, [rsp+20h]
0x1800252a1  mov     rax, cs:__security_cookie
0x1800252a8  xor     rax, rbp
0x1800252ab  mov     [rbp+0A0h+var_38], rax
0x1800252af  mov     eax, [rsp+0C0h+var_C0]
0x1800252b2  xorps   xmm0, xmm0
0x1800252b5  xorps   xmm1, xmm1
0x1800252b8  mov     [rbp+0A0h+flOldProtect], 0
0x1800252bf  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x1800252c3  mov     [rbp+0A0h+StackSizeInBytes], 0
0x1800252ca  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x1800252ce  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x1800252d2  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x1800252d6  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x1800252da  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x1800252de  sub     rsp, 10h
0x1800252e2  lea     r14, [rsp+0D0h+Address]
0x1800252e7  mov     eax, [r14]
0x1800252ea  mov     r8d, 30h ; '0'; dwLength
0x1800252f0  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x1800252f4  mov     rcx, r14; lpAddress
0x1800252f7  call    cs:__imp_VirtualQuery
0x1800252fd  test    rax, rax
0x180025300  jz      short loc_180025345
0x180025302  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x180025306  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x18002530a  call    cs:__imp_GetSystemInfo
0x180025310  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x180025313  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x180025317  xor     ebx, ebx
0x180025319  call    cs:__imp_SetThreadStackGuarantee
0x18002531f  cmp     eax, 1
0x180025322  jnz     short loc_18002532C
0x180025324  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x180025327  test    eax, eax
0x180025329  cmovnz  ebx, eax
0x18002532c  lea     edx, [rdi-1]
0x18002532f  lea     ecx, [rdx+rbx]
0x180025332  cmp     ecx, ebx
0x180025334  jb      short loc_180025345
0x180025336  mov     eax, edx
0x180025338  not     eax
0x18002533a  and     eax, ecx
0x18002533c  jz      short loc_180025360
0x18002533e  lea     ecx, [rax+rdi]
0x180025341  cmp     ecx, eax
0x180025343  jnb     short loc_180025362
0x180025345  xor     eax, eax
0x180025347  mov     rcx, [rbp+0A0h+var_38]
0x18002534b  xor     rcx, rbp; StackCookie
0x18002534e  call    __security_check_cookie
0x180025353  lea     rsp, [rbp+78h]
0x180025357  pop     r15
0x180025359  pop     r14
0x18002535b  pop     rdi
0x18002535c  pop     rsi
0x18002535d  pop     rbx
0x18002535e  pop     rbp
0x18002535f  retn
0x180025360  mov     ecx, eax
0x180025362  lea     eax, [rdi+rdi*2]
0x180025365  mov     ebx, edx
0x180025367  cmp     ecx, eax
0x180025369  not     rbx
0x18002536c  cmovnb  eax, ecx
0x18002536f  and     rbx, r14
0x180025372  mov     esi, eax
0x180025374  lea     rax, [r15+rdi]
0x180025378  sub     rbx, rsi
0x18002537b  cmp     rbx, rax
0x18002537e  jb      short loc_180025345
0x180025380  mov     r9d, 4; flProtect
0x180025386  mov     r8d, 1000h; flAllocationType
0x18002538c  mov     edx, esi; dwSize
0x18002538e  mov     rcx, rbx; lpAddress
0x180025391  call    cs:__imp_VirtualAlloc
0x180025397  test    rax, rax
0x18002539a  jz      short loc_180025345
0x18002539c  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x1800253a0  mov     r8d, 104h; flNewProtect
0x1800253a6  mov     edx, esi; dwSize
0x1800253a8  mov     rcx, rbx; lpAddress
0x1800253ab  call    cs:__imp_VirtualProtect
0x1800253b1  xor     ecx, ecx
0x1800253b3  test    eax, eax
0x1800253b5  setnz   cl
0x1800253b8  mov     eax, ecx
0x1800253ba  jmp     short loc_180025347
```
