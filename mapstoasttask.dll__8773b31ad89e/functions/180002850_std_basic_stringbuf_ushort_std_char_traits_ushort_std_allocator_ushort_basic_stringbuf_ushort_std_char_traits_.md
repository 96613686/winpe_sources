# std::basic_stringbuf<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_stringbuf<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180002850`
- end: `0x18000293a`
- name: `??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ`
- size: `234`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002b64`
- `0x180002c24`
- `0x180002cb0`
- `0x1800044a8`

## callees

- `0x180001624`
- `0x180002850`

## import_xrefs

- `msvcp_win!??1?$basic_streambuf@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180002933`

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
0x180002850  mov     [rsp+arg_0], rbx
0x180002855  push    rdi
0x180002856  sub     rsp, 20h
0x18000285a  test    byte ptr [rcx+70h], 1
0x18000285e  lea     rax, ??_7?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringbuf<ushort>::`vftable'
0x180002865  mov     [rcx], rax
0x180002868  mov     rbx, rcx
0x18000286b  jz      short loc_1800028DA
0x18000286d  mov     rax, [rcx+40h]
0x180002871  mov     rdx, [rax]
0x180002874  test    rdx, rdx
0x180002877  jz      short loc_180002886
0x180002879  mov     rax, [rcx+58h]
0x18000287d  movsxd  rcx, dword ptr [rax]
0x180002880  lea     rdx, [rdx+rcx*2]
0x180002884  jmp     short loc_180002898
0x180002886  mov     rax, [rcx+50h]
0x18000288a  movsxd  rdx, dword ptr [rax]
0x18000288d  mov     rax, [rcx+38h]
0x180002891  mov     rcx, [rax]
0x180002894  lea     rdx, [rcx+rdx*2]
0x180002898  mov     rax, [rbx+18h]
0x18000289c  mov     rcx, [rax]
0x18000289f  sub     rdx, rcx
0x1800028a2  sar     rdx, 1
0x1800028a5  add     rdx, rdx
0x1800028a8  cmp     rdx, 1000h
0x1800028af  jb      short loc_1800028CF
0x1800028b1  mov     rax, [rcx-8]
0x1800028b5  sub     rcx, rax
0x1800028b8  sub     rcx, 8
0x1800028bc  cmp     rcx, 1Fh
0x1800028c0  ja      short loc_1800028C8
0x1800028c2  add     rdx, 27h ; '''
0x1800028c6  jmp     short loc_1800028D2
0x1800028c8  mov     ecx, 5
0x1800028cd  int     29h; Win8: RtlFailFast(ecx)
0x1800028cf  mov     rax, rcx
0x1800028d2  mov     rcx, rax; Block
0x1800028d5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800028da  mov     rax, [rbx+18h]
0x1800028de  mov     rcx, rbx
0x1800028e1  mov     qword ptr [rax], 0
0x1800028e8  mov     rax, [rbx+38h]
0x1800028ec  mov     qword ptr [rax], 0
0x1800028f3  mov     rax, [rbx+50h]
0x1800028f7  mov     dword ptr [rax], 0
0x1800028fd  mov     rax, [rbx+20h]
0x180002901  mov     qword ptr [rax], 0
0x180002908  mov     rax, [rbx+40h]
0x18000290c  mov     qword ptr [rax], 0
0x180002913  mov     rax, [rbx+58h]
0x180002917  mov     dword ptr [rax], 0
0x18000291d  and     dword ptr [rbx+70h], 0FFFFFFFEh
0x180002921  mov     qword ptr [rbx+68h], 0
0x180002929  mov     rbx, [rsp+28h+arg_0]
0x18000292e  add     rsp, 20h
0x180002932  pop     rdi
0x180002933  jmp     cs:__imp_??1?$basic_streambuf@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_streambuf<ushort>::~basic_streambuf<ushort,std::char_traits<ushort>>(void)
```
