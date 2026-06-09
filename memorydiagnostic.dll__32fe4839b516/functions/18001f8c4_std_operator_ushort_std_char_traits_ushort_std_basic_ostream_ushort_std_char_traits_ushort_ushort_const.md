# std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort,std::char_traits<ushort>> &,ushort const *)

- ea: `0x18001f8c4`
- end: `0x18001fa56`
- name: `??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002061c`

## callees

- `0x18001f8c4`
- `0x1800200b8`
- `0x180024010`

## import_xrefs

- `msvcp_win!?sputn@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAA_JPEBG_J@Z` at `0x18001f985`
- `msvcp_win!?sputn@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAA_JPEBG_J@Z` at `0x18001f985`
- `msvcp_win!?uncaught_exception@std@@YA_NXZ` at `0x18001f9ff`
- `msvcp_win!?uncaught_exception@std@@YA_NXZ` at `0x18001f9ff`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18001f9f2`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18001f9f2`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x18001f94e`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x18001f9ad`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x18001f94e`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x18001f9ad`
- `msvcp_win!?_Osfx@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAXXZ` at `0x18001fa14`
- `msvcp_win!?_Osfx@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAXXZ` at `0x18001fa14`

## string_xrefs

- `0x18001f979`: `@memorydiagnostic.dll,-`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::operator<<<unsigned short,std::char_traits<unsigned short>>(__int64 a1)
{
  __int64 v1; // rdi
  unsigned int v2; // ebx
  __int64 v3; // rsi
  __int64 v4; // rsi
  int v5; // eax
  __int16 v6; // ax
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v10; // [rsp+20h] [rbp-28h] BYREF
  char v11; // [rsp+28h] [rbp-20h]

  v1 = a1;
  v2 = 0;
  v3 = *(_QWORD *)(*(int *)(*(_QWORD *)a1 + 4LL) + a1 + 40);
  if ( v3 < 24 )
    v4 = 0;
  else
    v4 = v3 - 23;
  std::basic_ostream<unsigned short>::sentry::sentry(&v10, a1);
  if ( v11 )
  {
    v5 = *(_DWORD *)(*(int *)(*(_QWORD *)v1 + 4LL) + v1 + 24) & 0x1C0;
    if ( v5 != 64 )
    {
      while ( v4 > 0 )
      {
        try
        {
          v6 = std::basic_streambuf<unsigned short>::sputc(
                 *(_QWORD *)(*(int *)(*(_QWORD *)v1 + 4LL) + v1 + 72),
                 *(unsigned __int16 *)(*(int *)(*(_QWORD *)v1 + 4LL) + v1 + 88));
        }
        catch ( ... )
        {
          LOBYTE(v7) = 1;
          std::basic_ios<unsigned short>::setstate(a1 + *(int *)(*(_QWORD *)a1 + 4LL), 4, v7);
          v1 = a1;
          v2 = 0;
          goto LABEL_18;
        }
        if ( v6 == -1 )
        {
          v2 = 4;
          goto LABEL_16;
        }
        --v4;
      }
    }
    if ( std::basic_streambuf<unsigned short>::sputn(
           *(_QWORD *)(*(int *)(*(_QWORD *)v1 + 4LL) + v1 + 72),
           L"@memorydiagnostic.dll,-",
           23) == 23 )
    {
      while ( v4 > 0 )
      {
        if ( (unsigned __int16)std::basic_streambuf<unsigned short>::sputc(
                                 *(_QWORD *)(*(int *)(*(_QWORD *)v1 + 4LL) + v1 + 72),
                                 *(unsigned __int16 *)(*(int *)(*(_QWORD *)v1 + 4LL) + v1 + 88)) == 0xFFFF )
          goto LABEL_15;
        --v4;
      }
    }
    else
    {
LABEL_15:
      v2 = 4;
    }
LABEL_16:
    *(_QWORD *)(*(int *)(*(_QWORD *)v1 + 4LL) + v1 + 40) = 0;
  }
  else
  {
    v2 = 4;
  }
LABEL_18:
  std::basic_ios<unsigned short>::setstate(v1 + *(int *)(*(_QWORD *)v1 + 4LL), v2, 0);
  if ( !std::uncaught_exception() )
    std::basic_ostream<unsigned short>::_Osfx(v10);
  v8 = *(_QWORD *)(*(int *)(*(_QWORD *)v10 + 4LL) + v10 + 72);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return v1;
}

