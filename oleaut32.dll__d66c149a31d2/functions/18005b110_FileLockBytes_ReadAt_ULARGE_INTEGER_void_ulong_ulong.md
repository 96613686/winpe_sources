# FileLockBytes::ReadAt(_ULARGE_INTEGER,void *,ulong,ulong *)

- ea: `0x18005b110`
- end: `0x18005b195`
- name: `?ReadAt@FileLockBytes@@UEAAJT_ULARGE_INTEGER@@PEAXKPEAK@Z`
- size: `133`
- prototype: `int(FileLockBytes *__hidden this, union _ULARGE_INTEGER, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18005b110`

## import_xrefs

- `api-ms-win-core-kernel32-private-l1-1-0!_lread` at `0x18005b160`
- `api-ms-win-core-kernel32-private-l1-1-0!_lread` at `0x18005b160`
- `api-ms-win-core-kernel32-private-l1-1-0!_llseek` at `0x18005b142`
- `api-ms-win-core-kernel32-private-l1-1-0!_llseek` at `0x18005b142`

## pseudocode

```c
__int64 __fastcall FileLockBytes::ReadAt(
        FileLockBytes *this,
        union _ULARGE_INTEGER a2,
        void *a3,
        UINT a4,
        unsigned int *a5)
{
  LONG v9; // esi
  UINT v10; // ecx

  if ( !a3 )
    return 2147680265LL;
  v9 = a2.LowPart + *((_DWORD *)this + 4);
  if ( v9 != *((_DWORD *)this + 5) )
  {
    if ( _llseek(*((_DWORD *)this + 3), v9, 0) == -1 )
      return 2147680281LL;
    *((_DWORD *)this + 5) = v9;
  }
  v10 = _lread(*((_DWORD *)this + 3), a3, a4);
  if ( v10 == -1 )
  {
    *((_DWORD *)this + 5) = -1;
    return 2147680286LL;
  }
  else
  {
    *((_DWORD *)this + 5) += v10;
    if ( a5 )
      *a5 = v10;
    return 0;
  }
}

```

## disassembly

```asm
0x18005b110  push    rbx
0x18005b112  push    rbp
0x18005b113  push    rsi
0x18005b114  push    rdi
0x18005b115  push    r14
0x18005b117  sub     rsp, 20h
0x18005b11b  mov     r14d, r9d
0x18005b11e  mov     rbp, r8
0x18005b121  mov     rbx, rcx
0x18005b124  test    r8, r8
0x18005b127  jnz     short loc_18005B130
0x18005b129  mov     eax, 80030009h
0x18005b12e  jmp     short loc_18005B18A
0x18005b130  mov     esi, [rcx+10h]
0x18005b133  add     esi, edx
0x18005b135  cmp     esi, [rcx+14h]
0x18005b138  jz      short loc_18005B157
0x18005b13a  mov     ecx, [rcx+0Ch]; hFile
0x18005b13d  xor     r8d, r8d; iOrigin
0x18005b140  mov     edx, esi; lOffset
0x18005b142  call    cs:__imp__llseek
0x18005b148  cmp     eax, 0FFFFFFFFh
0x18005b14b  jnz     short loc_18005B154
0x18005b14d  mov     eax, 80030019h
0x18005b152  jmp     short loc_18005B18A
0x18005b154  mov     [rbx+14h], esi
0x18005b157  mov     ecx, [rbx+0Ch]; hFile
0x18005b15a  mov     r8d, r14d; uBytes
0x18005b15d  mov     rdx, rbp; lpBuffer
0x18005b160  call    cs:__imp__lread
0x18005b166  mov     ecx, eax
0x18005b168  or      eax, 0FFFFFFFFh
0x18005b16b  cmp     ecx, eax
0x18005b16d  jnz     short loc_18005B179
0x18005b16f  mov     [rbx+14h], eax
0x18005b172  mov     eax, 8003001Eh
0x18005b177  jmp     short loc_18005B18A
0x18005b179  add     [rbx+14h], ecx
0x18005b17c  mov     rax, [rsp+48h+arg_20]
0x18005b181  test    rax, rax
0x18005b184  jz      short loc_18005B188
0x18005b186  mov     [rax], ecx
0x18005b188  xor     eax, eax
0x18005b18a  add     rsp, 20h
0x18005b18e  pop     r14
0x18005b190  pop     rdi
0x18005b191  pop     rsi
0x18005b192  pop     rbp
0x18005b193  pop     rbx
0x18005b194  retn
```
