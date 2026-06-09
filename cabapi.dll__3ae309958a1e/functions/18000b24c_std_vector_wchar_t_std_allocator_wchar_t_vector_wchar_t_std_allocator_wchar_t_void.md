# std::vector<wchar_t,std::allocator<wchar_t>>::~vector<wchar_t,std::allocator<wchar_t>>(void)

- ea: `0x18000b24c`
- end: `0x18000b2b8`
- name: `??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ`
- size: `108`
- prototype: `void __fastcall(char **)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000b34c`
- `0x18000b4c0`
- `0x18000ff98`
- `0x1800104d4`
- `0x18001418c`
- `0x18001419e`

## callees

- `0x180001564`
- `0x18000b24c`

## pseudocode

```c
void __fastcall std::vector<wchar_t>::~vector<wchar_t>(char **a1)
{
  char *v1; // rdx
  unsigned __int64 v3; // rax
  char *v4; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v3 = 2 * ((a1[2] - v1) >> 1);
    if ( v3 < 0x1000 )
    {
      v4 = *a1;
    }
    else
    {
      v4 = (char *)*((_QWORD *)v1 - 1);
      if ( (unsigned __int64)(v1 - v4 - 8) > 0x1F )
        __fastfail(5u);
      v3 += 39LL;
    }
    operator delete(v4, v3);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x18000b24c  push    rbx
0x18000b24e  sub     rsp, 20h
0x18000b252  mov     rdx, [rcx]
0x18000b255  mov     rbx, rcx
0x18000b258  test    rdx, rdx
0x18000b25b  jz      short loc_18000B2B2
0x18000b25d  mov     rax, [rcx+10h]
0x18000b261  sub     rax, rdx
0x18000b264  sar     rax, 1
0x18000b267  add     rax, rax
0x18000b26a  cmp     rax, 1000h
0x18000b270  jb      short loc_18000B290
0x18000b272  mov     rcx, [rdx-8]
0x18000b276  sub     rdx, rcx
0x18000b279  sub     rdx, 8
0x18000b27d  cmp     rdx, 1Fh
0x18000b281  ja      short loc_18000B289
0x18000b283  add     rax, 27h ; '''
0x18000b287  jmp     short loc_18000B293
0x18000b289  mov     ecx, 5
0x18000b28e  int     29h; Win8: RtlFailFast(ecx)
0x18000b290  mov     rcx, rdx; void *
0x18000b293  mov     rdx, rax; unsigned __int64
0x18000b296  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b29b  mov     qword ptr [rbx], 0
0x18000b2a2  mov     qword ptr [rbx+8], 0
0x18000b2aa  mov     qword ptr [rbx+10h], 0
0x18000b2b2  add     rsp, 20h
0x18000b2b6  pop     rbx
0x18000b2b7  retn
```