```

## disassembly

```asm
0x18001f8c4  mov     [rsp+arg_10], rbx
0x18001f8c9  mov     [rsp+arg_8], rdx
0x18001f8ce  mov     [rsp+arg_0], rcx
0x18001f8d3  push    rsi
0x18001f8d4  push    rdi
0x18001f8d5  push    r14
0x18001f8d7  sub     rsp, 30h
0x18001f8db  mov     rdi, rcx
0x18001f8de  xor     ebx, ebx
0x18001f8e0  mov     dword ptr [rsp+48h+arg_8], ebx
0x18001f8e4  mov     rax, [rcx]
0x18001f8e7  movsxd  rdx, dword ptr [rax+4]
0x18001f8eb  mov     rsi, [rdx+rcx+28h]
0x18001f8f0  cmp     rsi, 18h
0x18001f8f4  jl      short loc_18001F8FC
0x18001f8f6  add     rsi, 0FFFFFFFFFFFFFFE9h
0x18001f8fa  jmp     short loc_18001F8FE
0x18001f8fc  xor     esi, esi
0x18001f8fe  mov     rdx, rdi
0x18001f901  lea     rcx, [rsp+48h+var_28]
0x18001f906  call    ??0sentry@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAA@AEAV12@@Z; std::basic_ostream<ushort>::sentry::sentry(std::basic_ostream<ushort> &)
0x18001f90b  nop
0x18001f90c  cmp     [rsp+48h+var_20], 0
0x18001f911  jnz     short loc_18001F91D
0x18001f913  mov     ebx, 4
0x18001f918  jmp     loc_18001F9E3
0x18001f91d  mov     rax, [rdi]
0x18001f920  movsxd  rcx, dword ptr [rax+4]
0x18001f924  mov     eax, [rcx+rdi+18h]
0x18001f928  and     eax, 1C0h
0x18001f92d  mov     r14d, 0FFFFh
0x18001f933  cmp     eax, 40h ; '@'
0x18001f936  jz      short loc_18001F96C
0x18001f938  test    rsi, rsi
0x18001f93b  jle     short loc_18001F96C
0x18001f93d  mov     rax, [rdi]
0x18001f940  movsxd  rcx, dword ptr [rax+4]
0x18001f944  movzx   edx, word ptr [rcx+rdi+58h]
0x18001f949  mov     rcx, [rcx+rdi+48h]
0x18001f94e  call    cs:__imp_?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z; std::basic_streambuf<ushort>::sputc(ushort)
0x18001f955  nop     dword ptr [rax+rax+00h]
0x18001f95a  cmp     r14w, ax
0x18001f95e  jnz     short loc_18001F967
0x18001f960  mov     ebx, 4
0x18001f965  jmp     short loc_18001F9C2
0x18001f967  dec     rsi
0x18001f96a  jmp     short loc_18001F938
0x18001f96c  mov     rax, [rdi]
0x18001f96f  movsxd  rcx, dword ptr [rax+4]
0x18001f973  mov     r8d, 17h
0x18001f979  lea     rdx, aMemorydiagnost_0; "@memorydiagnostic.dll,-"
0x18001f980  mov     rcx, [rcx+rdi+48h]
0x18001f985  call    cs:__imp_?sputn@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAA_JPEBG_J@Z; std::basic_streambuf<ushort>::sputn(ushort const *,__int64)
0x18001f98c  nop     dword ptr [rax+rax+00h]
0x18001f991  cmp     rax, 17h
0x18001f995  jnz     short loc_18001F9BF
0x18001f997  test    rsi, rsi
0x18001f99a  jle     short loc_18001F9C6
0x18001f99c  mov     rax, [rdi]
0x18001f99f  movsxd  rcx, dword ptr [rax+4]
0x18001f9a3  movzx   edx, word ptr [rcx+rdi+58h]
0x18001f9a8  mov     rcx, [rcx+rdi+48h]
0x18001f9ad  call    cs:__imp_?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z; std::basic_streambuf<ushort>::sputc(ushort)
0x18001f9b4  nop     dword ptr [rax+rax+00h]
0x18001f9b9  cmp     r14w, ax
0x18001f9bd  jnz     short loc_18001F9D5
0x18001f9bf  or      ebx, 4
0x18001f9c2  mov     dword ptr [rsp+48h+arg_8], ebx
0x18001f9c6  mov     rax, [rdi]
0x18001f9c9  movsxd  rcx, dword ptr [rax+4]
0x18001f9cd  and     qword ptr [rcx+rdi+28h], 0
0x18001f9d3  jmp     short loc_18001F9E3
0x18001f9d5  dec     rsi
0x18001f9d8  jmp     short loc_18001F997
0x18001f9da  mov     rdi, [rsp+48h+arg_0]
0x18001f9df  mov     ebx, dword ptr [rsp+48h+arg_8]
0x18001f9e3  mov     rax, [rdi]
0x18001f9e6  movsxd  rcx, dword ptr [rax+4]
0x18001f9ea  add     rcx, rdi
0x18001f9ed  xor     r8d, r8d
0x18001f9f0  mov     edx, ebx
0x18001f9f2  call    cs:__imp_?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::setstate(int,bool)
0x18001f9f9  nop     dword ptr [rax+rax+00h]
0x18001f9fe  nop
0x18001f9ff  call    cs:__imp_?uncaught_exception@std@@YA_NXZ; std::uncaught_exception(void)
0x18001fa06  nop     dword ptr [rax+rax+00h]
0x18001fa0b  test    al, al
0x18001fa0d  jnz     short loc_18001FA21
0x18001fa0f  mov     rcx, [rsp+48h+var_28]
0x18001fa14  call    cs:__imp_?_Osfx@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAXXZ; std::basic_ostream<ushort>::_Osfx(void)
0x18001fa1b  nop     dword ptr [rax+rax+00h]
0x18001fa20  nop
0x18001fa21  mov     rcx, [rsp+48h+var_28]
0x18001fa26  mov     rax, [rcx]
0x18001fa29  movsxd  rdx, dword ptr [rax+4]
0x18001fa2d  mov     rcx, [rdx+rcx+48h]
0x18001fa32  test    rcx, rcx
0x18001fa35  jz      short loc_18001FA44
0x18001fa37  mov     rax, [rcx]
0x18001fa3a  mov     rax, [rax+10h]
0x18001fa3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa43  nop
0x18001fa44  mov     rax, rdi
0x18001fa47  mov     rbx, [rsp+48h+arg_10]
0x18001fa4c  add     rsp, 30h
0x18001fa50  pop     r14
0x18001fa52  pop     rdi
0x18001fa53  pop     rsi
0x18001fa54  retn
```
