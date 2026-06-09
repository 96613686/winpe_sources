# write_multi_char

- ea: `0x18004065c`
- end: `0x1800406a8`
- name: `write_multi_char`
- size: `76`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800407b0`
- `0x1800412f0`
- `0x180042500`

## callees

- `0x180021a24`
- `0x18004065c`

## pseudocode

```c
void __fastcall write_multi_char(char a1, int a2, _DWORD *a3)
{
  int v4; // esi
  int v5; // edi

  if ( a2 > 0 )
  {
    v4 = a1;
    v5 = a2;
    while ( putch_nolock(v4) != -1 )
    {
      if ( ++*a3 != -1 && --v5 > 0 )
        continue;
      return;
    }
    *a3 = -1;
  }
}

```

## disassembly

```asm
0x18004065c  test    edx, edx
0x18004065e  jle     short locret_1800406A7
0x180040660  mov     [rsp+arg_0], rbx
0x180040665  mov     [rsp+arg_8], rsi
0x18004066a  push    rdi
0x18004066b  sub     rsp, 20h
0x18004066f  mov     rbx, r8
0x180040672  movsx   esi, cl
0x180040675  mov     edi, edx
0x180040677  mov     ecx, esi; Ch
0x180040679  call    _putch_nolock
0x18004067e  cmp     eax, 0FFFFFFFFh
0x180040681  jz      short loc_180040692
0x180040683  inc     dword ptr [rbx]
0x180040685  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180040688  jz      short loc_180040698
0x18004068a  dec     edi
0x18004068c  test    edi, edi
0x18004068e  jg      short loc_180040677
0x180040690  jmp     short loc_180040698
0x180040692  mov     dword ptr [rbx], 0FFFFFFFFh
0x180040698  mov     rbx, [rsp+28h+arg_0]
0x18004069d  mov     rsi, [rsp+28h+arg_8]
0x1800406a2  add     rsp, 20h
0x1800406a6  pop     rdi
0x1800406a7  retn
```
