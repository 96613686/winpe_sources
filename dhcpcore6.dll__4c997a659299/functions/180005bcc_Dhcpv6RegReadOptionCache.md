# Dhcpv6RegReadOptionCache

- ea: `0x180005bcc`
- end: `0x180005db0`
- name: `Dhcpv6RegReadOptionCache`
- size: `484`
- prototype: `__int64 __fastcall(__int64, HKEY)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000bc88`
- `0x180014e18`

## callees

- `0x180005bcc`
- `0x18000678c`
- `0x180017bc4`
- `0x180018fa4`
- `0x18002836c`
- `0x1800338c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005d58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005d58`

## pseudocode

```c
__int64 __fastcall Dhcpv6RegReadOptionCache(__int64 a1, HKEY a2)
{
  unsigned int RegistryValue; // edi
  LPVOID lpMem; // [rsp+50h] [rbp-68h] BYREF

  lpMem = 0;
  RegistryValue = Dhcpv6QueryRegistryValue(a2, (__int64)&lpMem);
  if ( !RegistryValue )
    RegistryValue = 87;
  if ( (xmmword_1800423E0 & 2) != 0 )
    WPP_SF_D(1025, 31, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids, RegistryValue);
  return RegistryValue;
}

```

## disassembly

```asm
0x180005bcc  mov     r11, rsp
0x180005bcf  mov     [r11+10h], rbx
0x180005bd3  mov     [r11+20h], r9b
0x180005bd7  mov     [r11+18h], r8
0x180005bdb  mov     [r11+8], rcx
0x180005bdf  push    rbp
0x180005be0  push    rsi
0x180005be1  push    rdi
0x180005be2  push    r12
0x180005be4  push    r13
0x180005be6  push    r14
0x180005be8  push    r15
0x180005bea  sub     rsp, 80h
0x180005bf1  lea     rax, [r11-68h]
0x180005bf5  movaps  [rsp+0B8h+var_48], xmm6
0x180005bfa  lea     r9, [r11+20h]
0x180005bfe  mov     [rsp+0B8h+var_98], rax; __int64
0x180005c03  lea     r8, [r11+18h]
0x180005c07  mov     dword ptr [r11+18h], 0
0x180005c0f  mov     rcx, rdx; hKey
0x180005c12  mov     qword ptr [r11-68h], 0
0x180005c1a  xorps   xmm6, xmm6
0x180005c1d  mov     dword ptr [r11+20h], 400h
0x180005c25  call    Dhcpv6QueryRegistryValue
0x180005c2a  mov     edi, eax
0x180005c2c  test    eax, eax
0x180005c2e  jnz     loc_180005D6B
0x180005c34  mov     esi, dword ptr [rsp+0B8h+arg_18]
0x180005c3b  test    esi, esi
0x180005c3d  jz      loc_180005D66
0x180005c43  cmp     [rsp+0B8h+arg_10], 3
0x180005c4b  jnz     loc_180005D66
0x180005c51  mov     r14, [rsp+0B8h+lpMem]
0x180005c56  mov     r15, r14
0x180005c59  cmp     esi, 14h
0x180005c5c  jb      loc_180005D41
0x180005c62  mov     eax, [r14]
0x180005c65  lea     r8, [r14+4]
0x180005c69  mov     ebp, [r8]
0x180005c6c  mov     r12d, [r8+4]
0x180005c70  mov     dword ptr [rsp+0B8h+lpMem], eax
0x180005c74  lea     r9d, [rbp+17h]
0x180005c78  add     r9d, r12d
0x180005c7b  and     r9d, 0FFFFFFFCh
0x180005c7f  cmp     r9d, esi
0x180005c82  ja      loc_180005D41
0x180005c88  mov     eax, [r8+0Ch]
0x180005c8c  lea     rcx, [r8+10h]
0x180005c90  xor     ebx, ebx
0x180005c92  mov     dword ptr [rsp+0B8h+arg_18], eax
0x180005c99  test    ebp, ebp
0x180005c9b  lea     rdx, [rcx+rbp]
0x180005c9f  lea     r14, [rdx+3]
0x180005ca3  cmovnz  rbx, rcx
0x180005ca7  xor     eax, eax
0x180005ca9  test    r12d, r12d
0x180005cac  cmovnz  rax, rdx
0x180005cb0  add     r14, r12
0x180005cb3  and     r14, 0FFFFFFFFFFFFFFFCh
0x180005cb7  mov     [rsp+0B8h+var_60], rax
0x180005cbc  sub     esi, r9d
0x180005cbf  test    r12d, r12d
0x180005cc2  jz      short loc_180005C59
0x180005cc4  mov     r13d, [r8+8]
0x180005cc8  test    rbx, rbx
0x180005ccb  jz      short loc_180005CE0
0x180005ccd  mov     r8d, ebp
0x180005cd0  mov     rdx, rbx
0x180005cd3  call    Dhcpv6AddClass
0x180005cd8  mov     rbx, rax
0x180005cdb  test    rax, rax
0x180005cde  jz      short loc_180005D41
0x180005ce0  mov     eax, dword ptr [rsp+0B8h+arg_18]
0x180005ce7  mov     r9, rbx; int
0x180005cea  movzx   edx, byte ptr [rsp+0B8h+lpMem]; int
0x180005cef  mov     r8d, r13d; int
0x180005cf2  mov     rcx, qword ptr [rsp+0B8h+arg_0]; int
0x180005cfa  mov     [rsp+0B8h+var_78], rax; __int64
0x180005cff  mov     rax, [rsp+0B8h+var_60]
0x180005d04  mov     dword ptr [rsp+0B8h+Size], r12d; Size
0x180005d09  mov     [rsp+0B8h+Src], rax; Src
0x180005d0e  lea     rax, [rsp+0B8h+var_58]
0x180005d13  mov     [rsp+0B8h+var_90], rax; __int64
0x180005d18  mov     dword ptr [rsp+0B8h+var_98], ebp; int
0x180005d1c  movdqa  xmmword ptr [rsp+0B8h+var_58], xmm6
0x180005d22  call    Dhcpv6AddOptionToList
0x180005d27  mov     edi, eax
0x180005d29  test    eax, eax
0x180005d2b  jz      loc_180005C59
0x180005d31  test    rbx, rbx
0x180005d34  jz      short loc_180005D41
0x180005d36  mov     r8d, ebp
0x180005d39  mov     rdx, rbx
0x180005d3c  call    Dhcpv6DelClass
0x180005d41  test    r15, r15
0x180005d44  jz      short loc_180005D8D
0x180005d46  mov     rcx, gs:60h
0x180005d4f  mov     r8, r15; lpMem
0x180005d52  xor     edx, edx; dwFlags
0x180005d54  mov     rcx, [rcx+30h]; hHeap
0x180005d58  call    cs:__imp_HeapFree
0x180005d5f  nop     dword ptr [rax+rax+00h]
0x180005d64  jmp     short loc_180005D8D
0x180005d66  mov     edi, 57h ; 'W'
0x180005d6b  test    byte ptr cs:xmmword_1800423E0, 2
0x180005d72  jz      short loc_180005D8D
0x180005d74  mov     edx, 1Fh
0x180005d79  lea     r8, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids
0x180005d80  mov     ecx, 401h
0x180005d85  mov     r9d, edi
0x180005d88  call    WPP_SF_D
0x180005d8d  mov     rbx, [rsp+0B8h+arg_8]
0x180005d95  mov     eax, edi
0x180005d97  movaps  xmm6, [rsp+0B8h+var_48]
0x180005d9c  add     rsp, 80h
0x180005da3  pop     r15
0x180005da5  pop     r14
0x180005da7  pop     r13
0x180005da9  pop     r12
0x180005dab  pop     rdi
0x180005dac  pop     rsi
0x180005dad  pop     rbp
0x180005dae  retn
```
