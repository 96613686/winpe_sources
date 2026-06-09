# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::operator=(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &&)

- ea: `0x180008414`
- end: `0x1800084ad`
- name: `??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `153`
- prototype: `char **__fastcall(char **, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180008d80`
- `0x180008fd8`
- `0x18000bcac`
- `0x180010124`
- `0x1800104d4`

## callees

- `0x180001564`
- `0x180008414`

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
0x180008414  mov     [rsp+arg_10], rbx
0x180008419  push    rdi
0x18000841a  sub     rsp, 20h
0x18000841e  mov     rdi, rdx
0x180008421  mov     rbx, rcx
0x180008424  cmp     rcx, rdx
0x180008427  jz      short loc_18000849F
0x180008429  mov     rdx, [rcx+18h]
0x18000842d  cmp     rdx, 7
0x180008431  jbe     short loc_18000846D
0x180008433  mov     rax, [rcx]
0x180008436  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x18000843e  cmp     rdx, 1000h
0x180008445  jb      short loc_180008465
0x180008447  mov     rcx, [rax-8]
0x18000844b  sub     rax, rcx
0x18000844e  sub     rax, 8
0x180008452  cmp     rax, 1Fh
0x180008456  ja      short loc_18000845E
0x180008458  add     rdx, 27h ; '''
0x18000845c  jmp     short loc_180008468
0x18000845e  mov     ecx, 5
0x180008463  int     29h; Win8: RtlFailFast(ecx)
0x180008465  mov     rcx, rax; void *
0x180008468  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000846d  mov     qword ptr [rbx+10h], 0
0x180008475  xor     eax, eax
0x180008477  mov     [rbx], ax
0x18000847a  mov     qword ptr [rbx+18h], 7
0x180008482  movups  xmm0, xmmword ptr [rdi]
0x180008485  movups  xmmword ptr [rbx], xmm0
0x180008488  movups  xmm1, xmmword ptr [rdi+10h]
0x18000848c  movups  xmmword ptr [rbx+10h], xmm1
0x180008490  mov     [rdi+10h], rax
0x180008494  mov     qword ptr [rdi+18h], 7
0x18000849c  mov     [rdi], ax
0x18000849f  mov     rax, rbx
0x1800084a2  mov     rbx, [rsp+28h+arg_10]
0x1800084a7  add     rsp, 20h
0x1800084ab  pop     rdi
0x1800084ac  retn
```
