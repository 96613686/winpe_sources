# STRA::AuxAppend(uchar const *,ulong,ulong,bool)

- ea: `0x180002c48`
- end: `0x180002cf4`
- name: `?AuxAppend@STRA@@AEAAJPEBEKK_N@Z`
- size: `172`
- prototype: `__int64 __fastcall(STRA *__hidden this, const unsigned __int8 *Src, size_t Size, unsigned int, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002714`

## callees

- `0x180002b94`
- `0x180002c48`
- `0x180002d96`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002c89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002c89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ca7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ca7`

## pseudocode

```c
signed int __fastcall STRA::AuxAppend(STRA *this, const unsigned __int8 *Src, size_t Size, unsigned int a4)
{
  __int64 v4; // rbp
  unsigned __int64 v6; // rcx
  size_t v8; // r14
  unsigned __int64 v9; // rdx
  signed int result; // eax

  v4 = a4;
  v6 = *((unsigned int *)this + 10);
  v8 = (unsigned int)Size;
  if ( v6 >= (unsigned int)Size + (unsigned __int64)a4 + 1 )
    goto LABEL_8;
  v9 = (unsigned int)Size + a4 + 128LL;
  if ( v9 > 0xFFFFFFFF )
  {
    SetLastError(0x216u);
    return 0;
  }
  if ( (unsigned int)v9 <= (unsigned int)v6 || BUFFER::ReallocStorage(this, v9) )
  {
LABEL_8:
    memcpy_0((void *)(v4 + *((_QWORD *)this + 4)), Src, v8);
    *((_DWORD *)this + 12) = v8 + v4;
    *(_BYTE *)((unsigned int)(v8 + v4) + *((_QWORD *)this + 4)) = 0;
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180002c48  push    rbx
0x180002c4a  push    rbp
0x180002c4b  push    rsi
0x180002c4c  push    rdi
0x180002c4d  push    r14
0x180002c4f  push    r15
0x180002c51  sub     rsp, 28h
0x180002c55  mov     ebp, r9d
0x180002c58  mov     rbx, rcx
0x180002c5b  mov     ecx, [rcx+28h]
0x180002c5e  mov     r15, rdx
0x180002c61  mov     r14d, r8d
0x180002c64  lea     rax, [rbp+1]
0x180002c68  add     rax, r14
0x180002c6b  cmp     rcx, rax
0x180002c6e  jnb     short loc_180002CC1
0x180002c70  lea     rdx, [rbp+80h]
0x180002c77  mov     eax, 0FFFFFFFFh
0x180002c7c  add     rdx, r14; unsigned int
0x180002c7f  cmp     rdx, rax
0x180002c82  jbe     short loc_180002C97
0x180002c84  mov     ecx, 216h; dwErrCode
0x180002c89  call    cs:__imp_SetLastError
0x180002c90  nop     dword ptr [rax+rax+00h]
0x180002c95  jmp     short loc_180002CE4
0x180002c97  cmp     edx, ecx
0x180002c99  jbe     short loc_180002CC1
0x180002c9b  mov     rcx, rbx; this
0x180002c9e  call    ?ReallocStorage@BUFFER@@AEAA_NK@Z; BUFFER::ReallocStorage(ulong)
0x180002ca3  test    al, al
0x180002ca5  jnz     short loc_180002CC1
0x180002ca7  call    cs:__imp_GetLastError
0x180002cae  nop     dword ptr [rax+rax+00h]
0x180002cb3  test    eax, eax
0x180002cb5  jle     short loc_180002CE6
0x180002cb7  movzx   eax, ax
0x180002cba  or      eax, 80070000h
0x180002cbf  jmp     short loc_180002CE6
0x180002cc1  mov     rcx, [rbx+20h]
0x180002cc5  mov     r8, r14; Size
0x180002cc8  add     rcx, rbp; void *
0x180002ccb  mov     rdx, r15; Src
0x180002cce  call    memcpy_0
0x180002cd3  lea     eax, [r14+rbp]
0x180002cd7  mov     [rbx+30h], eax
0x180002cda  mov     ecx, eax
0x180002cdc  mov     rax, [rbx+20h]
0x180002ce0  mov     byte ptr [rcx+rax], 0
0x180002ce4  xor     eax, eax
0x180002ce6  add     rsp, 28h
0x180002cea  pop     r15
0x180002cec  pop     r14
0x180002cee  pop     rdi
0x180002cef  pop     rsi
0x180002cf0  pop     rbp
0x180002cf1  pop     rbx
0x180002cf2  retn
```
