# _resetstkoflw_static

- ea: `0x180017aac`
- end: `0x180017bdc`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180017a84`

## callees

- `0x180017aac`
- `0x1800181e0`

## import_xrefs

- `KERNEL32!VirtualQuery` at `0x180017b17`
- `KERNEL32!VirtualQuery` at `0x180017b17`
- `KERNEL32!VirtualAlloc` at `0x180017bb1`
- `KERNEL32!VirtualAlloc` at `0x180017bb1`
- `KERNEL32!GetSystemInfo` at `0x180017b2a`
- `KERNEL32!GetSystemInfo` at `0x180017b2a`
- `KERNEL32!VirtualProtect` at `0x180017bcb`
- `KERNEL32!VirtualProtect` at `0x180017bcb`
- `KERNEL32!SetThreadStackGuarantee` at `0x180017b39`
- `KERNEL32!SetThreadStackGuarantee` at `0x180017b39`

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
0x180017aac  push    rbp
0x180017aae  push    rbx
0x180017aaf  push    rsi
0x180017ab0  push    rdi
0x180017ab1  push    r14
0x180017ab3  push    r15
0x180017ab5  sub     rsp, 98h
0x180017abc  lea     rbp, [rsp+20h]
0x180017ac1  mov     rax, cs:__security_cookie
0x180017ac8  xor     rax, rbp
0x180017acb  mov     [rbp+0A0h+var_38], rax
0x180017acf  mov     eax, [rsp+0C0h+var_C0]
0x180017ad2  xorps   xmm0, xmm0
0x180017ad5  xorps   xmm1, xmm1
0x180017ad8  mov     [rbp+0A0h+flOldProtect], 0
0x180017adf  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x180017ae3  mov     [rbp+0A0h+StackSizeInBytes], 0
0x180017aea  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x180017aee  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x180017af2  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x180017af6  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x180017afa  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x180017afe  sub     rsp, 10h
0x180017b02  lea     r14, [rsp+0D0h+Address]
0x180017b07  mov     eax, [r14]
0x180017b0a  mov     r8d, 30h ; '0'; dwLength
0x180017b10  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x180017b14  mov     rcx, r14; lpAddress
0x180017b17  call    cs:__imp_VirtualQuery
0x180017b1d  test    rax, rax
0x180017b20  jz      short loc_180017B65
0x180017b22  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x180017b26  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x180017b2a  call    cs:__imp_GetSystemInfo
0x180017b30  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x180017b33  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x180017b37  xor     ebx, ebx
0x180017b39  call    cs:__imp_SetThreadStackGuarantee
0x180017b3f  cmp     eax, 1
0x180017b42  jnz     short loc_180017B4C
0x180017b44  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x180017b47  test    eax, eax
0x180017b49  cmovnz  ebx, eax
0x180017b4c  lea     edx, [rdi-1]
0x180017b4f  lea     ecx, [rdx+rbx]
0x180017b52  cmp     ecx, ebx
0x180017b54  jb      short loc_180017B65
0x180017b56  mov     eax, edx
0x180017b58  not     eax
0x180017b5a  and     eax, ecx
0x180017b5c  jz      short loc_180017B80
0x180017b5e  lea     ecx, [rax+rdi]
0x180017b61  cmp     ecx, eax
0x180017b63  jnb     short loc_180017B82
0x180017b65  xor     eax, eax
0x180017b67  mov     rcx, [rbp+0A0h+var_38]
0x180017b6b  xor     rcx, rbp; StackCookie
0x180017b6e  call    __security_check_cookie
0x180017b73  lea     rsp, [rbp+78h]
0x180017b77  pop     r15
0x180017b79  pop     r14
0x180017b7b  pop     rdi
0x180017b7c  pop     rsi
0x180017b7d  pop     rbx
0x180017b7e  pop     rbp
0x180017b7f  retn
0x180017b80  mov     ecx, eax
0x180017b82  lea     eax, [rdi+rdi*2]
0x180017b85  mov     ebx, edx
0x180017b87  cmp     ecx, eax
0x180017b89  not     rbx
0x180017b8c  cmovnb  eax, ecx
0x180017b8f  and     rbx, r14
0x180017b92  mov     esi, eax
0x180017b94  lea     rax, [r15+rdi]
0x180017b98  sub     rbx, rsi
0x180017b9b  cmp     rbx, rax
0x180017b9e  jb      short loc_180017B65
0x180017ba0  mov     r9d, 4; flProtect
0x180017ba6  mov     r8d, 1000h; flAllocationType
0x180017bac  mov     edx, esi; dwSize
0x180017bae  mov     rcx, rbx; lpAddress
0x180017bb1  call    cs:__imp_VirtualAlloc
0x180017bb7  test    rax, rax
0x180017bba  jz      short loc_180017B65
0x180017bbc  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x180017bc0  mov     r8d, 104h; flNewProtect
0x180017bc6  mov     edx, esi; dwSize
0x180017bc8  mov     rcx, rbx; lpAddress
0x180017bcb  call    cs:__imp_VirtualProtect
0x180017bd1  xor     ecx, ecx
0x180017bd3  test    eax, eax
0x180017bd5  setnz   cl
0x180017bd8  mov     eax, ecx
0x180017bda  jmp     short loc_180017B67
```
