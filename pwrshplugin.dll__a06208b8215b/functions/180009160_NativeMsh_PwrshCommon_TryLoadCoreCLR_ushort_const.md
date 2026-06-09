# NativeMsh::PwrshCommon::TryLoadCoreCLR(ushort const *)

- ea: `0x180009160`
- end: `0x180009259`
- name: `?TryLoadCoreCLR@PwrshCommon@NativeMsh@@MEAAPEAUHINSTANCE__@@PEBG@Z`
- size: `249`
- prototype: `__int64 __fastcall(NativeMsh::PwrshCommon *this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180006100`
- `0x180007818`
- `0x180009160`
- `0x1800096b0`
- `0x18000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000921d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009232`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000921d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009232`

## string_xrefs

- `0x1800091a3`: `CoreCLR.dll`

## pseudocode

```c
__int64 __fastcall NativeMsh::PwrshCommon::TryLoadCoreCLR(NativeMsh::PwrshCommon *this, unsigned __int16 *a2)
{
  void **v3; // rdx
  __int64 v4; // rbx
  void **v5; // r8
  __int64 v7; // [rsp+30h] [rbp-30h] BYREF
  void *Src[3]; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int64 v9; // [rsp+50h] [rbp-10h]

  v9 = 7;
  Src[2] = 0;
  LOWORD(Src[0]) = 0;
  std::wstring::assign(Src, a2);
  std::wstring::operator+=(Src, L"CoreCLR.dll");
  v3 = Src;
  if ( v9 >= 8 )
    v3 = (void **)Src[0];
  v4 = (*(__int64 (__fastcall **)(_QWORD, void **, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 8LL))(
         *((_QWORD *)this + 2),
         v3,
         0,
         0);
  if ( !v4 )
    goto LABEL_7;
  v7 = 0;
  v5 = Src;
  if ( v9 >= 8 )
    v5 = (void **)Src[0];
  if ( (*(unsigned int (__fastcall **)(_QWORD, __int64, void **, __int64 *))(**((_QWORD **)this + 2) + 32LL))(
         *((_QWORD *)this + 2),
         1,
         v5,
         &v7) )
  {
    if ( v9 >= 8 )
      operator delete(Src[0]);
    return v4;
  }
  else
  {
LABEL_7:
    if ( v9 >= 8 )
      operator delete(Src[0]);
    return 0;
  }
}

```

## disassembly

```asm
0x180009160  mov     [rsp-8+arg_10], rbx
0x180009165  mov     [rsp-8+arg_18], rdi
0x18000916a  push    rbp
0x18000916b  mov     rbp, rsp
0x18000916e  sub     rsp, 60h
0x180009172  mov     rax, cs:__security_cookie
0x180009179  xor     rax, rsp
0x18000917c  mov     [rbp+var_8], rax
0x180009180  mov     rdi, rcx
0x180009183  mov     [rbp+var_10], 7
0x18000918b  mov     [rbp+var_18], 0
0x180009193  xor     eax, eax
0x180009195  mov     word ptr [rbp+Src], ax
0x180009199  lea     rcx, [rbp+Src]; void *
0x18000919d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800091a2  nop
0x1800091a3  lea     rdx, aCoreclrDll; "CoreCLR.dll"
0x1800091aa  lea     rcx, [rbp+Src]; Src
0x1800091ae  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x1800091b3  mov     rcx, [rdi+10h]
0x1800091b7  mov     rax, [rcx]
0x1800091ba  lea     rdx, [rbp+Src]
0x1800091be  cmp     [rbp+var_10], 8
0x1800091c3  cmovnb  rdx, [rbp+Src]
0x1800091c8  xor     r9d, r9d
0x1800091cb  xor     r8d, r8d
0x1800091ce  mov     rax, [rax+8]
0x1800091d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091d7  mov     rbx, rax
0x1800091da  test    rax, rax
0x1800091dd  jz      short loc_180009212
0x1800091df  mov     [rbp+var_30], 0
0x1800091e7  mov     rcx, [rdi+10h]
0x1800091eb  mov     rax, [rcx]
0x1800091ee  lea     r8, [rbp+Src]
0x1800091f2  cmp     [rbp+var_10], 8
0x1800091f7  cmovnb  r8, [rbp+Src]
0x1800091fc  lea     r9, [rbp+var_30]
0x180009200  mov     edx, 1
0x180009205  mov     rax, [rax+20h]
0x180009209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000920e  test    eax, eax
0x180009210  jnz     short loc_180009227
0x180009212  cmp     [rbp+var_10], 8
0x180009217  jb      short loc_180009223
0x180009219  mov     rcx, [rbp+Src]
0x18000921d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009223  xor     eax, eax
0x180009225  jmp     short loc_18000923B
0x180009227  cmp     [rbp+var_10], 8
0x18000922c  jb      short loc_180009238
0x18000922e  mov     rcx, [rbp+Src]
0x180009232  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009238  mov     rax, rbx
0x18000923b  mov     rcx, [rbp+var_8]
0x18000923f  xor     rcx, rsp; StackCookie
0x180009242  call    __security_check_cookie
0x180009247  lea     r11, [rsp+60h+var_s0]
0x18000924c  mov     rbx, [r11+20h]
0x180009250  mov     rdi, [r11+28h]
0x180009254  mov     rsp, r11
0x180009257  pop     rbp
0x180009258  retn
```
