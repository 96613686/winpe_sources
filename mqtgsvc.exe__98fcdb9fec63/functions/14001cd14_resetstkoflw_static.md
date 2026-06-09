# _resetstkoflw_static

- ea: `0x14001cd14`
- end: `0x14001ce44`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001ccec`

## callees

- `0x14001cd14`
- `0x14001cf00`

## import_xrefs

- `KERNEL32!VirtualQuery` at `0x14001cd7f`
- `KERNEL32!VirtualQuery` at `0x14001cd7f`
- `KERNEL32!SetThreadStackGuarantee` at `0x14001cda1`
- `KERNEL32!SetThreadStackGuarantee` at `0x14001cda1`
- `KERNEL32!VirtualAlloc` at `0x14001ce19`
- `KERNEL32!VirtualAlloc` at `0x14001ce19`
- `KERNEL32!VirtualProtect` at `0x14001ce33`
- `KERNEL32!VirtualProtect` at `0x14001ce33`
- `KERNEL32!GetSystemInfo` at `0x14001cd92`
- `KERNEL32!GetSystemInfo` at `0x14001cd92`

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
0x14001cd14  push    rbp
0x14001cd16  push    rbx
0x14001cd17  push    rsi
0x14001cd18  push    rdi
0x14001cd19  push    r14
0x14001cd1b  push    r15
0x14001cd1d  sub     rsp, 98h
0x14001cd24  lea     rbp, [rsp+20h]
0x14001cd29  mov     rax, cs:__security_cookie
0x14001cd30  xor     rax, rbp
0x14001cd33  mov     [rbp+0A0h+var_38], rax
0x14001cd37  mov     eax, [rsp+0C0h+var_C0]
0x14001cd3a  xorps   xmm0, xmm0
0x14001cd3d  xorps   xmm1, xmm1
0x14001cd40  mov     [rbp+0A0h+flOldProtect], 0
0x14001cd47  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x14001cd4b  mov     [rbp+0A0h+StackSizeInBytes], 0
0x14001cd52  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x14001cd56  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x14001cd5a  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x14001cd5e  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x14001cd62  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x14001cd66  sub     rsp, 10h
0x14001cd6a  lea     r14, [rsp+0D0h+Address]
0x14001cd6f  mov     eax, [r14]
0x14001cd72  mov     r8d, 30h ; '0'; dwLength
0x14001cd78  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x14001cd7c  mov     rcx, r14; lpAddress
0x14001cd7f  call    cs:__imp_VirtualQuery
0x14001cd85  test    rax, rax
0x14001cd88  jz      short loc_14001CDCD
0x14001cd8a  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x14001cd8e  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x14001cd92  call    cs:__imp_GetSystemInfo
0x14001cd98  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x14001cd9b  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x14001cd9f  xor     ebx, ebx
0x14001cda1  call    cs:__imp_SetThreadStackGuarantee
0x14001cda7  cmp     eax, 1
0x14001cdaa  jnz     short loc_14001CDB4
0x14001cdac  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x14001cdaf  test    eax, eax
0x14001cdb1  cmovnz  ebx, eax
0x14001cdb4  lea     edx, [rdi-1]
0x14001cdb7  lea     ecx, [rdx+rbx]
0x14001cdba  cmp     ecx, ebx
0x14001cdbc  jb      short loc_14001CDCD
0x14001cdbe  mov     eax, edx
0x14001cdc0  not     eax
0x14001cdc2  and     eax, ecx
0x14001cdc4  jz      short loc_14001CDE8
0x14001cdc6  lea     ecx, [rax+rdi]
0x14001cdc9  cmp     ecx, eax
0x14001cdcb  jnb     short loc_14001CDEA
0x14001cdcd  xor     eax, eax
0x14001cdcf  mov     rcx, [rbp+0A0h+var_38]
0x14001cdd3  xor     rcx, rbp; StackCookie
0x14001cdd6  call    __security_check_cookie
0x14001cddb  lea     rsp, [rbp+78h]
0x14001cddf  pop     r15
0x14001cde1  pop     r14
0x14001cde3  pop     rdi
0x14001cde4  pop     rsi
0x14001cde5  pop     rbx
0x14001cde6  pop     rbp
0x14001cde7  retn
0x14001cde8  mov     ecx, eax
0x14001cdea  lea     eax, [rdi+rdi*2]
0x14001cded  mov     ebx, edx
0x14001cdef  cmp     ecx, eax
0x14001cdf1  not     rbx
0x14001cdf4  cmovnb  eax, ecx
0x14001cdf7  and     rbx, r14
0x14001cdfa  mov     esi, eax
0x14001cdfc  lea     rax, [r15+rdi]
0x14001ce00  sub     rbx, rsi
0x14001ce03  cmp     rbx, rax
0x14001ce06  jb      short loc_14001CDCD
0x14001ce08  mov     r9d, 4; flProtect
0x14001ce0e  mov     r8d, 1000h; flAllocationType
0x14001ce14  mov     edx, esi; dwSize
0x14001ce16  mov     rcx, rbx; lpAddress
0x14001ce19  call    cs:__imp_VirtualAlloc
0x14001ce1f  test    rax, rax
0x14001ce22  jz      short loc_14001CDCD
0x14001ce24  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x14001ce28  mov     r8d, 104h; flNewProtect
0x14001ce2e  mov     edx, esi; dwSize
0x14001ce30  mov     rcx, rbx; lpAddress
0x14001ce33  call    cs:__imp_VirtualProtect
0x14001ce39  xor     ecx, ecx
0x14001ce3b  test    eax, eax
0x14001ce3d  setnz   cl
0x14001ce40  mov     eax, ecx
0x14001ce42  jmp     short loc_14001CDCF
```
