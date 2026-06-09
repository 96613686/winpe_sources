# DhcpRegReadFromAnyLocation

- ea: `0x180005db8`
- end: `0x180005e86`
- name: `DhcpRegReadFromAnyLocation`
- size: `206`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, LPDWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180016350`

## callees

- `0x180005db8`
- `0x180006124`
- `0x1800337d0`
- `0x1800338c0`

## pseudocode

```c
__int64 __fastcall DhcpRegReadFromAnyLocation(char *Src, __int64 a2, BYTE **a3, DWORD *a4, LPDWORD a5)
{
  unsigned int v9; // edi
  __int64 v10; // rbx

  *a4 = 0;
  *a3 = 0;
  *a5 = 0;
  v9 = 2;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_S(1028, 18, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids, a2);
  while ( 1 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)&Src[2 * v10] );
    if ( !v10 )
      break;
    if ( !(unsigned int)DhcpRegReadFromLocation(Src, a2, a3, a4, a5) )
    {
      v9 = 0;
      break;
    }
    Src += 2 * v10 + 2;
  }
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 19, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180005db8  push    rbx
0x180005dba  push    rbp
0x180005dbb  push    rsi
0x180005dbc  push    rdi
0x180005dbd  push    r12
0x180005dbf  push    r13
0x180005dc1  push    r14
0x180005dc3  push    r15
0x180005dc5  sub     rsp, 38h
0x180005dc9  mov     r12, [rsp+78h+arg_20]
0x180005dd1  xor     r13d, r13d
0x180005dd4  mov     [r9], r13d
0x180005dd7  mov     r14, r9
0x180005dda  mov     r15, r8
0x180005ddd  mov     [r8], r13
0x180005de0  mov     rbp, rdx
0x180005de3  mov     rsi, rcx
0x180005de6  mov     [r12], r13d
0x180005dea  mov     edi, 2
0x180005def  test    byte ptr cs:xmmword_1800423E0, 10h
0x180005df6  jnz     short loc_180005E4B
0x180005df8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005dfc  inc     rbx
0x180005dff  cmp     [rsi+rbx*2], r13w
0x180005e04  jnz     short loc_180005DFC
0x180005e06  test    rbx, rbx
0x180005e09  jz      short loc_180005E2E
0x180005e0b  mov     r9, r14
0x180005e0e  mov     [rsp+78h+var_58], r12; LPDWORD
0x180005e13  mov     r8, r15
0x180005e16  mov     rdx, rbp
0x180005e19  mov     rcx, rsi; Src
0x180005e1c  call    DhcpRegReadFromLocation
0x180005e21  test    eax, eax
0x180005e23  jz      short loc_180005E81
0x180005e25  lea     rsi, [rsi+rbx*2]
0x180005e29  add     rsi, rdi
0x180005e2c  jmp     short loc_180005DF8
0x180005e2e  test    byte ptr cs:xmmword_1800423E0, 10h
0x180005e35  jnz     short loc_180005E66
0x180005e37  mov     eax, edi
0x180005e39  add     rsp, 38h
0x180005e3d  pop     r15
0x180005e3f  pop     r14
0x180005e41  pop     r13
0x180005e43  pop     r12
0x180005e45  pop     rdi
0x180005e46  pop     rsi
0x180005e47  pop     rbp
0x180005e48  pop     rbx
0x180005e49  retn
0x180005e4b  mov     edx, 12h
0x180005e50  lea     r8, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids
0x180005e57  mov     ecx, 404h
0x180005e5c  mov     r9, rbp
0x180005e5f  call    WPP_SF_S
0x180005e64  jmp     short loc_180005DF8
0x180005e66  mov     edx, 13h
0x180005e6b  lea     r8, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids
0x180005e72  mov     ecx, 404h
0x180005e77  mov     r9d, edi
0x180005e7a  call    WPP_SF_D
0x180005e7f  jmp     short loc_180005E37
0x180005e81  mov     edi, r13d
0x180005e84  jmp     short loc_180005E2E
```
