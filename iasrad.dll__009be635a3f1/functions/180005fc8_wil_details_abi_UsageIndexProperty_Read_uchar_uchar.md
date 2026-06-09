# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180005fc8`
- end: `0x1800060b1`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003fb8`
- `0x1800051cc`
- `0x18000578c`
- `0x1800065e8`
- `0x180007684`

## callees

- `0x180005fc8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006017`
- `msvcrt!memcpy_s` at `0x18000604c`
- `msvcrt!memcpy_s` at `0x180006077`
- `msvcrt!memcpy_s` at `0x180006017`
- `msvcrt!memcpy_s` at `0x18000604c`
- `msvcrt!memcpy_s` at `0x180006077`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char *v5; // r8
  char *v7; // rbx
  __int16 v8; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al
  unsigned __int16 v11; // [rsp+50h] [rbp+8h] BYREF

  v5 = (char *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    v11 = 0;
    memcpy_s(&v11, 2u, v5, 2u);
    *((_DWORD *)this + 1) = v11;
  }
  else
  {
    v7 = (char *)*a2;
    if ( *((_BYTE *)this + 2) == 2 )
    {
      v7 = v5 + 4;
      if ( v5 + 4 > (char *)a3 )
        return 0;
      *((_QWORD *)this + 2) = v5;
      memcpy_s((char *)this + 4, 4u, v5, 4u);
    }
  }
  v8 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v8 )
    goto LABEL_10;
  if ( v7 + 2 > (char *)a3 )
    return 0;
  memcpy_s((char *)this + 8, 2u, v7, 2u);
  v7 += 2;
LABEL_10:
  v9 = (unsigned __int8 *)&v7[*((unsigned __int16 *)this + 4)];
  if ( v9 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v7;
  result = 1;
  *a2 = v9;
  return result;
}

```

## disassembly

```asm
0x180005fc8  mov     rax, rsp
0x180005fcb  mov     [rax+10h], rbx
0x180005fcf  mov     [rax+18h], rbp
0x180005fd3  push    rsi
0x180005fd4  push    rdi
0x180005fd5  push    r12
0x180005fd7  push    r14
0x180005fd9  push    r15
0x180005fdb  sub     rsp, 20h
0x180005fdf  xor     r15d, r15d
0x180005fe2  mov     rsi, r8
0x180005fe5  cmp     byte ptr [rcx+2], 1
0x180005fe9  mov     r12, rdx
0x180005fec  mov     r8, [rdx]; Source
0x180005fef  mov     rdi, rcx
0x180005ff2  jnz     short loc_180006027
0x180005ff4  lea     rbx, [r8+2]
0x180005ff8  cmp     rbx, rsi
0x180005ffb  ja      loc_18000608C
0x180006001  lea     ebp, [r15+2]
0x180006005  mov     [rcx+10h], r8
0x180006009  mov     r9d, ebp; SourceSize
0x18000600c  mov     [rax+8], r15w
0x180006011  mov     edx, ebp; DestinationSize
0x180006013  lea     rcx, [rax+8]; Destination
0x180006017  call    cs:__imp_memcpy_s
0x18000601d  movzx   eax, [rsp+48h+arg_0]
0x180006022  mov     [rdi+4], eax
0x180006025  jmp     short loc_180006052
0x180006027  mov     ebp, 2
0x18000602c  mov     rbx, r8
0x18000602f  cmp     [rcx+2], bpl
0x180006033  jnz     short loc_180006052
0x180006035  lea     rbx, [r8+4]
0x180006039  cmp     rbx, rsi
0x18000603c  ja      short loc_18000608C
0x18000603e  lea     edx, [rbp+2]; DestinationSize
0x180006041  mov     [rcx+10h], r8
0x180006045  mov     r9d, edx; SourceSize
0x180006048  add     rcx, 4; Destination
0x18000604c  call    cs:__imp_memcpy_s
0x180006052  movzx   eax, word ptr [rdi]
0x180006055  lea     r14, [rdi+8]
0x180006059  mov     [r14], ax
0x18000605d  test    ax, ax
0x180006060  jnz     short loc_180006080
0x180006062  lea     r15, [rbx+2]
0x180006066  cmp     r15, rsi
0x180006069  ja      short loc_18000608C
0x18000606b  mov     r9, rbp; SourceSize
0x18000606e  mov     r8, rbx; Source
0x180006071  mov     rdx, rbp; DestinationSize
0x180006074  mov     rcx, r14; Destination
0x180006077  call    cs:__imp_memcpy_s
0x18000607d  mov     rbx, r15
0x180006080  movzx   ecx, word ptr [r14]
0x180006084  add     rcx, rbx
0x180006087  cmp     rcx, rsi
0x18000608a  jbe     short loc_180006090
0x18000608c  xor     al, al
0x18000608e  jmp     short loc_18000609A
0x180006090  mov     [rdi+18h], rbx
0x180006094  mov     al, 1
0x180006096  mov     [r12], rcx
0x18000609a  mov     rbx, [rsp+48h+arg_8]
0x18000609f  mov     rbp, [rsp+48h+arg_10]
0x1800060a4  add     rsp, 20h
0x1800060a8  pop     r15
0x1800060aa  pop     r14
0x1800060ac  pop     r12
0x1800060ae  pop     rdi
0x1800060af  pop     rsi
0x1800060b0  retn
```
