# NcaStringCopy

- ea: `0x180019c70`
- end: `0x180019d7e`
- name: `NcaStringCopy`
- size: `270`
- prototype: `__int64 __fastcall(_WORD *Src, _QWORD *)`
- caller_count: `14`
- callee_count: `8`
- tags: ``

## callers

- `0x180001400`
- `0x1800050d8`
- `0x180005398`
- `0x1800063f0`
- `0x180006470`
- `0x1800066ac`
- `0x18000673c`
- `0x180009714`
- `0x18000a398`
- `0x1800112ac`
- `0x1800193f8`
- `0x180019638`
- `0x18001a38c`
- `0x18001c03c`

## callees

- `0x1800033bc`
- `0x180004f04`
- `0x1800199b4`
- `0x180019ad0`
- `0x180019c70`
- `0x180019dac`
- `0x18001abd4`
- `0x18001cc32`

## string_xrefs

- `0x180019d13`: `NcaStringCopy`
- `0x180019d3e`: `NcaStringCopy`
- `0x180019d52`: `NcaStringCopy`

## pseudocode

```c
__int64 __fastcall NcaStringCopy(_WORD *Src, _QWORD *a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rcx
  signed int v7; // eax
  int v8; // r8d
  int v9; // r8d
  void *v10; // rax
  size_t Size; // [rsp+50h] [rbp+8h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 4) != 0 )
      WPP_SF_S(v4[2], 20, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids, Src);
  }
  Size = 0;
  v5 = 0;
  *a2 = 0;
  if ( Src )
  {
    v6 = -1;
    do
      ++v6;
    while ( Src[v6] );
    v7 = NcaSizeTMultiply(v6 + 1, 2u, &Size);
    v5 = v7;
    if ( v7 < 0 )
    {
      NcaReportReturnError((int)"NcaStringCopy", v7, v8);
      return (unsigned int)NcaReportReturnError((int)"NcaStringCopy", v5, v9);
    }
    v10 = NcaAlloc(Size);
    *a2 = v10;
    if ( v10 )
    {
      memcpy_0(v10, Src, Size);
      return v5;
    }
    v5 = NcaReportErrorAsWinError((int)"NcaStringCopy", (__int64)"NcaAlloc", 8);
    if ( (v5 & 0x80000000) != 0 )
      return (unsigned int)NcaReportReturnError((int)"NcaStringCopy", v5, v9);
  }
  return v5;
}

```

## disassembly

```asm
0x180019c70  push    rbx
0x180019c72  push    rbp
0x180019c73  push    rsi
0x180019c74  push    rdi
0x180019c75  sub     rsp, 28h
0x180019c79  mov     rsi, rdx
0x180019c7c  mov     rdi, rcx
0x180019c7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c86  lea     rbx, WPP_GLOBAL_Control
0x180019c8d  cmp     rcx, rbx
0x180019c90  jz      short loc_180019CD7
0x180019c92  test    byte ptr [rcx+1Ch], 8
0x180019c96  jz      short loc_180019CB4
0x180019c98  mov     rcx, [rcx+10h]
0x180019c9c  lea     r8, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids
0x180019ca3  mov     edx, 13h
0x180019ca8  call    WPP_SF_
0x180019cad  mov     rcx, cs:WPP_GLOBAL_Control
0x180019cb4  cmp     rcx, rbx
0x180019cb7  jz      short loc_180019CD7
0x180019cb9  test    byte ptr [rcx+1Ch], 4
0x180019cbd  jz      short loc_180019CD7
0x180019cbf  mov     rcx, [rcx+10h]
0x180019cc3  lea     r8, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids
0x180019cca  mov     edx, 14h
0x180019ccf  mov     r9, rdi
0x180019cd2  call    WPP_SF_S
0x180019cd7  xor     ebp, ebp
0x180019cd9  mov     [rsp+48h+Size], rbp
0x180019cde  mov     ebx, ebp
0x180019ce0  mov     [rsi], rbp
0x180019ce3  test    rdi, rdi
0x180019ce6  jz      loc_180019D72
0x180019cec  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180019cf0  inc     rcx
0x180019cf3  cmp     [rdi+rcx*2], bp
0x180019cf7  jnz     short loc_180019CF0
0x180019cf9  inc     rcx
0x180019cfc  lea     r8, [rsp+48h+Size]
0x180019d01  mov     edx, 2
0x180019d06  call    NcaSizeTMultiply
0x180019d0b  mov     ebx, eax
0x180019d0d  test    eax, eax
0x180019d0f  jns     short loc_180019D21
0x180019d11  mov     edx, eax
0x180019d13  lea     rcx, aNcastringcopy; "NcaStringCopy"
0x180019d1a  call    NcaReportReturnError
0x180019d1f  jmp     short loc_180019D50
0x180019d21  mov     rcx, [rsp+48h+Size]
0x180019d26  call    NcaAlloc
0x180019d2b  mov     [rsi], rax
0x180019d2e  test    rax, rax
0x180019d31  jnz     short loc_180019D62
0x180019d33  lea     r8d, [rax+8]
0x180019d37  lea     rdx, aNcaalloc; "NcaAlloc"
0x180019d3e  lea     rcx, aNcastringcopy; "NcaStringCopy"
0x180019d45  call    NcaReportErrorAsWinError
0x180019d4a  mov     ebx, eax
0x180019d4c  test    eax, eax
0x180019d4e  jns     short loc_180019D72
0x180019d50  mov     edx, ebx
0x180019d52  lea     rcx, aNcastringcopy; "NcaStringCopy"
0x180019d59  call    NcaReportReturnError
0x180019d5e  mov     ebx, eax
0x180019d60  jmp     short loc_180019D72
0x180019d62  mov     r8, [rsp+48h+Size]; Size
0x180019d67  mov     rdx, rdi; Src
0x180019d6a  mov     rcx, rax; void *
0x180019d6d  call    memcpy_0
0x180019d72  mov     eax, ebx
0x180019d74  add     rsp, 28h
0x180019d78  pop     rdi
0x180019d79  pop     rsi
0x180019d7a  pop     rbp
0x180019d7b  pop     rbx
0x180019d7c  retn
```
