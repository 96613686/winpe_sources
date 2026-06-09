# _resetstkoflw

- ea: `0x180006250`
- end: `0x180006380`
- name: `_resetstkoflw`
- size: `304`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005968`

## callees

- `0x180006250`
- `0x180127dc0`

## import_xrefs

- `KERNEL32!SetThreadStackGuarantee` at `0x1800062dd`
- `KERNEL32!SetThreadStackGuarantee` at `0x1800062dd`
- `KERNEL32!GetSystemInfo` at `0x1800062ce`
- `KERNEL32!GetSystemInfo` at `0x1800062ce`
- `KERNEL32!VirtualAlloc` at `0x180006355`
- `KERNEL32!VirtualAlloc` at `0x180006355`
- `KERNEL32!VirtualProtect` at `0x18000636f`
- `KERNEL32!VirtualProtect` at `0x18000636f`
- `KERNEL32!VirtualQuery` at `0x1800062bb`
- `KERNEL32!VirtualQuery` at `0x1800062bb`

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
0x180006250  push    rbp
0x180006252  push    rbx
0x180006253  push    rsi
0x180006254  push    rdi
0x180006255  push    r14
0x180006257  push    r15
0x180006259  sub     rsp, 98h
0x180006260  lea     rbp, [rsp+20h]
0x180006265  mov     rax, cs:__security_cookie
0x18000626c  xor     rax, rbp
0x18000626f  mov     [rbp+0A0h+var_38], rax
0x180006273  mov     eax, [rsp+0C0h+var_C0]
0x180006276  xorps   xmm0, xmm0
0x180006279  xorps   xmm1, xmm1
0x18000627c  mov     [rbp+0A0h+flOldProtect], 0
0x180006283  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x180006287  mov     [rbp+0A0h+StackSizeInBytes], 0
0x18000628e  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x180006292  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x180006296  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x18000629a  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x18000629e  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x1800062a2  sub     rsp, 10h
0x1800062a6  lea     r14, [rsp+0D0h+Address]
0x1800062ab  mov     eax, [r14]
0x1800062ae  mov     r8d, 30h ; '0'; dwLength
0x1800062b4  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x1800062b8  mov     rcx, r14; lpAddress
0x1800062bb  call    cs:__imp_VirtualQuery
0x1800062c1  test    rax, rax
0x1800062c4  jz      short loc_180006309
0x1800062c6  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x1800062ca  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x1800062ce  call    cs:__imp_GetSystemInfo
0x1800062d4  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x1800062d7  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x1800062db  xor     ebx, ebx
0x1800062dd  call    cs:__imp_SetThreadStackGuarantee
0x1800062e3  cmp     eax, 1
0x1800062e6  jnz     short loc_1800062F0
0x1800062e8  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x1800062eb  test    eax, eax
0x1800062ed  cmovnz  ebx, eax
0x1800062f0  lea     edx, [rdi-1]
0x1800062f3  lea     ecx, [rdx+rbx]
0x1800062f6  cmp     ecx, ebx
0x1800062f8  jb      short loc_180006309
0x1800062fa  mov     eax, edx
0x1800062fc  not     eax
0x1800062fe  and     eax, ecx
0x180006300  jz      short loc_180006324
0x180006302  lea     ecx, [rax+rdi]
0x180006305  cmp     ecx, eax
0x180006307  jnb     short loc_180006326
0x180006309  xor     eax, eax
0x18000630b  mov     rcx, [rbp+0A0h+var_38]
0x18000630f  xor     rcx, rbp; StackCookie
0x180006312  call    __security_check_cookie
0x180006317  lea     rsp, [rbp+78h]
0x18000631b  pop     r15
0x18000631d  pop     r14
0x18000631f  pop     rdi
0x180006320  pop     rsi
0x180006321  pop     rbx
0x180006322  pop     rbp
0x180006323  retn
0x180006324  mov     ecx, eax
0x180006326  lea     eax, [rdi+rdi*2]
0x180006329  mov     ebx, edx
0x18000632b  cmp     ecx, eax
0x18000632d  not     rbx
0x180006330  cmovnb  eax, ecx
0x180006333  and     rbx, r14
0x180006336  mov     esi, eax
0x180006338  lea     rax, [r15+rdi]
0x18000633c  sub     rbx, rsi
0x18000633f  cmp     rbx, rax
0x180006342  jb      short loc_180006309
0x180006344  mov     r9d, 4; flProtect
0x18000634a  mov     r8d, 1000h; flAllocationType
0x180006350  mov     edx, esi; dwSize
0x180006352  mov     rcx, rbx; lpAddress
0x180006355  call    cs:__imp_VirtualAlloc
0x18000635b  test    rax, rax
0x18000635e  jz      short loc_180006309
0x180006360  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x180006364  mov     r8d, 104h; flNewProtect
0x18000636a  mov     edx, esi; dwSize
0x18000636c  mov     rcx, rbx; lpAddress
0x18000636f  call    cs:__imp_VirtualProtect
0x180006375  xor     ecx, ecx
0x180006377  test    eax, eax
0x180006379  setnz   cl
0x18000637c  mov     eax, ecx
0x18000637e  jmp     short loc_18000630B
```
