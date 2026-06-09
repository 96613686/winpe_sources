# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::operator=(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&)

- ea: `0x140005a04`
- end: `0x140005a9d`
- name: `??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `153`
- prototype: `char **__fastcall(char **, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000d124`
- `0x14000de70`
- `0x14000df20`
- `0x14000e3b8`
- `0x14000e828`
- `0x14000eeb8`
- `0x14000f8d0`

## callees

- `0x1400021b4`
- `0x140005a04`

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
0x140005a04  mov     [rsp+arg_0], rbx
0x140005a09  push    rdi
0x140005a0a  sub     rsp, 20h
0x140005a0e  mov     rdi, rdx
0x140005a11  mov     rbx, rcx
0x140005a14  cmp     rcx, rdx
0x140005a17  jz      short loc_140005A8F
0x140005a19  mov     rdx, [rcx+18h]
0x140005a1d  cmp     rdx, 7
0x140005a21  jbe     short loc_140005A5D
0x140005a23  mov     rax, [rcx]
0x140005a26  lea     rdx, ds:2[rdx*2]
0x140005a2e  cmp     rdx, 1000h
0x140005a35  jb      short loc_140005A55
0x140005a37  mov     rcx, [rax-8]
0x140005a3b  sub     rax, rcx
0x140005a3e  sub     rax, 8
0x140005a42  cmp     rax, 1Fh
0x140005a46  ja      short loc_140005A4E
0x140005a48  add     rdx, 27h ; '''
0x140005a4c  jmp     short loc_140005A58
0x140005a4e  mov     ecx, 5
0x140005a53  int     29h; Win8: RtlFailFast(ecx)
0x140005a55  mov     rcx, rax; Block
0x140005a58  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140005a5d  mov     qword ptr [rbx+10h], 0
0x140005a65  xor     eax, eax
0x140005a67  mov     [rbx], ax
0x140005a6a  mov     qword ptr [rbx+18h], 7
0x140005a72  movups  xmm0, xmmword ptr [rdi]
0x140005a75  movups  xmmword ptr [rbx], xmm0
0x140005a78  movups  xmm1, xmmword ptr [rdi+10h]
0x140005a7c  movups  xmmword ptr [rbx+10h], xmm1
0x140005a80  mov     [rdi+10h], rax
0x140005a84  mov     qword ptr [rdi+18h], 7
0x140005a8c  mov     [rdi], ax
0x140005a8f  mov     rax, rbx
0x140005a92  mov     rbx, [rsp+28h+arg_0]
0x140005a97  add     rsp, 20h
0x140005a9b  pop     rdi
0x140005a9c  retn
```
