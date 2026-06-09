# STRA::Copy(char const *)

- ea: `0x18000cd40`
- end: `0x18000ce01`
- name: `?Copy@STRA@@QEAAJPEBD@Z`
- size: `193`
- prototype: `__int64 __fastcall(STRA *__hidden this, const char *Src)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180001160`
- `0x18001ce20`

## callees

- `0x18000cd40`
- `0x18000ce10`
- `0x18002c476`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cdf2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cdf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdd9`

## pseudocode

```c
signed int __fastcall STRA::Copy(void **this, const char *Src)
{
  __int64 v4; // rbx
  unsigned __int64 v5; // rcx
  _BYTE *v6; // rax
  signed int result; // eax
  unsigned int v8; // edx

  if ( !Src )
    return -2147024809;
  v4 = -1;
  do
    ++v4;
  while ( Src[v4] );
  v5 = *((unsigned int *)this + 10);
  if ( v5 >= (unsigned __int64)(unsigned int)v4 + 1 )
    goto LABEL_5;
  v8 = v4 + 128;
  if ( (unsigned __int64)(unsigned int)v4 + 128 > 0xFFFFFFFF )
  {
    SetLastError(0x216u);
    return 0;
  }
  if ( v8 <= (unsigned int)v5 || BUFFER::ReallocStorage((BUFFER *)this, v8) )
  {
LABEL_5:
    memcpy_0(this[4], Src, (unsigned int)v4);
    v6 = this[4];
    *((_DWORD *)this + 12) = v4;
    v6[(unsigned int)v4] = 0;
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
0x18000cd40  mov     [rsp+arg_10], rbp
0x18000cd45  push    rdi
0x18000cd46  sub     rsp, 20h
0x18000cd4a  mov     rdi, rdx
0x18000cd4d  mov     rbp, rcx
0x18000cd50  test    rdx, rdx
0x18000cd53  jz      loc_18000CDFA
0x18000cd59  mov     [rsp+28h+arg_0], rbx
0x18000cd5e  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000cd65  mov     [rsp+28h+arg_8], rsi
0x18000cd6a  nop     word ptr [rax+rax+00h]
0x18000cd70  inc     rbx
0x18000cd73  cmp     byte ptr [rdx+rbx], 0
0x18000cd77  jnz     short loc_18000CD70
0x18000cd79  mov     ecx, [rcx+28h]
0x18000cd7c  mov     esi, ebx
0x18000cd7e  lea     rax, [rsi+1]
0x18000cd82  cmp     rcx, rax
0x18000cd85  jb      short loc_18000CDB8
0x18000cd87  mov     rcx, [rbp+20h]; void *
0x18000cd8b  mov     r8, rsi; Size
0x18000cd8e  mov     rdx, rdi; Src
0x18000cd91  call    memcpy_0
0x18000cd96  mov     rax, [rbp+20h]
0x18000cd9a  mov     [rbp+30h], ebx
0x18000cd9d  mov     byte ptr [rsi+rax], 0
0x18000cda1  xor     eax, eax
0x18000cda3  mov     rsi, [rsp+28h+arg_8]
0x18000cda8  mov     rbx, [rsp+28h+arg_0]
0x18000cdad  mov     rbp, [rsp+28h+arg_10]
0x18000cdb2  add     rsp, 20h
0x18000cdb6  pop     rdi
0x18000cdb7  retn
0x18000cdb8  lea     rdx, [rsi+80h]; unsigned int
0x18000cdbf  mov     eax, 0FFFFFFFFh
0x18000cdc4  cmp     rdx, rax
0x18000cdc7  ja      short loc_18000CDED
0x18000cdc9  cmp     edx, ecx
0x18000cdcb  jbe     short loc_18000CD87
0x18000cdcd  mov     rcx, rbp; this
0x18000cdd0  call    ?ReallocStorage@BUFFER@@AEAA_NK@Z; BUFFER::ReallocStorage(ulong)
0x18000cdd5  test    al, al
0x18000cdd7  jnz     short loc_18000CD87
0x18000cdd9  call    cs:__imp_GetLastError
0x18000cddf  test    eax, eax
0x18000cde1  jle     short loc_18000CDA3
0x18000cde3  movzx   eax, ax
0x18000cde6  or      eax, 80070000h
0x18000cdeb  jmp     short loc_18000CDA3
0x18000cded  mov     ecx, 216h; dwErrCode
0x18000cdf2  call    cs:__imp_SetLastError
0x18000cdf8  jmp     short loc_18000CDA1
0x18000cdfa  mov     eax, 80070057h
0x18000cdff  jmp     short loc_18000CDAD
```
