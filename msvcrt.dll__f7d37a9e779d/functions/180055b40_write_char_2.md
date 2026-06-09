# write_char_2

- ea: `0x180055b40`
- end: `0x180055b92`
- name: `write_char_2`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180055b98`
- `0x180055c10`
- `0x180059b90`
- `0x18005cd90`

## callees

- `0x1800507b0`
- `0x1800510a4`
- `0x180055b40`

## pseudocode

```c
void __fastcall write_char_2(wchar_t a1, __int64 a2, _DWORD *a3)
{
  if ( (*(_BYTE *)(a2 + 24) & 0x40) == 0 || *(_QWORD *)(a2 + 16) )
  {
    if ( fputwc_nolock(a1, (FILE *)a2) == 0xFFFF && ferror((FILE *)a2) )
      *a3 = -1;
    else
      ++*a3;
  }
  else
  {
    ++*a3;
  }
}

```

## disassembly

```asm
0x180055b40  mov     [rsp+arg_0], rbx
0x180055b45  push    rdi
0x180055b46  sub     rsp, 20h
0x180055b4a  test    byte ptr [rdx+18h], 40h
0x180055b4e  mov     rbx, r8
0x180055b51  mov     rdi, rdx
0x180055b54  jz      short loc_180055B62
0x180055b56  cmp     qword ptr [rdx+10h], 0
0x180055b5b  jnz     short loc_180055B62
0x180055b5d  inc     dword ptr [r8]
0x180055b60  jmp     short loc_180055B87
0x180055b62  call    _fputwc_nolock
0x180055b67  mov     ecx, 0FFFFh
0x180055b6c  cmp     ax, cx
0x180055b6f  jnz     short loc_180055B85
0x180055b71  mov     rcx, rdi; Stream
0x180055b74  call    ferror
0x180055b79  test    eax, eax
0x180055b7b  jz      short loc_180055B85
0x180055b7d  mov     dword ptr [rbx], 0FFFFFFFFh
0x180055b83  jmp     short loc_180055B87
0x180055b85  inc     dword ptr [rbx]
0x180055b87  mov     rbx, [rsp+28h+arg_0]
0x180055b8c  add     rsp, 20h
0x180055b90  pop     rdi
0x180055b91  retn
```
