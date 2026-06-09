# std::basic_stringbuf<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_stringbuf<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x14000e870`
- end: `0x14000e95a`
- name: `??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ`
- size: `234`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000ea98`
- `0x14000eb20`
- `0x14000eb5c`
- `0x14000f0f0`
- `0x140011bb0`

## callees

- `0x140002624`
- `0x14000e870`

## import_xrefs

- `msvcp_win!??1?$basic_streambuf@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x14000e953`

## pseudocode

```c
__int64 __fastcall std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(__int64 a1)
{
  bool v1; // zf
  __int64 v3; // rdx
  __int64 v4; // rdx
  char **v5; // rax
  char *v6; // rcx
  char *v7; // rax

  v1 = (*(_BYTE *)(a1 + 112) & 1) == 0;
  *(_QWORD *)a1 = &std::basic_stringbuf<unsigned short>::`vftable';
  if ( !v1 )
  {
    v3 = **(_QWORD **)(a1 + 64);
    if ( v3 )
      v4 = v3 + 2LL * **(int **)(a1 + 88);
    else
      v4 = **(_QWORD **)(a1 + 56) + 2LL * **(int **)(a1 + 80);
    v5 = *(char ***)(a1 + 24);
    v6 = *v5;
    if ( (unsigned __int64)(2 * ((v4 - (__int64)*v5) >> 1)) < 0x1000 )
    {
      v7 = *v5;
    }
    else
    {
      v7 = (char *)*((_QWORD *)v6 - 1);
      if ( (unsigned __int64)(v6 - v7 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v7);
  }
  **(_QWORD **)(a1 + 24) = 0;
  **(_QWORD **)(a1 + 56) = 0;
  **(_DWORD **)(a1 + 80) = 0;
  **(_QWORD **)(a1 + 32) = 0;
  **(_QWORD **)(a1 + 64) = 0;
  **(_DWORD **)(a1 + 88) = 0;
  *(_DWORD *)(a1 + 112) &= ~1u;
  *(_QWORD *)(a1 + 104) = 0;
  return std::basic_streambuf<unsigned short>::~basic_streambuf<unsigned short,std::char_traits<unsigned short>>(a1);
}

```

## disassembly

```asm
0x14000e870  mov     [rsp+arg_0], rbx
0x14000e875  push    rdi
0x14000e876  sub     rsp, 20h
0x14000e87a  test    byte ptr [rcx+70h], 1
0x14000e87e  lea     rax, ??_7?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringbuf<ushort>::`vftable'
0x14000e885  mov     [rcx], rax
0x14000e888  mov     rbx, rcx
0x14000e88b  jz      short loc_14000E8FA
0x14000e88d  mov     rax, [rcx+40h]
0x14000e891  mov     rdx, [rax]
0x14000e894  test    rdx, rdx
0x14000e897  jz      short loc_14000E8A6
0x14000e899  mov     rax, [rcx+58h]
0x14000e89d  movsxd  rcx, dword ptr [rax]
0x14000e8a0  lea     rdx, [rdx+rcx*2]
0x14000e8a4  jmp     short loc_14000E8B8
0x14000e8a6  mov     rax, [rcx+50h]
0x14000e8aa  movsxd  rdx, dword ptr [rax]
0x14000e8ad  mov     rax, [rcx+38h]
0x14000e8b1  mov     rcx, [rax]
0x14000e8b4  lea     rdx, [rcx+rdx*2]
0x14000e8b8  mov     rax, [rbx+18h]
0x14000e8bc  mov     rcx, [rax]
0x14000e8bf  sub     rdx, rcx
0x14000e8c2  sar     rdx, 1
0x14000e8c5  add     rdx, rdx; unsigned __int64
0x14000e8c8  cmp     rdx, 1000h
0x14000e8cf  jb      short loc_14000E8EF
0x14000e8d1  mov     rax, [rcx-8]
0x14000e8d5  sub     rcx, rax
0x14000e8d8  sub     rcx, 8
0x14000e8dc  cmp     rcx, 1Fh
0x14000e8e0  ja      short loc_14000E8E8
0x14000e8e2  add     rdx, 27h ; '''
0x14000e8e6  jmp     short loc_14000E8F2
0x14000e8e8  mov     ecx, 5
0x14000e8ed  int     29h; Win8: RtlFailFast(ecx)
0x14000e8ef  mov     rax, rcx
0x14000e8f2  mov     rcx, rax; void *
0x14000e8f5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000e8fa  mov     rax, [rbx+18h]
0x14000e8fe  mov     rcx, rbx
0x14000e901  mov     qword ptr [rax], 0
0x14000e908  mov     rax, [rbx+38h]
0x14000e90c  mov     qword ptr [rax], 0
0x14000e913  mov     rax, [rbx+50h]
0x14000e917  mov     dword ptr [rax], 0
0x14000e91d  mov     rax, [rbx+20h]
0x14000e921  mov     qword ptr [rax], 0
0x14000e928  mov     rax, [rbx+40h]
0x14000e92c  mov     qword ptr [rax], 0
0x14000e933  mov     rax, [rbx+58h]
0x14000e937  mov     dword ptr [rax], 0
0x14000e93d  and     dword ptr [rbx+70h], 0FFFFFFFEh
0x14000e941  mov     qword ptr [rbx+68h], 0
0x14000e949  mov     rbx, [rsp+28h+arg_0]
0x14000e94e  add     rsp, 20h
0x14000e952  pop     rdi
0x14000e953  jmp     cs:__imp_??1?$basic_streambuf@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_streambuf<ushort>::~basic_streambuf<ushort,std::char_traits<ushort>>(void)
```
