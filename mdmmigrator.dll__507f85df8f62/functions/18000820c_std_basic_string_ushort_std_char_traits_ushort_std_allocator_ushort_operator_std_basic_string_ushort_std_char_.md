# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::operator=(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&)

- ea: `0x18000820c`
- end: `0x1800082a5`
- name: `??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `153`
- prototype: `char **__fastcall(char **, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180008520`
- `0x18000de8c`
- `0x18000e284`
- `0x18000eae0`
- `0x180010170`

## callees

- `0x1800026b0`
- `0x18000820c`

## pseudocode

```c
char **__fastcall std::wstring::operator=(char **a1, __int64 a2)
{
  unsigned __int64 v4; // rdx
  char *v5; // rax
  const struct std::nothrow_t *v6; // rdx
  char *v7; // rcx

  if ( a1 != (char **)a2 )
  {
    v4 = (unsigned __int64)a1[3];
    if ( v4 > 7 )
    {
      v5 = *a1;
      v6 = (const struct std::nothrow_t *)(2 * v4 + 2);
      if ( (unsigned __int64)v6 < 0x1000 )
      {
        v7 = *a1;
      }
      else
      {
        v7 = (char *)*((_QWORD *)v5 - 1);
        if ( (unsigned __int64)(v5 - v7 - 8) > 0x1F )
          __fastfail(5u);
        v6 = (const struct std::nothrow_t *)((char *)v6 + 39);
      }
      operator delete(v7, v6);
    }
    a1[2] = 0;
    *(_WORD *)a1 = 0;
    a1[3] = (char *)7;
    *(_OWORD *)a1 = *(_OWORD *)a2;
    *((_OWORD *)a1 + 1) = *(_OWORD *)(a2 + 16);
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 7;
    *(_WORD *)a2 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18000820c  mov     [rsp+arg_0], rbx
0x180008211  push    rdi
0x180008212  sub     rsp, 20h
0x180008216  mov     rdi, rdx
0x180008219  mov     rbx, rcx
0x18000821c  cmp     rcx, rdx
0x18000821f  jz      short loc_180008297
0x180008221  mov     rdx, [rcx+18h]
0x180008225  cmp     rdx, 7
0x180008229  jbe     short loc_180008265
0x18000822b  mov     rax, [rcx]
0x18000822e  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x180008236  cmp     rdx, 1000h
0x18000823d  jb      short loc_18000825D
0x18000823f  mov     rcx, [rax-8]
0x180008243  sub     rax, rcx
0x180008246  sub     rax, 8
0x18000824a  cmp     rax, 1Fh
0x18000824e  ja      short loc_180008256
0x180008250  add     rdx, 27h ; '''
0x180008254  jmp     short loc_180008260
0x180008256  mov     ecx, 5
0x18000825b  int     29h; Win8: RtlFailFast(ecx)
0x18000825d  mov     rcx, rax; void *
0x180008260  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008265  mov     qword ptr [rbx+10h], 0
0x18000826d  xor     eax, eax
0x18000826f  mov     [rbx], ax
0x180008272  mov     qword ptr [rbx+18h], 7
0x18000827a  movups  xmm0, xmmword ptr [rdi]
0x18000827d  movups  xmmword ptr [rbx], xmm0
0x180008280  movups  xmm1, xmmword ptr [rdi+10h]
0x180008284  movups  xmmword ptr [rbx+10h], xmm1
0x180008288  mov     [rdi+10h], rax
0x18000828c  mov     qword ptr [rdi+18h], 7
0x180008294  mov     [rdi], ax
0x180008297  mov     rax, rbx
0x18000829a  mov     rbx, [rsp+28h+arg_0]
0x18000829f  add     rsp, 20h
0x1800082a3  pop     rdi
0x1800082a4  retn
```
