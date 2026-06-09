# _resetstkoflw_static

- ea: `0x180060e04`
- end: `0x180060f56`
- name: `_resetstkoflw_static`
- size: `338`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800086d0`

## callees

- `0x180060e04`
- `0x180062310`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x180060e9d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x180060e9d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180060e88`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180060e88`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180060e6f`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180060e6f`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180060f3c`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180060f3c`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180060f1c`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180060f1c`

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
0x180060e04  push    rbp
0x180060e06  push    rbx
0x180060e07  push    rsi
0x180060e08  push    rdi
0x180060e09  push    r14
0x180060e0b  push    r15
0x180060e0d  sub     rsp, 98h
0x180060e14  lea     rbp, [rsp+20h]
0x180060e19  mov     rax, cs:__security_cookie
0x180060e20  xor     rax, rbp
0x180060e23  mov     [rbp+0A0h+var_38], rax
0x180060e27  mov     eax, [rsp+0C0h+var_C0]
0x180060e2a  xorps   xmm0, xmm0
0x180060e2d  xorps   xmm1, xmm1
0x180060e30  mov     [rbp+0A0h+flOldProtect], 0
0x180060e37  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x180060e3b  mov     [rbp+0A0h+StackSizeInBytes], 0
0x180060e42  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x180060e46  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x180060e4a  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x180060e4e  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x180060e52  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x180060e56  sub     rsp, 10h
0x180060e5a  lea     r14, [rsp+0D0h+Address]
0x180060e5f  mov     eax, [r14]
0x180060e62  mov     r8d, 30h ; '0'; dwLength
0x180060e68  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x180060e6c  mov     rcx, r14; lpAddress
0x180060e6f  call    cs:__imp_VirtualQuery
0x180060e76  nop     dword ptr [rax+rax+00h]
0x180060e7b  test    rax, rax
0x180060e7e  jz      short loc_180060ECF
0x180060e80  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x180060e84  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x180060e88  call    cs:__imp_GetSystemInfo
0x180060e8f  nop     dword ptr [rax+rax+00h]
0x180060e94  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x180060e97  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x180060e9b  xor     ebx, ebx
0x180060e9d  call    cs:__imp_SetThreadStackGuarantee
0x180060ea4  nop     dword ptr [rax+rax+00h]
0x180060ea9  cmp     eax, 1
0x180060eac  jnz     short loc_180060EB6
0x180060eae  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x180060eb1  test    eax, eax
0x180060eb3  cmovnz  ebx, eax
0x180060eb6  lea     edx, [rdi-1]
0x180060eb9  lea     ecx, [rdx+rbx]
0x180060ebc  cmp     ecx, ebx
0x180060ebe  jb      short loc_180060ECF
0x180060ec0  mov     eax, edx
0x180060ec2  not     eax
0x180060ec4  and     eax, ecx
0x180060ec6  jz      short loc_180060EEB
0x180060ec8  lea     ecx, [rax+rdi]
0x180060ecb  cmp     ecx, eax
0x180060ecd  jnb     short loc_180060EED
0x180060ecf  xor     eax, eax
0x180060ed1  mov     rcx, [rbp+0A0h+var_38]
0x180060ed5  xor     rcx, rbp; StackCookie
0x180060ed8  call    __security_check_cookie
0x180060edd  lea     rsp, [rbp+78h]
0x180060ee1  pop     r15
0x180060ee3  pop     r14
0x180060ee5  pop     rdi
0x180060ee6  pop     rsi
0x180060ee7  pop     rbx
0x180060ee8  pop     rbp
0x180060ee9  retn
0x180060eeb  mov     ecx, eax
0x180060eed  lea     eax, [rdi+rdi*2]
0x180060ef0  mov     ebx, edx
0x180060ef2  cmp     ecx, eax
0x180060ef4  not     rbx
0x180060ef7  cmovnb  eax, ecx
0x180060efa  and     rbx, r14
0x180060efd  mov     esi, eax
0x180060eff  lea     rax, [r15+rdi]
0x180060f03  sub     rbx, rsi
0x180060f06  cmp     rbx, rax
0x180060f09  jb      short loc_180060ECF
0x180060f0b  mov     r9d, 4; flProtect
0x180060f11  mov     r8d, 1000h; flAllocationType
0x180060f17  mov     edx, esi; dwSize
0x180060f19  mov     rcx, rbx; lpAddress
0x180060f1c  call    cs:__imp_VirtualAlloc
0x180060f23  nop     dword ptr [rax+rax+00h]
0x180060f28  test    rax, rax
0x180060f2b  jz      short loc_180060ECF
0x180060f2d  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x180060f31  mov     r8d, 104h; flNewProtect
0x180060f37  mov     edx, esi; dwSize
0x180060f39  mov     rcx, rbx; lpAddress
0x180060f3c  call    cs:__imp_VirtualProtect
0x180060f43  nop     dword ptr [rax+rax+00h]
0x180060f48  xor     ecx, ecx
0x180060f4a  test    eax, eax
0x180060f4c  setnz   cl
0x180060f4f  mov     eax, ecx
0x180060f51  jmp     loc_180060ED1
```
