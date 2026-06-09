# std::list<Command,std::allocator<Command>>::merge(std::list<Command,std::allocator<Command>> &)

- ea: `0x1400098e8`
- end: `0x140009aee`
- name: `?merge@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXAEAV12@@Z`
- size: `518`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140009c08`

## callees

- `0x1400098e8`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140009a9a`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140009a9a`
- `msvcp110_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x140009a5b`
- `msvcp110_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x140009a77`
- `msvcp110_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x140009a5b`
- `msvcp110_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x140009a77`
- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x140009a4d`
- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x140009a69`
- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x140009a4d`
- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x140009a69`
- `msvcrt!wcstol` at `0x140009965`
- `msvcrt!wcstol` at `0x1400099bc`
- `msvcrt!wcstol` at `0x140009965`
- `msvcrt!wcstol` at `0x1400099bc`
- `msvcrt!_errno` at `0x14000994b`
- `msvcrt!_errno` at `0x14000997a`
- `msvcrt!_errno` at `0x1400099a2`
- `msvcrt!_errno` at `0x1400099d1`
- `msvcrt!_errno` at `0x14000994b`
- `msvcrt!_errno` at `0x14000997a`
- `msvcrt!_errno` at `0x1400099a2`
- `msvcrt!_errno` at `0x1400099d1`

## pseudocode

```c
void __fastcall std::list<Command>::merge(__int64 ***a1, __int64 ***a2)
{
  __int64 **v2; // r14
  __int64 **v4; // rdi
  __int64 **v6; // rsi
  __int64 **v7; // rbx
  const wchar_t *v8; // r12
  const wchar_t *v9; // r12
  __int64 **v10; // rcx
  __int64 *v11; // rdx
  __int64 *v12; // rcx
  __int64 **v13; // rax
  unsigned __int64 v14; // rcx
  __int64 *v15; // rcx
  int v16; // [rsp+60h] [rbp+8h]
  wchar_t *EndPtr; // [rsp+68h] [rbp+10h] BYREF
  wchar_t *v18; // [rsp+70h] [rbp+18h] BYREF

  if ( a2 != a1 )
  {
    v2 = *a1;
    v4 = *a2;
    v6 = (__int64 **)**a1;
    v7 = (__int64 **)**a2;
    while ( v6 != v2 )
    {
      if ( v7 == v4 )
        return;
      v8 = (const wchar_t *)(v7 + 2);
      if ( (unsigned __int64)v7[5] >= 8 )
        v8 = *(const wchar_t **)v8;
      EndPtr = 0;
      *_errno() = 0;
      v16 = wcstol(v8, &EndPtr, 10);
      if ( v8 == EndPtr )
      {
        std::_Xinvalid_argument("invalid stoi argument");
        __debugbreak();
      }
      if ( *_errno() == 34 )
      {
        std::_Xout_of_range("stoi argument out of range");
        __debugbreak();
      }
      v9 = (const wchar_t *)(v6 + 2);
      if ( (unsigned __int64)v6[5] >= 8 )
        v9 = *(const wchar_t **)v9;
      v18 = 0;
      *_errno() = 0;
      LODWORD(EndPtr) = wcstol(v9, &v18, 10);
      if ( v9 == v18 )
      {
        std::_Xinvalid_argument("invalid stoi argument");
        __debugbreak();
      }
      if ( *_errno() == 34 )
      {
        std::_Xout_of_range("stoi argument out of range");
        __debugbreak();
      }
      if ( v16 >= (int)EndPtr )
      {
        v6 = (__int64 **)*v6;
      }
      else
      {
        v10 = a1[1];
        if ( v10 == (__int64 **)0x1FFFFFFFFFFFFFELL )
          goto LABEL_23;
        v11 = *v7;
        a1[1] = (__int64 **)((char *)v10 + 1);
        a2[1] = (__int64 **)((char *)a2[1] - 1);
        *v7[1] = (__int64)v11;
        *(_QWORD *)v11[1] = v6;
        *v6[1] = (__int64)v7;
        v12 = v6[1];
        v6[1] = (__int64 *)v11[1];
        v11[1] = (__int64)v7[1];
        v7[1] = v12;
        v7 = (__int64 **)v11;
      }
    }
    if ( v7 != v4 )
    {
      v13 = a1[1];
      v14 = (unsigned __int64)a2[1];
      if ( 0x1FFFFFFFFFFFFFELL - (__int64)v13 < v14 )
LABEL_23:
        std::_Xlength_error("list<T> too long");
      a1[1] = (__int64 **)((char *)v13 + v14);
      a2[1] = (__int64 **)((char *)a2[1] - v14);
      *v7[1] = (__int64)v4;
      *v4[1] = (__int64)v2;
      *v2[1] = (__int64)v7;
      v15 = v2[1];
      v2[1] = v4[1];
      v4[1] = v7[1];
      v7[1] = v15;
    }
  }
}

