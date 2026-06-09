# std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort,std::char_traits<ushort>> &,ushort const *)

- ea: `0x18001e554`
- end: `0x18001e6c0`
- name: `??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z`
- size: `364`
- prototype: `__int64 *__fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001f1c4`

## callees

- `0x18001e554`
- `0x18001ecb8`
- `0x180023010`

## import_xrefs

- `msvcp_win!?uncaught_exception@std@@YA_NXZ` at `0x18001e676`
- `msvcp_win!?uncaught_exception@std@@YA_NXZ` at `0x18001e676`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x18001e5df`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x18001e62b`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x18001e5df`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x18001e62b`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18001e66f`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18001e66f`
- `msvcp_win!?sputn@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAA_JPEBG_J@Z` at `0x18001e609`
- `msvcp_win!?sputn@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAA_JPEBG_J@Z` at `0x18001e609`
- `msvcp_win!?_Osfx@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAXXZ` at `0x18001e685`
- `msvcp_win!?_Osfx@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAXXZ` at `0x18001e685`

## string_xrefs

- `0x18001e5fd`: `@memorydiagnostic.dll,-`

## pseudocode

```c
__int64 *__fastcall std::operator<<<unsigned short,std::char_traits<unsigned short>>(__int64 *a1)
{
  __int64 *v1; // rdi
  unsigned int v2; // ebx
  __int64 v3; // rsi
  __int64 v4; // rsi
  __int64 v5; // rdx
  __int64 v6; // rax
  __int16 v7; // ax
  __int64 v8; // r8
  __int64 v9; // rcx
  __int64 v11; // [rsp+20h] [rbp-28h] BYREF
  char v12; // [rsp+28h] [rbp-20h]

  v1 = a1;
  v2 = 0;
  v3 = *(__int64 *)((char *)a1 + *(int *)(*a1 + 4) + 40);
  if ( v3 < 24 )
    v4 = 0;
  else
    v4 = v3 - 23;
  std::basic_ostream<unsigned short>::sentry::sentry(&v11, a1);
  if ( v12 )
  {
    v5 = *v1;
    v6 = *(int *)(*v1 + 4);
    if ( (*(_DWORD *)((_BYTE *)v1 + v6 + 24) & 0x1C0) != 0x40 )
    {
      while ( v4 > 0 )
      {
        try
        {
          v7 = std::basic_streambuf<unsigned short>::sputc(
                 *(__int64 *)((char *)v1 + *(int *)(*v1 + 4) + 72),
                 *(unsigned __int16 *)((char *)v1 + *(int *)(*v1 + 4) + 88));
        }
        catch ( ... )
        {
          LOBYTE(v8) = 1;
          std::basic_ios<unsigned short>::setstate((char *)a1 + *(int *)(*a1 + 4), 4, v8);
          v1 = a1;
          v2 = 0;
          goto LABEL_18;
        }
        if ( v7 == -1 )
          goto LABEL_15;
        --v4;
      }
      v5 = *v1;
    }
    if ( std::basic_streambuf<unsigned short>::sputn(
           *(__int64 *)((char *)v1 + *(int *)(v5 + 4) + 72),
           L"@memorydiagnostic.dll,-",
           23) == 23 )
    {
      while ( v4 > 0 )
      {
        if ( (unsigned __int16)std::basic_streambuf<unsigned short>::sputc(
                                 *(__int64 *)((char *)v1 + *(int *)(*v1 + 4) + 72),
                                 *(unsigned __int16 *)((char *)v1 + *(int *)(*v1 + 4) + 88)) == 0xFFFF )
          goto LABEL_15;
        --v4;
      }
    }
    else
    {
LABEL_15:
      v2 = 4;
    }
    *(__int64 *)((char *)v1 + *(int *)(*v1 + 4) + 40) = 0;
  }
  else
  {
    v2 = 4;
  }
LABEL_18:
  std::basic_ios<unsigned short>::setstate((char *)v1 + *(int *)(*v1 + 4), v2, 0);
  if ( !std::uncaught_exception() )
    std::basic_ostream<unsigned short>::_Osfx(v11);
  v9 = *(_QWORD *)(*(int *)(*(_QWORD *)v11 + 4LL) + v11 + 72);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return v1;
}

```

## disassembly

