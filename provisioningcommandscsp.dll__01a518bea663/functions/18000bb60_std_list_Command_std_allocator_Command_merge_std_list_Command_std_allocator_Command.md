# std::list<Command,std::allocator<Command>>::merge(std::list<Command,std::allocator<Command>> &)

- ea: `0x18000bb60`
- end: `0x18000bd66`
- name: `?merge@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXAEAV12@@Z`
- size: `518`
- prototype: `void __fastcall(__int64 ***, __int64 ***)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000be80`

## callees

- `0x18000bb60`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000bd12`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000bd12`
- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000bcc5`
- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000bce1`
- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000bcc5`
- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000bce1`
- `msvcp110_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x18000bcd3`
- `msvcp110_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x18000bcef`
- `msvcp110_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x18000bcd3`
- `msvcp110_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x18000bcef`
- `msvcrt!wcstol` at `0x18000bbdd`
- `msvcrt!wcstol` at `0x18000bc34`
- `msvcrt!wcstol` at `0x18000bbdd`
- `msvcrt!wcstol` at `0x18000bc34`
- `msvcrt!_errno` at `0x18000bbc3`
- `msvcrt!_errno` at `0x18000bbf2`
- `msvcrt!_errno` at `0x18000bc1a`
- `msvcrt!_errno` at `0x18000bc49`
- `msvcrt!_errno` at `0x18000bbc3`
- `msvcrt!_errno` at `0x18000bbf2`
- `msvcrt!_errno` at `0x18000bc1a`
- `msvcrt!_errno` at `0x18000bc49`

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
0x18000bb60  cmp     rdx, rcx
0x18000bb63  jz      locret_18000BD65
0x18000bb69  mov     [rsp+arg_18], rbx
0x18000bb6e  push    rbp
0x18000bb6f  push    rsi
0x18000bb70  push    rdi
0x18000bb71  push    r12
0x18000bb73  push    r13
0x18000bb75  push    r14
0x18000bb77  push    r15
0x18000bb79  sub     rsp, 20h
0x18000bb7d  mov     r14, [rcx]
0x18000bb80  mov     rbp, rdx
0x18000bb83  mov     rdi, [rdx]
0x18000bb86  mov     r15, rcx
0x18000bb89  mov     r13, 1FFFFFFFFFFFFFEh
0x18000bb93  mov     rsi, [r14]
0x18000bb96  mov     rbx, [rdi]
0x18000bb99  cmp     rsi, r14
0x18000bb9c  jz      loc_18000BCF6
0x18000bba2  cmp     rbx, rdi
0x18000bba5  jz      loc_18000BD51
0x18000bbab  cmp     qword ptr [rbx+28h], 8
0x18000bbb0  lea     r12, [rbx+10h]
0x18000bbb4  jb      short loc_18000BBBA
0x18000bbb6  mov     r12, [r12]
0x18000bbba  mov     [rsp+58h+EndPtr], 0
0x18000bbc3  call    cs:__imp__errno
0x18000bbc9  mov     r8d, 0Ah; Radix
0x18000bbcf  lea     rdx, [rsp+58h+EndPtr]; EndPtr
0x18000bbd4  mov     rcx, r12; String
0x18000bbd7  mov     dword ptr [rax], 0
0x18000bbdd  call    cs:__imp_wcstol
0x18000bbe3  mov     [rsp+58h+arg_0], eax
0x18000bbe7  cmp     r12, [rsp+58h+EndPtr]
0x18000bbec  jz      loc_18000BCE8
0x18000bbf2  call    cs:__imp__errno
0x18000bbf8  cmp     dword ptr [rax], 22h ; '"'
0x18000bbfb  jz      loc_18000BCDA
0x18000bc01  lea     r12, [rsi+10h]
0x18000bc05  cmp     qword ptr [r12+18h], 8
0x18000bc0b  jb      short loc_18000BC11
0x18000bc0d  mov     r12, [r12]
0x18000bc11  mov     [rsp+58h+arg_10], 0
0x18000bc1a  call    cs:__imp__errno
0x18000bc20  mov     r8d, 0Ah; Radix
0x18000bc26  lea     rdx, [rsp+58h+arg_10]; EndPtr
0x18000bc2b  mov     rcx, r12; String
0x18000bc2e  mov     dword ptr [rax], 0
0x18000bc34  call    cs:__imp_wcstol
0x18000bc3a  mov     dword ptr [rsp+58h+EndPtr], eax
0x18000bc3e  cmp     r12, [rsp+58h+arg_10]
0x18000bc43  jz      loc_18000BCCC
0x18000bc49  call    cs:__imp__errno
0x18000bc4f  cmp     dword ptr [rax], 22h ; '"'
0x18000bc52  jz      short loc_18000BCBE
0x18000bc54  mov     eax, [rsp+58h+arg_0]
0x18000bc58  cmp     eax, dword ptr [rsp+58h+EndPtr]
0x18000bc5c  jge     short loc_18000BCB6
0x18000bc5e  mov     rcx, [r15+8]
0x18000bc62  mov     rax, r13
0x18000bc65  sub     rax, rcx
0x18000bc68  cmp     rax, 1
0x18000bc6c  jb      loc_18000BD0B
0x18000bc72  mov     rdx, [rbx]
0x18000bc75  lea     rax, [rcx+1]
0x18000bc79  mov     [r15+8], rax
0x18000bc7d  dec     qword ptr [rbp+8]
0x18000bc81  mov     rax, [rbx+8]
0x18000bc85  mov     [rax], rdx
0x18000bc88  mov     rax, [rdx+8]
0x18000bc8c  mov     [rax], rsi
0x18000bc8f  mov     rax, [rsi+8]
0x18000bc93  mov     [rax], rbx
0x18000bc96  mov     rax, [rdx+8]
0x18000bc9a  mov     rcx, [rsi+8]
0x18000bc9e  mov     [rsi+8], rax
0x18000bca2  mov     rax, [rbx+8]
0x18000bca6  mov     [rdx+8], rax
0x18000bcaa  mov     [rbx+8], rcx
0x18000bcae  mov     rbx, rdx
0x18000bcb1  jmp     loc_18000BB99
0x18000bcb6  mov     rsi, [rsi]
0x18000bcb9  jmp     loc_18000BB99
0x18000bcbe  lea     rcx, aStoiArgumentOu; "stoi argument out of range"
0x18000bcc5  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18000bccb  int     3; Trap to Debugger
0x18000bccc  lea     rcx, aInvalidStoiArg; "invalid stoi argument"
0x18000bcd3  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x18000bcd9  int     3; Trap to Debugger
0x18000bcda  lea     rcx, aStoiArgumentOu; "stoi argument out of range"
0x18000bce1  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18000bce7  int     3; Trap to Debugger
0x18000bce8  lea     rcx, aInvalidStoiArg; "invalid stoi argument"
0x18000bcef  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x18000bcf5  int     3; Trap to Debugger
0x18000bcf6  cmp     rbx, rdi
0x18000bcf9  jz      short loc_18000BD51
0x18000bcfb  mov     rax, [r15+8]
0x18000bcff  mov     rcx, [rbp+8]
0x18000bd03  sub     r13, rax
0x18000bd06  cmp     r13, rcx
0x18000bd09  jnb     short loc_18000BD19
0x18000bd0b  lea     rcx, aListTTooLong; "list<T> too long"
0x18000bd12  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000bd19  add     rax, rcx
0x18000bd1c  mov     [r15+8], rax
0x18000bd20  sub     [rbp+8], rcx
0x18000bd24  mov     rax, [rbx+8]
0x18000bd28  mov     [rax], rdi
0x18000bd2b  mov     rax, [rdi+8]
0x18000bd2f  mov     [rax], r14
0x18000bd32  mov     rax, [r14+8]
0x18000bd36  mov     [rax], rbx
0x18000bd39  mov     rax, [rdi+8]
0x18000bd3d  mov     rcx, [r14+8]
0x18000bd41  mov     [r14+8], rax
0x18000bd45  mov     rax, [rbx+8]
0x18000bd49  mov     [rdi+8], rax
0x18000bd4d  mov     [rbx+8], rcx
0x18000bd51  mov     rbx, [rsp+58h+arg_18]
0x18000bd56  add     rsp, 20h
0x18000bd5a  pop     r15
0x18000bd5c  pop     r14
0x18000bd5e  pop     r13
0x18000bd60  pop     r12
0x18000bd62  pop     rdi
0x18000bd63  pop     rsi
0x18000bd64  pop     rbp
0x18000bd65  retn
```
