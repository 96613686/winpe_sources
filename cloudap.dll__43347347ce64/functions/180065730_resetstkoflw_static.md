# _resetstkoflw_static

- ea: `0x180065730`
- end: `0x180065860`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a810`

## callees

- `0x180042410`
- `0x180065730`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x1800657bd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x1800657bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800657ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800657ae`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18006579b`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18006579b`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180065835`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180065835`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18006584f`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18006584f`

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
0x180065730  push    rbp
0x180065732  push    rbx
0x180065733  push    rsi
0x180065734  push    rdi
0x180065735  push    r14
0x180065737  push    r15
0x180065739  sub     rsp, 98h
0x180065740  lea     rbp, [rsp+20h]
0x180065745  mov     rax, cs:__security_cookie
0x18006574c  xor     rax, rbp
0x18006574f  mov     [rbp+0A0h+var_38], rax
0x180065753  mov     eax, [rsp+0C0h+var_C0]
0x180065756  xorps   xmm0, xmm0
0x180065759  xorps   xmm1, xmm1
0x18006575c  mov     [rbp+0A0h+flOldProtect], 0
0x180065763  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x180065767  mov     [rbp+0A0h+StackSizeInBytes], 0
0x18006576e  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x180065772  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x180065776  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x18006577a  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x18006577e  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x180065782  sub     rsp, 10h
0x180065786  lea     r14, [rsp+0D0h+Address]
0x18006578b  mov     eax, [r14]
0x18006578e  mov     r8d, 30h ; '0'; dwLength
0x180065794  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x180065798  mov     rcx, r14; lpAddress
0x18006579b  call    cs:__imp_VirtualQuery
0x1800657a1  test    rax, rax
0x1800657a4  jz      short loc_1800657E9
0x1800657a6  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x1800657aa  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x1800657ae  call    cs:__imp_GetSystemInfo
0x1800657b4  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x1800657b7  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x1800657bb  xor     ebx, ebx
0x1800657bd  call    cs:__imp_SetThreadStackGuarantee
0x1800657c3  cmp     eax, 1
0x1800657c6  jnz     short loc_1800657D0
0x1800657c8  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x1800657cb  test    eax, eax
0x1800657cd  cmovnz  ebx, eax
0x1800657d0  lea     edx, [rdi-1]
0x1800657d3  lea     ecx, [rdx+rbx]
0x1800657d6  cmp     ecx, ebx
0x1800657d8  jb      short loc_1800657E9
0x1800657da  mov     eax, edx
0x1800657dc  not     eax
0x1800657de  and     eax, ecx
0x1800657e0  jz      short loc_180065804
0x1800657e2  lea     ecx, [rax+rdi]
0x1800657e5  cmp     ecx, eax
0x1800657e7  jnb     short loc_180065806
0x1800657e9  xor     eax, eax
0x1800657eb  mov     rcx, [rbp+0A0h+var_38]
0x1800657ef  xor     rcx, rbp; StackCookie
0x1800657f2  call    __security_check_cookie
0x1800657f7  lea     rsp, [rbp+78h]
0x1800657fb  pop     r15
0x1800657fd  pop     r14
0x1800657ff  pop     rdi
0x180065800  pop     rsi
0x180065801  pop     rbx
0x180065802  pop     rbp
0x180065803  retn
0x180065804  mov     ecx, eax
0x180065806  lea     eax, [rdi+rdi*2]
0x180065809  mov     ebx, edx
0x18006580b  cmp     ecx, eax
0x18006580d  not     rbx
0x180065810  cmovnb  eax, ecx
0x180065813  and     rbx, r14
0x180065816  mov     esi, eax
0x180065818  lea     rax, [r15+rdi]
0x18006581c  sub     rbx, rsi
0x18006581f  cmp     rbx, rax
0x180065822  jb      short loc_1800657E9
0x180065824  mov     r9d, 4; flProtect
0x18006582a  mov     r8d, 1000h; flAllocationType
0x180065830  mov     edx, esi; dwSize
0x180065832  mov     rcx, rbx; lpAddress
0x180065835  call    cs:__imp_VirtualAlloc
0x18006583b  test    rax, rax
0x18006583e  jz      short loc_1800657E9
0x180065840  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x180065844  mov     r8d, 104h; flNewProtect
0x18006584a  mov     edx, esi; dwSize
0x18006584c  mov     rcx, rbx; lpAddress
0x18006584f  call    cs:__imp_VirtualProtect
0x180065855  xor     ecx, ecx
0x180065857  test    eax, eax
0x180065859  setnz   cl
0x18006585c  mov     eax, ecx
0x18006585e  jmp     short loc_1800657EB
```
