# LipsBufferCopy

- ea: `0x18004a188`
- end: `0x18004a220`
- name: `LipsBufferCopy`
- size: `152`
- prototype: `__int64 __fastcall(void *Src, size_t Size, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18004c85c`

## callees

- `0x180006f00`
- `0x18000c4d0`
- `0x18000e510`
- `0x18004a188`
- `0x18004d052`

## string_xrefs

- `0x18004a1f0`: `LipsBufferCopy`

## pseudocode

```c
__int64 __fastcall LipsBufferCopy(void *Src, size_t Size, __int64 a3, _QWORD *a4)
{
  void *v7; // rax

  *a4 = 0;
  if ( !Size )
    return 0;
  v7 = IpsecAllocMem(Size);
  *a4 = v7;
  if ( v7 )
  {
    memcpy_0(v7, Src, Size);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_f9bd4346a19839ab9ee18df0d3aaefbd_Traceguids, 8);
  return LipsReportError(8, "LipsBufferCopy");
}

```

## disassembly

```asm
0x18004a188  mov     [rsp+arg_0], rbx
0x18004a18d  mov     [rsp+arg_8], rsi
0x18004a192  push    rdi
0x18004a193  sub     rsp, 20h
0x18004a197  mov     qword ptr [r9], 0
0x18004a19e  mov     rdi, r9
0x18004a1a1  mov     rbx, rdx
0x18004a1a4  mov     rsi, rcx
0x18004a1a7  test    rdx, rdx
0x18004a1aa  jz      short loc_18004A20E
0x18004a1ac  mov     rcx, rdx
0x18004a1af  call    IpsecAllocMem
0x18004a1b4  mov     [rdi], rax
0x18004a1b7  test    rax, rax
0x18004a1ba  jnz     short loc_18004A200
0x18004a1bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a1c3  lea     rax, WPP_GLOBAL_Control
0x18004a1ca  mov     ebx, 8
0x18004a1cf  cmp     rcx, rax
0x18004a1d2  jz      short loc_18004A1F0
0x18004a1d4  test    byte ptr [rcx+1Ch], 10h
0x18004a1d8  jz      short loc_18004A1F0
0x18004a1da  mov     rcx, [rcx+10h]
0x18004a1de  lea     edx, [rbx+3]
0x18004a1e1  mov     r9d, ebx
0x18004a1e4  lea     r8, WPP_f9bd4346a19839ab9ee18df0d3aaefbd_Traceguids
0x18004a1eb  call    WPP_SF_d
0x18004a1f0  lea     rdx, aLipsbuffercopy; "LipsBufferCopy"
0x18004a1f7  mov     ecx, ebx
0x18004a1f9  call    LipsReportError
0x18004a1fe  jmp     short loc_18004A210
0x18004a200  mov     r8, rbx; Size
0x18004a203  mov     rdx, rsi; Src
0x18004a206  mov     rcx, rax; void *
0x18004a209  call    memcpy_0
0x18004a20e  xor     eax, eax
0x18004a210  mov     rbx, [rsp+28h+arg_0]
0x18004a215  mov     rsi, [rsp+28h+arg_8]
0x18004a21a  add     rsp, 20h
0x18004a21e  pop     rdi
0x18004a21f  retn
```
