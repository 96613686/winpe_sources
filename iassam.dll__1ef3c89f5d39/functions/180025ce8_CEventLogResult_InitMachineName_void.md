# CEventLogResult::InitMachineName(void)

- ea: `0x180025ce8`
- end: `0x180025d88`
- name: `?InitMachineName@CEventLogResult@@AEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(CEventLogResult *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180025e38`

## callees

- `0x18000342c`
- `0x180025ce8`
- `0x180026c64`

## import_xrefs

- `KERNEL32!GetComputerNameExW` at `0x180025d03`
- `KERNEL32!GetComputerNameExW` at `0x180025d69`
- `KERNEL32!GetComputerNameExW` at `0x180025d03`
- `KERNEL32!GetComputerNameExW` at `0x180025d69`
- `KERNEL32!GetLastError` at `0x180025d11`
- `KERNEL32!GetLastError` at `0x180025d11`

## pseudocode

```c
signed int __fastcall CEventLogResult::InitMachineName(CEventLogResult *this)
{
  signed int result; // eax
  unsigned __int128 v3; // rax
  void *v4; // rax
  WCHAR *v5; // rdx
  DWORD nSize; // [rsp+38h] [rbp+10h] BYREF

  nSize = 0;
  GetComputerNameExW(ComputerNamePhysicalDnsFullyQualified, 0, &nSize);
  if ( nSize )
  {
    v3 = nSize * (unsigned __int128)2uLL;
    if ( !is_mul_ok(nSize, 2u) )
      *(_QWORD *)&v3 = -1;
    v4 = operator new[](v3, *((const struct std::nothrow_t **)&v3 + 1));
    std::unique_ptr<unsigned short>::reset((char *)this + 8, v4);
    v5 = (WCHAR *)*((_QWORD *)this + 1);
    if ( !v5 )
      return -2147024882;
    if ( GetComputerNameExW(ComputerNamePhysicalDnsFullyQualified, v5, &nSize) )
      return 0;
    std::unique_ptr<unsigned short>::reset((char *)this + 8, 0);
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180025ce8  push    rbx
0x180025cea  sub     rsp, 20h
0x180025cee  xor     edx, edx; lpBuffer
0x180025cf0  mov     [rsp+28h+nSize], 0
0x180025cf8  mov     rbx, rcx
0x180025cfb  lea     r8, [rsp+28h+nSize]; nSize
0x180025d00  lea     ecx, [rdx+7]; NameType
0x180025d03  call    cs:__imp_GetComputerNameExW
0x180025d09  mov     eax, [rsp+28h+nSize]
0x180025d0d  test    eax, eax
0x180025d0f  jnz     short loc_180025D25
0x180025d11  call    cs:__imp_GetLastError
0x180025d17  test    eax, eax
0x180025d19  jle     short loc_180025D82
0x180025d1b  movzx   eax, ax
0x180025d1e  or      eax, 80070000h
0x180025d23  jmp     short loc_180025D82
0x180025d25  mov     rcx, rax
0x180025d28  mov     eax, 2
0x180025d2d  mul     rcx
0x180025d30  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180025d37  cmovb   rax, rcx
0x180025d3b  mov     rcx, rax; Size
0x180025d3e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180025d43  mov     rdx, rax
0x180025d46  lea     rcx, [rbx+8]
0x180025d4a  call    ?reset@?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort>::reset(ushort *)
0x180025d4f  mov     rdx, [rbx+8]; lpBuffer
0x180025d53  test    rdx, rdx
0x180025d56  jnz     short loc_180025D5F
0x180025d58  mov     eax, 8007000Eh
0x180025d5d  jmp     short loc_180025D82
0x180025d5f  lea     r8, [rsp+28h+nSize]; nSize
0x180025d64  mov     ecx, 7; NameType
0x180025d69  call    cs:__imp_GetComputerNameExW
0x180025d6f  test    eax, eax
0x180025d71  jnz     short loc_180025D80
0x180025d73  xor     edx, edx
0x180025d75  lea     rcx, [rbx+8]
0x180025d79  call    ?reset@?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort>::reset(ushort *)
0x180025d7e  jmp     short loc_180025D11
0x180025d80  xor     eax, eax
0x180025d82  add     rsp, 20h
0x180025d86  pop     rbx
0x180025d87  retn
```
