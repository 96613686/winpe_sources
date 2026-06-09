# _resetstkoflw_static

- ea: `0x18001e150`
- end: `0x18001e280`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e128`

## callees

- `0x18001e150`
- `0x18001e380`

## import_xrefs

- `KERNEL32!VirtualQuery` at `0x18001e1bb`
- `KERNEL32!VirtualQuery` at `0x18001e1bb`
- `KERNEL32!SetThreadStackGuarantee` at `0x18001e1dd`
- `KERNEL32!SetThreadStackGuarantee` at `0x18001e1dd`
- `KERNEL32!GetSystemInfo` at `0x18001e1ce`
- `KERNEL32!GetSystemInfo` at `0x18001e1ce`
- `KERNEL32!VirtualAlloc` at `0x18001e255`
- `KERNEL32!VirtualAlloc` at `0x18001e255`
- `KERNEL32!VirtualProtect` at `0x18001e26f`
- `KERNEL32!VirtualProtect` at `0x18001e26f`

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
0x18001e150  push    rbp
0x18001e152  push    rbx
0x18001e153  push    rsi
0x18001e154  push    rdi
0x18001e155  push    r14
0x18001e157  push    r15
0x18001e159  sub     rsp, 98h
0x18001e160  lea     rbp, [rsp+20h]
0x18001e165  mov     rax, cs:__security_cookie
0x18001e16c  xor     rax, rbp
0x18001e16f  mov     [rbp+0A0h+var_38], rax
0x18001e173  mov     eax, [rsp+0C0h+var_C0]
0x18001e176  xorps   xmm0, xmm0
0x18001e179  xorps   xmm1, xmm1
0x18001e17c  mov     [rbp+0A0h+flOldProtect], 0
0x18001e183  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x18001e187  mov     [rbp+0A0h+StackSizeInBytes], 0
0x18001e18e  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x18001e192  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x18001e196  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x18001e19a  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x18001e19e  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x18001e1a2  sub     rsp, 10h
0x18001e1a6  lea     r14, [rsp+0D0h+Address]
0x18001e1ab  mov     eax, [r14]
0x18001e1ae  mov     r8d, 30h ; '0'; dwLength
0x18001e1b4  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x18001e1b8  mov     rcx, r14; lpAddress
0x18001e1bb  call    cs:__imp_VirtualQuery
0x18001e1c1  test    rax, rax
0x18001e1c4  jz      short loc_18001E209
0x18001e1c6  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x18001e1ca  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x18001e1ce  call    cs:__imp_GetSystemInfo
0x18001e1d4  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x18001e1d7  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x18001e1db  xor     ebx, ebx
0x18001e1dd  call    cs:__imp_SetThreadStackGuarantee
0x18001e1e3  cmp     eax, 1
0x18001e1e6  jnz     short loc_18001E1F0
0x18001e1e8  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x18001e1eb  test    eax, eax
0x18001e1ed  cmovnz  ebx, eax
0x18001e1f0  lea     edx, [rdi-1]
0x18001e1f3  lea     ecx, [rdx+rbx]
0x18001e1f6  cmp     ecx, ebx
0x18001e1f8  jb      short loc_18001E209
0x18001e1fa  mov     eax, edx
0x18001e1fc  not     eax
0x18001e1fe  and     eax, ecx
0x18001e200  jz      short loc_18001E224
0x18001e202  lea     ecx, [rax+rdi]
0x18001e205  cmp     ecx, eax
0x18001e207  jnb     short loc_18001E226
0x18001e209  xor     eax, eax
0x18001e20b  mov     rcx, [rbp+0A0h+var_38]
0x18001e20f  xor     rcx, rbp; StackCookie
0x18001e212  call    __security_check_cookie
0x18001e217  lea     rsp, [rbp+78h]
0x18001e21b  pop     r15
0x18001e21d  pop     r14
0x18001e21f  pop     rdi
0x18001e220  pop     rsi
0x18001e221  pop     rbx
0x18001e222  pop     rbp
0x18001e223  retn
0x18001e224  mov     ecx, eax
0x18001e226  lea     eax, [rdi+rdi*2]
0x18001e229  mov     ebx, edx
0x18001e22b  cmp     ecx, eax
0x18001e22d  not     rbx
0x18001e230  cmovnb  eax, ecx
0x18001e233  and     rbx, r14
0x18001e236  mov     esi, eax
0x18001e238  lea     rax, [r15+rdi]
0x18001e23c  sub     rbx, rsi
0x18001e23f  cmp     rbx, rax
0x18001e242  jb      short loc_18001E209
0x18001e244  mov     r9d, 4; flProtect
0x18001e24a  mov     r8d, 1000h; flAllocationType
0x18001e250  mov     edx, esi; dwSize
0x18001e252  mov     rcx, rbx; lpAddress
0x18001e255  call    cs:__imp_VirtualAlloc
0x18001e25b  test    rax, rax
0x18001e25e  jz      short loc_18001E209
0x18001e260  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x18001e264  mov     r8d, 104h; flNewProtect
0x18001e26a  mov     edx, esi; dwSize
0x18001e26c  mov     rcx, rbx; lpAddress
0x18001e26f  call    cs:__imp_VirtualProtect
0x18001e275  xor     ecx, ecx
0x18001e277  test    eax, eax
0x18001e279  setnz   cl
0x18001e27c  mov     eax, ecx
0x18001e27e  jmp     short loc_18001E20B
```
