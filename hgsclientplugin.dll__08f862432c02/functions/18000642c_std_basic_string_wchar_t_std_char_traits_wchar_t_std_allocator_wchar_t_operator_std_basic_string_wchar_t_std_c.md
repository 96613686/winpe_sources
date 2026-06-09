# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::operator=(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &&)

- ea: `0x18000642c`
- end: `0x1800064c5`
- name: `??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `153`
- prototype: `char **__fastcall(char **, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180006060`
- `0x1800065c0`
- `0x1800088cc`

## callees

- `0x1800018f0`
- `0x18000642c`

## pseudocode

```c
char **__fastcall std::wstring::operator=(char **a1, __int64 a2)
{
  unsigned __int64 v4; // rdx
  char *v5; // rax
  char *v6; // rcx

  if ( a1 != (char **)a2 )
  {
    v4 = (unsigned __int64)a1[3];
    if ( v4 > 7 )
    {
      v5 = *a1;
      if ( 2 * v4 + 2 < 0x1000 )
      {
        v6 = *a1;
      }
      else
      {
        v6 = (char *)*((_QWORD *)v5 - 1);
        if ( (unsigned __int64)(v5 - v6 - 8) > 0x1F )
          __fastfail(5u);
      }
      operator delete(v6);
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
0x18000642c  mov     [rsp+arg_0], rbx
0x180006431  push    rdi
0x180006432  sub     rsp, 20h
0x180006436  mov     rdi, rdx
0x180006439  mov     rbx, rcx
0x18000643c  cmp     rcx, rdx
0x18000643f  jz      short loc_1800064B7
0x180006441  mov     rdx, [rcx+18h]
0x180006445  cmp     rdx, 7
0x180006449  jbe     short loc_180006485
0x18000644b  mov     rax, [rcx]
0x18000644e  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180006456  cmp     rdx, 1000h
0x18000645d  jb      short loc_18000647D
0x18000645f  mov     rcx, [rax-8]
0x180006463  sub     rax, rcx
0x180006466  sub     rax, 8
0x18000646a  cmp     rax, 1Fh
0x18000646e  ja      short loc_180006476
0x180006470  add     rdx, 27h ; '''
0x180006474  jmp     short loc_180006480
0x180006476  mov     ecx, 5
0x18000647b  int     29h; Win8: RtlFailFast(ecx)
0x18000647d  mov     rcx, rax; void *
0x180006480  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006485  mov     qword ptr [rbx+10h], 0
0x18000648d  xor     eax, eax
0x18000648f  mov     [rbx], ax
0x180006492  mov     qword ptr [rbx+18h], 7
0x18000649a  movups  xmm0, xmmword ptr [rdi]
0x18000649d  movups  xmmword ptr [rbx], xmm0
0x1800064a0  movups  xmm1, xmmword ptr [rdi+10h]
0x1800064a4  movups  xmmword ptr [rbx+10h], xmm1
0x1800064a8  mov     [rdi+10h], rax
0x1800064ac  mov     qword ptr [rdi+18h], 7
0x1800064b4  mov     [rdi], ax
0x1800064b7  mov     rax, rbx
0x1800064ba  mov     rbx, [rsp+28h+arg_0]
0x1800064bf  add     rsp, 20h
0x1800064c3  pop     rdi
0x1800064c4  retn
```
