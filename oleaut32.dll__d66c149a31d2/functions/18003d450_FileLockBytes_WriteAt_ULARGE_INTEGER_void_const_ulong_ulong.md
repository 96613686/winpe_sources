# FileLockBytes::WriteAt(_ULARGE_INTEGER,void const *,ulong,ulong *)

- ea: `0x18003d450`
- end: `0x18003d4c7`
- name: `?WriteAt@FileLockBytes@@UEAAJT_ULARGE_INTEGER@@PEBXKPEAK@Z`
- size: `119`
- prototype: `int(FileLockBytes *__hidden this, union _ULARGE_INTEGER, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18003d450`

## import_xrefs

- `api-ms-win-core-kernel32-private-l1-1-0!_lwrite` at `0x18003d475`
- `api-ms-win-core-kernel32-private-l1-1-0!_lwrite` at `0x18003d475`
- `api-ms-win-core-kernel32-private-l1-1-0!_llseek` at `0x18003d4b0`
- `api-ms-win-core-kernel32-private-l1-1-0!_llseek` at `0x18003d4b0`

## pseudocode

```c
__int64 __fastcall FileLockBytes::WriteAt(
        FileLockBytes *this,
        union _ULARGE_INTEGER a2,
        const CHAR *a3,
        UINT a4,
        unsigned int *a5)
{
  DWORD LowPart; // ebx
  UINT v9; // ecx

  LowPart = a2.LowPart;
  if ( a2.LowPart != *((_DWORD *)this + 5) )
  {
    if ( _llseek(*((_DWORD *)this + 3), a2.LowPart, 0) == -1 )
      return 2147680281LL;
    *((_DWORD *)this + 5) = LowPart;
  }
  v9 = _lwrite(*((_DWORD *)this + 3), a3, a4);
  if ( v9 == -1 )
  {
    *((_DWORD *)this + 5) = -1;
    return 2147680285LL;
  }
  else
  {
    *((_DWORD *)this + 5) += v9;
    if ( a5 )
      *a5 = v9;
    return 0;
  }
}

```

## disassembly

```asm
0x18003d450  push    rbx
0x18003d452  push    rbp
0x18003d453  push    rsi
0x18003d454  push    rdi
0x18003d455  push    r14
0x18003d457  sub     rsp, 20h
0x18003d45b  mov     ebp, r9d
0x18003d45e  mov     r14, r8
0x18003d461  mov     rbx, rdx
0x18003d464  mov     rdi, rcx
0x18003d467  cmp     edx, [rcx+14h]
0x18003d46a  jnz     short loc_18003D4AA
0x18003d46c  mov     ecx, [rdi+0Ch]; hFile
0x18003d46f  mov     r8d, ebp; uBytes
0x18003d472  mov     rdx, r14; lpBuffer
0x18003d475  call    cs:__imp__lwrite
0x18003d47b  mov     ecx, eax
0x18003d47d  or      eax, 0FFFFFFFFh
0x18003d480  cmp     ecx, eax
0x18003d482  jz      short loc_18003D4A0
0x18003d484  add     [rdi+14h], ecx
0x18003d487  mov     rax, [rsp+48h+arg_20]
0x18003d48c  test    rax, rax
0x18003d48f  jz      short loc_18003D493
0x18003d491  mov     [rax], ecx
0x18003d493  xor     eax, eax
0x18003d495  add     rsp, 20h
0x18003d499  pop     r14
0x18003d49b  pop     rdi
0x18003d49c  pop     rsi
0x18003d49d  pop     rbp
0x18003d49e  pop     rbx
0x18003d49f  retn
0x18003d4a0  mov     [rdi+14h], eax
0x18003d4a3  mov     eax, 8003001Dh
0x18003d4a8  jmp     short loc_18003D495
0x18003d4aa  mov     ecx, [rcx+0Ch]; hFile
0x18003d4ad  xor     r8d, r8d; iOrigin
0x18003d4b0  call    cs:__imp__llseek
0x18003d4b6  cmp     eax, 0FFFFFFFFh
0x18003d4b9  jnz     short loc_18003D4C2
0x18003d4bb  mov     eax, 80030019h
0x18003d4c0  jmp     short loc_18003D495
0x18003d4c2  mov     [rdi+14h], ebx
0x18003d4c5  jmp     short loc_18003D46C
```
