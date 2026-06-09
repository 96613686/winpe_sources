# STRA::AuxAppend(uchar const *,ulong,ulong,bool)

- ea: `0x180002a54`
- end: `0x180002af3`
- name: `?AuxAppend@STRA@@AEAAJPEBEKK_N@Z`
- size: `159`
- prototype: `__int64 __fastcall(STRA *__hidden this, const unsigned __int8 *Src, size_t Size, unsigned int, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800025bc`

## callees

- `0x1800029c0`
- `0x180002a54`
- `0x180002b96`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002a95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002a95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002aad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002aad`

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
0x180002a54  push    rbx
0x180002a56  push    rbp
0x180002a57  push    rsi
0x180002a58  push    rdi
0x180002a59  push    r14
0x180002a5b  push    r15
0x180002a5d  sub     rsp, 28h
0x180002a61  mov     ebp, r9d
0x180002a64  mov     rbx, rcx
0x180002a67  mov     ecx, [rcx+28h]
0x180002a6a  mov     r15, rdx
0x180002a6d  mov     r14d, r8d
0x180002a70  lea     rax, [rbp+1]
0x180002a74  add     rax, r14
0x180002a77  cmp     rcx, rax
0x180002a7a  jnb     short loc_180002AC1
0x180002a7c  lea     rdx, [rbp+80h]
0x180002a83  mov     eax, 0FFFFFFFFh
0x180002a88  add     rdx, r14; unsigned int
0x180002a8b  cmp     rdx, rax
0x180002a8e  jbe     short loc_180002A9D
0x180002a90  mov     ecx, 216h; dwErrCode
0x180002a95  call    cs:__imp_SetLastError
0x180002a9b  jmp     short loc_180002AE4
0x180002a9d  cmp     edx, ecx
0x180002a9f  jbe     short loc_180002AC1
0x180002aa1  mov     rcx, rbx; this
0x180002aa4  call    ?ReallocStorage@BUFFER@@AEAA_NK@Z; BUFFER::ReallocStorage(ulong)
0x180002aa9  test    al, al
0x180002aab  jnz     short loc_180002AC1
0x180002aad  call    cs:__imp_GetLastError
0x180002ab3  test    eax, eax
0x180002ab5  jle     short loc_180002AE6
0x180002ab7  movzx   eax, ax
0x180002aba  or      eax, 80070000h
0x180002abf  jmp     short loc_180002AE6
0x180002ac1  mov     rcx, [rbx+20h]
0x180002ac5  mov     r8, r14; Size
0x180002ac8  add     rcx, rbp; void *
0x180002acb  mov     rdx, r15; Src
0x180002ace  call    memcpy_0
0x180002ad3  lea     eax, [r14+rbp]
0x180002ad7  mov     [rbx+30h], eax
0x180002ada  mov     ecx, eax
0x180002adc  mov     rax, [rbx+20h]
0x180002ae0  mov     byte ptr [rcx+rax], 0
0x180002ae4  xor     eax, eax
0x180002ae6  add     rsp, 28h
0x180002aea  pop     r15
0x180002aec  pop     r14
0x180002aee  pop     rdi
0x180002aef  pop     rsi
0x180002af0  pop     rbp
0x180002af1  pop     rbx
0x180002af2  retn
```
