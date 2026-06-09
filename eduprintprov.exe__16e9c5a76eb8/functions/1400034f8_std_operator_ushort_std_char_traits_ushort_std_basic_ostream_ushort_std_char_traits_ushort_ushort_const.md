# std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort,std::char_traits<ushort>> &,ushort const *)

- ea: `0x1400034f8`
- end: `0x14000367e`
- name: `??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z`
- size: `390`
- prototype: `__int64(_QWORD, _QWORD, ...)`
- caller_count: `16`
- callee_count: `3`
- tags: ``

## callers

- `0x140005f00`
- `0x140006724`
- `0x140007acc`
- `0x14000afac`
- `0x14000b4a0`
- `0x14000c88c`
- `0x14000d064`
- `0x14000d2a4`
- `0x14000e624`
- `0x14000e9a8`
- `0x14000ebec`
- `0x14000f0f0`
- `0x140010384`
- `0x140010f8c`
- `0x1400111bc`
- `0x140011bb0`

## callees

- `0x1400034f8`
- `0x140004c48`
- `0x140014010`

## import_xrefs

- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x14000359f`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x1400035e3`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x14000359f`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x1400035e3`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x140003623`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x140003623`
- `msvcp_win!?_Osfx@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAXXZ` at `0x140003639`
- `msvcp_win!?_Osfx@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAXXZ` at `0x140003639`
- `msvcp_win!?sputn@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAA_JPEBG_J@Z` at `0x1400035c2`
- `msvcp_win!?sputn@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAA_JPEBG_J@Z` at `0x1400035c2`
- `msvcp_win!?uncaught_exception@std@@YA_NXZ` at `0x14000362a`
- `msvcp_win!?uncaught_exception@std@@YA_NXZ` at `0x14000362a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *std::operator<<<unsigned short,std::char_traits<unsigned short>>(__int64 *a1, __int64 a2, __int64 a3, ...)
{
  __int64 *v4; // rdi
  unsigned int v5; // ebx
  __int64 v6; // r15
  __int64 v7; // r14
  __int64 v8; // r14
  __int64 v9; // rdx
  __int64 v10; // rax
  __int16 v11; // ax
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v15; // [rsp+20h] [rbp-38h] BYREF
  char v16; // [rsp+28h] [rbp-30h]

  v4 = a1;
  v5 = 0;
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(a2 + 2 * v6) );
  v7 = *(__int64 *)((char *)a1 + *(int *)(*a1 + 4) + 40);
  if ( v7 <= 0 || v7 <= v6 )
    v8 = 0;
  else
    v8 = v7 - v6;
  std::basic_ostream<unsigned short>::sentry::sentry(&v15, a1);
  if ( v16 )
  {
    v9 = *v4;
    v10 = *(int *)(*v4 + 4);
    if ( (*(_DWORD *)((_BYTE *)v4 + v10 + 24) & 0x1C0) != 0x40 )
    {
      while ( v8 > 0 )
      {
        try
        {
          v11 = std::basic_streambuf<unsigned short>::sputc(
                  *(__int64 *)((char *)v4 + *(int *)(*v4 + 4) + 72),
                  *(unsigned __int16 *)((char *)v4 + *(int *)(*v4 + 4) + 88));
        }
        catch ( ... )
        {
          LOBYTE(v12) = 1;
          std::basic_ios<unsigned short>::setstate((char *)a1 + *(int *)(*a1 + 4), 4, v12);
          v4 = a1;
          v5 = 0;
          goto LABEL_21;
        }
        if ( v11 == -1 )
          goto LABEL_18;
        --v8;
      }
      v9 = *v4;
    }
    if ( std::basic_streambuf<unsigned short>::sputn(*(__int64 *)((char *)v4 + *(int *)(v9 + 4) + 72), a2, v6) == v6 )
    {
      while ( v8 > 0 )
      {
        if ( (unsigned __int16)std::basic_streambuf<unsigned short>::sputc(
                                 *(__int64 *)((char *)v4 + *(int *)(*v4 + 4) + 72),
                                 *(unsigned __int16 *)((char *)v4 + *(int *)(*v4 + 4) + 88)) == 0xFFFF )
          goto LABEL_18;
        --v8;
      }
    }
    else
    {
LABEL_18:
      v5 = 4;
    }
    *(__int64 *)((char *)v4 + *(int *)(*v4 + 4) + 40) = 0;
  }
  else
  {
    v5 = 4;
  }
LABEL_21:
  std::basic_ios<unsigned short>::setstate((char *)v4 + *(int *)(*v4 + 4), v5, 0);
  if ( !std::uncaught_exception() )
    std::basic_ostream<unsigned short>::_Osfx(v15);
  v13 = *(_QWORD *)(*(int *)(*(_QWORD *)v15 + 4LL) + v15 + 72);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return v4;
}

```

## disassembly

