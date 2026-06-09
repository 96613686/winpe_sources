# DhcpRegReadEnabledDhcpFromMultipleLocations

- ea: `0x180017f44`
- end: `0x180017ff3`
- name: `DhcpRegReadEnabledDhcpFromMultipleLocations`
- size: `175`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR, LPCWSTR)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180009f00`
- `0x18002ddd4`

## callees

- `0x180009fa8`
- `0x180017f44`
- `0x1800337d0`
- `0x1800338c0`
- `0x180034680`

## pseudocode

```c
__int64 __fastcall DhcpRegReadEnabledDhcpFromMultipleLocations(LPCWSTR lpSubKey, LPCWSTR a2, LPCWSTR a3, _DWORD *a4)
{
  int v8; // ecx
  unsigned int EnabledDhcp; // ebx

  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_S(1028, 23, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids, a3);
  EnabledDhcp = DhcpRegReadEnabledDhcp(lpSubKey, a3, a4);
  if ( EnabledDhcp )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_SS(v8, 24, (unsigned int)WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids, (_DWORD)lpSubKey, (__int64)a2);
    EnabledDhcp = DhcpRegReadEnabledDhcp(a2, a3, a4);
  }
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 25, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids, EnabledDhcp);
  return EnabledDhcp;
}

```

## disassembly

```asm
0x180017f44  push    rbx
0x180017f46  push    rbp
0x180017f47  push    rsi
0x180017f48  push    rdi
0x180017f49  push    r14
0x180017f4b  sub     rsp, 30h
0x180017f4f  mov     r14, r9
0x180017f52  mov     rdi, r8
0x180017f55  mov     rbp, rdx
0x180017f58  mov     rsi, rcx
0x180017f5b  test    byte ptr cs:xmmword_1800423E0, 10h
0x180017f62  jz      short loc_180017F7D
0x180017f64  mov     r9, r8
0x180017f67  mov     edx, 17h
0x180017f6c  lea     r8, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids
0x180017f73  mov     ecx, 404h
0x180017f78  call    WPP_SF_S
0x180017f7d  mov     r8, r14
0x180017f80  mov     rdx, rdi; LPCWSTR
0x180017f83  mov     rcx, rsi; lpSubKey
0x180017f86  call    DhcpRegReadEnabledDhcp
0x180017f8b  mov     ebx, eax
0x180017f8d  test    eax, eax
0x180017f8f  jz      short loc_180017FC3
0x180017f91  test    byte ptr cs:xmmword_1800423E0, 10h
0x180017f98  jz      short loc_180017FB3
0x180017f9a  mov     edx, 18h
0x180017f9f  mov     [rsp+58h+var_38], rbp
0x180017fa4  mov     r9, rsi
0x180017fa7  lea     r8, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids
0x180017fae  call    WPP_SF_SS
0x180017fb3  mov     r8, r14
0x180017fb6  mov     rdx, rdi; LPCWSTR
0x180017fb9  mov     rcx, rbp; lpSubKey
0x180017fbc  call    DhcpRegReadEnabledDhcp
0x180017fc1  mov     ebx, eax
0x180017fc3  test    byte ptr cs:xmmword_1800423E0, 10h
0x180017fca  jz      short loc_180017FE5
0x180017fcc  mov     edx, 19h
0x180017fd1  lea     r8, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids
0x180017fd8  mov     ecx, 404h
0x180017fdd  mov     r9d, ebx
0x180017fe0  call    WPP_SF_D
0x180017fe5  mov     eax, ebx
0x180017fe7  add     rsp, 30h
0x180017feb  pop     r14
0x180017fed  pop     rdi
0x180017fee  pop     rsi
0x180017fef  pop     rbp
0x180017ff0  pop     rbx
0x180017ff1  retn
```