```asm
0x18001e554  mov     [rsp+arg_10], rbx
0x18001e559  mov     [rsp+arg_8], rdx
0x18001e55e  mov     [rsp+arg_0], rcx
0x18001e563  push    rsi
0x18001e564  push    rdi
0x18001e565  push    r14
0x18001e567  sub     rsp, 30h
0x18001e56b  mov     rdi, rcx
0x18001e56e  xor     ebx, ebx
0x18001e570  mov     dword ptr [rsp+48h+arg_8], ebx
0x18001e574  mov     rax, [rcx]
0x18001e577  movsxd  rdx, dword ptr [rax+4]
0x18001e57b  mov     rsi, [rdx+rcx+28h]
0x18001e580  cmp     rsi, 18h
0x18001e584  jl      short loc_18001E58C
0x18001e586  add     rsi, 0FFFFFFFFFFFFFFE9h
0x18001e58a  jmp     short loc_18001E58E
0x18001e58c  xor     esi, esi
0x18001e58e  mov     rdx, rdi
0x18001e591  lea     rcx, [rsp+48h+var_28]
0x18001e596  call    ??0sentry@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAA@AEAV12@@Z; std::basic_ostream<ushort>::sentry::sentry(std::basic_ostream<ushort> &)
0x18001e59b  nop
0x18001e59c  cmp     [rsp+48h+var_20], 0
0x18001e5a1  jnz     short loc_18001E5AD
0x18001e5a3  mov     ebx, 4
0x18001e5a8  jmp     loc_18001E660
0x18001e5ad  mov     rdx, [rdi]
0x18001e5b0  movsxd  rax, dword ptr [rdx+4]
0x18001e5b4  mov     ecx, [rax+rdi+18h]
0x18001e5b8  and     ecx, 1C0h
0x18001e5be  mov     r14d, 0FFFFh
0x18001e5c4  cmp     ecx, 40h ; '@'
0x18001e5c7  jz      short loc_18001E5F3
0x18001e5c9  test    rsi, rsi
0x18001e5cc  jle     short loc_18001E5F0
0x18001e5ce  mov     rax, [rdi]
0x18001e5d1  movsxd  rcx, dword ptr [rax+4]
0x18001e5d5  movzx   edx, word ptr [rcx+rdi+58h]
0x18001e5da  mov     rcx, [rcx+rdi+48h]
0x18001e5df  call    cs:__imp_?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z; std::basic_streambuf<ushort>::sputc(ushort)
0x18001e5e5  cmp     r14w, ax
0x18001e5e9  jz      short loc_18001E637
0x18001e5eb  dec     rsi
0x18001e5ee  jmp     short loc_18001E5C9
0x18001e5f0  mov     rdx, [rdi]
0x18001e5f3  movsxd  rcx, dword ptr [rdx+4]
0x18001e5f7  mov     r8d, 17h
0x18001e5fd  lea     rdx, aMemorydiagnost_0; "@memorydiagnostic.dll,-"
0x18001e604  mov     rcx, [rcx+rdi+48h]
0x18001e609  call    cs:__imp_?sputn@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAA_JPEBG_J@Z; std::basic_streambuf<ushort>::sputn(ushort const *,__int64)
0x18001e60f  cmp     rax, 17h
0x18001e613  jnz     short loc_18001E637
0x18001e615  test    rsi, rsi
0x18001e618  jle     short loc_18001E640
0x18001e61a  mov     rax, [rdi]
0x18001e61d  movsxd  rcx, dword ptr [rax+4]
0x18001e621  movzx   edx, word ptr [rcx+rdi+58h]
0x18001e626  mov     rcx, [rcx+rdi+48h]
0x18001e62b  call    cs:__imp_?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z; std::basic_streambuf<ushort>::sputc(ushort)
0x18001e631  cmp     r14w, ax
0x18001e635  jnz     short loc_18001E652
0x18001e637  mov     ebx, 4
0x18001e63c  mov     dword ptr [rsp+48h+arg_8], ebx
0x18001e640  mov     rax, [rdi]
0x18001e643  movsxd  rcx, dword ptr [rax+4]
0x18001e647  mov     qword ptr [rcx+rdi+28h], 0
0x18001e650  jmp     short loc_18001E660
0x18001e652  dec     rsi
0x18001e655  jmp     short loc_18001E615
0x18001e657  mov     rdi, [rsp+48h+arg_0]
0x18001e65c  mov     ebx, dword ptr [rsp+48h+arg_8]
0x18001e660  mov     rax, [rdi]
0x18001e663  movsxd  rcx, dword ptr [rax+4]
0x18001e667  add     rcx, rdi
0x18001e66a  xor     r8d, r8d
0x18001e66d  mov     edx, ebx
0x18001e66f  call    cs:__imp_?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::setstate(int,bool)
0x18001e675  nop
0x18001e676  call    cs:__imp_?uncaught_exception@std@@YA_NXZ; std::uncaught_exception(void)
0x18001e67c  test    al, al
0x18001e67e  jnz     short loc_18001E68C
0x18001e680  mov     rcx, [rsp+48h+var_28]
0x18001e685  call    cs:__imp_?_Osfx@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAXXZ; std::basic_ostream<ushort>::_Osfx(void)
0x18001e68b  nop
0x18001e68c  mov     rdx, [rsp+48h+var_28]
0x18001e691  mov     rax, [rdx]
0x18001e694  movsxd  rcx, dword ptr [rax+4]
0x18001e698  mov     rcx, [rcx+rdx+48h]
0x18001e69d  test    rcx, rcx
0x18001e6a0  jz      short loc_18001E6AF
0x18001e6a2  mov     rax, [rcx]
0x18001e6a5  mov     rax, [rax+10h]
0x18001e6a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6ae  nop
0x18001e6af  mov     rax, rdi
0x18001e6b2  mov     rbx, [rsp+48h+arg_10]
0x18001e6b7  add     rsp, 30h
0x18001e6bb  pop     r14
0x18001e6bd  pop     rdi
0x18001e6be  pop     rsi
0x18001e6bf  retn
```