```

## disassembly

```asm
0x1400098e8  cmp     rdx, rcx
0x1400098eb  jz      locret_140009AED
0x1400098f1  mov     [rsp+arg_18], rbx
0x1400098f6  push    rbp
0x1400098f7  push    rsi
0x1400098f8  push    rdi
0x1400098f9  push    r12
0x1400098fb  push    r13
0x1400098fd  push    r14
0x1400098ff  push    r15
0x140009901  sub     rsp, 20h
0x140009905  mov     r14, [rcx]
0x140009908  mov     rbp, rdx
0x14000990b  mov     rdi, [rdx]
0x14000990e  mov     r15, rcx
0x140009911  mov     r13, 1FFFFFFFFFFFFFEh
0x14000991b  mov     rsi, [r14]
0x14000991e  mov     rbx, [rdi]
0x140009921  cmp     rsi, r14
0x140009924  jz      loc_140009A7E
0x14000992a  cmp     rbx, rdi
0x14000992d  jz      loc_140009AD9
0x140009933  cmp     qword ptr [rbx+28h], 8
0x140009938  lea     r12, [rbx+10h]
0x14000993c  jb      short loc_140009942
0x14000993e  mov     r12, [r12]
0x140009942  mov     [rsp+58h+EndPtr], 0
0x14000994b  call    cs:__imp__errno
0x140009951  mov     r8d, 0Ah; Radix
0x140009957  lea     rdx, [rsp+58h+EndPtr]; EndPtr
0x14000995c  mov     rcx, r12; String
0x14000995f  mov     dword ptr [rax], 0
0x140009965  call    cs:__imp_wcstol
0x14000996b  mov     [rsp+58h+arg_0], eax
0x14000996f  cmp     r12, [rsp+58h+EndPtr]
0x140009974  jz      loc_140009A70
0x14000997a  call    cs:__imp__errno
0x140009980  cmp     dword ptr [rax], 22h ; '"'
0x140009983  jz      loc_140009A62
0x140009989  lea     r12, [rsi+10h]
0x14000998d  cmp     qword ptr [r12+18h], 8
0x140009993  jb      short loc_140009999
0x140009995  mov     r12, [r12]
0x140009999  mov     [rsp+58h+arg_10], 0
0x1400099a2  call    cs:__imp__errno
0x1400099a8  mov     r8d, 0Ah; Radix
0x1400099ae  lea     rdx, [rsp+58h+arg_10]; EndPtr
0x1400099b3  mov     rcx, r12; String
0x1400099b6  mov     dword ptr [rax], 0
0x1400099bc  call    cs:__imp_wcstol
0x1400099c2  mov     dword ptr [rsp+58h+EndPtr], eax
0x1400099c6  cmp     r12, [rsp+58h+arg_10]
0x1400099cb  jz      loc_140009A54
0x1400099d1  call    cs:__imp__errno
0x1400099d7  cmp     dword ptr [rax], 22h ; '"'
0x1400099da  jz      short loc_140009A46
0x1400099dc  mov     eax, [rsp+58h+arg_0]
0x1400099e0  cmp     eax, dword ptr [rsp+58h+EndPtr]
0x1400099e4  jge     short loc_140009A3E
0x1400099e6  mov     rcx, [r15+8]
0x1400099ea  mov     rax, r13
0x1400099ed  sub     rax, rcx
0x1400099f0  cmp     rax, 1
0x1400099f4  jb      loc_140009A93
0x1400099fa  mov     rdx, [rbx]
0x1400099fd  lea     rax, [rcx+1]
0x140009a01  mov     [r15+8], rax
0x140009a05  dec     qword ptr [rbp+8]
0x140009a09  mov     rax, [rbx+8]
0x140009a0d  mov     [rax], rdx
0x140009a10  mov     rax, [rdx+8]
0x140009a14  mov     [rax], rsi
0x140009a17  mov     rax, [rsi+8]
0x140009a1b  mov     [rax], rbx
0x140009a1e  mov     rax, [rdx+8]
0x140009a22  mov     rcx, [rsi+8]
0x140009a26  mov     [rsi+8], rax
0x140009a2a  mov     rax, [rbx+8]
0x140009a2e  mov     [rdx+8], rax
0x140009a32  mov     [rbx+8], rcx
0x140009a36  mov     rbx, rdx
0x140009a39  jmp     loc_140009921
0x140009a3e  mov     rsi, [rsi]
0x140009a41  jmp     loc_140009921
0x140009a46  lea     rcx, aStoiArgumentOu; "stoi argument out of range"
0x140009a4d  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x140009a53  int     3; Trap to Debugger
0x140009a54  lea     rcx, aInvalidStoiArg; "invalid stoi argument"
0x140009a5b  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x140009a61  int     3; Trap to Debugger
0x140009a62  lea     rcx, aStoiArgumentOu; "stoi argument out of range"
0x140009a69  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x140009a6f  int     3; Trap to Debugger
0x140009a70  lea     rcx, aInvalidStoiArg; "invalid stoi argument"
0x140009a77  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x140009a7d  int     3; Trap to Debugger
0x140009a7e  cmp     rbx, rdi
0x140009a81  jz      short loc_140009AD9
0x140009a83  mov     rax, [r15+8]
0x140009a87  mov     rcx, [rbp+8]
0x140009a8b  sub     r13, rax
0x140009a8e  cmp     r13, rcx
0x140009a91  jnb     short loc_140009AA1
0x140009a93  lea     rcx, aListTTooLong; "list<T> too long"
0x140009a9a  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x140009aa1  add     rax, rcx
0x140009aa4  mov     [r15+8], rax
0x140009aa8  sub     [rbp+8], rcx
0x140009aac  mov     rax, [rbx+8]
0x140009ab0  mov     [rax], rdi
0x140009ab3  mov     rax, [rdi+8]
0x140009ab7  mov     [rax], r14
0x140009aba  mov     rax, [r14+8]
0x140009abe  mov     [rax], rbx
0x140009ac1  mov     rax, [rdi+8]
0x140009ac5  mov     rcx, [r14+8]
0x140009ac9  mov     [r14+8], rax
0x140009acd  mov     rax, [rbx+8]
0x140009ad1  mov     [rdi+8], rax
0x140009ad5  mov     [rbx+8], rcx
0x140009ad9  mov     rbx, [rsp+58h+arg_18]
0x140009ade  add     rsp, 20h
0x140009ae2  pop     r15
0x140009ae4  pop     r14
0x140009ae6  pop     r13
0x140009ae8  pop     r12
0x140009aea  pop     rdi
0x140009aeb  pop     rsi
0x140009aec  pop     rbp
0x140009aed  retn
```
