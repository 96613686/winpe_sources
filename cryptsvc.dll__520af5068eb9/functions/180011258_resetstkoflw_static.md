# _resetstkoflw_static

- ea: `0x180011258`
- end: `0x180011388`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011230`

## callees

- `0x18000e2f0`
- `0x180011258`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x1800112e5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x1800112e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800112d6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800112d6`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001135d`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001135d`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180011377`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180011377`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x1800112c3`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x1800112c3`

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
0x180011258  push    rbp
0x18001125a  push    rbx
0x18001125b  push    rsi
0x18001125c  push    rdi
0x18001125d  push    r14
0x18001125f  push    r15
0x180011261  sub     rsp, 98h
0x180011268  lea     rbp, [rsp+20h]
0x18001126d  mov     rax, cs:__security_cookie
0x180011274  xor     rax, rbp
0x180011277  mov     [rbp+0A0h+var_38], rax
0x18001127b  mov     eax, [rsp+0C0h+var_C0]
0x18001127e  xorps   xmm0, xmm0
0x180011281  xorps   xmm1, xmm1
0x180011284  mov     [rbp+0A0h+flOldProtect], 0
0x18001128b  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x18001128f  mov     [rbp+0A0h+StackSizeInBytes], 0
0x180011296  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x18001129a  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x18001129e  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x1800112a2  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x1800112a6  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x1800112aa  sub     rsp, 10h
0x1800112ae  lea     r14, [rsp+0D0h+Address]
0x1800112b3  mov     eax, [r14]
0x1800112b6  mov     r8d, 30h ; '0'; dwLength
0x1800112bc  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x1800112c0  mov     rcx, r14; lpAddress
0x1800112c3  call    cs:__imp_VirtualQuery
0x1800112c9  test    rax, rax
0x1800112cc  jz      short loc_180011311
0x1800112ce  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x1800112d2  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x1800112d6  call    cs:__imp_GetSystemInfo
0x1800112dc  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x1800112df  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x1800112e3  xor     ebx, ebx
0x1800112e5  call    cs:__imp_SetThreadStackGuarantee
0x1800112eb  cmp     eax, 1
0x1800112ee  jnz     short loc_1800112F8
0x1800112f0  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x1800112f3  test    eax, eax
0x1800112f5  cmovnz  ebx, eax
0x1800112f8  lea     edx, [rdi-1]
0x1800112fb  lea     ecx, [rdx+rbx]
0x1800112fe  cmp     ecx, ebx
0x180011300  jb      short loc_180011311
0x180011302  mov     eax, edx
0x180011304  not     eax
0x180011306  and     eax, ecx
0x180011308  jz      short loc_18001132C
0x18001130a  lea     ecx, [rax+rdi]
0x18001130d  cmp     ecx, eax
0x18001130f  jnb     short loc_18001132E
0x180011311  xor     eax, eax
0x180011313  mov     rcx, [rbp+0A0h+var_38]
0x180011317  xor     rcx, rbp; StackCookie
0x18001131a  call    __security_check_cookie
0x18001131f  lea     rsp, [rbp+78h]
0x180011323  pop     r15
0x180011325  pop     r14
0x180011327  pop     rdi
0x180011328  pop     rsi
0x180011329  pop     rbx
0x18001132a  pop     rbp
0x18001132b  retn
0x18001132c  mov     ecx, eax
0x18001132e  lea     eax, [rdi+rdi*2]
0x180011331  mov     ebx, edx
0x180011333  cmp     ecx, eax
0x180011335  not     rbx
0x180011338  cmovnb  eax, ecx
0x18001133b  and     rbx, r14
0x18001133e  mov     esi, eax
0x180011340  lea     rax, [r15+rdi]
0x180011344  sub     rbx, rsi
0x180011347  cmp     rbx, rax
0x18001134a  jb      short loc_180011311
0x18001134c  mov     r9d, 4; flProtect
0x180011352  mov     r8d, 1000h; flAllocationType
0x180011358  mov     edx, esi; dwSize
0x18001135a  mov     rcx, rbx; lpAddress
0x18001135d  call    cs:__imp_VirtualAlloc
0x180011363  test    rax, rax
0x180011366  jz      short loc_180011311
0x180011368  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x18001136c  mov     r8d, 104h; flNewProtect
0x180011372  mov     edx, esi; dwSize
0x180011374  mov     rcx, rbx; lpAddress
0x180011377  call    cs:__imp_VirtualProtect
0x18001137d  xor     ecx, ecx
0x18001137f  test    eax, eax
0x180011381  setnz   cl
0x180011384  mov     eax, ecx
0x180011386  jmp     short loc_180011313
```
