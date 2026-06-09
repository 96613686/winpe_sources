# std::vector<gsl::byte,std::allocator<gsl::byte>>::~vector<gsl::byte,std::allocator<gsl::byte>>(void)

- ea: `0x1400057fc`
- end: `0x140005860`
- name: `??1?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(char **)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140005868`
- `0x140007c84`
- `0x14000c929`

## callees

- `0x140001cb8`
- `0x1400057fc`

## pseudocode

```c
void __fastcall std::vector<enum gsl::byte>::~vector<enum gsl::byte>(char **a1)
{
  char *v1; // rax
  const struct std::nothrow_t *v3; // rdx
  char *v4; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v3 = (const struct std::nothrow_t *)(a1[2] - v1);
    if ( (unsigned __int64)v3 < 0x1000 )
    {
      v4 = *a1;
    }
    else
    {
      v4 = (char *)*((_QWORD *)v1 - 1);
      if ( (unsigned __int64)(v1 - v4 - 8) > 0x1F )
        __fastfail(5u);
      v3 = (const struct std::nothrow_t *)((char *)v3 + 39);
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
0x1400057fc  push    rbx
0x1400057fe  sub     rsp, 20h
0x140005802  mov     rax, [rcx]
0x140005805  mov     rbx, rcx
0x140005808  test    rax, rax
0x14000580b  jz      short loc_14000585A
0x14000580d  mov     rdx, [rcx+10h]
0x140005811  sub     rdx, rax; struct std::nothrow_t *
0x140005814  cmp     rdx, 1000h
0x14000581b  jb      short loc_14000583B
0x14000581d  mov     rcx, [rax-8]
0x140005821  sub     rax, rcx
0x140005824  sub     rax, 8
0x140005828  cmp     rax, 1Fh
0x14000582c  ja      short loc_140005834
0x14000582e  add     rdx, 27h ; '''
0x140005832  jmp     short loc_14000583E
0x140005834  mov     ecx, 5
0x140005839  int     29h; Win8: RtlFailFast(ecx)
0x14000583b  mov     rcx, rax; void *
0x14000583e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140005843  mov     qword ptr [rbx], 0
0x14000584a  mov     qword ptr [rbx+8], 0
0x140005852  mov     qword ptr [rbx+10h], 0
0x14000585a  add     rsp, 20h
0x14000585e  pop     rbx
0x14000585f  retn
```
