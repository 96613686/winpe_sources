# _resetstkoflw_static

- ea: `0x18003731c`
- end: `0x18003744c`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800372f4`

## callees

- `0x180001670`
- `0x18003731c`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x18003739a`
- `KERNEL32!GetSystemInfo` at `0x18003739a`
- `KERNEL32!VirtualAlloc` at `0x180037421`
- `KERNEL32!VirtualAlloc` at `0x180037421`
- `KERNEL32!VirtualProtect` at `0x18003743b`
- `KERNEL32!VirtualProtect` at `0x18003743b`
- `KERNEL32!SetThreadStackGuarantee` at `0x1800373a9`
- `KERNEL32!SetThreadStackGuarantee` at `0x1800373a9`
- `KERNEL32!VirtualQuery` at `0x180037387`
- `KERNEL32!VirtualQuery` at `0x180037387`

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
0x18003731c  push    rbp
0x18003731e  push    rbx
0x18003731f  push    rsi
0x180037320  push    rdi
0x180037321  push    r14
0x180037323  push    r15
0x180037325  sub     rsp, 98h
0x18003732c  lea     rbp, [rsp+20h]
0x180037331  mov     rax, cs:__security_cookie
0x180037338  xor     rax, rbp
0x18003733b  mov     [rbp+0A0h+var_38], rax
0x18003733f  mov     eax, [rsp+0C0h+var_C0]
0x180037342  xorps   xmm0, xmm0
0x180037345  xorps   xmm1, xmm1
0x180037348  mov     [rbp+0A0h+flOldProtect], 0
0x18003734f  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x180037353  mov     [rbp+0A0h+StackSizeInBytes], 0
0x18003735a  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x18003735e  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x180037362  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x180037366  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x18003736a  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x18003736e  sub     rsp, 10h
0x180037372  lea     r14, [rsp+0D0h+Address]
0x180037377  mov     eax, [r14]
0x18003737a  mov     r8d, 30h ; '0'; dwLength
0x180037380  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x180037384  mov     rcx, r14; lpAddress
0x180037387  call    cs:__imp_VirtualQuery
0x18003738d  test    rax, rax
0x180037390  jz      short loc_1800373D5
0x180037392  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x180037396  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x18003739a  call    cs:__imp_GetSystemInfo
0x1800373a0  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x1800373a3  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x1800373a7  xor     ebx, ebx
0x1800373a9  call    cs:__imp_SetThreadStackGuarantee
0x1800373af  cmp     eax, 1
0x1800373b2  jnz     short loc_1800373BC
0x1800373b4  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x1800373b7  test    eax, eax
0x1800373b9  cmovnz  ebx, eax
0x1800373bc  lea     edx, [rdi-1]
0x1800373bf  lea     ecx, [rdx+rbx]
0x1800373c2  cmp     ecx, ebx
0x1800373c4  jb      short loc_1800373D5
0x1800373c6  mov     eax, edx
0x1800373c8  not     eax
0x1800373ca  and     eax, ecx
0x1800373cc  jz      short loc_1800373F0
0x1800373ce  lea     ecx, [rax+rdi]
0x1800373d1  cmp     ecx, eax
0x1800373d3  jnb     short loc_1800373F2
0x1800373d5  xor     eax, eax
0x1800373d7  mov     rcx, [rbp+0A0h+var_38]
0x1800373db  xor     rcx, rbp; StackCookie
0x1800373de  call    __security_check_cookie
0x1800373e3  lea     rsp, [rbp+78h]
0x1800373e7  pop     r15
0x1800373e9  pop     r14
0x1800373eb  pop     rdi
0x1800373ec  pop     rsi
0x1800373ed  pop     rbx
0x1800373ee  pop     rbp
0x1800373ef  retn
0x1800373f0  mov     ecx, eax
0x1800373f2  lea     eax, [rdi+rdi*2]
0x1800373f5  mov     ebx, edx
0x1800373f7  cmp     ecx, eax
0x1800373f9  not     rbx
0x1800373fc  cmovnb  eax, ecx
0x1800373ff  and     rbx, r14
0x180037402  mov     esi, eax
0x180037404  lea     rax, [r15+rdi]
0x180037408  sub     rbx, rsi
0x18003740b  cmp     rbx, rax
0x18003740e  jb      short loc_1800373D5
0x180037410  mov     r9d, 4; flProtect
0x180037416  mov     r8d, 1000h; flAllocationType
0x18003741c  mov     edx, esi; dwSize
0x18003741e  mov     rcx, rbx; lpAddress
0x180037421  call    cs:__imp_VirtualAlloc
0x180037427  test    rax, rax
0x18003742a  jz      short loc_1800373D5
0x18003742c  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x180037430  mov     r8d, 104h; flNewProtect
0x180037436  mov     edx, esi; dwSize
0x180037438  mov     rcx, rbx; lpAddress
0x18003743b  call    cs:__imp_VirtualProtect
0x180037441  xor     ecx, ecx
0x180037443  test    eax, eax
0x180037445  setnz   cl
0x180037448  mov     eax, ecx
0x18003744a  jmp     short loc_1800373D7
```