```asm
0x1400034f8  mov     [rsp+arg_8], rbx
0x1400034fd  mov     [rsp+arg_18], rsi
0x140003502  mov     [rsp+arg_0], rcx
0x140003507  push    rdi
0x140003508  push    r12
0x14000350a  push    r13
0x14000350c  push    r14
0x14000350e  push    r15
0x140003510  sub     rsp, 30h
0x140003514  mov     r13, rdx
0x140003517  mov     rdi, rcx
0x14000351a  xor     esi, esi
0x14000351c  mov     ebx, esi
0x14000351e  mov     [rsp+58h+arg_10], ebx
0x140003522  or      r15, 0FFFFFFFFFFFFFFFFh
0x140003526  inc     r15
0x140003529  cmp     [rdx+r15*2], si
0x14000352e  jnz     short loc_140003526
0x140003530  mov     rax, [rcx]
0x140003533  movsxd  rcx, dword ptr [rax+4]
0x140003537  mov     r14, [rcx+rdi+28h]
0x14000353c  test    r14, r14
0x14000353f  jle     short loc_14000354B
0x140003541  cmp     r14, r15
0x140003544  jle     short loc_14000354B
0x140003546  sub     r14, r15
0x140003549  jmp     short loc_14000354E
0x14000354b  mov     r14, rsi
0x14000354e  mov     rdx, rdi
0x140003551  lea     rcx, [rsp+58h+var_38]
0x140003556  call    ??0sentry@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAA@AEAV12@@Z; std::basic_ostream<ushort>::sentry::sentry(std::basic_ostream<ushort> &)
0x14000355b  nop
0x14000355c  cmp     [rsp+58h+var_30], sil
0x140003561  jnz     short loc_14000356D
0x140003563  mov     ebx, 4
0x140003568  jmp     loc_140003614
0x14000356d  mov     rdx, [rdi]
0x140003570  movsxd  rax, dword ptr [rdx+4]
0x140003574  mov     ecx, [rax+rdi+18h]
0x140003578  and     ecx, 1C0h
0x14000357e  mov     r12d, 0FFFFh
0x140003584  cmp     ecx, 40h ; '@'
0x140003587  jz      short loc_1400035B3
0x140003589  test    r14, r14
0x14000358c  jle     short loc_1400035B0
0x14000358e  mov     rax, [rdi]
0x140003591  movsxd  rcx, dword ptr [rax+4]
0x140003595  movzx   edx, word ptr [rcx+rdi+58h]
0x14000359a  mov     rcx, [rcx+rdi+48h]
0x14000359f  call    cs:__imp_?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z; std::basic_streambuf<ushort>::sputc(ushort)
0x1400035a5  cmp     r12w, ax
0x1400035a9  jz      short loc_1400035EF
0x1400035ab  dec     r14
0x1400035ae  jmp     short loc_140003589
0x1400035b0  mov     rdx, [rdi]
0x1400035b3  movsxd  rcx, dword ptr [rdx+4]
0x1400035b7  mov     r8, r15
0x1400035ba  mov     rdx, r13
0x1400035bd  mov     rcx, [rcx+rdi+48h]
0x1400035c2  call    cs:__imp_?sputn@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAA_JPEBG_J@Z; std::basic_streambuf<ushort>::sputn(ushort const *,__int64)
0x1400035c8  cmp     rax, r15
0x1400035cb  jnz     short loc_1400035EF
0x1400035cd  test    r14, r14
0x1400035d0  jle     short loc_1400035F8
0x1400035d2  mov     rax, [rdi]
0x1400035d5  movsxd  rcx, dword ptr [rax+4]
0x1400035d9  movzx   edx, word ptr [rcx+rdi+58h]
0x1400035de  mov     rcx, [rcx+rdi+48h]
0x1400035e3  call    cs:__imp_?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z; std::basic_streambuf<ushort>::sputc(ushort)
0x1400035e9  cmp     r12w, ax
0x1400035ed  jnz     short loc_140003606
0x1400035ef  mov     ebx, 4
0x1400035f4  mov     [rsp+58h+arg_10], ebx
0x1400035f8  mov     rax, [rdi]
0x1400035fb  movsxd  rcx, dword ptr [rax+4]
0x1400035ff  mov     [rcx+rdi+28h], rsi
0x140003604  jmp     short loc_140003614
0x140003606  dec     r14
0x140003609  jmp     short loc_1400035CD
0x14000360b  mov     rdi, [rsp+58h+arg_0]
0x140003610  mov     ebx, [rsp+58h+arg_10]
0x140003614  mov     rax, [rdi]
0x140003617  movsxd  rcx, dword ptr [rax+4]
0x14000361b  add     rcx, rdi
0x14000361e  xor     r8d, r8d
0x140003621  mov     edx, ebx
0x140003623  call    cs:__imp_?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::setstate(int,bool)
0x140003629  nop
0x14000362a  call    cs:__imp_?uncaught_exception@std@@YA_NXZ; std::uncaught_exception(void)
0x140003630  test    al, al
0x140003632  jnz     short loc_140003640
0x140003634  mov     rcx, [rsp+58h+var_38]
0x140003639  call    cs:__imp_?_Osfx@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAXXZ; std::basic_ostream<ushort>::_Osfx(void)
0x14000363f  nop
0x140003640  mov     rdx, [rsp+58h+var_38]
0x140003645  mov     rax, [rdx]
0x140003648  movsxd  rcx, dword ptr [rax+4]
0x14000364c  mov     rcx, [rcx+rdx+48h]
0x140003651  test    rcx, rcx
0x140003654  jz      short loc_140003663
0x140003656  mov     rax, [rcx]
0x140003659  mov     rax, [rax+10h]
0x14000365d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003662  nop
0x140003663  mov     rax, rdi
0x140003666  mov     rbx, [rsp+58h+arg_8]
0x14000366b  mov     rsi, [rsp+58h+arg_18]
0x140003670  add     rsp, 30h
0x140003674  pop     r15
0x140003676  pop     r14
0x140003678  pop     r13
0x14000367a  pop     r12
0x14000367c  pop     rdi
0x14000367d  retn
```
