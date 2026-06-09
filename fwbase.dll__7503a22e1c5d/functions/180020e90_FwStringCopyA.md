# FwStringCopyA

- ea: `0x180020e90`
- end: `0x180020f79`
- name: `FwStringCopyA`
- size: `233`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180004750`
- `0x1800047e0`
- `0x180004870`
- `0x18000c060`
- `0x180020e90`
- `0x180021528`
- `0x18002f674`

## string_xrefs

- `0x180020f08`: `FwStringCopyA`
- `0x180020f33`: `FwStringCopyA`
- `0x180020f47`: `FwStringCopyA`

## pseudocode

```c
__int64 __fastcall FwStringCopyA(_BYTE *Src, _QWORD *a2, __int64 a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rdx
  void *v9; // rax
  size_t Size; // [rsp+30h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, a3, Src);
  v5 = 0;
  Size = 0;
  *a2 = 0;
  if ( Src )
  {
    v6 = -1;
    do
      ++v6;
    while ( Src[v6] );
    v7 = FwSizeTMultiply(v6 + 1, 1, &Size);
    v5 = v7;
    if ( v7 < 0 )
    {
      FwReportReturnError("FwStringCopyA", (unsigned int)v7);
      return (unsigned int)FwReportReturnError("FwStringCopyA", v5);
    }
    v9 = (void *)FwAlloc(Size, v8);
    *a2 = v9;
    if ( v9 )
    {
      memcpy_0(v9, Src, Size);
      return v5;
    }
    v5 = FwReportErrorAsWinError("FwStringCopyA", "FwAlloc", 8);
    if ( (v5 & 0x80000000) != 0 )
      return (unsigned int)FwReportReturnError("FwStringCopyA", v5);
  }
  return v5;
}

```

## disassembly

```asm
0x180020e90  mov     [rsp+arg_8], rbx
0x180020e95  mov     [rsp+arg_10], rsi
0x180020e9a  push    rdi
0x180020e9b  sub     rsp, 20h
0x180020e9f  mov     rsi, rdx
0x180020ea2  mov     rdi, rcx
0x180020ea5  mov     rcx, cs:WPP_GLOBAL_Control
0x180020eac  lea     rax, WPP_GLOBAL_Control
0x180020eb3  cmp     rcx, rax
0x180020eb6  jz      short loc_180020ECF
0x180020eb8  test    byte ptr [rcx+1Ch], 4
0x180020ebc  jz      short loc_180020ECF
0x180020ebe  mov     rcx, [rcx+10h]
0x180020ec2  mov     edx, 0Ch
0x180020ec7  mov     r9, rdi
0x180020eca  call    WPP_SF_s
0x180020ecf  xor     ebx, ebx
0x180020ed1  mov     [rsp+28h+Size], rbx
0x180020ed6  mov     [rsi], rbx
0x180020ed9  test    rdi, rdi
0x180020edc  jz      loc_180020F67
0x180020ee2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180020ee6  inc     rcx
0x180020ee9  cmp     [rdi+rcx], bl
0x180020eec  jnz     short loc_180020EE6
0x180020eee  inc     rcx
0x180020ef1  lea     r8, [rsp+28h+Size]
0x180020ef6  mov     edx, 1
0x180020efb  call    FwSizeTMultiply
0x180020f00  mov     ebx, eax
0x180020f02  test    eax, eax
0x180020f04  jns     short loc_180020F16
0x180020f06  mov     edx, eax
0x180020f08  lea     rcx, aFwstringcopya_0; "FwStringCopyA"
0x180020f0f  call    FwReportReturnError
0x180020f14  jmp     short loc_180020F45
0x180020f16  mov     rcx, [rsp+28h+Size]
0x180020f1b  call    FwAlloc
0x180020f20  mov     [rsi], rax
0x180020f23  test    rax, rax
0x180020f26  jnz     short loc_180020F57
0x180020f28  lea     r8d, [rax+8]
0x180020f2c  lea     rdx, aFwalloc_0; "FwAlloc"
0x180020f33  lea     rcx, aFwstringcopya_0; "FwStringCopyA"
0x180020f3a  call    FwReportErrorAsWinError
0x180020f3f  mov     ebx, eax
0x180020f41  test    eax, eax
0x180020f43  jns     short loc_180020F67
0x180020f45  mov     edx, ebx
0x180020f47  lea     rcx, aFwstringcopya_0; "FwStringCopyA"
0x180020f4e  call    FwReportReturnError
0x180020f53  mov     ebx, eax
0x180020f55  jmp     short loc_180020F67
0x180020f57  mov     r8, [rsp+28h+Size]; Size
0x180020f5c  mov     rdx, rdi; Src
0x180020f5f  mov     rcx, rax; void *
0x180020f62  call    memcpy_0
0x180020f67  mov     rsi, [rsp+28h+arg_10]
0x180020f6c  mov     eax, ebx
0x180020f6e  mov     rbx, [rsp+28h+arg_8]
0x180020f73  add     rsp, 20h
0x180020f77  pop     rdi
0x180020f78  retn
```
