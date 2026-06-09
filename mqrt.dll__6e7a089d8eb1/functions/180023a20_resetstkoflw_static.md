# _resetstkoflw_static

- ea: `0x180023a20`
- end: `0x180023b50`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800239f8`

## callees

- `0x180023a20`
- `0x180023ca0`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x180023a9e`
- `KERNEL32!GetSystemInfo` at `0x180023a9e`
- `KERNEL32!SetThreadStackGuarantee` at `0x180023aad`
- `KERNEL32!SetThreadStackGuarantee` at `0x180023aad`
- `KERNEL32!VirtualQuery` at `0x180023a8b`
- `KERNEL32!VirtualQuery` at `0x180023a8b`
- `KERNEL32!VirtualAlloc` at `0x180023b25`
- `KERNEL32!VirtualAlloc` at `0x180023b25`
- `KERNEL32!VirtualProtect` at `0x180023b3f`
- `KERNEL32!VirtualProtect` at `0x180023b3f`

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
0x180023a20  push    rbp
0x180023a22  push    rbx
0x180023a23  push    rsi
0x180023a24  push    rdi
0x180023a25  push    r14
0x180023a27  push    r15
0x180023a29  sub     rsp, 98h
0x180023a30  lea     rbp, [rsp+20h]
0x180023a35  mov     rax, cs:__security_cookie
0x180023a3c  xor     rax, rbp
0x180023a3f  mov     [rbp+0A0h+var_38], rax
0x180023a43  mov     eax, [rsp+0C0h+var_C0]
0x180023a46  xorps   xmm0, xmm0
0x180023a49  xorps   xmm1, xmm1
0x180023a4c  mov     [rbp+0A0h+flOldProtect], 0
0x180023a53  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x180023a57  mov     [rbp+0A0h+StackSizeInBytes], 0
0x180023a5e  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x180023a62  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x180023a66  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x180023a6a  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x180023a6e  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x180023a72  sub     rsp, 10h
0x180023a76  lea     r14, [rsp+0D0h+Address]
0x180023a7b  mov     eax, [r14]
0x180023a7e  mov     r8d, 30h ; '0'; dwLength
0x180023a84  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x180023a88  mov     rcx, r14; lpAddress
0x180023a8b  call    cs:__imp_VirtualQuery
0x180023a91  test    rax, rax
0x180023a94  jz      short loc_180023AD9
0x180023a96  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x180023a9a  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x180023a9e  call    cs:__imp_GetSystemInfo
0x180023aa4  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x180023aa7  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x180023aab  xor     ebx, ebx
0x180023aad  call    cs:__imp_SetThreadStackGuarantee
0x180023ab3  cmp     eax, 1
0x180023ab6  jnz     short loc_180023AC0
0x180023ab8  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x180023abb  test    eax, eax
0x180023abd  cmovnz  ebx, eax
0x180023ac0  lea     edx, [rdi-1]
0x180023ac3  lea     ecx, [rdx+rbx]
0x180023ac6  cmp     ecx, ebx
0x180023ac8  jb      short loc_180023AD9
0x180023aca  mov     eax, edx
0x180023acc  not     eax
0x180023ace  and     eax, ecx
0x180023ad0  jz      short loc_180023AF4
0x180023ad2  lea     ecx, [rax+rdi]
0x180023ad5  cmp     ecx, eax
0x180023ad7  jnb     short loc_180023AF6
0x180023ad9  xor     eax, eax
0x180023adb  mov     rcx, [rbp+0A0h+var_38]
0x180023adf  xor     rcx, rbp; StackCookie
0x180023ae2  call    __security_check_cookie
0x180023ae7  lea     rsp, [rbp+78h]
0x180023aeb  pop     r15
0x180023aed  pop     r14
0x180023aef  pop     rdi
0x180023af0  pop     rsi
0x180023af1  pop     rbx
0x180023af2  pop     rbp
0x180023af3  retn
0x180023af4  mov     ecx, eax
0x180023af6  lea     eax, [rdi+rdi*2]
0x180023af9  mov     ebx, edx
0x180023afb  cmp     ecx, eax
0x180023afd  not     rbx
0x180023b00  cmovnb  eax, ecx
0x180023b03  and     rbx, r14
0x180023b06  mov     esi, eax
0x180023b08  lea     rax, [r15+rdi]
0x180023b0c  sub     rbx, rsi
0x180023b0f  cmp     rbx, rax
0x180023b12  jb      short loc_180023AD9
0x180023b14  mov     r9d, 4; flProtect
0x180023b1a  mov     r8d, 1000h; flAllocationType
0x180023b20  mov     edx, esi; dwSize
0x180023b22  mov     rcx, rbx; lpAddress
0x180023b25  call    cs:__imp_VirtualAlloc
0x180023b2b  test    rax, rax
0x180023b2e  jz      short loc_180023AD9
0x180023b30  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x180023b34  mov     r8d, 104h; flNewProtect
0x180023b3a  mov     edx, esi; dwSize
0x180023b3c  mov     rcx, rbx; lpAddress
0x180023b3f  call    cs:__imp_VirtualProtect
0x180023b45  xor     ecx, ecx
0x180023b47  test    eax, eax
0x180023b49  setnz   cl
0x180023b4c  mov     eax, ecx
0x180023b4e  jmp     short loc_180023ADB
```
