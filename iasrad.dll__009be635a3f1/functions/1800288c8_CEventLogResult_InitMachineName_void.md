# CEventLogResult::InitMachineName(void)

- ea: `0x1800288c8`
- end: `0x180028968`
- name: `?InitMachineName@CEventLogResult@@AEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(CEventLogResult *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b560`

## callees

- `0x18000e4e0`
- `0x1800288c8`
- `0x180029820`

## import_xrefs

- `KERNEL32!GetComputerNameExW` at `0x1800288e3`
- `KERNEL32!GetComputerNameExW` at `0x180028949`
- `KERNEL32!GetComputerNameExW` at `0x1800288e3`
- `KERNEL32!GetComputerNameExW` at `0x180028949`
- `KERNEL32!GetLastError` at `0x1800288f1`
- `KERNEL32!GetLastError` at `0x1800288f1`

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
0x1800288c8  push    rbx
0x1800288ca  sub     rsp, 20h
0x1800288ce  xor     edx, edx; lpBuffer
0x1800288d0  mov     [rsp+28h+nSize], 0
0x1800288d8  mov     rbx, rcx
0x1800288db  lea     r8, [rsp+28h+nSize]; nSize
0x1800288e0  lea     ecx, [rdx+7]; NameType
0x1800288e3  call    cs:__imp_GetComputerNameExW
0x1800288e9  mov     eax, [rsp+28h+nSize]
0x1800288ed  test    eax, eax
0x1800288ef  jnz     short loc_180028905
0x1800288f1  call    cs:__imp_GetLastError
0x1800288f7  test    eax, eax
0x1800288f9  jle     short loc_180028962
0x1800288fb  movzx   eax, ax
0x1800288fe  or      eax, 80070000h
0x180028903  jmp     short loc_180028962
0x180028905  mov     rcx, rax
0x180028908  mov     eax, 2
0x18002890d  mul     rcx
0x180028910  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180028917  cmovb   rax, rcx
0x18002891b  mov     rcx, rax; Size
0x18002891e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180028923  mov     rdx, rax
0x180028926  lea     rcx, [rbx+8]
0x18002892a  call    ?reset@?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort>::reset(ushort *)
0x18002892f  mov     rdx, [rbx+8]; lpBuffer
0x180028933  test    rdx, rdx
0x180028936  jnz     short loc_18002893F
0x180028938  mov     eax, 8007000Eh
0x18002893d  jmp     short loc_180028962
0x18002893f  lea     r8, [rsp+28h+nSize]; nSize
0x180028944  mov     ecx, 7; NameType
0x180028949  call    cs:__imp_GetComputerNameExW
0x18002894f  test    eax, eax
0x180028951  jnz     short loc_180028960
0x180028953  xor     edx, edx
0x180028955  lea     rcx, [rbx+8]
0x180028959  call    ?reset@?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort>::reset(ushort *)
0x18002895e  jmp     short loc_1800288F1
0x180028960  xor     eax, eax
0x180028962  add     rsp, 20h
0x180028966  pop     rbx
0x180028967  retn
```
